# 3. 複素指数・三角の分解公式

　ある関数の範囲を限って積分し，その値を求めることを考えよう．これを定積分 *definite integral* という． $x$ がこれについて定積分を考えることができたのなら，それは変数として $x$ が関数にしたがっているということである．  
　定積分の関数 $f(x)$ の原始関数 *primitive function* を $F(x)$ とするとき， $F(b)-F(a)$ は関数 $f(x)$ の $a$ から $b$ までの定積分である．これは

$$\int_{a}^{b}f(x)dx=[F(x)]^b_a=F(b)-F(a)$$

　と表せる．ここで定積分を求める区間 $a\leq x\leq b$ を積分区間 *(integral's) inteval* と呼ぶ．  
 
　指数関数 *exponential function* に従う全ての変数 $x$ が、そのようにして定積分を考えられるのであれば，実数全体がこの定積分に従うべきだろう．ところが指数には累乗根はないため，至って部分的である．具体的には微分学の導入しかできない．  
　指数は累乗への式変形として $x$ が有理数 *rational number* にあるときに自明で，自然数 $m$ ， $n$ を用いて $x=\frac{m}{n}$ と表せる場合に  

$$a^x=a^\frac{m}{n}=\sqrt[n]{a^m}$$  

　と定義される．  
　実数 $x$ について $a^x$ を定めるには，実数 $x$ に収束する有理数の列 $x_1, x_2, \cdots, x_n\cdots$ を定め，
 
$$\displaystyle\lim_{n\to\infty}x_n=x$$

　を用いて，

$$a^x=\displaystyle\lim_{n\to\infty}a^{x_n}$$

　とする実用例がある．  
　しかしながら，これでは極限を求めることになり，分解公式における変数 $x$ が如何なる存在かの話題からは遠く離れている．これは，指数分解に収束する定理が話題にないからである．もっとも，分解公式の変数には従属性があり，ここでは一般類 *G-Variants* に話題が帰着している．そのため，帰着しない話題には，どのような解析学を持ち込んでも無意味ということになる．  
　では定理の話として話題を考えよう．ここで，指数関数と三角関数 *trigonometric function* は，一見して関係なく思えるものかもしれない．しかし複素数 *complex number* としては密接に関係しているのである．定数項 *constant term* がスフィア *sphere* として球状であることは，三角関数が円を微積分学に持つことと等価なのである．  

　一般に，指数関数の級数は  

$$e^x=\displaystyle\sum^{\infty}_{k=0}\frac{x^k}{k!} = 1+x+\frac{1}{2!}x^2+\frac{1}{3!}x^3+\frac{1}{4!}x^4+\cdots$$  

　と定義する．ここで $n!$ は階乗関数 *factorial function* である．三角関数の正弦・余弦の級数は  

$$\sin(x)=\displaystyle\sum^\infty_{k=0}\frac{(-1)^k x^{1+2k}}{(1+2k)!}=x-\frac{1}{3!}x^3+\frac{1}{5!}x^5-\frac{1}{7!}x^7+\cdots$$  
$$\cos(x)=\displaystyle\sum^\infty_{k=0}\frac{(-1)^k x^{2k}}{(2k)!}=1-\frac{1}{2!}x^2+\frac{1}{4!}x^4-\frac{1}{6!}x^6+\cdots$$  

　と定義され，指数関数と同様に，定数項が階乗の一般化であるガンマ関数 *gamma function* に満足していることが分かる．定数項は関数にある決まった数の項であり，ガンマ関数 $0!,1!,2!,3!,\ldots$ はこれに当てはまると言えよう．  
　これは微分 *differential calculus* を満足させ，マクローリンの定理を証明している．  
　マクローリンの定理とは，関数 $f(x)$ は $x=0$ を含む区間で $n$ 回微分可能であれば，  

$$f(x)=f(0)+\frac{f^{\prime}(0)}{1!}x+\frac{f^{\prime\prime}(0)}{2!}x^2+\cdots+\frac{f^{(n-1)}(0)}{(n-1)!}x^{n-1}+\frac{f^{(n)}(\theta x)}{n!}x^n$$  

　となる $\theta(0\lt \theta\lt 1)$ が存在するということである．一般にはテイラーの定理が用いられるが，テイラーの定理は $z=0$ の包括が明示にないといったニュアンスがある．  

　マクローリン級数 *maclaurin series* として複素指数関数  

$$e^z=\displaystyle\sum^{\infty}_{n=0}\frac{z^n}{n!}$$  

　を定義しよう．指数・正弦・余弦を同時に計算していることになるので  

$$e^z=e^{x+\imath y}=e^x(\cos y\ +\imath \sin y)$$  

　を得る．これは， $x=0$ とすると，次のような式になる．  

$$e^{\imath\theta}=(\cos \theta +\imath \sin \theta)$$

　これが有名な**オイラーの公式**である．  

　正弦・余弦をオイラーの公式によって微分方程式に満足させることを考えるのであれば，

$$\left\lbrace \begin{array}{cl}
\cos\theta & : \frac{e^{\imath\theta}+e^{-\imath\theta}}{2} \\
\sin\theta & : \frac{e^{\imath\theta}-e^{-\imath\theta}}{2\imath}
\end{array} \right.$$  

　 $e^{-\imath\theta}$ は  

$$e^{-\imath\theta}=(\cos \theta -\imath \sin \theta)$$  

　であり，オイラーの公式は

$$\left\lbrace \begin{array}{cl}
e^{\imath\theta} & : \cos\theta+\imath\sin\theta \\
e^{-\imath\theta} & : \cos\theta-\imath\sin\theta
\end{array} \right.$$  

　の変形を得る．この変形は数値計算では便利なので覚えておくとよい．  

　初等関数に還元されるところに分解公式は至ってシンプルな公式になることは前章で示された．オイラーの公式もそうだろう．例えば $-\imath\sin(\imath z)=\sinh(z)$ な双曲線関数 *hyperbolic function* は，マクローリンの定理で証明は可能である．  

$$\sinh(z)=\displaystyle\sum^\infty_{k=0} \frac{x^{1+2k}}{(1+2k)!}=z+\frac{z^3}{3!}+\frac{z^5}{5!}+\frac{z^7}{7!}+\cdots$$
$$\cosh(z)=\displaystyle\sum^\infty_{k=0} \frac{x^{2k}}{(2k)!}=1+\frac{z^2}{2!}+\frac{z^4}{4!}+\frac{z^6}{6!}+\cdots$$

　ここで双曲線 *hyperbola* とは，例えば $\sqrt{x^2-1}$ などによって幾何学的に得られる正負の相対であるような曲線をいう．定理からすると，三角関数の双曲線を得たかのようなバージョンであることを確認できる．  

　分解公式は微分・積分のいずれにも導入可能であるが，定理からすると，指数に導入できる積分は部分積分 *integration by parts* のみである．また，実数の根や虚数の根はそれの複素係数の中で現れ，有理関数の積分で明白なものである．  
　三角関数には虚数の根 $\imath=\sqrt{-1}$ が現れるため逆元は存在するだろう．とはいえ，無限大において発散している恐れもある．  

(執筆中)

参考文献:  
基礎から発展まで 三角関数 | 小林 道正 (著) | ベル出版 | 2020.1.25 (初版)  
新体系 大学数学 入門の教科書 上・下 | 芳沢 光雄 (著) | ブルーバックス | 2023.5.12 (2刷)
