# 행렬곱(Matrix Product)

## 행렬의 열벡터 표현

행렬 $A$의 각 열을 $\vec{a}_1$, $\vec{a}_2$, $\cdots$로 두면 행렬을 열벡터로 나타낼 수 있다.

$$
\begin{array}{ccc}
A = 
\begin{bmatrix}
a_{11} & a_{12}\\
a_{21} & a_{22}
\end{bmatrix}
&
\vec{a}_1 = 
\begin{bmatrix}
a_{11}\\
a_{21}
\end{bmatrix}
&
\vec{a}_2 = 
\begin{bmatrix}
a_{12}\\
a_{22}
\end{bmatrix}
\end{array}
\\[2em]
→ A = \begin{bmatrix}
\vec{a}_1&\vec{a}_2
\end{bmatrix}
$$

단, 행렬이 단 하나의 열로만 이루어진 경우 행렬 그 자체가 하나의 벡터이다.

$$
A = \vec{a}_1 = \begin{bmatrix}
a_{11}\\a_{21}
\end{bmatrix}
$$

## 행렬의 행벡터 표현

열벡터 표현 때와는 달리 행렬 $A$의 각 행을 $\vec{a}_1$, $\vec{a}_2$, $\cdots$로 두면 행렬을 행벡터로 나타낼 수 있다.

$$
\begin{array}{ccc}
A = 
\begin{bmatrix}
a_{11} & a_{12}\\
a_{21} & a_{22}
\end{bmatrix}
&
\vec{a}_1 = 
\begin{bmatrix}
a_{11}\\a_{12}
\end{bmatrix}
&
\vec{a}_2 = 
\begin{bmatrix}
a_{21}\\a_{22}
\end{bmatrix}
\end{array}
\\[2em]
→ A = \begin{bmatrix}
\vec{a}^T_1\\
\vec{a}^T_2
\end{bmatrix}
$$

단, 행렬이 단 하나의 행으로만 이루어진 경우 행렬 그 자체가 한 벡터의 전치이다.

$$
A = \vec{a}_1^T = \begin{bmatrix}
a_{11} & a_{21}
\end{bmatrix}
$$

## 행렬곱 표

두 행렬의 곱셈은 다음과 같이 행렬곱 표로 나타낼 수 있다.

$$
A = 
\begin{bmatrix}
a_{11} & a_{12}\\
a_{21} & a_{22}
\end{bmatrix}
\quad
B = 
\begin{bmatrix}
b_{11} & b_{12}\\
b_{21} & b_{22}
\end{bmatrix}

\\[2em]

AB \quad=\quad 
\def\arraystretch{1.5}
\begin{array}{cc|cc}
        &           & b_{11}    & b_{12}\\
        &           & b_{21}    & b_{22}\\
\hline
a_{11}  & a_{12}    & a_{11}b_{11}+a_{12}b_{21} & a_{11}b_{12}+a_{12}b_{22} \\

a_{21}  & a_{22}    & a_{21}b_{11}+a_{22}b_{21} & a_{21}b_{12}+a_{22}b_{22} \\
\end{array}
$$

예를 들어

$$
\begin{bmatrix}
1 & 2\\
3 & 4
\end{bmatrix}
\begin{bmatrix}
1 & 3\\
2 & 4
\end{bmatrix}\quad=\quad
\def\arraystretch{1.5}
\begin{array}{cc|cc}
        &           & 1    & 3\\
        &           & 2    & 4\\
\hline
1  & 2    & 5 & 11 \\
3  & 4    & 11 & 25 \\
\end{array}
$$


행렬곱 표를 사용하면 어느 원소가 어느 자리의 연산에 사용되는지 명확하게 보인다.

행렬곱 표는 행렬곱의 각 원소가 왼쪽 행렬의 $i$번째 행벡터와 오른쪽 행렬의 $j$번째 열벡터의 내적임을 확연히 보여준다.

$$
A = 
\begin{bmatrix}
\vec{a}_1^T\\
\vec{a}_2^T
\end{bmatrix}

B = 
\begin{bmatrix}
\vec{b}_1&\vec{b}_2
\end{bmatrix}

\\[2em]

AB = 
\def\arraystretch{1.5}
\begin{array}{c|cc}
                & \vec{b}_1    & \vec{b}_2\\
\hline
\vec{a}_1^T    & \vec{a}_1^T \cdot \vec{b}_{1} & \vec{a}_1^T \cdot \vec{b}_2 \\

\vec{a}_2^T    & \vec{a}_2^T \cdot \vec{b}_{1} & \vec{a}_2^T \cdot \vec{b}_2 \\
\end{array}
$$

행렬곱 표를 사용하면 선형 시스템이 행렬 형태로 표현되는 과정을 머리속으로 쉽게 그릴 수 있다.

$$
\begin{array}{ll}
    &\begin{cases}
    a_{11}x_1 + a_{12} x_2 = b_1\\
    a_{21}x_1 + a_{22} x_2 = b_2
    \end{cases}\\[2em]

    →

    &\begin{bmatrix}
    a_{11}\\
    a_{21}
    \end{bmatrix}x_1
    +
    \begin{bmatrix}
    a_{12}\\
    a_{22}
    \end{bmatrix}x_2
    =
    \begin{bmatrix}
    b_1\\
    b_2
    \end{bmatrix}\\[2em]

    →

    &\begin{bmatrix}
    a_{11}x_1 + a_{12}x_2\\
    a_{21}x_1 + a_{22}x_2
    \end{bmatrix}
    =
    \begin{bmatrix}
    b_1\\
    b_2
    \end{bmatrix}\\[2em]

    →

    &\begin{bmatrix}
    a_{11} & a_{21}\\
    a_{12} & a_{22}
    \end{bmatrix}
    \begin{bmatrix}
    x_1\\x_2
    \end{bmatrix}
    =
    \begin{bmatrix}
    b_1\\
    b_2
    \end{bmatrix}
\end{array}

$$


$$
\because\quad
\def\arraystretch{1.5}
\begin{array}{cc|c}
        &           & x_1\\
        &           & x_2\\
\hline
a_{11}  & a_{12}    & a_{11}x_1 +a_{12}x_2 \\

a_{21}  & a_{22}    & a_{21}x_1 + a_{22}x_2 \\
\end{array}
$$

## 행렬곱의 벡터 표현

### 왼쪽 행렬만 열벡터로 바꾸는 경우

행렬곱의 왼쪽 행렬을 열벡터 표현으로 고쳐보면, 마치 각 열벡터가 각각의 원소인 것처럼 행렬곱을 적용할 수 있음을 알 수 있다.

$$
\begin{array}{ll}
    &\begin{bmatrix}
    a_{11} & a_{12}\\
    a_{21} & a_{22}
    \end{bmatrix}
    \begin{bmatrix}
    x_{11}&x_{12}\\
    x_{21}&x_{22}
    \end{bmatrix}\\[2em]

    =

    &\begin{bmatrix}
    \vec{a}_1 & \vec{a}_2
    \end{bmatrix}
    \begin{bmatrix}
    x_{11}&x_{12}\\
    x_{21}&x_{22}
    \end{bmatrix}\\[2em]

    =

    &\begin{bmatrix}
    \vec{a}_1x_{11} + \vec{a_2}x_{21} &
    \vec{a}_1x_{12} + \vec{a_2}x_{22}
    \end{bmatrix}
\end{array}
$$

특히 왼쪽 행렬이 하나의 열로만 이루어져 있는 경우 다음과 같이 벡터의 다항식으로 나타낼 수 있다

$$
\begin{array}{ll}
    &\begin{bmatrix}
    a_{11}\\
    a_{21}
    \end{bmatrix}
    \begin{bmatrix}
    x_{11}&x_{12}
    \end{bmatrix}\\[2em]

    =

    &\vec{a}\vec{x}^T
    \\[2em]

    =

    &\vec{a}x_{11} + \vec{a}x_{12}
\end{array}
$$

## 왼쪽 행렬을 행벡터로 바꾸고 오른쪽 행렬을 열벡터로 바꾸는 경우

행렬곱 표를 그릴 때와 마찬가지로 행렬 내에서 왼쪽 행렬은 행벡터, 오른쪽 행렬은 열벡터로 나타낸 경우 행렬곱 연산이 각 $i$번째 행벡터와 $j$번째 열벡터의 내적임을 보여준다.

$$
\begin{array}{ll}
    &\begin{bmatrix}
    a_{11} & a_{12}\\
    a_{21} & a_{22}
    \end{bmatrix}
    \begin{bmatrix}
    x_{11}&x_{12}\\
    x_{21}&x_{22}
    \end{bmatrix}\\[2em]

    =

    &\begin{bmatrix}
    \vec{a}_1^T \\ \vec{a}_2^T
    \end{bmatrix}
    \begin{bmatrix}
    \vec{x}_1&\vec{x}_2
    \end{bmatrix}\\[2em]=

    &\begin{bmatrix}
    \vec{a}_1^T \cdot \vec{x}_1 & \vec{a}_1^T \cdot \vec{x}_2 \\ 
    \vec{a}_2^T \cdot \vec{x}_1 & \vec{a}_2^T \cdot \vec{x}_2
    \end{bmatrix}\\[2em]
\end{array}
$$

특히, 왼쪽 행렬이 하나의 행으로만 이루어져 있고, 오른쪽 행렬이 하나의 열로만 이루어져 있다면, 행렬곱이 곧 내적이다.

$$
\begin{array}{ll}
    &\begin{bmatrix}
    a_{11} & a_{12}\\
    \end{bmatrix}
    \begin{bmatrix}
    x_{11}\\x_{21}
    \end{bmatrix}\\[2em]

    =&

    a_{11}x_{11} + a_{12}x_{21}\\[2em]

    =&
    \vec{a}_1^T
    \cdot
    \vec{x}\\[2em]
\end{array}
$$
