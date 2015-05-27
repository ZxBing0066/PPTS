title: hybrid-分享
speaker: 王兵兵
transition: zoomin


[slide]


# hybrid-分享

<small>演讲者:王兵兵</small>


[slide]


# 个人见解,仅供参考

> 里面很多观点可能与个人工作经历有关,
>
> 可能只代表部分情况下的个人见解,
>
> 有问题还请大家指正.


[slide]


# 移动端-大趋势

* 手机
* 平板
* 可穿戴设备(Watch,Glass)
* etc


[slide]


# APP开发模式

> 根据移动端的特性,出现了很多不同的开发模式.

* Native--->Android,IOS,WP {:&.rollIn}
* Web
* Hybrid--->phonegap,weixin-JSAPI,Lizard
* React-Native


[slide]


# 各种开发模式的优缺点

开发模式之间各有优劣.

[slide]


# Native的优势与缺陷

[subslide]
## 优势
	* 人机交互用户体验(原生组件) {:&.rollIn}
	* 绝对的性能优势
	* 功能实现更全面(通知栏,服务等)
============
## 缺陷
	* 开发成本高,发布周期远远跟不上产品节奏 {:&.rollIn}
	* 平台差异需要开发多套代码
	* 灵活性差,模块化不起来
	* 发布麻烦(审批)
	* 更新困难,需用户主动
[/subslide]


[slide]


# WebApp的优势与缺陷

[subslide]
## 优势
	* 适用范围广 {:&.rollIn}
	* 开发成本低
	* 发布部署方便
	* 无需手动更新,实时最新展示
============
## 缺陷
	* 体验差 {:&.rollIn}
	* 性能差
	* 需要互联网
	* 功能限制
[/subslide]


[slide]


# Hybird

> Hybird混合了Native以及Web的优势和缺陷,折中的方式.
> 
> 而且目前Hybrid使用面已经很广:腾讯,阿里,京东,携程等.

[subslide]
## 优势
	* 所有webapp的优势 {:&.rollIn}
	* 可使用本地代码解决资源下载慢,互联网必要等限制
	* 可以调用Native的功能
============
## 缺陷
	* 大多数功能实现都是使用web,还是存在性能瓶颈 {:&.rollIn}
	* 多了一层HybridAPI,开发协调有困难
[/subslide]


[slide]


# React-Native

[subslide]
![React-Native](/imgs/react-native.jpg)
============
## 优势
	* Native的用户体验 {:&.rollIn}
	* React的开发效率
============
## 缺陷
	* 依赖 React native 开发人员暴露的接口 {:&.rollIn}
	* 初学成本
	* 安卓版10月份出世
	* 目前不完善
[/subslide]


[slide]


# 携程Lizard框架的实现

[subslide]
### 桥接方式
	* confirm {:&.rollIn}
	* URL Schemes(主流)
	* etc
============
![流程图1](/imgs/process1.jpg)
============
### URL Schemes
	* ctrip://wireless 打开携程App {:&.rollIn}
	* weixin:// 打开微信
============
### Native调用JS
	* native通过string调用js {:&.rollIn}
	* webview调用js解释器的eval方法将string转化为js方法
	* webview调用js方法
============
### JS调用Native
	* javascript改变url，通过url传递调用的方法和参数 {:&.rollIn}
	* webview监听到了URL变化，并且探测到url中定义的方法和参数
	* 寻找对应的映射表，找到native对应接口api进行调用
	* 执行javascript调用方法时传入的回调string并添加数据
	* webview解析string转化为javascript进行调用
[/subslide]


[slide]


# 结束,谢谢各位~