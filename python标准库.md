M

# 标准库

## turtle函数库语法

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

## random库

| 函数                          | 含义                                                         | 参数                                       |
| ----------------------------- | ------------------------------------------------------------ | ------------------------------------------ |
| .seed(a)                      | 设置初始化随机种子a                                          | a：随机种子，可以整数、浮点数              |
| .random()                     | 生成一个[0.0,1.0)之间的随机小数                              |                                            |
| .randiant(a,b)                | 生成一个[a,b]之间的随机整数                                  | a：开始数，整数；b：结束数，包括结束值整数 |
| .getrandbits(k)               | 生成一个k比特长度的随机整数                                  | k：长度的整数                              |
| .randrange(start,stop[,step]) | 生成一个[start,stop)之间以step为步长的随机整数               | step：步长，即结果必是其a+n*step，默认是1  |
| .uniform(a,b)                 | 生成一个[a,b]之间的随机小数                                  |                                            |
| .choice(seq)                  | 从序列中随机返回一个元素                                     | seq：序列类型，例如列表类型                |
| .shuffle(seq)                 | 将序列类型seq中元素随机排列，返回打乱后的的序列；调用该函数后，序列类型变量seq将被改变 |                                            |
| .sample(seq,k)                | 从pop类型中随机选取k个元素，以列表类型返回                   |                                            |



## time库

### 1.时间处理

| 函数         | 含义                                          | 参数 |
| ------------ | --------------------------------------------- | ---- |
| .time()      | 返回当前时间戳                                |      |
| .gmtime()    | 返回当前时间戳对应的struct_time对象           |      |
| .localtime() | 返回当前时间戳对应的本地时间的struct_time对象 |      |
| .ctime()     | 返回当前时间戳所对应的易读字符串              |      |
```
>>> from time import *
>>> time()
1582716310.8309927
>>> gmtime()
time.struct_time(tm_year=2020, tm_mon=2, tm_mday=26, tm_hour=11, tm_min=25, tm_sec=18, tm_wday=2, tm_yday=57, tm_isdst=0)
>>> localtime()
time.struct_time(tm_year=2020, tm_mon=2, tm_mday=26, tm_hour=19, tm_min=26, tm_sec=52, tm_wday=2, tm_yday=57, tm_isdst=0)
>>> ctime()
'Wed Feb 26 19:27:27 2020'
```
### 2.时间格式化
| 函数                     | 含义                                                         | 参数                             |
| ------------------------ | ------------------------------------------------------------ | -------------------------------- |
| .mktime(t)               | 将struct_time对象变量t转换为时间戳                           | t：代表时间的struct_time对象变量 |
| .strftime(format,t)      | 根据format格式定义打印输出t                                  |                                  |
| .strptime(string,format) | 根据format格式定义，解析字符串string，返回struct_time类型时间变量 |                                  |

```
>>> from time import *
>>> >>> t = (2009, 2, 17, 17, 3, 38, 1, 48, 0)
>>> mktime( t )
1234861418.0
```
| 格式化字符串 | 星期/时间   |      |
| ------------ | ----------- | ---- |
| %Y           | 年份        |      |
| %m           | 月份        |      |
| %B           | 月名        |      |
| %b           | 月名缩写    |      |
| %d           | 日期        |      |
| %A           | 星期        |      |
| %a           | 星期缩写    |      |
| %H           | 小时（24h） |      |
| %I           | 小时（12h） |      |
| %p           | 上午/下午   |      |
| %M           | 分钟        |      |
| %S           | 秒          |      |



### 3.计时

| 函数         | 含义                                          | 参数 |
| ------------ | --------------------------------------------- | ---- |
| .sleep(secs) | 将当前程序挂起secs秒，挂起即停止执行            | secs：表示时间的数值 |
| .perf_counter()| 返回一个代表时间的精确浮点数，两次或多次调用，其差值用来计时           |      |