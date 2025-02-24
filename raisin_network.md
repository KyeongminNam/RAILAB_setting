## Step 0. clone & install depancancy

- clone `raisin_master` as `raisin_network_ws`
```
cd raisin_network_ws
git clone git@github.com:railabatkaist/raisin_master.git .
```

- clone `raisin`, `raisin_plugin`, `raiway_controller`, `raibo_controller` to `raisin_master/src`

```
# navigate raisin
chmod +x ./install_dependencies.sh
./install_dependencies.sh

# navigate raisin_network_ws
python3 raisin_workspace_setup.py
```

- build
```
# navigate raisin_network_ws
mkdir build && cd build
cmake .. -G Ninja -DCMAKE_BUILD_TYPE=Release
ninja -j 32
```

- pip3 install
```
Sphinx                               4.5.0
sphinx-panels                        0.6.0
sphinx-rtd-theme                     1.0.0
sphinx-tabs                          3.4.7
sphinxcontrib-applehelp              1.0.4
sphinxcontrib-devhelp                1.0.2
sphinxcontrib-htmlhelp               2.0.1
sphinxcontrib-jquery                 4.1
sphinxcontrib-jsmath                 1.0.1
sphinxcontrib-qthelp                 1.0.3
sphinxcontrib-serializinghtml        1.1.5
sphinxcontrib-youtube                1.3.0
```

- run  
    navigate raisin_network_ws  
    - node: `./build/src/raisin/raisin_raibo2/raisin_raibo2_node`  
    - node, real: `./build/src/raisin/raisin_raibo2/raisin_raibo2_node real`  
    - gui: `./build/src/raisin/raisin_gui/raisin_gui/raisin_gui`

