---
layout: post
title: Deriving Effective Thickness from Prepulse Effects
use_math: true
category: physics
---

The paper I found postulates that the rarefaction wave will travel to the left with a velocity of $C_h$ and be replaced by an exponential decay function of $e^{-\frac{x}{C_ht}}$.  Obviously, this is only valid up until $d/2 = C_ht$, at which point the wave will have converted the entire initial distribution into an exponential decay function; let us call the value for time that makes this equation true $\tau$.  If we assume that the wave travels up to $x_f = 5.517C_h\tau$ (as shown in prior derivations), we can find the amount of mass that can be accounted for within the distribution:

\begin{equation}
M_{tot} = n_0 d = \int_{-x_f}^{x_f} n(x) dx
\end{equation}

\begin{equation}
\int_{-x_f}^{x_f} n(x) dx = 2 \int_0^{5.517C_h\tau} n_0 e^{-\frac{x}{C_h\tau}} dx
\end{equation}

\begin{equation}
M_{tot} = 2 \left[ -C_h \tau n_0 e^{-\frac{x}{C_h\tau}} \right]_{x=0}^{5.517C_h\tau}
\end{equation}

Here, we note that $C_h \tau = \frac{d}{2}$ at this point in time, as it is defined as the time at which the rarefaction wave has consumed the original distribution.  So:

\begin{equation}
M_{tot} = 2 \frac{d}{2} n_0 \left(1 -  e^{-5.517} \right)
\end{equation}

\begin{equation}
M_{tot} = n_0 d (1 - 0.00402)
\end{equation}

\begin{equation}
M_{tot} = n_0 d (0.9960)
\end{equation}

Meaning that 99.6\% of the original plasma mass can be accounted for.  As such, we can safely proceed with our next assumptions.

Now, let us assume that a time $t$ has passed since the plasma was originally allowed to evolve.  How would the density and, therefore, the effective thickness continue to evolve?  I assert that the plasma's shape will stay the same; it will continue to exponentially decay according to $e^{-\frac{x}{C_h(t)}}$.  However, there is no more plasma inside of the original distribution from which the exponential tail can grow; as such, the maximum density must decrease to a new density $n_{max}$ over time to conserve total mass.  We assert that mass is conserved:

\begin{equation}
\int_{-x_f(\tau)}^{x_f(\tau)} n(x) dx = \int_{-x_f(t)}^{x_f(t)} n(x) dx
\end{equation}

\begin{equation}
2 \int_{0}^{5.517C_h t} n_{max}e^{-\frac{x}{C_ht}} dx = n_0 d (0.9960)
\end{equation}

\begin{equation}
\left[ n_{max} C_h t e^{-\frac{x}{C_ht}} \right]_{x=0}^{5.517C_ht} = \frac{n_0 d}{2} (0.9960)
\end{equation}

\begin{equation}
n_{max}C_ht \left(1 - e^{-5.517} \right)= \frac{n_0 d}{2} (0.9960)
\end{equation}

\begin{equation}
n_{max} = \frac{n_0 d}{2 C_h t}
\end{equation}

Verifying our edge case, when $t = \tau$, $C_h t = \frac{d}{2}$, so $n_{max} = n_0$.  Now, we can solve for $x_0$, the point at which density decays to critical, assuming $n_{max} > n_{crit}$ to begin with:

\begin{equation}
n_{max} e^{-\frac{x_0}{C_ht}} = n_{crit} 
\end{equation}

\begin{equation}
e^{-\frac{x_0}{C_ht}} = \frac{n_{crit}}{n_{max}} 
\end{equation}

\begin{equation}
\frac{x_0}{C_ht} = \ln{n_{max}} - \ln{n_{crit}}
\end{equation}

\begin{equation}
x_0 = C_h t \left( \ln{n_{max}} - \ln{n_{crit}} \right)
\end{equation}

Using our previous equation for $n_{max}$:

\begin{equation}
x_0 = C_h t \left( \ln{n_0 d} -  \ln{2C_ht} - \ln{n_{crit}} \right)
\end{equation}

Finally, using $d_{eff} = 2x_0$:

\begin{equation}
d_{eff} = 2 C_h t \left( \ln{n_0 d} -  \ln{2C_ht} - \ln{n_{crit}} \right)
\end{equation}

\end{document}
