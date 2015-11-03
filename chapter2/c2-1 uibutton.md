#UIButton

## create
```
-(void)viewDidLoad{
    [super viewDidLoad];
    UIButton *button = [UIButton buttonWithType:UIButtonTypeRoundedRect];
    [button setBackgroundImage:normalImage forState:UIControlStateNormal];
    [button setBackgroundImage:selectedImage forState:UIControlStateHighlighted];
    [button setBackgroundImage:selectedImage forState:UIControlStateSelected];
    [button addTarget:self action:@selector(theButtonClick) forControlEvents:UIControlEventTouchDown];
    [button setTitle:@"Login" forState:UIControlStateNormal];              
    button.titleLabel.font = [UIFont fontWithName:@"helvetica" size:12];

    button.exclusiveTouch=YES;
    button.tag = 101;
    button.backgroundColor = [UIColor clearColor];
    button.frame = CGRectMake(80.0, 210.0, 160.0, 40.0);

    button.layer.cornerRadius = 5.0f; 圆角半径
    button.layer.masksToBounds = YES; 圆角
    button.layer.borderWidth = 0.5f; 边框宽度
    button.layer.borderColor = [[UIColor grayColor]CGColor]; 

    [self.view addSubview:button];
}

-(void)theButtonClick:(id)sender{
}
```
## 值
```
typedef enum {
    UIButtonTypeCustom = 0, 自定义风格
    UIButtonTypeRoundedRect, 圆角矩形 
    UIButtonTypeDetailDisclosure, 蓝色小箭头按钮，主要做详细说明用
    UIButtonTypeInfoLight, 亮色感叹号
    UIButtonTypeInfoDark, 暗色感叹号
    UIButtonTypeContactAdd, 十字加号按钮
} UIButtonType;

forState:
typedef enum {
    UIControlStateNormal = 0, 常规状态显现 
    UIControlStateHighlighted = 1 << 0, 高亮状态显现 
    UIControlStateDisabled = 1 << 1, 禁用的状态才会显现
    UIControlStateSelected = 1 << 2, 选中状态 
    UIControlStateApplication = 0x00FF0000, 当应用程序标志时 
    UIControlStateReserved = 0xFF000000 为内部框架预留，可以不管他 
};
```
## 属性
1. showsTouchWhenHighlighted //按下会发光
2. tintColor
3. imageEdgeInsets
4. adjustsImageWhenHighlighted

## 其他扩展
[UIButton添加Block](http://www.oschina.net/question/1861864_160550)
[创建非正规形状按钮](http://my.oschina.net/makeffort/blog/86807)
[UIButton-Bootstrap](https://github.com/OskarGroth/UIButton-Bootstrap)


