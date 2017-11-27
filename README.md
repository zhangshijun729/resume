## 联系方式
* 应聘职位：前端开发工程师
* 手机：13682141467
* Email：zhangshijun729@163.com
* QQ：462895506
* 微信：z462895506
## 个人信息
* 张世钧/男/1990
* 专科/天津中德应用技术大学
* 工作年限：2年
* 期望薪资：6k-7k
* 期望城市：天津
## 项目
#### VueNote
功能介绍：这是一款轻量在线单页记笔记管理的应用，支持增删改查、标记等管理操作

技术细节：技术上应用了vue-cli快速搭建开发环境，vue2.0框架构建单页应用，vuex处理各组件间的通讯，使用预处理语言SCSS开发样式，webpack打包模块，flex布局让代码更简洁，使用localStorage本地存储

难点：
vue的双向数据绑定给人的最大的感觉就是方便。当数据data发生变化时，页面自动发生更新。但是有一个缺点也是因为自动更新而导致的，因为这样你就不知道data什么时候变了，也不知道是谁变了，变化后也不会通知你，当然可以watch来监听data的变化，但是这变复杂了，还不如单向数据绑定。除此之外单向数据绑定对于复杂应用来说是实施统一的状态管理，方便跟踪。
根据vuex文档，得知双向绑定改为单向绑定的方法，就是给input绑定value，然后监听input或者change事件，在事件回调中调用action来实现单向绑定

技术栈：vue-cli+vue+vuex+SCSS+webpack+flex+ES6+localStorage

预览地址：https://zhangshijun729.github.io/vueNotepad/dist/index#/

源码：https://github.com/zhangshijun729/vueNotepad

#### canvas画图
功能介绍：这是一款在移动端运行的画图软件，支持画图和橡皮擦功能

技术细节：技术上运用了HTML5的新元素标签canvas，所有功能完全使用canvasAPI实现。代码由原生js编写

难点：
在控制台打开手机模拟手机模式，canvas是行内模式，会很大，可以左右移动，这样不是我们想要的，所以需要手动设置宽高，但是手动行内设置宽高，会导致大小被写死，在不同的屏幕下不能自适应。还可以在css写宽高，但是这样会导致canvas缩放，并不会改变宽高。所以，要用js来改变宽高，可以用document.clientWitch和document.clientHeight来获取可见的宽和高，再赋值给canvas的宽和高，这样就可以做到屏幕自适应。还有一点，canvas在最下方会有一条缝隙，把canvas设置成display:block可以解决这个问题，设置vertical-align:top也可以获得相同的结果.

在实际画图时，每次开始绘画时都会在上一次停止的点继续绘画，第一次除外，这是因为，touchmove有一个触发频率，如果移动得越慢，触发的点越密集，相反，触发的点越疏散，为了能够让每个点之间用线连起来，我们用一个变量来存储上一个点的位置，然后在新触发的点和上一个点之间连线，这样，每次停止绘画，记录的上一个点就变成了停止的那个点，所以会在停止的点继续绘画。解决办法是，每次停止绘画时，就添加一个touchend事件，把记录上一个点的变量清除，值为null，这样，就可以重新绘画了。

技术栈：HTML5 canvas+js

预览地址：https://zhangshijun729.github.io/canvas/canvas%E7%94%BB%E5%9B%BE

源码：https://github.com/zhangshijun729/canvas

#### 网站主页
功能介绍：仿某首页项目，完全按照该网页样式制作，高精度还原。以组件化实现全屏轮播和回到顶部功能。

技术细节：技术上应用了jQuery库和webpack前端模块化工具，webpack可以帮助我们打包文件，并且可以使用bable转换器让浏览器更好的支持ES6

难点：
在点击左右移动箭头时，若点击速度不快，不会看出有什么bug，当点击速度过快时，因为点击速度快，轮播图片左右移动的速度慢，所以图片会一直左右移动，直到达到点击的次数，这显然不是想要的效果，所以效仿ajax请求数据时的操作，添加一个isAimate状态锁，赋值为false，每次点击左右移动时，检查isAnimate是不是true，如果是，就返回，如果是false，就进行点击左右移动的操作，并把isAnimate赋值为true，使动画结束前点击的操作无效化，在动画结束后，再把isAnimate赋值为false，使接下来的操作有效化。

技术栈：jQuery+webpack+ES6

预览地址：https://zhangshijun729.github.io/newBootstrap/

源码：https://github.com/zhangshijun729/newBootstrap

#### 瀑布流新闻
功能介绍：这是一个利用瀑布流布局展示的新闻网站,调用新浪图片的接口，利用jsonp跨域方法获取到数据

技术细节：技术上利用了jQuery库，通过jQuery的简洁命令，实现数据请求，页面渲染，事件监控等，极大地减少了代码量

难点：
在项目中，我们让瀑布流只能显示三列，新的一行的起始是在上一行高度最短的那一行开始，那么怎么知道哪一行的高度最短呢？最初的想法是直接获取，发现获取的高度为0，不是有图片了吗，为什么高度是0？通过网上查找，知道是异步的原因，因为在img标签在被添加到页面时，图片还没开始下载，所以获取不到高度，高度为0，就没办法完成瀑布流。解决办法，我们可以等到这一次请求的图片全部下载完成，通过jQuery官方文档查询，知道jQuery有load方法，图片都下载完了，知道了图片的高度，就可以运行瀑布流布局的函数了。

技术栈：jQuery+jsonp跨域

预览地址：https://zhangshijun729.github.io/waterFall/waterfall

源码：https://github.com/zhangshijun729/waterFall
## 我的技能
&nbsp;&nbsp;熟悉 W3C 规范，熟练掌握HTML(5)和常用CSS(3)，能结合 	JavaScript 以及 jQuery 做出对设计稿像素级还原的静态页面。

&nbsp;&nbsp;熟悉原生JavaScript，掌握如：原型、闭包、作用域链、面向对象等重要概念，熟练使用ES6新特性。

&nbsp;&nbsp;了解AJAX的原理及应用，了解 JSONP等跨域解决方案，能与后端程序员配合实现动态页面。

&nbsp;&nbsp;了解npm&Git，有相关使用经验，能使用Git工具对代码进行版本管理。

&nbsp;&nbsp;熟悉vue框架，理解生命周期、组件等重要概念，了解vuex，可基于vue实现web应用，并有独立完成的项目。

## 工作经历
天津阿尔斯通水电设备有限公司  数控操作
