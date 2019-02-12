# Vue.js2开发

## 课程目标

**&emsp;&emsp;学会从简单到复杂企业级应用的VueJS程序编写方法**

**&emsp;&emsp;能在单页和多页应用中自如使用VueJS**

**&emsp;&emsp;真正理解VueJS的背后原理，并在真实项目中应用它们**

## 学习条件

**&emsp;&emsp;学习本课程需要对HTML、CSS、JS有基本了解，只要你想学习VueJS前端框架，认真学习本课程,相信你一定能够学会的。**



## 第1章 从这里开始

### 1.1 课程介绍

#### Vue是什么?

&emsp;&emsp;Vue (读音 /vjuː/，类似于 view) 是一套用于构建用户界面的渐进式框架。与其它大型框架不同的是，Vue 被设计为可以自底向上逐层应用。Vue 的核心库只关注视图层，不仅易于上手，还便于与第三方库或既有项目整合。另一方面，当与现代化的工具链以及各种支持类库结合使用时，Vue 也完全能够为复杂的单页应用提供驱动。

#### Vue的应用(Vue能做什么)?

**&emsp;Vue能应用于各个方面,比如:**

&emsp;&emsp;1. 在现有项目添加JavaScript驱动的小控件

&emsp;&emsp;2. 还能开发中型应用,你能用JavaScript控制整个页面,对部分页面重新渲染,页面响应非常迅速,正如课程中的另一个例子一样

&emsp;&emsp;3. 此外,Vue还能开发大型企业级应用,单页面应用,即你的整个应用,在用户感觉中是多页面,看起来是这个样子的,Vue驱动整个页面,局部渲染部分页面,让用户以为是切换了不同页面,但其实是个单页面,JavaScript在起作用罢了.

#### 为什么是JavaScript?

因为它运行于浏览器,而无需借助任何服务器(Server),重新渲染部分页面也无需等待,因此页面响应非常迅速,用户感受很好,也提供了非常友好的用户体验.


#### 为什么要使用这个框架?

##### &emsp;接下来我们聊聊为什么要选择Vue这个框架,而不是像Angular/React等类似框架?

&emsp;&emsp;首先,从体积来说,Vue非常精悍小巧,核心代码的压缩包版本只有16KB,16KB并不包括额外引入的路由插件,即使算上它,整个框架还是非常小,是个功能聚焦,直击要害的框架,但因为体积小它不仅加载快,运行时也非常快,某些基准测试显示,Vue的运行时甚至超过Angular/React,当然不同应用的运行时会有所差异,但可以说它真的很快,这也进一步增强了Vue响应迅速的体验.


#### 它会如何帮助你?

&emsp;&emsp;你可能会觉得如此小而快的框架,能提供的功能肯定不多,那你错了,Vue提供了丰富的功能,后面我会一一给大家讲解所用的功能特性,你会学到其中实现的原理,如何使用以及何时使用,以及框架背后的架构思维,你会发现它的扩展性很强,比如引入路由插件,Vue框架对这些扩展支持的很好,再次给大家说一下,后面我会一一给大家讲解所有的功能特性,相信大家现在对Vue有了大体印象.

&emsp;&emsp;接下来,让我们正式开始的学习Vue吧,用Vue来创建第一个应用,同时也看一下如何安装Vue.


### 1.2 实现第一个VueJS应用

- 创建第一个Vue应用其实非常简单,先打开官网首页 ([https://vuejs.org/](https://vuejs.org/ "vue"))
- 看到这个起步(GET STARTED)按钮,点击进入Vue官方文档,官方文档永远值得一看
- 现在点击安装(Installation)

#### Vue的安装方式?

- 本地安装
	- 可以直接下载Vue,后面我们会演示
	- 或者像我现在一样,直接从CDN获取,引入到我们的服务器中,点击unpkg,然后直接复制url,项目中引入该链接,就能获取到Vue
- 命令安装
	- 后面课程,我们会使用复杂的(也就是命令安装),通过webpack配置来打包所有文件

#### 在JS Fiddle上操作 或者 本地上操作

在这里我们使用JS Fiddle,它是个网页在线编辑器,只能开发非常简单的HTML CSS JavaScript项目,左上角是HTML编辑区域,在这里引入脚本,现在让我们输入script,键入tab,就会自动补齐成<script>标签,然后在<script>标签里面添加src属性,直接插入刚才复制的链接:

	<script src="https://unpkg.com/vue@2.6.2/dist/vue.js"></script>

可以就保持这样,也可以删除版本信息:

	<script src="https://unpkg.com/vue/dist/vue.js"></script>

如果删除的话,从而自动获取最新版本,这样就成功的引入了vue,现在可以使用vue的所有特性.

#### 创建第一个Vue应用

现在我想添加一个内容为Hello World的段落:

	<script src="https://unpkg.com/vue/dist/vue.js"></script>

	<p>Hello World</p>

这么"打招呼"看起来很无趣,没有任何JavaScript参与.

我们要用Vue来输出Hello World:

HTML:
	
	<script src="https://unpkg.com/vue/dist/vue.js"></script>

	<p></p>

为此,来到左下角的JavaScript编辑区域,有了上面的Vue引入,现在可以使用Vue中的一个核心对象,`Vue对象`,用new关键词和Vue来创建一个实例,这个实例就是个Vue实例,这样创建的Vue实例,其核心在于能让你处处使用Vue特性,创建的Vue实例有个最重要的功能,控制自己的模板即HTML中的代码,这些代码会最终渲染到页面上,要让该实例实现该功能,需传参至构造函数,参数是个对象,其中有个非常重要的属性,`el`属性,这是Vue的保留属性,Vue会识别,`el`属性接受一个字符串,该字符串定义了Vue实例能控制的HTML片段.

JS:

	new Vue({
		el : ""
	})

这里的"控制"是指可以用Vue实例改变HTML内容,等下我们就会看到.

这里我想控制`<p>`标签这部分,用`<div>`标签把它包起来,输入`div#app`,在按`tab`键,会自动补齐成id为app的`<div>`标签,把段落移入`<div>`标签,

HTML:

	<script src="https://unpkg.com/vue/dist/vue.js"></script>

	<div id="app">
		<p></p>
	</div>	

现在可以通过app的id属性选择这个`<div>`元素,`el`的属性值写法类似CSS选择器,输入#app,就选择了样式id为app的元素,如果输入的是 .app,那就选择了样式类为app的第一个元素,现在我们就控制了这个div元素,也就是这个Vue实例的模板

JS:

	new Vue({
		el : "#app"
	});
	

要想有所输出,就需要数据,Vue有个专门的属性,`data`属性,也是个保留属性,它不是字符串,而是个对象,势力中需要的所有数据都存入其中:

JS:

	new Vue({
		el : "#app",
		data : {

		}
	});

比如说,我们需要一个title属性,属性值我们随便写,比如Hello World

JS:

	new Vue({
		el : "#app",
		data : {
			title : "Hello World"
		}
	})

我想在模板中输出这个,之前我直接写死在HTML中,现在这个模板能被Vue控制了,只要在模板中简单添加特殊的Vue语法,双大括号,开始...,结尾...

HTML:

	<script src="https://unpkg.com/vue/dist/vue.js"></script>

	<div id="app">
		<p>{{ title }}</p>
	</div>
	
在内部添加title即可,Vue会自动在data对象中查找,刚说过,data是保留属性,在data对象中找到title属性,然后输出到HTML中,按住Ctrl + Enter运行查看页面结果,就可以看到右边出现Hello World,这是因为Vue控制了这段HTML模板,从而把内容title输出到了页面,

### 1.3 扩展这个VueJS应用

### 1.4 课程结构

### 1.5 课程说明

### 1.6 本地配置VueJS开发环境

## 第2章 通过VueJS来与DOM交互

### 2.1 本章介绍

### 2.2 理解VueJS模板

### 2.3 VueJS的模板语法和实例

### 2.4 访问Vue实例里的数据

### 2.5 属性绑定

### 2.6 理解和使用指令

### 2.7 用v-once禁止二次渲染

### 2.8 如何输出基础的HTML

### 2.9 作业1问题: 输出数据到模板

### 2.10 作业1答案: 输出数据到模板

### 2.11 监听事件

### 2.12 从事件对象里获取事件数据

### 2.13 传递你自己的事件参数

### 2.14 用事件修饰符来修改事件

### 2.15 监听键盘事件

### 2.16 作业2问题: 事件

### 2.17 作业2答案: 事件

### 2.18 在模板中编写JS代码

### 2.19 使用双向绑定

### 2.20 用计算属性来响应改变

### 2.21 计算属性的替代: 观察改变

### 2.22 用缩写来节省事件

### 2.23 作业3问题: 响应式属性

### 2.24 作业3答案: 响应式属性

### 2.25 CSS类动态样式-基础

### 2.26 CSS动态类样式-使用对象

### 2.27 CSS动态类样式-使用命名

### 2.28 动态设置样式(不使用CSS类)

### 2.29 用数组语法设置元素样式

### 2.30 作业4问题: 样式设置

### 2.31 作业4答案: 样式设置

### 2.32 本章总结

## 第3章 使用条件和列表渲染

### 3.1 本章介绍

### 3.2 用v-if来做条件渲染

### 3.3 替代v-if语法

### 3.4 不要用v-show解绑

### 3.5 用v-for来渲染列表

### 3.6 获取当前的下标

### 3.7 替代v-for语法

### 3.9 循环一组对象

### 3.10 循环一组数字列表

### 3.11 用v-for来跟踪对象

### 3.12 作业5问题: 条件和列表

### 3.13 作业5答案: 条件和列表

### 3.14 本章总结

## 第4章 第一个实训项目-怪物猎人

### 4.1 介绍和挑战

### 4.2 搭建工程

### 4.3 创建Vue实例以及给血槽加样式

### 4.4 根据条件来显示玩家操作

### 4.5 实现"开始游戏"方法

### 4.6 实现"攻击"方法

### 4.7 重构事件到! 更好的代码

### 4.8 实现"特殊攻击"方法

### 4.9 实现"疗愈"方法

### 4.10 完成操作按钮

### 4.11 创建操作日志

### 4.12 打印日志 (v-for)

### 4.13 完成日志功能

### 4.14 根据条件来调整日志样式

### 4.15 总结

## 第5章 理解VueJS实例

### 5.1 本章简介

### 5.2 关于vue实例的一些基础

### 5.3 使用多个Vue实例

### 5.4 从外部访问Vue实例

### 5.5 Vue是如何管理数据和方法

### 5.6 深入分析$el和$data

### 5.7 在你的模板中使用$refs

### 5.8 去哪里可以学到更多的Vue API

### 5.9 挂载一个模板

### 5.10 使用组件

### 5.11 一些模板的限制

### 5.12 Vue是怎样更新DOM的

### 5.13 Vue实例的生命周期

### 5.15 Vue实例生命周期实战

### 5.16 本章总结

## 第6章 使用WebPack和Vue命令进入真实的开发

### 6.1 本章介绍

### 6.2 为什么我们要有开发服务器

### 6.3 "开发流程"指的是什么?

### 6.4 使用Vue命令行来创建项目

### 6.5 Vue命令行安装以及创建一个新项目

### 6.6 WebPack模板目录结构概述

### 6.7 理解".vue"后缀的文件

### 6.8 理解vue文件中的对象

### 6.9 如何构建一个真正的可发布应用

### 6.10 本章总结

## 第7章 组件介绍

### 7.1 本章介绍

### 7.2 组件介绍

### 7.3 使用数据方法来向组件中保存数据

### 7.4 将组件注册到局部或全局

### 7.5 在App.vue文件中的根组件

### 7.6 创建一个组件

### 7.7 使用组件

### 7.8 作业6问题: 组件练习

### 7.9 作业6答案: 组件练习

### 7.10 采用更好的目录结构

### 7.11 怎样给组件标签命名 (选择器)

### 7.12 组件样式作用域

### 7.13 本章总结

## 第8章 组件之间的通信

### 8.1 本章介绍

### 8.2 通信存在的问题

### 8.3 使用Props来让父子组件通信

### 8.4 为Props命名

### 8.5 在子组件中使用Props

### 8.6 验证Props

### 8.7 使用自定义事件来让父子组件通信

### 8.8 理解单向数据流

### 8.9 使用回调函数来通信

### 8.10 在同级组件间通信

### 8.11 在一个事件总线中集中实现代码

### 8.12 作业7问题: 组件间通信

### 8.13 作业7答案: 组件间通信

### 8.14 本章总结

## 第9章 高级组件用法

### 9.1 本章介绍

### 9.2 创建本章工程

### 9.3 非最优的传递内容方案

### 9.4 使用插槽来传递内容

### 9.5 插槽内容是如何编译和风格化的

### 9.6 使用多个插槽 (命名插槽)

### 9.7 默认插槽和插槽的默认设置

### 9.8 关于插槽的总结

### 9.9 将多组件转换为动态组件

### 9.10 理解动态组件行为

### 9.11 让动态组件保活

### 9.12 动态组件声明周期钩子

### 9.13 作业8描述: 插槽和动态组件

### 9.14 作业8答案: 插槽和动态组件

### 9.15 本章总结

## 第10章 第二个实训项目-漂亮的句子

### 10.1 本章介绍

### 10.2 创建工程

### 10.3 应用初始化

### 10.4 创建Application组件

### 10.5 使用Props和插槽传递数据

### 10.6 允许用户使用NewQuote组件创建句子

### 10.7 使用自定义事件来添加引用

### 10.8 添加一个消息框

### 10.9 允许删除句子

### 10.10 通过进度条来控制句子

### 10.11 结语和状态管理

## 第11章 用表单处理用户输入

### 11.1 本章介绍

### 11.2 绑定表单input标签

### 11.3 分组数据和预填充输入

### 11.4 使用输入修饰符来修改用户输入

### 11.5 绑定textarea标签和保存换行符

### 11.6 使用复选框并将数据保存在数组中

### 11.7 使用单选按钮

### 11.8 使用select和option标签处理下拉菜单

### 11.9 v-model有什么用和如何创建自定义控件

### 11.10 创建自定义控件 (输入)

### 11.11 提交表单

### 11.12 作业9描述: 表单练习

### 11.13 作业9解答: 表单练习

### 11.14 本章总结

## 第12章 使用和创建指令

### 12.1 本章介绍

### 12.2 理解什么是指令

### 12.3 指令的工作原理-钩子函数

### 12.4 创建一个简单的指令

### 12.5 给自定义指令传值

### 12.6 给自定义指令传参

### 12.7 用修饰符来修改自定义指令

### 12.8 自定义指令总结

### 12.9 本地注册指令

### 12.10 同时使用多个修饰符

### 12.11 给指令传递多个复杂值

### 12.12 作业10指令 : 问题

### 12.13 作业10答案 : 指令

### 12.14 本章总结

## 第13章 使用过滤器和混入来优化程序

### 13.1 本章介绍

### 13.2 创建本地过滤器

### 13.3 全局过滤器以及如何串联多个多虑器

### 13.4 替代过滤器 : 计算属性

### 13.5 理解什么是混入 (Mixins)

### 13.6 创建和使用混入

### 13.7 怎样合并多个混入

### 13.8 创建一种特殊的全局混入

### 13.9 混入和作用域

### 13.10 作业11描述 : 过滤器和混入

### 13.11 作业11答案 : 过滤器和混入

### 13.12 本章总结

## 第14章 使用动画和过渡

### 14.1 本章介绍

### 14.2 理解什么是过渡?

### 14.3 为使用过渡来做代码准备

### 14.4 过渡的配置

### 14.5 为过渡分配css类

### 14.6 使用css过渡属性来创建

### 14.7 使用css动画属性来创建"滑动"过渡

### 14.8 混合过渡和动画两种属性

### 14.9 v-if和v-show动画

### 14.10 配置初始化(加载)动画

### 14.11 使用不同的css类名

### 14.12 使用动态命名和属性

### 14.13 多个元素间的过渡 (理论)

### 14.14 多个元素间的过渡 (实践)

### 14.15 监听过渡事件的钩子

### 14.16 理解什么是JS动画

### 14.17 从动画中去掉css

### 14.18 在JS中创建动画

### 14.19 让动态组件做动画

### 14.20 使用来做列表动画

### 14.21使用的准备

### 14.22 使用来让列表做动画

### 14.23 理解这个应用

### 14.24 创建这个应用

### 14.25 添加动画

### 14.26 本章总结

## 第15章 使用vue-resource来通过HTTP连接到服务器

### 15.1 本章介绍

### 15.2 配置:用vue-resource来访问HTTP

### 15.3 基于Firebase来创建应用和服务端

### 15.4 用POST方法给服务端发送数据

### 15.5 用GET请求来获取和转换数据

### 15.6 全局配置vue-resource

### 15.7 拦截请求

### 15.8 拦截响应

### 15.9 vue-resource里的resource从哪里来

### 15.10 创建自定义的资源

### 15.11 资源vs传统HTTP请求

### 15.12 理解URL模板

### 15.13 本章总结

## 第16章 VueJS应用中的路由概念

### 16.1 本章介绍

### 16.2 配置VueJS路由 (vue-router)

### 16.3 配置和加载路由

### 16.4 理解路由模式 (哈希vs历史)

### 16.5 路由链接导航

### 16.6 我在哪儿 ? 定义活动链接

### 16.7 通过代码导航 (强制导航)

### 16.8 配置路由参数

### 16.9 获取,使用路由参数

### 16.10 响应路由参数改动

### 16.11 配置子路由 (嵌套路由)

### 16.12 潜逃路由导航

### 16.13 更动态的配置路由链接

### 16.14 创建链接的更好方式 - 命名路由

### 16.15 使用查询参数

### 16.16 多路由视图 (命名路由视图)

### 16.16 重定向

### 16.17 配置 "Catch All"路由/通配符

### 16.18 路由动画过渡

### 16.19 传递Hash Fragment

### 16.20 控制卷屏行为

### 16.21 使用守卫来保护路由

### 16.22 使用"beforeEnter"守卫

### 16.23 使用"beforeLeave"守卫

### 16.24 路由懒加载

### 16.25 本章总结

## 第17章 用Vuex来更好的管理状态

### 17.1 本章介绍

### 17.2 为什么要用一个不同的状态管理机制

### 17.3 理解集中的状态

### 17.4 使用集中状态

### 17.5 为什么集中状态自身并不能解决问题

### 17.6 理解Getter

### 17.7 使用Getter

### 17.8 将Getter映射到属性

### 17.9 理解Mutation

### 17.10 使用Mutation

### 17.11 为什么Mutation要使用同步执行模式

### 17.12 Action怎么改进Mutation

### 17.13 使用Action

### 17.14 将Action映射到方法

### 17.15 Vuex总结

### 17.16 双向绑定 (v-model) 和 Vuex

### 17.17 改进的目录结构

### 17.18 模块化状态管理

### 17.19 使用分割的文件

### 17.20 使用名字空间来避免命名冲突问题

### 17.21 本章总结

## 第18章 最终实训项目-股票交易

### 18.1 项目介绍

### 18.2 项目配置和规划

### 18.3 创建第一个组件

### 18.4 配置项目路由

### 18.5 添加头部导航

### 18.6 规划下一步

### 18.7 创建股票组件

### 18.8 添加购买按钮

### 18.9  配置Vuex状态管理

### 18.10 为Vuex添加展示模块

### 18.11 实现展示用的股票

### 18.12 将展示模块连接到Vuex

### 18.13 修复一些Bug

### 18.14 显示资金

### 18.15 添加记名支票

### 18.16 使用过滤器让资金显示更好看

### 18.17 一天的结束 - 随机股票价格

### 18.18 路由过渡动画

### 18.19 保存和获取数据 - 添加下拉菜单

### 18.20 与Firebase一起配置vue-resource

### 18.21 保存数据 (PUT请求)

### 18.22 获取数据 (GET请求)

### 18.23 测试和修复Bug

### 18.24 项目总结

### 18.25 使用Vue开发工具调试Vuex

## 第19章 部署VueJS应用

### 19.1 项目介绍

### 19.2 部署准备

### 19.3 部署应用(使用亚马逊AWS S3)

## 第20章 课程总结

### 课程总结

## 第21章 使用Axios替代vue-resource

### 21.1 概述

### 21.2 本章介绍

### 21.3 工程配置

### 21.4 Axios配置

### 21.5 发送POST请求

### 21.6 发送GET请求

### 21.7 访问和使用响应数据

### 21.8 全局请求配置

### 21.9 使用拦截器

### 21.10 自定义Axios实例

### 21.11 总结

## 第22章 Vue应用中的鉴权

### 22.1 概述

### 22.2 本章介绍

### 22.3 单页应用中鉴权工作原理

### 22.4 工程配置

### 22.5 添加用户注册

### 22.6 添加用户登录

### 22.7 使用Vuex发送鉴权请求

### 22.8 在Vuex中保存鉴权数据

### 22.9 通过Vuex访问其他资源

### 22.10 向后台发送Token

### 22.11 路由保护 (Auth Guard)

### 22.12 基于鉴权状态来更新UI状态

### 22.13 添加用户登出功能

### 22.14 添加自动登出功能

### 22.15 添加自动登录功能

### 22.16 总结

## 第23章 表单输入验证

### 23.1 概述

### 23.2 本章介绍

### 23.3 安装Vuelidate

### 23.4 添加验证器

### 23.5 验证时添加UI反馈

### 23.6 控制错误输入的显示风格

### 23.7 更多的验证器

### 23.8 验证密码

### 23.9 使用必填验证器

### 23.10 验证数组

### 23.11 控制表单提交按钮

### 23.12 创建自定义验证器

### 23.13 异步验证器

### 23.14 本章总结
