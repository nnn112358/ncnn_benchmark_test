
# M5Stack CoreMP135(Debian)

```
$ uname -a
Linux M5Core135 5.15.118 #1 SMP PREEMPT Tue May 7 15:14:07 CST 2024 armv7l GNU/Linux

$ cat /etc/os-release
PRETTY_NAME="Debian GNU/Linux 12 (bookworm)"
NAME="Debian GNU/Linux"
VERSION_ID="12"
VERSION="12 (bookworm)"
VERSION_CODENAME=bookworm
ID=debian
HOME_URL="https://www.debian.org/"
SUPPORT_URL="https://www.debian.org/support"
BUG_REPORT_URL="https://bugs.debian.org/"
```

#### build ncnn 
```
$ wget https://github.com/nnn112358/ncnn_benchmark_test/releases/download/benchmark_arm/benchmark_arm-linux-gnueabihf.zip
$ unzip benchmark_arm-linux-gnueabihf.zip
$ cd benchmark
$ chmod +x benchncnn
```
#### result 

```
$ ./benchncnn 4 1 0 -1 1
loop_count = 4
num_threads = 1
powersave = 0
gpu_device = -1
cooling_down = 1
          squeezenet  min =  535.26  max =  536.01  avg =  535.62
     squeezenet_int8  min =  364.90  max =  366.00  avg =  365.35
           mobilenet  min =  937.72  max =  944.77  avg =  940.21
      mobilenet_int8  min =  499.61  max =  500.78  avg =  500.01
        mobilenet_v2  min =  618.19  max =  620.32  avg =  619.26
        mobilenet_v3  min =  496.60  max =  498.31  avg =  497.38
          shufflenet  min =  311.15  max =  312.68  avg =  311.66
       shufflenet_v2  min =  292.44  max =  293.66  avg =  293.22
             mnasnet  min =  607.94  max =  609.09  avg =  608.54
     proxylessnasnet  min =  691.01  max =  691.69  avg =  691.34
     efficientnet_b0  min = 1010.46  max = 1030.67  avg = 1016.16
   efficientnetv2_b0  min = 1188.48  max = 1191.89  avg = 1189.88
        regnety_400m  min =  730.38  max =  731.59  avg =  730.86
           blazeface  min =   86.61  max =   87.47  avg =   86.86
           googlenet  min = 1753.05  max = 1755.93  avg = 1754.33
      googlenet_int8  min = 1100.80  max = 1109.38  avg = 1103.19
            resnet18  min = 1581.46  max = 1583.82  avg = 1582.50
       resnet18_int8  min =  817.56  max =  823.16  avg =  820.28
             alexnet  min = 1012.00  max = 1013.54  avg = 1012.93

```

# M5Stack CoreMP135(BuildRoot)

```
# uname -a
Linux CoreMP135 5.15.118 #1 SMP PREEMPT Wed May 15 15:34:26 CST 2024 armv7l GNU/Linux

#  cat /etc/os-release
NAME=Buildroot
VERSION=2021.05-10169-gb885d5525a
ID=buildroot
VERSION_ID=2023.02.2
PRETTY_NAME="Buildroot 2023.02.2"

#  ./benchncnn 4 1 0 -1 1
loop_count = 4
num_threads = 1
powersave = 0
gpu_device = -1
cooling_down = 1
          squeezenet  min =  531.80  max =  532.63  avg =  532.20
     squeezenet_int8  min =  361.08  max =  361.75  avg =  361.39
           mobilenet  min =  932.67  max =  934.00  avg =  933.25
      mobilenet_int8  min =  497.71  max =  498.07  avg =  497.87
        mobilenet_v2  min =  614.77  max =  616.07  avg =  615.46
        mobilenet_v3  min =  492.15  max =  493.12  avg =  492.77
          shufflenet  min =  307.61  max =  308.09  avg =  307.83
       shufflenet_v2  min =  289.53  max =  290.40  avg =  289.82
             mnasnet  min =  603.62  max =  604.35  avg =  603.87
     proxylessnasnet  min =  685.61  max =  686.89  avg =  686.26
     efficientnet_b0  min = 1001.24  max = 1001.77  avg = 1001.49
   efficientnetv2_b0  min = 1177.08  max = 1179.96  avg = 1178.58
        regnety_400m  min =  721.99  max =  722.87  avg =  722.29
           blazeface  min =   84.75  max =   85.43  avg =   85.08
           googlenet  min = 1741.78  max = 1744.97  avg = 1742.84
      googlenet_int8  min = 1090.19  max = 1091.28  avg = 1090.78
            resnet18  min = 1568.05  max = 1569.53  avg = 1568.86
       resnet18_int8  min =  810.82  max =  811.99  avg =  811.28
             alexnet  min = 1006.04  max = 1007.20  avg = 1006.40
```

