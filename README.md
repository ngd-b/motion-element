# motion-element
页面动效，整理并实现不限于CSS、JS、Canvas。

### Example-01 - CSS 动画(animate)

知识点：

1. `@keyframes` 自定义动画，名称作为`animation-name`

    支持所有的CSS 属性，同一关键帧中多次定义属性，以最后一次为准；不支持`!important`
    ```css
    /*两端关键帧*/
    @keyframes Motion{
        from{
            /*...*/
        }
        to{
            /*...*/
        }
    }
    /* 使用百分比，创建多个关键帧 */
    @keyframes Motion{
        0%{
            /*...*/
        }
        25%{
            /*...*/
        }
        50%{
            /*...*/
        }
        100%{
            /*...*/
        }
    }
    ```
2. `linear-gradient` 多种颜色线性渐变的效果，

    属于`<gradient>`数据类型系`<image>`自数据类型。只能用于可以使用image的地方。即`background-image`或者`bordre-image`

3. `animation` 创建动画。

    属性包括：
    |属性|释义||
    |-----|-----|-----|
    |`animation-delay` |延时执行|
    |`animation-direction`| 一次运行完后重复运行的方向
    |`animation-duration` |执行周期
    |`animation-iteration-count`| 执行次数
    |`animation-name`| @keyframes动画名称 |
    |`animation-timing-function`| 动画执行过程中的速度、
    |`animation-play-state`| 允许暂停或恢复动画|
    |`animation-fill-mode`| 设置执行之前和之后是否应用关键帧样式
```css
#container .item>span{
    width: 100%;
    height: 64px;
    display: inline-block;
    background: linear-gradient(180deg, rgba(24, 144, 255, 0) 0, #1890ff);
    animation: meterSlider 4s ease-in-out 1.5s infinite;
    transform: translateY(-64px);
}
/* 自定义特效、朝向y轴移动*/
@keyframes meterSlider {
    0%,25%{
        transform: translateY(-64px);
    }
    75%,100%{
        transform: translateY(676px);
    }
}
```