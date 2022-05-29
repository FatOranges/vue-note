# Vue-imooc

## 基本使用

### computed

#### 概述

computed 有缓存，data 不变则不会重新计算。

#### 类型

`{[key:string]: Function | {get: Function, set: Function}}`

#### 示例

```vue
<script>
    const vm  = new Vue({
        computed: {
            computedProperty: function() {
                
            },
            computedProperty2: {
                get: function() {
                    
                },
                set: function() {
                    
                }
             }
        }
    })
</script>
```

### watch

#### 类型

`{[key: string]: string | Function | Object | Array}`

#### 概述

Vue 实例将会在实例化时调用 $watch()，遍历 watch 对象的每一个 property。

#### 示例

```vue
<script>
	const vm = new Vue({
        data: {
            a: 1,
            b: 2,
            c: 3,
            d: 4,
            e: {
                f: {
                    g: 5
                }
            }
        },
        watch: {
            a: function (val, oldVal) {
                console.log('new: %s, old: %s', val, oldVal)
            },
            // 方法名
            b: 'someMethod',
            // 该回调会在任何被侦听的对象的 property 改变时被调用，不论其被嵌套多深
            c: {
                handler: function (val, oldVal) { /* ... */ },
                deep: true
            },
            // 该回调将会在侦听开始之后被立即调用
            d: {
                handler: 'someMethod',
                immediate: true
            },
            // 你可以传入回调数组，它们会被逐一调用
            e: [
                'handle1',
                function handle2 (val, oldVal) { /* ... */ },
                {
                    handler: function handle3 (val, oldVal) { /* ... */ },
                    /* ... */
                }
            ],
            // watch vm.e.f's value: {g: 5}
            'e.f': function (val, oldVal) { /* ... */ }
        }
})
vm.a = 2 // => new: 2, old: 1
</script>
```

#### 注

==1. watch 监听引用类型，拿不到 oldVal。==

==2. 不应该使用箭头函数来定义 watch 函数。会导致 this.updateAutocomplete 将会是 undefined。==

### class & style

### 列表渲染

### 事件处理

https://cn.vuejs.org/v2/guide/events.html

### 表单输入绑定

https://cn.vuejs.org/v2/guide/forms.html

### 组件基础

https://cn.vuejs.org/v2/guide/components.html

#### 组件定义

##### 全局注册组件

```js
// 定义一个名为 button-counter 的新组件
Vue.component('button-counter', {
  data: function () {
    return {
      count: 0
    }
  },
  template: '<button v-on:click="count++">You clicked me {{ count }} times.</button>'
})
```

```html
<div id="components-demo">
  <button-counter></button-counter>
</div>
```

```js
new Vue({ el: '#components-demo' })
```

#### 通过 props 向子组件传递数据

```js
//子组件通过 props 属性接收数据。
Vue.component('blog-post', {
  props: ['title'],
  template: '<h3>{{ title }}</h3>'
})
```

```html
<!-- 父组件通过 attribute 传递数据 -->
<blog-post title="My journey with Vue"></blog-post>
<blog-post title="Blogging with Vue"></blog-post>
<blog-post title="Why Vue is so fun"></blog-post>
```

#### 监听子组件事件



#### 注

==1. 组件的 data 必须是一个函数，如果是一个对象的话会造成组件复用中某个组件的 data 发生修改，其他组件的 data 也会随之修改。==

### 父子组件如何通讯

