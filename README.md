- [总览](#总览)
  - [CS61A](#cs61a)
    - [Proj](#proj)
      - [Hog](#hog)
        - [规则](#规则)
        - [要点](#要点)
        - [具体安排](#具体安排)
      - [Cats](#cats)
        - [要点](#要点-1)
        - [具体安排](#具体安排-1)
      - [Ants](#ants)
        - [要点](#要点-2)
        - [具体安排](#具体安排-2)
      - [Scheme](#scheme)
        - [实现内容](#实现内容)
        - [要点](#要点-3)
        - [具体安排](#具体安排-3)
  - [**笔记不涉及Lab和Project的代码部分**](#笔记不涉及lab和project的代码部分)


# 总览

**CS61ABC系列课程笔记，后续补充中**

> CS61A: <https://inst.eecs.berkeley.edu/~cs61a/su20/>
>
> CS61B:
>
> <https://sp18.datastructur.es/>
>
> <https://sp21.datastructur.es/>
>
> CS61C: <https://inst.eecs.berkeley.edu/~cs61c/su20/>

## CS61A

### Proj

#### [Hog](./CS61A/Proj/01%20Hog.md)
一种传统的骰子游戏。玩家轮流掷骰子并根据特定的规则来计分。玩家可以根据骰子的点数来选择不同的策略，以最大化自己的得分并阻止对手得分。这种类型的游戏可以通过一些变体和自定义规则进行调整，以增加挑战和趣味性。

##### 规则
```python
先投骰子，得分为骰子之和。但是：
如果投骰子数目 == 0，那么得分 10 - 对手个位数 + 对手十位数。
如果存在一个骰子结果为1，那么得分 1。
如果投骰子数目 == 上轮得分 ±2，那么额外 +3分。

然后和对手分数进行比较。
如果 abs(自己个位数-对手个位数) == 对手十位数，那么两方分值互换。

至此当轮结束。
```
##### 要点
1. 利用函数将功能进行分块处理。
2. Python高阶函数的应用。

##### 具体安排
1. 根据项目文档和测试案例完成项目。
2. 给项目添加DEBUG信息。
3. 根据蒙特卡洛模拟方法制定策略，实现单机版AI。

#### [Cats](./CS61A/Proj/02%20Cats.md)
本质上是打字软件，单机版本提供测速 + 自动更正功能，联机版本提供联机对战功能。

CS61A的第二个项目，难度和复杂度都并不是很大。

##### 要点
1. 递归思路解决问题
2. 使用Cache提高运行效率
3. 考虑输入输出设备，如用户键盘为QWERTY键盘，可据此优化代码自动更正功能。

##### 具体安排
1. 计算wpm，实现测速功能。
2. 将给定单词与数据库中单词比对，实现自动更正功能。
3. 向服务器发送数据，实现客户端功能。

#### [Ants](./CS61A/Proj/03%20Ants.md)

##### 要点
1. 利用OOP思想完成较为复杂的项目。
2. 添加新类型子类时，到基类中做修改，并在子类中集成+重写。
3. 具体的判断逻辑，各模块可自己解决时，就不必在全局中做统一处理了。

##### 具体安排
1. 基于链表思想构建整片地图
2. 基于继承+重写思想构建Ants
3. 稍复杂的逻辑判断，实现Container类
4. 实现新类型的地图和新类型的Ants

#### [Scheme](./CS61A/Proj/04%20Scheme.md)

##### 实现内容

##### 要点

##### 具体安排

Notes，讲求简明扼要，切忌照抄正文（Lab和Proj部分有大体思路，但是不包含代码）

怎么做？重点是搞清楚来龙去脉，细分如下：

- 遇到了什么问题？
- 提出了哪些办法？
- 具体表现是怎么样的？有哪些示例？（代码框内体现）
  
- 还可以解决什么问题？实际使用情况是怎样的？
  
文末回顾： 我学到了什么、如何学会的、可以怎样类推出去

## **笔记不涉及Lab和Project的代码部分**
