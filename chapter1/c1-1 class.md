#类文件定义

## 头文件 MyTest.h

```
/*
类头文件定义：
*/
#import <Foundation/Foundation.h>   //<> 系统类
#import "my.h"                      //"" 自定义类

@protocol MyDelegate <NSObject>
@required                           //必须实现
- (void)onDo2:(int)num;
@optional                           //可选
- (void)onDo:(int)num;
@end

@class Room;                        // 效率高
@interface MyTest : NSObject<RoomDeleate>
{
    @private
    int num; 

    @protected
    BOOL isOK;

    @public
    NSString *str1;    
}

typedef void (^FinishBlock)(NSString *dataString);

@property (strong, nonatomic) FinishBlock finishBlock;
@property(nonatomic,weak)id<MyDelegate> delegate;  //id
@property (nonatomic,strong)Room *currRoom; 
//nonatomic|atomic
//strong|retain,copy
//weak|assign
//readwrite|readonly

+ (MyTest*) shareMy();                  //静态方法
- (void) print;
- (void) setNum:(int)n;
- (int)goWork:(int)movieId shopIndex:(int)shopIndex;
+ (void)postRequestWithURL:(NSString *)urlStr
              finshedBlock:(FinishBlock)block;

@end
```

## 实现文件 MyTest.m

```
//类头文件定义：
#import "MyTest.h"
#import "Room.h"

@implementation MyTest

@synthesize delegate;
@synthesize currRoom;

static MyTest *instance = nil;

- (id) init
{
    self = [super init];            //super父类
    if (self) {
        num = 100;
        isOK = TRUE;                //TRUE/FALSE
    }

    return self;
}

+ (MyTest*) shareMy()
{
    if (instance == nil) {
        instance = [MyTest new];
    }
    return instance;
}

-(void) print
{
    NSLog(@"%i/%i",numerator,denominator);

    MyTest *test1 = [MyTest new];

    [test1 setValue:1 forKey:num];      //kVC

    [self performSelector:@selector(goWork:shopIndex:) 
        withObject:1 withObject:2];
    if(self.delegate && [self.delegate respondsToSelector:@selector(onDo:)])
    {
        [self.delegate onDo:1];
    }

    [MyTest postRequestWithURL:@"http://www.baidu.com"
                       finshedBlock:^(NSString *dataString) {
                           NSLog(@"finish callback block, result: %@", dataString);
    }];
}

- (void) setNum:(int)n
{
    num = 1;
}

- (int) goWork:(int)movieId shopIndex:(int)shopIndex
{
    [self performSelector:@selector(print)];
    [self performSelector:@selector(setNum:) withObject:1];
    return moviedId + shopIndex;
}

@end
```

## 调用

```
//Fraction *fraction = [[Fraction alloc] init];
Fraction *fraction = [Fraction new];
[fraction print];
[fraction setNum:1];
int rtn = [fraction goWork:1 shopIndex:2];
```

## 常用方法

```
Class c1 = [Fraction class];
Class c2 = [Fraction superclass];
Class c3 = NSClassFromString("Fraction");
NSString *name = NSStringFromClass([Fraction class]);
```
