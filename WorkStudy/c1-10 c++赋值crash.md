### c++赋值Crash

#### 问题描述
- 平台:cocosx
- 语言:c++
- 在给C++对象赋值的时候，crash

#### 解决思路
- 对象赋值时，确保对象先初始化,nullptr
- 对象释放时，清空nullptr



