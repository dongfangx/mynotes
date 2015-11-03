#类文件定义

## 头文件 

```
#import <Foundation/Foundation.h>

@interface UIView (Addtions)

@property (nonatomic) CGFloat left;

- (void)removeAllSubviews;

@end
```

## 实现文件 
```
#import "UIViewAdditions.h"

@implementation UIView (Addtions)

- (CGFloat)left {
    return self.frame.origin.x;
}

- (void)removeAllSubviews {
    while (self.subviews.count) {
        UIView* child = self.subviews.lastObject;
        [child removeFromSuperview];
    }
}

@end
```
## 作用

1. 将类的实现分散到多个不同文件或多个不同框架中。
2. 创建对私有方法的前向引用。（实现对基类中私有方法（就是没在.h文件中申明）的访问
3. 向对象添加非正式协议。


## 注意

1. 尽管分类可以访问原始类的实例变量，但是它不能添加自身的任何变量。如果需要添加变量，可以考虑创建子类。
2. 分类可以重载该类中的另一个方法，但是通常认为这种做法不可取。因为，重载之后，再不能访问原来的方法。
3. 可以拥有很多分类。
4. 和一般接口部分不同的是，不必实现分类中的所有方法。这对于程序扩展很有用，可以在该分类中声明所有方法，然后在一段时间之后才实现它。
5. 通过使用分类添加新方法来扩展类不仅会影响这个类，同时也会影响它的所有子类。

