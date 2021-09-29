# 1 入门指南

SVG-Scalable Vector Graphics-可缩放矢量图形，XML应用。

计算机描述图形的两大系统：

- 栅格图形raster graphics
  - 用途：表示照片
- 矢量图形vector graphics
  - 用途
    - 计算机辅助绘图Computer Assisted Drafting，CAD
    - 用于高分辨率打印图片的程序，例如Adobe Illustrator
    - Adobe PostScript打印和城乡语言
    - 基于矢量图形Macromedia Flash系统（被Adobe收购），用来设计动画、演示和网站

创建一个SVG图像

https://oreillymedia.github.io/svg-essentials-examples/ch01/ex01-02.html

```SVG
<?xml version="1.0"?>
<!DOCTYPE svg PUBLIC "-//W3C//DTD SVG 1.0//EN"
    "http://www.w3.org/TR/2001/REC-SVG-20010904/DTD/svg10.dtd">

<svg width="140" height="170">
    xmlns:xlink="http://www.w3.org/1999/xlink">
<title>Cat</title>
<desc>Stick Figure of a Cat</desc>

<circle cx="70" cy="95" r="50" style="stroke: black; fill: none"/>
<circle cx="55" cy="80" r="5" stroke="black" fill="#339933"/>
<circle cx="85" cy="80" r="5" stroke="black" fill="#339933"/>
<g id="whiskers">
   <line x1="75" y1="95" x2="135" y2="85" style="stroke: black;"/>
   <line x1="75" y1="95" x2="135" y2="105" style="stroke: black;"/>
 </g>
<use xlink:href="#whiskers" transform="scale(-1 1) translate(-140 0)"/>
<!-- ears -->
<polyline points="108 62,  90 10,  70 45,  50, 10,  32, 62"
   style="stroke: black; fill: none;" />
<!-- mouth -->
<polyline points="35 110, 45 120, 95 120, 105, 110"
    style="stroke: black; fill: none;" />
<!-- nose -->
<path d="M 75 90 L 65 90 A 5 10 0  0 0 75 90"
   style="stroke: black; fill: #ffcccc"/>
<text x="60" y="165" style="font-family: sans-serif; font-size: 14pt;
   stroke: none; fill: black;">Cat</text>
</svg>
```

# 2 在网页中使用SVG

