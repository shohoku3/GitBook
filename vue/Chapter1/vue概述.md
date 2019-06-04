##Vue概述
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
#### 监听属性
- watch:{语句}
#### 计算属性和监听属性
Vue 提供了一种更通用的方式来观察和响应 Vue 实例上的数据变动：侦听属性

- 推荐使用计算属性

#### setter getter
- 源于Js的对象属性访问器

#### style 绑定
- html class 绑定 v-bind:class
- 数组语法 v-bind:class="[activeclass,errorclass]"
- 组件添加


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
