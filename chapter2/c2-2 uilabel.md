#UILabel

## create
```
-(void)viewDidLoad{
    [super viewDidLoad];
    UILabel *titleLbl = [UILabel new];
    titleLbl.frame =  CGRectMake(50,2,230,21)
    titleLbl.tag = 100;
    titleLbl.textAlignment = UITextAlignmentLeft;
    titleLbl.backgroundColor = [UIColor clearColor];
    titleLbl.textColor = [UIColor colorWithRed:91.0/255.0 green:47.0/255.0 blue:26.0/255.0 alpha:1.0];
    titleLbl.font = [UIFont fontWithName:kFONT_NAME size:NUM2(14.0f)];
    titleLbl.adjustsFontSizeToFitWidth = YES;
    titleLbl.minimumFontSize = NUM2(8.0f);
    titleLbl.text = NSLocalizedString(b1.title, "Test111");

    titleLbl.highlighted = YES;       
    titleLbl.highlightedTextColor = [UIColor orangeColor];   
    titleLbl.shadowColor = [UIColor redColor];       
    titleLbl.shadowOffset = CGSizeMake(1.0,1.0);  

    titleLbl.lineBreakMode = UILineBreakModeWordWrap;
    titleLbl.numberOfLines = 0;

    [self.view addSubview:titleLbl];
}```
## 值
```
typedef enum {
    UITextAlignmentLeft = 0,左对齐
    UITextAlignmentCenter,居中对齐
    UITextAlignmentRight, 右对齐                 
} UITextAlignment;

typedef enum {       
    UILineBreakModeWordWrap = 0,    以空格为边界，保留整个单词         
    UILineBreakModeCharacterWrap,   保留整个字符         
    UILineBreakModeClip,            到边界为止         
    UILineBreakModeHeadTruncation,  省略开始，以……代替       
    UILineBreakModeTailTruncation,  省略结尾，以……代替      
    UILineBreakModeMiddleTruncation,省略中间，以……代替，多行时作用于最后一行       
} UILineBreakMode;

typedef enum {
    UIBaselineAdjustmentAlignBaselines = 0, 默认值文本最上端于label中线对齐
    UIBaselineAdjustmentAlignCenters,//文本中线于label中线对齐
    UIBaselineAdjustmentNone,//文本最低端与label中线对齐
} UIBaselineAdjustment;
```
## 属性

## 其他扩展


