# LaTex note

## Latex math mode

* 行内公式

```latex
$ f(x) = a + b $
```

output: $ f(x) = a \times b $

* 行间公式

```latex
$$
\begin{equation}
f(x) = a + b
\end{equation}
$$
```

output:
$$
\begin{align}
f(x) = a + b\tag{1.1}
\end{align}
$$


这个 (1.1) 是`\tag{1.1}`

```latex
$$
% This is comment
\lim\limits_{x \to \infty} x^2_{22}
$$
```

 注释方法如上

### 简单运算

拉丁字母、阿拉伯数字和 +-*/= 运算符均可以直接输入获得，命令\cdot表示乘法的圆点，命令\neq表示不等号，命令\equiv表示恒等于，命令\bmod表示取模

```latex
$ x + 2 - 3 \cdot \frac{4}{6} \neq \frac{4}{y} \bmod x \cdot y \equiv x + z $
```

output: $ x + 2 - 3 \cdot \frac{4}{6} \neq \frac{4}{y} \bmod x \cdot y \equiv x + z $

### 根号,分式

`\sqrt` 平方根, `\sqrt[n]` 表示 n 次方根, `\frac` 表示分式

```latex
$$
\begin{align}
\sqrt{x} + \sqrt{x^{2} + \sqrt{y}} = \sqrt[3]{k_i} - \frac{x}{m}
\end{align}
$$
```


$$
\begin{align}
\sqrt{x} + \sqrt{x^{2} + \sqrt{y}} = \sqrt[3]{k_i} - \frac{x}{m} \tag{1.2}
\end{align}
$$

### 上下标记

`\overline, \underline` 上下水平线

```latex
$$
\overline{x + y} \qquad \underline{a + b} 
$$
```

$$
\overline{x + y} \qquad \underline{a + b} \tag{1.3}
$$

## 大括号

`\overbrace,\underline` 上下给出一个大括号

```latex
$$
\overbrace{1 + 2 + \cdots + n}^{n} \qquad \underbrace{a + b+ \cdots + z}_{26}
$$
```

$$
\overbrace{1 + 2 + \cdots + n}^{n 个} \qquad \underbrace{a + b+ \cdots + z}_{26} \tag{1.4}
$$

### 向量

`\vec` 表示向量, `\overrightarrow` 箭头向右的向量, `\overleftarrow` 箭头向左的向量

```latex
$$
\begin{align}
\vec{a} + \overrightarrow{AB} + \overleftarrow{DE} + \underrightarrow{FG} + \vec{BX} 
\end{align} 
$$
```

$$
\begin{align}
\vec{a} + \overrightarrow{AB} + \overleftarrow{DE} + \underrightarrow{FG} + \vec{BX} \tag{1.5}
\end{align}
$$

### 积分,极限

`\int` 积分, `lim` 极限, `\sum` 求和, `\prod` 乘积

```latex
$$
\begin{align}
\limits_{x \to \infty} x^2_{22} - \int{1}^5}x\mathrm{d}x + \sum_{n = 1}^{20} n^2 
& = \prod_{j = 1}^{3} y_{j} + \lim_{x \to -2} \frac{x-2}{x} 
\end{align}
$$
```

$$
\begin{align}
\lim\limits_{x \to +\infty} x^2_{22} - \int{1}^5x\mathrm{d}x + \sum_{n = 1}^{20} n^2 & = \prod_{j = 1}^{3} y_{j} + \lim_{x \to -2} \frac{x-2}{x} \tag{1.6}
\end{align}
$$

### 重音符号

$ \hat{x} $ and $ \bar{x} $ and $ \tilde{x} $

#### 常见希腊字母

<center>小写希腊字母</center>

`\alpha` $\alpha$, `\beta` $\beta$, `gamma` $\gamma$, `\delat` $\delta$, `\epsilon` $\epsilon$, `\eta` $\eta$, `\theta` $\theta$, `lambda` $\lambda$, `\pi` $\pi$, `\mu` $\mu$

<center>大写希腊字母</center>

`\Delta` $\Delta$, `\Theta` $\Theta$ `\Pi` $\Pi$, `\Lambda` $\Lambda$, `\Phi` $\Phi$

## 公式组合

```latex
$$
D(x) = \begin{cases}
\lim\limits_{x \to 0} \frac{a^x}{b+c}, & x < 3 \\
\pi, & x = 3 \\
\int_a^{3b} x_{ij} + e^2 \mathrm{d}x, & x > 3 \\
\end{cases}
$$
```

$$
D(x) = \begin{cases}
\lim\limits_{x \to 0} \frac{a^x}{b+c}, & x<3 \newline
\pi, & x=3 \newline
\int_a^{3b} x_{ij} + e^2 \mathrm{d}x, & x>3 \newline
\end{cases}\tag{2.1}
$$

## 拆分公式

```latex
$$
\begin{split}
\cos 2x & = cos^2x - sin^2x \newline
& = 2 cos^2x - 1
\end{split}
$$
```

$$
\begin{split}
\cos2x & = \cos^2x - \sin^2x \newline
& = 2 \cos^2x - 1
\end{split}\tag{2.2}
$$

