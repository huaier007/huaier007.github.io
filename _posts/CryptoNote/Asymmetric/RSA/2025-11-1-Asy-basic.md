---
title: Basic of Asymmetric
author: Huaier
date: 2025-10-20
category: Asymmetric
layout: post
---

# 一.基础知识

## 欧几里得算法

首先介绍计算最大公约数(gcd)的问题。两个正整数$r_0$ 和 $r_1$ 的gcd表示为

$$
    \gcd(r_0,r_1)
$$

它指的是被 $r_0$ 和 $r_1$ 同时整除的最大正整数，例如gcd(21,9)=3,对小整数而言，gcd的计算非常容易，就是将两个整数因式分解，并找出最大的公共因子
然而，对公钥方案中使用的大整数而言，因式分解通常是不可能的，所以人们通常使用一种更有效的算法计算gcd，那就是**欧几里得算法**，此算法基于一个简单的观察，即

$$
    \gcd(r_0,r_1)=\gcd(r_0-r_1,r_1)
$$

其中，通常假设 $r_0>r_1$,并且两个数均为正整数，此属性的证明非常简单：假设gcd($r_0,r_1$)=g,由于g可以同时除 $r_0$ 和 $r_1$,既可以记作$r_0$=g\*x和$r_1$=g\*y,其中x>y,且x和y为互素的整数，即它们没有公共因子，此外，证明（x-y）与y互素也非常简单，因此可以得到：

$$
    \gcd(r_0-r_1,r_1)=\gcd(g*(x-y),g*y)=g  
$$

可参考链接 <https://blog.sengxian.com/algorithms/gcd-extgcd>

## 模运算

**加法：**

$$
    (a + b) \bmod p = (a \bmod p + b \bmod p) \bmod p 
$$

**减法：**

$$
    (a - b) \bmod p = (a \bmod p - b \bmod p) \bmod p
$$

**乘法：**

$$
    (a * b) \bmod p = (a \bmod p * b \bmod p) \bmod p
$$

**幂运算：**

$$
    (a ^ b) \bmod p = ((a \bmod p) ^ b) \bmod p
$$

## 中国剩余定理

设正整数 $m\_1,m\_2,...,m\_k$ 两两互素，则同余方程组：

$$
\begin{cases}
x \equiv a_1 ( \bmod \quad m_1) \\
x \equiv a_2 ( \bmod \quad m_2) \\
\dots \,\dots \\
x \equiv a_k ( \bmod \quad m_k) \\
\end{cases}
$$

有整数解，并且在模 $M = m\_1 * m\_2 * ... * m\_k$ 下的解是唯一的，解为

$x\equiv(a_1M_1M_1^-1+a2M_2M_2^-1+...+a_kM_kM_k^-1)mod M$

参考链接 <https://oi-wiki.org/math/number-theory/crt/>
