## Ch01

### exercise 1.2

#### 思路：

此题借鉴上一问的解法，只是在损失函数那里加上了一个正则项。对应的矩阵形式求导方面要注意**自身函数内积求导要乘以一个单位矩阵** 及$\frac{ \partial w^{T}w }{ \partial w }=Iw$ 之后用求和形式表示即可

![1675650347205](E:/%E7%BE%8E%E8%B5%9B/%E7%BE%8E%E8%B5%9B%E8%B5%9B%E9%A2%98/prml-master/prml-master/chapter01/exercise_img/1675650347205.jpg)

