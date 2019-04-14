一款基于jQuery的简便的，高扩展性的全屏轮播插件。可用于产品轮播导航，个人信息展示等场景。

### 基本使用
---

#### 引入

```html
<link rel="stylesheet" href="../src/jquery.fsscroll.css">
<script src="jquery.min.js"></script>
<script src="jquery.fsscroll.js"></script>
 ```

#### DOM结构

```html
<div class="container">
  <div class="sections">
    <div class="section"></div>
    <div class="section"></div>
    <div class="section"></div>
    <div class="section"></div>
  </div>
</div>
```

.container容器表示轮播容器，.section表示每一页容器。以上类别可以自定义，只要在插件参数中加入对应配置即可。

#### 加载插件

data属性方式加载：

```html
<div class="container" data-fs-scroll>
  ...
</div>
```

JS方式加载：

```html
<script>
  $('.container').fsScroll({
    direction: 'horizontal'
  })
</script>
```

### 参数说明

--- 

| 参数 | 说明 | 类型 | 默认值|
| --- | --- | --- | --- |
| selectors|选择器类型对象|Object| 如下 |
| index | 当前页索引 | int | 0|
| timing | 动画曲线 | string | ease|
| duration | 动画时间（ms）| int | 500 |
| loop | 是否循环播放 | boolean | false |
| pagination | 是否显示分页 | boolean | true | 
| keyboard | 是否支持键盘操作 | boolean | false |
| direction | 滑动方向 | string | vertical |
| beforeScroll | 滑动开始前回调 | function | null | 
| afterScroll | 滑动结束后回调 | function | null | 

#### option.selectors

- 默认值

```js
{
  selectors: {
    sections: '.sections', // 播放页父容器类
    section: '.section',   // 播放页容器类
    page: '.page',     // 分页容器类
    active: '.active'   // 活动页类
  }
}

```

#### option.beforeScroll(a,b)

- 说明： 滑动开始前回调
- 函数参数：
 ``a``: 显示页的容器section， jquery对象
 ``b``: 显示页的索引

 #### option.afterScroll(a,b)

- 说明： 滑动结束后回调
- 函数参数：
 ``a``: 显示页的容器section， jquery对象
 ``b``: 显示页的索引
