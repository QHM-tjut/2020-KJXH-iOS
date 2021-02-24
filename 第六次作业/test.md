# 齐浩铭第六周学习报告

---

[toc]

## UIKit相关

### UIGestureRecongnizerDelegate

处理点击滑动等手势操作

通过 Delegate 的⽅式扩展在⼿势识别过程中的⾃定义操作

### iOS UIWebView and WKWebView

请注意：UIWebView 由于稳定性原因已弃用

通过delegate的方式处理业务逻辑

使用WKWebView的流程：

1.创建WKWebView

2.设置Delegate 以及样式、JS注入

3.加载URL 或 HTML字符串

4.在相应的回调中处理业务逻辑

### iOS动画

#### Core Animation

#### UIView动画

* 处理基本的Frame、Alpha、Transform
* 解决日常开发80%的动画效果
* 不能自定义中间过程

实现方法：

1. 设置动画参数（时间，效果）
2. 动画中之时的属性

### CALayer

全部的UI组件都能取到对应的CALayer

设置圆角或边框啥的用得到

## 观察者模式

* 定义了⼀种⼀对多的关系，可以让多个观察者同时监听某⼀个对象或对象的属性变化

* 被监听的对象在状态变化时，会通知所有的观察者，使他们能够及时的处理业务逻辑

<img src="/Users/qihaoming/Library/Application Support/typora-user-images/image-20210210170402094.png" alt="image-20210210170402094" style="zoom:25%;" />

<img src="/Users/qihaoming/Library/Application Support/typora-user-images/image-20210210170419278.png" alt="image-20210210170419278" style="zoom:25%;" />

## iOS中的Web应用

和浏览器不同：除了要展示的同时还要处理与原生的通信

优点是能跨平台，比如谷歌的Flutter。。。。

## 代码重构方面

### Xcode自带工具

* refactor
* 注释：option + commend + /
* 编译器指令 #pragma mark -

## 依赖管理

常用依赖管理方式

|          subModel          |     CocoaPods（常用）      |        Carthage         |
| :------------------------: | :------------------------: | :---------------------: |
|        基于Git管理         |         Ruby 语言          |       swift 语言        |
|          使用简单          | sudo gem install cocoapods |           ～            |
| 功能较少，只能下载全部项目 | 中心化的管理生成workspace  | 去中心化，提供framework |
|         debug方便          |         debug方便          |       debug不方便       |



## 网络知识

### URL : Uniform Resource Locator

```http
[协议类型]://[服务器地址]:[端⼝号]/[资源层级UNIX⽂件路径][⽂件名]?[查询]#[⽚段ID]
```

### HTTP 请求

GET方法：从指定的资源请求数据

POST方法：向指定的资源提交要被处理的数据

HTTP Header ：请求和相应的补充信息 //长度、编码类型、压缩方式、事件

### 常用开源网络框架AFNetworking

#### 使用CocoaPods 集成

1.在项目文件目录下创建podfile文件

```ruby
target 'Show' do
    pod 'AFNetworking'
end
```

2.执行podiinstall命令

3.出现 项目名称.workspace 代表集成集成成功

#### 使用：

<img src="/Users/qihaoming/Library/Application Support/typora-user-images/image-20210221130712963.png" alt="image-20210221130712963" style="zoom:50%;" />

### JSON

轻量级，⾼可读性，纯⽂本形式的数据交换格式

#### 其他数据格式

protobuf：

内容不具备可读性，但是高性能

#### iOS中的JSON解析

NSJSONSerialization：提供JSON数据和系统对象之间的转换

#### JSON Model 开源项目

优点：

* 简化 NSData —— JSON —— Model 流程
* 避免类型转换错误 / 属性和对象不⼀致
* 相互转换

常用开源项目

YYModel / Mantle / MJExtension

