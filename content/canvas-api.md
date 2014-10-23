# Canvas API 初探

---

## About Me

@state: blue, @fragment

* **Sandy**
* 奇舞团前端
* 支持问答项目组

---

## Canvas 是什么？

@state: black, @fragment

* 一块矩形画布
* 可以用js控制，并绘图，制作动画
* 不能获取其中的DOM结构

---

## 简单概念

---

@state: black, @fragment

## canvas坐标
* 从左上角开始，x轴沿着水平方向向右延伸，y轴沿垂直方向向下延伸。左上角坐标为x=0,y=0的点乘坐原点。

---

## 代替内容

@state: black, @fragment

* ```html
  <canvas>Updata your browser to enjoy canvas!</canvas>
```
---

## 检测浏览器支持情况

@state: black, @fragment

* ```javascript
  try{
	document.createElement('canvas').getContext('2d');
	document.getElementById('diagonal').innerHTML 
	= 'HTML5 Canvas is supported in your browser.';
  }
  catch(e){
  	document.getElementById('diagonal').innerHTML 
  	= 'HTML5 Canvas is not supported in your browser.';
  }
```
---

## Canvas画布

@state: blue, @fragment

* ```html
<canvas height="200" width="200"></canvas>
```

---

## 设置Canvas样式

@state: black, @fragment

* ```html
<canvas id="diagonal"></canvas>
```

* ```css
   #diagonal{
   	border:1px solid #dd0000;
   	background:#f88;
   	width:200px;
   	height:200px;
   }
```
---

## 一块Canvas画布

<iframe src="http://jsbin.com/zenim/2/embed??js" class="" id="" style="border: 1px solid rgb(170, 170, 170); width: 100%; min-height: 600px;"></iframe>

---

## 路径

@state: blue, @fragment

* beginPath() 【创建路径】
* moveTo()    【移动起点】
* lineTo()    【指定终点】
* closePath() 【闭合路径】
* stroke()    【绘制路径】

---

## 画一条对角线

<iframe src="http://jsbin.com/nemoho/7/embed?js" class="" id="" style="border: 1px solid rgb(170, 170, 170); width: 100%; min-height: 600px;"></iframe>

---

## 变换

@state: blue, @fragment

*```javascript
 //保存画布
 context.save();
 
 //将画布原点移动到点(x, y)
 context.translate(x, y);
 
 //···其他操作···
 
 //恢复画布初始位置
 context.restore();
```


---

## 画一条一样的对角线

<iframe src="http://jsbin.com/nemoho/11/embed?js" class="" id="" style="border: 1px solid rgb(170, 170, 170); width: 100%; min-height: 600px;"></iframe>

---

## 其他方法和属性

@state: blue, @fragment

* fill()      【填充路径】
* fillRect()  【填充矩形区域】

* fillStyle   【填充样式】
* strokeStyle 【描边样式】
* lineWidth   【描边宽度】

---

## 画一棵树

<iframe src="http://jsbin.com/nemoho/27/embed?js" class="" id="" style="border: 1px solid rgb(170, 170, 170); width: 100%; min-height: 600px;"></iframe>

---

## 曲线函数

@state: blue, @fragment

* quadraticCurveTo(x1, y1, x2, y2)
* 以当前坐标作为起点
* 接受四个参数，分别是控制点(x1, y1)和终点(x2, y2)的坐标
<img src="http://p4.qhimg.com/t01206d4cf079aa3ace.jpg" class="" id="" style="width:500px;height:500px;">

---

## 绘制蜿蜒小路

<iframe src="http://jsbin.com/nemoho/38/embed?js" class="" id="" style="border: 1px solid rgb(170, 170, 170); width: 100%; min-height: 600px; "></iframe>

---

## 控制点分析

@state: black, @fragment

* 曲线函数 —— quadraticCurveTo(170, -50, 260, -190)
* 起点 —— (-10, 350)
* 控制点, 终点 ——  (170, -50) , (260, -190)

<img src="http://p4.qhimg.com/t01f89363a49172658f.png" class="" id="" style="width:398px;489px;" />

---

## 渐变

@state: blue, @fragment

* ```javascript
//创建三阶水平渐变
createLinearGradient(x1, y1, x2, y2)

//在渐变对象上添加渐变点
addColorStop(0,'#000') 
addColorStop(1,'rgba(0, 0, 0, 0.5)')
```
---
## 画渐变树干

<iframe src="http://jsbin.com/nemoho/41/embed?js" class="" id="" style="border: 1px solid rgb(170, 170, 170); width: 100%; min-height: 600px;"></iframe>

---

## 放射性渐变

@state: blue, @fragment

createRadialGradient(x0, y0, r0, x1, y1, r1)

* 前三个参数代表以(x0, y0)为圆心，r0为半径的圆
* 后三个参数代表以(x1, y1)为圆心，r1为半径的圆
* 渐变会在两个圆中间的区域出现

---

### 放射性渐变demo

<iframe src="http://jsbin.com/hapumu/2/embed?js" class="" id="" style="border: 1px solid rgb(170, 170, 170); width: 100%; min-height: 600px;"></iframe>

---

## 缩放

@state: blue, @fragment

* scale(2,3)
* scale函数带有两个参数来分别代表在x，y两个维度的缩放值

---

## 画一棵两倍大的树

<iframe src="http://jsbin.com/nemoho/45/embed?js" class="" id="" style="border: 1px solid rgb(170, 170, 170); width: 100%; min-height: 600px;"></iframe>

---

## 一种变换的使用方法

@state: blue, @fragment

* 矩阵变换
* ```javascript
      //所有坐标都与矩阵相乘，进行拉伸变换
      transform(1, 0, -0.5, 1, 0, 0)
```

---

## 画树的阴影

<iframe src="http://jsbin.com/nemoho/48/embed?js" class="" id="" style="border: 1px solid rgb(170, 170, 170); width: 100%; min-height: 600px;"></iframe>

---

## Canvas文本

@state: blue, @fragment

---

## 文本属性和方法

@state: black, @fragment

* font (可以设置大小字体)
* textAlign（左右对齐方式）
* textBaseline（上下对齐方式）
* fillText('text', x, y, [maxwidth])
* strokeText('text', x, y, [maxwidth])

---

## 阴影属性

@state: black, @fragment

* shadowColor
* shadowOffsetX
* shadowOffsetY
* shadowBlur

---

## 绘制文本

<iframe src="http://jsbin.com/nemoho/49/embed?js" class="" id="" style="border: 1px solid rgb(170, 170, 170); width: 100%; min-height: 500px; height: 46px;"></iframe>

---

## 在canvas中插入图片

@state: green, @fragment

* ```javascript
//插入一张图
drawImage(img, x, y, width, height)

//创建一个图片填充/描边模式
createPattern(img, 'repeat/repeat-x/repeat-y/no-repeat')
```
---

## 图片填充和旋转

<iframe src="http://jsbin.com/jilora/6/embed?js" class="" id="" style="border: 1px solid rgb(170, 170, 170); width: 100%; min-height: 500px; height: 46px;"></iframe>

---

##canvas图片应用

@state: green, @fragment

请听下次讲解~  =。=

---
@fragment

## 总结

* 路径
* 描边
* 填充
* 变换
* 缩放
* 阴影
* 绘制曲线
* 文本
* 图片

---

@state: blue

## 谢谢大家！

<p style="font-size:6em"><i class="icon-smile"></i></p>



<style type="text/css">
.reveal h1 {font-size:2.4em;}
.reveal h2 {font-size:1.6em;}
.reveal img {max-width:100%;}
.reveal a:not(.image) { color: #ccc; color: rgba(255,255,255,0.8); }
.reveal a:not(.image):hover { color: #fff; }
.reveal .overlay {display:inline-block;width:auto;background:rgba(0,0,0,0.5);padding:0.5em 1em;margin:0;line-height:1.6;font-size:1.5em}

.browser-support {display: table; margin-top:2em!important;}
.browser-support img {display: block; margin: 0 auto}
.browser-support li {display: table-cell; vertical-align:top; text-align: center;font-size:1.5em; box-sizing:border-box;padding:0 0.2em;}
</style>
