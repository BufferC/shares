## Postman接口测试工具实战演练

### 文章目录

#### 一、前言

二、Postman工具介绍
三、Postman工具下载安装
四、Postman工具使用
五、Postman工具之接口测试
		5.1 接口测试的必要条件
		5.2 常见请求与传参
		5.3 接口演示
		5.4 接口collection集合讲解
		5.5 接口collection集合执行
		5.6 设置变量
			5.6.1 collection集合变量设置
			5.6.2 全局变量设置
			5.6.3 环境变量设置
			5.6.4 Tests设置变量
		5.7 接口Tests断言
		5.8 接口参数化
		5.9 接口随机数
		5.10 Monitor监视器

#### 一、前言

  本文章为Postman接口测试工具的实战使用，让大家认知Postman，熟悉并使用它，能够在真实的工作项目中加以运用，具体的使用方式会在文章中介绍，快来一起看看吧~

#### 二、[Postman](https://so.csdn.net/so/search?q=Postman&spm=1001.2101.3001.7020)工具介绍

工具简介： Postman是一款当今行业市场上非常流行且强大的http接口测试工具，常见的主流接口测试工具除了Postman还有Jmeter、Soapui等

  工具选择： 有很多接口测试工具，而选择Postman的首要原因是因为Postman更有针对性且界面整洁、清晰，易理解，对于新手而言具有一定的友好性
  安装方式： Postman一共有两种安装方式，分别是postman客户端安装以及浏览器的插件安装，其中postman客户端的安装最多，同时也被广泛使用，其次是浏览器插件安装，插件只支持谷歌浏览器，具有一定的局限性
  使用人员： 开发工程师、测试开发工程师、测试工程师等，开发主要用于测试自主编写的接口的功能正确性以及前后联调，测试主要为对接口功能等方面进行检验

#### 三、Postman工具下载安装

**第一步：** 进入postman官网地址下载，快速跳转→ [Postman官网](https://www.postman.com/)，打开后的界面如下所示：

![](C:\Users\86155\Desktop\ppt\1.png)

 **第二步：** 选择对应的系统下载，一共有三种，从左至右分别对应为：Windows系统、MacOS系统及Linux系统，本次举例以Windows系统进行举例，点击进入后的界面如下所示：

![](C:\Users\86155\Desktop\ppt\2.png)

![](C:\Users\86155\Desktop\ppt\3.png)

**第三步：** 根据系统位数选择对应的下载方式，通常为64位，点击后弹出浏览器内置下载，点击下载后即可

![](C:\Users\86155\Desktop\ppt\4.png)

![](C:\Users\86155\Desktop\ppt\5.png)

**第四步：** 运行安装程序后，等待程序安装完成即可，在界面的下方可以选择跳过创建或登录：

![](C:\Users\86155\Desktop\ppt\6.png)

![](C:\Users\86155\Desktop\ppt\7.png)

我们可以在官网查看历史版本： Resources and support →→ [Release notes](https://www.postman.com/downloads/release-notes/)，在这里也可以进行历史版本的预览和下载，同样支持Windows系统、MacOS系统及Linux系统的版本安装

![](C:\Users\86155\Desktop\ppt\8.png)

![](C:\Users\86155\Desktop\ppt\9.png)

# 四、Postman工具使用

  这里会提及到Postman工具的使用，会讲解重点部分、常用部分以及一些小技巧~

  打开Postman后，在最左上角点击File-New，在这里可以进行新建请求、集合、环境等

![](C:\Users\86155\Desktop\ppt\10.png)

同样在File中有个选项是Import，Import是导入功能，可以导入文件、文件夹、链接、文本信息等内容，可以导入一些Postman的脚本进行测试

![](C:\Users\86155\Desktop\ppt\11.png)

依旧是可爱的File中有个选项是New Runner Tab，它是一个集合运行界面，可以运行集合的请求

![](C:\Users\86155\Desktop\ppt\12.png)

 在界面上端有个“卫星”样的图标，API的抓取请求，我们可以使用它进行一些请求的抓取

![](C:\Users\86155\Desktop\ppt\13.png)

![](C:\Users\86155\Desktop\ppt\14.png)

“卫星”图标旁是设置按钮，点击后选择Settings进入设置界面，设置中可进行调节部分内容的开关、数据、使用快捷键等

![](C:\Users\86155\Desktop\ppt\15.png)

 在设置按钮旁是Sign in按钮，即登录按钮，可以点击后进行Postman的登录，登录后可以在A,B,C等不同设备上通过Postman内置的同步功能进行数据同步，更快捷、方便，也可以不进行登录，在本地进行测试工作

![](C:\Users\86155\Desktop\ppt\16.png)

左侧菜单栏History，在Postman执行请求后，会在History进行消息同步展示，每天进行统计

![](C:\Users\86155\Desktop\ppt\17.png)

左侧菜单栏Collections，它是一个项目的集合，如果有多个项目时，可以使用它进行管理，并把对应接口放置对应项目中，接口管理、文档参数化等都会通过它进行操作，非常实用~

![](C:\Users\86155\Desktop\ppt\18.png)

 新建HTTP请求后，会弹出右侧的布局，GET、POST等则是我们常用的请求方式，列表中也存在多种请求方式，请求方式旁是地址栏，输入完整的接口地址，配合Send进行发送，就可以模拟器客户端进行请求行为，而窗口中间位置有Params、Body等主要用于接口传参、会和上面的内容配合使用
![](C:\Users\86155\Desktop\ppt\19.png)

![](C:\Users\86155\Desktop\ppt\20.png)

Send旁有个倒立箭头，点击后是Send and Download，点击后会将请求下载到本地

![](C:\Users\86155\Desktop\ppt\21.png)

在send上方有个Save，将请求保存到哪个集合下

![](C:\Users\86155\Desktop\ppt\22.png)

在请求方式下的Authorization代表鉴权方式，鉴权方式在下方Type中可以进行各种鉴权方式的选取，具体的鉴权的选择参见需求文档

![](C:\Users\86155\Desktop\ppt\23.png)

Headers-请求头，也是需要看需求文档填写的，隔壁是Body，同样也是传参数，例如表单形式等，具体的传参内容也根据需求文档填写

![](C:\Users\86155\Desktop\ppt\24.png)

![](C:\Users\86155\Desktop\ppt\25.png)

Pre-request Script，请求前置脚本，主要用于处理请求前脚本，例如发送的内容需要加密等

![](C:\Users\86155\Desktop\ppt\26.png)

Tests，请求后置脚本，又称为断言，右侧工具栏有很多json脚本，对新手非常友好

![](C:\Users\86155\Desktop\ppt\27.png)

  Console-控制台，在这里可以查看到请求接口相关的日志信息

![](C:\Users\86155\Desktop\ppt\28.png)

#### 五、Postman工具之接口测试

##### 5.1 接口测试的必要条件

  要先想进行接口测试，就必须掌握以下几个内容：
  （1）请求地址
  （2）请求协议
  （3）请求方式
  （4）请求头
  （5）请求参数

ps：公司没有接口文档也并非完全没办法测试接口，仍然可以通过抓包工具获取，但要想测试接口，还是需要上述的必要条件
  

##### 5.2 常见请求与传参

  常见请求方式主要为GET请求与POST请求，常见的传参格式为请求体提交与表单提交

##### 5.3 接口演示

![](C:\Users\86155\Desktop\ppt\29.png)

![](C:\Users\86155\Desktop\ppt\30.png)

##### 5.4 接口collection集合讲解

  collection集合在接口测试中显得尤为重要，最重要的功能就是集合请求，将个别请求进行分组处理，这些请求可以进一步组织成文件夹，创建集合的好处主要有以下几点：
  统一化： 将对应的请求集合在一个文件夹下，以便统一化的执行、调用、修改等
  文档 ： 增删改查文件夹的内容，可以备注
  测试套件： 将测试脚本附加到请求并构建集成测试套件
  条件工作流程： 脚本可以在API请求之间传递数据，并构建反馈实际用例API的工作流。
 ![](C:\Users\86155\Desktop\ppt\31.png)

我们可以通过右键新创建的合集进行名称修改，**右键集合名 → Rename**：

![](C:\Users\86155\Desktop\ppt\32.png)

右键集合后我们可以新建下一个层级，点击Add Folder

![](C:\Users\86155\Desktop\ppt\33.png)

![](C:\Users\86155\Desktop\ppt\34f.png)

我们可以在文件夹下新建一个请求，这样这个请求就隶属于这个合集下对应文件夹，右键文件夹或总合集，点击Add Request新建请求

![](C:\Users\86155\Desktop\ppt\35.png)

![](C:\Users\86155\Desktop\ppt\36.png)

可以直接在下图红框处修改名称，也可以直接右键重命名，方式与集合一致

![](C:\Users\86155\Desktop\ppt\37.png)

通常而言接口地址为固定地址，修改的只需要是模块名称，但每次新建又会很麻烦，可以右击请求title，并选择Duplicate Tab 来复制一个请求，在复制的基础上进行修改,，需要提前将复制出的接口保存到文件夹下（复制是完全复制前一个请求接口所填写的信息）

![](C:\Users\86155\Desktop\ppt\38.png)

复制完成后能看到名称也是一致的，并会有橘色提醒，即代表着未进行保存，快捷键ctrl+s可进行保存，也可以通过点击Save进行保存

![](C:\Users\86155\Desktop\ppt\39.png)

##### 5.5 接口collection集合执行

  collection集合执行顾名思义是将集合下的所有请求统一执行，点击集合右侧的三个点，再次选择Run collection：

![](C:\Users\86155\Desktop\ppt\40.png)

 打开后会展示如下界面：（图中只有一个请求，举例子，目的是让大家清楚工具使用，真实测试时有多个请求即可）

![](C:\Users\86155\Desktop\ppt\41.png)

![](C:\Users\86155\Desktop\ppt\42.png)

##### 5.6 设置变量

###### 5.6.1 collection集合变量设置

  接口collection变量可以理解成集合专用变量，则在集合下可使用的全局变量，在对应的请求中调用对应变量，则可以使用全集合专用变量，当collection集合变量修改时，对应调用请求的变量也会一同修改，选择3个点，选择Edit打开界面：

  ps：变量则是让接口与接口之间存在关联性的联系，例如注册某网站，那么注册与登录必定是使用同一个用户名进行登录，那么在用户名这里，两个变量则是相同变量，此时我们就可以使用collection集合变量进行设置并调用

![](C:\Users\86155\Desktop\ppt\43.png)

选择Variables后进行一个变量的设置，设置完成后进入单个请求中进行调用

![](C:\Users\86155\Desktop\ppt\44.png)

将原变量替换掉，使用两个花括号进行变量的调用，这里格外需要注意的是集合修改后务必需要保存，保存后才能够调用到变量，否则会默认当成保存前的数据

![](C:\Users\86155\Desktop\ppt\45.png)

###### 5.6.2 全局变量设置

  全局变量可针对集合、某个接口进行的变量设置，在任何情况下不受到特定环境因素的影响下，也同样可以使用全局变量，全局变量针对所有集合、接口生效，点击任意一个请求，在界面最右侧点击眼睛的图标：

![](C:\Users\86155\Desktop\ppt\46.png)

点击后会展开一个下拉界面，Globals则是全局变量，点击该界面右侧的Add进行全局变量的设置：

![](C:\Users\86155\Desktop\ppt\47.png)

点击Add后会打开Globals窗口，进行变量设置（**特别需要了解的是集合中的变量名称不能与全局变量名称一致，要时刻注意，设置完成后在传参处调用即可，调用方式同collection集合调用**）：

![](C:\Users\86155\Desktop\ppt\48.png)

5.6.3 环境变量设置
  环境变量是与集合类似，环境变量只能在特定的环境下使用，例如测试环境、正式环境等，在测试环境中的变量则不能用于正式环境，环境中的变量是独立的，查找的方式与全局变量方式一致，点击眼睛图标，找到环境变量后，点击Add，进入到界面后可以设置一个新的变量，最后进行调用，调用同collection集合方式：

![](C:\Users\86155\Desktop\ppt\50.png)

 这里设置了2个环境变量，分别是测试环境与正式环境，正式环境与测试环境的变量是独立的，使用方式仍然与集合变量的方式一样，使用两个花括号并填写变量名即可（下面的URL是演示使用，大家用自己的接口地址即可）

![](C:\Users\86155\Desktop\ppt\51.png)

在右侧这里默认是No Environment，没有环境变量，我们自己设置好环境变量后，可以自主的选择环境，例如正式环境，而后修改对应的内容为环境变量即可

![](C:\Users\86155\Desktop\ppt\52.png)

###### 5.6.4 Tests设置变量

  通过Tests，将接口的返回结果取出后设置为对应的变量，后续的相关接口就可以通过变量值进行接口关联，图中的例子是取token值，取出后选择好对应的环境变量并点击send，在小“眼睛”处可以查看到对应的token信息：

![](C:\Users\86155\Desktop\ppt\53.png)

![](C:\Users\86155\Desktop\ppt\54.png)

##### 5.7 接口Tests断言

  Tests属于Postman内置的强大断言功能，可以通过内置的脚本直接进行调用，不需要过多的学习JavaScript的内容，非常方便且对新手友好，常见Tests响应断言的几种方式：
1、Response body：Contains string （校验返回结果中是否包含某个字符串）
2、Response body：Is equal to a string （校验返回结果是否等于该字符串）
3、Response body：JSON value check （校验返回结果中某个字段值是否等于某个值）
4、Response header：Content-type header check（检查响应头是否包含某个值）
5、Response time is less than 200ms （检查响应时间是否少于200ms）
6、Status code:Code is 200（检查状态码是否为200）

  我们也可以选择Tests后在右侧看到相关的说明，点击后会直接在Tests中生成内容，具体的用法，大家可以百度自行查询，这里有很多相关的Tests断言，不逐一讲解：

![](C:\Users\86155\Desktop\ppt\55.png)

![](C:\Users\86155\Desktop\ppt\56.png)

##### 5.8 接口参数化

  在接口测试时，部分请求参数都是重复的，那么我们就可以使用接口参数化，接口参数化可以很大程度上减少重复工作时间，常用的接口参数化有三种方式：csv、txt、json文档参数化（本次以txt进行举例）：

  1、举例前需要一个必要的前置条件，接口参数化必须在集合中进行操作，故此我们需要先创建个集合并把相关接口放置集合中（上面有提到如何创建集合以及把接口放置对应集合下，这里省略图片~）
  2、在本地可以创建个对应的txt文档，参数间隔使用英文逗号：

![](C:\Users\86155\Desktop\ppt\57.png)

3、关闭txt文档上传txt，点击按钮后，选择对应的文本文档并点击打开按钮上传：

![](C:\Users\86155\Desktop\ppt\58.png)

![](C:\Users\86155\Desktop\ppt\59.png)

4、上传文档后选择txt文本格式，点击右侧的Preview可以进行预览，一切安排好后，点击Run即可（效果类似上面的集合执行结果，这里不在放图说明了，小伙伴们快自己尝试一下吧~）：

![](C:\Users\86155\Desktop\ppt\60.png)

![](C:\Users\86155\Desktop\ppt\61.png)

##### 5.9 接口随机数

  在日常的接口测试、自动化接口测试时会出现大量的重复参数，即对同一个不允许重复的参数进行传参时，可以确保参数内容不重复，最典型的例子就是注册，注册的手机号在第一次注册时为注册成功，如果第二次使用同一个手机号，势必会提示手机号已注册，在这类场景下，我们需要使用接口随机数以确保参数不重复，随机数主要有以下3个方式：

  {{$guid}}：添加一个v4风格GUID

![](C:\Users\86155\Desktop\ppt\62.png)

 {{$timestamp}}：将当前的时间戳，精确到秒、毫秒时，后面增加000即可（执行结果也是个随机数，这里就不放图撩~）

![](C:\Users\86155\Desktop\ppt\63.png)

{{$randomInt}}：随机整数，添加0到1000之间的随机整数

![](C:\Users\86155\Desktop\ppt\64.png)

效果大同小异，输出的结果例如：“ename”：“CSDNmengxiaotian156”

##### 5.10 Monitor监视器

  Monitor监视器是Postman内置的监控模块，作用类似于Jinkens，可以设置按照分钟、小时、周等单位进行监控且在接口出现错误的情况下可以设置邮件通知（最多支持5个），非常重要且强大的功能（用过的都说好，手动滑稽）

  Monitor也必须要依赖集合运行，所以小伙伴们在测试的时候还需要有个集合，日常集合3个点，选择Monitor，然后：

![](C:\Users\86155\Desktop\ppt\65.png)

![](C:\Users\86155\Desktop\ppt\66.png)

![](C:\Users\86155\Desktop\ppt\67.png)