#UITextField

## create
```
-(void)viewDidLoad{
    [super viewDidLoad];

    UIAlertView *alert = [[UIAlertView alloc]initWithTitle:@"提示"
                        message:@"这是一个简单的警告框" 
                        delegate:nil
                        ancelButtonTitle:@"确定"
                        otherButtonTitles:nil];
                        [alert show];
    [alert show];

    UIAlertView *alert2 = [[UIAlertView alloc]initWithTitle:@"提示"
                        message:@"请选择一个按钮："
                        delegate:self
                        cancelButtonTitle:@"取消"
                        otherButtonTitles:@"按钮一", @"按钮二", @"按钮三",nil];  
    [alert2 show];    

    UIAlertView * alert3 = [[UIAlertView alloc]initWithTitle:@"CD-KEY"
                        message:@"please enter cd-key："
                        delegate:self
                        cancelButtonTitle:@"Cancel"
                        otherButtonTitles:@"Ok",nil];  
    [alert3 setAlertViewStyle:UIAlertViewStyleLoginAndPasswordInput];
    UITextField * text1 = [alert3 textFieldAtIndex:0];
    UITextField * text2 = [alert3 textFieldAtIndex:1];
    text1.keyboardType = UIKeyboardTypeNumberPad;
    text2.keyboardType = UIKeyboardTypeNumbersAndPunctuation;
    [alert3 show];
}

- (void)alertView:(UIAlertView *)alertView clickedButtonAtIndex:(NSInteger)buttonIndex
{

}
```
## 值
```
typedef enum {
    UIAlertViewStyleDefault = 0,
    UIAlertViewStyleSecureTextInput,
    UIAlertViewStylePlainTextInput,
    UIAlertViewStyleLoginAndPasswordInput
} UIAlertViewStyle;
```
## 属性
```
```
## 其他扩展
[自定义UIAlertView样式](http://blog.csdn.net/toss156/article/details/7552075)
