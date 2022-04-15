# Layui

**下载地址：https://lh_yun.gitee.io/layui/www.layui.com/index.html**



# 介绍：

大家好，我是来自20软信2班的许文浩，今天给大家分享的内容为：Layui框架。

## Layui简介：

l**ayui**（谐音：类 UI) 是一套开源的[ Web UI ](https://baike.baidu.com/item/ Web UI /5701329)解决方案，采用自身经典的模块化规范，并遵循原生[ HTML](https://baike.baidu.com/item/ HTML/97049)/CSS/[JS](https://baike.baidu.com/item/JS/10687961) 的开发方式，常适合网页界面的快速开发。layui 区别于那些基于[MVVM](https://baike.baidu.com/item/MVVM/96310) 底层的前端框架，它更多是面向后端开发者，无需涉足[前端](https://baike.baidu.com/item/前端/5956545)各种工具，只需面对[浏览器](https://baike.baidu.com/item/浏览器/213911)本身，让一切所需要的元素与交互。 

2021年9月，layui 官网发布公告称，layui 官网 2021 年 10 月 13 日 进行下线，届时，包括新版下载、文档和示例在内的所有框架日常维护工作，将全部迁移到 Github 和 Gitee。

## 产生背景：

事实上，layui 更多是面向于后端开发者，所以在组织形式上毅然采用了几年前的以浏览器为宿主的类 AMD 模块管理方式，却又并非受限于 CommonJS 的那些条条框框，它拥有自己的模式，更加轻量和简单。layui 定义为“经典模块化”，并非是刻意强调“模块”理念本身，而是有意避开当下 JS 社区的主流方案，试图以尽可能简单的方式去诠释高效。它的所谓经典，是在于对返璞归真的执念，它以当前浏览器普通认可的方式去组织模块。 layui 认为这种轻量的组织方式，仍然可以填补 WebPack 以外的许多场景。所以它坚持采用经典模块化，也正是能让人避开工具的复杂配置，重新回归到原生态的 HTML/CSS/JavaScript本身。

## 主要功能：

**layui 可作为 PC 网页端界面速成开发方案**

## 运行环境：

**Chrome / Firefox / Safari /Internet Explorer 8.0+**

## 主要构成：

### 组件：

layui 的元素由以下组成：

**布局（栅格、后台布局）、颜色、字体图标、动画、按钮、表单、导航条、面包屑、选项卡、进度条、面板、静态表格、徽章、时间线、辅助元素等。**

### 模块：

layui 提供了丰富的内置模块，他们皆可通过模块化的方式按需加载，其中包括：**[layer](https://baike.baidu.com/item/layer/972483)、layDate、layPage、laytpl、table、form、upload、element、tree、layeditor、rate、carousel、flow、util、code等。**

## layui的优点和缺点：

**优点有以下几方面：**

（1）layui属于轻量级框架，简单美观。适用于开发后端模式，它在服务端页面上有非常好的效果。

（2）layui是提供给后端开发人员最好的ui框架，基于DOM驱动，只要不涉及到交互layui还是很不错的。

**缺点如下：**

（1）layui出现较迟，想必其他前端框架来说还是不太成熟。现在已更新到2.X版本了。

（2）在实现前端交互上比较麻烦，因为页面的增删改查都需要查询DOM元素。

## 兼容性：

**layui 兼容人类正在使用的全部浏览器（IE6/7除外），可作为 PC 端后台系统与前台界面的速成开发方案。**

## Layui的目录结构：

**|—css  //css目录**

**|    |—modules    // 模块css目录（一般模块如果相对较大，我们会单独提取，比如下面三个：）**

**|    |   |—laydate**

**|    |   |—layer**

**|    |   |—layim**

**|    |__layui.css   //核心样式文件**

**|—font     //字体图标目录**

**|—inages      //图片资源目录（目前只有layui和编译器用到的GIF表情）**

**|—lay    //模块核心目录 ——modules   //各模块组件**

**|—layui.js     //基础核心库**

**|___layui.all.js     //包含layui.js和所有模块的合并文件**



# 下载和使用：

下载Layui：layui 是国内开发的 JavaScript 类库，所以下载比较简单，直接到 [layui官网](https://www.layui.com/) 下载即可，

官网下载下来的是一个layui的压缩包，点开压缩包，只需要解压layui这个文件夹。

#### ![Layui图片](C:\Layui图片\Layui图片.png)

## 使用layui复制到项目中：

首先将我们解压好的layui文件夹复制到我们的项目中：

## ![复制到项目](C:\Layui图片\复制到项目.png)

css 文件中存放的是 css 文件，lay 文件中存放的是一些模块的 js 代码，layui.all.js 和 layui.js 是使用 layui 时必须引入的 js 文件，这两个文件引入一个即可，在使用上稍微有些不同，layui.all.js 在使用时语法比较简单，layui.js 则是标准使用语法，官方给出的帮助文档中使用的就是 layui.js

## 引入文件：

前面看到了 layui 中有 css 文件和 js 文件，所以我们在引入文件的时候需要引入 css 文件和 js 文件

```html
<link rel="stylesheet" type="text/css" href="../../layui/css/layui.css" media="all" />
<script sre="../../layui/layui.all.js"></script>
      
```

将 css 文件和 js 文件引入之后就可以使用 layui 了。

# 页面布局：

## 布局容器：

1.固定宽度（两侧有留白效果）

```html
<div class="layui-container">
    <div class="layui-row">
        固定长度......
    </div>
</div>
```

2.完整宽度（占据屏幕宽度的100%）

```html
<div class="layui-fluid">
    完整宽度......
</div>
```

## 栅格系统：

```html

<!-- 
    栅格系统
        1、定义行 .layui-row
        2、定义列 .layui-col-md*
            md 表示不同屏幕的标识（xs、sm、md、lg）
            * 表示列的数量
 -->
<!-- 布局容器 -->
<div class="layui-container">
    <!-- 定义行 -->
    <div class="layui-row">
        <!-- 定义列 -->
        <div class="layui-col-md9">
            你的内容 9/12
        </div>
        <div class="layui-col-md3">
            你的内容 3/12
        </div>
    </div>
</div>

```

# 组件示例：

### 弹出层：ayui模块化使用

只需要引入layui的css于js文件，在script中使用layui,use()加载模块

```html
<script type="text/javascript">
        layui.use(['layer'],function () {
            var layer = layui.layer;

            layer.msg('你愿意做我女朋友吗?',{
                tiem: 0, //不自动关闭
                btn: ['愿意', '死了这条心吧'],  //按钮
                yes: function (index) {
                    layer.close(index);     //关闭当前弹出层
                    layer.msg('晚点遇见你，余生都是你',{
                        icon: 6,    //图标
                    })
                }
            })
        });
    </script>
```

![弹出层](C:\Layui图片\弹出层.png)

### 日期与时间选择：layui.laydate

模块加载名称：*laydate*

```html
<div class="layui-inline"> <!-- 注意：这一层元素并不是必须的 -->
  <input type="text" class="layui-input" id="test1">
</div>

    <script type="text/javascript">
        layui.use(['laydate'],function () {
            var laydate = layui.laydate;

              //执行一个laydate实例
			  laydate.render({
			    elem: '#test1' //指定元素
			  });
		});
    </script>
```

![日期和时间选择](C:\Layui图片\日期和时间选择.png)

### 分页：layui.laypage

模块加载名称：laypage ，指向一个用于存放分页的容器，通过服务端得到一些初始值，即可完成分页渲染

```html
<div id="test1"></div>
    <script type="text/javascript">
        layui.use(['laydate','laypage'],function () {
            var laydate = layui.laydate;
            var laypage = layui.laypage;

              laypage.render({
			    elem: 'test1' //注意，这里的 test1 是 ID，不用加 # 号
			    ,count: 50 //数据总数，从服务端得到
			  });
        });
    </script>
```

![分页](C:\Layui图片\分页.png)