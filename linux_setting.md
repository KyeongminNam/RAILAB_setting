
### graphic driver install
https://donghyun99.tistory.com/18

### cuda 11.8, cudnn 8.7.0 on Ubuntu 20.04
https://velog.io/@qaszx1004/Install-CUDA11.8-CUDNN-on-Ubuntu-20.04
```
# write in ~/.bashrc and source
export PATH="/usr/local/cuda/bin:$PATH"
export LD_LIBRARY_PATH="/usr/local/cuda/lib64:$LD_LIBRARY_PATH"
```

Cuda : https://developer.nvidia.com/cuda-toolkit-archive  
Cudnn: https://developer.nvidia.com/rdp/cudnn-archive
```
sudo ln -sf libcudnn.so.8.7.0 libcudnn.so.8
sudo ln -sf libcudnn.so.8 libcudnn.so

sudo ln -sf libcudnn_adv_infer.so.8.7.0 libcudnn_adv_infer.so.8
sudo ln -sf libcudnn_adv_infer.so.8 libcudnn_adv_infer.so

sudo ln -sf libcudnn_adv_train.so.8.7.0 libcudnn_adv_train.so.8
sudo ln -sf libcudnn_adv_train.so.8 libcudnn_adv_train.so

sudo ln -sf libcudnn_cnn_infer.so.8.7.0 libcudnn_cnn_infer.so.8
sudo ln -sf libcudnn_cnn_infer.so.8 libcudnn_cnn_infer.so

sudo ln -sf libcudnn_cnn_train.so.8.7.0 libcudnn_cnn_train.so.8
sudo ln -sf libcudnn_cnn_train.so.8 libcudnn_cnn_train.so

sudo ln -sf libcudnn_ops_infer.so.8.7.0 libcudnn_ops_infer.so.8
sudo ln -sf libcudnn_ops_infer.so.8 libcudnn_ops_infer.so

sudo ln -sf libcudnn_ops_train.so.8.7.0 libcudnn_ops_train.so.8
sudo ln -sf libcudnn_ops_train.so.8 libcudnn_ops_train.so
```


```
nvidia-smi
nvcc -V
cat /usr/local/cuda/include/cudnn_version.h | grep CUDNN_MAJOR -A 2
```

### anaconda install  
https://record-everything.tistory.com/entry/Ubuntu-2004-%EC%9A%B0%EB%B6%84%ED%88%AC%EC%97%90-%EC%95%84%EB%82%98%EC%BD%98%EB%8B%A4-%EC%84%A4%EC%B9%98-%EB%B0%8F-Python-%EA%B0%80%EC%83%81%ED%99%98%EA%B2%BD-%EC%84%A4%EC%A0%95

### miniconda install
https://docs.anaconda.com/free/miniconda/

### other dependency  
```
sudo apt install git cmake minizip ffmpeg
sudo apt-get install tmux
sudo apt-get install terminator
sudo apt install git-all
sudo apt-get install htop
sudo apt-get install gpustat
sudo apt-get install imagemagick

pip install "ruamel.yaml<0.18.0"
```

### memory check
buffer cache delete : `sudo echo 3 > sudo /proc/sys/vm/drop_caches`
