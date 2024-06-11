# ncnn_benchmark_test

[CoreMP135](M5Stack_CoreMP135.md)<br>
[Raspberry Pi Zero 2 W](RaspberryPiZero2W.md)<br>
[M5Stack_UnitV2](M5Stack_UnitV2.md)<br>
<br>


# Result

![image](https://github.com/nnn112358/ncnn_benchmark_test/assets/27625496/b293548c-fbe4-4f45-954b-7495f8ae83b6)

|M5 CoreMP135|M5 UnitV2|M5 UnitV2|RasPi Zero 2 W|RasPi Zero 2 W|RasPi Zero 2 W|RasPi Zero 2 W|
|--|--|--|--|--|--|--|
|Debian12|BuildRoot|BuildRoot|Debian12(32Bit)|Debian12(32Bit)|Debian12(64Bit)|Debian12(64Bit)|
|512MB|128MB|128MB|512MB|512MB|512MB|512MB|
|single-task|single-task|multi-task(2thread)|single-task|multi-task(4thread)|single-task|multi-task(4thread)|
|squeezenet|535.62|365.53|208.12|214.49|105.87|164.25|95.22|
|squeezenet_int8|365.35|253.99|149.1|167.94|81.78|152.55|79.68|
|mobilenet|940.21|639.61|349.23|379.64|155.31|273.27|127.4|
|mobilenet_int8|500.01|351.51|182.88|266.41|83.53|226.1|78.81|
|mobilenet_v2|619.26|431.16|258.93|259.36|139.68|201.23|129.15|
|mobilenet_v3|497.38|344.59|203.37|207.05|106.74|163.21|98.33|


## Rerference

CoreMP135 :https://www.switch-science.com/products/9650  
Raspberry Pi Zero 2 W:https://www.switch-science.com/products/7600  
M5Stack UnitV2 :https://www.switch-science.com/products/7160

