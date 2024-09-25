# How to Debug
1. Run `python setup develop --Debug`, then `<prj>_debug_app` appears in `raisimGym/env/bin`.  

2. Using Clion, put program argument `rsc_folder_directory yaml_directory`  
i.e. `/home/nkm/raisim_ws/raisimGymForRaisin/rsc /home/nkm/raisim_ws/raisimGymForRaisin/raisimGymTorch/env/envs/rsg_raibo_pj2/cfg.yaml`

default valgrind option: `--leak-check=full --leak-resolution=med --track-origins=yes --vgdb=no`

3. How to use GDB
```
Thread 34 "rsg_raibo_pj2_d" received signal SIGSEGV, Segmentation fault.

(gdb) thread 34
[Switching to thread 34 (Thread 0x7fedf7fe7700 (LWP 3832))]

(gdb) bt
~~~
#4  0x0000560d19f81e32 in Eigen::internal::first_aligned_impl<16, Eigen::Block<Eigen::Matrix<int, -1, 1, 0, -1, 1>, -1, 1, false>, false>::run (m=...) at /usr/include/eigen3/Eigen/src/Core/DenseCoeffsBase.h:627
Backtrace stopped: frame did not save the PC
```

**Backtrace stopped: frame did not save the PC** meaning
gdb was unable to continue analyzing the call stack because of corruption or a lack of proper information to determine the return address in the previous stack frame. 

