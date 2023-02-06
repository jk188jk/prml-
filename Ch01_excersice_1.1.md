## Ch01

### exsercise 1.1

#### 解：

由题所知

1. $y(x,y)=\sum_{j=0}^{M}w_{j}\cdot x^{j}$ (预测函数)

​			$\qquad =\sum_{j=0}^{M}x^{j}\cdot w_{j}$ （要求的最优解为$w$）

视 $\vec w^{T}=[w_{1},w_{2},...,w_{M}]_{1 \times M}$ 

​	$\quad \vec x=[x_{1},x_{2},...,x_{M}]_{1 \times M}$ 

则$y(x,w)=x^{T}\cdot w$

2. $E(w)=\frac{1}{2}\sum_{n=0}^{N}[y(x_{n},w)-t_{n}]^{2}$ (损失函数)

   视，原式化为向量二范数的平方

   则，
   $$
   \begin{equation}
   \begin{aligned}
   &
   \mbox{视}
   \qquad
   A
   =
   \left[
   \begin{array}{ccc}
       x_{1}^{T} \\
       x_{2}^{T} \\
       x_{3}^{T}
   \end{array}
   \right]_{N\times M}\mbox{为观测矩阵}\\
   & \mbox{视}\qquad
   \vec t_{n}=
   \left[
   \begin{array}{c}
       t_{1} \\ 
       t_{2} \\
       t_{3}
   \end{array}
   \right]_{N\times 1}\quad\mbox{为观测结果}
   \end{aligned}
   \end{equation}
   $$
   

则
$$
\begin{equation}
\begin{aligned}
E(w) & =\frac{1}{2}\Vert A\vec w-\vec t_{n} \Vert_2^{2}\\&=\frac{1}{2}(Aw-t_{n})^{T}(Aw-t_{n})\\&=\frac{1}{2}(w^{T}A^{T}-t_{n}^{T})(Aw-t_{n})\\&=\frac{1}{2}(w^{T}A^{T}Aw-w^{T}A^{T}t_{n}-t_{n}^{T}Aw+t_{n}^{T}t_{n})\\&=\frac{1}{2}(w^{T}A^{T}Aw-2t_{n}^{T}Aw+t_{n}^{T}t_{n})
\end{aligned}
\end{equation}
$$
将$E(w)$ 对$\vec w$求导（应用公式$\frac{\partial f}{\partial x}$时$\frac{\partial x^{T}A^{T}Ax}{\partial x}=2A^{T}Ax,$ 且$\frac{\partial (At_{n})^{T}x}{\partial x}=At_{n}$）
$$
\begin{equation}
\begin{aligned}
& \frac{\partial E(w)}{\partial \vec w}=\frac{1}{2}(2A^{T}Aw-2A^{T}t_{n})=0\\ & \Longrightarrow A^{T}Aw=A^{T}t_{n}
\end{aligned}
\end{equation}
$$
如题所示:
$$
\begin{equation}
\begin{aligned}
&

A^{T}
=
\left[
\begin{array}{ccc}
   \vec x_{1}, 
   \vec x_{2},
   \cdots
   \vec x_{n},
\end{array}
\right]_{M\times N}
 \quad,\quad
\vec t_{n}=
\left[
\begin{array}{c}
    t_{1} \\ 
    t_{2} \\
    t_{3}
\end{array}
\right]_{N\times 1}\\
&
\therefore A^{T}t_{n}=\left[
\begin{array}{t}
\sum_{n=1}^{N}x_{n}t_{n}\\
\sum_{n=1}^{N}x_{n}^{2}t_{n}\\
\vdots \\
\sum_{n=1}^{N}x_{n}^{M}t_{n}
\end{array}
\right]_{M \times 1}\\
&
\quad A^{T}A=\vec x_{1}\cdot \vec x_{1}^{T}+\vec x_{2}\cdot \vec x_{2}^{T}+\cdots+\vec x_{N}\cdot \vec x_{N}^{T}\\
&
\quad \quad \quad =
\begin{bmatrix}
\sum_{1}^{N}x_{n}^{1+1} & \sum_{1}^{N}x_{n}^{1+2} & \cdots & \sum_{1}^{N}x_{n}^{1+M}\\
\sum_{1}^{N}x_{n}^{2+1} & \sum_{1}^{N}x_{n}^{2+2} & \cdots & \sum_{1}^{N}x_{n}^{2+M}\\
\vdots & \vdots & \ddots & \vdots \\
\sum_{1}^{N}x_{n}^{M+1} & \sum_{1}^{N}x_{n}^{M+2} & \cdots & \sum_{1}^{N}x_{n}^{M+M}
\end{bmatrix}_{M \times M}
\end{aligned}
\end{equation}
$$
$\therefore$ 得证。