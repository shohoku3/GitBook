##Vue
#### 简介
轻量 用户界面层 渐进式 框架
#### 建议基础
html css js
#### 引入
- CDN
- npm

#### 特点
- 声明式渲染 {{}}
- 条件循环式显示 v-if v-for
- 处理用户事件 v-on v-model v-bind
- 组件化

#### 约定
- vm == view model

#### 数据方法
- 响应式触发
- Object.freeze() 阻止修改
- 全局属性 $ 区别于用户自定义属性

#### 实例生命周期钩子
vue 实例创建过程中有一系列初始化过程
- 数据监听
- 编辑模板
- 实例挂载Dom
- 数据更新Dom
- 生命周期钩子函数：给用户添加自己的代码
> 不要使用箭头函数
#### 生命周期
##### 创造
- beforeCreate
- create
##### 挂载el
- beforeMount
- mount 挂载
##### data change
- beforeUpdate
- updated
##### destory()
- beforeDestory
- destoryed

![图片](https://cn.vuejs.org/images/lifecycle.png)

#### 模板
基于html 声明式的将Dom绑定 Vue 将模板编译成虚拟 DOM 渲染函数

- 插值 {{message}}
- 原始html v-html="rawhtml"
- v-bind: or :
- 表达式 {{ number+1 }}
> 注意：语句不会生效,花括号内为表达式

#### 语句
- v-if
- v-bind:href=""
- v-bind:[attrname]
- v-on:submit.prevent=""

#### 计算属性
- computed:{ 语句 }

#### 计算属性和监听属性
Vue 提供了一种更通用的方式来观察和响应 Vue 实例上的数据变动：侦听属性

- 推荐使用计算属性

#### setter getter

#### class style 绑定
- html class 绑定 v-bind:class
- 数组语法 v-bind:class="[activeclass,errorclass]"
- 组件添加
#### 条件渲染
- v-if
- v-else
- v-else-if
- v-if="loginType=='key" 根据key值判断 以分开显示
- v-show
> 注意：此属性仅仅是切换css 中的display
> v-if 直到条件为真时才会渲染元素
> v-show 会直接渲染

- v-for

> 不推荐： v-for 和 v-if 一起使用　v-for 的优先级高

#### List render
- 使用v-for控制

#### 事件处理
##### 监听事件 v-on
##### 事件处理方法
- v-on:接收一个需要调用的方法名称

>   
    v-on:click="greet
        methods:{
        	greet:function(){
        	}
    	}

    
- 直接调用方法

>
	<button v-om:click="say(hi)"></button>
	methods:{
		say:function(msg)
		{
			alert(msg)
		}
	}

- 事件修饰符

>	
	v-on:click.stop
	v-on:submit.prevent

- 一次事件

>
	v-on:scroll.once="dothis"

- passive

>
	v-on:scroll.passive="onScroll" 

- 系统修饰
- 按键修饰
- 鼠标修饰

#### 表单输入绑定

- v-model 

>
	v-model 会忽略所有表单元素的 value、checked、selected 特性的初始值而总是将 Vue 实例的数据作为数据来源。

>
	vue-model 在内部为不同输入元素使用不同的属性

- text 和 textarea使用value和input
- checkbox radio 使用checked change
- select 使用 value 作为prop并change

##### 文本
>
	<input v-model="message" palceholder="edit me">
	<p>Messge is :{{message}}</p>

### 组件基础
>	
	Vue.component('button-counter', {
  		data: function () {
    	return {
     	 count: 0
   		}
  	},
  	template: '<button v-on:click="count++">You clicked me {{ count }} times.</button>'
	})
#### 组件复用
>
	data 必须是一个函数

>	data:function(){}

#### 组件的组织
- 组件树
![](https://cn.vuejs.org/images/components.png)
##### 组件树注册类型
- 全局注册
- 局部注册
##### 通过Prop 向子组件传递数据

>	
	Vue.component('blog-post',{
		props:['title'],
		})

		<blog-post title="my journey with vue"></blog-post>

##### 单个根元素 
- 将模板包含于一个父元素中

##### 在组件上使用 v-model

- 将value 绑定 到名为value prop上
- input 触发时 将新值用$emit() 抛出

>
	Vue.component('custom-input',{
		props:['value'],
		template:`
			<input v-bind:value="value"
			v-on:input="$emit('input',$event.target.value)"
			>
			`
		})

##### 通过插槽分发内容
##### 动态组件
- 特殊 is 特性实现

>
	<component v-bind:is="currentTabComponent"></component>

#####解析 DOM 模板时的注意事项
- 如果使用单文件组件不会出现
