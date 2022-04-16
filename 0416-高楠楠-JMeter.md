## 一、JMeter概述

#### 1. 概述

**Jmeter是Apache组织开发的基于Java的性能测试工具，主要用来测试部署在服务器端的应用程序的性能**。**近来，JMeter因为其使用简单，现在也常被用来作为接口测试工具。**

啥？什么是性能测试，怎么又来了个接口测试？

例子：比如，你开了一个网店，兴冲冲地准备双十一大干一把，没想当天活动的时候大量用户一访问你的网店，你的网店挂了，那怎么办？办法就是在实际搞活动之前，先测试一下以确认系统能承受那么多的用户，当然测试的时候我们不需要请真正的这么多实际用户，否则得花多少钱啊，JMeter就是那个能帮助模拟大量用户访问你网站的一个软件。

对，而且它是开源的，不花钱！那个接口测试呢，这里大概了解一下就可以了，就是验证你的网店应用逻辑有没有问题的，比如你做打折活动的时候，结算的时候金额别出错，要不客户找你麻烦不是？

#### ***2.*JMeter的作用**

1.能够对HTTP和[FTP服务器](https://baike.sogou.com/lemma/ShowInnerLink.htm?lemmaId=449752&ss_c=ssc.citiao.link)进行压力和性能测试， 也可以对任何数据库进行同样的测试（通过JDBC）。

2.完全的可移植性和100% 纯java。

3.完全 Swing 和轻量组件支持（预编译的JAR使用 javax.swing.*)包。

4.完全[多线程](https://baike.sogou.com/lemma/ShowInnerLink.htm?lemmaId=452880&ss_c=ssc.citiao.link) 框架允许通过多个线程并发取样和 通过单独的线程组对不同的功能同时取样。

5.精心的GUI设计允许快速操作和更精确的计时。

6.缓存和离线分析/回放测试结果。

##  二、 Jmeter的下载和安装

安装Jmter之前的准备工作：

1:下载jdk：https://www.oracle.com/technetwork/java/javase/downloads/index.html

进入jdk的官网下载即可，我这里选择的是最新版jdk下载

![](C:\Users\86178\Desktop\JMeter\a1.png)


2:安装jdk

下载完成后，找到你下载的jdk,双击安装

![](C:\Users\86178\Desktop\JMeter\a2.png)

3：配置Java环境变量
3.1 右键点击计算机找到属性，点击打开属性

![](C:\Users\86178\Desktop\JMeter\a3.png)

3.2 双击打开高级系统设置

![](C:\Users\86178\Desktop\JMeter\a4.png)

3.3 点击高级里的环境变量打开环境变量的配置窗口

![](C:\Users\86178\Desktop\JMeter\a5.png)

![](C:\Users\86178\Desktop\JMeter\a6.png)

3.4 在高级-“系统变量（S）”窗口点击新建，弹出如下新建系统变量的窗口，
变量名输入：JAVA_HOME
变量值输入：D:\Program Files\Java\jdk-11.0.1 （jdk的安装位置）

![](C:\Users\86178\Desktop\JMeter\a7.png)

点击确定
3.5 点击系统变量中的 Path 变量，双击，
在变量值一栏的末尾输入：(英文状态下的分号)；%JAVA_HOME%\bin
点击确定，完成java环境变量的配置

![](C:\Users\86178\Desktop\JMeter\a8.png)

3.6 同时按Windows+R 打开cmd,输入java -version 查看java版本，显示版本信息，则环境变量配置成功

![](C:\Users\86178\Desktop\JMeter\a9.png)

下载与安装Jmeter

1：下载Jmeter：http://jmeter.apache.org/download_jmeter.cgi

进入Jmeter官网下载即可，我下载的是zip格式

![](C:\Users\86178\Desktop\JMeter\a10.png)

2:解压Jmeter

下载完成，将zip压缩包解压

![](C:\Users\86178\Desktop\JMeter\a11.png)

3.配置Jmeter的环境变量

方法同java的环境变量的配置

3.1 新建系统变量

变量名：JMETER_HOME
变量值：D:\Program Files\Jmeter\apache-jmeter-5.0 （Jmeter的压缩后的位置）

3.2 双击Path变量编辑

变量值末尾：(英文状态下的分号)；%JMETER_HOME%\bin

3.3 同时按 Windows+R 打开cmd 输入jmeter -v 查看版本，显示如下则证明环境变量已成功配置

![](C:\Users\86178\Desktop\JMeter\a12.png)

4.启动Jmeter
最后搜索Jmeter 点击 jmeter.bat，就可以启动jmeter啦！

![](C:\Users\86178\Desktop\JMeter\a13.png)

![](C:\Users\86178\Desktop\JMeter\a14.png)

## 三、 Jmeter的目录结构

1 /bin 目录（常用文件介绍）

 examples：目录下包含Jmeter使用实例

 ApacheJMeter.jar：JMeter源码包

 jmeter.bat：windows下启动文件

 jmeter.sh：Linux下启动文件

 jmeter.log：Jmeter运行日志文件

 jmeter.properties：Jmeter配置文件

 jmeter-server.bat：windows下启动负载生成器服务文件

 jmeter-server：Linux下启动负载生成器文件

2 /docs目录——Jmeter帮助文档

3 /extras目录——提供了对Ant的支持文件，可也用于持续集成

4 /lib目录——存放Jmeter依赖的jar包，同时安装插件也放于此目录

5 /licenses目录——软件许可文件，不用管

6 /printable_docs目录——Jmeter用户手册



------

## 四、JMeter的组成（大概）

![img](https:////upload-images.jianshu.io/upload_images/13610839-f63b0f3f4bbcb9a4.png?imageMogr2/auto-orient/strip|imageView2/2/w/668/format/webp)

**测试计划**：测试脚本根节点，每一个测试脚本都是一个测试计划，名称可以自己定义。

**线程组**：控制多线程并发，设置虚拟用户。

![img](https:////upload-images.jianshu.io/upload_images/13610839-a468c5ccda1b1fde.png?imageMogr2/auto-orient/strip|imageView2/2/w/1200/format/webp)



**断言**：预期结果和实际结果比对。

**定时器**：操作线程时候停顿多长时间之类。

**监听器**：重要组成部分，可以用来调试脚本，看看是否成功，还可以对资源进行监控。

**配置元件**： 重要组成部分，可以在里面获取cookie信息之类的配置信息。

**后置处理器**： 在并发完成后想要做什么。后一个请求用到前一个请求的结果，用后置处理器就可以拿到，放的一个变量里，下一次请求去用。

**前置处理器**：请求发生前做什么。

**逻辑控制器**：当一个条件满足时，需要去做的操作。

**Sampler**：放置请求。

## 五、 Jmeter测试组件（详细）

**1 .Threads (Users)：**

线程用户。虽然有三个添加线程组的选项，名字不一样， 创建之后，其界面是完全一样的。之前的版本只有一个线程组的名字。现在多一个setUp theread Group 与terDown Thread Group 

1）setup thread group  

一种特殊类型的ThreadGroup的，可用于执行预测试操作。这些线程的行为完全像一个正常的线程组元件。不同的是，这些类型的线程执行测试前进行定期线程组的执行。

2）teardown thread group

一种特殊类型的ThreadGroup的，可用于执行测试后动作。这些线程的行为完全像一个正常的线程组元件。不同的是，这些类型的线程执行测试结束后执行定期的线程组。

可能你还是不太理他们与普通的线程组有什么不同。 如果你用过junit，想必你不会对setup ，teardown这2个字眼陌生。 即时每用过，也没关系。 熟悉loadrunner的应该知道，loadrunner的脚本除了action里是真正的脚本核心内容，还有初始化“环境”的初始化脚本和测试完毕后对应的清除信息的脚本块。 那么这里 setup thread group 和 teardown thread group 就是分别指这两部分。 其实从本质上来看，他们并没有什么不同。

3）thread group(线程组)

这个就是我们通常添加运行的线程。通俗的讲一个线程组，可以看做一个虚拟用户组，线程组中的每个线程都可以理解为一个虚拟用户。线程组中包含的线程数量在测试执行过程中是不会发生改变的。测试里每个任务都要线程去处理，所有我们后来的任务必须在线程组下面创建。可以在“测试计划->添加->线程组”来建立它，然后在线程组面板里有几个输入栏：线程数、Ramp-Up Period(in seconds)、循环次数，其中Ramp-Up Period(in seconds)表示在这时间内创建完所有的线程。如有8个线程，Ramp-Up = 200秒，那么线程的启动时间间隔为200/8=25秒，这样的好处是：一开始不会对服务器有太大的负载。

**2.Test Fragment**

测试片段是在2.5版本之后新加的一个选项。测试片段元素是控制器上的一个种特殊的线程组，它在测试树上与线程组处于一个层级。它与线程组有所不同，因为它不被执行，除非它是一个模块控制器或者是被控制器所引用时才会被执行。

**3.控制器**：

JMeter有两种类型的控制器：取样器（sample）和逻辑控制器（Logic Controller），用这些元件来驱动处理一个测试。

1) Sample

取样器，是性能测试中向服务器发送请求，记录响应信息，记录响应时间的最小单元，JMeter 原生支持多种不同的sampler ，如 HTTP Request Sampler 、 FTP Request Sample 、TCP Request Sample 、JDBC Request Sampler 等，每一种不同类型的 sampler 可以根据设置的参数向服务器发出不同类型的请求。（在jmeter 的所有sampler 中，Java Request Sampler 和 Beanshell Request Sampler 是两种特殊的可定制的 Sampler ，后面会深入讨论。）

2）逻辑控制器

逻辑控制器，包括两类无件，一类是用于控制test plan 中 sampler 节点发送请求的逻辑顺序的控制器，常用的有 如果（If）控制器 、switch Controller 、Runtime Controller、循环控制器等。另一类是用来组织可控制 sampler 来节点的，如 事务控制器、吞吐量控制器。

 **4.配置元件**：

config element用于提供对静态数据配置的支持。和Sample组件一起工作，主要用来配置Sample如何来发起请求访问服务器，这个东西的主要特点是可以把一些Sample的共同配置放在一个元素里面方便管理，配置单元是有作用域的。作用域和树的那个关系一样越是上级节点的作用域越大，越是接近叶子节点的作用域就越小，可以复写上级作用域的配置。CSV Data Set config 可以将本地数据文件形成数据池（Data Pool），而对应于HTTP Request Sampler和 TCP Request Sampler等类型的配置元件则可以修改Sampler的默认数据。（例如，HTTP Cookie Manager 可以用于对 HTTP Request Sampler 的cookie 进行管理）

**5 定时器：**

这个主要是用来调节（线程组），控制线程每次运行测试逻辑（比如说：发出请求）的时间间隔。当然这个下面还有很多类型的定时器，他们主要功能就是调节时间间隔，但个个组件之间的策略有很大不同。Timer用于操作之间设置等待时间，等待时间是性能测试中常用的控制客户端QPS的手端。类似于LoadRunner里面的“思考时间”。JMeter 定义了Bean Shell Timer、Constant Throughput Timer、固定定时器等不同类型的Timer。

**6 前置处理器：**

用于在实际的请求发出之前对即将发出的请求进行特殊处理。例如，HTTP URL重写修复符则可以实现URL重写，当RUL中有sessionID 一类的session信息时，可以通过该处理器填充发出请求的实际的sessionID 。

**7 后置处理器**：

用于对Sampler 发出请求后得到的服务器响应进行处理。一般用来提取响应中的特定数据（类似LoadRunner测试工具中的关联概念）。例如，XPath Extractor 则可以用于提取响应数据中通过给定XPath 值获得的数据。

**8 断言：**

用于检查测试中得到的相应数据等是否符合预期，断言一般用来设置检查点，用以保证性能测试过程中的数据交互是否与预期一致。

**9 监听器：**

这个监听器可不是用来监听系统资源的元件。他是伴随着Jemeter测试的运行而从中抓取运行期间的数据的一个组件，对测试结果数据进行处理和可视化展示的一系列元件。经常使用的是聚合报告组件，从里面可以统计到测试的TPS，响应时间等关键测试数据。

 **JMeter 的主要测试组件总结如下：**

1 测试计划是使用 JMeter 进行测试的起点，它是其它 JMeter 测试元件的容器。

2 线程组代表一定数量的并发用户，它可以用来模拟并发用户发送请求。实际的请求内容在Sampler中定义，它被线程组包含。

3 monitor负责收集测试结果，同时也被告知了结果显示的方式。

4 逻辑控制器可以自定义JMeter发送请求的行为逻辑，它与Sampler结合使用可以模拟复杂的请求序列。

5 断言可以用来判断请求响应的结果是否如用户所期望的。它可以用来隔离问题域，即在确保功能正确的前提下执行压力测试。这个限制对于有效的测试是非常有用的。

6 配置元件维护Sampler需要的配置信息，并根据实际的需要会修改请求的内容。

7 前置处理器和后置处理器负责在生成请求之前和之后完成工作。前置处理器常常用来修改请求的设置，后置处理器则常常用来处理响应的数据。

8 定时器负责定义请求之间的延迟间隔。

## 六、性能测试流程

![](C:\Users\86178\Desktop\JMeter\c.png)

​       （1）业务学习：通过查看文档，手动操作系统来来了解系统性能；

　　（2）需求分析：分析系统非功能需求，圈定性能测试的范围，了解系统的性能指标；

　　（3）工作评估：工作量分解，评估工作量，计划资源投入；

　　（4）设计模型：圈定性能测试范围后，把业务模型映射成测试模型；

　　（5）计划编写：计划测试工作，在文档中明确列出测试范围、人力投入、持续时间、工作内容、风险评估、风险应对策略等；

　　（6）脚本开发：录制或者编写性能测试脚本；

　　（7）测试环境准备：性能测试环境准备包括服务器与负载机两部分，服务器是被测系统的运行平台，负载机是我们用来生产负载的机器，用来安装负载工具，运行测试脚本；

　　（8）测试数据准备：根据测试模型来准备被测系统的主数据与业务数据；

　　（9）测试执行

　　（10）缺陷管理：对性能测试过程中发现的缺陷进行管理；

　　（11）性能分析：对性能测试过程中暴露出来的问题进行分析，找出原因；

　　（12）性能调优：性能测试人员与开发人员一起来解决性能问题；

　　（13）测试报告：测试工作的重要交付文件，对测试结果进行报告，主要包括性能指标说明（tps、rt、cpu等）；

　　性能测试主要交付件：

```
1 测试计划
2 测试脚本
3 测试程序
4 测试报告或者阶段性测试报告
```

　　（14）评审：对性能报告中的内容进行评审，确认问题，评估上线风险。

### 以测度娘为例来描述构造一个简单的性能测试过程

#### 1、添加虚拟用户组

步骤：右键点击“测试计划” -> “添加” -> “线程(用户)” -> “线程组”

 “线程组”的意思：JMeter是由Java实现的，并且使用一个Java线程来模拟一个用户，因此线程组（Thread Group）就是指一组用户的意思，换句话说一个线程组就是一组虚拟用户（virtual   users），这些虚拟用户用来模拟访问被测系统。

![图片](https://mmbiz.qpic.cn/mmbiz_png/JfTPiahTHJhrVGsfiaH5hZor9IESn6Edaosa62DDD12B0qjiamGFGL10NGRQbp9RxefaYiaJ7LA3ia5iac8roaTV3l6A/640?wx_fmt=png&wxfrom=5&wx_lazy=1&wx_co=1)

新建线程组

线程组参数（线程属性）详解：

1）线程数：这里就是指虚拟用户数，默认的输入是“1”，则表明模拟一个虚拟用户访问被测系统，如果想模拟100个用户，则此处输入100。

2）Ramp-Up Period (in seconds): 虚拟用户增长时长。不明白别着急，xmeter君给你举个栗子：比如你测试的是一个考勤系统，那么实际用户登录使用考勤系统的时候并不是大家喊1、2、3 - 走起，然后一起登录。实际使用场景可能是9点钟上班，那么从8:30开始，考勤系统会陆陆续续有人开始登录，直到9:10左右，那么如果完全按照用户的使用场景，设计该测试的时候此处应输入40（分钟）* 60（秒）= 2400。

但是实际测试一般不会设置如此长的Ramp-Up时间，原因嘛，难道你做一次测试要先等上40分钟做登录操作？一般情况下，可以估计出登录频率最高的时间长度，比如此处可能从8:55到9:00登录的人最多，那这里设置成300秒，如果“线程数”输入为100，则意味着在5分钟内100用户登录完毕。

3）循环次数：该处设置一个虚拟用户做多少次的测试。默认为1，意味着一个虚拟用户做完一遍事情之后，该虚拟用户停止运行。如果选中“永远”，则意味着测试运行起来之后就根本停不下来了，除非你把它强制咔嚓。

![图片](https://mmbiz.qpic.cn/mmbiz_png/JfTPiahTHJhrVGsfiaH5hZor9IESn6Edao4DRAdjWiaBG2cczO1KGs6R8Yv6uNh2Hou4ic2FaAFI7dljXibhckhnLUw/640?wx_fmt=png&wxfrom=5&wx_lazy=1&wx_co=1)

线程组的设置

------

#### 2、添加被测页面

步骤：右键点击“线程组” -> “添加” -> “Sampler” -> “HTTP请求”

![图片](https://mmbiz.qpic.cn/mmbiz_png/JfTPiahTHJhrVGsfiaH5hZor9IESn6EdaoiaSNrsib32lsac2A2ZADxW0hwEGr3oAE9rNuKJZNWiaia2kiadRG5GZjwAQ/640?wx_fmt=png&wxfrom=5&wx_lazy=1&wx_co=1)

添加“HTTP请求”

接下来需要设置一下“HTTP请求” Sampler的属性，如下所示：

1）名称：输入“百度”，就是被测试网页的描述性文字

2）服务器名称或IP：被测服务器的网站名字，也可以是IP地址。剩下的属性可以按照被测系统的属性按需配置，现在都可以为空。

![图片](https://mmbiz.qpic.cn/mmbiz_png/JfTPiahTHJhrVGsfiaH5hZor9IESn6Edaoky01oQLXBAn63ogouC4Ow8FPesxLJv7eF1PWwk2eqcZyxbiaXVsevIA/640?wx_fmt=png&wxfrom=5&wx_lazy=1&wx_co=1)

设置HTTP请求的属性

现在的测试脚本已经可以运行了，先点击下面如图所示的第一步：点击保存脚本按钮；然后点击如图所示的第二步：点击运行测试按钮。

![图片](https://mmbiz.qpic.cn/mmbiz_png/JfTPiahTHJhrVGsfiaH5hZor9IESn6Edaob5XUKwtHtKPlutv5xASxQsaFQGl12CBPzWqs97ibKXXaUNmcOUibzlmw/640?wx_fmt=png&wxfrom=5&wx_lazy=1&wx_co=1)

------

保存与运行测试

等等，为什么我的测试跑完了没啥反应？嗯，其实测试已经跑完了，你可以去“选项” > “Log Viewer”看看运行的日志。如果你还是看不到日志，你可以点击下面所示的三角箭头展开或者收起日志视图。日志视图中可以看到“线程组 1-1”的启动和结束时间，表明测试已经跑完。

![图片](https://mmbiz.qpic.cn/mmbiz_png/JfTPiahTHJhrVGsfiaH5hZor9IESn6EdaooXzgqrqzoZYEagVLrtp8k1bmjf1dwyq1LFY04glRGVXMBurw07O3hQ/640?wx_fmt=png&wxfrom=5&wx_lazy=1&wx_co=1)

测试日志视图

那如果我的测试有问题了，怎么发现？JMeter提供了“监听器”让用户来观察测试结果。

#### **3、添加结果监听器**

如下图所示，右击“线程组” > “监听器” > “察看结果树”来查看性能测试过程中请求和响应信息。添加完毕后，保存测试脚本，再次运行。

运行测试完毕之后，点击“察看结果树” > “百度”，点击下图中3所示位置，你可以看到一些测试期间一些有用的信息，比如发送的请求的信息和响应数据等。接下来可以试着改一下“线程组”里的“线程数”为10，就是模拟10个用户访问。别改太大哦，否则小心度娘把你的IP地址给封了 。

![图片](https://mmbiz.qpic.cn/mmbiz_png/JfTPiahTHJhrVGsfiaH5hZor9IESn6EdaoaicJyy6F7TSlOANh9Zggm3OicJXNicky5zSJzbV7NGIJxJPZxMMfFVicVw/640?wx_fmt=png&wxfrom=5&wx_lazy=1&wx_co=1)

#### **补：Jmeter性能测试的一些相关概念**

(1) **压测**：通过逐步加压的方法，使得系统的某些资源达到饱和，甚至失效的状态，简单粗暴的解释就是什么条件能把系统压崩溃。Jmeter通过模拟大量的虚拟用户向服务器产生负载，使服务器的资源处于极限状态下长时间连续运行，以测试服务器在高负载情况下是否能够稳定工作。

(2) **并发**：在操作系统中，是指一个时间段中有几个程序都处于已启动运行到运行完毕之间，且这几个程序都是在同一个处理机上运行，但任一个时刻点上只有一个程序在处理机上运行。也就是说并发是指在一段时间内宏观上多个程序同时运行。（区别于并行，并行是指在同一时刻，有多条指令在多个处理器上同时执行。所以无论从微观还是从宏观来看，二者都是一起执行的。）JMeter是以线程的方式来进行模拟用户的并发访问的。

(3) **并行：**当系统有一个以上CPU时,则线程的操作有可能非并发。当一个CPU执行一个线程时，另一个CPU可以执行另一个线程，两个线程互不抢占CPU资源，可以同时进行，这种方式我们称之为并行(Parallel)

(3) **吞吐量(Throughput)**：是指系统在单位时间处理的请求数量。对于无并发的应用系统而言，吞吐量与响应时间成严格的反比关系，实际此时吞吐量就是响应时间的倒数。对于单用户的系统，响应时间可以很好地度量系统的性能，但对于并发系统，通常需要吞吐量作为性能指标。

(4) **QPS每秒查询率（Query Per Second）**每秒查询率QPS是对一个特定的查询服务器在规定的查询服务器在规定时间内所处理流量多少的衡量标准。（类似于TPS，只是应用于特定场景的吞吐量）

## 七 、用Jmeter做功能测试的优缺点

#### 优点：

1.不依赖于界面，如果服务正常启动，传递参数明确就可以添加测试用例，执行测试

2.测试脚本不需要编程，熟悉http请求，熟悉业务流程，就可以根据页面中input对象来编写测试用例。

3.测试脚本维护方便，可以将测试脚本复制，并且可以将某一部分单独保存。

4.可以跳过页面限制，向后台程序添加非法数据，这样可以测试后台程序的健壮性。

5.利用badboy录制测试脚本，可以快速的形成测试脚本

6.Jmeter断言可以验证代码中是否有需要得到的值。

7.使用参数化以及Jmeter提供的函数功能，可以快速完成测试数据的添加修改等

#### 缺点

1.使用Jmeter无法验证JS程序，也无法验证页面，所以需要手工去验证。

2.Jmeter的断言功能不是很强大

3.就算是jmeter脚本顺利执行，依旧无法确定程序是否正确执行，有时候需要进入程序查看，或者查看Jmeter的响应数据。

4.Jmeter脚本的维护需要保存为本地文件，而每个脚本文件只能保存一个测试用例，不利于脚本的维护。