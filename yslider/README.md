# H5 轮播 slider 组件 #

> 本文主要介绍一款简单的h5 slider --Yslider, 采用原生js书写，使用于任何js框架
> ![slider](./yslider.png)

## Yslider 参数 ##
> Yslider 参数以对象形式传入
> 1、target: Slier 容器 DOM 的 id 属性， 必填， 类型 string  
> 2、interval: 图片切换间隔时间， 非必填， 类型 number, 单位 s(秒)， defualt 3s  
> 3、showCircle: 是否显示圆点导航， 非必填， 类型 boolean, default true   
> 4、circleColor： 圆点颜色， 非必填， 类型 颜色(string)， default '#00F5FF'   
> 5、imgArray: 图片列表， 必填， 类型 array
>> - redirect: 点击图片跳转地址， 非必填， 类型 url(string), 
>> - url: 图片地址， 必填， 类型 url(string)
>> - detail: 图片介绍， 放在 alt 属性中， 非必填，类型 string

## Yslider 使用 ##
> 1、在html 标签中定一个 slider 元素用于容纳图片列表, 并定义好slider容器的尺寸
```html
<style>
.page-wrap .slider {  //
    height: 25rem; //定义容器高度，
    width: 100%; //容器宽度
    overflow: hidden;  //超出不显示
}
</style>
<div class="page-wrap">
    <div id="slider" class="slider">  //slider 容器标签 一定包含id 属性
    </div>
</div>
<script src="/static/common/slider/slider-1.0.js"></script> <!--引入 slider-->
```

> 2、使用slider
```html
<script>
(function(win) {
    imgArray = [
        {redirect: '', url: '/static/images/slider1.jpg', detail: 'img1'},
        {redirect: '', url: '/static/images/slider2.jpg', detail: 'img2'},
        {redirect: '', url: '/static/images/slider3.jpg', detail: 'img3'},
        {redirect: '', url: '/static/images/slider4.jpg', detail: 'img4'}
    ]  //准备图片列表， redirect 为点击图片跳转链接， url 为图片下载地址， detail: 为图片说明

     Yslider({  //初始化 yslider
        target: 'slider',  //slider 容器id
        interval: 2,  //图片切换间隔时间, 单位s, default 3s
        imgArray: imgArray, //图片列表
        showCircle: true,  //是否显示圆点导航
        circleColor: '#00C5CD', //圆点导航颜色
     })
  })(window);
</script>
```