- [Hog](#hog)
  - [概述](#概述)
  - [文件](#文件)
  - [具体实现](#具体实现)
    - [Simulator模拟](#simulator模拟)
    - [Commentary解说](#commentary解说)
    - [Strategies策略](#strategies策略)
  - [总结](#总结)
    - [项目小结](#项目小结)
    - [我学到了什么](#我学到了什么)

# [Hog](https://inst.eecs.berkeley.edu/~cs61a/su20/proj/hog/)

## 概述
Hog是一种传统的骰子游戏。玩家轮流掷骰子并根据特定的规则来计分。玩家可以根据骰子的点数来选择不同的策略，以最大化自己的得分并阻止对手得分。这种类型的游戏可以通过一些变体和自定义规则进行调整，以增加挑战和趣味性。

在Su20中，总分为100，分值先到100的人获胜。

具体规则有四类：
1. Pig Out：每个用户选择投0~10个骰子，本轮分值取骰子总和，但是骰子中任何一个是1，那么计分为1。
2. Free Bacon：用户投0个骰子，得分 10 - 对手分数的个位数 + 对手分数的十位数。
3. Feral Hogs：用户投 上轮得分±2 个骰子，获得额外3分。
4. Swine Swap：当轮结束后，如果双方个位数差的绝对值 == 对手分数的十位数，那么两方分值互换。


规则比较复杂，按顺序具体阐释一下。

```python
先投骰子，
如果投骰子数目 == 0，那么得分 10 - 对手个位数 + 对手十位数。
如果存在一个骰子结果为1，那么得分 1，否则得分为骰子数值之和。
如果投骰子数目 == 上轮得分 ±2，那么额外 +3分。

然后和对手分数进行比较。
如果 abs(自己个位数-对手个位数) == 对手十位数，那么两方分值互换。

至此当轮结束。
```

## 文件
- hog.py: Hog文件的具体实现
- dice.py: 骰子文件
- hog_gui.py: GUI文件
- ucb.py: 61A函数
- ok: ok评测系统
- tests: 测试文件夹
- gui_files: GUI文件夹

## 具体实现

分为三个部分

### Simulator模拟
在hog.py中模拟游戏流程，实现完整项目。

核心思路还是前面对规则的具体阐释，将语言叙述转化为Python代码即可。

注意运用高阶函数、代码复用等规则，提高代码可读性、可维护性和运行效率等即可。
```python
先投骰子，
如果投骰子数目 == 0，那么得分 10 - 对手个位数 + 对手十位数。
如果存在一个骰子结果为1，那么得分 1，否则得分为骰子数值之和。
如果投骰子数目 == 上轮得分 ±2，那么额外 +3分。

然后和对手分数进行比较。
如果 abs(自己个位数-对手个位数) == 对手十位数，那么两方分值互换。

至此当轮结束。
```

### Commentary解说
在模拟过程中添加debug信息，用于具体解说。

主要目的是让开发者熟悉给项目增加调试信息的流程。这里最值得称道的就是高阶函数的运用，将中间变量放在函数内部，调用时不必有额外的变量开销。

### Strategies策略
制定AI策略，支持单人游戏。

规则是公开透明的，本质上是蒙特卡洛原理，通过多次模拟取最优解。

## 总结

### 项目小结
毕竟是CS61A的第一个项目，本身偏向大模拟但难度不大，更多是熟悉开发过程。

包括：
1. 理解项目需求，根据需求制定流程。
2. 把大需求拆分成小任务，逐个去处理。
3. 函数抽象的思想，函数内每个函数只做一件事，函数外复用代码通过调用函数解决。
4. 给项目添加Debug信息。
5. 通过模拟取最优解，实现游戏AI的思想。
   
### 我学到了什么
我在这个项目中学到的最有价值的事情，就是开发前先写项目文档  +  开发时结合代码文档去处理。文档比较全面的项目中，出现问题的一般解决方案就是读文档和改文档。

具体来说，包括绘制项目的流程图，总共分为哪些部分，分别起什么作用。确定每一部分需要用到的函数、函数的输入输出（具体实现可以等之后完成）等。之前打算法竞赛时候有过在写代码前，考虑好有哪些变量，起什么作用等等，写之前会花很长时间，但是写的时候会很顺畅，即使中间出了什么问题，大框架也是定好的，只需要小范围更改就可以解决问题，也便于后续维护。

需要指出的是，这里并不是说“可以先不写文档，只是写文档可以做得更好”，而是“做项目是一定要写项目文档的”，即使现在没有写文档，做规划，也开始去做了，到后面也总归是要补起来的。最怕最怕的就是做了一多半，结果回头一看做的不对，方向就错了。又得回头规划又浪费了时间，得不偿失。而如果提前有文档（哪怕是很简陋的大纲），也有可以作为参照的框架，不论是修改还是增删功能都会方便许多。

> 马克思在《资本论》第一卷里写道：“我们不谈最初的动物式的本能的劳动形式。……我们要考察的是专属于人的劳动。蜘蛛的活动与织工的活动相似，蜜蜂建筑蜂房的本领使人间的许多建筑师感到惭愧。但是，最蹩脚的建筑师从一开始就比最灵巧的蜜蜂高明的地方，是他在建筑蜂房以前，已经在自己的头脑中把它建成了。劳动过程结束时得到的结果，在这个过程开始时就已经在劳动者的表象中存在着，即已经观念地存在着。他不仅使自然物发生形式变化，同时他还在自然物中实现自己的目的，这个目的是他所知道的，是作为规律决定着他的活动的方式和方法的，他必须使他的意志服从这个目的。”