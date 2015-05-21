---
layout: post
title: 概率统计学相关笔记（九）
---

##概率统计学相关笔记（九）##

这里介绍几个常见的分布的最大似然估计解析解。

1. 多元高斯分布。
令$X\sim N(\mu,\Sigma)$为k元高斯分布，$X_1,\dots,X_n$为iid样本。似然函数为
$$\begin{array}{l}L(\mu,\Sigma) & = & \prod_{i=1}^n\frac{1}{\sqrt{(2\pi)^k|\Sigma|}}e^{-\frac{1}{2}(X_i-\mu)^T\Sigma^{-1}(X_i-\mu)} \\& = & C|\Sigma|^{-\frac{n}{2}}e^{\sum_{i=1}^n-\frac{1}{2}(X_i-\mu)^T\Sigma^{-1}(X_i-\mu)}\end{array}$$
对数似然函数为
$$\begin{array}{l}l(\mu,\Sigma)=\frac{n}{2}\ln|\Sigma^{-1}|-\frac{1}{2}\sum_{i=1}^n(X_i-\mu)^T\Sigma^{-1}(X_i-\mu)+const\end{array}$$
$$\begin{array}{l}\frac{\partial l}{\partial\mu} & = & \Sigma^{-1}\sum_{i=1}^n(X_i-\mu) \\\frac{\partial l}{\partial\Sigma^{-1}} & = & \frac{n}{2}\Sigma-\frac{1}{2}\sum_{i=1}^n(X_i-\mu)(X_i-\mu)^T\end{array}$$
令上述偏导等于0得最大似然估计为
$$\begin{array}{l}\mu_{MLE} & = & \frac{1}{n}\sum_{i=1}^nX_i \\\Sigma_{MLE} & = & \frac{1}{n}\sum_{i=1}^n(X_i-\mu)(X_i-\mu)^T \end{array}$$

2. 伯努力分布
令$X\sim Bernoulli(p)$为伯努力分布，$X_1,\dots,X_n$为iid样本，似然函数为
$$\begin{array}{l}L(p) & = & \prod_{i=1}^np^{X_i}(1-p)^{1-X_i} \\& = & p^{\sum_{i=1}^nX_i}(1-p)^{n-\sum_{i=1}^nX_i}\end{array}$$
对数似然函数为
$$\begin{array}{l}l(p)=(\sum_{i=1}^nX_i)\ln p+(n-\sum_{i=1}^nX_i)\ln(1-p)\end{array}$$
$$\begin{array}{l}\frac{\partial l}{\partial p} & = & \frac{\sum_{i=1}^nX_i}{p}-\frac{n-\sum_{i=1}^nX_i}{1-p}\end{array}$$
令上述偏导数等于0得最大似然估计为
$$\begin{array}{l}p_{MLE} & = & \frac{1}{n}\sum_{i=1}^nX_i \end{array}$$

3. 几何分布
令$X\sim Geom(p)$为几何分布，$X_1,\dots,X_n$为iid样本，似然函数为
$$\begin{array}{l}L(p) & = & \prod_{i=1}^np(1-p)^{X_i-1} \\& = & p^n(1-p)^{\sum_{i=1}^nX_i -n}\end{array}$$
对数似然函数为
$$\begin{array}{l}l(p)=n\ln p+(\sum_{i=1}^nX_i-n)\ln(1-p)\end{array}$$
$$\begin{array}{l}\frac{\partial l}{\partial p} & = & \frac{n}{p}-\frac{\sum_{i=1}^nX_i-n}{1-p}\end{array}$$
令上述偏导数等于0得最大似然估计为
$$\begin{array}{l}p_{MLE} & = & \frac{1}{\frac{1}{n}\sum_{i=1}^nX_i} \end{array}$$

4. 一致分布
令$X\sim Uniform(a,b)$为一致分布，$X_1,\dots,X_n$为iid样本，当任何一个样本小于a或大于b时，似然函数都为0。设所有样本都在区间[a,b]内，则似然函数为
$$\begin{array}{l}L(a,b) & = & \prod_{i=1}^n\frac{1}{b-a} \end{array}$$
则当
$$\begin{array}{l}a_{MLE} & = & \min_iX_i \\ b_{MLE} & = & \max_iX_i\end{array}$$
时，似然函数取最大值。

5. 指数分布
令$X\sim Exp(\beta)$为指数分布，$X_1,\dots,X_n$为iid样本，似然函数为
$$\begin{array}{l}L(\beta) & = & \prod_{i=1}^n\frac{1}{\beta}e^{-\frac{X_i}{\beta}} \\& = & \beta^{-n}e^{-\frac{1}{\beta}\sum_{i=1}^nX_i}\end{array}$$
对数似然函数为
$$\begin{array}{l}l(\beta)=-n\ln\beta-\frac{1}{\beta}\sum_{i=1}^nX_i\end{array}$$
$$\begin{array}{l}\frac{\partial l}{\partial\beta} & = & -\frac{n}{\beta}+\frac{1}{\beta^2}\sum_{i=1}^nX_i\end{array}$$
令上述偏导数等于0得最大似然估计为
$$\begin{array}{l}\beta_{MLE} & = & \frac{1}{n}\sum_{i=1}^nX_i \end{array}$$


