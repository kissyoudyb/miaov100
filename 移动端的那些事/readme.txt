
第一课：Emulation 模拟器

一：Device 设备设置
       1. model 模型选择
       2. resolution 分辨率设置
       3. Device pixel ratio 像素比设置
       4. *Emulate mobile 模拟移动端特性
       5. *Enable text autosizing 自动缩放字体
       6. *Shrink to fit 缩放以适应屏幕
二：Media 媒体查询
三：Network 浏览器信息
四：Sensors 传感器
       1. Emulate touch screen 模拟移动端触摸事件
                 --touch-events
       2. Device Geolocation Overrides 重置地理信息
       3. Accelerometer 模拟陀螺仪
                 α 围绕这Z轴的旋转
                 β 围绕这X轴的旋转
                 γ 围绕这Y轴的旋转


第二课:viewport
<meta name="viewport" content="" />
           1.width [pixel_value | device-width]
        2.user-scalable 是否允许缩放 （no||yes）
        3.initial-scale 初始比例
        4.minimum-scale 允许缩放的最小比例
        5.maximum-scale 允许缩放的最大比例
        6.target-densitydpi [dpi_value | device-dpi | high-dpi | medium-dpi | low-dpi]

第三课:媒体查询
引入方式
    1.
<link rel="stylesheet" type="text/css" href="index.css" media="all and (min-width: 600px)">
复制代码
  2.
@import url("css/reset.css") all and (min-width: 600px) ;
复制代码
    3.
@media all and (min-width: 600px)
{
    .box
    {
        width:100px;
    }
}
复制代码

媒体类型
    1.all 所有媒体
    2.braille 盲文触觉设备
    3.embossed 盲文打印机
    4.print 手持设备
    5.projection 打印预览
    6.screen 彩屏设备
    7.speech '听觉'类似的媒体类型
    8.tty 不适用像素的设备
    9.tv  电视

媒体特性
    1.(max-width:599px)
    2.(min-width:600px)
    3.(orientation:portrait) 竖屏
    4.(orientation:landscape)        横屏
    5.(-webkit-min-device-pixel-ratio: 2) 像素比



关键字
    1.and
    2.not      not关键字是用来排除某种制定的媒体类型
    3.only     only用来定某种特定的媒体类型
         -很多时候是用来对那些不支持媒体特性但却支持媒体类型的设备