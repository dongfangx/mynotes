#UIViewController

## create
```
- (void)loadView
{
    CGRect frame = [[UIScreen mainScreen] bounds];
    self.view = [UIView new];
    self.view.frame = CGRectMake(0, 0, frame.size.height, frame.size.width);
}
```
## 加载顺序
1. alloc
2. init (initWithNibName)
3. loadView
4. viewDidLoad
5. viewWillAppear
6. viewDidAppear
## 销毁顺序
1. viewWillDisappear
2. viewDidDisappear
3. dealloc


