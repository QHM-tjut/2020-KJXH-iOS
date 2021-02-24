# 齐浩铭第五周学习报告

---

[toc]

## OC语法

### NSCollection类

#### NSArray

NSArray类有两个限制：

1 它只能存储Objective－C对象，不能存储基础数据类型（int、float、BOOL等）。

2 它不能存粗nil（对象的零值和NULL）。

```objective-c
NSArray *ary = @[@"top",@"jungle",@"mid",@"adc",@"support"]; // 初始化
NSLog(@"ary = %@",ary);
```

因为下面的都是NSArray的属性所以可以使用点方法也可以使用get方法

```objective-c
NSArray *ary = @[@"top",@"jungle",@"mid",@"adc",@"support"];
//ary.count == [ary count];
NSLog(@"数组长度 = %lu",ary.count);
//ary.firstObject == [ary firstObject];
NSLog(@"第一个对象 = %@",ary.firstObject);
//ary.lastObject == [ary lastObject];
NSLog(@"最后一个对象 = %@",ary.lastObject);
//ary.sortedArrayHint == [ary sortedArrayHint];
NSLog(@"NSData 的对象 = %@",ary.sortedArrayHint);
//ary.description == [ary description];
NSLog(@"description方法 = %@",ary.description);
```



```objective-c

NSArray *ary = @[@"top",@"jungle"];
//在最后添加一个OC对象，形成一个新的数组。
NSArray *ary1 = [ary arrayByAddingObject:@"lol"];
NSLog(@"ary1 = %@",ary1);
//在最后添加多个对象，形成一个新的数组。
NSArray *ary2 = [ary arrayByAddingObjectsFromArray:ary1];
NSLog(@"ary2 = %@",ary2);
NSLog(@"ary2的长度 = %lu",ary2.count);
//截取数组一部分创建新的数组
NSArray *ary3 = [ary2 subarrayWithRange:NSMakeRange(1, 3)];
NSLog(@"ary3 = %@",ary3);
//ary并没有改变，只是通过它派生出新的数组。
NSLog(@"ary = %@",ary);
```

```objective-c
unsigned long ind = [ary indexOfObject:@"adc"];
NSLog(@"adc在数组中的下标 = %lu",ind);

BOOL co = [ary containsObject:@"support"];
NSLog(@"ary是否包含字符串support %i",co);

//数组连接参数形成字符串
NSString *str1 = [ary componentsJoinedByString:@""];
NSLog(@"str1 = %@",str1);
NSString *str2 = [ary componentsJoinedByString:@"!"];
NSLog(@"str2 = %@",str2);
```

#### NSSet

特点：无需 ， 不能重复

经过了哈希处理，常用来判断里面是不是有包含的对象

```objective-c
if([set containsObject:@"age"]) {
            NSLog(@"set包含age");
        }
        //判断set 是否等于set1
        if ([set isEqualToSet:set1]) {
            NSLog(@"set 等于 set1");
        }
        //判断set是否是否是set1的子集合
        if ([set isSubsetOfSet:set1]) {
            NSLog(@"set isSubsetOfSet set1");
        }

```



#### NSDictionary

字典 键-值

```objective-c
 NSDictionary *dict4=@{@"zs":@"zhaosi",@"zs":@"zhangsan",@"ls":@"lisi",@"bz":@"banzhang"};
NSlog("%@",dice4[@"zs"]);
```







