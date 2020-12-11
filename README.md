# MOPS 插座固件

MOPS插座，芯片为esp_wroom_02。出厂固件未知，目前配套APP尚不能使用。

因此，需要重刷固件。


## pin对应功能

| pin | 对应元件 | 触发方式 |
| :------------- | :----------: | :----------: |
|  15 | 继电器   | 高电平 |
| 12   | 状态灯 | 低电平 |
| 13   | 按钮 | 低电平 |


## esp_wroom_02 pinout

| pin | name |  | name | pin |
| :---- | :-----: | :----: | :----: | :----: |
|    | 3.3v |  | gnd |  | 
|    | en |  | io16 | 16 | 
|  14  |  io14  |  | A0 | A0 | 
|  12  |  io12  |  | rst |  |
|  13  |  io13  |  | scl | 5 |  
|  15  |  io15  |  | gnd |  | 
|  2  |  io2  |  | txd | 1 | 
|  0  |  io1  |  | rxd | 3 | 
|  ⭕️  |  gnd  |  | sda | 4 | 


注：上面红色圆圈与芯片中的圆点对应。

刷固件时，需让io1接地。然后如图，用鳄鱼夹刷固件。

![](./pin.png)

红色文字的是USB转ttl的pin，黄色文字是板载pin。


需要修改platformio.ini中的upload_port


刷完后，按钮可独立控制插座开关。也可输入url进行控制：

开：

http://MopsPower.local/on

关：

http://MopsPower.local/off

状态：

http://MopsPower.local/status