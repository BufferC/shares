​		



# emelent UI



官方文档：[组件 | Element](https://element.eleme.io/#/zh-CN/component/installation)

​	Element UI 是一套采用 Vue 2.0 作为基础框架实现的组件库，一套为开发者、设计师和产品经理准备的基于 Vue 2.0 的组件库，提供了配套设计资源，帮助网站快速成型。

​	1.创建一个名为emelent UI的工程 

2.他是基于Vue-cli脚手架下，需要一些基础。

3、安装环境。 需要安装Node.js环境、Vue.js脚手架等工具即可。

```vue
首先安装Vue.js脚手架，命令如下：
	vue create cli

切换到安装好的cli目录下，安装Element UI,命令如下：
	npm i element-ui -S

在脚手架main.js引入Elenent Ui,具体如下：
	import Elementimport ElementUI from 'element-ui'
	import 'element-ui/lib/theme-chalk/index.css'

Vue.use(ElementUI)
```

这样就配置好了element UI了

 因为时间有限，我就简单讲一下常用的组件



## Layout布局

​		**通过基础的 24 分栏，可以迅速简便地创建布局。**

​	1.基本感念：一行通过分割24栅格栏进行布局，如果要占满一行如下：



```vue
	<!--el-row表示一行-->
	<!--el-col表示一列-->

	<el-row>
        <el-col:span="24">
        24
        </el-col:span>
</el-row>

```

2.如果设置18个栅格栏位，那么会留出6个位置是空白区域；

```vue
<el-row>
	<el-col:span="18">
    18
    </el-col:span>
</el-row>

```

3.如果想要时列占满24个格栅栏位，那么每列占6个栅格栏位：

```vue
<el-row>
   <el-row>
                <el-col :span="6">6</el-col>
                <el-col :span="6">6</el-col>
                <el-col :span="6">6</el-col>
                <el-col :span="6">6</el-col>
            </el-row>
</el-row>
```

4.手册里el-col子元素还有一层div，他可以被：gutter设置为间隔：

```vue
     <el-row :gutter="10">
                <el-col :span="6">
                    <dav style="background-color: sienna">6</dav>
                </el-col>
                <el-col :span="6">6</el-col>
                <el-col :span="6">6</el-col>
                <el-col :span="6">6</el-col>
            </el-row>
```

5.使用type=”flex“来设置栏位的对齐方式，可以通过justify来设置方向：

```vue
<el-row type="flex" justify="center">
                <el-col :span="4">4</el-col>
                <el-col :span="4">4</el-col>
                <el-col :span="4">4</el-col>
                <el-col :span="6">6</el-col>
            </el-row>
```

6.通过使用：offset=n来设置栏位之间的偏移量；

```vue
   <el-row type="flex" justify="center">
                <el-col :span="4" :offset="1">4</el-col>
                <el-col :span="4">4</el-col>
                <el-col :span="4">4</el-col>
                <el-col :span="6">6</el-col>
            </el-row>
```

## Container布局容器

**用于布局的容器组件，方便快速搭建页面的基本结构**：

`<el-container>`：外层容器。当子元素中包含 `<el-header>` 或 `<el-footer>` 时，全部子元素会垂直上下排列，否则会水平左右排列。

`<el-header>`：顶栏容器。

`<el-aside>`：侧边栏容器。

`<el-main>`：主要区域容器。

`<el-footer>`：底栏容器。



```vue
<template>
    <div class="Contaioner">
        <el-container>
            <el-header>header</el-header>
            <el-container>
 <el-aside>aside</el-aside>
            <el-main>main</el-main>
            </el-container>
           
            <el-footer>footer</el-footer>
        </el-container>
    </div>
</template>

<script>
export default {
    name:"Container"
}

</script>
<style scoped>
    .el-container{
        background-color: aqua;
        color: white;
    }
    .el-header{
        background-color: rgb(31, 182, 68);
    }
    .el-footer{
        background-color: rgb(24, 90, 188);
    }
    .el-aside{
         background-color: rgb(188, 24, 24);
         max-width: 200px;
         min-height: 350px;
    }
    .el-main{
         background-color: rgb(158, 197, 17);
    }
</style>
```



## Icon图标、Link文字

### Icon 图标

提供了一套常用的图标集合。

**使用方法**

直接通过设置类名为 `el-icon-iconName` 来使用即可



![image-20220415132637646](C:\Users\LENOVO\AppData\Roaming\Typora\typora-user-images\image-20220415132637646.png)



![image-20220415132758426](C:\Users\LENOVO\AppData\Roaming\Typora\typora-user-images\image-20220415132758426.png)

这只是一小部分，官方的有很多。

```vue
<i class="el-icon-edit"></i>
```

### Link文字

Attributes属性

| 参数      | 说明           | 类型    | 可选值                                      | 默认值  |
| :-------- | :------------- | :------ | :------------------------------------------ | :------ |
| type      | 类型           | string  | primary / success / warning / danger / info | default |
| underline | 是否下划线     | boolean | —                                           | true    |
| disabled  | 是否禁用状态   | boolean | —                                           | false   |
| href      | 原生 href 属性 | string  | —                                           | -       |
| icon      | 图标类名       | string  | —                                           | -       |

```vue
 <el-link type="primary">主要链接</el-link> |
    <el-link type="success">成功链接</el-link> |
    <el-link type="danger">警告链接</el-link> |
    <el-link type="warning">危险链接</el-link> |
    <el-link type="info">信息链接</el-link> |
```



## 按钮



![image-20220415091016425](C:\Users\LENOVO\AppData\Roaming\Typora\typora-user-images\image-20220415091016425.png)

1.Button按钮和Link文字一样，有固定的几个样式；

```vue
<el-row>
        <el-button type="promary">主要按钮</el-button>
        <el-button type="danger">危险按钮</el-button>
        <el-button type="warning">警告按钮</el-button>
        <el-button type="success">成功按钮</el-button>
        <el-button type="info">信息按钮</el-button>
    </el-row>
```

2.使用plain属性，可以实现镂空效果；使用disablad属性，可以实现禁用；round实现椰圆，circle实现圆；

```vue
   <el-row>
        <el-button type="promary" circle class="el-icon-s-platform"></el-button>
        <el-button type="danger" plain>危险按钮</el-button>
        <el-button type="warning" disabled>警告按钮</el-button>
        <el-button type="success" round>成功按钮</el-button>
        <el-button type="info" disabled> 信息按钮</el-button>
    </el-row>
```

3.使用type="text"可以将button转换为文本按钮

```vue
<el-button type="text" >文本按钮</el-button>
```

4.使用<el-button-group>可以将多个按钮设置成组合按钮；

```vue
<el-button-group>
                <el-button >上一页</el-button>
                <el-button >下一页</el-button>
        </el-button-group>
```

5.使用：loading="true"实现加载中的效果；

```vue
<el-button :loading="true">加载中</el-button>
```

6.使用size="small"等属性，实现三种大小

```vue
 <el-button size="small">小按钮</el-button>
```

## Radio单选框、Checkbox多选框

### Radio单选框

在一组备选项中进行单选

```vue
<template>
  <el-radio v-model="radio" label="1">备选项</el-radio>
  <el-radio v-model="radio" label="2">备选项</el-radio>
</template>

<script>
  export default {
    data () {
      return {
        radio: '1'
      };
    }
  }
```

这只是一小部分，官方是讲的还是比较详细的，很好理解 。

