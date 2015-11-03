#UITextField

## create
```
-(void)viewDidLoad{
    [super viewDidLoad];

    UIScrollView *sv = [UIScrollView new];
    sv.frame =  CGRectMake(0,0,500,500);
    scrollView.contentSize= CGSize(500,500);
    sv.backgroundColor=[UIColor clearColor];
    sv.showsVerticalScrollIndicator=NO;
    sv.showsHorizontalScrollIndicator=NO;
    sv.scrollEnabled=YES;
    sv.pagingEnabled=YES;    //是否自己动适应
    sv.maximumZoomScale=2.0;
       sv.minimumZoomScale=0.5;

    scrollview.delegate=self;
    scrollview.canCancelContentTouches=NO;
    scrollview.delaysContentTouches=YES;

    sv.bounces = NO;
    [this.view addSubview:sv];
}

#pragma mark UIScrollViewDelegate
//只要滚动了就会触发
- (void)scrollViewDidScroll:(UIScrollView *)scrollView;   
{
    NSLog(@"ContentOffset  x is  %f,yis %f",scrollView.contentOffset.x,scrollView.contentOffset.y);
}
//开始拖拽视图
- (void)scrollViewWillBeginDragging:(UIScrollView *)scrollView;   
{
   NSLog(@"scrollViewWillBeginDragging");
}
//完成拖拽
- (void)scrollViewDidEndDragging:(UIScrollView *)scrollView willDecelerate:(BOOL)decelerate; 
{
   NSLog(@"scrollViewDidEndDragging");
}
//将开始降速时
- (void)scrollViewWillBeginDecelerating:(UIScrollView *)scrollView;   
{
   NSLog(@"scrollViewWillBeginDecelerating");
}

//减速停止了时执行，手触摸时执行执行
- (void)scrollViewDidEndDecelerating:(UIScrollView *)scrollView;   
{
   NSLog(@"scrollViewDidEndDecelerating");
}
//滚动动画停止时执行,代码改变时出发,也就是setContentOffset改变时
- (void)scrollViewDidEndScrollingAnimation:(UIScrollView *)scrollView;
{
   NSLog(@"scrollViewDidEndScrollingAnimation");
}
//设置放大缩小的视图，要是uiscrollview的subview
- (UIView *)viewForZoomingInScrollView:(UIScrollView *)scrollView;   
{
   NSLog(@"viewForZoomingInScrollView");
   return viewA;
}
//完成放大缩小时调用
- (void)scrollViewDidEndZooming:(UIScrollView *)scrollView withView:(UIView *)view atScale:(float)scale; 
{
    viewA.frame=CGRectMake(50,0,100,400);
       NSLog(@"scale between minimum and maximum. called after any 'bounce' animations");
}// scale between minimum and maximum. called after any 'bounce' animations

//如果你不是完全滚动到滚轴视图的顶部，你可以轻点状态栏，那个可视的滚轴视图会一直滚动到顶部，那是默认行为，你可以通过该方法返回NO来关闭它
- (BOOL)scrollViewShouldScrollToTop:(UIScrollView *)scrollView;   
{
    NSLog(@"scrollViewShouldScrollToTop");
       return YES;
}

- (void)scrollViewDidScrollToTop:(UIScrollView *)scrollView;     
{
    NSLog(@"scrollViewDidScrollToTop");
}
```
## 值
```

```
## 属性
```
CGPoint contentOffSet  监控目前滚动的位置
CGSize contentSize      滚动范围的大小
UIEdgeInsets contentInset  视图在scrollView中的位置
id<UIScrollerViewDelegate> delegate  设置协议
BOOL directionalLockEnabled 指定控件是否只能在一个方向上滚动
BOOL bounces         控制控件遇到边框是否反弹
BOOL alwaysBounceVertical   控制垂直方向遇到边框是否反弹
BOOL alwaysBounceHorizontal 控制水平方向遇到边框是否反弹
BOOL pagingEnabled      控制控件是否整页翻动
BOOL scrollEnabled      控制控件是否能滚动
BOOL showsHorizontalScrollIndicator 控制是否显示水平方向的滚动条
BOOL showsVerticalScrollIndicator 控制是否显示垂直方向的滚动条
UIEdgeInsets scrollIndicatorInsets 指定滚动条在scrollerView中的位置
UIScrollViewIndicatorStyleindicatorStyle 设定滚动条的样式
float decelerationRate     改变scrollerView的减速点位置
BOOL tracking              监控当前目标是否正在被跟踪
BOOL dragging              监控当前目标是否正在被拖拽
BOOL decelerating          监控当前目标是否正在减速
BOOL delaysContentTouches     控制视图是否延时调用开始滚动的方法
BOOL canCancelContentTouches  控制控件是否接触取消touch的事件
float minimumZoomScale        缩小的最小比例
float maximumZoomScale       放大的最大比例
float zoomScale              设置变化比例
BOOL bouncesZoom             控制缩放的时候是否会反弹
BOOL zooming                 判断控件的大小是否正在改变
BOOL zoomBouncing            判断是否正在进行缩放反弹
BOOL scrollsToTop            控制控件滚动到顶部

```
## 其他扩展

