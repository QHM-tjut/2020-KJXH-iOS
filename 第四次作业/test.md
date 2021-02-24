# 齐浩铭第四周学习报告 

---

[toc]

## 完成iOS培训demo

<img src="/Users/qihaoming/Library/Application Support/typora-user-images/image-20210125202631461.png" alt="image-20210125202631461" style="zoom: 25%;" />

<img src="/Users/qihaoming/Library/Application Support/typora-user-images/image-20210125202720848.png" alt="image-20210125202720848" style="zoom:25%;" />

## 部分代码

### 单例

在某些情况下（如管理类）我们只需要实例化一个类，每次实例化这个（管理）类的时候都返回第一次实例化时得到的地址

```objective-c
+ (instancetype)blueToothDeviceManager{
    static MYBlueToothDeviceManager *blueToothDeviceManager;
    static dispatch_once_t onceToken;
    dispatch_once(&onceToken, ^{
        blueToothDeviceManager = [[MYBlueToothDeviceManager alloc] init];
    });
    return blueToothDeviceManager;
}
```

### delegate

真正自己写了delegate，之前都是用系统写好的

⚠️：

1.

```
@protocol MYDeviceManagerDelegate <NSObject>
-(XXXX)xxxx;
@end
```



2.设置XXX.delegate = self;

3.设置@property (weak) ID delegate   //weak 解除循环应用，防止内存泄露

4.在委托方中判断被委托方是否实现必须的方法 并且执行此方法

```objective-c
 if (self.delegate && [self.delegate respondsToSelector:@selector(reloadDataInManager:)]){
            [self.delegate reloadDataInManager:self];
        }
```









