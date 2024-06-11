# ncnn_benchmark_test

CoreMP135 :https://www.switch-science.com/products/9650  
Raspberry Pi Zero 2 W:https://www.switch-science.com/products/7600  
M5Stack UnitV2 :https://www.switch-science.com/products/7160

# Result

||M5 CoreMP135|RasPi Zero 2 W|RasPi Zero 2 W|M5 UnitV2|M5 UnitV2|
| ------ | -------- |------ |-- |-- |-- |
||  32Bit OS/32Bit CPU|  32Bit OS/64Bit CPU|   32Bit OS/64Bit CPU| 32Bit OS/32Bit CPU|  32Bit OS/32Bit CPU|
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
