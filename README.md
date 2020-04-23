# Machine-Learning
A repositoty for machine learning.

## 1.Linear_Regression
#### 理解原理
线性回归是一种用于回归问题的最常见的方法。我们可以分别从一般形式以及极大似然方面对其进行理解。
对我个人而言，一般形式更有助于直观理解[多个因变量共同造成了某个自变量]的结果这一理论。而通过极大似然估计的推导，则可以知道为什么线性回归的代价函数是均方误差。因为最大化似然函数（求取使得某种结果出现的最大概率值）其实就可以变换为最小化真实值与预测值的均方误差。
#### 损失函数、代价函数、目标函数的定义与区别
其代价函数是真实值与预测值的均方误差。

损失函数(Loss Function)：度量单样本预测的错误程度，损失函数值越小，模型就越好。
代价函数(Cost Function)：度量全部样本集的平均误差。
目标函数(Object Function)：代价函数和正则化函数，最终要优化的函数。
#### 优化方法
优化方法有：（1）最小二乘估计法求模型的最优参数。（2）梯度下降法。（3）（拟）牛顿法。

本次利用sklearn.linear_model库中的LinearRegression模型用于回归预测。以便加深理解。

## 2.Naive_Bayes
### 理解原理
贝叶斯方法是一种最典型的生成模型，即根据先验概率和联合概率分布，求得造成某个果的某个因的后验概率的多少。另外一种典型的生成模型是隐马尔科夫模型。
### 贝叶斯公式
$$P(c|x) = \frac{P(x,c)}{P(x)} = \frac{P(c) P(x|c)}{P(x)}$$
最大似然估计是一种“模型已定，参数未知”的方法。

