# Animation

animation 动画，用于背景色，高度，宽度等
使用需要加上**@keyframs**

1. 样例一
~~~html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>active</title>
    <script src="https://cdn.bootcss.com/jquery/1.12.4/jquery.js"></script>
    <link rel="stylesheet" href="active.css">
    <script src="all.js"></script>
</head>
<body>
<div class="element"></div>
</body>
</html>
~~~

~~~css
.element {
    width: 100%;
    height: 100%;
    animation: pulse 5s infinite;
}

@keyframes pulse {
    0% {
        background-color: #001F3F;
    }
    100% {
        background-color: #FF4136;
    }
}

html,body {
    height: 100%;
}
~~~

通过运用animation可以自定义动画，下面列出属性值

| Animation-      | 效果                                                         |
| --------------- | ------------------------------------------------------------ |
| name            | 指定由@keyframes描述的关键帧名称                             |
| duration        | 设置动画一个周期的时长                                       |
| function        | 设置动画速度                                                 |
| delay           | 设置演示                                                     |
| direction       | 设置动画在每次运行完后是反向运行还是重新回到开始位置重复运行 |
| iteration-count | 设置动画重复次数，infinite无限次重复动画                     |
| fill-mode       | 指定动画执行前后如何为目标元素应用样式                       |
| play-state      | 允许暂停和恢复动画                                           |



样例二

~~~html
<div class="element"></div>
~~~

~~~css
.element {
    height: 250px;
    width: 250px;
    margin: 0 auto;
    background-color: red;
    animation-name: stretch;
    animation-duration: 1.5s;
    animation-timing-function: ease-out;
    animation-delay: 0;
    animation-direction: alternate;
    animation-iteration-count: infinite;
    animation-fill-mode: none;
    animation-play-state: running;
}

@keyframes stretch {
    0% {
        transform: scale(.3);
        background-color: red;
        border-radius: 100%;
    }
    50% {
        background-color: orange;
    }
    100% {
        transform: scale(1.5);
        background-color: yellow;
    }
}

html, body {
    height: 100%;
}

body {
    display: flex;
    align-items: center;
    justify-content: center;
}
~~~

可以实现多种动画组合执行
样例三
~~~html
<div class="element"></div>
~~~

~~~css
.element {
    height: 400px;
    width: 400px;
    background: red;
    animation: pulse 3s ease infinite alternate,
    nudge 5s linear infinite alternate;
    border-radius: 100%;
}

@keyframes pulse {
    0%, 100% {
        background-color: red;
    }
    50% {
        background-color: orange;
    }
}

@keyframes nudge {
    0%, 100% {
        transform: translate(0,0);
    }
    50% {
        transform: translate(0,150px);
    }
    80% {
        transform: translate(0,-150px);
    }
}

html, body {
    height: 100%;
}

body {
    display: flex;
    align-items: center;
    justify-content: center;
}
~~~

## 效果与参考
[CSS-Tricks](https://css-tricks.com/almanac/properties/a/animation/)
[properties](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Animations/Using_CSS_animations)
