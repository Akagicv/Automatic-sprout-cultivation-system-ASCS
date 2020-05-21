# Automatic-sprout-Cultivation-System
自动化豆芽培育系统 <br>
基于ESP8266的自动化豆芽培育系统（ASCS） 
====  
前言
-------  
魔改自yltzdhbc大佬的https://github.com/yltzdhbc/FloewrCareSys <br>
flower care sys项目（变量中"浇花"的由来）<br>
以及DHT接入以及记录于服务器上使用酷安@仟念 大佬的项目（之前用的DHT库老是报错，恰好在酷安看到了这位大佬的教程，嘿嘿）<br>
此项目由来： <br>
母上因看了抖音手工种豆芽视频觉定种豆芽，然而每天都要定时浇水，一直放在阴凉处，生长效率并不高。 <br>
遂做了这一套系统让种豆芽更有效率<br>
根据气温和土壤湿度可选择性（可以选择开启或关闭自动浇水）自动浇水，可以自己手动（使用水泵）浇水<br>
记录温度、湿度、土壤湿度数据在服务器上，手机端可以看折线图<br>
可以在项目附属的OLED显示屏（0.96寸）上看到以中文显示（自己写的字库文件）的目前温度、土壤湿度以及此系统的运行状态（浇水与加热）的情况<br>
温度传感器用的DHT11(主要是便宜，毕竟我也是个穷学生)<br>
电源用升压线+面包板供电模块（正是如此导致同时加热浇水很吃力）<br>
因为在yltzdhbc大佬的项目中传参不是很明白，便使用了另一种实现方法（在空针脚写电平，然后读取空针脚的电平）<br>
此系统有接入小爱的代码（能用小爱同学查询豆芽温度和湿度，但不能浇水）请在米家-我的-其他平台设备-添加-点灯科技内添加<br>
为什么没有接入天猫，百度，Siri？因为我没有上述设备_(:3」∠)_ <br>
接线：<br>
OLED:D5 /*clock*/, D7 /*data*/, D8 /*cs*/, D2 /*dc*/, D3 /*reset*/<br>
（yltzdhbc大佬的项目在介绍里面吧时钟线和数据线写反了导致我还以为显示屏坏了23333）<br>
DHT11 D6 土壤传感器 A0 水泵继电器输入端 D4 PTC加热片继电器输入端 D1<br>
注释能写的都写了，希望大家使用的时候可以理解原理是最好的<br>
字库导入之前要下载U8g2与U8g2lib库，在U8g2\src\clib里面找到u8g2_fonts.c文件将其替换为此项目上传的u8g2_fonts.c文件<br>
APP界面先打开你接入的开发板界面，点击右上的圆里三个点的图标，点击界面配置，把APP界面文件里面的字符复制粘贴进去，点更新配置就行了

注意：此代码目前处于个人使用稳定（指blinker日常离线），如要用于大型生产环境，请三思！！！
====  
本人只是一个秃头医学生，做这些只是兴趣使然，只会看看官方文档写点简单的项目，如代码有错，请礼貌指出，如果要喷我，我也只会嘤嘤嘤。
