#UITextField

## create
```
-(void)viewDidLoad{
    [super viewDidLoad];

    UIPickerView *pickerView = [UIPickerView new];
    pickerView.frame = CGRectMake(0, 0, 320, 216);
    pickerView.delegate=self;  
    pickerView.datasource=self;
    pickerView.showsSelectionIndicator=YES;  
    [self.view addSubview:pickerView];  

    pickerData = [[NSArray alloc] initWithObjects:@"许嵩",@"周杰伦",@"林俊杰", nil];
}

#pragma mark -  
#pragma mark Picker Date Source Methods  

//返回显示的列数  
-(NSInteger)numberOfComponentsInPickerView:(UIPickerView *)pickerView  
{  
    return 1;  
}  
//返回当前列显示的行数  
-(NSInteger)pickerView:(UIPickerView *)pickerView numberOfRowsInComponent:(NSInteger)component  
{  
    return [pickerData count];  
}   
//返回当前行的内容,此处是将数组中数值添加到滚动的那个显示栏上  
-(NSString*)pickerView:(UIPickerView *)pickerView titleForRow:(NSInteger)row forComponent:(NSInteger)component  
{  
    return [pickerData objectAtIndex:row];  
}
```
## 值
```
```
## 属性
```
```
## 其他扩展
## 详细见文档

