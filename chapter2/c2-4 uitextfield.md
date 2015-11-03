#UITextField

## create
```
-(void)viewDidLoad{
    [super viewDidLoad];

    UITextField *txt = [UITextField new];
    txt.frame =  CGRectMake(85.0f, 60.0f, 190.0f, 40.0f);
    [txt setBorderStyle:UITextBorderStyleRoundedRect]; //外框类型
    txt.placeholder = @"用户名"; //默认显示的字
    txt.secureTextEntry = NO; //是否以密码形式显示

    txt.autocorrectionType = UITextAutocorrectionTypeNo;／／设置是否启动自动提醒更正功能
    txt.autocapitalizationType = UITextAutocapitalizationTypeNone;
    txt.returnKeyType = UIReturnKeyDone;  ／／键盘返回类型
    txt.clearButtonMode = UITextFieldViewModeWhileEditing; //编辑时会出现个修改X
    txt.delegate = self;
    txt.keyboardType = UIKeyboardTypeDefault;／／键盘显示类型
    txt.contentVerticalAlignment = UIControlContentVerticalAlignmentCenter; ／／设置居中输入
    txt.scrollEnabled = YES;//是否可以拖动 www.2cto.com
    txt.autoresizingMask = UIViewAutoresizingFlexibleHeight;//自适应高度
    txt.keyboardAppearance=UIKeyboardAppearanceDefault;//键盘外观
    [txt becomeFirstResponder];

    [self.view addSubview:txt];
}

- (BOOL)textFieldShouldReturn:(UITextField *)textField { 
    [textField resignFirstResponder];
    return YES;
}
```
## 值
```
typedef enum {
    UITextBorderStyleNone, 
    UITextBorderStyleLine,
    UITextBorderStyleBezel,
    UITextBorderStyleRoundedRect  
} UITextBorderStyle;

typedef enum {
    UITextFieldViewModeNever,　重不出现
    UITextFieldViewModeWhileEditing, 编辑时出现
    UITextFieldViewModeUnlessEditing,　除了编辑外都出现
    UITextFieldViewModeAlways 　一直出现
} UITextFieldViewMode;

typedef enum {
    UITextAutocorrectionTypeDefault, 默认
    UITextAutocorrectionTypeNo, 　不自动纠错
    UITextAutocorrectionTypeYes,　自动纠错
} UITextAutocorrectionType;
```
## 属性
```
```
## 其他扩展

