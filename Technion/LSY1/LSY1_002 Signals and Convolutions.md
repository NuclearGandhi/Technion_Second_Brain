---
aliases:
  - unit impulse
  - delta function
  - time shift
  - convolution
  - signal norm
---


# Standard signals
The following definition introduces basic signals that play a prominent role in this course:
- **step**:
	$$\mathbb{1}(t)=\begin{cases}
1 & t\geq  0 \\
0 & t<0
\end{cases}$$
	![[LSY1_002/Screenshot_20240609_093549_Samsung Notes.jpg|book|200]]
- **ramp**:
	$$\text{ramp}(t)=t\mathbb{1}(t)=\begin{cases}
t & t\geq  0 \\
0 & t<0
\end{cases}$$
	![[LSY1_002/Screenshot_20240609_093653_Samsung Notes.jpg|book|200]]
- **rectangular pulse (of width $a$)**:
	$$\text{rect}_{a}(t)=\begin{cases}
1 & \left|t\right|<a/2 \\
0 & \left|t\right|>a/2
\end{cases}\qquad a>0$$
	![[LSY1_002/Screenshot_20240609_093920_Samsung Notes.jpg|book|200]]
- **triangular pulse (of width $a$)**:
	$$\text{tent}_{a}(t)=\begin{cases}
1-\dfrac{\left|t\right|}{a} & \lvert t \rvert\leq  a \\
0 & \left|t\right|>a
\end{cases}\qquad a>0$$
	![[LSY1_002/Screenshot_20240609_094121_Samsung Notes.jpg|book|200]]
- **sinusodial**:
	$$\sin(\omega t+\phi)$$
	![[LSY1_002/Screenshot_20240609_095700_Samsung Notes.jpg|book|200]]
	
- **sinc (sine cardinal)**:
	$$\mathrm{sinc} (t)=\dfrac{\sin t}{t}$$
	![[LSY1_002/Screenshot_20240609_095726_Samsung Notes.jpg|book|200]]
- **exponential**:
	$$\exp_{\lambda}(t)=\exp(\lambda t)=e^{\lambda t}$$
	![[LSY1_002/Screenshot_20240609_095848_Samsung Notes.jpg|book|200]]

>[!notes] Notes: 
 >Common abbreviations are:
 >$$\begin{gathered}
\text{rect}\equiv \text{rect}_{1} &  & \text{tent}\equiv \text{tent}_{1}
\end{gathered}$$


# Norms
We can define signal [[../NUM1/NUM1_003 נורמה#נורמה של וקטור|norms]] in a very similar way to vector norms:
>[!def] Definition:
> - ${L}_{1}$-norm:
> 	$$\left|\left|x\right|\right|_{1}=\int_{-\infty }^{\infty } \left|x(t)\right| \, \mathrm{d}t $$
> If $\left|\left|x\right|\right|_{1}<\infty$, then we say that $x \in L_{1}$ and call **absolutely integrable**.
> - ${L}_{2}$-norm:
> 	$$\left|\left|x\right|\right|_{2}=\left( \int_{-\infty }^{\infty } \left|x(t)\right|^{2} \, \mathrm{d}t  \right)^{1/2}$$
> 	If $\left|\left|x\right|\right|_{i}<\infty$, then we say that $x \in L_{i}$ and call **square integrable**.
> - ${L}_{\infty}$-norm:
> 	$$\left|\left|x\right|\right|_{\infty }=\underset{ t\in \mathbb{R} }{ \mathrm{sup} }\left|x(t)\right|$$
>If $\left|\left|x\right|\right|_{\infty}<\infty$, then we say that $x \in L_{\infty}$ and call it **bounded**

>[!example] Example: Standard signals' norms
>- if $x=\exp_{\lambda}$, then
>	$$x \notin {L}_{1},\, x \notin {L}_{2},\, x \notin L_{\infty }$$
>- if $x=\exp_{\lambda}\mathbb{1}$ with $\lambda<0$, then
>	$$x \notin {L}_{1},\qquad  x \in  {L}_{2}(\left|\left|x\right|\right|_{2}=\sqrt{ \pi }),\qquad  x \in L_{\infty }(\left|\left|x\right|\right|_{\infty }=1)$$
>- if $x=\mathbb{1}$ then
>	$$x \notin {L}_{1},\qquad x\notin {L}_{2},\qquad x \in L_{\infty }(\left|\left|x\right|\right|_{\infty }=1)$$



# Operations on Signals
## (Amplitude) Scaling
Given $x:\mathbb{R}\to \mathbb{F}$ and $a\in \mathbb{F}$, the signal $ax:\mathbb{R}\to \mathbb{F}$ (or $a\cdot x$) is defined as
$$(ax)(t)=ax(t),\qquad  \forall t\in \mathbb{R}$$
with $-x\equiv(-1\cdot x)$.

>[!example] Example: 
 >$$\begin{aligned}
 & 2\mathbb{1}=\begin{cases}
2 & t\geq  0 \\
0 & t<0
\end{cases} \\[1ex]
 & \dfrac{1}{2}\mathrm{ramp}=\begin{cases}
t/2 &  & t\geq  0  \\
0 &  & t<0
\end{cases}
\end{aligned}$$

## Addition
Given $x:\mathbb{R}\to \mathbb{F}$ and $y:\mathbb{R}\to \mathbb{F}$, the signal $x+y:\mathbb{R}\to \mathbb{F}$ is defined as
$$(x+y)(t)\equiv x(t)+y(t),\qquad  \forall t\in \mathbb{R}$$


## Multiplication
Given $x:\mathbb{R}\to \mathbb{F}$ and $y:\mathbb{R}\to \mathbb{F}$, the signal $xy:\mathbb{R}\to \mathbb{F}$ (or $x\cdot y$ ) is defined as
$$(xy)(t)\equiv x(t)y(t)\qquad t\in \mathbb{R}$$
## Time Scale (pace change)
Given $x:\mathbb{R}\to \mathbb{F}$ and $\zeta \in \mathbb{R} \setminus \{ 0 \}$, the signal $\mathbb{P}_{\zeta}x:\mathbb{R}\to \mathbb{F}$ is defined as
$$(\mathbb{P}_{\zeta}x)(t)\equiv x(\zeta t),\, \qquad  \forall t\in \mathbb{R}$$
**Commutativity property**:
$$\mathbb{P}_{{\zeta}_{1}}(\mathbb{P}_{{\zeta}_{2}}x)=\mathbb{P}_{{\zeta}_{1}{\zeta}_{2}}x=\mathbb{P}_{{\zeta}_{2}}(\mathbb{P}_{{\zeta}_{1}}x)$$

## Time Shift
Given $x:\mathbb{R}\to \mathbb{F}$ and $\tau \in \mathbb{R}$, the signal $\mathbb{S}_{\tau}x: \mathbb{R}\to \mathbb{F}$ is defined as
$$(\mathbb{S}_{\tau}x)(t)\equiv x(t+\tau)\qquad t\in \mathbb{R}$$
**Commutativity property**:
$$\mathbb{S}_{{\tau}_{1}}(\mathbb{S}_{{\tau}_{2}}x)=\mathbb{S}_{{\tau}_{1}+{\tau}_{2}}x=\mathbb{S}_{{\tau}_{2}}(\mathbb{S}_{{\tau}_{1}}x)$$

# Periodic Signals
A signal $f(t)$ is periodic if a $T>0$ exists such that $f(t+T)=f(t)$ for all $t\in \mathbb{R}$. A signal will be referred to as $T$-periodic if it is periodic with period $T$.

>[!def] Defintion: 
 >A real-valued signal $f(t)$ that can be written as
 >$$f(t)=A\cos(\omega t+\phi)\qquad A>0,\, \phi \in \mathbb{R},\, t\in \mathbb{R}$$
 >is called a **sinusoid** or real [[../PHY1/PHY1_004 תנועה הרמונית ומערכות ייחוס#תנועה הרמונית|harmonic signal]]. Then $A$ is the **amplitude**, $\omega$ the **angular frequency**, and $\phi$ the **initial phase** of the signal $f(t)$.
 
 Such sinusoids have a period of $T=2\pi /\omega$.

>[!theorem] Lemma: 
 >Suppose that $f(t)$ is integrable on $[0,T]$ and that $f(t)$ is periodic with period $T>0$. Then for every $a\in \mathbb{R}$, there holds:
 >$$\int_{a}^{a+T} f(t) \, \mathrm{d}t=\int_{0}^{T} f(t) \, \mathrm{d}t  $$
 

# Energy and Power
It is customary in signal analysis to use "energy" instead of norm:
>[!def] Definition:
>The **energy** $E_{f}$ of a signal $f(t)$ is defined as
>$$E_{f}=\int_{-\infty }^{\infty} \left|f(t)\right|^{2} \, \mathrm{d}t $$
>If $E_{f}<\infty$ (finite energy content), then the signal is said to be an **energy signal**.

The rectangular and traingular pulses are examples of energy signals. For a signal $f(t)$ to have a finitie energy content it is necessary that $\lim_{ t \to \infty}\int_{a}^{t} \left|f(\tau)\right|^{2} \, \mathrm{d}\tau$ converges. Consequently, signals like sinusoids, periodic signals and the unit step and many others, are not energy signals. In such cases it is customary to consider instead its averages energy *per unit time*, i.e., to look at its (averaged) power.

>[!def] Definition:
>The **power** $P_{f}$ of a signal $f(t)$ is defined as
>$$P_{f}=\lim_{ M \to \infty} \dfrac{1}{M}\int_{-M/2}^{M/2} \left|f(t)\right|^{2} \, \mathrm{d}t $$
>Signals that have finite power are called **power signals**.

>[!example] Example: 
> In the case of a $T$-periodic signal, the power signal $f(t)$ is finite, and it equals the average energy over one period:
> $$\begin{aligned}
> P_{f} & =\lim_{ M \to \infty} \dfrac{1}{M}\int_{-M/2}^{M/2} \left|f(t)\right|^{2} \, \mathrm{d}t \\[1ex]
> \end{aligned}$$
> Let there be $k$ such that $M=kT$:
> $$\begin{aligned}
> P_{f} & =\lim_{ k \to \infty} \dfrac{1}{kT}\int_{-kT/2}^{kT/2}\left|f(t)\right|^{2} \, \mathrm{d}t  \\[1ex]
>  & =\lim_{ k \to \infty} \sum_{i=0}^{k-1} \int_{iT-kT/2}^{iT-(kT/2)+T} \left|f(t)\right|^{2} \, \mathrm{d}t \\[1ex]
>   & =\lim_{ k \to \infty} \dfrac{1}{kT}\sum_{i=0}^{k-1}\int_{0}^{T} \left|f(t)\right|^{2} \, \mathrm{d}t \\
>   & =\lim_{ k \to \infty} \dfrac{1}{kT}k\int_{0}^{T} \left|f(t)\right|^{2} \, \mathrm{d}t \\[1ex]
>  & =\boxed{\dfrac{1}{T}\int_{0}^{T} \left|f(t)\right|^{2} \, \mathrm{d}x  }  
> \end{aligned}$$


>[!example] Example: 
>The power of the sinusoid $f(t)=A\cos({\omega}_{0}t+\phi)$ with period $T=2\pi /{\omega}_{0}$, is:
>$$\begin{aligned}
P_{f} & =\dfrac{{\omega}_{0}}{2\pi}\int_{-\pi /{\omega}_{0}}^{{\pi /\omega}_{0}} A^{2}\cos ^{2}({\omega}_{0}t+\phi) \, \mathrm{d}t\underset{ x={\omega}_{0}t }{ = }\dfrac{A^{2}}{2\pi}\int_{-\pi}^{\pi} \cos ^{2}(x+\phi) \, \mathrm{d}x  \\[1ex]
 & =\boxed {
\dfrac{A^{2}}{2} 
 }
\end{aligned}$$


# Convolution

![](https://youtu.be/KuXjwB4LzSA?si=cmk717AthemfPfWl)

Loosely speaking a **convolution** is a linear combination of shifted copies  of signal. For instance:
$$3g(t)-41g(t-1)+501g(t+100)$$
Is an example of convolution of signal $g(t)$. Note that the convolution is itself a signal. More generally expression like:
$$\sum _{\tau}f_{\tau}g(t-\tau),\qquad f_{\tau}\in \mathbb{R}$$
are known as convolutions, and so is its integral version which we take to be its definition.

>[!def] Definition: 
 >The **convolution** or **convolution product** of two signals $f(t)$ and $g(t)$ is denoted as $(f*g)(t)$ and is defined as:
 >$$(f*g)(t)=\int_{-\infty }^{\infty} f(\tau)g(t-\tau) \, \mathrm{d}\tau $$

It is an interesting fact that convolution products commute:
$$(f*g)(t)=\int_{-\infty }^{\infty } f(\tau)g(t-\tau) \, \mathrm{d}\tau \underset{ v=t-\tau }{ = }\int_{-\infty }^{\infty}g(v)f(t-v)  \, \mathrm{d}v=(g*f)(t) $$

Convolutions are very common in applications, and are, for instance, useful if we want to remove noise from signals, detect edges in pictures, soften pictures, etc.

>[!example] Example: Sliding window averaging and noise reduction
>For a given signal $f(t)$ we construct the signal $f_{\text{swa}}$ by averaging $f(t)$ around $t$ over an interval of a fixed length $P$, i.e., we consider
>$$f_{\text{swa}}(t)=\dfrac{1}{P}\int_{t-P/2}^{t+P/2}f(\tau)  \, \mathrm{d}\tau $$
Averaging $f(t)$ this way filters out highly fluctuating noise. It is to be expected then, that $f_{\text{swa}}(t)$ is somewhat smoother that $f(t)$, but as long as $P$ is not too large the graph of the averagd $f_{\text{swa}}(t)$ should retain roughly the same shape as the graph of $f(t)$.
 >![[Screenshot_20240609_111610_Samsung Notes.jpg|book]]
>[](LSY1_002/Screenshot_20240609_111610_Samsung%20Notes.jpg)veraged with $P=0.1$
>
> The signal $f_{\text{swa}}$ can be written as the convolution of $f$ with a suitable function $g$:
> $$f_{\text{swa}}(t)=\dfrac{1}{P}\int_{t-P/2}^{t+P/2} f(\tau)  \, \mathrm{d}\tau\underset{ v=t-\tau }{ = } \dfrac{1}{P}\int_{-P/2}^{P/2}f(t-v)  \, \mathrm{d}v=(f*g)(t)  $$
> for
> $$g(t)=\dfrac{1}{P}\mathrm{rect}_{P}(t)$$
> ![[Screenshot_20240609_112515_Samsung Notes 1.jpg|book|200]]
[](LSY1_002/Screenshot_20240609_112515_Samsung%20Notes%201.jpg)

>[!example] Example: Convolution with step:
>Convolution with the unit step amount to integration:
$$(\mathbb{1}*x)(t)=\int_{-\infty }^{\infty} \mathbb{1}(t-s)x(s) \, \mathrm{d}s = \int_{-\infty }^{t} \mathbb{1}(t-s) \, \mathrm{d}s+\int_{t}^{\infty} \mathbb{1}(t-s) \, \mathrm{d}s  $$
 >For the step signal, we get zero for every $t-s<0$, therefore the second integral evaluates to $0$:
 >$$\boxed {
(\mathbb{1}\cdot x)(t)=\int_{-\infty }^{t} x(s) \, \mathrm{d}s 
 }$$
 
# The Delta Function
In applications we often encounter signals that a very short duration but nevertheless have a definite impact. Such signals are called impulses. The standard are called impulses. The standard impulse is the so-called Dirac **delta function** also known as the **unit impulse**. The delta function $\delta(t)$ is introduced as the limit as $n\to \infty$ of
$$r_{n}(t)\equiv \begin{cases}
n & \left|t\right|<\dfrac{1}{2n} \\[1ex]
0 & \left|t\right|>\dfrac{1}{2n}
\end{cases}$$
![[LSY1_002/Screenshot_20240609_114536_Samsung Notes.jpg|book|200]]

As $n$ goes to infinity, the rectangular pulses $r_{n}(t)$ become spikier and spikier, with spike around $t=0$.

![[LSY1_002/Screenshot_20240609_114950_Samsung Notes.jpg|book|450]]
>A series of $r_{n}(t)$ for $n=1,\,n=2,\,n=3$ and $n=4$

However, the area enclosed by the spike and the $x$-axis, $\int_{-\infty}^{\infty} r_{n}(t) \, \mathrm{d}t$, equals $1$ independent of $n$. We now naively define **delta function** $\delta(t)$ as the limit
$$\delta(t)=\lim_{ n \to \infty}r_{n}(t)$$
and we think of the delta function as a "function" that is zero everywhere except at $t=0$ where it has a spike so large that
$$\int_{0-}^{0+} \delta(t) \, \mathrm{d}t=1 $$
The delta function is usually depicted as
![[LSY1_002/Screenshot_20240609_123456_Samsung Notes.jpg|book|200]]
>The delta function $\delta(t)$

The idea to see the function as a pike in this sense is helpful, but mathematically it is far from sound. After all,
$$\lim_{ n \to \infty}r_{n}(t)=\begin{cases}
0 & t\neq 0 \\
\infty  & t=0
\end{cases}$$
and the integral of a function that is zero everywhere except for one point, is zero.

>[!theorem] Lemma: 
 >If $f(t)$ is continuous at $t=0$, then
 >$$\int_{-\infty }^{\infty} \delta(t)f(t) \, \mathrm{d}t=f(0) $$
 
## Properties of the delta function
 Delta functions can be added, they can be multiplied with regular functions, they can be integrated etc.

### The Sifting Property
The scaled and shifted delta function $\delta(at-b)$ we take to be defined as:
$$\delta(at-b)=\lim_{ n \to \infty}r_{n}(at-b)$$

For $t=b/a$ the argument $at-b$ is zero, so $r_{n}(at-b)$ as a function of $t$ is centered around $t=b/a$.

![[LSY1_002/Screenshot_20240609_125324_Obsidian.jpg|book|400]]
>Shifted and scaled $r_{n}(t)$

This is very much like a shifted copy of $r_{n}(t)$ with the difference that the spike does not have a unit area:
![[LSY1_002/Screenshot_20240609_125453_Obsidian 1.jpg|book|200]]
>Shifted delta function $\delta(t-b)$

We can now generalize the previous Lemma:
>[!theorem] Lemma: 
 >If $f(t)$ is continuous, then:
 >$$\int_{-\infty }^{\infty} \delta(at-b)f(t) \, \mathrm{d}t=\dfrac{1}{\left|a\right|}f\left( b/a \right) $$

An immediate special case is that
$$\int_{-\infty }^{\infty} \delta(t-b)f(t) \, \mathrm{d}t=f(b),\, \qquad  (\text{if } f(t) \text{ is continuous at } t=b) $$
 This property is known as the **sifting property** of the delta function. It is the property that out of all values $\{ f(t)\mid t\in \mathbb{R} \}$ that $f(t)$ can take, the value at $t=b$ is sifted out. It is also possible to determine the convolution product $(f*\delta)(t)$ of a signal $f(t)$ and the delta function $\delta(t)$.
 $$\boxed {
(f*\delta)(t)=\int_{-\infty }^{\infty} \delta(t-\tau)f(\tau) \, \mathrm{d}\tau=f(t) 
 }$$
 
### Products with delta functions
>[!theorem] Lemma: 
 >If $f(t)$ is continuous at $t=b$, then
 >$$f(t)\delta(t-b)=f(b)\delta(t-b)$$


| Property    | Condition                                                             | Notes                      |
| ----------- | --------------------------------------------------------------------- | -------------------------- |
| Sifting     | $\int_{-\infty}^{\infty} \delta(t-b)f(t) \, \mathrm{d}t=f(b)$         | $f(t)$ continuous at $t=b$ |
|             | $f(t)\delta(t-b)=f(b)\delta(t-b)$                                     | $f(t)$ continuous $t=b$    |
| Convolution | $(f*\delta)(t)=f(t)$                                                  |                            |
| Scaling     | $\delta(at-b)=\left( \dfrac{1}{\lvert a \rvert} \right)\delta(t-b/a)$ |                            |
|             | $\int_{-\infty}^{t} \delta(\tau) \, \mathrm{d}\tau=\mathbb{1}(t)$     | $t\neq 0$                  |
>Properties and rules of calculus for the delta function

# Exercises
## Question 1
Consider the continuous time signal
$$y(t)=\begin{cases}
t & 0\leq  t<10 \\
60-5t & 10\leq  t\leq  12 \\
0 & \text{otherwise}
\end{cases}$$
![[LSY1_004/Pasted image 20240617175116.png|book|400]]
>Triangle signal

Construct $y$ using the step function $\mathbb{1}$, and the $\mathrm{ramp}$ signal. Compute the $L_{\infty}$ and ${L}_{2}$ norms of $y$.

**Solution**:
$$\boxed {
y(t)=\mathrm{ramp}(t)-6\mathrm{ramp}(t-10)+\mathrm{ramp}(t-12)
 }$$
![[LSY1_002/Pasted image 20240617192429.png|book|400]]
>The above mentioned signal, broken down to three $\mathrm{ramp}$ signals. Try to match the $\mathrm{ramp}$ signals to their corresponding graph representation.

According to [[LSY1_002 Signals and Convolutions#Norms|signal norm]]:
$$\begin{aligned}
 & \lVert y \rVert _{\infty }=\sup_{t\in \mathbb{R}}(y)=10 \\[1ex]
 & \lVert y \rVert _{2}=\left( \int_{-\infty }^{\infty}\lvert y(t) \rvert^{2}  \, \mathrm{d}t \right)^{1/2}=\left( \int_{0}^{10} t^{2} \, \mathrm{d}t +\int_{10}^{12} (60-5t)^{2} \, \mathrm{d}t \right)^{1/2} \\[1ex]
 & \phantom{\lVert y \rVert _{2}} = \left( \left[ \dfrac{1}{3}t^{3} \right]_{0}^{10}+\left[ 3600t-300t^{2}+\dfrac{25}{3}t^{3} \right]_{10}^{12} \right)^{1/2} \\[1ex]
 & \phantom{\lVert y \rVert _{2}}=\left( 333 \dfrac{1}{3}+  66 \dfrac{2}{3}\right)^{1/2}=20
\end{aligned}$$
We have:
$$\boxed {
\begin{aligned}
\lVert y \rVert _{\infty }=10 &  & \lVert y \rVert _{2}=20
\end{aligned}
 }$$
## Question 2
Let $y$ be the signal from [[#Question 1]]. Let $f={f}_{1}+{f}_{2}+{f}_{3}$, where:
$$\begin{aligned}
{f}_{1}=\delta &  & {f}_{2}=3\mathbb{S}_{-2}\delta &  & {f}_{3}=0.5\mathbb{S}_{-3}\delta
\end{aligned}$$
i.e.
$$f(t)=\delta(t)+3\delta(t-2)+\dfrac{1}{2}\delta(t-3)$$
find the convolution $y*f$.

**Solution**:
One of the properties of [[#Convolution]] is:
$$\begin{aligned}
y*f=y*({f}_{1}+{f}_{2}+{f}_{3})=y*{f}_{1}+y*{f}_{2}+y*{f}_{3}
\end{aligned}$$
We'll calculate each one individually, using the [[#The Sifting Property]]:
$$\begin{aligned}
 & y*{f}_{1}=\int_{-\infty }^{\infty} y(\tau){f}_{1}(t-\tau) \, \mathrm{d}\tau = \int_{-\infty }^{\infty} y(\tau)\delta(t-\tau) \, \mathrm{d}\tau=y(t)  \\[2ex]
 & {y}*{f}_{2}=\int_{-\infty }^{\infty} y(\tau){f}_{2}(t-\tau)  \, \mathrm{d}\tau=\int_{-\infty }^{\infty} 3y(\tau)\delta(t-\tau-2) \, \mathrm{d}\tau=3y(t-2) \\[2ex]
 & y*{f}_{3}=\int_{-\infty}^{\infty} y(\tau){f}_{3}(t-\tau)  \, \mathrm{d}\tau=\int_{-\infty }^{\infty} \dfrac{1}{2} y(\tau)\delta(t-\tau-3) \, \mathrm{d}\tau= \dfrac{1}{2}y(t-3)
\end{aligned}$$
and we end up with
$$\boxed {
(y*f)(t)=y(t)+3y(t-2)+\dfrac{1}{2}y(t-3)
 }$$