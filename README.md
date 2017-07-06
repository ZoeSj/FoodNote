这个参考的是一个记事本的demo，为了面试学的vue，看了两天，觉得想要更快的上手最好还是做一个demo。这是我刚开始学的时候做的一些小[demo](https://github.com/ZoeSj/demo-of-vue)，跟着[文档](http://cn.vuejs.org/v2/guide/)来的。
这里就不写关于如何安装vue了，文档上写的很清楚，而且我自己安装过程也没遇到什么大问题，如果有问题，可以看看他写的[[windows下搭建vue开发环境](http://blog.csdn.net/wu__di/article/details/54234894)](http://blog.csdn.net/wu__di/article/details/54234894)（他这里面npm老是写错，注意点）。把那几个命令记住就可以了（我老是记不住，我写在这里防止我自己又忘了）
```
# 全局安装 vue-cli
$ npm install --global vue-cli
# 创建一个基于 webpack 模板的新项目
$ vue init webpack my-project
# 安装依赖，走你
$ cd my-project
$ npm install
$ npm run dev
```
安装依赖的时候，使用npm可能会比较慢，推荐使用cnpm。
```
npm install -g cnpm --registry=[https://registry.npm.taobao.org](https://registry.npm.taobao.org/)
# vue-cli的安装
cnpm install -g vue-cli 
```
担心自己忘了，就截图放这了，唉，人老了，记性好差的。
![这是这个demo里面用到的命令](http://upload-images.jianshu.io/upload_images/3162008-c791230b0d208aa4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![安装依赖node-sass，和上面作用一样](http://upload-images.jianshu.io/upload_images/3162008-cff3574ed63e431d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![安装sass-loader](http://upload-images.jianshu.io/upload_images/3162008-402e53356114e710.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
还有要安装vuex：`npm insatll --save vuex`

这里说下啊，如果不想用eslint来规范代码的话，可以选择no，不然后面没配置好容易报一些格式上的错误。
![](http://upload-images.jianshu.io/upload_images/2645110-770d0f432f77b684.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

-------

vue给我最大的特点就是数据绑定和组件化，使用起来确实很方便，而且功能强大。
建议先把文档上给的小demo都跟着敲一遍，然后看看文档，入门还是可以的。我是为了更快的入门，所以打算着手做一个大点的demo，不然面试会被刷啊。poor me。

--------

这里推荐一篇写的不错的，可以参考参考。

- [Vue 学习笔记](http://www.jianshu.com/p/06be98001dc3)

因为这个demo基于vue2.0+vuex+localStorage+sass+webpack，所以需要了解webpack的一些知识，这里面总结的挺好的。我也在看，后面看完了我再写笔记吧。
废话不多说了，我要开始撸代码了。
先了解一下vuex。这篇[Vuex 入门介绍](http://www.jianshu.com/p/490e7726fe67)挺好的。
相关参考：

- [Vuex 通俗版教程](http://www.jianshu.com/p/caff7b8ab2cf)
- [快速上手vuex](http://www.jianshu.com/p/04ebf09e72a1)
- [Vue 2.0 起步(3) 数据流vuex和LocalStorage实例 - 微信公众号RSS](http://www.jianshu.com/p/fb758398268a)
- [vuex入门实例2](http://www.jianshu.com/p/2b19a2b36d20)
- [vue全家桶之vuex](http://www.jianshu.com/p/ee77747f9dd8)

--------

###为什么要用vuex？
vuex是类似redux的状态管理器，用来管理Vue的所有组件状态，一般来说vuex适合中型或者大型的单页应用（SPA），会出现多个视图组件依赖同一个状态，来自不同视图的行为需要变更同一个状态。但是这个记事本中有个修改主题，切换状态的地方，所以使用vuex更加方便。利用vuex进行状态管理，把所有事件和状态存储在store对象中，在组件中通过计算属性获得事件，因此就有了实时性。使用vuex管理主题状态，并进行模块化管理，用localStorage永久存储选中的主题颜色。