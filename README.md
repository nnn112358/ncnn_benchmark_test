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

