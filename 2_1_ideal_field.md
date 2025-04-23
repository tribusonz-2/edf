# 1. 形式的べき級数環およびp進イデアル体との関係

　従属変数 *dependent variable* が何らかの公式に従っているなら，その公式には従わせるための変数，いわば独立変数 *independent variable* が存在しているのではないかという見方がある．これは，議論としても，ほぼ肯定的な意見を得られるものだろう．例えば，前章で示されたような，初等関数に還元されるに至っては実にシンプルな式になるものは，その応用になる式にとって基礎に過ぎていない．ここでは指数と対数を用いる累乗 $x^y=e^{y log(x)}$ は典型と言える．  
　前章の分解公式にある変数は一般化 *generalization* を従属変数としているので，筆者はこれを従属一般変数 *dependent general variable* とした．ここでは独立変数こそ指数 *exponent* そのものであることは疑いようもない．では，その関係において一般化されない変数もあるのではないかという見方も出来上がる．これがここで詳しく述べる従属イデアル変数 *dependent ideal variable* である．  

　イデアル体について，たかだか $1/2$ を求めるという考えは，  

$\frac{1}{2^2}+\frac{1}{2^3}+\frac{1}{2^4}+\frac{1}{2^5}+\frac{1}{2^6}+\frac{1}{2^7}+\cdots=\frac{1}{2}$

　と無限等比級数 *infinite geometric series* に見られることがある．  
　こうした考えは，この公式では形式的べき級数環 *formal power series rings* と関係を持つことがわかっている．ただの多項式環と見ると，実に規則性を持っている．(ただし規則によっては途中で発散するものもある)  
　絶対収束よりは条件収束に変数の現れを持ち，その変数を $n$ とすると，それは有限個しか存在しない．こうした“中途半端”な部分和が連続して現れることで，分解公式は有限和に有界である．この体を $\text{EDF}^\prime F$ と定義すると，有限次元 *finite-dimensional* $V$ は部分和の集合を意味するものになる．この体はp進数 *p-adic numbers* と等価であり，p進イデアル体にも分解公式の変数が見えることがある．  

　この公式を発見した当初は，先述の様子と対数関数が混在したものであった．基数相補法 *radix complementation method* は今でこそ簡素であるものの，発見当初の変数は以下のCプログラムのように複雑を極めた．  

```CXX
// Radix Complementation Method
double
rcm2_core(register double x, int *exp)
{
	register int i, exp_val, have_sign;
	register double fra;
	//Radix table
	static const int radix_tab[5] = { 0, 1, 2, 4, 8 };
	//Resolution Table
	static const double reso_tab[5] =
		{
			1.0 / 2.0, 1.0 / 4.0, 1.0 / 16.0,
			1.0 / 256.0, 1.0 / 65536.0
		};
	
	if (isnan(x) || isinf(x))  { *exp = 0; return x; }
	if (x < 0)  { fra = rcm2_core(x, exp); return -fra; } /* Recursive call. Recommend do not use */
	
	exp_val = 0;
	fra = fabs(x);
	if (fra == 0.0) { *exp = 0; return 0; } /* Recommend do not use */
	else if (fra >=	1.0) { fra = foo(1 / fra); have_sign = 0; }
	else  have_sign = 1;
	for (;;) {
		// Binary search
		if (fra == 1.0) break; /* Exit the loop if the mantissa is equal to 1.0 */
		else if (reso_tab[0] <= fra)  i = 0;
		else if (reso_tab[1] <= fra)  i = 1;
		else if (reso_tab[2] <= fra)  i = 2;
		else if (reso_tab[3] <= fra)  i = 3;
		else if (reso_tab[4] <= fra)  i = 4;
		else                          i = 4;
		
		 // Exception when mantissa was 0.0 (i.e. exponent up 1)
		if (!have_sign && fra ==  reso_tab[0])  i++;
		exp_val += radix_tab[i]; // Add
		
		// If the complement factor is 0, exit the loop
		if (radix_tab[i] == 0)
		{
			fra = (!have_sign) ? foo(1 / fra) : foo(fra * 2);
			break;
		}
		foo(fra /= reso_tab[i-1]); // Weighting
	}
	
	
	if (have_sign) 	exp_val = ~exp_val;
	*exp = exp_val;
	return fra;
}
```

(執筆中)

参考文献:  
p進ゼータ関数 久保田-レオポルドから岩沢理論へ | 青木 美穂 (著) | 日本評論社 | 2019.2.20 (1版1刷)  
p進解析入門 p進数からゼータ関数まで | ニール・コブリッツ (著), 長岡 昇勇 (訳) | 丸善出版 | R7.1.30  
