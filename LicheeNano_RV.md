# Sipeed LicheeRV Nano

## nccc build 

```
export RISCV_ROOT_PATH="/home/nnn/licheerv_nano/duo-sdk/riscv64-linux-musl-x86_64/"
cmake -B build/c906 -DCMAKE_TOOLCHAIN_FILE=../toolchains/c906-v240.toolchain.cmake -DCMAKE_BUILD_TYPE=release -DNCNN_BUILD_TESTS=ON -DNCNN_OPENMP=OFF -DNCNN_THREADS=OFF -DNCNN_RUNTIME_CPU=OFF -DNCNN_RVV=ON -DNCNN_SIMPLEOCV=ON -DNCNN_BUILD_EXAMPLES=OFF . &&
cmake --build build/c906 &&
cmake --install build/c906 --prefix install/c906
```

# Spec 
```
# uname -m
riscv64

# uname -v
#1 PREEMPT Tue May 28 17:27:59 HKT 2024

# cat /proc/cpuinfo
processor       : 0
hart            : 0
isa             : rv64imafdvcsu
mmu             : sv39

# cat /proc/meminfo
MemTotal:         162668 kB
MemFree:          131620 kB
MemAvailable:     133448 kB
Buffers:             692 kB
Cached:             4228 kB
SwapCached:            0 kB
Active:             1904 kB
Inactive:           8192 kB
Active(anon):        140 kB
Inactive(anon):     5272 kB
Active(file):       1764 kB
Inactive(file):     2920 kB
Unevictable:           0 kB
Mlocked:               0 kB
SwapTotal:             0 kB
SwapFree:              0 kB
Dirty:                36 kB
Writeback:             0 kB
AnonPages:          5196 kB
Mapped:             2908 kB
Shmem:               236 kB
KReclaimable:       3084 kB
Slab:               9744 kB
SReclaimable:       3084 kB
SUnreclaim:         6660 kB
KernelStack:        1168 kB
PageTables:          488 kB
NFS_Unstable:          0 kB
Bounce:                0 kB
WritebackTmp:          0 kB
CommitLimit:       81332 kB
Committed_AS:       8288 kB
VmallocTotal:   67108863 kB
VmallocUsed:        4916 kB
VmallocChunk:          0 kB
Percpu:               32 kB
CmaTotal:              0 kB
CmaFree:               0 kB

# cat /etc/os-release
NAME=Buildroot
VERSION=-g82a0b70d8-dirty
ID=buildroot
VERSION_ID=2023.11.2
PRETTY_NAME="Buildroot 2023.11.2"

# cat /etc/issue
Welcome to Linux

# df -h
Filesystem                Size      Used Available Use% Mounted on
/dev/mmcblk0p2           28.5G    522.8M     26.6G   2% /
devtmpfs                 78.1M         0     78.1M   0% /dev
tmpfs                    79.4M         0     79.4M   0% /dev/shm
tmpfs                    79.4M     84.0K     79.3M   0% /tmp
tmpfs                    79.4M    140.0K     79.3M   0% /run
/dev/mmcblk0p1           16.0M     10.6M      5.4M  66% /boot

```

# Result 

```
# ./benchncnn 4 1 0 -1 1
loop_count = 4
num_threads = 1
powersave = 0
gpu_device = -1
cooling_down = 1
          squeezenet  min =  258.75  max =  265.83  avg =  260.87
     squeezenet_int8  min = 9659.92  max = 9667.19  avg = 9665.30
           mobilenet  min =  398.63  max =  401.00  avg =  399.75
      mobilenet_int8  min = 14793.44  max = 14806.26  avg = 14798.42
        mobilenet_v2  min =  297.37  max =  299.08  avg =  298.39
        mobilenet_v3  min =  243.94  max =  244.84  avg =  244.30
          shufflenet  min =  441.43  max =  444.05  avg =  442.29
       shufflenet_v2  min =  281.79  max =  282.26  avg =  281.99
             mnasnet  min =  298.63  max =  299.22  avg =  298.87
     proxylessnasnet  min =  349.01  max =  356.01  avg =  350.96
     efficientnet_b0  min =  423.65  max =  431.97  avg =  426.17
   efficientnetv2_b0  min =  587.97  max =  588.66  avg =  588.39
        regnety_400m  min =  416.59  max =  418.47  avg =  417.32
           blazeface  min =  133.46  max =  133.72  avg =  133.57
           googlenet  min =  995.92  max =  996.87  avg =  996.34
      googlenet_int8  min = 21981.34  max = 22006.10  avg = 21994.08
            resnet18  min =  709.38  max =  710.55  avg =  709.81
       resnet18_int8  min = 22158.76  max = 22167.79  avg = 22161.85
Killed
```


# Reference

LicheeRV-Nano-Build<br>
https://github.com/sipeed/LicheeRV-Nano-Build<br>

