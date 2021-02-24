# 第三周学习报告

[toc] 

## iOS常用开发工具

![iOS 开发工具](/Users/qihaoming/Desktop/iOS 学习截图/iOS 开发工具.png)

### 层级图

![3D71690038808D3BE3A3FCC0D59A3A78](/Users/qihaoming/Desktop/3D71690038808D3BE3A3FCC0D59A3A78.jpg)

![041F6788771598B8A5A68FC3D21CBC05](/Users/qihaoming/Desktop/041F6788771598B8A5A68FC3D21CBC05.jpg)



## iOS开发学习

---

### 常用视图

#### UIview

管理屏幕上矩形区域内容的对象。

#### UIViewController

一个为你的UIKit应用管理视图层次结构的对象。

#### UICollectionView

一个对象，它管理有序的数据项集合，并使用可定制的布局来显示这些数据项。(比如快手的流势界面)

#### UITableViewController

专门管理表视图的视图控制器。

##### 实现delegate 和 datasource

delegate：cell的高度，header、footer 点击

detasource：行数 cell复用

##### UITableView复用Cell

```objective-c
HMTableViewCell *cell = [tableView dequeueReusableCellWithIdentifier:@"id"];
    if(!cell){
        cell = [[HMTableViewCell alloc] initWithStyle:UITableViewCellStyleSubtitle reuseIdentifier:@"id"];
    }
```

##### UITableViewCell默认提供基础样式

![UITableViewCell 默认提供的样式](/Users/qihaoming/Desktop/iOS 学习截图/UITableViewCell 默认提供的样式.png)

##### index

![UITableViewCell](/Users/qihaoming/Desktop/iOS 学习截图/UITableViewCell.png)

##### 默认展示

![UITableViewCell 默认提供的样式](/Users/qihaoming/Desktop/iOS 学习截图/UITableViewCell 默认提供的样式.png)

#### UINavigationController

定义了一个基于堆栈的方案来导航分层内容的容器视图控制器

1.通过栈来管理页面的跳转

2.通常只显示栈顶页面

3.push（入栈） pop（出栈）

![UINavigationController 管理页面](/Users/qihaoming/Desktop/iOS 学习截图/UINavigationController 管理页面.png)

#### UIScrollView

允许滚动和缩放所包含视图的视图

被UITableView和UICollectionView等能滑动的界面包含

![UIScrollViewDelegate](/Users/qihaoming/Desktop/UIScrollViewDelegate.png)

![UIScrollView](/Users/qihaoming/Desktop/UIScrollView.png)

#### UILable

显示一行或多行信息文本的视图。

![image-20210118121102698](/Users/qihaoming/Library/Application Support/typora-user-images/image-20210118121102698.png)

---

### app设计模式

Apple推荐设计模式——UITabbar 下的n个UINavigationController

![方便、常用的应用设计模式](/Users/qihaoming/Desktop/iOS 学习截图/方便、常用的应用设计模式.png)

---

方便常用的设计模式

![方便、常用的应用设计模式](/Users/qihaoming/Desktop/iOS 学习截图/方便、常用的应用设计模式.png)

#### delegate设计模式

委托

![2323548-1012c802b4451641](/Users/qihaoming/Desktop/2323548-1012c802b4451641.webp)

[优质回调博客网址](https://www.jianshu.com/p/376ba5343097)

#### MVC设计模式

**model**

存放数据

**view**

存放视图

**controller**

存放控制器

