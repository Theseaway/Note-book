# Cmake 笔记
参考链接 https://www.hahack.com/codes/cmake/
## 自定义编译选项
CMake允许为项目增加编译选项，如果该选项为 ON，就使用该库定义的数学函数来进行运算。

在Cmake中加入一个配置头文件，用于处理CMake对源码的设置，注意，下面声明字configure_files后接的是()

    configure_file(
        "${PROJECT_SOURCE_DIR}/config.h.in",
        "${PROJECT_BINARY_DIR}/config.h"
    )

是否使用自己的MathFunction库，并在此处声明USE_MYMATH时
option(USE_MYMATH
       "Use provided math implementation" ON)

是否加入MathFunction库

    if(USE_MYMATH)
    