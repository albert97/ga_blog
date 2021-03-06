---
layout:     post
title:      "Stochastic Calculus -- Ito Integral"
subtitle:   "Ito integral is the stochastic calculus version of integration of ordinary calculus"
date:       2021-01-12 12:00
author:     "Albert"
category:   techblog
tags:       [math]
---

<html>
<head>
  <!-- Global site tag (gtag.js) - Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-QY6RDJK8PM"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'G-QY6RDJK8PM');
</script>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width">
  <title>MathJax example</title>
  <script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
  <script id="MathJax-script" async
          src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js">
  </script>
</head>
<body>
  
</body>
</html>

<h2 class="section-heading">Disclaimer </h2>

The following content was extracted from Stochastic Calclus lecture note by Jonathan Goodman at Courant Insititute 

<h2 class="section-heading">Introduction</h2>

The integral is the sum of infinitely many infinitely small contributions.
The expression:

$$
\int_{0}^{T}  F_{t} dt
$$

<html>
  <body>
means that you divide the interval [0,T] into infinitely many tiny and non- overlapping pieces of length dt and add \( F_{t}dt\) . The integral sign is a distorted S, for “sum”. It is possible to give a less vague definition by defining approximate integrals of the form:
  </body>
</html>

$$
Y_T^{(h)} = \sum_{0 \le t_{k} < T} F_{t_{k}} h = \sum_{0 \le{ t_{k}} \lt{T}} F_{t_{k}}(t_{k+1) - t_{k}} 
$$

<html>
<body>
Here, h > 0 is a time step and tk = kh is the start of a time interval [tk,tk+1]of lengthh. It is possible to prove that the following limit exists
</body>
</html>

$$
Y_{T}= \lim_{h->0}Y_T^{(h)}  
$$

<html>
<body>
This proof depends on the function Ft – is it continuous.
You can integrate (add up) contributions of the form FtdX, which gives an integral of the form:
</body>
</html>  

  
$$
  Y_{T}= \int_{0}^{T}  F_{t} dX_{t}            (1)
$$


<html>
<body>
If Xt is a random process, then the “decision” Ft must be made on the basis of information available at time t. This information does not include future values Xs, for \(s > t\), but it might involve predictions of future values from present information. A trading strategy Ft is adapted, or non-anticipating, or progressively measurable1 if Ft is a function of X[0,t].
 </body>
</html>  

<html>
<body>
If Xt is a diffusion process and Ft is adapted, then the integral (1) is the Ito integral. The random processes Xt and Ft define a new random process YT . This Lesson explains (not in complete mathematical rigor) the proof that the following limit exits
  </body>
</html>  
  

$$
Y_{T}= \lim_{h->0}Y_T^{(h)}  = \lim_{h->0} \sum_{0 <= t_{k} \lt T} F_{t_{k}}(t_{k+1) - t_{k}}
$$

<html>
<body>
Starting here, the concept of a martingale will be used constantly. A stochas- tic process is a martingale if its increments have expected value zero at the start of each increment interval. That is, if \(s > 0\), then
</body>
</html>  
  
$$
  E[X_{t+3} - X_{t} | F_{t}] = 0
$$

<html>
<body>
(The full technical definition of martingale requires more technical hypotheses on Xt and a full technical definition of Ft.) Some important facts about mar- tingales: (1) Brownian motion is a martingale. (2) If Xt is a martingale then YT , defined by the Ito integral (1), is a martingale. This is sometimes called Doob’s martingale theorem. The financial interpretation is that a trading strat- egy from a martingale produces a martingale – you cannot make an expected profit from a non-anticipating trading strategy. (3) A diffusion is a martingale if the infinitesimal drift is zero.
</body>
</html>  


<html>
<body>
The Ito isometry formula, for a martingale diffusion, is
</body>
</html>  

$$
   E[Y_{T}^2] = \int_{0}^{T} E{F_{t}^{2}} E[v(X_{t})^{2}]dt
$$

<html>
<body>
This is an intergal version of a simple face about random sums. First, suppose that Uk are random vairbale with E[Uk] = 0, and 
</body>
</html>  

$$
  S_{n} = \sum_{1}^{n} U_{k}
$$

<html>
<body>
Then  
</body>
</html>  

$$
  E[S_{n}^2] = \sum_{1}^{n} E[U_{k}^{2}]
$$


<html>
<body>
Now suppose that Fn is “all the information” in the random numbers F1, . . . , Fn and U1,...,Un−1, and suppose that the Un are martingale differences in the sense that
</body>
</html>  


$$
  E[U_{n}|F_{n}]=0.
$$

<html>
<body>
Define a sum that looks more like (1)
</body>
</html>  


$$
  S_{n} = \sum_{1}^{n} F_{k}U_{k}
$$

<html>
<body>
This has 
</body>
</html>  


$$
  E[S_{n}^{2}] = \sum_{1}^{n} E[F_{k}^{2}] E[U_{k}^{2} | F_{k}]
$$


<html>
<body>
This is like the Ito isometry formula, if E[Ft2] is replaced with E[Fn2] and E[dX2 | Ft] = v(Xt)dt is replaced with E[ Uk2 | Fk]. This lesson explains calculations like this.
</body>
</html>  


<h2 class="section-heading">Application to SDE</h2>

<html>
<body>
A stochastic differential equation (or SDE) is an expression of the form 
</body>
</html>

$$
    dX_{t} = a(X_{t}, t)dt + b(X_{t}, t)dW_{t}
$$

<html>
<body>
we will instead interpret the SDE in the more literal strong form. In the strong interpretation, Wt is the Brownian motion that “drives” Xt. The position at time t, which is Xt, depends on the Brownian driver (or forcing) up until that time. That is Xt is a function of W[0,t]. The SDE is to be interpreted in the integral sense
</body>
</html>

$$
    X_{T} - X_{0} = \int_{0}^{T} a(X_{t},t)dt + \int_{0}^{T} b(X_{t},t)dW_{t} (7)
$$

<html>
<body>
The first integral on the right is an ordinary Riemann integral defined as in ordinary calculus. This makes sense because a(Xt,t) is a continuous function of t (assuming a(x, t) is a continuous function of x and t) and dt integrals are defined for continuous integrands. Keep in mind that Xt is random, so the value of the integral is also random.
</body>
</html>  

<html>
<body>
The second integral is an Ito integral with respect to Brownian motion. The theory of Ito integration has to cover this important case – the integrand Ft = b(Xt,t) is a continuous but not differentiable function of t. The mathematical term regularity refers to the degree of smoothness (number of derivatives) or the amount by which Ft can change in a small interval of time. Regularity is qualitative, which means that it does not matter what the constant in the inequality is, only that there is a constant. Whatever is supposed to converge should converge no matter what (finite) value the constant has.  
</body>
</html>    

<html>
<body>
  A continuous function b(x) is Lipschitz continuous if there is a C so that :
</body>
</html> 

$$
    |b(y)−b(x)| \le{ C|y−x|} 
$$

<html>
<body>
A common theory of SDE like (6) applies under the hypothesis that the coefficients a(x, t) and b(x, t) are Lipschitz continuous functions of x. We we assume b is Lipschitz and we ignore the less important dependence of b on t (assume, for example, that b depends on x but not t). In this case, some regularity of Ft = b(Xt) comes from the regularity of Xt. For a diffusion, 
</body>
</html>

$$
   E[(\Delta X)^2 |F_{t}] = O(\Delta t)
$$

<html>
<body>
  When b is Lipschitz continuous, and from the properties of big Oh, it follows that
</body>
</html>
 
$$
   E[(\Delta F)^2 |F_{t}] = O(\Delta t)         (8)
$$

<html>
<body>
where \(F_{t} = b(X_{t})\). We will make a definition of the Ito integral (1) under the hypotheses that \(X_{t}\) is a diffusion and a martingale and that \(F_{t}\) has the regularity property (8).
</body>
</html>

<h2 class="section-heading">Borel Cantelli lemma </h2>

<html>
<body>
To prove the sequence \( Y_{T}^{(h_{n})} \) converges as \( n -> \infty \) and \( h_{n} = 2^{−n} \). We T need a way to show that limits exist without calculating the limit explicitly. We need a way that applies to random sequences.
</body>
</html>
  
<html>
<body>
  Suppose \( y_{n} \) is a sequence of numbers and we want to show the limit exists: 
</body>
</html>

$$
 y = \lim_{n-> \infty} y_{n}
$$

<html>
<body>
 One way is to study the differences \( z_{n} = y_{n+1} − y_{n} \) and show that the
  inite
sum converges
</body>
</html>
$$
\sum_{1}^{\infty} |z_{n}| < \infty
$$
<html>
<body>
This shows that the partial sums converge to the infinite sum, which defines the limit:
</body>
</html>
$$
y_n = y_{0} + \sum_{k=1}^{n} z_{k} 
$$
<html>
<body>
with n goes to infinity:
</body>
</html>
$$
y_n = y_{0} + \sum_{k=1}^{\infty} z_{k} 
$$
<html>
<body>
In practice, the expression for zn may be complicated and the sum hard to calculate. We try instead to find simple bounds of the form \( |z_{n}| \le a_{n} \), where the numbers \( a_{n} \) are simple enough that
</body>
</html>
$$
\sum_{k=1}^{\infty} a_{n} <\infty
$$
<html>
<body>
is a direct explicit calculation. If this works, then the zn sum is finite because
</body>
</html>

$$
\sum_{k=1}^{\infty}|z_{n}| \le{ \sum_{k=1}^{\infty}a_{n}}< \infty
$$

<html>
<body>
Arguments like this are not quite enough for random sequences like \(Y_{n} = Y_{T}^{(h_{n})}\). The \(Y_{n} \) are random and the differences \(Z_{n} = Y_{n+1} − Y_{n} \) are random too. If \(Z_{n}\) is Gaussian,there is no bound of the form
</body>
</html>

$$
|Z_{n}| \le{a_{n}}
$$

<html>
<body>
At least, no bound that it true almost surely (i.e., with probability one). No matter how large an is, there is some tiny chance \( |Z_{n}|\) is larger.
</body>
</html>

<html>
<body>
The Borel Cantelli lemma is the fact that convergence follows from
</body>
</html>

$$
E[|Z_{n}|] \le a_{n}, \sum_{k=1}^{\infty} a_{n} <\infty.  (10)
$$

<html>
<body>
To see this define the random sum  (an infinite sum in the sense that there are infinitely many terms but a finite sum in the sense that the sum should be finite).
</body>
</html>
$$
 \sum_{1}^{\infty} |Z_{n}|
$$

<html>
<body>
In this sum, we set \( S = \infty \) if the sum is infinite. The following fact is called the monotone convergence theorem (you may know it in a more general form):
</body>
</html>

$$
 E|S| = \sum_{1}^{\infty} E[|Z_{n}|]
$$

<html>
<body>
If the inequality (10) is satisfied, then \( E[ S] < \infty \).
</body>
</html>

<html>
<body>
  The Borel Cantelli argument is to argue that if \( E[S] < \infty \) then \( S < \infty \) almost surely. This means that \( Pr(S=\infty)=0 \). If \( Pr(S=\infty)= \epsilon >0 \),then
</body>
</html>

$$
 E|S| = \sum_{1}^{ \infty } E[|Z_{n}|] E[S|S= \infty]\cdot Pr(S=\infty) + E[S|S<\infty] \cdot Pr(S<\infty)
$$

$$
 E|S| \ge \infty \cdot \epsilon
$$

$$
 E|S| = \infty 
$$

<html>
<body>
 If \( S < \infty \) then \( \sum|Z_{n}| < \infty \), which implies that the the limit of \(Y_{n} \) exists.
</body>
</html>

<html>
<body>
In the present application, will calculate an inequality
</body>
</html>

$$
 E[|Y^{h_{n} + 1} - Y^{h_{n}}|] \le {a_{n}}
$$

<html>
<body>
We will use the Cauchy Schwarz inequality, and first calculate
</body>
</html>

$$
 E[|Y^{h_{n} + 1} - Y^{h_{n}}|] \le{ C_{T}h_{n}}
$$

<html>
  <body>
    
Cauchy Schwarz implies that we can take (The two numbers \(C_{T}\) are not the same, but they both are “constants” that depend on T and on the problem but
not on n.)

  </body>
</html>

$$
a_{n} = \sqrt{C_{t}h_{n}} = C_{T}(\sqrt{2})^{-n}
$$

<html>
<body>
This verifies the hypothesis  and proves that the limit exists.

</body>
</html>


