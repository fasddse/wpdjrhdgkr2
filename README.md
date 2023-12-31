# 2018732003 정수홍 제어공학 문제풀이 2

## P3.1
그림 P3.1에 스프링-질량-감쇠기 시스템이 주어져 있다. (a) 적당한 상태변수를 설정하라. (b) 상태변수로 표현된 1차 미분방정식을 구하라. (C) 상태미분방정식을 구하라.

(a) 

$$
M\ddot{y(t)} + b\dot{y(t)} + ky(t) = F(t)
$$


$$
x_1(t) = y(t), x_2(t) = \frac{\mathrm{dy(t)} }{\mathrm{d} t}
$$

(b) 
상태 변수를 적용하여 2개의 1차 미분방정식

$$
\dot{x_1(t)} = \dot{y(t)}
$$

$$
\dot{x_2(t)} = \frac{1}{M}F(t) -\frac{b}{M}x_2(t)-\frac{k}{M}x_1(t)
$$

(C) 
B의 두 식을 통해 

$$
\dot{\tilde{x(t)}} = \begin{bmatrix}
0 & \frac{-k}{M}\\ 
\frac{-K}{M} & \frac{-B}{M}
\end{bmatrix}\begin{bmatrix}
 x_1(t) \\
 x_2(t)
\end{bmatrix}
+
\begin{bmatrix}
0 \\
 \frac{1}{M}
\end{bmatrix}
F(t)
$$

다음과 같이 식을 세울 수 있다.

## P3.3
그림 3.3과 같은 RLC회로가 주어져 있다. 상태변수 $x_1(t) = i_L(t),x_2(t) = v_c(t)$로 설정하고 상태미분방정식을 구하라. 


$$
L\frac{\mathrm{di(t)} }{\mathrm{d} t} - v_c(t) + v_2(t) - v_1(t) = 0
\rightarrow
\frac{\mathrm{di(t)} }{\mathrm{d} t}  = \frac{1}{L} v_c(t) + -\frac{1}{L}v_2(t) + \frac{1}{L}v_1(t)
$$


$$
i_L(t) = i_R(t) - i_c(t) \rightarrow  \frac{\mathrm{dv_c(t)} }{\mathrm{d} t} = i_R(t) - i_L(t)
$$

서 $x_1(t) = i_L(t), x_2(t) = v_c(t)$ 로 설정 

$$
i_R(t) = \frac{1}{R}v_2(t) - \frac{1}{R}v_c(t)
$$

을 적용하여 식을 정리하게 되면

$$
\dot{x_1(t)} = \frac{1}{L}x_2(t) - \frac{1}{L}v_2(t) + \frac{1}{L}v_1(t)
$$

$$
\dot{x_2(t)} = \frac{1}{RC}v_2(t) - \frac{1}{RC}x_2(t) - \frac{1}{C}x_1(t)
$$

상태미분 방정식은

$$
\dot{\tilde{x(t)}} = \begin{bmatrix}
0 & \frac{1}{L}\\ 
\frac{-1}{C} & \frac{-1}{RC}
\end{bmatrix}\begin{bmatrix}
 x_1(t) \\
 x_2(t)
\end{bmatrix}
+
\begin{bmatrix}
 \frac{1}{L} & \frac{-1}{L}\\ 
 0 & \frac{1}{RC}
\end{bmatrix}\begin{bmatrix}
 V_1(t) \\
 V_2(t)
\end{bmatrix}
$$

과 같이 나오게 된다.


## P3.5
그림 P3.5에 폐루프 제어시스템이 주어져 있다.
(a) 폐루프 전달함수 $T(s) = Y(s) / R(s)$를 구하라. (b) 상태변수 모델을 구하라.

전달함수를 구해보면

$$
T(s) = \frac{Y(s)}{R(s)} = \frac{s+2}{s^3+5s^2-23s+2}
$$

(b)

$$
Y(s) = S*Z(s) + 2Z(s)
$$

$$
s^3Z(s)+5s^2Z(s)-23sZ(s)+2
$$

 $y(t)$는 출력방정식으로 상태미분방정식을 완성할 수 있는 식을 얻게 된다.

$$
\dot{\tilde{x(t)}} = \begin{bmatrix}
0 & 1 & 0\\ 
0 & 0 & 1 \\
-2 & 2 & -5 \\
\end{bmatrix}
x(t)
+
\begin{bmatrix}
 0\\ 
 0\\
 1
\end{bmatrix}
r(t)
$$

$$
y(t) =  \begin{bmatrix}
2 & 1 & 0\\ 
\end{bmatrix}
x(t)
$$

따라서 A,B,C,D는

$$
A = \begin{bmatrix}
0 & 1 & 0\\ 
0 & 0 & 1 \\
-2 & 2 & -5 \\
\end{bmatrix}
,
B=\begin{bmatrix}
 0\\ 
 0\\
 1
\end{bmatrix}
,
C=\begin{bmatrix}
2 & 1 & 0\\ 
\end{bmatrix}
,
D = 0
$$

## P3.12
다음 전달함수를 가지는 시스템에서

$$
\frac{Y(s)}{R(s)} = T(s) = \frac{8(s+5)}{s^3+12s^2+44s+48}
$$

(a) 상태공간모델을 구하라. (b) 상태천이 행렬 $\phi(t)$를 구하라.

(a)

$$
Y(s) = 8S*Z(s) + 40Z(s)
$$

$$
s^3Z(s)+12s^2Z(s) + 44sZ(s) + 48
$$



$$
\dot{\tilde{x(t)}} = \begin{bmatrix}
0 & 1 & 0\\ 
0 & 0 & 1 \\
-48 & -44 & -12 \\
\end{bmatrix}
x(t)
+
\begin{bmatrix}
 0\\ 
 0\\
 1
\end{bmatrix}
r(t)
$$

$$
y(t) =  \begin{bmatrix}
40 & 8 & 0\\ 
\end{bmatrix}
x(t)
$$

$$
A = \begin{bmatrix}
0 & 1 & 0\\ 
0 & 0 & 1 \\
-48 & -44 & -12 \\
\end{bmatrix}
,
B=\begin{bmatrix}
 0\\ 
 0\\
 1
\end{bmatrix}
,
C=\begin{bmatrix}
40& 8 & 0\\ 
\end{bmatrix}
,
D = 0
$$

(b) 


$$ 
[S*I -A]^-1 = \begin{bmatrix}
s & -1 & 0\\ 
0 & s & -1 \\
48 & -44 & s +12 \\
\end{bmatrix} 
$$ 

다음의 역행렬을 전개

$$
\begin{bmatrix}
\frac{(s^2+12s+44)}{(s^3+12s^2+44s+48)} & \frac{ (s+12)}{(s^3+12s^2+44s+48)} &\frac{1}{(s^3+12s^2+44s+48)} \\ 
\frac{-48}{(s^3+12s^2+44s+48)} & \frac{(s^2+12s)}{(s^3+12s^2+44s+48)} & \frac{s}{(s^3+12s^2+44s+48)}\\ 
\frac{-48*s}{(s^3+12s^2+44s+48)} & \frac{(-44s-48)}{(s^3+12s^2+44s+48)} & \frac{s^2}{(s^3+12s^2+44s+48)}
\end{bmatrix}
$$

역 라플라스

$$
\phi(t) = 
\begin{bmatrix}
e^{-6t} -3e^{-4t} +3e^{-2t} & \frac{3}{4}e^{-6t} -2e^{-4t} +\frac{5}{4}e^{-2t} & \frac{1}{9}e^{-6t} -\frac{1}{4}e^{-4t}+ \frac{1}{8}e^{-2t}\\ 
-6e^{-6t} +12e^{-4t} -6e^{-2t}& \frac{-9}{2}e^{-6t} +8e^{-4t}+ \frac{-5}{2}e^{-2t} & \frac{-3}{4}e^{-6t} +e^{-4t} \frac{-1}{4}e^{-2t} \\ 
 36e^{-6t} -48e^{-4t} +12e^{-2t}& 27e^{-6t} -32e^{-4t} +5e^{-2t} & \frac{9}{2}e^{-6t} -4e^{-4t} +\frac{1}{2}e^{-2t}
\end{bmatrix}
$$

### P3.17
다음과 같은 상태변수 방정식으로 표현된 시스템에서 $G(s) = \frac{Y(s)}{U(s)}$을 구하라.

해당 시스템의 상태공간방정식은 

$$
\dot{\tilde{x(t)}} = \begin{bmatrix}
1 & 1 & -1\\ 
4 & 3 & 0 \\
-2 & 1 & 10 \\
\end{bmatrix}
x(t)
+
\begin{bmatrix}
 0\\ 
 0\\
 4
\end{bmatrix}
u(t)
$$

$$
y(t) =  \begin{bmatrix}
1 & 0 & 0\\ 
\end{bmatrix}
x(t)
$$

이러한 시스템에서 전달함수 $G(s)$는 $C*\phi(s)*B$를 전개

$$
\begin{bmatrix}
1 & 0 & 0
\end{bmatrix} \cdot 
\begin{bmatrix}
\frac{(s^2-13s+30)}{(s^3-14s^2+37s+20)} & \frac{ (s-11)}{(s^3-14s^2+37s+20)} &\frac{-s+3}{(s^3-14s^2+37s+20)} \\ 
\frac{+4s-40}{(s^3-14s^2+37s+20)} & \frac{(s^2-11s+8)}{(s^3-14s^2+37s+20)} & \frac{-4}{(s^3-14s^2+37s+20)}\\ 
\frac{-2s+10}{(s^3-14s^2+37s+20)} & \frac{(s-3)}{(s^3-14s^2+37s+20)} & \frac{s^2-4s-1}{(s^3-14s^2+37s+20)}
\end{bmatrix}\cdot \begin{bmatrix}
0\\
0\\
4 
\end{bmatrix}
$$

$\phi(s),B$를 정리하여 $C$를 전개하면 아래와 같다.

$$
\begin{bmatrix}
1 & 0 & 0
\end{bmatrix} \cdot 
\begin{bmatrix}
&\frac{-4s+12}{(s^3-14s^2+37s+20)}\\ 
&\frac{-16}{(s^3-14s^2+37s+20)}\\ 
&\frac{4s^2-16s-4}{(s^3-14s^2+37s+20)}
\end{bmatrix}
\rightarrow 
\frac{-4s+12}{(s^3-14s^2+37s+20)}
$$
