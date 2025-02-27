# 3. 複素指数・三角の分解公式

　指数関数 *exponential function* と三角関数 *trigonometric function* は，一見して関係なく思えるものかもしれない．しかし複素数としては密接に関係しているのである．定数項 *constant term* がスフィア *sphere* として円状であることは，三角関数が円を微積分学に持つことと等価なのである．  

　一般に，指数関数の級数は  

$$e^x=\displaystyle\sum^{\infty}_{k=0}\frac{x^k}{k!} = 1+x+\frac{1}{2!}x^2+\frac{1}{3!}x^3+\frac{1}{4!}x^4+\cdots$$  

　と定義する．ここで $n!$ は階乗関数 *factorial function* である．三角関数の正弦・余弦の級数は  

$$\sin(x)=\displaystyle\sum^\infty_{k=0}\frac{(-1)^k x^{1+2k}}{(1+2k)!}=x-\frac{1}{3!}x^3+\frac{1}{5!}x^5-\frac{1}{7!}x^7+\cdots$$  
$$\cos(x)=\displaystyle\sum^\infty_{k=0}\frac{(-1)^k x^{2k}}{(2k)!}=1-\frac{1}{2!}x^2+\frac{1}{4!}x^4-\frac{1}{6!}x^6+\cdots$$  

　と定義され，指数関数と同様に，定数項が階乗の一般化であるガンマ関数 *gamma function* に満足していることが分かる．定数項は関数にある決まった数の項であり，ガンマ関数 $0!,1!,2!,3!,\ldots$ はこれに当てはまると言えよう．  

　ある関数の範囲を限って積分し，その値を求めることを考えよう．これを定積分 *definite integral* という． $x$ がこれについて定積分を考えることができたのなら，それは変数として $x$ が関数にしたがっているということである．  
　指数関数に従う全ての変数 $x$ が、そのようにして定積分を考えられるのであれば，実数全体がこの定積分に従うべきだろう．ところが指数には累乗根はないため，至って部分的である．累乗への式変形は $x$ が有理数にあるときに自明で，自然数 $m$ ， $n$ を用いて $x=\frac{m}{n}$ と表せる場合に $a^x=a^\frac{m}{n}=\sqrt[n]{a^m}$ と定義される．  
　実数 $x$ について $a^x$ を定めるには，実数 $x$ に収束する有理数の列 $x_1, x_2, \cdots, x_n\cdots$ を定め， $\displaystyle\lim_{n\to\infty}x_n=x$ を用いて， $a^x=\displaystyle\lim_{n\to\infty}a^{x_n}$ とする実用例がある．  
 
