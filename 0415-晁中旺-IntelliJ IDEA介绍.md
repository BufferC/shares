<h1 type="" align="center"> IntelliJ IDEA介绍


# 一、产品

IDEA(https://www.jetbrains.com/idea/)是 JetBrainshttps://www.jetbrains.com/公司的产品

- 介绍：IntelliJ IDEA 主要用于支持 Java、Scala、Groovy 等语言的开发工具，同时具备支持目前主流的技术和框架，擅长于企业应用、移动应用和 Web 应用的开发

## 1.功能

![](https://img-blog.csdnimg.cn/img_convert/b350bab83bf1886b532ba4e7435f1279.png)

## 2.IDEA 的主要优势（相较于 Eclipse 而言）

① 强大的整合能力。比如：Git、Maven、Spring 等
② 提示功能的快速、便捷
③ 提示功能的范围广
④ 好用的快捷键和代码模板 private static final psf
⑤ 精准搜索

## 3.IDEA版本

IDEA 分为两个版本：旗舰版(Ultimate)和社区版(Community)
旗舰版收费(限 30 天免费试用)，社区版免费，这和 Eclipse 有很大区别![](https://img-blog.csdnimg.cn/img_convert/1223174c8ee59904443304c999ecd690.png)

# 二. windows 下安装过程

## 简单易安装

![](https://img-blog.csdnimg.cn/img_convert/662befc99492d2101d4f3d1b2dae4906.png)

- 确认 32 位版还是 64 位版
- 确认是否与.java、.groovy、.kt 格式文件进行关联，这里也可以选择不关联

## 查看安装目录结构

![](https://img-blog.csdnimg.cn/img_convert/c5badda8019f96a65fc7caef8055244c.png)

- bin：容器，执行文件和启动参数等

- help：快捷键文档和其他帮助文档

- jre64：64 位java 运行环境（内置jre的运行环境）

- lib：idea 依赖的类库

- license：各个插件许可

- plugin：插件

  ![](https://img-blog.csdnimg.cn/img_convert/c19453f72d04bc27b45a1249c1394158.png)

![](https://img-blog.csdnimg.cn/img_convert/c5e1ae1b67f6547a6fec5e44574ed271.png)

## 查看设置目录结构

![](https://img-blog.csdnimg.cn/img_convert/56d1587c4f902206380807e39cc930fb.png)

- 这是 IDEA 的各种配置的保存目录。这个设置目录有一个特性，就是你删除掉整个目录之后，重新启动 IntelliJ IDEA 会再自动帮你生成一个全新的默认配置，所以很多时候如果你把 IntelliJ IDEA 配置改坏了，没关系，删掉该目录，一切都会还原到默认

config文件夹

- config 目录是 IntelliJ IDEA 个性化化配置目录，或者说是整个 IDE 设置目录。此目录可看成是最重要的目录，没有之一，如果你还记得安装篇的介绍的时候，安装新版本的 IntelliJ IDEA 会自动扫描硬盘上的旧配置目录，指的就是该目录。这个目录主要记录了：IDE 主要配置功能、自定义的代码模板、自定义的文件模板、自定义的快捷键、Project 的 tasks 记录等等个性化的设置。

system文件夹

- system 目录是 IntelliJ IDEA 系统文件目录，是 IntelliJ IDEA 与开发项目一个桥梁目录，里面主要有：缓存、索引、容器文件输出等等，虽然不是最重要目录，但也是最不可或缺的目录之一

# 三. 创建 Java 工程

![](https://img-blog.csdnimg.cn/img_convert/8d125b44a0e19502fcb98848a0bfced3.png)

注：IntelliJ IDEA 没有类似 Eclipse 的工作空间的概念（Workspaces），最大单元就是Project。这里可以把 Project 理解为 Eclipse 中的 Workspace。

![](https://img-blog.csdnimg.cn/img_convert/ec690458317f87105634b0f6584427f4.png)

![](https://img-blog.csdnimg.cn/img_convert/d57aa39a57a9a066c36becf120bf1556.png)

![](https://img-blog.csdnimg.cn/img_convert/0aa93731475ce7cf7c57fc22e68e619b.png)

![](https://img-blog.csdnimg.cn/img_convert/07db81ded4908bd58b8db87a41e2e516.png)

![](https://img-blog.csdnimg.cn/img_convert/ee3c7c53469e35e5086454c9438677d6.png)

- 工程下的 src 类似于 Eclipse 下的 src 目录，用于存放代码。
- 工程下的.idea 和 puddingtest.iml 文件都是 IDEA 工程特有的。类似于 Eclipse 工程下的.settings、.classpath、.project 等
- src创建包，然后创建类就可以写代码了

# 四. 创建模块(Module)

在 Eclipse 中我们有 Workspace（工作空间）和 Project（工程）的概念，在 IDEA中只有 Project（工程）和 Module（模块）的概念。这里的对应关系为：

![](https://img-blog.csdnimg.cn/img_convert/161150814836387e678f6af0f34b15f6.png)

- 在 IntelliJ IDEA 中 Project 是最顶级的级别，次级别是 Module。一个 Project可以有多个 Module。目前主流的大型项目都是分布式部署的，结构都是类似这种多 Module 结构。

  ![](https://img-blog.csdnimg.cn/img_convert/2b9eea13b30fbc2e8d72924e0a48c9ae.png)

- 这类项目一般是这样划分的，比如：core Module、web Module、plugin Module、solr Module 等等，模块之间彼此可以相互依赖。通过这些 Module 的命名也可以看出，他们之间都是处于同一个项目业务下的模块，彼此之间是有不可分割的业务关系的

  ![](https://img-blog.csdnimg.cn/img_convert/551e5362ef46e379d3ed896c845e5ca1.png)

  ![](https://img-blog.csdnimg.cn/img_convert/99b7e29807efe357166802ebb161b706.png)

  ![](https://img-blog.csdnimg.cn/img_convert/b502ada20ede0047b964eb5fcae91351.png)

# 五. IDEA导入项目

idea导入(import)项目和打开(open)项目的区别？

- 首先如果你没有把svn或git集成idea,直接下来的项目，那这种情况，他并不属于idea模型的项目，所以这时候要选择导入项目–import
- 如果本身就是idea项目，那么直接打开–open

![](https://img-blog.csdnimg.cn/1ac3a222f71540cd996d88e4f7e95ded.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5ben5YWL5YqbY29kZQ==,size_20,color_FFFFFF,t_70,g_se,x_16)

![](https://img-blog.csdnimg.cn/0d309fa677c64dd9b3476f42289f9866.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5ben5YWL5YqbY29kZQ==,size_16,color_FFFFFF,t_70,g_se,x_16)

重新打开的项目目录下，src目录是失效的（即变成了普通文件夹形式）为了让其恢复为蓝色，右键单击src,然后在下拉列表里选中Mark Directory as–Source Root

![](https://img-blog.csdnimg.cn/3c73d14a74074b1298da57017ff8ced6.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5ben5YWL5YqbY29kZQ==,size_20,color_FFFFFF,t_70,g_se,x_16)

![](https://img-blog.csdnimg.cn/b34ab9e06dda451fa0dc83393e028d4e.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5ben5YWL5YqbY29kZQ==,size_20,color_FFFFFF,t_70,g_se,x_16)

![](https://img-blog.csdnimg.cn/d2366bc5d9f5437db8f84625e10f4622.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5ben5YWL5YqbY29kZQ==,size_20,color_FFFFFF,t_70,g_se,x_16)

![](https://img-blog.csdnimg.cn/ccfbe9746fab4002b43cd2da0bc86d36.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5ben5YWL5YqbY29kZQ==,size_20,color_FFFFFF,t_70,g_se,x_16)

应用——>运行

# 六. 查看项目配置

![](https://img-blog.csdnimg.cn/img_convert/1d6fca54d8da484d13c6765c92b37aaf.png)

![](https://img-blog.csdnimg.cn/img_convert/0b4fa899b7b02d2840fabb28b7c15e5f.png)

# 七. 常用配置

![](https://img-blog.csdnimg.cn/img_convert/8b25c0d89ada2122f3135eae3d2d54b5.png)

## Appearance & Behavior

(1). 修改主题

![](https://img-blog.csdnimg.cn/img_convert/5f95aac5fb8ee8a7443671ce46bbec15.png)


通过插件(plugins)更换主题

## Editor - General

![](https://img-blog.csdnimg.cn/img_convert/c2d864805548ac8f4fa923dc5a0fafbd.png)

设置鼠标滚轮修改字体大小
设置鼠标悬浮提示

![](https://img-blog.csdnimg.cn/img_convert/bd2516123a89f838aa11463a8539e3ac.png)

设置显示行号和方法间的分隔符

![](https://img-blog.csdnimg.cn/img_convert/4e2772d5e03d53e28cc943502fe67fb4.png)

忽略大小写提示

![](https://img-blog.csdnimg.cn/img_convert/21d35de8feefdf6ac89e97540f49a40a.png)

设置取消单行显示 tabs 的操作

![](https://img-blog.csdnimg.cn/img_convert/a05258f9730e45abc72d1392ef4845a3.png)

Editor – Font：设置默认的字体、字体大小、字体行间距

![](https://img-blog.csdnimg.cn/img_convert/00795353fb4201edfee782647d45658d.png)

修改代码中注释的字体颜色

![](https://img-blog.csdnimg.cn/img_convert/6b00c61042a3d61672aab4884160aaee.png)

Doc Comment – Text：修改文档注释的字体颜色
Block comment：修改多行注释的字体颜色
Line comment：修改当行注释的字体颜色
设置项目文件编码

![](https://img-blog.csdnimg.cn/img_convert/194b798d8f9040d6585f540a963d8f93.png)

设置当前源文件的编码

![](https://img-blog.csdnimg.cn/img_convert/5e18e72d8961bafb17137a6c18a2329b.png)

关于模板(Templates)

![](https://img-blog.csdnimg.cn/img_convert/8490ba56acddda875abb209f7e37b1df.png)

![](https://img-blog.csdnimg.cn/img_convert/3a12439fa96ebdc0bc9cd6cf94c2b876.png)

- Live Templates 可以自定义，而 Postfix Completion 不可以。同时，有些操作二者都提供了模板，Postfix Templates 较 Live Templates 能快 0.01 秒

## Build,Execution,Deployment

设置自动编译

![](https://img-blog.csdnimg.cn/img_convert/63997c0984468fd8acbd587b9a782675.png)

## 设置快捷键(Keymap)

![](https://img-blog.csdnimg.cn/img_convert/a1d7daaf7c1368a570e349bae4f433a7.png)

导入已有的设置

## 版本控制(Version Control)

![](https://img-blog.csdnimg.cn/img_convert/1523e78b95532dfab1af04cb2e608049.png)

(1). 提前安装好 Git 的客户端
(2). 关联 git.exe

![](https://img-blog.csdnimg.cn/img_convert/9dee5c682867ab900f75461b97cf2f52.png)

(3). 关联 GitHub 上的账户，并测试连接
由于github登录不上，用gitee尝试

![](https://img-blog.csdnimg.cn/img_convert/7355e6ab6ca4816630ddd32c606e7b7b.png)

(4). 连接成功以后，会下载 github/gitee上的项目

![](https://img-blog.csdnimg.cn/img_convert/d3f1d12a747fb41982db594a3fe40544.png)


复制github或者gitee的仓库的http地址

![](https://img-blog.csdnimg.cn/img_convert/63903c3bf434649e35319bbe88bd2411.png)

![](https://img-blog.csdnimg.cn/img_convert/2552b857a8574e86974d29f290aebd23.png)

![](https://img-blog.csdnimg.cn/img_convert/0ee9f0178805dfa2f3d9a3dd83607391.png)

![](https://img-blog.csdnimg.cn/img_convert/0e78de0858ffc967f01932779011a1f6.png)

(5). 本地代码分享到 GitHub/gitee

![](https://img-blog.csdnimg.cn/img_convert/c439162d532413dbb775d65c3d8d126d.png)



![](https://img-blog.csdnimg.cn/img_convert/22022fd82809ffdd59ecebf23ed3993e.png)

![](https://img-blog.csdnimg.cn/img_convert/e7832a8476ff4005945623e07533bd60.png)

(6). Git 的常用操作

![](https://img-blog.csdnimg.cn/img_convert/0b1023cae7be9ff65122d071533d72ec.png)

- clone：拷贝远程仓库
- commit：本地提交
- push：远程提交
- pull：更新到本地

# 八. 创建 Java Web Project 或 Module

## 创建的静态 Java Web

![](https://img-blog.csdnimg.cn/img_convert/116e925c1ba5f93e5581a390cefd9f87.png)

![](https://img-blog.csdnimg.cn/img_convert/d9da36f139c9115c21ff1fc3b61ecebd.png)

![](https://img-blog.csdnimg.cn/img_convert/a5f749deaa0cbe5f226332646c8fea4a.png)

## 创建动态的 Java Web

之前我们的项目都是普通java项目，如果要使用tomcat运行项目，需要配合web项目来使用。就是说我们开发网站项目。

web项目创建步骤：

创建一个普通的java项目
选择项目右键点击：Add Frameworks Support
勾选：Web Application
(1). 新建项目

![](https://img-blog.csdnimg.cn/img_convert/749fafbd89fa8660c66c5ab0c8f713df.png)

![](https://img-blog.csdnimg.cn/img_convert/19b5efdaa606a6b722bf6b04af6b1282.png)

![](https://img-blog.csdnimg.cn/img_convert/0a6420e7789828e489b8ed68abccf298.png)

(2). 配置 Tomcat

![](https://img-blog.csdnimg.cn/img_convert/d290f875d359c94fc94e6b39c8fbfbca.png)

![](https://img-blog.csdnimg.cn/img_convert/1600d1f7e02c5f5398451a99d82a1e95.png)

![](https://img-blog.csdnimg.cn/img_convert/dea5af7f46f88b06a7c099b9b9a50e94.png)

# 九. 关联数据库

## 关联方式

![](https://img-blog.csdnimg.cn/img_convert/5fdef3d9dd591154bbb8f61576338f73.png)

![](https://img-blog.csdnimg.cn/img_convert/29cbebc2ec6f2e9691c37e8e78e564fd.png)

![](https://img-blog.csdnimg.cn/img_convert/3be4d5328487f3c56bef45929dc2a94d.png)

## IDEA操作数据库

![](https://img-blog.csdnimg.cn/img_convert/bcc9c48f5cdd12bd54ad9257d408a218.png)

# 十. 断点调试

## Debug 的设置

![](https://img-blog.csdnimg.cn/img_convert/c3731b4af436ff35fe6d23bf7a162afc.png)

- 
  设置 Debug 连接方式，默认是 Socket。Shared memory 是 Windows 特有的一个属性，一般在 Windows 系统下建议使用此设置，内存占用相对较少。

## 常用断点调试快捷键

![](https://img-blog.csdnimg.cn/img_convert/82fc784b5b1f0d155a67bf7f1a483436.png)

![](https://img-blog.csdnimg.cn/img_convert/1ebebabcacf7c78660c5f05743b8eb53.png)


或者

![](https://img-blog.csdnimg.cn/img_convert/b4ac49b8ab7f2e70b06b2335007cacec.png)

![](https://img-blog.csdnimg.cn/img_convert/de0b42af5fc6939b8cf134bddbc6c53d.png)

![](https://img-blog.csdnimg.cn/img_convert/4ed31396a95619993fc586c97c99b418.png)

![](https://img-blog.csdnimg.cn/img_convert/1403bdf23c25e9292a5e68cac4b7af47.png)

![](https://img-blog.csdnimg.cn/img_convert/3e6fedbfe1cf65909a3580ab474d1790.png)

# 十一. 配置 Maven

## maven的介绍

Make -> Ant -> Maven -> Gradle

- Maven 是 Apache 提供的一款自动化构建工具，用于自动化构建和依赖管理。


- 开发团队基本不用花多少时间就能自动完成工程的基础构建配置，因为 Maven使用了一个标准的目录结构和一个默认的构建生命周期。在如下环节中，Maven使得开发者工作变得更简单。


- 构建环节： 

![](https://img-blog.csdnimg.cn/img_convert/54701a55e74cfab3fb38c6d7f4bfbe40.png)
1 清理：表示在编译代码前将之前生成的内容删除
2 编译：将源代码编译为字节码
3  测试：运行单元测试用例程序
4 报告：测试程序的结果
5打包：将 java 项目打成 jar 包；将 Web 项目打成 war 包安装：将 jar 或 war 生成到 Maven 仓库中
6部署：将 jar 或 war 从 Maven 仓库中部署到 Web 服务器上运行

## Maven 的配置

![](https://img-blog.csdnimg.cn/img_convert/b62096fe22a73074342e13204b05b808.png)

![](https://img-blog.csdnimg.cn/img_convert/94c205a6b035eef473c1d85b1a9c0f2f.png)

# 十二. 其它设置

## 生成 javadoc

![](https://img-blog.csdnimg.cn/img_convert/33ebf2a392e1eae6f12e1a6125ffebcf.png)

![](https://img-blog.csdnimg.cn/img_convert/bdf4d8c271da8dd3a747a83f913a5476.png)

![](https://img-blog.csdnimg.cn/img_convert/ccf69d653858a6a9ffd66b3a64323f9b.png)

## 缓存和索引的清理

- IntelliJ IDEA 首次加载项目的时候，都会创建索引，而创建索引的时间跟项目的文件多少成正比。在 IntelliJ IDEA 创建索引过程中即使你编辑了代码也是编译不了、运行不起来的，所以还是安安静静等 IntelliJ IDEA 创建索引完成。

- IntelliJ IDEA 的缓存和索引主要是用来加快文件查询，从而加快各种查找、代码提示等操作的速度

清理缓存和索引

![](https://img-blog.csdnimg.cn/img_convert/4e1dc4210c2d93d61cbe165f00757a18.png)

![](https://img-blog.csdnimg.cn/img_convert/e45133afac3ca793b3b1f6dc314b1c3c.png)

## 取消更新

![](https://img-blog.csdnimg.cn/img_convert/37d30a6daccc43aa7a85250bac952b45.png)

## 插件的使用

官网插件库：https://plugins.jetbrains.com/

![](https://img-blog.csdnimg.cn/img_convert/af19bff16e4874fabd15918e3b75d853.png)


