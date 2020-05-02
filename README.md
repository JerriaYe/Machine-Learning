# Machine-Learning <font color = 'red'> 
A repositoty for machine learning.
https://github.com/MisterBooo/LeetCodeAnimation/tree/master/0001-Two-Sum
## 1.Linear_Regression
### 理解原理
线性回归是一种用于回归问题的最常见的方法。我们可以分别从一般形式以及极大似然方面对其进行理解。
对我个人而言，一般形式更有助于直观理解[多个因变量共同造成了某个自变量]的结果这一理论。而通过极大似然估计的推导，则可以知道为什么线性回归的代价函数是均方误差。因为最大化似然函数（求取使得某种结果出现的最大概率值）其实就可以变换为最小化真实值与预测值的均方误差。
### 损失函数、代价函数、目标函数的定义与区别
其代价函数是真实值与预测值的均方误差。

损失函数(Loss Function)：度量单样本预测的错误程度，损失函数值越小，模型就越好。
代价函数(Cost Function)：度量全部样本集的平均误差。
目标函数(Object Function)：代价函数和正则化函数，最终要优化的函数。
### 优化方法
优化方法有：（1）最小二乘估计法求模型的最优参数。（2）梯度下降法。（3）（拟）牛顿法。

本次利用sklearn.linear_model库中的LinearRegression模型用于回归预测。以便加深理解。

## 2.Naive_Bayes
### 理解原理
贝叶斯方法是一种最典型的生成模型，即根据先验概率和联合概率分布，求得造成某个果的某个因的后验概率的多少。另外一种典型的生成模型是隐马尔科夫模型。

**后验概率**: 在贝叶斯统计中，一个随机事件或者一个不确定事件的后验概率是在考虑和给出相关证据或数据后所得到的条件概率。同样，后验概率分布是一个未知量（视为随机变量）基于试验和调查后得到的概率分布。“后验”在本文中代表考虑了被测试事件的相关证据。
后验概率，就是在知道“果”之后，去推测“因”的概率，也就是说，如果已经知道瓜是好瓜，那么瓜的颜色是青绿的概率是多少。后验和先验的关系就需要运用贝叶斯决策理论来求解。

### 贝叶斯公式
P(c|x) = P(x,c)/P(x)= {P(c) *P(x|c)}/P(x)

最大似然估计是一种“模型已定，参数未知”的方法。

### 优缺点
优点

朴素贝叶斯模型有稳定的分类效率。
对小规模的数据表现很好，能处理多分类任务，适合增量式训练，尤其是数据量超出内存时，可以一批批的去增量训练。
对缺失数据不太敏感，算法也比较简单，常用于文本分类。
缺点:

理论上，朴素贝叶斯模型与其他分类方法相比具有最小的误差率。但是实际上并非总是如此，这是因为朴素贝叶斯模型给定输出类别的情况下,假设属性之间相互独立，这个假设在实际应用中往往是不成立的，在属性个数比较多或者属性之间相关性较大时，分类效果不好。而在属性相关性较小时，朴素贝叶斯性能最为良好。对于这一点，有半朴素贝叶斯之类的算法通过考虑部分关联性适度改进。
需要知道先验概率，且先验概率很多时候取决于假设，假设的模型可以有很多种，因此在某些时候会由于假设的先验模型的原因导致预测效果不佳。
由于我们是通过先验和数据来决定后验的概率从而决定分类，所以分类决策存在一定的错误率。
对输入数据的表达形式很敏感。

## 3.EM算法
### 原理
概率模型有时候既含有观测变量，又含有隐变量或潜在变量，如果概率模型的变量都是观测变量，那么给定数据，可以直接用极大似然估计法，或贝叶斯估计方法估计模型参数，但是当模型含有隐变量时，就不能简单的使用这些方法，EM算法就是含有隐变量的概率模型参数的极大似然估计法，或极大后验概率估计法，我们讨论极大似然估计，极大后验概率估计与其类似。
EM算法是机器学习十大算法之一，它很简单，但是也同样很有深度，简单是因为它就分两步求解问题，
E步：求期望（expectation）
M步：求极大（maximization)
### 代码
代码演示EM.ipynb所示，以便加深理解。

## 4.CRF
### 原理
条件随机场是给定一组输入随机变量条件下另一组输出随机变量的条件概率分布模型，其特点是假设输出随机变量构成马尔科夫随机场。
条件随机场可以用于不同的预测问题，标注问题是其常见的应用。
线性链条件随机场是最普遍的。此时，问题变成了由输入序列对输出序列预测的判别模型，形式为对数线性模型。其学习方法通常都是极大似然估计或者正则化的极大似然估计。
### 代码
代码演示CRF.ipynb所示，以便加深理解。

## 5.svm
### 原理
支持向量机是一种二类分类模型，它的基本模型是定义在特征空间上的间隔最大的线性分类器，间隔最大使它有别于感知机；支持向量机还包括核技巧，这使它成为实质上的非线性分类器。支持向量机的学习策略是间隔最大化，可形式化为一个求解凸二次规划的问题，也等价于正则化的合页函数的最小化问题。
### 模型
1.线性可分支持向量机：训练数据线性可分的时候，通过硬间隔最大化学习一个线性的分类器。

2.线性支持向量机：训练数据近似线性可分时，通过软间隔最大化，学习一个线性分类器。

3.非线性支持向量机：训练数据线性不可分时，通过使用核技巧以及软间隔最大化。

