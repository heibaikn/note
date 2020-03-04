# vue

## 生命周期
```js
new Vue()   //初始化
beforeCreate  //数据观测 (data observer) 和 event/watcher 事件配置之前
create  //实例创建完成
beforeMount  //挂载前
mounted     // 挂载后 可以访问 vm.$el，但子组件不确定已更新
beforeUpdate // 数据更新时调用
updated       //这个钩子被调用时，组件 DOM 已经更新
activated     //keep-alive 缓存的组件激活时
deactivated   //keep-alive 缓存的组件停用时调用
beforeDestroy
destroyed
```

## 双向数据绑定
Vue 2.x双向数据绑定是Object.defineProperty,此属性无法被babel/polyfill模拟(shim)，故不支持IE8一下版本
```js
// Object.defineProperty
function func(){
    let count = 10;
    Object.defineProperty(this,'skillLevel',{
        get:() => {
            return count;
        },
        set:value => {
            count = value;
        }
    })
}

let x = new func();
console.log(x.skillLevel);// 10

```
Vue 3.0双向数据绑定是es6 Proxy, Proxy的主要用途为：日志记录，校验值，计算属性，双向数据绑定

```js
const obj = {name:'value'}
const representtive = new Proxy(obj, {
    get: (target, key) =>{
        return key in target ? target[key]:"不存在该值“
    },
    set: (target, key, value)=>{
        target[key] = value;
    }
})

```
## 数据通信

> props,$emit  子父组件通信，父传递数据给子，子事件触发到父

> provide/inject  多级组件嵌套通信 

> $attrs/$listeners 多级组件嵌套

> eventBus    任意组件通信，中央事件总线（事件中心）

> vuex    任意组件通信 


## 指令

生命钩子
```js
bind
inserted
update
componentUpdated
unbind
```
每个钩子方面内可以访问 el,binding(name,value,expression),vnode,oldvnode

## 组件
全局组件
```js
import MyLoading from './Loading.vue';
const Loading = {
    install: function(Vue){
        Vue.component('Loading',MyLoading)
    }
}
Vue.use(Loading);
```
局部组件
```js
var ComponentA = { /* ... */ }
var ComponentB = {
  components: {
    'component-a': ComponentA
  },
}
```



