---
title: Hello World
math: true
---

$$
\begin{align}
&\underset{\boldsymbol{w}}{\min}\sum_{i=1}^N{\left( \boldsymbol{p}_i\boldsymbol{w} \right) ^2 },\,\, s.t. \,\left\| \boldsymbol{w} \right\| _2=1 \notag
\\
\Rightarrow &\underset{\boldsymbol{w}}{\min}\,\,\boldsymbol{w}^T\boldsymbol{P}^T\boldsymbol{Pw},\,\, s.t.\, \boldsymbol{w}^T\boldsymbol{w}=1
\end{align}
$$


$$
\begin{align}
\sum_{i=1}^N{d_{i}^{2}}&=\boldsymbol{w}^T\boldsymbol{P}^T\boldsymbol{Pw}\notag
\\
&=\left( -\lambda \right) \boldsymbol{w}^T\left( -\lambda \right) \boldsymbol{w}\notag
\\
&=\lambda ^2\boldsymbol{w}^T\boldsymbol{w}=\lambda^2
\end{align}
$$


$$
\begin{align}
d_i=\frac{a\hat{x}_i+b\hat{y}_i}{\sqrt{a^2+b^2}} \label{distance}
\end{align}
$$