# Luckfox Pico Max

```
# uname -m
armv7l

# uname -a
Linux luckfox 5.10.110 #1 Tue Nov 14 18:06:04 CST 2023 armv7l GNU/Linux

# cat /proc/cpu
cpu/     cpuinfo

# cat /proc/cpuinfo
processor       : 0
model name      : ARMv7 Processor rev 5 (v7l)
BogoMIPS        : 17.47
Features        : half thumb fastmult vfp edsp neon vfpv3 tls vfpv4 idiva idivt vfpd32 lpae
CPU implementer : 0x41
CPU architecture: 7
CPU variant     : 0x0
CPU part        : 0xc07
CPU revision    : 5
Hardware        : Generic DT based system
Revision        : 0000
Serial          : eb8d68468b29abe9

# cat /proc/meminfo
MemTotal:         186388 kB
MemFree:          156540 kB
MemAvailable:     164424 kB
Buffers:               0 kB
Cached:            11248 kB
SwapCached:            0 kB
Active:             6272 kB
Inactive:           9876 kB
Active(anon):        200 kB
Inactive(anon):     5252 kB
Active(file):       6072 kB
Inactive(file):     4624 kB
Unevictable:           0 kB
Mlocked:               0 kB
SwapTotal:             0 kB
SwapFree:              0 kB
Dirty:                 4 kB
Writeback:             0 kB
AnonPages:          4920 kB
Mapped:             7520 kB
Shmem:               552 kB
KReclaimable:       3840 kB
Slab:               8224 kB
SReclaimable:       3840 kB
SUnreclaim:         4384 kB
KernelStack:         576 kB
PageTables:          436 kB
NFS_Unstable:          0 kB
Bounce:                0 kB
WritebackTmp:          0 kB
CommitLimit:       93192 kB
Committed_AS:      19304 kB
VmallocTotal:    1032192 kB
VmallocUsed:        3580 kB
VmallocChunk:          0 kB
Percpu:               32 kB
CmaTotal:          67584 kB
CmaAllocated:         12 kB
CmaReleased:       67572 kB
CmaFree:               0 kB

#  cat /etc/os-release
NAME=Buildroot
VERSION=-g68ee52d1d
ID=buildroot
VERSION_ID=2023.02.6
PRETTY_NAME="Buildroot 2023.02.6"

#  cat /etc/issue
Welcome to luckfox pico

# df -h
Filesystem                Size      Used Available Use% Mounted on
ubi0:rootfs             181.3M     60.0M    121.3M  33% /
devtmpfs                 90.9M         0     90.9M   0% /dev
tmpfs                    91.0M         0     91.0M   0% /dev/shm
tmpfs                    91.0M     64.0K     90.9M   0% /tmp
tmpfs                    91.0M    488.0K     90.5M   1% /run
/dev/ubi4_0              20.2M     17.1M      3.0M  85% /oem
/dev/ubi5_0               2.2M     28.0K      2.2M   1% /userdata
```

## Result

```
#  ./benchncnn 4 1 0 -1 1
loop_count = 4
num_threads = 1
powersave = 0
gpu_device = -1
cooling_down = 1
        squeezenet  min =  459.52  max =  460.33  avg =  459.80
     squeezenet_int8  min =  309.75  max =  310.10  avg =  309.92
           mobilenet  min =  797.15  max =  797.50  avg =  797.37
      mobilenet_int8  min =  414.08  max =  414.60  avg =  414.35
        mobilenet_v2  min =  517.26  max =  518.28  avg =  517.69
        mobilenet_v3  min =  422.17  max =  422.56  avg =  422.37
          shufflenet  min =  275.52  max =  276.03  avg =  275.78
       shufflenet_v2  min =  247.08  max =  247.42  avg =  247.29
             mnasnet  min =  514.06  max =  514.51  avg =  514.22
     proxylessnasnet  min =  590.52  max =  590.94  avg =  590.71
     efficientnet_b0  min =  873.99  max =  874.59  avg =  874.19
   efficientnetv2_b0  min = 1028.21  max = 1029.42  avg = 1028.89
        regnety_400m  min =  628.44  max =  628.85  avg =  628.62
           blazeface  min =   73.65  max =   74.32  avg =   74.12
           googlenet  min = 1477.98  max = 1479.47  avg = 1478.75
      googlenet_int8  min =  947.31  max =  949.72  avg =  948.40
Killed

```


