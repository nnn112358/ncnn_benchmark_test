# Raspberry Pi Zero 2 W (Bullseye 32 Bit)

```
 $ uname -a
Linux raspizero 6.1.21-v7+ #1642 SMP Mon Apr  3 17:20:52 BST 2023 armv7l GNU/Linux

 $ cat /etc/os-release
PRETTY_NAME="Raspbian GNU/Linux 11 (bullseye)"
NAME="Raspbian GNU/Linux"
VERSION_ID="11"
VERSION="11 (bullseye)"
VERSION_CODENAME=bullseye
ID=raspbian
ID_LIKE=debian
HOME_URL="http://www.raspbian.org/"
SUPPORT_URL="http://www.raspbian.org/RaspbianForums"
BUG_REPORT_URL="http://www.raspbian.org/RaspbianBugs"
```

#### build ncnn 

```
$ git clone https://github.com/Tencent/ncnn
$ cd ncnn/
$ cmake -B build/arm_raspi -DNCNN_SIMPLEOCV=ON -DCMAKE_BUILD_TYPE=Release -DNCNN_VULKAN=OFF -DNCNN_BUILD_EXAMPLES=OFF .
$ cmake --build build/arm_raspi &&  cmake --install build/arm_raspi --prefix install/arm_raspi
```
#### result 

```
$ cd build/arm_raspi/benchmark
$ ./benchncnn 4 1 0 -1 1
loop_count = 4
num_threads = 1
powersave = 0
gpu_device = -1
cooling_down = 1
          squeezenet  min =  938.66  max =  945.04  avg =  940.61
     squeezenet_int8  min =  690.06  max =  690.78  avg =  690.35
           mobilenet  min = 1762.97  max = 1764.23  avg = 1763.62
      mobilenet_int8  min = 1271.40  max = 1271.81  avg = 1271.59
        mobilenet_v2  min = 1093.92  max = 1095.76  avg = 1094.86
        mobilenet_v3  min =  889.74  max =  891.29  avg =  890.25
          shufflenet  min =  529.11  max =  530.60  avg =  529.56
       shufflenet_v2  min =  501.60  max =  502.76  avg =  502.05
             mnasnet  min = 1072.78  max = 1074.21  avg = 1073.42
     proxylessnasnet  min = 1190.77  max = 1191.60  avg = 1191.08
     efficientnet_b0  min = 1860.71  max = 1860.98  avg = 1860.90
   efficientnetv2_b0  min = 2171.31  max = 2171.81  avg = 2171.53
        regnety_400m  min = 1328.42  max = 1330.83  avg = 1329.18
           blazeface  min =  140.93  max =  140.99  avg =  140.97
           googlenet  min = 3319.30  max = 3321.45  avg = 3320.41
      googlenet_int8  min = 2208.13  max = 2209.77  avg = 2208.91
            resnet18  min = 2632.64  max = 2634.94  avg = 2633.43
       resnet18_int8  min = 1620.20  max = 1621.80  avg = 1621.00
             alexnet  min = 1750.73  max = 1752.68  avg = 1751.36

$ ./benchncnn 4 4 0 -1 1
loop_count = 4
num_threads = 4
powersave = 0
gpu_device = -1
cooling_down = 1
          squeezenet  min =  272.60  max =  273.21  avg =  272.91
     squeezenet_int8  min =  206.47  max =  207.07  avg =  206.68
           mobilenet  min =  470.76  max =  471.19  avg =  470.97
      mobilenet_int8  min =  326.04  max =  329.53  avg =  326.97
        mobilenet_v2  min =  315.18  max =  315.64  avg =  315.50
        mobilenet_v3  min =  280.67  max =  282.22  avg =  281.08
          shufflenet  min =  195.33  max =  195.85  avg =  195.50
       shufflenet_v2  min =  159.98  max =  160.32  avg =  160.13
             mnasnet  min =  305.17  max =  305.94  avg =  305.64
     proxylessnasnet  min =  414.62  max =  415.66  avg =  414.99
     efficientnet_b0  min =  541.81  max =  542.51  avg =  542.05
   efficientnetv2_b0  min =  597.78  max =  598.76  avg =  598.09
        regnety_400m  min =  458.66  max =  459.02  avg =  458.83
           blazeface  min =   48.32  max =   48.62  avg =   48.51
           googlenet  min =  908.36  max =  909.12  avg =  908.63
      googlenet_int8  min =  628.26  max =  630.62  avg =  628.92
            resnet18  min =  723.13  max =  723.70  avg =  723.40
       resnet18_int8  min =  438.34  max =  438.90  avg =  438.65
             alexnet  min =  504.77  max =  514.60  avg =  508.30
```

# Raspberry Pi Zero 2 W (bookworm 64 Bit)

```
 $ $ uname -a
Linux raspberrypi 6.6.31+rpt-rpi-v8 #1 SMP PREEMPT Debian 1:6.6.31-1+rpt1 (2024-05-29) aarch64 GNU/Linux

$  cat /etc/os-release
PRETTY_NAME="Debian GNU/Linux 12 (bookworm)"
NAME="Debian GNU/Linux"
VERSION_ID="12"
VERSION="12 (bookworm)"
VERSION_CODENAME=bookworm
ID=debian
HOME_URL="https://www.debian.org/"
SUPPORT_URL="https://www.debian.org/support"
BUG_REPORT_URL="https://bugs.debian.org/"

$ free -h
               total        used        free      shared  buff/cache   available
Mem:           417Mi       159Mi       136Mi       1.1Mi       173Mi       258Mi
Swap:          2.0Gi          0B       2.0Gi

$ cat /proc/cpuinfo
processor       : 0
BogoMIPS        : 38.40
Features        : fp asimd evtstrm crc32 cpuid
CPU implementer : 0x41
CPU architecture: 8
CPU variant     : 0x0
CPU part        : 0xd03
CPU revision    : 4

processor       : 1
BogoMIPS        : 38.40
Features        : fp asimd evtstrm crc32 cpuid
CPU implementer : 0x41
CPU architecture: 8
CPU variant     : 0x0
CPU part        : 0xd03
CPU revision    : 4

processor       : 2
BogoMIPS        : 38.40
Features        : fp asimd evtstrm crc32 cpuid
CPU implementer : 0x41
CPU architecture: 8
CPU variant     : 0x0
CPU part        : 0xd03
CPU revision    : 4

processor       : 3
BogoMIPS        : 38.40
Features        : fp asimd evtstrm crc32 cpuid
CPU implementer : 0x41
CPU architecture: 8
CPU variant     : 0x0
CPU part        : 0xd03
CPU revision    : 4

Revision        : 902120
Serial          : 000000000d9e6dff
Model           : Raspberry Pi Zero 2 W Rev 1.0

$ cat /proc/meminfo
MemTotal:         427072 kB
MemFree:          147196 kB
MemAvailable:     271652 kB
Buffers:           15832 kB
Cached:           148352 kB
SwapCached:            0 kB
Active:           172736 kB
Inactive:          39764 kB
Active(anon):      49404 kB
Inactive(anon):        0 kB
Active(file):     123332 kB
Inactive(file):    39764 kB
Unevictable:           0 kB
Mlocked:               0 kB
SwapTotal:       2097148 kB
SwapFree:        2097148 kB
Zswap:                 0 kB
Zswapped:              0 kB
Dirty:                 0 kB
Writeback:             0 kB
AnonPages:         48352 kB
Mapped:            69496 kB
Shmem:              1088 kB
KReclaimable:      13084 kB
Slab:              34388 kB
SReclaimable:      13084 kB
SUnreclaim:        21304 kB
KernelStack:        2724 kB
PageTables:         2436 kB
SecPageTables:         0 kB
NFS_Unstable:          0 kB
Bounce:                0 kB
WritebackTmp:          0 kB
CommitLimit:     2310684 kB
Committed_AS:     393972 kB
VmallocTotal:   257687552 kB
VmallocUsed:       11040 kB
VmallocChunk:          0 kB
Percpu:              672 kB
CmaTotal:         262144 kB
CmaFree:          110468 kB
```


```
$ ./benchncnn 4 1 0 -1 1
loop_count = 4
num_threads = 1
powersave = 0
gpu_device = -1
cooling_down = 1
          squeezenet  min =  163.95  max =  164.64  avg =  164.25
     squeezenet_int8  min =  152.19  max =  152.72  avg =  152.55
           mobilenet  min =  272.43  max =  275.29  avg =  273.27
      mobilenet_int8  min =  225.68  max =  226.29  avg =  226.10
        mobilenet_v2  min =  201.11  max =  201.39  avg =  201.23
        mobilenet_v3  min =  163.07  max =  163.32  avg =  163.21
          shufflenet  min =  104.44  max =  104.75  avg =  104.55
       shufflenet_v2  min =   94.03  max =   94.42  avg =   94.28
             mnasnet  min =  194.75  max =  195.39  avg =  195.00
     proxylessnasnet  min =  261.84  max =  262.78  avg =  262.43
     efficientnet_b0  min =  316.91  max =  318.27  avg =  317.62
   efficientnetv2_b0  min =  356.69  max =  357.55  avg =  357.10
        regnety_400m  min =  236.01  max =  236.48  avg =  236.21
           blazeface  min =   28.70  max =   30.32  avg =   29.20
           googlenet  min =  592.67  max =  593.78  avg =  593.25
      googlenet_int8  min =  507.56  max =  507.98  avg =  507.74
            resnet18  min =  459.78  max =  460.66  avg =  460.39
       resnet18_int8  min =  347.81  max =  349.51  avg =  348.67
             alexnet  min =  366.01  max =  367.06  avg =  366.39
               vgg16  min = 66656.05  max = 77701.65  avg = 70366.46
          vgg16_int8  min = 2447.17  max = 21024.62  avg = 11687.93
            resnet50  min = 1254.07  max = 1256.08  avg = 1254.74
       resnet50_int8  min = 1077.75  max = 1078.04  avg = 1077.92
      squeezenet_ssd  min =  407.96  max =  409.61  avg =  408.64
 squeezenet_ssd_int8  min =  343.11  max =  344.72  avg =  343.74
       mobilenet_ssd  min =  564.39  max =  564.78  avg =  564.54
  mobilenet_ssd_int8  min =  463.88  max =  466.38  avg =  464.65
      mobilenet_yolo  min = 1236.83  max = 1238.93  avg = 1237.60
  mobilenetv2_yolov3  min =  695.02  max =  695.62  avg =  695.25
         yolov4-tiny  min =  853.00  max =  854.35  avg =  853.51
           nanodet_m  min =  240.53  max =  241.36  avg =  240.93
    yolo-fastest-1.1  min =  127.41  max =  127.71  avg =  127.58
      yolo-fastestv2  min =  100.92  max =  101.33  avg =  101.09
  vision_transformer  min = 14681.06  max = 14799.29  avg = 14750.90
          FastestDet  min =  111.73  max =  111.98  avg =  111.90

$ ./benchncnn 4 4 0 -1 1
loop_count = 4
num_threads = 4
powersave = 0
gpu_device = -1
cooling_down = 1
          squeezenet  min =   94.88  max =   95.50  avg =   95.22
     squeezenet_int8  min =   79.35  max =   80.08  avg =   79.68
           mobilenet  min =  127.13  max =  127.57  avg =  127.40
      mobilenet_int8  min =   78.65  max =   78.98  avg =   78.81
        mobilenet_v2  min =  128.54  max =  129.68  avg =  129.15
        mobilenet_v3  min =   98.26  max =   98.43  avg =   98.33
          shufflenet  min =   66.90  max =   67.47  avg =   67.21
       shufflenet_v2  min =   52.32  max =   52.75  avg =   52.57
             mnasnet  min =  111.90  max =  112.62  avg =  112.34
     proxylessnasnet  min =  118.48  max =  119.47  avg =  118.76
     efficientnet_b0  min =  155.56  max =  157.07  avg =  155.99
   efficientnetv2_b0  min =  171.39  max =  172.90  avg =  172.09
        regnety_400m  min =  135.76  max =  136.19  avg =  135.91
           blazeface  min =   17.39  max =   17.76  avg =   17.60
           googlenet  min =  264.43  max =  265.96  avg =  265.41
      googlenet_int8  min =  211.98  max =  213.73  avg =  212.97
            resnet18  min =  311.56  max =  319.92  avg =  314.21
       resnet18_int8  min =  167.23  max =  169.53  avg =  167.99
             alexnet  min =  188.50  max =  189.31  avg =  188.94
               vgg16  min = 73978.99  max = 82848.12  avg = 79031.31
          vgg16_int8  min = 1361.84  max = 30602.68  avg = 14190.58
            resnet50  min =  652.90  max = 1006.11  avg =  749.30
       resnet50_int8  min =  442.29  max =  458.85  avg =  446.79
      squeezenet_ssd  min =  277.98  max =  281.90  avg =  279.82
 squeezenet_ssd_int8  min =  200.31  max =  202.15  avg =  200.98
       mobilenet_ssd  min =  288.34  max =  291.08  avg =  289.81
  mobilenet_ssd_int8  min =  161.44  max =  161.59  avg =  161.55
      mobilenet_yolo  min =  596.91  max =  598.30  avg =  597.71
  mobilenetv2_yolov3  min =  408.89  max =  411.38  avg =  409.77
         yolov4-tiny  min =  474.56  max =  479.67  avg =  477.37
           nanodet_m  min =  145.40  max =  146.08  avg =  145.63
    yolo-fastest-1.1  min =   94.99  max =   95.68  avg =   95.32
      yolo-fastestv2  min =   73.39  max =   73.75  avg =   73.60
  vision_transformer  min = 4368.69  max = 4412.38  avg = 4396.93
          FastestDet  min =   76.88  max =   77.24  avg =   77.09

```





