# `A` 数论の重逢

时间限制：1000ms  内存限制：65536kb

通过率：/ `(%) `  正确率：/ `(%)`

## 题目描述

“今有物不知其数，三三数之剩二，五五数之剩三，七七数之剩二。问物几何？”

用通俗的话来说，题目的意思就是

有一些物品，不知道有多少个，只知道将它们三个三个地数，会剩下2个；

五个五个地数，会剩下3个；七个七个地数，也会剩下2个。

这些物品的数量至少是多少个？

那么改编下x ≡ p(mod 25)； x ≡ e(mod 28)； x ≡ i(mod 33)，x是多少呢？

≡为同余符号

## 输入

多组输入数据，每组数据一行，为p,e,i的值

## 输出

对于每组数据，输出一行，为满足条件的x的最小非负值。

## 输入样例

```
1 1 1
```

## 输出样例

```
1
```

## 提示

中国剩余定理

## 思路

数论的中国剩余定理模板

虽然数论并非本课程的大头，但是依旧是出现在《算法导论》上的内容，不容小觑啊

顺便，当所有的除数无法保证两两互质的时候，需要使用**扩展剩余中国定理(EXCRT)**

# `B` 大魔法师

时间限制：1000ms  内存限制：65536kb

通过率：/ `(%) `  正确率：/ `(%)`

## 题目描述

传说中有位方圆一厘米之内鼎鼎有名的大魔法师，能把好多种不同字符串施加魔法拼接在一起，拼成一个长度不大于k的大字符串——不过这个大魔法师拼接字符串的时候，**对于每一种字符串可以拿无数多个**。

大魔法师毕竟是大魔法师，他总是会让拼接到的字符串中，在长度不大于k的情况下，a, e, i, o, u 和 A, E, I, O, U 十种字母的总个数最多。

那么，给定n种长度不大于1000的**只包含大小写字母**的字符串，以及大字符串的最大长度k，求大魔法师拼接得到的大字符串中a, e, i, o, u 和 A, E, I, O, U 十种字母的最大个数。

## 输入

输入包含多组测试数据，以EOF结束。

每组数据第一行为2个数n与k，分别代表给定的字符串种类数目和大字符串的最大长度。 **1 <= n <= 1000，1 <= k <= 1000**

接下来n行，每行一个长度不大于1001的字符串，保证字符串只包含大小写字母。

## 输出

对于每组数据，输出一行，所求最大个数。

## 输入样例

```
3 10
abcdefg
ACG
PenPineappleApplePen
2 10
AC
WA
```

## 输出样例

```
3
5
```

## 思路

费用为字符串长度，价值为元音字母的个数的完全背包

# `C` Magry的微信鼓励金

时间限制：1500ms  内存限制：204800kb

通过率：/ `(%) `  正确率：/ `(%)`

## 题目描述

微信支付推出了鼓励金活动，在周日～周四这五天随机发放鼓励金，然后可以在周五、周六两天将这笔鼓励金花出去。另外，如果在周四获得鼓励金的话，这一周收到的鼓励金总额将翻倍。

例如：`Magry`周日、一、二、三、四分别收到1元、1元、1元、1元、1元，那么这一周`Magry`收到的鼓励金总额为10元。

假定鼓励金发放的策略是这样的：周日发放的鼓励金从一个由n个数组成的集合里取一个，周一发放的鼓励金从另一个由n个数组成的集合里取一个……以此类推。（这里的n都是相同的）

另外，同样假定`Magry`周日到周四这五天**每天都拿到了鼓励金**。

请问，`Magry`在这五天可能拿到的鼓励金总额的所有情况当中，有没有可能存在一个出现的概率**大于50%**的数额？

## 输入

输入包含多组测试数据（不超过10组），以**EOF**结束。

每组数据第一行为一个正整数n，表示五个数组的长度n。保证**1<=n<=30**

接下来5行，每行n个正整数，**各行**分别表示周日、一、二、三、四这五天的鼓励金数额可能在这n个正整数中的一个。对于每个正整数x，保证1≤x≤231−11≤x≤231−1

## 输出

对于每组数据，输出一行，这五天内`Magry`可能拿到的鼓励金总额所有情况中出现概率**大于50%**的数额。

当然，上述数额可能不存在，若不存在输出`None`

## 输入样例

```
2
1 2
3 4
5 6
7 8
10 9
2
1 1
1 1
1 1
1 1
1 1
2
1 1
1 1
1 1
1 1
1 2
```

## 输出样例

```
None
10
None
```

## 样例解释

在样例第一组数据中，微信共有32种选择发放鼓励金的策略（5个数组中每个数组选一个数相加），`Magry`可能得到的所有32个总额如下：（为方便阅读，下面展示的总额数组已从小到大排好序，并按每8个数一行排列）

```
50 52 52 52 52 52 54 54
54 54 54 54 54 54 54 54
56 56 56 56 56 56 56 56
56 56 58 58 58 58 58 60
//注意这是一个数组而不是四个数组呦喂 
```

这个由32个数构成的数组中不存在一个数额出现的概率大于50%，因此输出`None`

其余同理可得。

## 提示

`Magry`拿到的鼓励金数目应该在long long范围内。

提交本OJ的代码64位整型输出请使用`%lld`，或使用流输出语句`cout`

## 思路

众数选取问题，不借助任何其他STL记录的O(n)减治算法(对于本题而言就是O(n^5))

本算法在邓俊辉《数据结构》第12章有所介绍

注:按照本算法第一次遍历求得的“众数”显然不一定就是频率超过50%的数，还需要再遍历一次数组验证一下

# `D` 怠惰的王木木Ⅲ

时间限制：1000ms  内存限制：65536kb

通过率：/ `(%) `  正确率：/ `(%)`

## 题目描述

伟大的王木木的墓志铭上是这么写这的

——王木木，一个聪明、高尚的人，死于懒惰和deadline

王木木是一个领土意识很强的人，他想在自己的坟墓旁边圈上一块栅栏，但是又不想花费太多力气，所以他决定在坟墓的一个固定的小的距离上立上栅栏，那么他至少要围多长的栅栏呢？

## 输入

多组数据输入。

每组数据第一行为两个正整数，分别为坟墓的拐点数量N和固定的距离D （0<N<100,0<D<10000）

接下来N行，每行一个坐标，表示拐点的坐标，坐标顺序按顺时针给出。

## 输出

对于每组数据，输出一行，为最小的栅栏的周长的值，保留整数。

## 输入样例

```
9 100
200 400
300 400
300 300
400 300
400 400
500 400
500 200
350 200
200 200
```

## 输出样例

```
1628
```

## 样例解释

![img](http://poj.org/images/1113/1113_1.gif?_=2445633)

## 思路

不难想到，这题的答案就是一个凸包的周长+一个半径为r的圆的周长

四舍五入别忘了

# `E` Magry再度出山

时间限制：500ms  内存限制：65536kb

通过率：/ `(%) `  正确率：/ `(%)`

## 题目描述

相信很多人认识`Magry`都是冠上了“算法助教”的头衔，然而他大一大二的时候却没有人问过他和编程方面有关的任何问题，而是经常使用一个叫做`Adobe Photoshop`的软件来制作大大小小各种各样活动的海报图片，从沙河那边办的一系列迎新晚会联谊晚会，到2015“我耀新色彩”新年晚会，再到你们2015级刚入学时候的系服门贴等等装备，还有去年的北航校赛，一系列大小社团招新大小活动等等等等——并且他出海报的效率很高，最快的时候30min就能出一份。就这么，到了大三，他决定退隐，转而在学习方面下更多工夫，那些海报活学弟学妹们足以胜任。

然而，毕竟影响力在软院实在有些大，`Magry`最近收到了一份做海报的任务，并且要求的DDL很紧。虽然`Magry`很忙，然而`Magry`表示，时间很急很关键，即使再忙也会出山。于是他就接了这个活。

现在，`Magry`开始动手做海报啦！首先，他点开一张素材图片，发现这张图上，除了一大片白色，以及一系列疏疏落落的点，然后就啥都没有了。

**HOW UGLY IT IS!!!**

然而`Magry`还是想从中得到什么东西。

已知：`Magry`把这张素材图以左下角为原点，从左向右为x轴正方向，自下向上为y轴正方向建立平面直角坐标系，这样一来各个点都有其坐标表示。

那么，`Magry`想知道的是这些点中，任意地选取某两个点，取两点间距离的平方，求这一系列点当中任取两点的距离平方的最小值和最大值。

## 输入

输入只包含一组测试数据。

第一行为点的个数n。保证n为整数且**2 ≤ n ≤ 30,000**

接下来n行，每行2个数 x, y, 分别为第 i 个点的 x 坐标和 y 坐标。保证 n 个点的坐标都不同，x与y均为整数且0≤x,y≤1090≤x,y≤109

## 输出

输出一行，两个数，以一个空格分隔，所求最小值和最大值。

## 输入样例

```
3
0 0
0 1
1 0
```

## 输出样例

```
1 2
```

## 提示

最后得出的答案应该在long long范围内。

**scanf & printf are recommended**

提交本OJ的代码64位整型输出请使用`%lld`。

## 思路

最近点对和最远点对，复杂度均为O(nlogn)，抄板子即可

# `F` 老哥，稳！

时间限制：500ms  内存限制：65536kb

通过率：/ `(%) `  正确率：/ `(%)`

## 题目描述

```
难题，慎入
```

稳。不必多说，厉害的意思。

那什么形状最稳呢？（一个生硬又突兀的问题）

恩，三角形最稳啦！

## 输入

第一个数为数据组数T(T≤100)

接下来T组数据，每组数据第一行为一个正整数N(3≤N≤10000)。

接下来一行为N个正整数a[i]。 (1≤a[i]≤100000)

## 输出

对于每组数据，输出一行，为从这N个数中，任意抽取3个数能组成三角形的概率（保留六位小数）

## 输入样例

```
1
4
1 3 3 4
```

## 输出样例

```
0.500000
```

## 思路

在看到了每个整数都是有上限的时候，应该立刻想到**这是一个必须用O(nlogn)的FFT解决的问题**

将所有的边的长度当做多项式的次幂数，进行多项式乘法，即可以得到一种长度的加和有多少种取法

显然由于取数的无序性以及不能重复取，我们要先减去两者相同的组合，再各自除以2

接下来为了方便记录，我们对所有长度的取法进行前缀和处理

对于每一根棍，我们需要这么考虑

取走另外两棍之和大于他，然后去重，包括

- **其中一个比这根棍序号大，另一根比这根序号小的情况**

- **其中一根取的就是他自己，另一根随便取**
- **取走两根序号都比自己大**

然后由于计算的是**概率**，所以上述合法的总数还需要除以总数C(n,3)才是最终答案。

而为了方便记录，我们还可以对所有长度的取法进行前缀和处理，然后考虑**计算补集**。

对于每一根棍，我们需要这么考虑所有组成不大于每根木棍的方案依次加和，不难得到这种做法就不需要去重。然后用C(n, 3)减去上述即可。
