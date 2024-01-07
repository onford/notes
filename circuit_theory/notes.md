<style>
    h1,h2{
        border-bottom : none;
        font-family: "Times New Roman","宋体";
    }
    p,div{
        font-family: "Times New Roman","宋体";
        font-size:17px;
    }
    bw{
        font-family: "Times New Roman","仿宋";
        font-size:17px;
    }
    st{
        font-family:"Times New Roman","宋体";
        color: red;
    }
    blockquote{
        font-family:"Times New Roman","仿宋";
        font-size:17px;
        border-left: 5px solid #ccc;
    }
    table,th,td{
        font-size:17px;
        font-family:"Times New Roman","宋体";
        border: 1px solid;
        text-align:center;
    }
    caption{
        font-family:"Times New Roman","黑体";
        font-size:17px;
    }
    img{
        margin: 0 auto;
        left:50%;
        right:50%;
        width: 30%;
    }
</style>

# 电路理论笔记

<bw>wr按：\
这一部笔记，主要记录学习过程中的一些想法，以便后续查看时能回忆起当时的理解，并加深印象。实际上并不全面，只是自己想到的一些东西。</bw>

## $Chapter1$&emsp;电路模型与基本定律
**一、电路变量与元件**\
&emsp;&emsp;对包括电源在内的各种电路器件而言，当$u,i$选择**关联**的参考方向时，$p=ui$就是**吸收功率**。对于非直流电路，严格来说是**瞬时**吸收功率。\
&emsp;&emsp;课本上的四种受控电源都是**有源元件**，能够提供功率。这个功率来自受控源本身，课本上也没有详细说明受控源提供的能量来自哪里。是像电池一样储存在受控源内部的能量吗？事实上课本上的受控源是高度抽象的电路模型，不需要过多地纠结。\
**二、基尔霍夫定律**\
&emsp;&emsp;电路的基本定律就是基尔霍夫定律，其中包含基尔霍夫电流定律（KCL）和基尔霍夫电压定律（KVL）。\
&emsp;&emsp;**基尔霍夫电流定律**：集中参数电路中，任何时刻流入一个结点（或者一个闭合面）的支路电流的代数和为$0$.也即：
$$\sum _{k=1}^b i _k=0\tag{1.1}$$

&emsp;&emsp;这个实际上就是<st>电流连续性方程</st>。这里没有位移电流项，因为在电路里不能把类似电容这样的元器件拆开来看作两个极板，要整体地看成一个器件。\
&emsp;&emsp;**基尔霍夫电压定律**：集中参数电路中，任何时刻，任意一个回路中所有支路电压代数和为$0$.即：
$$\sum _{k=1}^b u _k=0\tag{1.2}$$
## $Chapter2$&emsp;电阻电路等效变换
&emsp;&emsp;等效变换的意义是在**不改变端口$u-i$关系**的前提下，简化电路的结构。对于电源支路，电流源串联其它元件，与串联元件被短路后等效；电压源并联其它元件，与并联元件被断路后等效。\
**一、星形电路和三角形电路**\
&emsp;&emsp;如果是对称电路的话，问题就很好解决。假设端口$ab$为上下方向，有下表。
<table align="center">
<caption align="top">表 对称电路的电压与电流</caption>
    <tr>
        <th>对称方式</th>
        <td>对称面过端口</td>
        <td>对称面垂直端口</td>
    </tr>
    <tr>
        <th>电流关系</th>
        <td>对称的支路电流相等<br>$$i _L=i _R$$</td>
        <td></td>
    </tr>
    <tr>
        <th>电压关系</th>
        <td>关于对称面对称的点，电势相同</td>
        <td>对称面上所有点的电势都为<br>$$\varphi=\cfrac{\varphi _a+\varphi _b}{2}$$</td>
    </tr>
</table>

&emsp;&emsp;如果不是对称电路，一般就需要用到星-三角互换。\
&emsp;&emsp;**$\Delta\rightarrow \mathrm Y$**：
$$\begin{cases}R _1=\cfrac{R _{12}R _{31}}{R _{12}+R _{23}+R _{31}}\\\\
R _2=\cfrac{R _{23}R _{12}}{R _{12}+R _{23}+R _{31}}\\\\
R _3=\cfrac{R _{23}R _{31}}{R _{12}+R _{23}+R _{31}}\end{cases}\tag{2.1}$$ 

&emsp;&emsp;规律是$R _k=\cfrac{连于k结点的两个电阻之积}{\Delta内三个电阻之和}$.\
&emsp;&emsp;**$\mathrm Y\rightarrow \Delta$**：
$$\begin{cases}G _{12}=\cfrac{G _1G _2}{G _1+G _2+G _3}\\\\
G _{23}=\cfrac{G _2G _3}{G _1+G _2+G _3}\\\\
G _{31}=\cfrac{G _3G _1}{G _1+G _2+G _3}\end{cases}\tag{2.2}$$

&emsp;&emsp;规律是$G _{kj}=\cfrac{连于k、连于j结点的两个电导之积}{\mathrm Y内三个电导之和}$.\
**二、电源变换**\
&emsp;&emsp;主要就是诺顿支路与戴维南支路相互变换。\
&emsp;&emsp;**诺顿$\rightarrow$戴维南**：$(I _s)\parallel (R)\rightarrow (U _s=I _s\cdot R)+R$\
&emsp;&emsp;**戴维南$\rightarrow$诺顿**：$(U _s)+(R)\rightarrow(I _s=U _s/R)\parallel(R)$\
&emsp;&emsp;变换之后还需要注意，变换前后电压源、电流源的方向相反（类似于非关联）。如果是控制源，也可以按照这样的规则变换。但是要达到最简等效电路的话，必须要把控制源变换成电阻。
<blockquote>
&emsp;&emsp;当受控源的$u-i$关系（关联参考方向）满足$u/i=R _c$（其中$R _c$时常量）时，就可以用一个大小为$R _c$的电阻等效替换这个受控源。$R _c$与一般的电阻不同，极有可能是负值，也有可能是$0$.
</blockquote>

## $Chapter3$&emsp;电路分析方程
&emsp;&emsp;用基尔霍夫定律，方程多，变量也多。所以考虑使用**结点方程**或**网孔方程**。\
**一、结点方程**\
&emsp;&emsp;结点方程，其实是在KCL方程组中，用<strong>结点电势$u _\mathrm n$消去支路电流$i$</strong>得到的。先标记结点$u _{\mathrm n0}$的电势为$0$，其他结点分别记为$u _{\mathrm n1\cdots\mathrm na}$.快速列写为方程$(3.1)$所示：
$$\begin{bmatrix}G _{11}&\cdots& G _{1a}\\\\
\vdots&\ddots&\vdots\\\\
G _{a1}&\cdots&G _{aa}\end{bmatrix}\begin{bmatrix}u _{\mathrm n1}\\\\
\vdots\\\\u _{\mathrm na}
\end{bmatrix}=\begin{bmatrix}i _{\mathrm{Sn}1}\\\\
\vdots\\\\ i _{\mathrm{Sn}a}\end{bmatrix}\tag{3.1}$$

&emsp;&emsp;$G _{kk}$是与结点$k$相连所有支路的电导之和，称为结点$k$的自电导。$G _{kj}(k\neq j)$是结点$k,j$之间支路电导的<st>相反数</st>，称为$k,j$结点的互电导。$i _{\mathrm{Sn}k}$是由电流源<st>流入</st>结点$k$的电流代数和。\
&emsp;&emsp;由此就可以解出结点$k$的电势$u _{\mathrm nk}$.\
&emsp;&emsp;使用节点方程前，要注意以下两种情况：\
&emsp;&emsp;1.先简化电源支路，以免干扰电导矩阵的列写。\
&emsp;&emsp;2.戴维南支路应全部转化为诺顿支路。
<blockquote>&emsp;&emsp;所谓简化电源支路，指的是以下两种情况：电流源串联了一个电阻，或者电压源并联了一个电阻。根据电源支路的等效变换，我们应直接把电阻给删了，以免后面出现不必要的麻烦。<br>
&emsp;&emsp;但是，如果要求电路中相应电源的功率的话，在解完结点方程后，还应把电路还原。
</blockquote>


&emsp;&emsp;使用节点方程的时候，对于电源支路的处理：\
&emsp;&emsp;1.支路上只有电流源，不参与电导矩阵的列写。\
&emsp;&emsp;2.支路上只有电压源。\
&emsp;&emsp;&emsp;&emsp;a.如果支路连接到结点$\mathrm n _0$，直接得出支路另一个结点的电势，其它结点正常列写方程，合计方程个数仍为$a$个。\
&emsp;&emsp;&emsp;&emsp;b.支路不连接到$\mathrm n _0$，应该把电压源支路的两个端头结点合并成一个广义结点，再弥补一个电压方程：比如电压源$u _s$的升压方向为结点$j\rightarrow k$，把$j,k$看作广义节点，再弥补一个方程$u _{\mathrm nk}-u _{\mathrm nj}=u _s$，合计方程个数仍为$a$个。\
**二、网孔方程**\
&emsp;&emsp;网孔方程，其实是在KVL方程组中，用<strong>网孔电流$i _m$消去各元件的电压$u$</strong>得到的。假设网孔电流设为$i _{\mathrm m1\cdots\mathrm mb}$.快速列写为方程$(3.2)$所示：
$$\begin{bmatrix}R _{11}&\cdots&R _{1b}\\\\
\vdots&\ddots&\vdots\\\\
R _{b1}&\cdots&R _{bb}\end{bmatrix}\begin{bmatrix}i _{\mathrm m1}\\\\
\vdots\\\\
i _{\mathrm mb}
\end{bmatrix}=\begin{bmatrix}
u _{\mathrm{Sm}1}\\\\
\vdots\\\\
u _{\mathrm{Sm}b}
\end{bmatrix}\tag{3.2}$$

&emsp;&emsp;$R _{kk}$是网孔$k$内所有支路的电阻之和，称为网孔$k$的自电阻。$R _{kj}(k\neq j)$是网孔$k,j$的公共支路电阻的<st>相反数</st>，称为网孔$k,j$的互电阻。$u _{\mathrm{Sn}k}$是沿着网孔$k$的电流方向电压源<st>升压</st>代数和。\
&emsp;&emsp;由此就可以解出网孔$k$的电流$i _{\mathrm mk}$.
<blockquote>
    &emsp;&emsp;教材上，默认了所有网孔电流的参考方向都是顺时针方向。其实每个网孔电流的方向都可以随意规定，只要列写方程时满足$u _\mathrm{Sn}$的书写规则（沿网孔电流方向<strong>升压</strong>），解出来的$i _\mathrm m$就是当前参考方向的网孔电流值。
</blockquote>

&emsp;&emsp;使用网孔方程前，要注意一下两种情况：\
&emsp;&emsp;1.先简化电路，同结点方程列写时的处理。\
&emsp;&emsp;2.诺顿支路应全部转化为戴维南支路。\
&emsp;&emsp;使用节点方程的时候，对于电源支路的处理：\
&emsp;&emsp;1.支路上只有电压源，不参与电阻矩阵的列写。\
&emsp;&emsp;2.支路上只有电流源。\
&emsp;&emsp;&emsp;&emsp;a.如果支路在电路边缘（只有一个网孔电流经过它），直接得出该网孔的电流，其它网孔正常列写方程，合计方程个数仍为$b$个。\
&emsp;&emsp;&emsp;&emsp;b.支路不在网孔边缘，应该把电流源支路两边的网孔合并成一个广义网孔，再弥补一个电流方程：比如电流源$i _s$支路被网孔$j,k$的电流经过，网孔$j$的电流与电流源是关联方向，网孔$k$的电流与电流源是非关联方向，把$j,k$看作广义网孔，再弥补一个方程$i _{\mathrm mj}-i _{\mathrm mk}=i _s$，合计方程个数仍为$b$个。\
&emsp;&emsp;网孔法无法应用于**非平面电路**。

## $Chapter4$&emsp;电路定理
**一、叠加定理与替代定理**\
&emsp;&emsp;**叠加定理**：线性电阻电路中，多个独立电源共同激励下的响应，等于独立电源单独激励下相应的代数和。\
&emsp;&emsp;线性电阻电路的相应和激励又是**齐次线性关系**，所以叠加定理可以表述为下式：
$$i(\mathrm{or\ } u)=\sum _{j=1}^n k _ju _{\mathrm sj}+\sum _{j=1}^mk'_ji _{\mathrm sj}\tag{3.3}$$

&emsp;&emsp;“齐次”表现在式$(3.3)$等号右边没有加上什么常数。只要确定所有系数$k$，响应就能够由各个电源的参数表示。
<blockquote>
&emsp;&emsp;如果要求$k _t$，可以把除电压源$u _{\mathrm st}$之外的电源全部置零，在置零后的电路中，就有$i(\mathrm{or\ }u)=k _tu _{\mathrm st}$，从而求出系数$k _t$.每一个系数都可以这样求。<br>
&emsp;&emsp;电压源置零相当于将其短路，电流源置零相当于将其断路。
</blockquote>

&emsp;&emsp;**替代定理**：在任何电路中，如果某条支路$k$的电压为$u _k$，则支路可以用电压源$ u _k$替代；如果支路$k$的电流为 $i _k$，则支路可用电流源$i _k$替代。在原电路和替换后电路<st>均具有唯一解</st>的条件下，两个电路的工作状态相同。\
**二、戴维南定理和诺顿定理**\
&emsp;&emsp;这两个定理都是对一端口**含电源**线性电阻网络的等效变化。戴维南定理将网络等效变换为戴维南电路，诺顿定理将网络等效变换为诺顿电路。\
&emsp;&emsp;**戴维南定理**：含有独立电源的一端口线性电阻网络，对端口以外的电路 而言，等效为<st>由电压源$u _{\mathrm{OC}}$和电阻$R _\mathrm{eq}$串联</st>的戴维南支路，称为戴维南等效电路。其中$u _\mathrm{OC}$是网络的<st>端口开路电压</st>，$R _\mathrm{eq}$是网络内部全部置零后的<st>端口等效电阻</st>。\
&emsp;&emsp;**诺顿定理**：含有独立电源的一端口线性电阻网络，对端口以外的电路而言，等效为<st>由电流源$i _\mathrm{SC}$和电阻$R _\mathrm{eq}$并联</st>的诺顿支路，称为诺顿等效电路。其中$i _\mathrm{SC}$是<st>端口短路电流</st>，$R _\mathrm{eq}$是网络内部独立电源全部置零后的端口等效电阻。
<blockquote>
&emsp;&emsp;一般碰到的电路都是由独立电压（电流）源、受控源、电阻组成的，这样的电路都是线性电阻网络，都可以使用上面两个定理。<br>
&emsp;&emsp;在用戴维南定理求$u _\mathrm{OC}$时，如果网络内部只有一个独立电源，可以运用基尔霍夫定律或者电路方程求解。当网络中出现<strong>多个独立电源</strong>的时，运用叠加定理，分别对单个独立电源激励的情况求解。在用诺顿定理求$i _\mathrm{SC}$时也是如此。<br>
&emsp;&emsp;上面两个定理求$R _\mathrm{eq}$时，都是在松弛网络里求解的。所谓松弛网络，就是网络中所有电源置零后得到的网络。松弛网络可能是纯电阻网络，这种情况挺好求解的,使用$Chapter2$中的方法。当松弛网络中<strong>含有受控源</strong>的时候，要通过写出端口的$u-i$关系求$R _\mathrm{eq}$.
</blockquote>

**三、最大功率传输定理**\
&emsp;&emsp;求某线性电阻网络中可变电阻$R$的最大传输功率，一般将电路中$R$外的一端口网络等效为戴维南支路，当$R$等于$R _\mathrm{eq}$时，获得最大功率$P _\mathrm{max}=\cfrac{U _\mathrm{OC}^2}{4R _\mathrm{eq}}$.

## $Chapter7$&emsp;电容、电感及动态电路
**一、广义函数**\
**1.单位阶跃函数**\
&emsp;&emsp;为了动态电路表示的需要，定义了一些特殊的函数。首先是单位阶跃函数：
$$\varepsilon(t)=\begin{cases}1& t > 0,\\\\0&t < 0.\end{cases}\tag{7.1}$$

&emsp;&emsp;函数在$t=0$处无定义，并且函数值在这里从$0$跳到$1$.阶跃函数有一些性质，比如$\varepsilon(t)+\varepsilon(-t)=1$.可以拓展为对$t$的任意函数$f(t)$，有：
$$\varepsilon(f(t))+\varepsilon(-f(t))=1\tag{7.2}$$

&emsp;&emsp;式$(7.2)$在这一章后面的计算、化简中经常会用到。\
**2.闸门函数**\
&emsp;&emsp;闸门函数的定义：
$$G(t _1,t _2)=\begin{cases}1&t _1< t < t _2,\\\\0& t < t _1\mathrm{\ or\ }t > t _2.\end{cases}\tag{7.3}$$
<blockquote>
&emsp;&emsp;$G(t _1,t _2)$其实是一种极致的简写，这样的写法甚至省略了自变量，只保留函数参数。一般闸门函数$G$的自变量就是$t$，也许写成$G(t,t _1,t _2)$更严谨一些。
</blockquote>

&emsp;&emsp;在$t _1\leq t _2$的情况下（一般不会跑出这种情况），$G(t _1,t _2)$满足：
$$G(t _1,t _2)=\varepsilon(t-t _1)-\varepsilon(t-t _2)=\varepsilon(t-t _1)\times\varepsilon(t _2-t)\tag{7.4}$$

&emsp;&emsp;为了避免高次项的出现，我们一般采用前一个等号。
<blockquote>
&emsp;&emsp;我们可以定义这样的式子：$\varepsilon(t+\infty)=\varepsilon(+\infty)=1,\varepsilon(t-\infty)=\varepsilon(-\infty)=0$.这样可以获得闸门函数的两种特殊情况：
$$\begin{aligned}G(-\infty,t _2)&=\varepsilon(t+\infty)-\varepsilon(t-t _2)=1-\varepsilon(t -t _2)=\varepsilon(t _2-t)\\
G(t _1,+\infty)&=\varepsilon(t-t _1)-\varepsilon(t _2-\infty)=\varepsilon(t-t _1)\end{aligned}\tag{7.5}$$
&emsp;&emsp;定义这两个式子可以方便一些解题。比如将$u=\begin{cases}2&t < 0\\
-5&0 < t <1\\
0& t > 1\end{cases}$写成广义函数，就可以这样：
$$\begin{aligned}u&=2G(-\infty,0)-5G(0,1)+0G(1,+\infty)\\
&=2\varepsilon(-t)-5[\varepsilon(t)-\varepsilon(t-1)]+0\\
&=2\varepsilon(-t)-5\varepsilon(t)+5\varepsilon(t-1)\end{aligned}\tag{7.6}$$
</blockquote>

**3.单位冲激函数**\
&emsp;&emsp;单位冲激函数$\delta(t)$定义如下：
$$\begin{cases}\begin{aligned}&\delta(t)=0,t\neq 0\\\\
&\int_{-\infty}^{+\infty}\delta(t)\mathrm dt=1\end{aligned}\end{cases}\tag{7.7}$$

&emsp;&emsp;可以理解为函数在$x=0$处取到了一个无穷大的值，$\delta(t)$超出了普通函数的范畴。它和$\varepsilon(t)$之间的关系为：
$$\begin{aligned}&\delta(t)=\cfrac{\mathrm d\varepsilon(t)}{\mathrm dt}&\varepsilon(t)=\int _{-\infty}^t\delta(t)\mathrm dt\\\\
&\delta(t-t _0)=\cfrac{\mathrm d\varepsilon(t-t _0)}{\mathrm dt}&\varepsilon(t-t _0)=\int _{-\infty}^t\delta(t-t _0)\mathrm dt\end{aligned}\tag{7.8}$$

**4.广义函数的运算**\
&emsp;&emsp;根据式$(7.8)$，可以比较容易地对具有$\varphi(t)\varepsilon(t-t _0)$形式的函数进行微分。一般不涉及到冲激函数$\delta(t)$的微分。\
&emsp;&emsp;冲激函数的<st>筛分性</st>比较重要：
$$f(t)\delta(t-t _0)=f(t _0)\delta(t-t _0)\tag{7.9}$$

&emsp;&emsp;依据式$(7.9)$可以进行具有$\varphi(t)\delta(t-t _0)$形式的函数进行积分：
$$\int _a^bf(t)\delta(t-t _0)\mathrm dt=\int _a^bf(t _0)\delta(t-t _0)\mathrm dt=f(t _0)\int _a^b\delta(t-t _0)\mathrm dt\tag{7.10}$$

&emsp;&emsp;对具有$\varphi(t)\varepsilon(t-t _0)$形式的函数进行的积分：
$$\int _{-\infty}^t\varphi(t)\varepsilon(t-t _0)\mathrm dt=\varepsilon(t-t _0)\int _{t _0}^t\varphi(t)\mathrm dt\tag{7.11}$$

**二、电容**\
&emsp;&emsp;储存电场能量的元件，$q=Cu$.其$u-i$关系：
$$\begin{aligned}& i=\cfrac{\mathrm dq}{\mathrm dt}=\cfrac{\mathrm d(Cu)}{\mathrm dt}=C\cfrac{\mathrm du}{\mathrm dt}\\\\
& u(t)=u(0 _-)+\cfrac{1}{C}\int _{0 _-}^ti\mathrm dt\end{aligned}\tag{7.12}$$

**1.电容串联**\
&emsp;&emsp;$n$个电容为$C _k$，初始电压为$u _{k0}(k=1,2,\cdots ,n)$的电容器，按照相同电压方向**串联**，得到一个电容为$C _\mathrm{eq}$，初始电压为$u _0$的等效电容：
$$u _0=\sum _{k=1}^nu _{k0}\qquad \cfrac{1}{C _\mathrm{eq}}=\sum _{k=1}^n\cfrac{1}{C _k}\tag{7.13}$$

&emsp;&emsp;如果等效电容两端的电压变为$u'$，那么电压的变化量$\Delta u=u'-u _0$以电容的倒数为权重，分给这$n$个电容：
$$u _k'=u _{k0}+\Delta u _k=u _{k0}+(u'-u _0)\cfrac{C _k^{-1}}{\sum\limits _{l=1}^nC _l^{-1}}\tag{7.14}$$

**2.电容并联**\
&emsp;&emsp;$n$个电容为$C _k$，初始电压为$u _{k0}(k=1,2,\cdots,n)$的电容器，按照相同电压方向**并联**，得到一个电容为$C _{eq}$，初始电压为$u _0$的等效电容：
$$C _\mathrm{eq}=\sum _{k=1}^nC _k\tag{7.15}$$

&emsp;&emsp;如果各个电容的初始电压相等，那么它们就等于$u _{k0}$.如果不是全部相等，在并联的一瞬间会产生冲击电流，使得电压统一为$u _0$：
$$u _0=\cfrac{\sum\limits _{k=1}^nC _ku _{k0}}{\sum\limits _{k=1}^nC _k}\tag{7.16}$$
<blockquote>
&emsp;&emsp;形式上，$u _0$是$u _{k0}$以$C _k$为权的加权平均值，也即各个电容的初始电压以电容为权的加权平均值。冲击电流带来的是电容极板上电荷量$q$的瞬间重新分配,冲击前后电容极板上电荷守恒$\sum q=\sum Cu=\mathrm{Const}$.
</blockquote>

**三、电感**\
&emsp;&emsp;储存磁场能量的元件，$\varPsi=Li$.其$u-i$关系：
$$\begin{aligned}&u=\cfrac{\mathrm d\varPsi}{\mathrm dt}=\cfrac{\mathrm d(Li)}{\mathrm dt}=L\cfrac{\mathrm di}{\mathrm dt}\\\\
&i(t)=i(0 _-)+\cfrac{1}{L}\int _{0 _-}^tu\mathrm dt\end{aligned}\tag{7.17}$$
<blockquote>
&emsp;&emsp;法拉第电磁感应定律指出，$\mathscr E _i=-\cfrac{\mathrm d\varPsi}{\mathrm dt}$.但是式$(7.17)$中没有负号。这是因为，感应电动势$\mathscr E _i$的方向是从低电势指向高电势；而电路理论中$u$的方向是压降的方向，从高电势指向低电势。
</blockquote>

**1.电感并联**\
&emsp;&emsp;$n$个电感为$L _k$，初始电流为$i _{k0}(k=1,2,\cdots,n)$的电感器，按照相同电流方向**并联**得到一个电感位$L _\mathrm{eq}$，初始电流为$i _0$的等效电感：
$$i _0=\sum _{k=1}^ni _{k0}\qquad \cfrac{1}{L _\mathrm{eq}}=\sum _{k=1}^n\cfrac{1}{L _k}\tag{7.18}$$

&emsp;&emsp;如果通过等效电感的电流变为$i'$，那么电流的变化量$\Delta i=i'-i _0$以电感的倒数为权重，分给这$n$个电感：
$$i _k'=i _{k0}+\Delta i _k=i _{k0}+(i'-i _0)\cfrac{L _k^{-1}}{\sum\limits _{l=1}^nL _l^{-1}}\tag{7.19}$$

**2.电感串联**\
&emsp;&emsp;$n$个电感位$C _k$，初始电压为$i _{k0}(k=1,2,\cdots,n)$的电感器，按照相同电流方向**串联**，得到一个电感为$L _{eq}$，初始电流为$i _0$的等效电感：
$$L _\mathrm{eq}=\sum _{k=1}^nL _k\tag{7.20}$$

&emsp;&emsp;如果各个电感的初始电流相等，那它们就等于$i _0$.如果不是全部相等，在串联的一瞬间会产生冲击电压，使得电流统一为$i _0$：
$$i _0=\cfrac{\sum\limits _{k=1}^nL _ki _{k0}}{\sum\limits _{k=1}^nL _k}\tag{7.21}$$
<blockquote>
&emsp;&emsp;形式上，$i _0$是$i _{k0}$以$L _k$为权的加权平均值，也即各个电感的初始电流以电感为权的加权平均值。冲击电压带来的是电感内磁链$\varPsi$的瞬间重新分配，冲击前后电感中磁链守恒$\sum \varPsi=\sum Li=\mathrm{Const}$.<br>
&emsp;&emsp;相比于电荷守恒，磁链守恒可能没有那么直观，理解起来稍微困难一些。
</blockquote>

**五、动态电路暂态分析**\
&emsp;&emsp;列写微分方程，根据初值条件得到唯一解。微分方程的阶数为电路中**独立储能元件**个数。
<blockquote>
&emsp;&emsp;两个储能元件不独立，一般具备以下条件：<br>
&emsp;&emsp;1.元件类型相同。比如说都是电容，或者都是电感。<br>
&emsp;&emsp;2.两个元件串联或者并联。<br>
&emsp;&emsp;其实也就是两个元件可以“合成”一个等效元件。如果电感$L _1$与一个电阻$R$先串联后，再与$L _2$并联，那也是两个独立储能元件。如果实在判断不了，就直接列微分方程；每个元件的微分方程阶数未必相等，但阶数最高的那个等于电路的阶数。<br>
&emsp;&emsp;两个元件不独立，也有可能是其它因素对它们造成了约束。
</blockquote>

&emsp;&emsp;初值条件是$t=0 _+$时各个量的值。一般情况是连续换路，对于电容有$u(0 _+)=u(0 _-)$，对于电感有$i (0 _+)=i (0 _-)$，根据电路定理求出电路在$t=0 _+$时的各电压、电流值。如果求微分值，一般需要进行转换：\
&emsp;&emsp;1.电容$C$的$\cfrac{\mathrm du _C}{\mathrm dt}$，根据$i=C\cfrac{\mathrm du}{\mathrm dt}$转化为求$i _C$.\
&emsp;&emsp;2.电感$L$的$\cfrac{\mathrm di _L}{\mathrm dt}$，根据$u=L\cfrac{\mathrm di}{\mathrm dt}$转化为求$u _L$.\
&emsp;&emsp;3.电容$C$的$\cfrac{\mathrm di _C}{\mathrm dt}$，根据KCL，用某个电感的$i _L$表示$i _C$，转化为2求解。\
&emsp;&emsp;4.电感$L$的$\cfrac{\mathrm du _L}{\mathrm dt}$，根据KVL，用某个电容的$u _C$表示$u _L$，转化为1求解。\
&emsp;&emsp;5.二阶及以上微分，一层层来。

## $Chapter8$&emsp;一阶电路暂态分析

$\boxed{\mathrm{To\ Be\ Continued}}$