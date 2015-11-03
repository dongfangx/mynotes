#UITextField

## create
```
-(void)viewDidLoad{
    [super viewDidLoad];

    UIDatePicker *datePicker = [[UIDatePicker alloc] initWithFrame:CGRectMake(0, 200, 320, 216)];
    // 设置时区
    [datePicker setTimeZone:[NSTimeZone timeZoneWithName:@"GMT"]];
    // 设置当前显示时间
    [datePicker setDate:tempDate animated:YES];
    // 设置显示最大时间（此处为当前时间）
    [datePicker setMaximumDate:[NSDate date]];
    // 设置UIDatePicker的显示模式
    [datePicker setDatePickerMode:UIDatePickerModeDate];
    // 当值发生改变的时候调用的方法
    [datePicker addTarget:self action:@selector(dateChanged:) forControlEvents:UIControlEventValueChanged];
    [self.view addSubview:datePicker];

    //NSDate *select = [datePicker date];  
}

-(void)dateChanged:(id)sender  
{  
    UIDatePicker *control = (UIDatePicker*)sender;  
    NSDate *date = control.date;  
    NSDateFormatter *dateFormatter = [[NSDateFormatter alloc]init];  
    [dateFormatter setDateFormat:@"yyyy-MM-dd HH:mm:ss"];  
    NSString *strDate = [dateFormatter stringFromDate:date];      
}
```
## 值
```
typedef enum {  
 UIDatePickerModeDateAndTime,
    UIDatePickerModeTime,            
    UIDatePickerModeDate,            
    UIDatePickerModeCountDownTimer    
} UIDatePickerMode;
```
## 属性
```
```
## 其他扩展
## 详细见文档

