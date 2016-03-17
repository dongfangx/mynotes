### python utf-8问题

#### C++11 新的回调，function方式
- 问题描述: 
    执行python脚本的时候，出现
    raise ValueError, 'unknown locale: %s' % localename
- 解决方案
    termianl中，运行 export LC_CTYPE="en_US.UTF-8"


#### Termianl中权限问题
- 问题描述: 
	Terminal中，输入./cocos.py....创建项目时，出现Permission denied
- 解决方案
    chmod u+x ./cocos.py




