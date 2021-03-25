## CSS 面试知识点总结
整理了 CSS 面试的部分知识点

### 目录

- [水平垂直居中](#水平垂直居中)
- [css选择符](#css选择符)
- [css优先级算法](#css优先级算法)


#### 水平垂直居中

```
一般常见的几种居中的方法有：

对于宽高固定的元素
（1）我们可以利用margin:0 auto来实现元素的水平居中。
（2）利用绝对定位，设置四个方向的值都为0，并将margin设置为auto，由于宽高固定，因此对应方向实现平分，
     可以实现水平和垂直方向上的居中。
（3）利用绝对定位，先将元素的左上角通过top:50%和left:50%定位到页面的中心，
     然后再通过margin负值来调整元素的中心点到页面的中心。
（4）利用绝对定位，先将元素的左上角通过top:50%和left:50%定位到页面的中心，
     然后再通过translate来调整元素的中心点到页面的中心。
（5）使用flex布局，通过align-items:center和justify-content:center设置容器的垂直和
     水平方向上为居中对齐，然后它的子元素也可以实现垂直和水平的居中。

对于宽高不定的元素，上面的后面两种方法，可以实现元素的垂直和水平的居中。
```

水平居中：给 div 设置一个宽度，然后添加 margin:0 auto 属性
```css
div {
  width: 200px;
  margin: 0 auto;
}
```
水平居中，利用 text-align:center 实现
```css
.container {
  background: rgba(0, 0, 0, 0.5);
  text-align: center;
  font-size: 0;
}
.box {
  display: inline-block;
  width: 500px;
  height: 400px;
  background-color: pink;
}
```
让绝对定位的 div 居中
```css
div {
  position: absolute;
  width: 300px;
  height: 300px;
  margin: auto;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
  background-color: pink; /*方便看效果*/
}
```
水平垂直居中一
```css
/*确定容器的宽高宽500高300的层设置层的外边距div{*/
position: absolute;/*绝对定位*/
width: 500px;
height: 300px;
top: 50%;
left: 50%;
margin: -150px00-250px;/*外边距为自身宽高的一半*/
background-color: pink;/*方便看效果*/
}
```
水平垂直居中二
```css
/*未知容器的宽高，利用`transform`属性*/
div {
  position: absolute; /*相对定位或绝对定位均可*/
  width: 500px;
  height: 300px;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background-color: pink; /*方便看效果*/
}
```
水平垂直居中三
```css
/*利用flex布局实际使用时应考虑兼容性*/
.container {
  display: flex;
  align-items: center; /*垂直居中*/
  justify-content: center; /*水平居中*/
}
.containerdiv {
  width: 100px;
  height: 100px;
  background-color: pink; /*方便看效果*/
}
```
水平垂直居中四
```css
/*利用text-align:center和vertical-align:middle属性*/
.container {
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  background: rgba(0, 0, 0, 0.5);
  text-align: center;
  font-size: 0;
  white-space: nowrap;
  overflow: auto;
}
.container::after {
  content: '';
  display: inline-block;
  height: 100%;
  vertical-align: middle;
}
.box {
  display: inline-block;
  width: 500px;
  height: 400px;
  background-color: pink;
  white-space: normal;
  vertical-align: middle;
}
```

#### css选择符

```
（1）id选择器（#myid）
（2）类选择器（.myclassname）
（3）标签选择器（div,h1,p）
（4）后代选择器（h1 p）
（5）相邻后代选择器（子）选择器（ul>li）
（6）兄弟选择器（li~a）
（7）相邻兄弟选择器（li+a）
（8）属性选择器（a[rel="external"]）
（9）伪类选择器（a:hover,li:nth-child）
（10）伪元素选择器（::before、::after）
（11）通配符选择器（*）
```

#### css优先级算法



