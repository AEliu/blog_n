---
title: 前端笔记
urlname: Front-end-note
date: 2020-05-02 14:34:22
tags: [IT, Web-development]
---

记录关于前端所见、所闻，已知、未知的基础知识以备查。

<!-- more -->

## HTML

HTML (HyperText Markup Language)，超文本标记语言，由元素组成，而元素由标签、内容、属性等组成。

## CSS

图片圆形外框

```css
border-radius: 50%;
```

`type` 属性 为 `checkbox` 的选择器：

```css
[type='checkbox'] {
    margin: 10px 0px 15px 0px;
}
```

CSS 变量

```css
background: var(--pengiun-skin, black);
```

随着屏幕宽度改变（如小于 350px 时）

```css
@media (max-width: 350px) {

}
```

文本相关样式

```css
text-align: justify; /*除最后一行，其他两端对齐*/

text-transform: lowercase; /*全小写*/
text-transform: uppercase; /*全大写*/
text-transform: capitalize; /*单词首字母大写*/
text-transform: initial; /*句子首字母大写*/
text-transform: inherit; /*继承*/
text-transform: none; /*没变化*/

line-height: 25px; /*行高*/
```

阴影效果 `box-shadow`，可以有多个阴影，用“`,`”分开，如下所示：

```css
/* x偏移量 | y偏移量 | 阴影模糊半径 | 阴影扩散半径 | 阴影颜色 */
box-shadow: 0 10px 20px rgba(0,0,0,0.19), 0 6px 6px rgba(0,0,0,0.23);
```

链接相关

```css
/*鼠标飘上面*/
a:hover {
    color: blue;
}
```

位置

```css
/*与正常应该在的位置相比较*/
h2 {
    position: relative;
    top: 15px;
  }
/*相对其上级的位置*/
#searchbar {
    position: absolute;
    top: 50px;
    right: 50px;
  }
/*相对浏览器窗口的位置*/
#navbar {
    position: fixed;
    top: 0;
    left: 0;
  }
/*不再按顺序走下去，在上级元素里浮动，属性值有 left、right 等，常与 width 配合使用*/
#left {
    float: left;
    width: 50%;
  }
#right {
    float: right;
    width: 40%;
  }
/*元素重叠的关系，z-index 越大越在上层*/
z-index: 2;
/*通过 margin 设置居中*/
margin: auto;
```

背景渐变色

```css
div {
    border-radius: 20px;
    width: 70%;
    height: 400px;
    margin: 50px auto;
    background: linear-gradient(35deg, #CCFFFF, #FFCCCC);
  }
```

效果如图：

<img src="https://tva1.sinaimg.cn/large/007S8ZIlly1geejznx5yhj30g60ow79k.jpg" width=200px>

改变元素外观

```css
transform: scale(2); /*比例*/
transform: skewX(24deg); /*X 轴的倾斜*/
```

## JavaScript
