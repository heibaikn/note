# css

## 盒子模型
> Box Model：边距，边框，填充，和实际内容
> box-sizing属性:border-box的width=border+padding+centent,centent-box的width=centent

## 清空浮动
BFC(块级格式化上下文)
形成BFC模式的盒子就会按自己的渲染规则布局和定位而不影响其他环境中的布局（常见的浮动元素脱离标准文档流，其内部子元素则按照其相应的渲染规则布局，而浮动元素之间则互不影响，其自身就像一个独立的容器）
float的值不为none
overflow值不为visible
position值不为static / relative
display的值为table-cell，table-caption， inline-block中的任何一个

```css
.clearfix:after {
        content: '';
        clear: both;
        display: block;
    }
```

## flex弹性布局

```css
flex-direction
flex-wrap
flex-flow
justify-content
align-items
align-content
```

## 常用css3
> 框模型 box-sizing:border-box; 

> 元素类型定义 display: flex; display:grid;

> 边框 border-image;border-radius;box-shadow;

> 背景 background-image;background-size;background-Origin(图片区域border,padding,content);background-clip(颜色区域)

> transform|2D转换 translate旋转,rotate缩放,scale移动（平移）,skew和倾斜

> transform|3D转换 translate旋转,rotate缩放,scale移动,perspective

> animation|动画 name duration timing-function delay iteration-count direction fill-mode play-state;

```css
@keyframes slideInUp {
  from {
    transform: translate3d(0, 100%, 0);
    visibility: visible;
  }

  to {
    transform: translate3d(0, 0, 0);
  }
}

.slideInUp {
  animation-name: slideInUp;
}
```

> column 多列,瀑布流布局 count width

> 媒体查询 @media 响应式布局 	
手机 < 768px < ipad < 992px < pc屏幕 <1200px < 大屏

## position

raletive
absolute
fixed
sticky

