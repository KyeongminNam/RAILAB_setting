## Step 0. Setup
- reservation: http://143.248.6.101:24/
- server information
```
ssh user@143.248.6.83 (password: hubo)
ssh railab@143.248.6.101/105/168 (password: railab)
ssh user@143.248.249.67/108/145/146 (password: raiboisKing)
ssh user@143.248.8.10 (password: raiboisKing)
ssh user@143.248.247.189 (password: RaiboisKing)
```
- add my account `nkm`

```
ssh user@143.248.6.83
sudo su
adduser nkm
sudo usermod -aG docker nkm
exit
```
- add git ssh in nkm@143.248.6.83
```
# exit user and log in as nkm
ssh-keygen
cat .ssh/id_rsa.pub
git clone git@github.com:railabatkaist/Railab_Manual.git
```

- modify Dockerfile, runner.bash  
```
cd Railab_Manual/raisim_docker

nano Dockerfile 
#modify 6006 to 4444  

nano runner.bash
#modify 6006:6006 to 4444:4444, rsg to nkm  

docker build -t nkm .
# . to navigate `Railab_Manual/raisim_docker`  

bash runner.bash

docker ps -a 
# you can see name of nkm is initialized to random (ex. loving_matsumoto)
docker rename loving_matsumoto nkm
docker ps -a
# you can see name of nkm is nkm

exit
# back to local
```

- How to start docker


```
# at local, go to server
nkm@nkm-com2:~$ ssh nkm@143.248.6.83
nkm@nkm-com2:~$ ssh -L 4444:localhost:4444 nkm@143.248.6.105

#then,nkm@user-TRX40-DESIGNARE:~$ 

# at server, go to docker
nkm@user-TRX40-DESIGNARE:~$ docker start nkm
nkm@user-TRX40-DESIGNARE:~$ docker attach nkm

# then, root@4442112939a3:/# 
```

- Some common commands
```
python setup.py develop --CMAKE_PREFIX_PATH ../raisimLib/raisim/linux


git checkout -- .

```

## 1. How to transer file btw docker & local

- from docker to server  
nkm@user-TRX40-DESIGNARE:~$ `docker cp nkm:/root/aaa .`  
`docker cp nkm:/root/../raisim_ws/raisimGymForSegway/raisimGymForSegway/data/ .`


- from server to docker  
nkm@user-TRX40-DESIGNARE:~$ `docker cp aaa nkm:/root`  

- from server to local  
nkm@nkm-com2:~$ `scp nkm@143.248.6.83:aaa .`  
when moving folder, add option `-r`  
`scp -r nkm@143.248.6.105:data/raiway_sit_down_GRU/ .`

- from local to server  
nkm@nkm-com2:~$ `scp aaa nkm@143.248.6.83`

