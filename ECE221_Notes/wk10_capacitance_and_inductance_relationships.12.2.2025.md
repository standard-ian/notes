## Class 17
#### #1
###### Questions:
1. How does the capacitor charge in relation to the 1A current?
2. Current is measure of coulombs per second.
3. Capacitance is what, in terms of units?
4. Once the switch is closed, there will be a 1 coulomb per second flow of charges.
5. What is the relationship between C, i(t) and v(t)?

When the switch is closed, the charges begin to flow at 1A. These build up at the capacitor, increasing its potential (voltage).



$$i(t) = C\times \frac{dV}{dt}$$
```tikz
\usepackage{circuitikz}

\begin{document}
\begin{circuitikz}[american, scale=2,font=\Large]
	\draw(0,0)
	to[capacitor,l=v(t),a=$C{=}1\mu F(10^{-6}F)$]++(0,2)
	to[isource,invert,l=$i(t){=}1A$]++(4,0)
	to[switch]++(1,0)--++(0,-2)--(0,0);
	
\end{circuitikz}
\end{document}
```
$$\frac{1}{C}\times i(t) = \frac{dV}{dt}$$Now, we can integrate both sides with respect to $t$. $\frac{1}{C}$ is a constant in this situation.
$$\frac{1}{C}\int_{T_0}^{T}i(t)\ dt= \int_{T_0}^{T}\frac{dV}{dt}\ dt$$
$i$ can also be taken out as a constant, since we are not integrating with respect to $i$. $T_{0}=0$ when the switch is closed.
$$v(t) =\frac{i}{C}\int_{0}^{T}1\ dt$$

$$v(t) = \frac{i}{C}\int_{0}^{T} 1\ dt$$
$$v(T) = \frac{i}{C}\ [t]_{0}^{T} = \frac{i}{C}T$$
#### #2
###### Questions:
1. How does the voltage drop over the resistor change as the capacitor charges?
2. The initial current is $\frac{10V}{1k\ohm} = 10mA$
3. How does the current change as the cap charges?
4. At what point is the current 0 (when is the capacitor charged to 10V)
5. The time constant $\tau$ is needed.

At $t=0$ switch is closed.
$V_R=10V, t = 10mA$

```tikz
\usepackage{circuitikz}

\begin{document}
\begin{circuitikz}[american, scale=2,font=\Large]
	\draw(0,0)
	to[capacitor,l=v(t),a=$C{=}1\mu F(10^{-6}F)$]++(0,2)
	to[R=$1k\Omega$]++(1,0)
	to[vsource,V=$10V$]++(3,0)
	to[switch]++(1,0)--++(0,-2)--(0,0);
	
\end{circuitikz}
\end{document}
```
At $V_{cap}=10V$, the capacitor will be fully charged, and the current flow will cease.

$$V_{cap}(t) = V_{final} + (V_0 - V_{final})e^{-t/\tau}$$
$$\tau = RC = 1000(0.000001) = 0.001s$$
$$10V = 10 - 10e^{-t/0.001}$$
$$i(t) = 10e^{-t/0.001}mA$$
At $\frac{t}{\tau} \approx -5$  the following will be true, because as the exponent of $e$ becomes increasingly negative, it approaches 0: $e^{\frac{t}{\tau}} \approx 0$
$$i(t) \approx 0 = 10e^{-0.005/0.001}$$
At this point, the current has stopped. This only happens when the potential at the capacitor is equal to the potential at the source $10V=10V$
## Class 18
