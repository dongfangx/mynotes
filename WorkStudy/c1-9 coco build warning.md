### coco build extern_c warning

#### 问题描述
- 平台:cocosx
- 语言:c++
- module warning: unknown attribute 'extern_c' [-Wignored-attributes]

#### 解决思路
- 打开JNI下面 Application.mk
- 删除NDK_TOOLCHAIN_VERSION=clang
