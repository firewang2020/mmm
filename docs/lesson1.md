# 1.方程组的几何解释
## 1.1 课程内容：方程组的几何解释
### 前置思考：考虑 n 个未知数 n 个方程组的情形
首先考虑最简单的二元线性方程组
$$
\begin{cases}
a_{1}x+b_{1}y=l  \\
a_{2}x+b_{2}y=m \\
\end{cases}
$$
__从行的角度来看__，

$$
\begin{array}{rl}
a_{1}x+b_{1}y &= l 
\\
a_{2}x+b_{2}y &= m 
\end{array}
$$
分别表示两条二维平面中的直线，如果这两条直线相交，那么交点的坐标 $(x^{*},y^{*})$ 即为方程组的解。

更确切的讲:
+ 如果两条直线相交于一点，那么该方程组有且仅有一个解，即为交点的坐标；
+ 如果两条直线重合，那么说明这两条直线方程实际上是同一条直线，此时直线上的所有点的坐标均为方程组的解；
+ 如果两条直线平行但不重合，则说明不存在点的坐标同时满足这两条直线的方程，此时方程组无解。

__从列的角度来看__，上述二元线性方程组可以写成
$$
x\begin{bmatrix}
a_{1} \\
a_{2} \\
\end{bmatrix}+
y\begin{bmatrix}
b_{1}\\
b_{2}\\
\end{bmatrix}=
\begin{bmatrix}
{l}\\
{m}\\
\end{bmatrix}
$$
此时，列向量
$$
\begin{bmatrix}
a_{1} \\
a_{2} \\
\end{bmatrix},
\begin{bmatrix}
b_{1}\\
b_{2}\\
\end{bmatrix},
\begin{bmatrix}
{l}\\
{m}\\
\end{bmatrix}
$$

表示起点为 $(0,0)$, 终点分别为 $(a_1,a_2)$, $(b_1,b_2)$,$(c_1,c_2)$ 的向量，分别记为 $\alpha$,$\beta$, $\gamma$.

那么方程的左边就表示向量 $\alpha$,$\beta$ 的线性组合，$x, y$ 称为线性组合的系数，因此线性方程组就可以理解为：

是否存在合适的线性组合系数 $x, y$, 使得 $\alpha$,$\beta$ 的线性组合 $x\alpha +y\beta$ 恰好等于 $\gamma$ .
    

类似的，将情形推广到三维，对于三元一次方程组
$$
\begin{cases}
a_{1}x+b_{1}y+c_{z}=l \\
a_{2}x+b_{2}y+c_{z}=m \\
a_{2}x+b_{2}y+c_{z}=n \\
\end{cases}
$$
__从行的角度来看__，三个三元一次方程表示三维空间中的三个平面，如果三个平面相交于一点，那么交点的坐标即为方程组的解。

更确切的讲
+ 如果三个平面有且只有一个交点，那么此时方程组有且仅有一个解，即为交点坐标；
+ 如果三个平面相交于一条直线，那么这条直线上的所有点的坐标均为方程组的解；
+ 如果三个平面重合，那么平面上的点的坐标均为方程组的解；
如果三个平面没有公共的交点，那么方程组无解。

__从列的角度来看__，类似二元线性方程组的情形，同样可以从列向量线性组合的角度来理解。

继续推广，对于一般的 $n$ 维线性方程组 $Ax=b$，其中 $A$ 是 $n\times n$ 维系数矩阵，$x$ 是 $n$ 维列向量，$b$ 是方程组右端的 $n$ 维列向量。

不妨设 $\alpha_{1},\alpha_{2},{\cdots},\alpha_{n}$ 是 $A$ 的 $n$ 个列向量，$x=(x_1,x_2,⋯,x_n)^{T}$，则方程组 $Ax=b $ 可以表示为
$$
(\alpha_{1},\alpha_{2},{\cdots},\alpha_{n})
\begin{pmatrix}
x_{1}  \\
x_{2}  \\
{\vdots} \\
x_{n}
\end{pmatrix}=b
$$

即
$$
x_{1}\alpha_{1}+x_{2}\alpha_{2}+⋯+x_{n}\alpha_{n}=b.
$$
由此可以看出，矩阵 $A$ 乘以向量 $x$ 相当于对 $A$ 的 $n$ 的列向量作线性组合，线性组合的系数即为向量 $x$ 各行对应的分量。

因此对线性方程组 $Ax=b$ 可以理解为：

是否存在合适的线性组合系数，使得 $A$ 的列向量的线性组合恰好为 $b$
如果存在，线性组合的系数为多少？
这些线性组合的系数就构成了 $Ax=b$ 的解向量 $x$.

现在，我们还有一个问题，线性方程组 $Ax=b$ 在什么情况下有解？

首先我们考虑对于任意的 $n$ 维列向量 $x$，当 $x$ 变动时， $Ax$ 也在变动，当 $x$ 取遍所有的 $n$ 维列向量时，$Ax$ 就能取遍所有 $A$ 的列向量的线性组合，也就是说，所有的 $Ax$ 就构成了 $A$ 的列向量张成的线性空间 $V=span\{\alpha_{1},\alpha_{2},{\cdots},\alpha_{n}\}$.

因此

$$
Ax=b \text{有解} \Leftrightarrow b\in span\{\alpha _1 ,\alpha _2 ,\cdots ,\alpha _n\}.
$$

又由于

$$
b\in span\{\alpha _1 ,\alpha _2 ,\cdots ,\alpha _n\} \Leftrightarrow rank(A)=rank(A,b)
$$

因此我们也就得出了

$$
Ax=b \text{有解} \Leftrightarrow rank(A)=rank(A,b)
$$

特别地，如果 $A$ 的 $n$ 个列向量线性无关，那么这 $n$ 个列向量就构成了 $n$ 维向量空间 $\mathbb{R}^{n}$ 的一组基。此时对于任意的 $b\in \mathbb{R}^{n}$ 均可由 $A$ 的列向量线性表出，也即是 $Ax=b$ 一定有解。

换言之，如果 $A$ 可逆，则 $Ax=b$ 一定有解。

有了对线性方程组的这些认识，我们可以更好地理解矩阵乘法。

首先考虑列向量 $x\in \mathbb{R}^{n}$右乘矩阵 $A\in \mathbb{R}^{n\times n}$

先从行的角度考虑，不妨设
$$
A=\begin{pmatrix}
\alpha_{1}^{T} \\
\alpha_{2}^{T}\\ 
{\cdots} \\
\alpha_{n}^{T}
\end{pmatrix} ,
x = \begin{pmatrix}
x_{1}  \\
x_{2}  \\
{\vdots} \\
x_{n}
\end{pmatrix}
$$
其中， $\alpha_{1}^{T},\alpha_{2}^{T} ,\cdots , \alpha_{n}^{T}$ 是 $A$ 的 $n$ 个行向量， $x_1,x_2,\cdots ,x_n$ 是 $x$ 的 $n$ 个分量。

则
$$
\begin{array}{c}
Ax=\begin{pmatrix}
\alpha_{1}^{T} \\
\alpha_{2}^{T}\\ 
{\cdots} \\
\alpha_{n}^{T}
\end{pmatrix}x =
\begin{pmatrix}
\alpha_{1}^{T}x \\
\alpha_{2}^{T}x\\ 
{\cdots} \\
\alpha_{n}^{T}x
\end{pmatrix} =
\begin{pmatrix}
\alpha_{1}x \\
\alpha_{2}x\\ 
{\cdots} \\
\alpha_{n}x
\end{pmatrix}
\end{array}
$$


由此可知，从行的角度来看，$Ax$ 相当于分别用 $A$ 的行点乘 $x$，这就是矩阵乘法的定义。

下面从列的角度考虑，这是一种非常重要的理解方式。

不妨设

$$
A=(\beta_{1},\beta_{2},{\cdots},{\beta_{n}})
$$

其中，$\beta_{1},\beta_{2},{\cdots},{\beta_{n}}$ 是 $A$ 的 $n$ 个列向量。

则
$$
\begin{array}{rl}
Ax
&=\begin{pmatrix}
\beta_{1},\beta_{2},{\cdots},{\beta_{n}} \\
\end{pmatrix}
\begin{pmatrix}
x_{1} \\
x_{2}\\ 
{\vdots} \\
x_{n}
\end{pmatrix}   \\
&=
\beta_{1}x_{1} +
\beta_{2}x_{2} +
{\cdots} +
\beta_{n}x_{n}
\end{array}
$$

由此即知，列向量 $x$ 右乘矩阵 $A$ 即是对 $A$ 的列向量作线性组合，$x$ 的各分量即为线性组合的系数。

下面考虑行向量 $y^{T}$ 左乘矩阵 $A\in \mathbb{R}^{n\times n}$， 其中 $y\in \mathbb{R}^{n}$

不妨设
$$
y^{T}=\begin{pmatrix}
y_{1},y_{2},{\cdots},y_{n} \\
\end{pmatrix}
$$
则
$$
\begin{array}{rl}
y^{T}A 
&=\begin{pmatrix}
y_{1},y_{2},{\cdots},y_{n} \\
\end{pmatrix}
\begin{pmatrix}
\alpha_{1}^{T} \\
\alpha_{2}^{T}\\ 
{\cdots} \\
\alpha_{n}^{T}
\end{pmatrix} \\
&=
y_{1}\alpha_{1}^{T} +
y_{2}\alpha_{2}^{T} +
{\cdots} +
y_{n}\alpha_{n}^{T}
\end{array}
$$


由此即知，行向量 $y^{T}$ 左乘矩阵 $A$ 相当于对 $A$ 的行向量作线性组合，$y^{T}$ 的各分量即为线性组合的系数。

综上所述，列向量 $x$ 右乘矩阵 $A$ 相当于对 $A$ 的列向量作线性组合，
$x$ 的各分量即为线性组合的系数；
行向量 $y^{T}$ 左乘矩阵 $A$ 相当于对 $A$ 的行向量作线性组合， $y^{T}$ 的各分量即为线性组合的系数。

对于矩阵与矩阵的乘法，只需把矩阵按行或列分块，即可按上述向量乘矩阵的方式理解。

即
$$
\begin{array}{rl}
AB&=A\begin{pmatrix}
\beta_{1},\beta_{2},{\cdots},{\beta_{n}} \\
\end{pmatrix}=
\begin{pmatrix}
A\beta_{1},A\beta_{2},{\cdots},{A\beta_{n}} \\
\end{pmatrix} \\
\\
&=\begin{pmatrix}
\alpha_{1}^{T} \\
\alpha_{2}^{T}\\ 
{\cdots} \\
\alpha_{n}^{T}
\end{pmatrix}B=
\begin{pmatrix}
\alpha_{1}^{T}B \\
\alpha_{2}^{T}B\\ 
{\cdots} \\
\alpha_{n}^{T}B
\end{pmatrix}
\end{array}
$$

也即是，矩阵 $B$ 右乘 矩阵 $A$ 相当于对 $A$ 的列作线性组合，$B$ 的各列的分量即为线性组合的系数；矩阵 $A$ 左乘 矩阵 $B$ 相当于对 $B$ 的行作线性组合，$A$ 的各行的分量即为线性组合的系数。

## 1.2 习题课
[2011年线性方程组的几何解释习题课](https://open.163.com/movie/2016/4/H/1/MBKJ0DQ52_MBKJ0MDH1.html)

思考下列方程组：
$$
\begin{cases}
2x+y=3 \\
x-2y=-1 \\
\end{cases}
$$
1. 线性方程组的形式
$$
x-2y=-1 \,
{→}     \,
x=2y-1  \,
$$
回代到方程组可得：
$$
2x+y=3 {→} 
2(2y-1) + y =3 → y=1 → x=1
$$

2. 行视图

行视图就是对于线性方程组的每一行的视角去理解该线性方程组，因此该方程组可以理解为 2 条直线（每一个方程组就是平面上的一条直线），所求的 $x,y$ 也就是两条直线的交点了。

3. 列视图

$$
x\begin{bmatrix}
{2}\\
{1}\\
\end{bmatrix}+
y\begin{bmatrix}
{1}\\
{-2}\\
\end{bmatrix}=
\begin{bmatrix}
{3}\\
{-1}\\
\end{bmatrix}
$$
将 $x,y$ 看作向量（2,1）和（1，-2）的线性组合，得到向量（3，-1），由此可以用平行四边形法则得到 $x,y$ 的具体值。

4. 矩阵形式
$$
A=\begin{bmatrix}
v_{1}&v_{2}\\
\end{bmatrix}=
\begin{bmatrix}
{2}&{1}\\
{1}&{-2}\\
\end{bmatrix}
$$

那么如何求解呢？

考虑一元方程的情况：
$$
ax=b 
\Rightarrow
x=\frac{b}{a}
\Rightarrow
x=a^{-1}b
$$
推广到矩阵：
$$
Ax=b 
\Rightarrow
x=\begin{bmatrix}
x \\
y \\
\end{bmatrix}
\Rightarrow
x=A^{-1}b
$$

因此为了解得方程组的解，实际上就转化为求方程组的系数构成的矩阵 $A$ 的逆矩阵