项目的起因，手里有一堆的18650的电池， 需要管理。就设计了一个充电器。功能很简单，就是用线性充电集成电路,用5C的速度给5块18650充电。   
目前完成度52%   

有朋友说需要测试电池容量，于是就给一号充电位置，增加了放电功能和电压检测功能，还增加了2500V隔离串口，sdcard报告导出,lcd显示功能,后续还会增加功能在线电池管理功能， 方便大家对手头的电池进行编号，对型号，历史数据进行管理。

初步的设想是，用静态的一堆css,html5,javascript进行图文并茂的报告输出， 动态数据是同目录下的csv文件。   

串口部分可以用python做跨平台的控制和显示界面。   

scad目录下是openscad做的一些外壳之类的设计   

arduino目录下是充电器的控制程序。   

电路图编辑软件 gEDA  

3d建模 openscad  

软件开发环境 arduino  

![Image](https://github.com/lshw/18650/pcb/5usb2a.pcb)
![Image](https://github.com/lshw/18650/pcb/5usb2.pcb)


**ToDo**  
 .优化程序大小， 争取可以放进atmega168  16k，重点是sd/fat部分  


**Changelog**  
 2015-05-12  
 .tf卡座封装尺寸调整   
 .重画板子，把尺寸从10X11.5cm缩减到10X10cm,因为10X10cm 加工费用只有40元/10片，而10X11.5cm要110元/10片  

 2015-05-11   
 .调整电阻数值   
 .如果AREF接外部基准电压，就不能用内部的基准电压了，所以adc全部使用内部1.1V基准   

 2015-05-10   
 .VACC需要跟VCC连在一起.   
 .修正mos管的管脚
 .确定A6,A7可以直接在arduino中调用，不需要对arduino打补丁   
 .重新计算adc，选定采样分压，及基准电压   
 .AVCC腿加个电容   
 .放电mos管，加射极随出器进行电平转换.
