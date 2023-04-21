# gplearnplus
升级后的gplearn， 支持包含时序和截面参数的自定义函数，例如均线

# 文件描述

## `_Program.py`

定义，生成树型对象，定义交叉变异方法



## `fitness.py`

定义适应度函数，和自定义适应函数的方法



## `function.py`

自定义函数和构建方法



## `genetic.py`

模型接口，包括由工厂类派生出，回归，分类器和特征工程工具类，应用于不同场景



## `utils.py`

支持函数



`test.py`

自定义函数样例



# 自定义函数文档

## 全局函数

| 函数名          | 实现逻辑         | 参数要求                   | 输出类型     |
| --------------- | ---------------- | -------------------------- | ------------ |
| combine（X, Y） | 拼接两个分类变量 | 【分类变量】，【分类变量】 | 【分类变量】 |





## 时间序列函数



| 函数名        | 实现逻辑       | 参数要求                   | 输出类型     |
| ------------- | -------------- | -------------------------- | ------------ |
| delay（X,d）  | 时序变量滞后   | 【数值变量】，【整形常量】 | 【数值变量】 |
| delta（X,d）  | 与滞后项作差   | 【数值变量】，【整形常量】 | 【数值变量】 |
| ts_min（X,d） | 时间窗口最小值 | 【数值变量】，【整形常量】 | 【数值变量】 |
|               |                |                            |              |
|               |                |                            |              |
|               |                |                            |              |
|               |                |                            |              |
|               |                |                            |              |
|               |                |                            |              |




# 更新记录

## v1.0

未调试完全， 有bug

## v1.1

处理完funtions模块的问题
调试成功，对于时序自定义函数中的常数参数，需要在函数中做去广播判定

## v1.2

test中加入了自定义函数的定义方法，需要忽略运行时的RuntimeWarning

## v1.3

functions中去掉了对于function.__code__.co_argument的限制
增强对函数修饰器的兼容

## v1.4
test.py debug
函数定义考虑特殊参数情况

## v1.5
新增面板数据支持功能
将场景分位截面，时序和面板
数据定义要求更新

函数定义要求更新

更新适应度惩罚计算

修改遗传规划中的特征筛选逻辑
（当最大相关系数绝对值低于某一阈值时，直接按fitness筛选）