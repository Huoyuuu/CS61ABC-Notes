- [Scheme](#scheme)
  - [概述](#概述)
  - [文件](#文件)
  - [具体实现](#具体实现)
  - [总结](#总结)
    - [项目总结](#项目总结)
    - [我学到了什么](#我学到了什么)


# [Scheme](https://inst.eecs.berkeley.edu/~cs61a/su20/proj/scheme)

## 概述
用Python实现Scheme解释器。

支持以下功能：
- Read：读入用户输入的Scheme语句。这一步会进行词法分析和语法分析。
- Load：从文件中载入Scheme代码。
- Eval：计算Scheme表达式的值。
- Turtle Graphics：借助Python的Turtle库实现的绘图功能。
- Print：打印输出。
- Loop：提供循环功能。
- Exceptions：提供异常处理功能。

## 文件
- scheme.py: 实现命令行交互和表达式求值功能
- scheme_reader.py: 实现读取Scheme语句功能
- scheme_tokens.py: 获取读入Scheme语句的token
- scheme_builtins.py: 实现Scheme库文件
- buffer.py: 实现Buffer类，在scheme_reader.py中调用
- ucb.py: 61A项目的功能函数
- questions.scm: 第三部分的骨架代码
- tests.scm: Scheme写的测试文件
- ok: ok评测系统
- tests: 测试文件夹
- mytests.rst: 自己的测试文件

## 具体实现

## 总结

### 项目总结

### 我学到了什么