

# turtle函数库语法
### 1.绘图窗体坐标体系
turtle.setup（width,height,startx,starty）<br>
setup不是必须的

参数 | 意思 | 备注
---|---|---
width  | 窗口宽度 | 整数表示像素值，小数表示与屏幕比例
height | 窗口高度 | 整数表示像素值，小数表示与屏幕比例 
startx | 窗口左侧与屏幕左侧距离 | None，位于水平中央
starty | 窗口顶部与屏幕顶部距离 | None，位于垂直中央


### 2.画笔控制函数
函数|简称|意思|参数含义
---|---|---|---
turtle.penup()       |turtle.up或turtle.pu | 抬笔
turtle.pendown()     |turtle.down或turle.pd| 落笔
turtle.pensize(width)|turtle.width|画笔尺寸|width：画笔线条宽度，<br>若为None或空，则返回当前画笔宽度
turtle.color(colorstring)<br>或turtle.color((r,g,b))|  |画笔颜色|colorstring:表示颜色的英文字符，如："red";<br>(r,g,b)：对应RGB值

### 3.形状绘制函数
函数|简称|意思|参数含义
---|---|---|---
turtle.fd(distance)|turtle.forward(distance) | 前进 |distance：距离
turtle.seth(to_angle)|turtle.setheading(to_angle)| 改变方向|to_angle：绝对方向的角度值
turtle.circle(radius,extent)||绘制弧形|radius：半径；<br>extent：弧形角度
turtle.goto(x,y)|