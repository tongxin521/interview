# React 面试知识点总结

## 1.fetchVSajaxVSaxios

传统Ajax指的是XMLHttpRequest（XHR），最早出现的发送后端请求技术，隶属于原始js中，核心使用XMLHttpRequest对象，多个请求之间如果有先后关系的话，就会出现回调地狱。JQueryajax是对原生XHR的封装

axios是一个基于Promise，本质上也是对原生XHR的封装，只不过它是Promise的实现版本，符合最新的ES规范



fetch不是ajax的进一步封装，而是原生js，没有使XMLHttpRequest对象

## 2.React事件处理---修改this指向

方式1：通过bind方法进行原地绑定，从而改变this指向

方式2：通过创建箭头函数

方式3：在constructor中提前对事件进行绑定

方式4：将事件调用的写法改为箭头函数的形式

## 3.请简述你对react的理解

React起源于facebook，react是一个用于构建用户界面的js库

特点：

声明式设计：react采用范式声明，开发者只需要声明显示内容，react就会自动完成

高效：react通过对dom的模拟（也就是虚拟dom），最大限度的减少与dom的交互

灵活：react可以和已知的库或者框架很好配合

组件：通过react构建组件，让代码更容易复用，能够很好应用在大型项目开发中，把页面功能拆分成小模块每个小模块就是组件

单向数据流：react是单向数据流，数据通过props从父节点传递到子节点，如果父级的某个props改变了，react会重新渲染所有的子节点

## 4.react组件之间的数据传递

正向传值用props

逆向传值用函数传值通过事件调用函数传递

同级传值用pubsub-js

​	用pubsub.publish（事件名，数据）抛出数据

​	用pubsub.subscribe（监听的事件，（）=）{}）接收数据

跨组件传递用context要使用context进行跨组件传值就需要使用createContext()方法，这个方法有两个对象provider生产者Consumer消费者

## 5.Vue与react区别

相同点：

​	都支持服务器渲染

​	都有虚拟dom，组件化开发，通过props参数进行父子组件数据的传递，都实现webcomponent规范

​	都是数据驱动视图

​	都有状态管理，react有redux，vue有vuex

​	都有支持native’的方案react有reactnativevue有weex

不同点：

react严格上只针对mvc的view层，vue是mvvm模式

虚拟dom不一样，vue会跟踪每一个组件的依赖关系，不需要重新渲染整个dom组件树，而react不同，当应用的状态被改变时，全部组件都会重新渲染，所以react中用shouldcomponentupdate这个生命周期的钩子函数来控制组件写法不一样，react是jsx和inlinestyle，就是把html和css全写进js中，vue则是html，css，js在同一个文件

6.请简述虚拟dom与diff算法

虚拟DOM也就是常说的虚拟节点，它是通过js的object对象模拟DOM中的节点，然后再通过特定的渲染方法将其渲染成真实的DOM节点。

频繁的操作DOM，或大量造成页面的重绘和回流

Diff算法：把树形结构按照层级分解，只比较同级元素，给列表结构的每个单元添加唯一的key值，方便比较

## 6.你对组件的理解

可组合，可复用，可维护，可测试

## 7.调用setState之后发生了什么？

React在调用setstate后，react会将传入的参数对象和组件当前的状态合并，触发调和过程，

在调和过程中，react会根据新的状态构建react元素树重新渲染整个UI界面，在得到元素树之后，react会自动计算新老节点的差异，根据差异对界面进行最小化重新渲染

## 8.react生命周期函数

componentWillMount组件渲染之前调用

componentDidMount在第一次渲染之后调用

componentWillReceiveProps在组件接收到一个新的props时调用

shouldComponentUpdate判断组件是否更新html

componentWillupdate组件即将更新html时调用

componentDidupdate在组件完成更新后立即调用

componentWillUnmount在组件移除之前调用

## 9.为什么虚拟dom会提高性能?(必考)

虚拟dom相当于在js和真实dom中间加了一个缓存，利用domdiff算法避免了没有必要的dom操作，从而提高性能

## 10.(组件的)状态(state)和属性(props)之间有何不同

区别：

​	Props是一个从外部传进组件的参数，主要作用就是父组件向子组件传递数据，但是props对于使用它的组件来说是只读的，一旦赋值不能修改，只能通过外部组件主动传入新的props来重新渲染子组件

​	State一个组件的显示形态可以由数据状态和外部参数决定，外部参数是props，数据状态就是state，首先，在组件初始化的时候，用this.state给组件设定一个初始的state，在第一次渲染的时候就会用这个数据来渲染组件，state不同于props一点时，state可以修改，通过this.setState()方法来修改state

## 11.shouldComponentUpdate是做什么的

这个react生命周期钩子函数是来解决这个问题

​	在更新数据的时候用setState修改整个数据，数据变了之后，遍历的时候所有内容都要被重新渲染，数据量少还好，数据量大就会严重影响性能

解决办法：

1.shouldcomponentupdate在渲染前进行判断组件是否更新，更新了再渲染

2.purecomponent（纯组件）省去了虚拟dom生成和对比的过程在类组件中使用

3.react.memo()类似于纯组件在无状态组件中使用

## 12.react diff原理

它是基于三个策略：

tree diff web UI中dom节点跨层级的移动操作特别少，可以忽略不计component diff拥有相同类的两个组件将会生成相似的树形结构，拥有不同类的两个组件会生成不同的树形结构

element diff对于同一层级的一组子节点，他们可以通过唯一的id进行区分何为受控组件

React负责渲染表单的组件，值是来自于state控制的，输入表单元素称为受控组件

## 13.调用super(props)的目的是什么

Super（）调用父类的构造方法，有super，组件才有自己的this，在组件全局中都可以使用this，如果只是constructor而不执行super，之后的this都是错的，super继承父组件的this

##14.React中构建组件的方式

自定义组件：函数组件或者无状态组件组件首字母大写

类组件：一个类组件必须实现一个render方法，这个方法必须返回一个jsx元素，要用一个外层的元素把所有内容包裹起来

