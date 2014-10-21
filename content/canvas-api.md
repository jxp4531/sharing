# Canvas API：初探

---

## whoami

@state: blue, @fragment

* **江雪**
* 奇舞团前端
* 目前支持问答项目

---

## Canvas 是什么？

@state: yellow, @fragment

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

@state: black, @fragment

##代替内容
* ```html
  <canvas>Updata your browser to enjoy canvas!</canvas>
```
---

@state: black, @fragment

## 检测浏览器支持情况

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

@state:black, @fragment

##隐形Canvas
```html
<canvas height="200" width="200"></canvas>
```
---

@state:black, @fragment

##设置Canvas样式
* ```html
<canvas id="diagonal"></canvas>
```

```css
   #diagonal{
   	border:1px solid #dd0000;
   	background:#f88;
   	width:200px;
   	height:200px;
   }
```

---

##画一条对角线

<iframe src="http://jsbin.com/nemoho/5/embed?js" class="" id="" style="border: 1px solid rgb(170, 170, 170); width: 100%; min-height: 500px; height: 46px;"></iframe>

---

@state: green

## box-sizing

---

@fragment

<style type="text/css">
.box-model {width: 10em;height: 6em;background:#09c;box-shadow:#f80 0 0 0px 2em, #690 0 0 0 4em, #999 0 0 0 6em; margin: 6em auto 7.5em auto!important}
.box-model p {line-height: 2em; position: relative; top: -6em}
</style>

<div class="box-model"><p>margin box<br>border box<br>padding box<br>content box</p></div>

box-sizing: content-box | padding-box | border-box

---

* [Demo 1: 全屏页面和自适应表单](http://dabblet.com/gist/de697755292033c055e8)
* [Demo 2: 自适应栅格](http://codepen.io/jason-kinney/pen/cKgzi?editors=110)

---

### Bootstrap、Pure、Foundation大量使用

```css
*, *:before, *:after {
    -webkit-box-sizing: border-box;
    -moz-box-sizing: border-box;
    box-sizing: border-box;
}
```

---

## box-sizing 浏览器支持

<ul class="browser-support">
    <li><img src="img/css3/ie.png" alt="IE">8+</li>
    <li><img src="img/css3/firefox.png" alt="Firefox"></li>
    <li><img src="img/css3/chrome.png" alt="Chrome"></li>
    <li><img src="img/css3/opera.png" alt="Opera">7.0+</li>
    <li><img src="img/css3/safari.png" alt="Safari">3.0+</li>
    <li><img src="img/css3/ios.png" alt="iOS"></li>
    <li><img src="img/css3/android.png" alt="Android">2.1+</li>
<ul>

---

## display: table

@fragment, @state: orange

CSS 2.1

---

```css
display: table                /* <table>     */
display: table-cell           /* <td>        */
display: table-row            /* <tr>        */
display: table-column         /* <col>       */
display: table-column-group   /* <colgroup>  */
display: table-footer-group   /* <tfoot>     */
display: table-header-group   /* <thead>     */
```

---

## 使用表格布局的优点

* 简洁灵活的多栏布局
* 简单的等高解决方案
* 简单的垂直居中
* 防止一行内的元素折行

---

* [Demo 1: 多栏布局](http://dabblet.com/gist/372edba1af0c2ef44adf)
* [Demo 2: 强制一行显示](http://dabblet.com/gist/a8823614dc5cfd0f7394)
* [Demo 3: 垂直居中](http://dabblet.com/gist/2528b21a7867023c2fed)

---

## display: table 浏览器支持

<ul class="browser-support">
    <li><img src="img/css3/ie.png" alt="IE">8+</li>
    <li><img src="img/css3/firefox.png" alt="Firefox"></li>
    <li><img src="img/css3/chrome.png" alt="Chrome"></li>
    <li><img src="img/css3/opera.png" alt="Opera">7.0+</li>
    <li><img src="img/css3/safari.png" alt="Safari"></li>
    <li><img src="img/css3/ios.png" alt="iOS"></li>
    <li><img src="img/css3/android.png" alt="Android"></li>
<ul>

---

@state: purple

## flexbox

---

Flexbox可控制容器内的子元素：

* 水平或垂直排成一行
* 控制子元素对齐方式
* 控制子元素的宽度/高度
* 控制子元素显示顺序
* 控制子元素是否折行

---

Flexbox是W3C布局方面标准中的*终极武器*

---

![axis](img/css3/axis.png)

---

[Flexbox Demo](http://dabblet.com/gist/95e5b65622aeae4d031d)

---

## 新旧标准

* 2009年语法
* 2012年语法

---

```css
.container {
    display: -webkit-box;
    display: -webkit-flex;
    display: flex;
    -webkit-box-direction: normal;
    -webkit-box-orient: horizontal;
    -webkit-flex-direction: row;
    flex-direction: row;
    -webkit-flex-wrap: nowrap;
    flex-wrap: nowrap;
    -webkit-box-pack: start;
    -webkit-justify-content: flex-start;
    justify-content: flex-start;
    -webkit-align-content: stretch;
    align-content: stretch;
}
```

---

## Flexbox浏览器支持(2009标准)

<ul class="browser-support">
    <li><img src="img/css3/ie.png" alt="IE">10+</li>
    <li><img src="img/css3/firefox.png" alt="Firefox"></li>
    <li><img src="img/css3/chrome.png" alt="Chrome"></li>
    <li><img src="img/css3/opera.png" alt="Opera">12.1+</li>
    <li><img src="img/css3/safari.png" alt="Safari"></li>
    <li><img src="img/css3/ios.png" alt="iOS"></li>
    <li><img src="img/css3/android.png" alt="Android">2.1+</li>
<ul>

---

## Flexbox浏览器支持(2012标准)

<ul class="browser-support">
    <li><img src="img/css3/ie.png" alt="IE">11+</li>
    <li><img src="img/css3/firefox.png" alt="Firefox">22+</li>
    <li><img src="img/css3/chrome.png" alt="Chrome">21+</li>
    <li><img src="img/css3/opera.png" alt="Opera">12.1+</li>
    <li><img src="img/css3/safari.png" alt="Safari">6.1+</li>
    <li><img src="img/css3/ios.png" alt="iOS">7.0+</li>
    <li><img src="img/css3/android.png" alt="Android">4.4+</li>
<ul>

---

@state: purple

# Multi-column Layout

---

主要解决文字内容的多列展示，实现报纸杂志效果。

---

[Demo](http://dabblet.com/gist/1e98898598d536015362)

---

## 多列显示浏览器支持

<ul class="browser-support">
    <li><img src="img/css3/ie.png" alt="IE">10+</li>
    <li><img src="img/css3/firefox.png" alt="Firefox"></li>
    <li><img src="img/css3/chrome.png" alt="Chrome"></li>
    <li><img src="img/css3/opera.png" alt="Opera">11.1+</li>
    <li><img src="img/css3/safari.png" alt="Safari"></li>
    <li><img src="img/css3/ios.png" alt="iOS"></li>
    <li><img src="img/css3/android.png" alt="Android"></li>
<ul>

---

### CSS Region

---

让内容依次流入不同的容器。

![region](img/css3/region.png)

---

```css
.content {
    /* 内容源流入到指定管道中 */
    flow-into: <pipe-name>;
}

.region {
    /* 从指定管道中读入内容 */
    flow-from: <pipe-name>;
}
```

---

[Demo](demos/css3/region.html)

---

## CSS Region浏览器支持

<ul class="browser-support">
    <li><img src="img/css3/ie.png" alt="IE">10+</li>
    <li><img src="img/css3/safari.png" alt="Safari">6.1+</li>
    <li><img src="img/css3/ios.png" alt="iOS">7.1+</li>
<ul>

---

## CSS Shapes

---

让内容在各种形状的容器内显示。

---

```css
.content {
    /*
     * shape-outside: 将内容在围绕在一个形状外面显示
     * shape-inside: 将内容在一个形状内部显示
     */
    shape-outside: polygon( /* parameters */ );
}
```

---

## 形状

* circle( radius at position )
* polygon( position, position, position ... )
* ellipse( radius1, radius2 at position )
* inset( top, right, bottom, left, border-radius )

---

* [Demo](http://codepen.io/adobe/full/rmual)

---

## CSS Shapes浏览器支持

<ul class="browser-support">
    <li><img src="img/css3/chrome.png" alt="Chrome">37+</li>
    <li><img src="img/css3/safari.png" alt="Safari">8.0+</li>
    <li><img src="img/css3/ios.png" alt="iOS">8.0+</li>
<ul>

---

@state: green

<p style="font-size:6em"><i class="fa-comments"></i></p>

---

@fragment

## 总结

* box-sizing
* display: table
* flexbox
* multiple column
* css region
* css shape

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
