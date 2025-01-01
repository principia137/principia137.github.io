---
title: 그린함수(Green function)의 이해와 적용
categories: [study&dev]
subcategory : mathematics
comments: true
---

# 들어가는 말

내가 학부 전자기학 수업때 그 교수님은 설명을 시작하는 말로 허구언날
\"This is my vending machine\"을 말했다. 하지만 내 생각엔 그 당시에 나를
포함해 그 누구도 이 설명을 온전히 이해하지 못했다(이 것이 학생들 잘못은
분명 아니다). 어찌간에 나중엔 따로 그린함수를 공부해서 의미를 이해하게
되었다. 그린함수 내용자체가 재밌게 다가왔고 인과율 까지 연결되는 것이
호기심을 자극했다. 그래서 그린함수를 끝까지 파고 들었다. 이 자료는 그
과정을 집대성한 결과물이다. 내가 봤던 어떤 자료보다도 명쾌하고 쉽게
이해할 수 있는 자료라 스스로 생각한다. 그린함수의 모든 것을 담고 있지는
않다. 그래도 거의 모든 것을 담고 있고 핵심적인 개념에 대해 아주 쉽고
명확히 기술하고 있다.

# 그린함수 이해하기

## 그린함수의 의미

선형시스템 , 미분방정식의 선형성 이용 자판기 비유, 신및시 그린함수의
의미 어쩌구

복잡한 시스템의 결과를 예측하는 것은 쉽지 않다. 여기서 시스템이란 보통
미분방정식을 일컫는다. 하지만 시스템의 선형성을 이용해 쉽게 풀수 있는
방법이 있다.

교수님이 해주었던 자판기 비유를 들어 그린함수를 설명을 해보겠다.
자판기가 있다. 이 자판기의 내부는 복잡하다. 우리는 자판기에 돈을 넣는
입력을 했을 때 출력으로 어떤 음료수가 나오는지 알고싶다. 하지만 매번
돈을 넣을때 마다 복잡한 자판기 시스템을 다 분석하여 출력을 계산하는 것은
너무 오래걸리고 쉽지 않다. 하지만 좋은 방법이 있다. 이 자판기는 선형
시스템이다. 선형성을 이용하면 입력값에 대한 출력값을 매번 일일이
계산하지 않아도 한번의 계산만으로 출력값을 쉽게 예측할 수 있도록 해준다.

시스템 F에 대해 $F(c_1\alpha+c_2\beta)=c_1F(\alpha)+c_2F(\beta)$ 가
성립하면 선형 시스템이다.

$f=c_1f_1+c_2f_2+...+c_nf_n$ 으로 분해하여 쓸 수 있다. 연산자
$\hat{L}$이 있다고 해보자. 여기서 연산자는 곧 시스템을 의미한다.
$\hat{L}y=f$ 여기서 $f$는 입력을 의미하고 $y$는 출력을 의미한다. 각기
다른 $f$를 입력할 수 있고 시스템$\hat{L}$을 거쳐서 우리가 구하고자 하느
해인 출력값 $y$를 구할 수 있다.

우리는 가장 쉬운 입력을 넣어보려고 한다. 자판기에 100원을 넣는 것이다.
그리고선 100원을 넣었을 때 출력으로 음료수가 몇개나오는지 살펴보면 된다.
자판기는 선형시스템이므로, 만약 우리가 100원을 넣었을 때 음료수 1개가
나온다는 것을 알 수 있다면 200원, 300원 \... 1200원 12만 7천500원.. 등을
넣었을 때 음료수가 몇개 나오는지를 예측할 수 있다. 결국 우리는 100원을
넣었을 때 나오는 음료수의 개수만 알면 된다. 매번 입력에 대하여 그
입력값을 복잡한 시스템에 적용시키고 계산하여 출력을 구할 필요가 없다는
것이다. 기본단위라고도 할 수 있는 100원에 대한 출력값을 한번 구해놓으면
끝이다. 이 100원이라는 입력에 대한 출력값이 바로 그린함수이다.\
따라서 그린함수를 정확히 정의해보면 \"기본 단위 입력에 대한 시스템의
응답\"이라고 할 수 있다.

## 그린함수 공식유도

\"기본 단위 입력에 대한 시스템의 응답\"을 어떻게 수식으로 표현할까?

$$\begin{aligned}
    \hat{L}g(x)&=f(x)\\
    \hat{L}G(x,x')&=\delta(x-x')
\end{aligned}$$

식의 양변에 입력함수$f(x')$를 곱해주고 적분해보자. $$\begin{aligned}
    &\int\hat{L}G(x,x')f(x')dx'=\int\delta(x-x')f(x')dx'=f(x)=\hat{L}g(x)\\
\end{aligned}$$ 미분연산자 $\hat{L}$ 은 $x$에 대한 미분이고 적분은
$x'$에 대해 이루어졌으므로 연산자가 밖으로 빠져나올 수 있다. 그러면
다음과 같다. $$\begin{aligned}
    &\hat{L}\left(\int G(x,x')f(x')dx'\right) =\hat{L}(g(x))\\
    \rightarrow &g(x)=\int G(x,x')f(x')dx'
\end{aligned}$$ 따라서 그린함수를 구한 후 입력함수와 곱해서 적분해주면
방정식의 해를 구할 수 있다.

# 그린함수의 풀이와 적용

그린함수를 이용해 미분방정식을 푸는 방법을 알아보았다. 실제 몇가지
미분방정식 문제를 살펴보며 각 시스템의 그린함수를 찾고 방정식의 해를
구해보자. 그린함수를 구하는 방법에는 여러가지가 있다. 어쩌나 저쩌나 무슨
방법이든지 그린함수만 찾으면 그만이다. 몇몇 미분방정식에서는 그린함수를
찾는 창의적인 방법을 쓸 수도 있다(아래에서 직접 살펴 볼 것이다). 하지만
어떤 시스템이든지 그린함수를 찾는 어느정도 기초적인 방법론이 있다. 이
것을 살펴보고 여러 시스템에서 그린함수를 직접 계산해보자.\
만약 그린함수를 구하는 것이 매우 어렵다면 굳이 그린함수를 이용하지
않아도 된다. 미분방정식의 해를 쉽게 찾기 위해 그린함수를 쓰는데 이 걸
구하는게 매우 어려워진다면 배보다 배꼽이 더 커지는 셈이다. 하지만
대부분의 경우에 그린함수를 이용해 해를 구하는 것이 복잡한 입력에 대한
비제차 미분방정식을 직접 구하는 것보다는 쉽다. 또한 그린함수를 한번
구해놓으면 어떤 입력값에 대해서도 적분만 해주면 해를 구할 수 있기 때문에
매우 편리하다. 그린함수는 단위 임펄스에 대한 응답이므로 어떤 시스템의
특성을 파악할 수 있기도 하다.\

## 그린함수 풀이법의 인사이트

그린함수를 찾기위해 공통적으로 쓰일 수 있는 기본적인 방법에 대해서 먼저
알아볼 것이다. 이 것을 정리하고 가는 것이 그린함수의 풀이를 이해하는데에
굉장한 인사이트를 줄 것이라 기대됨으로 정확히 정리하고 넘어가고자 한다.
어차피 각각 세세한 계산은 문제를 풀면서 다 할 것이므로 시간이 없다면 이
부분은 건너뛰어도 좋다(하지만 그렇지 않기를 추천한다).\

### 라플라스 변환을 이용한 미분방정식 풀이 {#라플라스-변환을-이용한-미분방정식-풀이 .unnumbered}

먼저 라플라스 변환에 대해 언급하고 싶다. 라플라스 변환만 가지고도 정말
많은 얘기들을 할 수 있지만 여기서는 라플라스 변환을 이용해 미분방정식을
풀이하는 방법에 대해 얘기할 것이다. 라플라스 변환을 이용하면 미분
방정식을 대수 방정식으로 바꾸어 풀이할 수 있다. 기본 컨셉은 다음과 같다.
라플라스 변환을 한다. 대수방정식으로 바꾼다. 대수방정식을 푼다. 라플라스
역변환을 한다. 핵심은 미분방정식을 대수방정식으로 바꾼다는 것이다.
대수방정식의 풀이법은 우리가 잘 알고 있는 것이 많으므로 계산이 훨씬
쉽다.

예제. $$\begin{aligned}
    y(t)=\frac{1}{2\pi i}\int_{\gamma-i\infty}^{\gamma+i\infty} \tilde{y}(s)e^{st}ds\\
    y''+y=e^{3t}\\
    \rightarrow \frac{\partial^2}{\partial t^2}\left(\frac{1}{2\pi i}\int_{\gamma-i\infty}^{\gamma+i\infty} \tilde{y}(s)e^{st}ds\right)+\frac{1}{2\pi i}\int_{\gamma-i\infty}^{\gamma+i\infty} \tilde{y}(s)e^{st}ds=\frac{1}{2\pi i}\int_{\gamma-i\infty}^{\gamma+i\infty} \frac{1}{s-3}e^{st}ds
\end{aligned}$$ 첫항의 미분을 수행한 후 정리하면 다음과 같다.\
$$\begin{aligned}
    \frac{1}{2\pi i}\int_{\gamma-i\infty}^{\gamma+i\infty}\left( s^2+1\right)\tilde{y}(s)e^{st}ds=\frac{1}{2\pi i}\int_{\gamma-i\infty}^{\gamma+i\infty}\left(\frac{1}{s-3}\right)e^{st}ds
\end{aligned}$$ 위 식을 만족하기 위해선, $$\begin{aligned}
    (s^2+1)\tilde{y}(s)=\frac{1}{s-3}
\end{aligned}$$ 이 되어야 한다. 라플라스 변환을 통해 미분방정식을
대수방정식으로 바꾸었다. 이 대수방정식은 양변을 $(s^2+1)$을 나누어
줌으로써 간단히 구할 수 있다.\
$$\begin{aligned}
    \tilde{y}(s)=\frac{1}{(s^2+1)(s-3)}=\frac{1}{(s+i)(s-i)(s-3)}
\end{aligned}$$ $s$영역의 함수를 구했으므로 이제 라플라스 역변환을
해주어 본래 함수를 구해보자.\
$$\begin{aligned}
    y(t)=\frac{1}{2\pi i}\int_{\gamma-i\infty}^{\gamma+i\infty} \tilde{y}(s)e^{st}ds=\frac{1}{2\pi i}\int_{\gamma-i\infty}^{\gamma+i\infty} \frac{1}{(s+i)(s-i)(s-3)}e^{st}ds
\end{aligned}$$

$$\begin{aligned}
    Res(-i)=\frac{e^{-it}}{2i(i+3)}\,,\,Res(i)=\frac{e^{it}}{2i(i-3)}\,,\,Res(3)=\frac{e^{3t}}{(3+i)(3-i)}
\end{aligned}$$ $$\begin{aligned}
    y(t)=\frac{1}{2\pi i}\cdot 2\pi i \left(Res(-i)+Res(i)+Res(3)\right)=\frac{e^{-it}}{2i(i+3)}+\frac{e^{it}}{2i(i-3)}+\frac{e^{3t}}{(3+i)(3-i)}\\
    =-\frac{3}{10}\sin{t}-\frac{1}{10}\cos{t}+\frac{1}{10}e^{3t}
\end{aligned}$$ 다른방법으로 풀어도 같은 결과를 주는 것을 확인할 수 있을
것이다.\
다시 이 풀이법을 요약해보면, 다음과 같다.\
1. 미분방정식이 있다.\
2. 라플라스변환을 통해 s 영역에서 미분방정식을 살펴본다.
$y(t)\rightarrow \tilde{y}(s)$\
3. 그럼 간단한 대수방정식이 되고 이를 풀어서 $\tilde{y}(s)$를 구한다.\
4. 라플라스 역변환을 통해 $y(t)$를 구한다.\
5. 라플라스 변환의 적분식에서 일반적으로 칸토어 적분을 이용하여
계산한다.\
이 흐름을 이해한채 그린함수 풀이법을 본 다면 이해가 쉬울 것이다.\
공대에서 공업수학시간에 라플라스 변환을 이용한 미분방정식 풀이를
배울때는 수학과나 물리학과처럼 일일히 라플라스 변환을 해주는 적분계산을
하지 않는다. 그러므로 복잡한 칸토어 적분을 할 필요도 없다. 그냥 라플라스
변환표에 있는 결과를 가져다 쓰는 것이 정석이다. 하지만 역시 공대는
맘에들지 않는다.\
이제 본격적으로 여러 문제를 살펴보면서 각 시스템의 그린함수를 구해보자.

## 외력이 있는 조화진동자

외력이 작용하고 마찰이 있는 조화 진동자가 있다고 하자. 그 시스템은
다음과 같이 적을 수 있다. $$\begin{aligned}
    \left(\frac{\partial^2}{\partial t^2}+2\gamma\frac{\partial}{\partial t}+\omega_0^2\right)x(t)=f(t)
\end{aligned}$$ 이 방정식의 해($x(t)$)를 구하는 여러가지 방법이 있다.
제차해와 특수해를 구하고 더해서 일반해를 구하는 기본적인 방법이 있겠고,
$f(t)$가 주어져 있다면 라플라스 변환을 이용해 푸는 방법도 있고,
그린함수를 이용해 푸는 방법이 있다. 우리는 그린함수를 이용해 풀겠다.
그린함수를 이용해 푸는 것은 라플라스 변환을 이용해 푸는 것과 유사한
느낌이 있다. 그 것이 내가 그린함수 풀이법의 인사이트로 라플라스변환을
언급한 이유이다.\
그린함수의 정의에 따라 다음을 만족하는 그린함수$G(t,t')$를 찾자.
$$\begin{aligned}
    \left(\frac{\partial^2}{\partial t^2}+2\gamma\frac{\partial}{\partial t}+\omega_0^2\right)G(t,t')=\delta(t-t')
\end{aligned}$$ 역시 어쩌나 저쩌나 무슨 방법이 됐던 위 조건을 만족하는
그린함수만 찾으면 장땡이다. 그런데 막막하다. 도대체 어떤 함수를 넣어야
우변이 델타함수가 나올까. 방정식을 그대로 보면 어려우니, 우리는 이
문제를 어떤 변환을 통해서 대수방정식으로 바꾸어 보고 싶다(라플라스변환을
이용해 미분방정식을 풀었던 철학과 동일하게). 푸리에 변환을 해서 주파수
영역에서 방정식을 살펴보면 우변의 델타함수는 그냥 1이 되어 아주
간단해진다.\
위 미분방정식을 대수방정식으로 바꾸기 위해 푸리에 변환을
사용하겠다(라플라스 변환대신). $$\begin{aligned}
    G(t,t')= \frac{1}{2\pi}\int \tilde{G}(w)e^{iw(t-t')}dw
\end{aligned}$$ 위 미분방정식에 대입해보면,\
$$\begin{aligned}
    &\frac{\partial^2}{\partial t^2}\left(\frac{1}{2\pi}\int \tilde{G}(w)e^{iw(t-t')}dw\right)+2\gamma\frac{\partial}{\partial t}\left(\frac{1}{2\pi}\int \tilde{G}(w)e^{iw(t-t')}dw\right)+\omega_0^2\left(\frac{1}{2\pi}\int \tilde{G}(w)e^{iw(t-t')}dw\right)\\
    &=\delta(t-t')=\frac{1}{2\pi}\int e^{iw(t-t')}dw
\end{aligned}$$ 미분을 수행한 후 정리하면 다음과 같다. $$\begin{aligned}
    \frac{1}{2\pi}\int \left( -w^2+2\gamma iw+\omega_0^2\right)\tilde{G}(w)e^{iw(t-t')}dw=\frac{1}{2\pi}\int e^{iw(t-t')}dw
\end{aligned}$$ 이 식을 만족하기 위해선, $$\begin{aligned}
    (-w^2+2\gamma iw+\omega_0^2)\tilde{G}(w)=1
\end{aligned}$$ 이 되어야 한다. 푸리에 변환을 통해 시간영역이 아닌
주파수영역에서 살펴봄으로써 미분방정식이 대수방정식이 되었다.\
이 대수방정식은 양변을 $(-w^2+2\gamma iw+\omega_0^2)$로 나눠줌으로써
간단히 구할 수 있다.\
$$\begin{aligned}
    \tilde{G}(w)=-\frac{1}{(w^2-2\gamma iw-\omega_0^2)}\,.
\end{aligned}$$ 인수분해하면 다음과 같이 쓸 수 있다. $$\begin{aligned}
    \tilde{G}(w)=-\frac{1}{\left(w-(i\gamma+\sqrt{\omega_0^2-\gamma^2}\,)\right)\left(w-(i\gamma-\sqrt{\omega_0^2-\gamma^2}\,)\right)}
\end{aligned}$$ 주파수 영역의 그린함수를 구했으므로 이제 푸리에 역변환을
해주어 본래 그린함수를 구해보자.\
$$\begin{aligned}
    &G(t,t')= \frac{1}{2\pi}\int \tilde{G}(w)e^{iw(t-t')}dw\\
    &=\frac{-1}{2\pi}\int\frac{e^{iw(t-t')}}{\left(w-(i\gamma+\sqrt{\omega_0^2-\gamma^2}\,)\right)\left(w-(i\gamma-\sqrt{\omega_0^2-\gamma^2}\,)\right)}dw
\end{aligned}$$ 이 적분을 계산하기 위해선 복소평면에서 칸토어 적분을
해야한다. Residue 정리를 이용하여 계산해보자. 위 쪽 반원으로 적분하는
경우엔 적분이 발산하지 않기 위해(?) $t>t'$이 되어야 한다. $t<t'$ 아래쪽
반원으로 적분하는 경우엔 다음과 같다. $0$이 된다.

$$\begin{aligned}
    G(t,t')=-\frac{1}{2\pi}\cdot 2\pi i \left[ Res\left(i\gamma+\sqrt{\omega_0^2-\gamma^2}\right)+ Res\left(i\gamma-\sqrt{\omega_0^2-\gamma^2}\right)\right]
\end{aligned}$$ $$\begin{aligned}
Res\left(i\gamma+\sqrt{\omega_0^2-\gamma^2}\right)=\frac{e^{i\left(i\gamma+\sqrt{\omega_0^2-\gamma^2}\right)(t-t')}}{2\sqrt{\omega_0^2-\gamma^2}}\,,\,\\
Res\left(i\gamma-\sqrt{\omega_0^2-\gamma^2}\right)=-\frac{e^{i\left(i\gamma-\sqrt{\omega_0^2-\gamma^2}\right)(t-t')}}{2\sqrt{\omega_0^2-\gamma^2}}\,.
\end{aligned}$$

$$\begin{aligned}
    G(t,t')=\frac{-i}{2\sqrt{\omega_0^2-\gamma^2}}\left(e^{i\left(i\gamma+\sqrt{\omega_0^2-\gamma^2}\right)(t-t')}-e^{i\left(i\gamma-\sqrt{\omega_0^2-\gamma^2}\right)(t-t')}\right)\\
    =\frac{-ie^{-\gamma (t-t')}}{2\sqrt{\omega_0^2-\gamma^2}}\left(e^{i\left(\sqrt{\omega_0^2-\gamma^2}\right)(t-t')}-e^{-i\left(\sqrt{\omega_0^2-\gamma^2}\right)(t-t')}\right)
    =\frac{e^{-\gamma (t-t')}}{\sqrt{\omega_0^2-\gamma^2}}\sin{\left(\sqrt{\omega_0^2-\gamma^2}(t-t')\right)}
\end{aligned}$$

$$\begin{aligned}
    G(t,t')=\Theta(t-t')\frac{e^{-\gamma (t-t')}}{\sqrt{\omega_0^2-\gamma^2}}\sin{\left(\sqrt{\omega_0^2-\gamma^2}(t-t')\right)}
\end{aligned}$$ 미분을 해서 델타함수가 나와야하므로 계단함수가 들어가는
것은 타당해보인다.

## 푸아송 방정식(쿨롱게이지)

다음은 쿨롱게이지를 잡았을 때 푸아송 방정식이다. $$\begin{aligned}
    \nabla^2V(x,y,z)=-\frac{\rho(x,y,z)}{\epsilon_0}
\end{aligned}$$ 그린함수의 정의에 따라 다음을 만족하는
$G(x,x',y,y',z,z')$을 찾자.\
$$\begin{aligned}
    \nabla^2G(x,x',y,y',z,z')=-\frac{\delta(x-x')\delta(y-y')\delta(z-z')}{\epsilon_0}
\end{aligned}$$

푸아송 방정식을 풀때 역시 그린함수만 알면 해를 구할 수 있다. 푸아송
방정식의 그린함수를 어떻게 구할까? 문제상황에 따라 그린함수를 구하는
여러가지 테크닉이 있다.

$$\begin{aligned}
    G(x,x',y,y',z,z')=\frac{1}{(2\pi)^3}\int \tilde{G}(k_x,k_y,k_z)e^{ik_x(x-x')+ik_y(y-y')+ik_z(z-z')}d^3k=\frac{1}{(2\pi)^3}\int \tilde{G}(k_x,k_y,k_z)e^{i\vec{k}\cdot (\vec{r}-\vec{r'})}d^3k
\end{aligned}$$ $$\begin{aligned}
    \nabla^2\frac{1}{(2\pi)^3}\int \tilde{G}(k_x,k_y,k_z)e^{i\vec{k}\cdot (\vec{r}-\vec{r'})}d^3k=\frac{1}{(2\pi)^3}\int(-k_x^2-k_y^2-k_z^2)\tilde{G}(k_x,k_y,k_z)e^{i\vec{k}\cdot (\vec{r}-\vec{r'})}d^3k
    =-\frac{1}{\epsilon_0}\frac{1}{(2\pi)^3}\int e^{i\vec{k}\cdot(\vec{r}-\vec{r'})}d^3k
\end{aligned}$$ $$\begin{aligned}
    (-k_x^2-k_y^2-k_z^2)\tilde{G}(k_x,k_y,k_z)=-\frac{1}{\epsilon_0}
\end{aligned}$$ $$\begin{aligned}
    \tilde{G}(k_x,k_y,k_z)=\frac{1}{\epsilon_0(k_x^2+k_y^2+k_z^2)}=\frac{1}{\epsilon_0k^2}\,,\,(k^2=k_x^2+k_y^2+k_z^2)
\end{aligned}$$ $$\begin{aligned}
    G(x,x',y,y',z,z')=\frac{1}{(2\pi)^3}\int \tilde{G}(k_x,k_y,k_z)e^{i\vec{k}\cdot (\vec{r}-\vec{r'})}d^3k=\frac{1}{(2\pi)^3}\int \frac{1}{\epsilon_0k^2}e^{i\vec{k}\cdot (\vec{r}-\vec{r'})}d^3k\\
    =\frac{1}{(2\pi)^3\epsilon_0}\int \frac{1}{k^2}e^{ikr\cos{\theta}}k^2\sin{\theta}dkd\theta d\phi
\end{aligned}$$ $$\begin{aligned}
    \int_{0}^{\pi} e^{ik(r-r')\cos{\theta}}\sin{\theta}d\theta
\end{aligned}$$ $\cos{\theta}=t$로 치환하면,

$$\begin{aligned}
    -\int_{1}^{-1} e^{ik(r-r')t}dt=\frac{1}{ik(r-r')}e^{ik(r-r')t} |_{-1}^{1}
    =\frac{1}{ik(r-r')}(e^{ik(r-r')}-e^{-ik(r-r')})
\end{aligned}$$

$$\begin{aligned}
    \frac{1}{(2\pi)^3\epsilon_0}\int \frac{1}{ik(r-r')}(e^{ik(r-r')}-e^{-ik(r-r')})dkd\phi=\frac{1}{(2\pi)^2\epsilon_0i(r-r')}\int_{0}^{\infty} \frac{1}{k}(e^{ik(r-r')}-e^{-ik(r-r')})dk
\end{aligned}$$

$$\begin{aligned}
    \int_{-\infty}^{\infty} \frac{1}{k}e^{ik(r-r')}dk=\int_{0}^{\infty} \frac{1}{k}e^{ik(r-r')}dk+\int_{-\infty}^{0} \frac{1}{k}e^{ik(r-r')}dk=\int_{0}^{\infty} \frac{1}{k}e^{ik(r-r')}dk+\int_{\infty}^{0} \frac{1}{k}e^{-ik(r-r')}dk\\
    =\int_{0}^{\infty} \frac{1}{k}e^{ik(r-r')}dk-\int_{0}^{\infty} \frac{1}{k}e^{-ik(r-r')}dk
\end{aligned}$$ $$\begin{aligned}
\lim _{\rho \to 0} \int_{\pi}^{0}\frac{1}{\rho e^{i\theta}}e^{i(r-r')\rho e^{i\theta}}\rho ie^{i\theta}d\theta=-i\pi
\end{aligned}$$ $$\begin{aligned}
    \frac{1}{(2\pi)^2\epsilon_0i(r-r')}\int_{0}^{\infty} \frac{1}{k}(e^{ik(r-r')}-e^{-ik(r-r')})dk=\frac{1}{4\pi\epsilon_0}\frac{1}{r-r'}
\end{aligned}$$ $$\begin{aligned}
    G(r,r')=\frac{1}{4\pi\epsilon_0}\frac{1}{r-r'}
\end{aligned}$$

푸아송 방정식의 그린함수를 구해보자.

$R=|r-r'|=\sqrt{(x-x')^2+(y-y')^2+(z-z')^2}$ $$\begin{aligned}
    \nabla\left(\frac{1}{R}\right) = -\frac{(x-x')\hat{x}+(y-y')\hat{y}+(z-z')\hat{z}}{({(x-x')^2+(y-y')^2+(z-z')^2})^{\frac{3}{2}}}=-\frac{\vec{R}}{R^3}=-\frac{\hat{R}}{R^2}
\end{aligned}$$ $$\begin{aligned}
\nabla\cdot\left(\frac{\hat{R}}{R^2}\right)=4\pi\delta(r-r')
\end{aligned}$$ 부록을 참고하자. $$\begin{aligned}
    \nabla\cdot\left(\frac{\hat{R}}{R^2}\right)=\nabla\cdot\left(-\nabla\left(\frac{1}{R}\right)\right)=-\nabla^2\left(\frac{1}{R}\right)=-\nabla^2\left(\frac{1}{|r-r'|}\right)=4\pi\delta(r-r')
\end{aligned}$$ 따라서 우리는 최종적으로 다음과 같은 식을 얻게 되었다.
$$\begin{aligned}
\nabla^2\left(\frac{1}{|r-r'|}\right)=-4\pi\delta(r-r')    
\end{aligned}$$ 위 식의 양변에 상수 $\frac{q}{4\pi\epsilon_0}$를
곱해주면 우리가 원래 구하고자 했던 푸아송방정식의 형태와 같아진다!
$$\begin{aligned}
\nabla^2\left(\frac{q}{4\pi\epsilon_0}\frac{1}{|r-r'|}\right)=-\frac{q\delta(r-r')}{\epsilon_0}\\
\rightarrow G(r,r')=\frac{1}{4\pi\epsilon_0}\frac{1}{|r-r'|}
\end{aligned}$$

그런데 사실 좌변 괄호안의 식은 우리가 잘 알고 있는 '점전하'에 대한 전위
식이다! 결국 푸아송 방정식의 그린함수는 점전하에서의 해인 것이다.
그린함수란 입력함수가 델타함수일때의 출력함수이다. 여기서의 입력함수는
전하분포인데 이것을 델타함수로 보겠다는 것은 점전하를 의미한다고 할 수
있다. 따라서 점전하에서의 해가 푸아송방정식의 그린함수가 되는 것은
물리적으로도 아주 타당하다.\
이제 그린함수를 구했으니 일반적인 전하분포에 대한 푸아송방정식의 해를
구할 수 있다(100원을 넣었을 때 얼마가 나오는지 알았으니 이제 얼마를
넣어도 값을 예측할 수 있다). 따라서 푸아송 방정식의 해를 다음과 같이
구할 수 있다. $$\begin{aligned}
    V(r)=\int G(r,r')f(r')dr'=\frac{1}{4\pi\epsilon_0}\int\frac{1}{|r-r'|}\rho(r')dr'
\end{aligned}$$

## 헬름홀츠 방정식

$$\begin{aligned}
    (\nabla^2+w^2)\phi(x,y,z)=-j(x,y,z)
\end{aligned}$$ $$\begin{aligned}
    (\nabla^2+w^2)G(x,x',y,y',z,z')=-\delta(x-x')\delta(y-y')\delta(z-z')
\end{aligned}$$ $$\begin{aligned}
    G(x,x',y,y',z,z')=\frac{1}{2\pi}\int \tilde{G}(k_x,k_y,k_z)e^{ik_x(x-x')+ik_y(y-y')+ik_z(z-z')}d^3k=\frac{1}{2\pi}\int \tilde{G}(k_x,k_y,k_z)e^{i\vec{k}\cdot (\vec{r}-\vec{r'})}d^3k
\end{aligned}$$ $$\begin{aligned}
     \nabla^2\left(\frac{1}{2\pi}\int \tilde{G}(k_x,k_y,k_z)e^{i\vec{k}\cdot (\vec{r}-\vec{r'})}d^3k\right)+\frac{w^2}{2\pi}\int \tilde{G}(k_x,k_y,k_z)e^{i\vec{k}\cdot (\vec{r}-\vec{r'})}d^3k
 
\end{aligned}$$ $$\begin{aligned}
=\frac{1}{2\pi}\int (-k_x^2-k_y^2-k_z^2+w^2)\tilde{G}(k_x,k_y,k_z)e^{i\vec{k}\cdot (\vec{r}-\vec{r'})}d^3k=-\frac{1}{2\pi}\int e^{i\vec{k}\cdot(\vec{r}-\vec{r'})}d^3k
\end{aligned}$$

$$\begin{aligned}
    (k_x^2+k_y^2+k_z^2-w^2)\tilde{G}(k_x,k_y,k_z)=1
\end{aligned}$$

$$\begin{aligned}
    \tilde{G}(k_x,k_y,k_z)=\frac{1}{(k_x^2+k_y^2+k_z^2-w^2)}=\frac{1}{(k^2-w^2)}\,,\,(k^2=k_x^2+k_y^2+k_z^2)
\end{aligned}$$ 이 푸리에 변환을 직각좌표계에서 하면 계산이 복잡해진다.
그러므로 구면좌표계로 바꾸어 계산해보겠다. $$\begin{aligned}
    G(r,r')=\frac{1}{2\pi}\int \tilde{G}(k)e^{i\vec{k}\cdot (\vec{r}-\vec{r'})}k^2\sin{\theta}\,dkd\theta d\phi=\frac{1}{2\pi}\int \frac{1}{(k^2-w^2)}e^{ik(r-r')\cos{\theta}}k^2\sin{\theta}\,dkd\theta d\phi
    
\end{aligned}$$ $$\begin{aligned}
    \int_{0}^{\pi} e^{ik(r-r')\cos{\theta}}\sin{\theta}d\theta
\end{aligned}$$ $\cos{\theta}=t$로 치환하면,

$$\begin{aligned}
    -\int_{1}^{-1} e^{ik(r-r')t}dt=\frac{1}{ik(r-r')}e^{ik(r-r')t} |_{-1}^{1}
    =\frac{1}{ik(r-r')}(e^{ik(r-r')}-e^{-ik(r-r')})
\end{aligned}$$

$$\begin{aligned}
    \frac{1}{2\pi}\int \frac{1}{k^2-w^2}\cdot\frac{1}{ik(r-r')}(e^{ik(r-r')}-e^{-ik(r-r')})k^2 dk d\phi\\
    =\frac{1}{i(r-r')}\int \frac{k}{k^2-w^2}\cdot(e^{ik(r-r')}-e^{-ik(r-r')}) dk\\
    =\frac{1}{i(r-r')}\int_{0}^{\infty} \frac{k}{(k+w)(k-w)}\cdot(e^{ik(r-r')}-e^{-ik(r-r')}) dk
\end{aligned}$$ 역시 칸토어적분을 통해 계산한다. 위 식을 변형하면
$\int_{0}^{\infty} \frac{k}{(k+w)(k-w)}\cdot(e^{ik(r-r')}-e^{-ik(r-r')}) dk=\int_{-\infty}^{\infty} \frac{k}{(k+w)(k-w)}\cdot e^{ik(r-r')} dk$와
같이 만들수 있다. 적분경로는 다음과 같이 잡는다.

그런데 적분 경로상에 특이점이 있으므로 이 부분을 우회해서 계산해야 한다.
$$\begin{aligned}
    \int_{-\infty}^{\infty} \frac{k}{(k+w)(k-w)}\cdot e^{ik(r-r')} dk
\end{aligned}$$ $z=-w+\rho e^{i\theta}\,(dz=i\rho e^{i\theta}d\theta)$
로 치환하여 $-w$에 있는 특이점 주위를 반원을 그리며 우회하는 적분경로로
계산해보자. 이때 위쪽 작은 반원을 잡으나 아래쪽 작은 반원을 잡으나
상관없다. $$\begin{aligned}
    \int_{\pi}^{0} \frac{-w+\rho e^{i\theta}}{(-w+\rho e^{i\theta}+w)(-w+\rho e^{i\theta}-w)}\cdot e^{i(-w+\rho e^{i\theta})(r-r')}i\rho e^{i\theta}d\theta\\
    =\int_{\pi}^{0} \frac{-w+\rho e^{i\theta}}{(\cancel{\rho e^{i\theta}})(\rho e^{i\theta}-2w)}\cdot e^{i(-w+\rho e^{i\theta})(r-r')}i\cancel{\rho e^{i\theta}}d\theta
=\int_{\pi}^{0} \frac{-w+\rho e^{i\theta}}{\rho e^{i\theta}-2w}\cdot e^{i(-w+\rho e^{i\theta})(r-r')}id\theta    
\end{aligned}$$ 이제 $\rho\rightarrow0$의 극한을 취해주자.
$$\begin{aligned}
    \frac{1}{2}\int_\pi^0 e^{-iw(r-r')}id\theta=\frac{-i\pi}{2} e^{-iw(r-r')}
\end{aligned}$$ $z=w+\rho e^{i\theta}\,(dz=i\rho e^{i\theta}d\theta)$ 로
치환하여 $w$에 있는 특이점 주위를 반원을 그리며 우회하는 적분경로로
계산해보자.

$$\begin{aligned}
    \int_{\pi}^{0} \frac{w+\rho e^{i\theta}}{(w+\rho e^{i\theta}+w)(w+\rho e^{i\theta}-w)}\cdot e^{i(w+\rho e^{i\theta})(r-r')}i\rho e^{i\theta}d\theta\\
    =\int_{\pi}^{0} \frac{w+\rho e^{i\theta}}{(\rho e^{i\theta}+2w)(\cancel{\rho e^{i\theta})}}\cdot e^{i(w+\rho e^{i\theta})(r-r')}i\cancel{\rho e^{i\theta}}d\theta
=\int_{\pi}^{0} \frac{w+\rho e^{i\theta}}{\rho e^{i\theta}+2w}\cdot e^{i(w+\rho e^{i\theta})(r-r')}id\theta    
\end{aligned}$$ 이제 $\rho\rightarrow0$의 극한을 취해주자.
$$\begin{aligned}
    \frac{1}{2}\int_\pi^0 e^{iw(r-r')}id\theta=\frac{-i\pi}{2} e^{iw(r-r')}
\end{aligned}$$

$$\begin{aligned}
    \int_{-\infty}^{\infty} \frac{k}{(k+w)(k-w)}\cdot e^{ik(r-r')} dk=\frac{i\pi}{2}(e^{iw(r-r')}+e^{-iw(r-r')})
\end{aligned}$$ 따라서 정리하면,\
$$\begin{aligned}
G(r,r')=\frac{1}{i(r-r')}\frac{i\pi}{2}(e^{iw(r-r')}+e^{-iw(r-r')})
\end{aligned}$$ 그런데 결과를 보면 다른 자료에서 본 것과 조금 다를
것이다. 일단 내가 생각하기엔 여기서 $(r-r')\rightarrow \infty$인 극한에
대해 $G(r,r')=0$이 되는 경계조건을 만족해야 함으로 첫째항을 없애준다.
그러면 원하는 결과가 나온다. 확신이 서진 않는다. 칸토어 적분과정에서
무언가 잘못되었을 수도 있고 다른 가능성도 있다. 하지만 그것은 이 글을
읽는 이들의 몫으로 남겨두고 혹시 답을 알고있다면 나에게 알려주길
부탁드린다(너무 오래고민했더니 머리가 아프다).

최종 결과는 $$\begin{aligned}
    G(r,r')=\frac{1}{4\pi(r-r')}e^{-iw(r-r')}
\end{aligned}$$

## 푸아송 방정식(로렌츠게이지), 비제차 파동방정식

$$\begin{aligned}
-\frac{\partial^2}{\partial t^2}V(t,x,y,z)+\nabla^2 V(t,x,y,z)=-\frac{\rho(t,x,y,z)}{\epsilon_0}
\end{aligned}$$ $$\begin{aligned}
    -\frac{\partial^2}{\partial t^2}G(t,t',x,x',y,y',z,z')+\nabla^2 G(t,t',x,x',y,y',z,z')=-\frac{\delta(t-t')\delta(x-x')\delta(y-y')\delta(z-z')}{\epsilon_0}
\end{aligned}$$

$$\begin{aligned}
    G(t,t',x,x',y,y',z,z')=\frac{1}{(2\pi)^4}\int \tilde{G}(w,k_x,k_y,k_z)e^{i(\vec{k}\cdot\vec{(r-r')}-w(t-t'))} dwd^3k
\end{aligned}$$ 이 푸리에 변환식을 위 미분방정식에 대입해보면,\
$$\begin{aligned}
    \frac{1}{(2\pi)^4}\int \tilde{G}(w,k_x,k_y,k_z)[-(-iw)^2+(ik)^2]e^{i(\vec{k}\cdot\vec{(r-r')}-w(t-t'))} dwd^3k=-\frac{1}{(2\pi)^4\epsilon_0}\int e^{i(\vec{k}\cdot(\vec{r}-\vec{r'})-w(t-t')}dwd^3k
\end{aligned}$$ 와 같이 된다. 정리하면 다음과 같다. $$\begin{aligned}
    \tilde{G}(w,k_x,k_y,k_z)(w^2-k^2)=-\frac{1}{\epsilon_0}
\end{aligned}$$ 미분방정식이 대수방정식이 되었고 이제
양변을$(w^2-k^2)$으로 나누어 주면 쉽게 풀린다. $$\begin{aligned}
    \tilde{G}(w,k_x,k_y,k_z)=-\frac{1}{\epsilon_0(w^2-k^2)}=\frac{1}{\epsilon_0(k^2-w^2)}
\end{aligned}$$ $\tilde{G}(w,k_x,k_y,k_z)$를 얻었으니 다음 식을 계산해서
$G(t,t',x,x',y,y',z,z')$을 구해야한다. $$\begin{aligned}
     G(t,t',x,x',y,y',z,z')=\frac{1}{(2\pi)^4}\int \tilde{G}(w,k_x,k_y,k_z)e^{i(\vec{k}\cdot\vec{(r-r')}-w(t-t'))} dwd^3k=\\
     \frac{1}{(2\pi)^4}\int \frac{1}{\epsilon_0(k^2-w^2)}e^{i(\vec{k}\cdot\vec{(r-r')}-w(t-t'))} dwd^3k=\frac{1}{2\pi\epsilon_0}\int\left(\frac{1}{(2\pi)^3}\int \frac{1}{(k^2-w^2)}e^{i\vec{k}\cdot\vec{(r-r')}}d^3k\right)e^{-iw(t-t')}\,dw
\end{aligned}$$ 그런데 괄호 안의 식을 잘 보면 우리가 헬름홀츠 방정식에서
구했던 식과 완전히 같은 형태이다. 따라서 그 결과를 가져다 쓸 수 있다.\
$$\begin{aligned}
    \frac{1}{2\pi\epsilon_0}\int\left(-\frac{e^{ik(r-r')}}{4\pi (r-r')}\right)e^{-iw(t-t')}dw=\frac{-1}{4\pi\epsilon_0 (r-r')}\frac{1}{2\pi}\int e^{i(k(r-r')-w(t-t'))}dw\\
    =\frac{-1}{4\pi\epsilon_0 (r-r')}\frac{1}{2\pi}\int e^{iw(\frac{(r-r')}{c}-(t-t'))}dw
\end{aligned}$$

델타함수의 성질을 이용하여 정리하면 다음과 같다.\
$$\begin{aligned}
    G(t,t',r,r')=-\frac{1}{4\pi\epsilon_0 (r-r')}\,\delta\left(t-t'-\frac{r-r'}{c}\right)
\end{aligned}$$

## 파인만 전파인자(클라인고든 방정식)

$$\begin{aligned}
    (\partial^2+m^2)\phi(x_\mu)=-j(x_\mu)
\end{aligned}$$ $$\begin{aligned}
    (\partial^2+m^2)G(x_\mu,y_\mu)=-\delta(x_\mu-y_\mu)
\end{aligned}$$

$$\begin{aligned}
    G(x_\mu,y_\mu)=\frac{1}{(2\pi)^4}\int \tilde{G}(k_\mu)e^{ik^\mu(x_\mu-y_\mu)}d^4k
\end{aligned}$$ $$\begin{aligned}
    \frac{1}{(2\pi)^4}\int \tilde{G}(k_\mu)(-k^2+m^2)e^{ik^\mu(x_\mu-y_\mu)}d^4k
    =-\frac{1}{(2\pi)^4}\int e^{ik^\mu(x_\mu-y_\mu)}d^4k
\end{aligned}$$

양변을 비교해보면, $\tilde{G}(k_\mu)(-k^2+m^2)=-1$ 가 된다.

이 대수방정식을 양변을 $(-k^2+m^2)$ 으로 나누어주면 다음과 같다.
$$\begin{aligned}
    \tilde{G}(k_\mu)=\frac{1}{k^2-m^2}
\end{aligned}$$ 원래 그린함수를 구해보면, $$\begin{aligned}
    G(x_\mu,y_\mu)=\frac{1}{(2\pi)^4}\int \tilde{G}(k_\mu)e^{ik^\mu(x_\mu-y_\mu)}d^4k=\frac{1}{(2\pi)^4}\int \frac{1}{k^2-m^2}e^{ik^\mu(x_\mu-y_\mu)}d^4k
\end{aligned}$$

이 적분식은 끝까지 계산하지는 않겠다.\
그런데 이 적분식은 우리가 전에 했던 계산처럼 역시 실수축 위에 특이점이
있다. 파인만은 이 적분을 계산하기 위해 다음과 같은 트릭을 썼다.\
$$\begin{aligned}
\frac{1}{k^2-m^2}\rightarrow\frac{1}{k^2-m^2\pm(i\epsilon)}
\end{aligned}$$ 아주 작은 $\epsilon$에 대해 위와 같은 변형을 통해서
실수축에 놓여있는 특이점을 위(또는 아래)로 약간 밀어내어, 실수축을
포함하는 적분이 가능하도록 한 것이다. 실수축 위에 있는 두개의 특이점을
어떻게 밀어내는냐에 따라 어떤 게이지 인지가 결정되는데 자세한 것은
입자물리 교재를 찾아보길 바란다.

# 부록

## Contour integral {#contour-integral .unnumbered}

## Divergence of $1/r^2$ {#divergence-of-1r2 .unnumbered}

$$\begin{aligned}
\nabla\cdot\left(\frac{\hat{R}}{R^2}\right)=4\pi\delta(r-r')
\end{aligned}$$
