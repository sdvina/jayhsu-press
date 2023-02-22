# Vue基础

# Vue Router 3.X

## 安装

* `直接下载/CDN`
 
  [Unpkg.com](https://unpkg.com/)提供了基于 NPM 的 CDN 链接。上面的链接会一直指向在 NPM 发布的最新版本。你也可以像 https://unpkg.com/vue-router@3.0.0/dist/vue-router.js 这样指定 版本号 或者 Tag。
```html
<script src="/path/to/vue.js"></script>
<script src="/path/to/vue-router.js"></script>
``` 
* `NPM`
```sh
npm install vue-router
```
  如果在一个模块化工程中使用它，必须要通过 Vue.use() 明确地安装路由功能：
```js
import Vue from 'vue'
import VueRouter from 'vue-router'

Vue.use(VueRouter)
```
  如果使用全局的 script 标签，则无须如此 (手动安装)。
* `Vue CLI`
  
  如果你有一个正在使用 [Vue CLI](https://cli.vuejs.org/zh/)的项目，你可以以项目插件的形式添加 Vue Router。CLI 可以生成上述代码及两个示例路由。它也会覆盖你的 App.vue，因此请确保在项目中运行以下命令之前备份这个文件：
```sh
vue add router
```
* `构建开发版`
  如果你想使用最新的开发版，就得从 GitHub 上直接 clone，然后自己 build 一个 vue-router。
```sh
git clone https://github.com/vuejs/vue-router.git node_modules/vue-router
cd node_modules/vue-router
npm install
npm run build
```
## 基础
用 Vue.js + Vue Router 创建单页应用，感觉很自然：使用 Vue.js ，我们已经可以通过组合组件来组成应用程序，当你要把 Vue Router 添加进来，我们需要做的是，将组件 (components) 映射到路由 (routes)，然后告诉 Vue Router 在哪里渲染它们。下面是个基本例子：
```html
<script src="https://unpkg.com/vue@2/dist/vue.js"></script>
<script src="https://unpkg.com/vue-router@3/dist/vue-router.js"></script>

<div id="app">
  <h1>Hello App!</h1>
  <p>
    <!-- 使用 router-link 组件来导航. -->
    <!-- 通过传入 `to` 属性指定链接. -->
    <!-- <router-link> 默认会被渲染成一个 `<a>` 标签 -->
    <router-link to="/foo">Go to Foo</router-link>
    <router-link to="/bar">Go to Bar</router-link>
  </p>
  <!-- 路由出口 -->
  <!-- 路由匹配到的组件将渲染在这里 -->
  <router-view></router-view>
</div>
```
```js
// 0. 如果使用模块化机制编程，导入Vue和VueRouter，要调用 Vue.use(VueRouter)

// 1. 定义 (路由) 组件。
// 可以从其他文件 import 进来
const Foo = { template: '<div>foo</div>' }
const Bar = { template: '<div>bar</div>' }

// 2. 定义路由
// 每个路由应该映射一个组件。 其中"component" 可以是
// 通过 Vue.extend() 创建的组件构造器，
// 或者，只是一个组件配置对象。
// 我们晚点再讨论嵌套路由。
const routes = [
  { path: '/foo', component: Foo },
  { path: '/bar', component: Bar }
]

// 3. 创建 router 实例，然后传 `routes` 配置
// 你还可以传别的配置参数, 不过先这么简单着吧。
const router = new VueRouter({
  routes // (缩写) 相当于 routes: routes
})

// 4. 创建和挂载根实例。
// 记得要通过 router 配置参数注入路由，
// 从而让整个应用都有路由功能
const app = new Vue({
  router
}).$mount('#app')

// 现在，应用已经启动了！
```
通过注入路由器，我们可以在任何组件内通过 this.$router 访问路由器，也可以通过 this.$route 访问当前路由：
```js
// Home.vue
export default {
  computed: {
    username() {
      // 我们很快就会看到 `params` 是什么
      return this.$route.params.username
    }
  },
  methods: {
    goBack() {
      window.history.length > 1 ? this.$router.go(-1) : this.$router.push('/')
    }
  }
}
```