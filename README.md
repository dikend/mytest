
#web前端规范

你是否常常碰到以下问题：
* 你总是看不懂他写的代码，或者读起来很吃力；
* 你需要改他的代码却无从下手，或总是要去问他这里是什么改了会不会影响其他代码；
* 你和他一起开发一个产品，你总是怕代码和他有冲突或互相影响；
* 你的代码在多次维护任务之后变得越来越臃肿，越来越难以维护。

解决以上问题只需一种方法——读我们的规范！


##HTML规范 - 整体结构

HTML基础结构
```javascript
  <!DOCTYPE html>
    <html>
    <head>
    <meta charset="utf-8"/>
    <meta name="viewport" content="width=device-width, initial-scale=1”>
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

    开始注释：<!-- 注释文案 -->（文案两头空格）。
    结束注释：<!-- /注释文案 -->（文案前加“/”符号，类似标签的闭合）。
    允许只有开始注释！



##关于作者

```javascript
  var ihubo = {
    nickName  : "草依山",
    site : "http://jser.me"
  }
```