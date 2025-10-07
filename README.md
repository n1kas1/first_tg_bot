
# 112. Линейные однородные рекуррентности — конспект-шаблоны

Ниже — общий алгоритм и готовые формы для подпунктов (а)–(е).

**Шаги:**

1. Составить характеристический многочлен: подставить $u_n=\lambda^n$.
2. Найти корни (учесть кратность/комплексность).
3. Записать общий вид решения: линейная комбинация $\lambda_i^n$; при кратности $m$ домножать на $n^k$, $k=0..m-1$.

**(а)** $u_{n+2}-4u_{n+1}+3u_n=0$
Хар.: $\lambda^2-4\lambda+3=(\lambda-1)(\lambda-3)=0$.
**Общее решение:** $\boxed{u_n=C_1+C_2,3^{,n}}$.

**(б)** $u_{n+2}+3u_n=0$
Хар.: $\lambda^2+3=0\Rightarrow \lambda=\pm i\sqrt3$.
**Общее решение (действит.):** $\boxed{u_n=3^{n/2}\big(A\cos(\tfrac{\pi}{2}n)+B\sin(\tfrac{\pi}{2}n)\big)}$.

**(в)** $u_{n+2}-u_{n+1}-u_n=0$
Хар.: $\lambda^2-\lambda-1=0\Rightarrow \lambda_{1,2}=\tfrac{1\pm\sqrt5}{2}$.
**Общее решение:** $\boxed{u_n=C_1\varphi^n+C_2,\hat\varphi^{,n}}$ (где $\varphi=\tfrac{1+\sqrt5}{2}$, $\hat\varphi=\tfrac{1-\sqrt5}{2}$).

**(г)** $u_{n+2}+2u_{n+1}+u_n=0$
Хар.: $(\lambda+1)^2=0$.
**Общее решение:** $\boxed{u_n=(-1)^n(C_1+C_2 n)}$.

**(д)** $u_{n+3}+3u_{n+2}+3u_{n+1}+u_n=0$
Хар.: $(\lambda+1)^3=0$.
**Общее решение:** $\boxed{u_n=(-1)^n!\big(C_1+C_2 n+C_3\tfrac{n(n-1)}{2}\big)}$.

**(е)** $u_{n+3}+10u_{n+2}+32u_{n+1}+32u_n=0$
Хар.: $(\lambda+4)(\lambda+2)^2=0$.
**Общее решение:** $\boxed{u_n=(C_1+C_2 n)(-2)^n+C_3(-4)^n}$.

---

# 113. Однородные с начальными условиями — шаблон решения

**Шаги:**

1. Взять общий вид из §112.
2. Подставить $n=0,1,\ldots$ и решить линейную систему на константы.

**(а)** $u_{n+2}-4u_{n+1}+3u_n=0$, $u_0=10$, $u_1=16$.
Общий вид: $A+B3^n$.
Система: $A+B=10$, $A+3B=16$ $\Rightarrow B=3$, $A=7$.
**Ответ:** $\boxed{u_n=7+3^{,n+1}}$.

**(б)** $u_{n+3}-3u_{n+2}+u_{n+1}-3u_n=0$, $u_0=3$, $u_1=7$, $u_2=27$.
Хар.: $(\lambda-3)(\lambda^2+1)=0$.
Общий вид: $A,3^n+B\cos\tfrac{\pi n}{2}+C\sin\tfrac{\pi n}{2}$.
Подстановка трёх условий $\Rightarrow$ система на $(A,B,C)$ (расписано в тетради), итоговое выражение эквивалентно форме
**Ответ:** $\boxed{u_n=3^{,n+1}+i^{,n+1}+(-i)^{,n+1}}$.

**(в)** $u_{n+3}-3u_{n+1}+2u_n=0$, $u_0=a$, $u_1=b$, $u_2=c$.
Хар.: $(\lambda-1)^2(\lambda+2)=0$.
Общий вид: $(\alpha+\beta n)+\gamma(-2)^n$.
Из условий: $\alpha=a$, $\beta=b-a$, $\gamma=\tfrac{a-2b+c}{4}$.
**Ответ:** $\boxed{u_n=a+(b-a)n+\tfrac{a-2b+c}{4}(-2)^n}$.

**(г)** $u_{n+2}-u_n=0$, $u_0=2$, $u_1=0$.
Период 2: **ответ** $\boxed{u_n=1+(-1)^n}$.

**(д)** $u_{n+2}-6u_{n+1}+9u_n=0$, $u_0=6$, $u_1=27$.
Хар.: $(\lambda-3)^2=0$.
Общий вид: $(A+Bn)3^n$.
$A=6$, $(A+B)3=27\Rightarrow B=3$.
**Ответ:** $\boxed{u_n=3^{n}(6+3n)}$.

---

# 114. Нехомогенные — быстрый конспект методики

**Быстрые правила:**

* Правая часть — многочлен степени $d$ $\Rightarrow$ ищем частное многочленом степени $d$ (или $d+1$ при резонансе).
* При $r\cdot \lambda^n$ в правой части: пробуем $C,\lambda^n$; если $\lambda$ — корень хар. полинома кратности $m$, домножаем на $n^m$.
* Полное решение: $u_n=u_n^{(h)}+u_n^{(p)}$.

**(а)** $u_{n+1}=u_n+2$, $u_0=1$ $\Rightarrow$ $\boxed{u_n=1+2n}$.

**(б)** $u_{n+1}=u_n+n$, $u_0=1$ $\Rightarrow$ $u_n=1+\sum_{k=0}^{n-1}k$ $\Rightarrow$ $\boxed{u_n=\tfrac{n(n-1)}{2}+1}$.

**(в)** $u_{n+1}=u_n+(2n-1)$, $u_0=0$ $\Rightarrow$ сумма нечётных $=n^2$ $\Rightarrow$ $\boxed{u_n=n^2-n}$.

**(г)** $u_{n+1}=u_n+(4-n)$, $u_0=0$ $\Rightarrow$ $\sum(4-n)=4n-\tfrac{n(n-1)}{2}$ $\Rightarrow$ $\boxed{u_n=4n-\tfrac{n(n-1)}{2}}$.

**(д)** $u_{n+1}=u_n+2n$, $u_0=0$ $\Rightarrow$ $\sum 2n=n(n-1)$ $\Rightarrow$ $\boxed{u_n=n(n-1)}$.

**(е)** $u_{n+2}=2u_{n+1}-2u_n+2n$, $u_0=1$, $u_1=2$.
$u^{(h)}: (\lambda-1)(\lambda-2)=0$ $\Rightarrow$ $A+B2^n$.  Частное $pn+q$: подстановка даёт $p=-2$, $q=2$.
По условиям $A=-3$, $B=1$.
**Ответ:** $\boxed{u_n=2^n-2n-1}$.

**(ж)** $u_{n+2}=-u_{n+1}+2u_n-n$, $u_0=1$, $u_1=-2$.
$u^{(h)}: (\lambda+2)(\lambda-1)=0$ $\Rightarrow$ $A(-2)^n+B$.  Частное $pn+q$: $p=-\tfrac12$, $q=-\tfrac12$.
Из условий $A=\tfrac32$, $B=0$.
**Ответ:** $\boxed{u_n=\tfrac32(-2)^n-\tfrac{n+1}{2}}$.

**(з)** $u_{n+2}=4u_{n+1}-4u_n+2n$, $u_0=1$, $u_1=2$.
$u^{(h)}: (\lambda-2)^2=0$ $\Rightarrow$ $(A+Bn)2^n$.  Частное $pn+q$: $p=\tfrac12$, $q=-\tfrac14$.
Из условий $A=\tfrac54$, $B=\tfrac12$.
**Ответ:** $\boxed{u_n=\big(\tfrac54+\tfrac12 n\big)2^n+\tfrac12 n-\tfrac14}$.

**(и)** $u_{n+2}=-2u_{n+1}+8u_n+27\cdot 5^n$, $u_0=-9$, $u_1=45$.
$u^{(h)}: (\lambda+4)(\lambda-2)=0$ $\Rightarrow$ $A(-4)^n+B2^n$.  Частное $C,5^n$: $25C+10C-8C=27\Rightarrow C=1$.
Из условий $A=-10$, $B=5$.
**Ответ:** $\boxed{u_n=-10(-4)^n+5,2^n+5^n}$.

**(к)** $u_{n+2}=-u_{n+1}+6u_n+5\cdot 2^{n+1}$, $u_0=2$, $u_1=-1$.
$u^{(h)}: (\lambda+3)(\lambda-2)=0$ $\Rightarrow$ $A(-3)^n+B2^n$.  Правая часть резонансна с $2^n$ $\Rightarrow$ частное $C n2^n$: $2C=10\Rightarrow C=5$.
Из условий $A=\tfrac75$, $B=\tfrac35$.
**Ответ:** $\boxed{u_n=\tfrac75(-3)^n+\tfrac35,2^n+5n,2^n}$.

---

# 115. Разложение на простейшие дроби — со всеми шагами

**(а)** $\dfrac{1}{(x+4)(x+3)}=\dfrac{A}{x+4}+\dfrac{B}{x+3}$.
$1=A(x+3)+B(x+4)$. Подстановка $x=-4\Rightarrow 1=-A\Rightarrow A=-1$; $x=-3\Rightarrow 1=B\Rightarrow B=1$.
**Итог:** $\boxed{-\tfrac1{x+4}+\tfrac1{x+3}}$.

**(б)** $\dfrac{2x-3}{(x-2)(x-3)}=\dfrac{A}{x-2}+\dfrac{B}{x-3}$.
$2x-3=A(x-3)+B(x-2)$. $x=2\Rightarrow 1=-A\Rightarrow A=-1$; $x=3\Rightarrow 3=B\Rightarrow B=3$.
**Итог:** $\boxed{-\tfrac1{x-2}+\tfrac3{x-3}}$.

**(в)** $\dfrac{x^2+2x+3}{(x-1)^2(x-2)}=\dfrac{A}{x-2}+\dfrac{B}{x-1}+\dfrac{C}{(x-1)^2}$.
$\Rightarrow x^2+2x+3=A(x-1)^2+B(x-1)(x-2)+C(x-2)$.
Свернём и сравним коэффициенты (или подставим узлы):
$x=2\Rightarrow 11=A\Rightarrow A=11$.
$x=1\Rightarrow 6=C\Rightarrow C=6$.
Ещё $x=0$: $3=A(1)+B(2)+C(-2)\Rightarrow 3=11+2B-12\Rightarrow B=-10$.
**Итог:** $\boxed{\tfrac{11}{x-2}-\tfrac{10}{x-1}+\tfrac{6}{(x-1)^2}}$.

**(г)** $\dfrac{x}{(x-1)(x-2)(x-3)}=\dfrac{A}{x-1}+\dfrac{B}{x-2}+\dfrac{C}{x-3}$.
Подстановка узлов:
$x=1\Rightarrow 1=A( -1)( -2) \Rightarrow A=\tfrac12$.
$x=2\Rightarrow 2=B(1)( -1) \Rightarrow B=-2$.
$x=3\Rightarrow 3=C(2)(1) \Rightarrow C=\tfrac32$.
**Итог:** $\boxed{\tfrac{1}{2(x-1)}-\tfrac{2}{x-2}+\tfrac{3}{2(x-3)}}$.

**(д)** $\dfrac{3x^2+1}{(x-1)^2(x-2)^2}=\dfrac{A}{x-1}+\dfrac{B}{(x-1)^2}+\dfrac{C}{x-2}+\dfrac{D}{(x-2)^2}$.
Используем узлы и сравнение коэф.:
$x=1\Rightarrow 4=B\Rightarrow B=4$.
$x=2\Rightarrow 13=D\Rightarrow D=13$.
Далее сравнение коэф. при $x^3,x^2,x$: получаем $A=14$, $C=-14$.
**Итог:** $\boxed{\tfrac{14}{x-1}+\tfrac{4}{(x-1)^2}-\tfrac{14}{x-2}+\tfrac{13}{(x-2)^2}}$.

---

# 116. Разложения в степенные ряды около $x=0$ — с выводом

**База:**

* Геометрический ряд: $\dfrac{1}{1-t}=\sum_{n\ge0}t^n$, $|t|<1$.
* Производные: $\dfrac{1}{(1-t)^2}=\sum_{n\ge0}(n+1)t^n$, $\dfrac{1}{(1-t)^3}=\sum_{n\ge0}\binom{n+2}{2}t^n$.

**(а)** $\displaystyle \frac1{x+4}=\frac14\cdot\frac1{1+x/4}=\sum_{n\ge0}\frac{(-1)^n}{4^{n+1}}x^n$.
Первые члены: $\boxed{\tfrac14-\tfrac1{16}x+\tfrac1{64}x^2-\tfrac1{256}x^3+\cdots}$.

**(б)** $\displaystyle \frac1{(x-2)^2}=\frac1{4}\cdot\frac1{(1-x/2)^2}=\frac14\sum_{n\ge0}(n+1)\big(\tfrac{x}{2}\big)^n=\sum_{n\ge0}\frac{n+1}{2^{n+2}}x^n$.
Первые члены: $\boxed{\tfrac14+\tfrac14x+\tfrac{3}{16}x^2+\tfrac18x^3+\cdots}$.

**(в)** $\displaystyle \frac1{(x-1)^3}=\frac{-1}{(1-x)^3}=-\sum_{n\ge0}\binom{n+2}{2}x^n$.
Первые члены: $\boxed{-1-3x-6x^2-10x^3-\cdots}$.

**(г)** $\displaystyle \frac{x}{(x-1)(x-2)}$.
Сначала простейшие: $\dfrac{x}{(x-1)(x-2)}=\dfrac{-1}{x-1}+\dfrac{2}{x-2}$.
Далее: $-\dfrac{1}{x-1}=\dfrac{1}{1-x}=\sum_{n\ge0}x^n$, а $\dfrac{2}{x-2}=-\sum_{n\ge0}\dfrac{x^n}{2^{n}}$.
Итого: $\sum_{n\ge0}\Big(1-\frac{1}{2^n}\Big)x^n=\sum_{n\ge1}\frac{2^n-1}{2^n}x^n$.
Первые члены: $\boxed{\tfrac12x+\tfrac34x^2+\tfrac78x^3+\cdots}$.

**(д)** $\displaystyle \frac{3x^2+1}{(x-1)^2(x-2)}$.
Простейшие: $\displaystyle -\frac{10}{x-1}-\frac{4}{(x-1)^2}+\frac{13}{x-2}$.
Ряды: $-\dfrac{10}{x-1}=10\sum_{n\ge0}x^n$, $-\dfrac{4}{(x-1)^2}=-4\sum_{n\ge0}(n+1)x^n$, $\dfrac{13}{x-2}=-\sum_{n\ge0}\dfrac{13}{2^{n+1}}x^n$.
Коэфф. при $x^n$: $10-4(n+1)-\dfrac{13}{2^{n+1}}$.
Первые члены: $\boxed{-\tfrac12-\tfrac54x-\tfrac{29}{8}x^2-\tfrac{73}{16}x^3-\cdots}$.

---

# 117. Производящие функции — как решать быстро (и готовые ответы)

**Шаблон:**

1. Умножить рекуррентность на $x^{n}$, просуммировать по $n\ge0$ (или с нужного старта).
2. Выразить $U(x)=\sum u_n x^n$; получить рациональную функцию.
3. Разложить на простейшие/выделить геом. ряды => извлечь замкнутую формулу.

Ниже — окончательные формулы (подробный вывод можно восстановить по шаблону):

* **(а)** $u_{n+1}=u_n+3$, $u_0=5$ $\Rightarrow$ $\boxed{u_n=3n+5}$.
* **(б)** $u_{n+2}=u_{n+1}+6u_n$, $u_0=1$, $u_1=4$ $\Rightarrow$ $\boxed{u_n=\tfrac15(6\cdot 3^n-(-2)^n)}$.
* **(в)** $u_{n+1}=3u_n+4^{n+1}$, $u_0=1$ $\Rightarrow$ $\boxed{u_n=4^{,n+1}-3^{,n+1}}$.
* **(г)** $u_{n+1}=2u_n+n+1$, $u_0=3$ $\Rightarrow$ $\boxed{u_n=-n-2+5\cdot 2^n}$.
* **(д)** $u_{n+1}=2u_n+3^{n+1}$, $u_0=1$ $\Rightarrow$ $\boxed{u_n=3^{,n+1}-2^{,n+1}}$.
* **(е)** $u_{n+1}=3u_n+n+1$, $u_0=2$ $\Rightarrow$ $\boxed{u_n=\tfrac{11}{4},3^n-\tfrac12,2^n-\tfrac34}$.
* **(ж)** $u_{n+2}=2u_{n+1}+3u_n$, $u_0=8$, $u_1=16$ $\Rightarrow$ $\boxed{u_n=6\cdot 3^n+2(-1)^n}$.
* **(з)** $u_{n+2}=4u_{n+1}-4u_n$, $u_0=1$, $u_1=0$ $\Rightarrow$ $\boxed{u_n=2^n-n,2^n}$.
* **(и)** $u_{n+1}=2u_n-3$, $u_0=4$ $\Rightarrow$ $\boxed{u_n=2^n+3}$.
* **(к)** $u_{n+1}=u_n+n+1$, $u_0=1$ $\Rightarrow$ $\boxed{u_n=\tfrac{n^2+n+2}{2}}$.
* **(л)** $u_{n+1}=3u_n+2^{,n+1}$, $u_0=2$ $\Rightarrow$ $\boxed{u_n=-2\cdot 2^n+4\cdot 3^n}$.
* **(м)** $u_{n+1}=2u_n+2^{,n+1}$, $u_0=1$ $\Rightarrow$ $\boxed{u_n=(n+3)2^n-n-2}$.
* **(н)** $u_{n+2}=6u_{n+1}-9u_n+2^{,n+2}$, $u_0=1$, $u_1=8$ $\Rightarrow$ $\boxed{u_n=(3^n-1)3^n+4\cdot 2^n}$.

---

### Комментарии

* В §116(б) обращай внимание на коэффициенты: $\dfrac1{(x-2)^2}=\sum\dfrac{n+1}{2^{n+2}}x^n$ (часто по невнимательности ставят $\tfrac12x$ вместо $\tfrac14x$).
* Если хочешь, добавлю ещё один раздел с «типовыми формами частных решений» (полином/экспонента/экспонента×полином/синус-коэффициенты) на 1 страницу-«шпаргалку».
