---
layout: post
title: Updated Fuchs Derivation
use_math: true
category: physics
---
The Fuchs function, while providing an incredibly useful basis with which a proton energy distribution resulting from TNSA can be estimated, does not account for the target deformation from the prepulse shot.  While the prepulse shot is several orders of magnitude lower than the main pulse shot in intensity, the temporal separation between the prepulse and main pulse shots allows for a significant change to the shape of the target.  Consider the following initial density distribution:  
(image of rectangular target of height $n_0$ and width d)  
Due to the conservation of mass, we can assume that there exists a conserved quantity, $N$, which is found by integrating the linear density with respect to position: 

\begin{equation}
N = \int_{-\infty}^\infty n(x) dx = n_0 d
\end{equation}

Trivially.  Now assume that a time $t$ has passed since the target was hit by a prepulse.  We would expect the target's density to be reduced over the rectangle of width $d$ from $n_0$ to some $n_{max}$ and gain an exponentially decaying tail on either end, as shown in the following figure:

(image of new distribution)

Thus, the density distribution function is as follows:
\begin{equation}
\displaystyle
  n(x) \equiv 
  \begin{cases}
  n_{max} &\mbox{ if }  0 \leq \lvert x \rvert < d/2 \\
  n_{max} e^{-(\frac{\lvert x \rvert -d/2}{c_st})} &\mbox{ if } d/2 \leq \lvert x \rvert < x_f \\
  0 &\mbox{ otherwise} 
  \end{cases}
\end{equation}

Where $c_s$ refers to the speed of sound in the medium.  Hence, to find the new density of the main target profile $n_{max}$, we can integrate the new density function over all space and set it equal to $N$, the total amount of material in the inital target.  That is:

\begin{equation}
\int_{-\infty}^\infty n(x) dx = 2 ( \int_0^{d/2} n_{max} dx + \int_{d/2}^{x_f} n_{max} e^{-\frac{x-d/2}{c_st}} dx ) = n_0 d
\end{equation}

Due to the symmetry of the density function.  Using the result of the Mora paper, we can estimate that $x_f = c_s t ( 2\ln{(\omega_{pi}t)} - \ln{2} + 3)$, where $\omega_{pi} t \approx 50$ for this experiment, giving $x_f \approx 5.517$.  Thus:

\begin{equation}
 2 n_{max} ( \frac{d}{2} + \int_{d/2}^{5.517c_st} n_{max} e^{-\frac{x-d/2}{c_st}} dx ) = n_0 d
\end{equation}

Using a u-subsitution of $u \equiv \frac{x-d/2}{c_st}, du = \frac{dx}{c_st}$, the integral becomes:

\begin{equation}
 I = \int_0^{5.517-\frac{d}{2c_st}} e^{-u} du \quad c_st
\end{equation}


\begin{equation}
 I = c_st \left[ -e^{-u}\right]_{u=0}^{5.517-\frac{d}{2c_st}}
\end{equation}

\begin{equation}
 I = c_st \left[ -e^{-5.517+\frac{d}{2c_st}} + e^0 \right]
\end{equation}

Here, we assume that $\frac{d}{2c_st}=0$-- that is, enough time has passed that the thickness of the original target is negligible compared to the long exponential tail.  We also note that $e^{-5.517} \approx 0.004$ and may also be safely ignored.  Therefore, evaluating the original equation with these results yields:

\begin{equation}
 2n_{max} (\frac{d}{2} + c_st) = n_0 d
\end{equation}

\begin{equation}
\therefore n_{max} = \dfrac{n_0d}{d + 2c_st}
\end{equation}

Giving us a formula for the effective density of the main target and how it decays as a function of time.
