# before/after

:before 与 :after是伪元素，实际不存在DOM元素中，但却显示在页面，看起来像是DOM元素，下面实现几个应用

* 六角星
**css**
~~~css
#start-six {
    width: 0;
    height: 0;
    border-left: 50px solid transparent;
    border-right: 50px solid transparent;
    border-bottom: 100px solid red;
    position: relative;
}

#start-six:after {
    width: 0;
    height: 0;
    border-left: 50px solid transparent;
    border-right: 50px solid transparent;
    border-top: 100px solid red;
    position: absolute;
    content: "";
    top: 30px;
    left: -50px;
}
~~~
**显示效果**

![六角星](..\img\star-six.png)


* 杂志
**css**
~~~
.left {
    float: left;
}

.right {
    float: right;
}

.box {
    height: 0;
}
/*
  这里不能用after否则会跑到文本内容之下
*/

.left:before, .right:before {
    content: '';
    width: 100px;
    height: 300px;
}
.left:before {
    float: right;
    /*background: #000;*/
}

.right:before {
    float: left;
    /*background: green;*/
}

.cat {
    position: absolute;
    width: 200px;
    height: 300px;
    left: 320px;
}

img {
    width: 100%;
    height: 100%;
}

~~~

**html**
~~~
<div class="row">
    <div class="l col-md-3"></div>
    <div class="box col-md-6">
        <div class="left col-md-6">Paris and Berlin appear on a collision course over the replacement of Jean-Claude
            Juncker as
            president
            of the European commission after poor results for the centre-right in the European elections damaged Angela
            Merkel’s
            choice for the post.
            Paris and Berlin appear on a collision course over the replacement of Jean-Claude
            Juncker as
            president
            of the European commission after poor results for the centre-right in the European elections damaged Angela
            Merkel’s
            choice for the post.
            Paris and Berlin appear on a collision course over the replacement of Jean-Claude
            Juncker as
            president
            of the European commission after poor results for the centre-right in the European elections damaged Angela
            Merkel’s
            choice for the post.
        </div>
        <div class="cat"><img src="http://placekitten.com/200/300" alt="cat"></div>
        <div class="right col-md-6">The German chancellor’s backing for the German MEP Manfred Weber, who leads the
            European People’s
            party of which her CDU party is a member, is facing tough resistance from the French president Emmanuel
            Macron
            in
            the post-election jockeying for top jobs.
            The German chancellor’s backing for the German MEP Manfred Weber, who leads the
            European People’s
            party of which her CDU party is a member, is facing tough resistance from the French president Emmanuel
            Macron
            in
            the post-election jockeying for top jobs.
            The German chancellor’s backing for the German MEP Manfred Weber, who leads the
            European People’s
            party of which her CDU party is a member, is facing tough resistance from the French president Emmanuel
            Macron
            in
            the post-election jockeying for top jobs.
        </div>
    </div>
    <div class="r col-md-3"></div>
</div>

~~~
**效果显示**
![杂志编辑](..\LearnCSS\img\cat.png)

