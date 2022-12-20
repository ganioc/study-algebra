抽象代数, abstract algebra, 
近世代数,  modern algebra, 
linear algebra,
groups symmetry,
二阶和更高阶数形式的算术研究和不定方程的研究，导致了环和理想的概念的产生。
拓扑学, topology, 

二元关系， 集合和运算本身,
group,  集合G, 二元关系*, G*G -> G, 的映射, 要求满足:
结合律, associativity, a,b,c,属于G, (a*b)*c = a*(b*c)
单位元存在, Identity, 存在e, ea=ae=a,
逆元的存在, a^-1, a*a^-1=a^-1*a=e,
<G, *>,一个集合和它的一个二元关系,
交换性, ab=ba, 
ab=ac, 则b=c,
ba=ca, 则b=c, 通过左乘和右乘, a^-1,
代数结构,
T={1,2,...,n}, 满足双射的一个映射f: T->T称为一个T的置换, 
双射，f(2)=1, f(1)=2, T={1,2}, 它的象的集合也是T, 是一个双射,
n元的置换，有n!种情况,
定义Sn为n元情况下的所有的置换，那么它是一个群，我们称为对称群,
群的元素都是映射，映射的乘法我们定义为复合，composition, 和函数复合的道理和运算法则是相同的。
S3 是最小的非交换的对称群,
S3 = { 1, x,y,x^2, xy, x^2y | x3=1, y^2 = 2, yx = x^2*y }
这个集合的约束条件，看出x,y表示这个集合的什么元素，通过一个群的部分元素进行不断的运算，是可以表示出这个完整的群的。
H=pZ, H!={0}, 有一系列的非零元素，取出最小的那个非零元素p,
h=pq + r, 0<r<p, H 是一个群，pq, 
整数群的子群的结构形式，

循环群,
G为一个群，a属于-G, n -属于N*, 使得a^n=e, a^k!=e, 0<k<n,那么我们说a的阶为n,
0(a)=n, 循环群就是指用一个元素就可以生成所有元素的群，
设G为一个群，如果存在一个x, 使得G可以表示成G={x^n | n 属于Z},那么G被称为循环群,
给定任意一个幂等矩阵A, 那么{e,A}就是一个循环群。显然是在矩阵乘法的意义下成立。A^2=E的时候满足。

群同态, homomorphism,
群的基本定义和性质后，就更加需要研究映射，代数的性质都是在映射中出现的。而群同态不过是从群的基本性质中引申出来的而已。
设G, G'为两个群，它们的单位元分别是e, e', 给定两个元素a,b属于G, 设映射$\varphi$ 为G->G', 满足$\varphi(a)\varphi(b)=\varphi(ab)$, 则说明这个群是一个同态,

群同态可以理解为二元关系在映射意义上的推广。

### 正规子群(normal subgroup)
G为一个群, H为G的一个子群, 那么对于任意的$h\in H ,\space g \in G$,我们有${g^{-1}}hg \in H$, 那么称$H$为一个正规子群。

我们给一个符号 $ H \lhd G $

群的中心, center,

### 群同构(isomorphism)
各向同性,

如果映射满足$\phi : G \rarr G^{'}$

(1) $\phi$ 是一个双射

(1) $\phi$ 满足群同构

那么$\phi$是一个同构。如果我们能够找到一个映射满足这个映射是一个同构映射，那么说明这两个群的结构是同构的，我们给一个记号$G \cong G^{'}$

同构在代数结构中是三大完美结构之一。在数学研究中如果找到了同构，就能把一个陌生问题转换到一个熟悉的问题上，进而方便解决。

### 群乘积(Group Multiplication)
$N1N2={n1n2 \space | \space n1\in N1, n2 \in N2}$
这被称为群乘积

陪集(Cosets),

### Modular arithmetic

$${a + kN : k \in Z}$$

任意两个数之间的差都是N的倍数, $a \equiv b$(mod N), 

### Montgometry form
如果a和b是$[0,N-1]$之间的一个整数, 那么它们的和的范围在$[0, 2N-2]$, 差的范围在$[-N+1, -N-1]$. 将之转化为$[0,N-1]$范围仅需要一次加法或减法。

然而如果是乘法的话, ab 的范围在$[0, N^{2} - 2N + 1]$, 存储中间的整数乘结果需要两倍的空间，a或者b. 有效地将结果重新表示的话需要除法。Euclidean division theorem,

$$ ab = qN + r$$

Montgometry算法就是干这个事情的。选择$R$, 使得$\gcd (R, N) = 1 $, 也需要division, reduction modulo $R$ 是轻量级的，没有那么昂贵。$ R > N $, 

Montgomery form of the residue class a, with respect R is aR mod N, 这就是转换形式, 看起来使问题更加负责了。

以蒙哥马利形式表示的数的乘法需要去除factor of R, 然而division by R is cheap, 

$$ (aR \space mod \space N)(bR \space mod \space N) \space mod \space N = (abR)R \space mod \space N $$

找到一个$R^{'}$,使得 $RR^{'}=1 \space (mod \space N)$, 这样就可以简化计算。

$$ (aR \space mod \space  N)(bR \space mod \space N)R^{'} = (aR)(bR)R^{-1} = (ab)R \space (mod \space N) $$

寻找$R^{'}$，首先它是存在的, R和N互质, extended Euclidean algorithm. Bezout's identity: $$ 0<R^{'} < N, 0 < N^{'} < R $$

$$ RR^{'} - NN^{'} = 1 $$

### Montgomery Reduction
REDC, 同时计算product by $R^{'}$ , reduces modulo N more quickly than the naive method. Montgomery reduciton focuses on making the number more divisible by $R$. 所有的计算，reduction, division, with respect to $R$, not $N$, 所以这个速度会比直接乘、除的速度会快得多。

reducing t into the desired range requries at most a single subtraction,

### Arithmetic in Montgomery form,
许多modulo N的操作也可以同样在Montgomery form中操作。这些算术操作包括: Addition, subtraction , negation, comparison for equality, multiplication by an integer not in Montgomery form, greatest common divisors with N man all be done with the standard algorithms. 

The **Jacobi symbol** can be calculated as:

$$
(\frac a N) = (\frac {aR} N) / (\frac R N) 
$$
as long as $(\frac R N) $ is stored.

When R > N, most other arithmetic operations can be expressed in terms of REDC. 

The product of aR mod N and bR mod N is REDC((aR mod N)(bR mod N)), 这个操作被称为Montgomery multiplication.

### 多精度整数的Montgomery arithmetic,
加密算法使用的数字，成百上千bit长, 无法存储在一个machine word里，那么对这些大数的乘法就需要结合几个小的乘法。一般来说base B会选择2, 

REDC算法需要modulo R的乘法, R> N, 因此有一个REDC的编程中，处理machine word sized integers. 假设positive multi-precision integers ares stored little endian. 

这个算法从一个多精度整数T开始，reduces it one word at a time. 首先an appropriate multiple of N is added to make T divisible by B, a multiple of N is added to make T divisible by $B^{2}$ , 直到T is divisible by $R$, 






