//---------------------------------------------------------------------------------------------------------------------
//---龙芯
//---体系结构教学试验箱3.0（Artix-7）
//---------------------------------------------------------------------------------------------------------------------

本目录提供实验箱（Artix-7）的GPIO设备的测试程序。

1.测试项包括：单色LED灯、双色LED灯、数码管、点阵、LCD触摸屏、
              复位键、拨码开关、按钮开关、矩阵键盘。

2.测试结果判断：
  a. 16个单色LED灯 与 4x4矩阵键盘上的16个按键  对应，按一个亮一个；
  b. 双色LED灯     与 两个按钮开关中的上方那个 对应，按一下变色；
  c. 8个数码管     与 8个拨码开关              对应，拨上则亮，且每个数码管会从0扫描显示到9；
  d. 点阵                                      则不停地自己刷新每一列每一行；
  e. LCD触摸屏     与 按钮开关下方那个         配合，显示单周期CPU的状态，按钮开关充当时钟，主要触摸屏的功能也要测试；
  f. 复位键                                    可以复位全局。

3.测试程序目录结构
   +--FPGA_green_test/:  测试程序目录
   |       |
   |       |---------rtl/: 测试程序源码与LCD屏硬件驱动IP
   |       |
   |       |---------FPGA_green_test.xdc: 测试程序vivado工程需要的约束文件
   |       |
   |       |---------prj_test/: 测试程序使用vivado2017.1创建的工程目录
   |
   |--FPGA_green_test.bit： 测试程序使用vivado生成的bit流文件，可直接下载至FPGA板上。

4.测试程序使用方法：
  1).直接下再本目录下的FPGA_green_test.bit至FPGA板上运行。
     下载工具可选：
     a.ISE工具套装里的ChipScope。
     注意：ise13.2的ChipScope不支持，建议使用更高版本的ChipScope，尝试14.3版本的是可以用的。
     b.使用vivado工具里的 Open Hardware Manager下载。
  
  2).可以使用vivado打开 FPGA_green_test/prj_test/prj_test.xpr，然后在工程里打开Hardware Manager下载。
     注意：提供的工程是使用vivado2017.1创建的。
