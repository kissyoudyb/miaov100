
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

第四课：相册
    适配：
    <meta name="viewport" content="width=device-width,user-scalable=no,target-densitydpi=medium-dpi" />

    主流分辨率:240*320（一般不考虑）、320*480、480*800（多）、640*960（多） 480*854 1280*720 800*1280 1080*1920

    /*
       320 - 480
    */
    A. 页面设置固定宽度320px, margin居中，左右留白用背景填充
    B. 通过media, 根据不同的分别率去设置不同的样式 （追求完美）
    C. 通过，100%、 flex或rem等手段，等比例缩放

    在高dpi情况下图片会有发虚失真
------------------------------------------------------------------

rem 相对于根节点的字体大小的计量单位

em 相对于字体大小的 font-size:24  1em=24px

CSS中的background-size属性：

background-size的值类型：1个或2个值，这些值既可以是像素px，也可以是百分比%或auto，还可以是特定值cover, contain。

　　background-size可以设置2个值，1个为必填，1个为可选。
　　其中第1个值用于指定背景图的width，第2个值用于指定背景图的height，如果只给background-size设置1个值，则第2个值默认为auto高度自动 (通常默认高度是auto自动,自适用内容而增高,通常如果想高度自适应不用设置) （cover和contain特定值除外）。

div{
background-image:url(test.png);
background-repeat:no-repeat;
background-size:100px;
}

　　等价于：

div{
background-image:url(test.png);
background-repeat:no-repeat;
background-size:100px auto;
}

　　查看具体DEMO: background-size的值定义。当你使用firebug抓取到那个实例节点时，你会发现第二个值被自动加上了并且值为auto。当然，你也可以手动将第2个值设置为auto，然后与该DEMO的实例对比，它们的效果将是相同的。

　　background-size的特定值：

cover: 保持图像本身的宽高比例，将图片缩放到正好完全覆盖定义背景的区域；
contain: 保持图像本身的宽高比例，将图片缩放到宽度或高度正好适应定义背景的区域；
cover值：

div{
background-image:url(test.png);
background-repeat:no-repeat;
background-size:cover;
}

　　上例，背景图片将覆盖整个div区域。查看具体DEMO: background-size:cover。

contain值：

div{
background-image:url(test.png);
background-repeat:no-repeat;
background-size:contain;
}

　　上例，背景图将缩放到宽度或高度的任意一边与div区域适应。查看具体DEMO: background-size:contain。

--------------------------------------------------------------
click 事件在移动端会有300ms的延迟
touch事件
touchstart == mousedown
touchmove == mousemove
touchend == mouseup