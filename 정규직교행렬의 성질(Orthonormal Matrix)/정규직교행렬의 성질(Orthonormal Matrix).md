# 정규직교행렬의 성질(orthonormal matrix)

정규직교행렬 $M$의 열벡터가 $v_1$ $v_2$ $v_3$라고 할 때, 열벡터 간에는 다음 성질이 성립한다.

$$
M = \begin{bmatrix}v_1&v_2&v_3\end{bmatrix}\\
v_1 \perp v_2 \perp v_3\\
||v_1|| = ||v_2|| = ||v_3|| = 1
$$

정규직교행렬 $M$의 역행렬은 전치행렬이다.

$$
M^T = M^{-1}
$$

이 사실은 행렬곱이 왼쪽 행렬의 행벡터와 오른쪽 행렬의 열벡터 사이의 점곱입을 생각하면 자명하다

$$
M^TM =
\begin{bmatrix}
v_1^T\\
v_2^T\\
v_3^T
\end{bmatrix}
\begin{bmatrix}
v_1&v_2&v_3
\end{bmatrix}
=
\begin{bmatrix}
v_1^T v_1&v_1^T v_2 & v_1^T v_3\\
v_2^T v_1&v_2^T v_2 & v_2^T v_3\\
v_3^T v_1&v_3^T v_2 & v_3^T v_3
\end{bmatrix}
=
\begin{bmatrix}
1 & 0 & 0\\
0 & 1 & 0\\
0 & 0 & 1
\end{bmatrix}
= I
$$

### 모델-뷰 행렬 구하기

회전 행렬이 적규직교행렬임을 생각하면 모델-뷰 행렬을 구할 때 도움이 될 수 있다.

원점의 $[e_1, e_2, e_3]$공간에서 정의된 점 $x$에서 중심이 $p$인 카메라의 공간 $[v_1, v_2, v_3]$에서 정의된 $x'$으로의 아핀 맵은 다음과 같이 정의된다.

$$
x' = Ax + p
$$

아핀 맵은 4차원 행렬로 표현할 수 있으므로, 다음과 같이 쓸 수 있다.

$$
x' = T_pR_vx = 
\begin{bmatrix}
1&0&0&\\
0&1&0&p\\
0&0&1&\\
0&0&0&1 
\end{bmatrix}
\begin{bmatrix}
&&&0\\
v_1&v_2&v_3&0\\
&&&0\\
0&0&0&1
\end{bmatrix}
x
$$

모델-뷰 행렬은 이 아핀 맵의 역행렬이다.

$$
x = R_v^{-1}T_p^{-1}x'
$$

여기서 회전행렬은 정규직교행렬이므로, $R_v^{-1}=R^T$이다. 또한, $T_p^{-1}=T_{-p}$이다.

$$
x = T_{-p}R_v^{T}x' = 
\begin{bmatrix}
&v_1^T&&0\\
&v_2^T&&0\\
&v_3^T&&0\\
0&0&0&1
\end{bmatrix}
\begin{bmatrix}
1&0&0&\\
0&1&0&-p\\
0&0&1&\\
0&0&0&1 
\end{bmatrix}
x'
$$

따라서 위치가 $p$이고 정규직교기저가 $v_1, v_2, v_3$인 카메라의 모델-뷰 행렬은 다음과 같다.

$$
\begin{bmatrix}
&v_1^T&&-v_1^Tp\\
&v_2^T&&-v_2^Tp\\
&v_3^T&&-v_3^Tp\\
0&0&0&1 
\end{bmatrix}
$$

이 방식으로 구할 경우 가우스 소거법을 사용하는 것 보다 더 적은 연산으로 역행렬을 구할 수 있다.