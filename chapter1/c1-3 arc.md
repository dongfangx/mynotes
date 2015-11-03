#内存管理

## MRC 

```
@property(nonatomic,retain)UIImageView *questIV;
self.questIV = [[[UIImageView alloc] init] autorelease];
```

## ARC
```
UIImageView *iv＝ [UIImageView new];
```
## ARC备注

1. arc的设置是在build phases中修改compiler Flags的值
2. 不可以使用retain, release,autorelease
3. 在@property声明中，用strong和weak代替相应的retain, copy,和assign。
4. 用@autoreleasepool 块代替 NSAutoReleasePool

