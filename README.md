# ncnn_benchmark_test

### Result

![image](https://github.com/nnn112358/ncnn_benchmark_test/assets/27625496/b474dd3b-6394-4f55-bc64-2ac12b86d664)



### Install 
 ```
$ wget https://github.com/nnn112358/ncnn_benchmark_test/releases/download/benchmark_arm/benchmark_arm-linux-gnueabihf.zip
 $ unzip benchmark_arm-linux-gnueabihf.zip
 $ cd benchmark
 $ chmod +x benchncnn
 $ ./benchncnn
```

# Result 

M5Stack CoreMP135

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
Raspberry Pi Zero 2 W

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

#Reference
https://github.com/Tencent/ncnn/blob/master/benchmark/README.md
