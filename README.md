# ncnn_benchmark_test

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
Killed
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

$ gcc -v
Using built-in specs.
COLLECT_GCC=gcc
COLLECT_LTO_WRAPPER=/usr/lib/gcc/arm-linux-gnueabihf/10/lto-wrapper
Target: arm-linux-gnueabihf
Configured with: ../src/configure -v --with-pkgversion='Raspbian 10.2.1-6+rpi1' --with-bugurl=file:///usr/share/doc/gcc-10/README.Bugs --enable-languages=c,ada,c++,go,d,fortran,objc,obj-c++,m2 --prefix=/usr --with-gcc-major-version-only --program-suffix=-10 --program-prefix=arm-linux-gnueabihf- --enable-shared --enable-linker-build-id --libexecdir=/usr/lib --without-included-gettext --enable-threads=posix --libdir=/usr/lib --enable-nls --enable-bootstrap --enable-clocale=gnu --enable-libstdcxx-debug --enable-libstdcxx-time=yes --with-default-libstdcxx-abi=new --enable-gnu-unique-object --disable-libitm --disable-libquadmath --disable-libquadmath-support --enable-plugin --with-system-zlib --enable-libphobos-checking=release --with-target-system-zlib=auto --enable-objc-gc=auto --enable-multiarch --disable-sjlj-exceptions --with-arch=armv6 --with-fpu=vfp --with-float=hard --disable-werror --enable-checking=release --build=arm-linux-gnueabihf --host=arm-linux-gnueabihf --target=arm-linux-gnueabihf
Thread model: posix
Supported LTO compression algorithms: zlib zstd
gcc version 10.2.1 20210110 (Raspbian 10.2.1-6+rpi1)

```

#Reference
https://github.com/Tencent/ncnn/blob/master/benchmark/README.md
