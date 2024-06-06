# ncnn_benchmark_test

CoreMP135 :https://www.switch-science.com/products/9650  
Raspberry Pi Zero 2 W:https://www.switch-science.com/products/7600  
M5Stack UnitV2 :https://www.switch-science.com/products/7160

# Result

||M5 CoreMP135|RasPi Zero 2 W(32Bit OS)|RasPi Zero 2 W(32Bit OS)|M5 UnitV2|M5 UnitV2|
| ------ | -------- |------ |-- |-- |-- |
||  single-task| single-task|  multi-task(4thread)|single-task|  multi-task(2thread)|
|squeezenet|535.62|940.61|272.91|365.53|208.12|
|squeezenet_int8|365.35|690.35|206.68|253.99|149.1|
|mobilenet|940.21|1763.62|470.97|639.61|349.23|
|mobilenet_int8|500.01|1271.59|326.97|351.51|182.88|
|mobilenet_v2|619.26|1094.86|315.5|431.16|258.93|
|mobilenet_v3|497.38|890.25|281.08|344.59|203.37|
|shufflenet|311.66|529.56|195.5|216.51|136.56|
|shufflenet_v2|293.22|502.05|160.13|201.24|133.42|
|mnasnet|608.54|1073.42|305.64|418.45|242.58|
|proxylessnasnet|691.34|1191.08|414.99|478.11|271.54|
|efficientnet_b0|1016.16|1860.9|542.05|700.15|388.85|
|efficientnetv2_b0|1189.88|2171.53|598.09|818.04|447.12|
|regnety_400m|730.86|1329.18|458.83|497.96|286.31|
|blazeface|86.86|140.97|48.51|58.91|36.18|
|googlenet|1754.33|3320.41|908.63|1214.04|656.65|
|googlenet_int8|1103.19|2208.91|628.92|767.95|424.95|
|resnet18|1582.5|2633.43|723.4|err|err|
|resnet18_int8|820.28|1621|438.65|err|err|
|alexnet|1012.93|1751.36|508.3|err|err|




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
# Raspberry Pi Zero 2 W

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

# M5Stack unitv2


```
unitv2% uname -a
Linux unitv2 4.9.84 #196 SMP PREEMPT Wed Apr 7 02:40:43 CST 2021 armv7l GNU/Linux

unitv2% cat /etc/os-release
NAME=Buildroot
VERSION=2020.02.8
ID=buildroot
VERSION_ID=2020.02.8
PRETTY_NAME="Buildroot 2020.02.8"
```

#### build ncnn
```
$ curl -LO https://developer.arm.com/-/media/Files/downloads/gnu-a/10.2-2020.11/binrel/gcc-arm-10.2-2020.11-x86_64-arm-none-linux-gnueabihf.tar.xz
$ tar Jxfv gcc-arm-10.2-2020.11-x86_64-arm-none-linux-gnueabihf.tar.xz
$  cmake -B build/arm_unitv2 -DCMAKE_TOOLCHAIN_FILE=./toolchains/arm-linux-gnueabihf-unitv2.toolchain.cmake -DNCNN_SIMPLEOCV=ON -DCMAKE_BUILD_TYPE=Release -DNCNN_VULKAN=OFF -DNCNN_BUILD_EXAMPLES=OFF .
$  cmake --build build/arm_unitv2 &&
 cmake --install build/arm_unitv2 --prefix install/arm_unitv2
```
#### result

```
unitv2% ./benchncnn 4 1 0 -1 1
loop_count = 4
num_threads = 1
powersave = 0
gpu_device = -1
cooling_down = 1
          squeezenet  min =  365.35  max =  365.64  avg =  365.53
     squeezenet_int8  min =  252.73  max =  255.21  avg =  253.99
           mobilenet  min =  639.05  max =  640.57  avg =  639.61
      mobilenet_int8  min =  349.64  max =  355.12  avg =  351.51
        mobilenet_v2  min =  430.81  max =  431.46  avg =  431.16
        mobilenet_v3  min =  344.34  max =  344.74  avg =  344.59
          shufflenet  min =  216.05  max =  217.20  avg =  216.51
       shufflenet_v2  min =  200.87  max =  201.98  avg =  201.24
             mnasnet  min =  417.98  max =  419.16  avg =  418.45
     proxylessnasnet  min =  477.86  max =  478.22  avg =  478.11
     efficientnet_b0  min =  699.24  max =  700.61  avg =  700.15
   efficientnetv2_b0  min =  817.53  max =  818.71  avg =  818.04
        regnety_400m  min =  497.26  max =  499.18  avg =  497.96
           blazeface  min =   58.75  max =   59.24  avg =   58.91
           googlenet  min = 1213.31  max = 1214.68  avg = 1214.04
      googlenet_int8  min =  766.48  max =  769.59  avg =  767.95

unitv2% ./benchncnn 4 2 0 -1 1
loop_count = 4
num_threads = 2
powersave = 0
gpu_device = -1
cooling_down = 1
          squeezenet  min =  207.65  max =  208.47  avg =  208.12
     squeezenet_int8  min =  149.00  max =  149.16  avg =  149.10
           mobilenet  min =  348.22  max =  351.24  avg =  349.23
      mobilenet_int8  min =  182.69  max =  182.96  avg =  182.88
        mobilenet_v2  min =  254.54  max =  270.19  avg =  258.93
        mobilenet_v3  min =  203.12  max =  203.81  avg =  203.37
          shufflenet  min =  136.41  max =  136.70  avg =  136.56
       shufflenet_v2  min =  126.79  max =  152.76  avg =  133.42
             mnasnet  min =  242.26  max =  243.36  avg =  242.58
     proxylessnasnet  min =  270.56  max =  272.37  avg =  271.54
     efficientnet_b0  min =  388.31  max =  389.73  avg =  388.85
   efficientnetv2_b0  min =  446.40  max =  448.80  avg =  447.12
        regnety_400m  min =  286.05  max =  286.55  avg =  286.31
           blazeface  min =   36.10  max =   36.31  avg =   36.18
           googlenet  min =  655.90  max =  658.45  avg =  656.65
      googlenet_int8  min =  424.22  max =  426.86  avg =  424.95


```




# Reference
https://github.com/Tencent/ncnn/blob/master/benchmark/README.md
