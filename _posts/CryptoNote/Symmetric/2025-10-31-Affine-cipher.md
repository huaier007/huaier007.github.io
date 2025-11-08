---
title: Affine Ciphers
author: Huaier
date: 2025-10-20
category: Symmetric
layout: post
---

# 仿射密码介绍

在仿射密码中，加密函数定义为：   

$$
    e(x) = (ax+b) \mod 26 ,\enspace a,b \in \mathbb{Z}_{26}
$$

因为这样的函数被称为仿射函数，所以这样的密码体制也称为仿射密码（可以看出，当 $a=1$ 时，其对应的正是移位密码）

为了能对密文进行解密，必须保证所选用的仿射函数是一个单射函数。换句话说，对任意的 $Y \in \mathbb{Z}$ ，如下同余方程:  

$$
    ax + b ≡ y \enspace (\text{mod} 26 )
$$

有唯一解。上述同余方程等价于

$$
    ax ≡ y - b(\text{mod} 26)
$$

当 $y$ 遍历 $\mathbb{Z}\_{26}$ 时，显然 $y - b$ 亦遍历 $\mathbb{Z}\_{26}$，我们只需要研究同余方程 $ax ≡ y(\text{mod} 26)$ 即可（$y\in \mathbb{Z}\_{26}$）。
我们断言，以上同余方程有唯一解的充分必要条件是 $\gcd(a，26）= 1$（这里的gcd表示最大公约数）。首先，假设 $\gcd(a，26) = d > 1$。则同余方程 $ax ≡ 0 \enspace (\text{mod} 26)$ 至少有两个解，分别为 $x=0$ 和 $x=26/d$。这种情况下，加密函数不是一个单射函数，因此不能用来作为一个有效的加密函数。
