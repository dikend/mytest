
#web前端规范

你是否常常碰到以下问题：
* 你总是看不懂他写的代码，或者读起来很吃力；
* 你需要改他的代码却无从下手，或总是要去问他这里是什么改了会不会影响其他代码；
* 你和他一起开发一个产品，你总是怕代码和他有冲突或互相影响；
* 你的代码在多次维护任务之后变得越来越臃肿，越来越难以维护。

解决以上问题只需一种方法——读我们的规范！


##HTML规范 

HTML基础结构
```javascript
  <!DOCTYPE html>
    <html>
    <head>
    <meta charset="utf-8"/>
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <meta http-equiv="X-UA-Compatible" content="IE=Edge,chrome=1">
    <meta name="keywords" content=""/>
    <meta name="description" content=""/>
    <title>开发规范</title>
    <link rel="stylesheet" href="css/style.css"/>
    <link rel="shortcut icon" href="img/favicon.ico"/>
    </head>
    <body>
      
    </body>
  </html> 
```

###结构顺序和视觉顺序基本保持一致

* 有时候为了便于搜索引擎抓取，我们也会将重要内容在HTML结构顺序上提前。
* 用div代替table布局，可以使HTML更具灵活性，也方便利用CSS控制。
* table不建议用于布局，但表现具有明显表格形式的数据，table还是首选。

###结构、表现、行为三者分离，避免内联

* 使用link将css文件引入，并置于head中。
* 使用script将js文件引入，并置于body底部。

###其他说明

* 一个标签上引用的className不要过多，越少越好。
比如避免这种情况频繁：<div class="class1 class2 class3 class4"></div>

###说明文案的注释方法
采用类似标签闭合的写法，与HTML统一格式；注释文案两头空格，与CSS注释统一格式。
* 开始注释：<!-- 注释文案 -->（文案两头空格）。
* 结束注释：<!-- /注释文案 -->（文案前加“/”符号，类似标签的闭合）。
* 允许只有开始注释！

```javascript
    <!-- 头部 -->
        <div class="g-hd">
            <!-- LOGO -->
            <h1 class="m-logo"><a href="#">LOGO</a></h1>
            <!-- /LOGO -->
            <!-- 导航 -->
            <ul class="m-nav">
                <li><a href="#">NAV1</a></li>
                <li><a href="#">NAV2</a></li>
                <!-- 更多导航项 -->
            </ul>
            <!-- /导航 -->
        </div>
    <!-- /头部 -->
```

##CSS规范

###CSS文件的分类和引用顺序
我们按照CSS的性质和用途，将CSS文件分成“公共型样式”、“特殊型样式” 等。

* 公共型样式：包括了以下几个部分：“标签的重置和设置默认值”、“统一调用背景图和清除浮动或其他需统一处理的长样式”、“网站通用布局”、“通用模块和其扩展”、“元件和其扩展”、“功能类样式”、“皮肤类样式”。
* 特殊型样式：当某个栏目或页面的样式与网站整体差异较大或者维护率较高时，可以独立引用一个样式：“特殊的布局、模块和元件及扩展”、“特殊的功能、颜色和背景”，也可以是某个大型控件或模块的独立样式。

###CSS规范 - 命名规则

* 使用类选择器，尽量避免ID选择器
* 分类的命名方法：使用单个字母+"-"为前缀
    * 布局（grid）（.g-）；模块（module）（.m-）；元件（unit）（.u-）；功能（function）（.f-）；皮肤（skin）（.s-）；状态（.z-）。
* 后代选择器命名

        约定不以单个字母+"-"为前缀且长度大于等于2的类选择器为后代选择器，如：.item为m-list模块里的每一个项，.text为m-list模块里的文本部分：.m-list .item{}.m-list .text{}。
        一个语义化的标签也可以是后代选择器，比如：.m-list li{}。
        不允许单个字母的类选择器出现，原因详见下面的“模块和元件的后代选择器的扩展类”。
* 命名应简约而不失语义
```javascript
/* 反对：表现化的或没有语义的命名 */
.m-abc .green2{}
.g-left2{}
/* 推荐：使用有语义的简短的命名 */
.m-list .wrap2{}
.g-side2{} 
```
* 相同语义的不同类命名
    * 方法：直接加数字或字母区分即可（如：.m-list、.m-list2、.m-list3等，都是列表模块，但是是完全不一样的模块）。
    * 其他举例：.f-fw0、.f-fw1、.s-fc0、.s-fc1、.m-logo2、.m-logo3、u-btn、u-btn2等等。

* 模块和元件的扩展类的命名方法
    * 当A、B、C、...它们类型相同且外形相似区别不大，那么就以它们中出现率最高的做成基类，其他做成基类的扩展。
    * 方法：+“-”+数字或字母（如：.m-list的扩展类为.m-list-1、.m-list-2等）。
    * 补充：基类自身可以独立使用（如：class="m-list"即可），扩展类必须基于基类使用（如：class="m-list m-list-2"）。
