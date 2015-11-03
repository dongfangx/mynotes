#UIImageView

## create
```
-(void)viewDidLoad{
    [super viewDidLoad];
     UIImageView *imageView = [UIImageView new];
    imageView.frame = CGRectMake(473,181,1318,128);
    imageView.contentMode = UIViewContentModeScaleAspectFit;
    imageView.image = [UIImage imageNamedTKPNG:@"main_light"];

    //点击
    imageView.userInteractionEnabled = YES;
    UITapGestureRecognizer *singleTap = [UITapGestureRecognizer new];
    [singleTap addTarget:self action:@selector(tapImageView:)];
    [imageView addGestureRecognizer:singleTap];

    //圆角
    CALayer *lay  = faceImg.layer;//获取ImageView的层 
    [lay setMasksToBounds:YES]; 
    [lay setCornerRadius:3.0];//值越大，角度越圆

    //帧动画
    NSMutableArray *bflies = [NSMutableArray array]; 

    for (int i = 1; i <= 3; i++) { 
        [bflies addObject:[UIImage imageWithContentsOfFile: 
                           [[NSBundle mainBundle] pathForResource: 
                            [NSString stringWithFormat:@"1%d",i] ofType:@"png"]]]; 
    } 
    imageView.animationImages = bflies; 
    imageView.animationDuration = 1.0f;  设置动画时间 
    [imageView startAnimating]; 

    [self.view addSubview:imageView];
}

//图片合并/还可以合成
-(UIImage *)addImage:(UIImage *)image1 toImage:(UIImage *)image2
{
    UIGraphicsBeginImageContext(image2.size);
    //Draw image2
    [image2 drawInRect:CGRectMake(0, 0, image2.size.width, image2.size.height)];
    //Draw image1
    [image1 drawInRect:CGRectMake(20, 20, image1.size.width, image1.size.height)];
    UIImage *resultImage=UIGraphicsGetImageFromCurrentImageContext();
    UIGraphicsEndImageContext();
    return resultImage;
}
```
## 值
```
```
## 属性
```
imageView.hidden = YES或者NO;    // 隐藏或者显示图片
imageView.alpha = (CGFloat) al;    // 设置透明度
imageView.highlightedImage = (UIImage *)hightlightedImage;     // 设置高亮时显示的图片
imageView.image = (UIImage *)image;    // 设置正常显示的图片
[imageView sizeToFit];    // 将图片尺寸调整为与内容图片相同

stretchableImageWithLeftCapWidth
```

## 其他扩展
[图片拉伸，微博气泡效果](http://my.oschina.net/zhangzhihao/blog/72173)
[扩展UIImageViewEx实现](http://www.oschina.net/question/213217_45564)

