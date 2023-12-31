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
        border-left: 5px solid lightblue;
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

# 大学物理（下）笔记
## 部分常用物理常量的计算值

<table align="center">
    <tr>
        <th>物理量</th>
        <th>计算用值</th>
        <th>物理量</th>
        <th>计算用值</th>
    </tr>
     <tr>
        <td>真空中的光速</td>
        <td>$c=3.0\times 10^8\mathrm{\ m\cdot s^{-1}}$</td>
        <td>引力常量</td>
        <td>$G=6.67\times10^{-11}\mathrm{\ m^3\cdot kg^{-1}\cdot s^{-2}}$</td>
    </tr>
    <tr>
        <td>重力加速度</td>
        <td>$g=9.8\mathrm{\ m\cdot s^{-2}}$</td>
        <td>元电荷</td>
        <td>$e=1.6\times10^{-19}\mathrm{\ C}$</td>
    </tr>
    <tr>
        <td>电子静质量</td>
        <td>$m_\mathrm{e}=9.91\times 10^{-31}\mathrm{\ kg}$</td>
        <td>电子荷质比</td>
        <td>$-e/m_\mathrm{e}=-1.76\times10^{11}\mathrm{\ C\cdot kg^{-1}}$</td>
    </tr>
    <tr>
        <td>电子经典半径</td>
        <td>$r_\mathrm{e}=2.82\times 10^{-15}\mathrm{\ m}$</td>
        <td>质子静质量</td>
        <td>$m_\mathrm{p}=1.673\times10^{-27}\mathrm{\ kg}$</td>
    </tr>
    <tr>
        <td>中子静质量</td>
        <td>$m_\mathrm{n}=1.675\times 10^{-27}\mathrm{\ kg}$</td>
        <td>真空介电常数</td>
        <td>$\varepsilon_0=8.85\times10^{-12}\mathrm{\ F\cdot m^{-1}}$</td>
    </tr>
    <tr>
        <td>真空磁导率</td>
        <td>$\mu_0=4\pi\times 10^{-7}\mathrm{\ N\cdot A^{-2}}$</td>
        <td>阿伏伽德罗常数</td>
        <td>$N_\mathrm{A}=6.02\times10^{23}\mathrm{\ mol^{-1}}$</td>
    </tr>
    <tr>
        <td>摩尔气体常量</td>
        <td>$R=8.31\mathrm{\ J\cdot mol^{-1}\cdot K^{-1}}$</td>
        <td>玻尔兹曼常量</td>
        <td>$k=1.38\times10^{-23}\mathrm{\ J\cdot K^{-1}}$</td>
    </tr>
    <tr>
        <td>理想气体摩尔体积（标准状况）</td>
        <td>$V_\mathrm{m}=22.4\times 10^{-3}\mathrm{\ m^3\cdot mol^{-1}}$</td>
        <td>标准大气压</td>
        <td>$1\mathrm{\ atm}=1.01\times10^5\mathrm{\ Pa}$</td>
    </tr>
    <tr>
        <td>普朗克常量</td>
        <td>$h=6.63\times 10^{-34}\mathrm{\ J\cdot s}$</td>
        <td>康普顿波长</td>
        <td>$\lambda=2.43\times10^{-12}\mathrm{\ m}$</td>
    </tr>
</table>

<bw>wr按：\
这一部笔记，主要记录学习过程中的一些想法，以便后续查看时能回忆起当时的理解，并加深印象。</bw>

## $Chapter9$&emsp;恒定磁场
**一、毕奥-萨伐尔定律**\
&emsp;&emsp;磁场和电场在很多性质上是有共性的，很多时候可以拿它们两个相互对比。\
&emsp;&emsp;恒定磁场最基础的公式是毕奥-萨伐尔定律：
$$\textrm{d}\boldsymbol B=\cfrac{\mu_0}{4\pi}\cfrac{I\textrm{d}\boldsymbol l\times\boldsymbol e_r}{r^2}\tag{9.1}$$

&emsp;&emsp;<st>$\mu_0=4\pi\times10^{-7}\mathrm{T\cdot m/A}$</st>，这个常数可以记忆一下。基于此，我们能够计算到电流为$I$的长直载流导线在距离其为$r$处激发的磁场为
$$B=\cfrac{\mu_0I}{4\pi r}(\cos \varphi_1-\cos\varphi_2)\tag{9.2}$$

&emsp;&emsp;其中$\varphi_1,\varphi_2$是该点与导线两端的连线和导线所成的夹角。无限长直载流导线激发的磁场，其实就是$(9.1)$式在$\varphi_1=0,\varphi_2=\pi$时的情况：
$$B=\cfrac{\mu_0I}{2\pi r}\tag{9.3}$$

&emsp;&emsp;通过毕奥-萨伐尔定律，还能够算得半径为$R$的圆环电流$I$在其轴线上坐标为$x$的点处产生的磁场大小
$$B=\cfrac{\mu_0I}{2(R^2+x^2)^{3/2}}\tag{9.4}$$

&emsp;&emsp;这个能够自行推导，感觉就足够了，倒也不是特别好记。\
**二、磁偶极子**\
&emsp;&emsp;磁偶极子可以认为是一个平面环形电流，只有当这个环的线度在问题中可以忽略时，才能把它作为磁偶极子处理。\
&emsp;&emsp;这很容易让我们联想到电偶极子。两者之间的对比如下：
<table align="center">
    <tr>
        <th></th>
        <th>电偶极子</th>
        <th>磁偶极子</th>
    </tr>
    <tr>
        <th>定义式</th>
        <td>$$\boldsymbol{p}=q\boldsymbol{l}=ql\boldsymbol{e}_\mathrm{r}$$</td>
        <td>$$\boldsymbol{m}=I\boldsymbol{S}=IS\boldsymbol{e}_\mathrm{n}$$</td>
    </tr>
    <tr>
        <th>激发的电磁场</th>
        <td>中垂面上的电场<br>$$\boldsymbol{E}=-\cfrac{\boldsymbol{p}}{4\pi\varepsilon_0r^3}$$</td>
        <td>中垂线上的磁场<br>$$\boldsymbol{B}=\cfrac{\mu_0\boldsymbol{m}}{2\pi r^3}$$</td>
    </tr>
    <tr>
        <th>在电磁场中受到力矩</th>
        <td>在电场$\boldsymbol{E}$中<br>$$\boldsymbol{M}=\boldsymbol{p}\times\boldsymbol{E}$$</td>
        <td>在磁场$\boldsymbol{B}$中<br>$$\boldsymbol{M}=\boldsymbol{m}\times\boldsymbol{B}$$</td>
    </tr>
</table>

&emsp;&emsp;电偶极子在电场中受到力矩作用，达到稳定平衡状态时电矩与电场方向相同，能够解释有极分子的取向极化；磁偶极子在磁场中受到力矩作用，达到稳定平衡状态时磁矩与磁场方向相同，能够解释顺磁质的磁化。

**三、磁场的高斯定理与安培环路定理**\
&emsp;&emsp;磁场的高斯定理
$$\oint_S \boldsymbol{B\ \cdot}\mathrm{d}\boldsymbol{S}=0\tag{9.5}$$

&emsp;&emsp;说明磁场是<st>无源场</st>，这在本质上是因为不存在所谓“磁单极子”或者叫做“磁荷”的东西。而静电场是由“电荷”所激发的，所以静电场是有源场：
$$\oint_S \boldsymbol{E\ \cdot}\mathrm{d}\boldsymbol{S}=\cfrac{q}{\varepsilon_0}\tag{9.6}$$

&emsp;&emsp;在恒定磁场中，安培环路定理也经常被应用：
$$\oint_L\boldsymbol{B\ \cdot}\mathrm{d}\boldsymbol{l}=\mu_0I\tag{9.7}$$

**四、洛伦兹力与安培力**\
&emsp;&emsp;主要想谈谈其矢量式中各个量摆放顺序的问题。\
&emsp;&emsp;洛伦兹力
$$\boldsymbol{F}=q\boldsymbol{v\ \times B}\tag{9.8}$$
&emsp;&emsp;安培力
$$\boldsymbol{F}=I\boldsymbol{L\ \times B}\tag{9.9}$$
&emsp;&emsp;观察$(9.8)$式和$(9.9)$式，发现它们都能写成“电量·**运动量×场量**”的形式。其中**粗体**为矢量。

**五、磁化强度$\boldsymbol{M}$与磁场强度$\boldsymbol{H}$**\
&emsp;&emsp;我们通常习惯于用磁感应强度$\boldsymbol{B}$来描述磁场，用电场强度$\boldsymbol{E}$来描述电场。当电磁场中存在介质的时候，这种描述方法是不好的。\
&emsp;&emsp;磁化强度$\boldsymbol{M}$与磁场强度$\boldsymbol{H}$是为了研究磁介质的磁化，在磁感应强度$\boldsymbol{B}$的基础上上又增加的两个磁场量。在研究电介质的极化时也曾引入电极化强度$\boldsymbol{P}$和电位移矢量$\boldsymbol{D}$.下面对这些量进行对比分析。\
**1.磁化强度$\boldsymbol{M}$与电极化强度$\boldsymbol{P}$**\
&emsp;&emsp;磁化强度$\boldsymbol{M}$的定义与电极化强度$\boldsymbol{P}$的定义式非常相似：

$$\boldsymbol{M}=\cfrac{\sum\limits_{i=1}^n\boldsymbol{m}_ i }{\Delta V}\ \ \ \ \ \ \boldsymbol{P}=\cfrac{\sum\limits _{i=1}^n\boldsymbol{p}_i }{\Delta V}\tag{9.10}$$

&emsp;&emsp;磁化强度$\boldsymbol{M}$描述磁介质受到磁化的情况，而磁介质磁化时伴有磁化电流$I'$.所以这两者还是有联系的：\
$$\oint_ L\boldsymbol{M\ \cdot}\mathrm{d}\boldsymbol l=\sum I'\tag{9.11}$$

&emsp;&emsp;其中，$\sum I'$表示穿过环路$L$的所有磁化电流之和。\
&emsp;&emsp;类似地，电极化强度$\boldsymbol{P}$描述电介质在外电场中产生的极化情况，而电介质极化时会产生束缚电荷$q'$.这两者有如下的联系：
$$\oint_ S\boldsymbol{P\ \cdot}\mathrm{d}\boldsymbol S=-\sum q'\tag{9.12}$$

&emsp;&emsp;其中，$\sum q'$表示高斯面$S$内所有的束缚电荷之和。式$(9.11)$与$(9.12)$在形式上非常相似，需要注意的是式$(9.12)$<st>多出了一个负号</st>。\
**2.磁场强度$\boldsymbol H$和电位移矢量$\boldsymbol D$**\
&emsp;&emsp;磁场强度$\boldsymbol{H}$，给我带来的直观感受是，它是磁感应强度$\boldsymbol{B}$在磁介质存在情况下，为了保证某种连续性而定义的表征磁场的量。这是它的定义式
$$\boldsymbol{H}=\cfrac{\boldsymbol B}{\mu_r\mu_0}=\cfrac{\boldsymbol B}{\mu}\tag{9.13}$$

&emsp;&emsp;可以看到，连接磁场强度$\boldsymbol H$与磁感应强度$\boldsymbol B$的桥梁是磁导率$\mu$.\
&emsp;&emsp;在没有磁介质的情况下，磁感应强度$\boldsymbol{B}$在空间内是连续的，因此磁感线也是连续的。但是，在有磁介质的情况下，磁感应强度矢量$\boldsymbol{B}$将会失去它的空间连续性，也就是说，$\boldsymbol B$会<st>在不同磁介质的交界处发生跳变</st>。这一跳变是不同的磁导率造成的。不过这个时候$\boldsymbol H$却具有空间连续性，因此用它描述磁场是比较理想的。\
&emsp;&emsp;当然，对于电场强度$\boldsymbol E$和电极化强度$\boldsymbol D$来说，上面的性质也是成立的。在空间中存在电介质的情况下，$\boldsymbol E$的空间连续性将失去，$\boldsymbol D$的空间连续性将被保留。教材中对于$\boldsymbol D$的引入是下式：
$$\boldsymbol D=\varepsilon _0\boldsymbol E+\boldsymbol P\tag{9.14}$$

&emsp;&emsp;我认为这样的引入很不妥当。可以给出类似式$(9.13)$的定义：
$$\boldsymbol D=\varepsilon_ r\varepsilon_ 0\boldsymbol E=\varepsilon \boldsymbol E\tag{9.15}$$

&emsp;&emsp;从式$(9.15)$能够看到，电位移矢量$\boldsymbol D$与电场强度$\boldsymbol E$之间是通过介电常数$\varepsilon$联系起来的。\
&emsp;&emsp;此外，我们发现磁场强度$\boldsymbol H$与磁化强度$\boldsymbol M$具有相同的量纲，实际上也有积分式
$$\oint_ L\boldsymbol{H\ \cdot}\mathrm{d}\boldsymbol l=\sum I\tag{9.16}$$

&emsp;&emsp;其中，$\sum I$表示穿过环路$L$的所有传导电流之和。我们大致能够得出这样的结论：$\boldsymbol H$描述的是空间某点本来的磁场，$\boldsymbol M$描述这一点由磁介质产生的磁场，$\boldsymbol B$是由前面两个磁场叠加得到的、描述该点实际磁场情况的物理量。这正如式$(9.17)$所描述的那样。
$$\oint_ L(\boldsymbol H+\boldsymbol M)\ \boldsymbol\cdot\mathrm{d}\boldsymbol l=\sum(I+I')=\oint _L \cfrac{\boldsymbol B}{\mu_0}\boldsymbol\cdot\mathrm{d}\boldsymbol l\tag{9.17}$$

&emsp;&emsp;类似地，在存在电介质的电场中，我们也有式$(9.18)$和式$(9.19)$.
$$\oint_ S\boldsymbol{D\ \cdot}\mathrm{d}\boldsymbol S=\sum q\tag{9.18}$$

$$\oint_ S(\boldsymbol D-\boldsymbol P)\ \boldsymbol\cdot\mathrm{d}\boldsymbol S=\sum(q+q')=\oint _S \varepsilon_0\boldsymbol E\boldsymbol\cdot\mathrm{d}\boldsymbol l\tag{9.19}$$

&emsp;&emsp;式$(9.18)$中，$\sum q$表示高斯面$S$内所有的自由电荷之和。\
**六、磁化电流面密度**\
&emsp;&emsp;首先应指出，电流面密度<st>不是</st>电流密度。通常意义上的电流$I$单位是$\mathrm{A}$，流过一根直线，沿着电流垂面方向截得一个点。电流流过一个平面时，沿着电流垂面方向截得一条直线，因此用电流面密度$i$描述，单位$\mathrm{A/m}$.电流流过一个立体时，沿电流垂面方向截得一个平面，因此用电流密度$j$描述，单位$\mathrm{A/m^2}$.\
&emsp;&emsp;磁化电流是上面的第二种，用磁化电流面密度$i_\mathrm{m}$描述。一般要求$i_\mathrm{m}$有两种思路，第一种是根据定义：
$$i_\mathrm{m}=\cfrac{\mathrm{d}I}{\mathrm{d}L}=\cfrac{I}{L}\tag{9.20}$$

&emsp;&emsp;其中$i_\mathrm{m}=\cfrac{I}{L}$只适合于电流沿$L$均匀分布的情况。如果题目中给出了，或者可以求得磁化强度$\boldsymbol M$，也可以采用第二种求法：
$$\boldsymbol i _\mathrm{m}=\boldsymbol{M\ \times e} _\mathrm{n}\tag{9.21}$$

&emsp;&emsp;其中$\boldsymbol e_\mathrm{n}$是磁介质表面法向单位矢量。此时磁化电流面密度的大小$i_\mathrm{m}=M$.

## $Chapter10$&emsp;电磁感应

$\boxed{ToBeContinued.}$
