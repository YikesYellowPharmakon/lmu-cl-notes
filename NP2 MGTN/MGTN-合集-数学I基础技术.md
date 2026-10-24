# 数学 I: 面向辅修学生的基础技术

Mathematik I: Grundlegende Techniken für Nebenfachstudierende

带颜色的阅读版是同目录的 [MGTN-合集-数学I基础技术.html](MGTN-%E5%90%88%E9%9B%86-%E6%95%B0%E5%AD%A6I%E5%9F%BA%E7%A1%80%E6%8A%80%E6%9C%AF.html), 图 (11 张示意图) 只在 HTML 里, 本文件只有文字. 正文里说「图中」「左图」时, 对照 HTML 看. 下面「> 补充」是幻灯片之外的背景知识, 「以后写入」留给以后的课.

这不是写完的讲义. 现在每一节是导览: 德语定义、中文说明、需要时加一张图. 上课之后, 新的定义、证明、例题和作业写进该节的「以后写入」, 编号不再另起一套.

原文笔误: Moodle 上的课程说明把 *Linearen* 印成了 *Llnearen*. 下面按正确拼写.

Das Modul stellt die für die Statistik notwendigen Grundlagen und Techniken der Linearen Algebra und der Analysis in einer Variablen bereit. Es wird ein Überblick über die wichtigsten Verfahren, Definitionen und Anwendungen gegeben.

Im Bereich der linearen Algebra kommen zunächst lineare Abhängigkeit, Norm und Metrik sowie reelle und allgemeine Vektorräume. Danach die Matrixrechnung, dann lineare Abbildungen mit Bild, Kern und Darstellungsmatrix.

这门课给统计准备两套工具: 线性代数, 和一元分析. 现在先看地图, 后面的课再把每个定义写完整.

线性代数的顺序是: 线性无关, 范数和距离, 实数上的向量空间, 更一般的向量空间, 矩阵, 然后才是线性映射的像、核、表示矩阵.

Im Bereich der Analysis kommen zunächst Folgen und Reihen, danach Stetigkeit und Differenzierbarkeit reeller Funktionen, und schließlich die Kurvendiskussion: lokale und globale Extrema, notwendige und hinreichende Bedingungen.

Vorangestellt ist ein Teil über Mengenlehre und Abbildungen: Injektivität, Surjektivität und Bijektivität. Lineare Gleichungssysteme und die Analyse von Funktionen in mehreren Variablen gehören ins zweite Semester.

一元分析的顺序是: 数列, 级数, 实函数的连续和可导, 最后用导数讨论曲线. 极值要分开看: 局部的、全局的、必要条件、充分条件. 可导也可以理解成: 函数在一点附近能用一条直线逼近.

这两块之前, 先学集合、命题逻辑和映射, 尤其是单射、满射、双射. 练习的目标是自己读一道抽象的数学题, 并把它拆开.

线性方程组, 以及多元函数的分析, 放在第二学期. 下面矩阵一节里先记下方程组的基本写法, 多元函数还没有展开.

## 0 · 集合、命题逻辑与映射 (Mengenlehre und Abbildungen)

后面的定义都用这套语法.

### 0.1 集合 (Mengen)

**Menge.** Eine Menge (bezeichnet z. B. mit M) ist eine Zusammenfassung wohlunterscheidbarer Objekte zu einem Ganzen. Die zu M gehörigen Objekte heißen Elemente von M. Ist m ein Element von M, so schreiben wir $m \in M$; sonst $m \notin M$. Dies ist der naive Mengenbegriff nach Georg Cantor.

**Teilmenge.** $A \subseteq B$ bedeutet: jedes Element von A ist auch Element von B. Insbesondere gilt $A \subseteq A$. Die **leere Menge** $\emptyset$ hat kein Element und ist Teilmenge jeder Menge.

集合 M 是把彼此分得清的对象收成一个整体. 这些对象叫元素. 这个说法是 Georg Cantor 的朴素集合概念. 写成 $\{1, 2, 3\}$.

m 属于 M, 写成 $m \in M$. m 不属于 M, 写成 $m \notin M$. 例如 $2 \in \{1, 2, 3\}$, $4 \notin \{1, 2, 3\}$.

$A \subseteq B$ 表示 A 的每一个元素都已经在 B 里. A 可以比 B 小, 也可以和 B 一样大. 所以 $A \subseteq A$ 总是成立.

空集 $\emptyset$ 里面一个元素也没有. 它是每个集合的子集: 要违反「每个元素都在 B 里」, 它得先拿出一个不在 B 里的元素, 而它拿不出来.

**Beispiele.** $M = \{\text{Apfel}, \text{Birne}, \text{Tisch}\}$. $N = \{\text{Apfel}, f\colon \mathbb{R} \to \mathbb{R}\colon x \mapsto x^{2}, 2, \pi\}$. O = Menge aller Studierender im Hörsaal. $P = \{\text{Menge aller Studierender im Hörsaal}, \mathbb{R}\} = \{O, \mathbb{R}\}$.

$\{1, \{2\}, 3\} \ne \{1, 2, 3\}$. Dagegen $\{1, 2, 3\} = \{3, 1, 2\}$. Ebenso gilt: $\{3, 1, 1+1\} = \{3, 1, 2\}$.

$\{a, a, b\}$ ist im strengen Sinne keine Menge. $\{a, b, c\}$ mit $a = b$ ist im strengen Sinne auch keine Menge. **Vereinbarung:** $\{a, a, b\} := \{a, b\}$.

元素可以是任何能分清的对象: 水果和桌子放在一起 (M) 可以, 函数、数字、π 混在一起 (N) 也可以. **集合本身也能当元素**: P 只有两个元素, 一个是集合 O (全班同学), 一个是集合 $\mathbb{R}$. P 不是「全班同学加上所有实数」. 所以某位同学 $s \in O$, 但 $s \notin P$; $O \in P$, 但 $O \not\subset P$.

$\{1, \{2\}, 3\}$ 的三个元素是 1、集合 $\{2\}$、3. $\{2\}$ 是装着 2 的盒子, 不是 2 本身: $\{2\} \in \{1, \{2\}, 3\}$, 而 $2 \notin \{1, \{2\}, 3\}$. 两个集合相等要求元素完全相同, 所以它和 $\{1, 2, 3\}$ 不相等.

写的顺序不影响集合: $\{1, 2, 3\} = \{3, 1, 2\}$. $1+1$ 只是 2 的另一种写法, 指的是同一个对象, 所以 $\{3, 1, 1+1\}$ 就是 $\{3, 1, 2\}$.

定义要求元素彼此分得清 (wohlunterscheidbar). $\{a, a, b\}$ 把 a 写了两次; $a = b$ 时的 $\{a, b, c\}$ 也是同一个对象写了两次. 严格按定义, 这不是集合. 所以**约定**: 重复写的元素只算一次, $\{a, a, b\} := \{a, b\}$. 「:=」读作「定义为」, 左边按右边理解.

**易错**: 数元素个数前先合并重复和同值的写法. $\{3, 1, 1+1\}$ 有 3 个元素, $\{1, \{2\}, 3\}$ 也是 3 个, P 是 2 个.

**Extensionale Darstellung.** Einfache Auflistung der Elemente in geschweiften Klammern. Bsp.: $\{1, 2, 3\}, \{a, b, \gamma , \delta \}$ oder $\{1, 2, 3, 4, \ldots \}$ oder $\{2, 3, \ldots \}$.

**Intensionale Darstellung.** Beschreibung der Elemente durch eine (oder mehrere) charakterisierende Eigenschaft(en). Bsp.: $\{x \mid x \text{ ist natürliche Zahl und } x \text{ ist gerade}\}$ (= {2, 4, 6, 8, …} in extensionaler Darstellung). Ebenso $M = \{ x \in \mathbb{R} \mid x^{2} < 4 \}$, gelesen „die Menge aller x in $\mathbb{R}$ mit $x^{2} < 4$“.

**Zahlenbereiche.** $\mathbb{N} = \{1, 2, 3, \ldots \}$ (manchmal mit 0), ℤ die ganzen, $\mathbb{Q}$ die rationalen, $\mathbb{R}$ die reellen Zahlen; es gilt $\mathbb{N} \subseteq \mathbb{Z} \subseteq \mathbb{Q} \subseteq \mathbb{R}$.

集合有两种写法. **Extensionale Darstellung 外延式** (列举法) 把元素一个个写在花括号里; 元素无穷多时用「…」, 前提是规律一眼看得出: $\{1, 2, 3, 4, \ldots \}$ 是全体正整数, $\{2, 3, \ldots \}$ 是从 2 起的整数. **Intensionale Darstellung 内涵式** (描述法) 写成「$\{\ \text{元素} \mid \text{要满足的性质}\ \}$」, 竖线读作「使得」. $\{x \mid x\ \text{是自然数且}\ x\ \text{是偶数}\}$ 用外延式写出来是 $\{2, 4, 6, 8, \ldots \}$. $\{ x \in \mathbb{R} \mid x^{2} < 4 \}$ 是开区间 (−2, 2), 这种集合没法一个个列出来, 只能用内涵式.

集合只关心「谁在里面」, 不关心顺序; 重复写的元素按上面的约定只算一次. 这一点和后面的有序对 (a, b)、数列 $(a_{n})$ 正好相反.

数集一层套一层: 自然数 $\subseteq$ 整数 $\subseteq$ 有理数 $\subseteq$ 实数. 德国教材里 $\mathbb{N}$ 有时含 0, 有时不含; 含 0 时常写 $\mathbb{N}_{0}$. 这份笔记里 $\mathbb{N} = \{1, 2, 3, \ldots \}$, 所以偶数的自然数是 $\{2, 4, 6, 8, \ldots \}$, 不含 0.

**Spezielle Mengen.** Die **leere Menge** ist die Menge, die kein Element enthält. Symbol: $\emptyset$, anderes Symbol: $\{ \}$.

**Bemerkung:** Es gibt nur eine leere Menge.

**Frage:** Gilt $\{\emptyset \} = \emptyset$? Antwort: Nein.

**leere Menge 空集**: 一个元素也没有的集合, 写成 $\emptyset$ 或 $\{ \}$.

**为什么只有一个**: 两个集合相等, 只看元素是否完全相同. 任取两个空集, 谁也拿不出一个「我有你没有」的元素, 所以它们相等. 于是不管用什么性质描述出来的空集 (没有最大自然数的集合、平方为负的实数的集合……) 都是同一个 $\emptyset$.

**$\{\emptyset \} \ne \emptyset$**: $\{\emptyset \}$ 是装着空集的集合, 有 1 个元素, 就是 $\emptyset$; $\emptyset$ 有 0 个元素. 元素个数都不同, 当然不相等. 好比一个空盒子和一个装着空盒子的盒子. 同样, $\emptyset \in \{\emptyset \}$ 为真, $\emptyset \in \emptyset$ 为假.

**Warum spricht man hier vom naiven Mengenbegriff?** Ein klassisches Beispiel: der Barbier von Sevilla. „Der Barbier von Sevilla rasiert *genau* diejenigen Personen, die sich *nicht* selbst rasieren.“

Jetzt sei M die Menge aller Personen, die vom Barbier rasiert werden. Frage: Ist der Barbier b ein Element von M?

Fall a) $b \in M \Rightarrow b$ wird vom Barbier rasiert $\Rightarrow b$ rasiert sich selber $\Rightarrow b \notin M$. ↯

Fall b) $b \notin M \Rightarrow b$ wird nicht vom Barbier rasiert $\Rightarrow b$ rasiert sich nicht selbst $\Rightarrow b$ wird vom Barbier rasiert $\Rightarrow b \in M$. ↯

[Ausweg: axiomatische Mengenlehre]

朴素定义允许把任何能分清的对象收成集合, 理发师的例子说明这会自相矛盾. 规则是: 理发师给**恰好**那些不给自己刮胡子的人刮胡子. 「恰好」有两层: 不自己刮的人, 他都刮; 自己刮的人, 他都不刮.

M 是被理发师刮胡子的人. 问理发师 b 自己在不在 M 里, 两种可能都走不通:

- **情况 a**: $b \in M$, 即 b 被理发师刮. 理发师就是 b, 所以 b 自己给自己刮. 按规则, 自己刮的人理发师不刮, 于是 $b \notin M$, 和假设矛盾.
- **情况 b**: $b \notin M$, 即 b 不被理发师刮, 也就是 b 不给自己刮. 按规则, 不自己刮的人理发师都刮, 于是 $b \in M$, 又矛盾.

↯ 是「矛盾」的记号. 两种情况都矛盾, 说明这样的 M (连同这样一位理发师) 根本不能存在. 出路是公理化集合论: 只允许按明确的公理造集合. 这门课用到的集合都安全, 所以继续用朴素定义, 这也是它叫 naiver Mengenbegriff 的原因. 推理里每一步「$\Rightarrow$」的含义, 见 0.2 的蕴含.

> **补充 · 罗素悖论**
>
> 理发师是罗素悖论的通俗版. Russell (1901) 考虑「所有不包含自身的集合组成的集合」$R = \{ X \mid X \notin X \}$: 若 $R \in R$, 按定义 $R \notin R$; 若 $R \notin R$, 它满足条件, 应当 $R \in R$. 结构和上面两种情况一模一样, 只是把「理发师」换成 R, 把「给自己刮胡子」换成「包含自身」. 公理化集合论 (如 ZF) 规定只能从一个已有的集合里按性质挑元素, 写成 $\{ x \in A \mid \ldots \}$, 不能凭空收集「所有满足某性质的东西」, R 就造不出来了. 上面 $\{ x \in \mathbb{R} \mid x^{2} < 4 \}$ 正是这种安全的写法.

#### 以后写入

- 幂集
- 练习里关于 $\in$ 和 $\subseteq$ 的题

### 0.2 命题逻辑与量词 (Aussagenlogik und Quantoren)

Sei 𝒜 eine Menge von **atomaren Aussagen**, für welche wir klar entscheiden können, ob sie wahr oder falsch sind. (In Symbolen: w oder 1 für wahr bzw. f oder 0 für falsch.)

Die Elemente von 𝒜 werden mit Großbuchstaben bezeichnet (z. B. A, B, C, …). Wir definieren jetzt den Wahrheitswert von gewissen verknüpften Aussagen.

**Aussage 命题**是能判断真假的句子: 「2 是偶数」为真, 「$3 > 5$」为假. 「$x > 2$」在 x 没定下来之前不是命题. **atomar 原子**命题是不再拆开的最小命题, 用大写字母 A、B、C 表示.

集合运算、子集, 以及后面每一个定义和证明, 都要用「且」「或」「非」「推出」把命题连起来, 所以先把这几个联结词定准. 复合命题的真假只由各部分的真假决定, 所以可以用 **Wahrheitstabelle 真值表**把所有组合列出来: 两个命题各有真假两种, 共 $2 \times 2 = 4$ 行.

1) **Konjunktion** (logisches „und“, Symbol: ∧). $A \land B$ ist wahr genau dann, wenn sowohl A als auch B wahr sind.

2) **Disjunktion** (einschließendes oder, Symbol: ∨). $A \lor B$ ist genau dann falsch, wenn A und B falsch sind.

3) **Negation** (Verneinung, Symbol: ¬). $\neg A$ ist genau dann wahr, wenn A falsch ist.

4) Die **Implikation** („aus A folgt B“, Symbol: ⇒). Nur falsch, wenn A (**Prämisse**) wahr ist, aber B (**Konklusion**) falsch ist. Insbesondere ist eine Implikation schon dann wahr, wenn die Prämisse falsch ist.

**Bemerkung:** Es gibt insgesamt $16 (= 2^{4})$ logisch verschiedene Verknüpfungen von zwei Aussagen A und B. Alle 16 Verknüpfungen können durch $\land , \lor , \neg$ erzeugt werden. (Es reicht sogar $\neg$ und $\land$.)

$\vert  A \vert  B \vert  A \land B \vert  A \lor B \vert  A \Rightarrow B \vert  \neg A \vert $
|---|---|---|---|---|---|
| w | w | w | w | w | f |
| w | f | f | w | f | f |
| f | w | f | w | w | w |
| f | f | f | f | w | w |

- **Konjunktion 合取 $\land$** (「且」): 两个都真才真, 其余三行都是假.
- **Disjunktion 析取 $\lor$** (「或」): 至少一个真就真, 只有两个都假时才假. 两个都真也算真, 所以叫 einschließend (包含的或). 日常说的「要么…要么」是 ausschließendes oder (异或), 两个都真时为假, 这里不是它.
- **Negation 否定 $\neg$**: 真假互换. $\neg A$ 只看 A, 所以表里它只随 A 那一列变.
- **Implikation 蕴含 $\Rightarrow$**: 只有「前提真、结论假」这一行为假. 前提为假时, 整句自动为真. 例: 「如果下雨, 地就湿」只在「下了雨、地却不湿」时被推翻; 没下雨时, 地湿不湿都不违背这句话.

**易错**: $A \Rightarrow B$ 不说 A 是 B 的原因, 也不等于 $B \Rightarrow A$. 第三行 f、w 为真, 正说明 B 真时 A 可以是假的.

**为什么是 16 种**: 两个命题的真值组合有 4 行, 每一行的结果可以独立地取 w 或 f, 所以一共有 $2^{4} = 16$ 种不同的真值表, 也就是 16 种二元联结词. 只用 $\neg$ 和 $\land$ 就能拼出全部, 例如 $A \lor B$ 与 $\neg (\neg A \land \neg B)$ 真值相同, $A \Rightarrow B$ 与 $\neg (A \land \neg B)$ 真值相同.

**Semantische Äquivalenz.** Zwei zusammengesetzte Aussagen heißen semantisch äquivalent, wenn sie für beliebige Wahrheitsbelegungen aller vorkommenden atomaren Aussagen denselben Wahrheitswert ergeben.

**Bemerkung.** Die Aussage $A \Rightarrow B$ ist semantisch äquivalent zur Aussage $\neg (A \land \neg B)$:

$\vert  A \vert  B \vert  \neg B \vert  A \land \neg B \vert  \neg (A \land \neg B) \vert  A \Rightarrow B \vert $
|---|---|---|---|---|---|
| w | w | f | f | w | w |
| w | f | w | w | f | f |
| f | w | f | f | w | w |
| f | f | w | f | w | w |

**semantisch äquivalent 语义等价**: 两个复合命题, 不管其中的原子命题怎样取真假, 算出来的真值都一样. 「语义」指只看真值 (意思), 不看写法: 两个命题可以长得完全不同, 却永远同真同假.

**怎样判断**: 用真值表. 列出原子命题的全部真假组合 (2 个变量 4 行, 3 个变量 8 行), 一列一列往外算, 最后比较要比的两列. 上表最后两列四行完全相同, 所以 $A \Rightarrow B$ 与 $\neg (A \land \neg B)$ 语义等价. 只要有一行不同, 就不等价.

**为什么成立**: 蕴含唯一被推翻的情况是「A 真而 B 假」, 也就是 $A \land \neg B$. 说「$A \Rightarrow B$ 成立」, 等于说「A 真而 B 假这种情况不会发生」, 即 $\neg (A \land \neg B)$. 这就是上面「为什么是 16 种」里提到的用 $\neg$ 和 $\land$ 表示 $\Rightarrow$ 的办法.

5) Die **Äquivalenz** („A gilt genau dann, wenn B gilt“, Symbol: ⇔) ist definiert durch $(A \Rightarrow B) \land (B \Rightarrow A)$.

$\vert  A \vert  B \vert  A \Rightarrow B \vert  B \Rightarrow A \vert  A \Leftrightarrow B \vert $
|---|---|---|---|---|
| w | w | w | w | w |
| w | f | f | w | f |
| f | w | w | f | f |
| f | f | w | w | w |

$A \Leftrightarrow B$ ist genau dann wahr, wenn A und B den gleichen Wahrheitswert haben.

**Äquivalenz 等价** (双条件) 读作「当且仅当」. 它定义成两个方向的蕴含同时成立: A 推出 B, 并且 B 推出 A. 表里 $A \Rightarrow B$ 只在第 2 行为假, $B \Rightarrow A$ 只在第 3 行为假, 两者的「且」只剩第 1、4 行为真. 这两行正好是 A、B 同真或同假的情况.

定义和定理里写「genau dann, wenn」, 就是在说 $\Leftrightarrow$: 证明时**两个方向都要证**. 例: 要证「整数 n 是偶数, 当且仅当 $n^{2}$ 是偶数」, 就要分别证「若 n 是偶数, 则 $n^{2}$ 是偶数」和「若 $n^{2}$ 是偶数, 则 n 是偶数」.

**$\Leftrightarrow$ 与语义等价**: $A \Leftrightarrow B$ 是一个命题, 在某一行可以真、可以假. 「A 与 B 语义等价」则是说 $A \Leftrightarrow B$ 在**每一行**都为真. 下面的运算律都写成 $\Leftrightarrow$, 意思是左右两边语义等价.

**Rechenregeln für logische Verknüpfungen.** Es gelten die folgenden Äquivalenzen:

1) **Assoziativgesetze:** $A \land (B \land C) \Leftrightarrow (A \land B) \land C$; $A \lor (B \lor C) \Leftrightarrow (A \lor B) \lor C$

2) **Kommutativgesetze:** $A \land B \Leftrightarrow B \land A$; $A \lor B \Leftrightarrow B \lor A$

3) **Distributivgesetze:** $A \land (B \lor C) \Leftrightarrow (A \land B) \lor (A \land C)$; $A \lor (B \land C) \Leftrightarrow (A \lor B) \land (A \lor C)$

4) **De Morgansche Gesetze:** $\neg (A \land B) \Leftrightarrow (\neg A) \lor (\neg B)$; $\neg (A \lor B) \Leftrightarrow (\neg A) \land (\neg B)$

5) **Involution** (doppelte Verneinung): $\neg (\neg A) \Leftrightarrow A$

- **Assoziativgesetz 结合律**: 只有 $\land$ 或只有 $\lor$ 时, 括号怎么加都一样, 所以可以直接写 $A \land B \land C$. $\land$ 和 $\lor$ 混在一起时括号不能乱去 (见分配律).
- **Kommutativgesetz 交换律**: $\land$、$\lor$ 两边可以交换. 注意 $\Rightarrow$ **不能**交换: $A \Rightarrow B$ 和 $B \Rightarrow A$ 不等价 (上面等价表第 2、3 行).
- **Distributivgesetz 分配律**: 像算术的 $a \cdot (b + c) = a \cdot b + a \cdot c$ 一样, $\land$ 可以分配到 $\lor$ 上. 和算术不同的是, 反过来 $\lor$ 也可以分配到 $\land$ 上 (算术里 $a + b \cdot c$ 一般不等于 (a + b) · (a + c)).
- **De Morgansche Gesetze 德摩根律**: 否定穿进括号时, 每一项都要否定, 同时 $\land$ 和 $\lor$ **互换**. 「不是 (下雨且刮风)」=「没下雨, 或者没刮风」; 「不是 (下雨或刮风)」=「既没下雨, 也没刮风」.
- **Involution 双重否定**: 否定两次回到原来的命题.

**怎样证明**: 每一条都用真值表证: 两个变量 4 行, 三个变量 (结合律、分配律) 8 行. 例如第一条德摩根律 (两列加粗的列四行相同):

$\vert  A \vert  B \vert  A \land B \vert $ **$\neg (A \land B)$** $\vert  \neg A \vert  \neg B \vert $ **$(\neg A) \lor (\neg B)$** |
|---|---|---|---|---|---|---|
| w | w | w | **f** | f | f | **f** |
| w | f | f | **w** | f | w | **w** |
| f | w | f | **w** | w | f | **w** |
| f | f | f | **w** | w | w | **w** |

运算律也可以连着用, 不必每次都列表. 例: $\neg (A \Rightarrow B) \Leftrightarrow \neg \neg (A \land \neg B) \Leftrightarrow A \land \neg B$, 第一步用上面的「$\Rightarrow$ 与 $\neg (A \land \neg B)$ 等价」, 第二步用双重否定. 意思是: 蕴含不成立, 恰好是「A 真而 B 假」.

**Tautologie 重言式**: 不管原子命题怎样取真假都为真的命题, 例如 $A \lor \neg A$ (排中律). 上面每一条运算律, 把中间的 $\Leftrightarrow$ 看成联结词, 整个式子都是重言式; 一般地, 两个命题语义等价, 当且仅当用 $\Leftrightarrow$ 把它们连起来得到一个重言式.

**Quantoren und Familien von Aussagen.** Sei E eine Eigenschaft und M eine Menge. Für $m \in M$ bezeichne E(m) die Aussage „m besitzt die Eigenschaft E“. Mit Hilfe dieser Familie von Aussagen E(m) können wir durch Quantoren neue Aussagen generieren:

- **Allquantor** $\forall$. Die Aussage $\forall m \in M\colon E(m)$ bedeutet „alle $m \in M$ besitzen die Eigenschaft E“. Ist etwa $M = \{m_{1}, m_{2}, \ldots , m_{k}\}$, so ist die Aussage $\forall m \in M\colon E(m)$ gleichbedeutend mit $E(m_{1}) \land E(m_{2}) \land \ldots \land E(m_{k})$.
- **Existenzquantor** $\exists$: Die Aussage $\exists m \in M\colon E(m)$ bedeutet „es existiert (mindestens) ein $m \in M$ mit E(m)“. Für $M = \{m_{1}, \ldots , m_{k}\}$ ist sie äquivalent zu $E(m_{1}) \lor E(m_{2}) \lor \ldots \lor E(m_{k})$.

**Familie von Aussagen 命题族**: E(m) 本身不是一个命题, 而是给每个 m 各配一个命题. 例如 $M = \{1, 2, 3\}$, 性质 E(m) 是「$m > 2$」: E(1)、E(2) 为假, E(3) 为真. 0.2 开头说「$x > 2$」在 x 没定下来之前不是命题; 量词就是把这种带变量的说法变成一个确定真假的命题的办法.

- **Allquantor 全称量词 $\forall$** (「对所有」): 每个 m 都满足 E. M 有限时, 它就是把所有 E(m) 用 $\land$ 连起来. 上例里 $\forall m \in M\colon m > 2$ 为假 (1 不满足), $\forall m \in M\colon m > 0$ 为真.
- **Existenzquantor 存在量词 $\exists$** (「存在」): **至少**一个 m 满足 E, 不是「恰好一个」. M 有限时, 它就是把所有 E(m) 用 $\lor$ 连起来. 上例里 $\exists m \in M\colon m > 2$ 为真 (3 满足).

写法: 冒号前是「对谁」, 冒号后是「要满足什么」. $\forall m \in M\colon E(m)$ 读作「对 M 中所有 m, 都有 E(m)」.

**易错**: M 是空集时, $\forall m \in \emptyset \colon E(m)$ 总为真 (没有元素可以违反, 和「前提为假时蕴含为真」同理), $\exists m \in \emptyset \colon E(m)$ 总为假 (根本找不到元素).

**Verneinung von Quantoren.** Frage: Was bedeutet $\neg (\forall m \in M\colon E(m))$? Antwort: $\neg (\forall m \in M\colon E(m)) \Leftrightarrow \exists m \in M\colon \neg E(m)$. Analog gilt: $\neg (\exists m \in M\colon E(m)) \Leftrightarrow \forall m \in M\colon \neg E(m)$.

否定穿过量词时, **$\forall$ 和 $\exists$ 互换**, 否定号移到里面. 「不是所有 m 都有性质 E」=「至少有一个 m 没有性质 E」, 而**不是**「所有 m 都没有 E」. 例: 「不是所有学生都通过了」意思是「有学生没通过」. 「没有一个学生通过」=「所有学生都没通过」.

M 有限时, 这正是德摩根律: $\neg (E(m_{1}) \land \ldots \land E(m_{k})) \Leftrightarrow \neg E(m_{1}) \lor \ldots \lor \neg E(m_{k})$, 第二条同理. 量词的否定可以看成德摩根律推广到任意多项.

数学例子: $\neg (\forall x \in \mathbb{R}\colon x^{2} > 0) \Leftrightarrow \exists x \in \mathbb{R}\colon x^{2} \le 0$. 右边为真 $(x = 0)$, 所以「所有实数的平方都大于 0」是假的. 要否定一个 $\forall$ 命题, 举出一个反例就够了.

**Achtung:** Die Reihenfolge von Quantoren ist wichtig. Im Allgemeinen gilt *nicht*: $(\forall x \exists y\colon E_{x}(y)) \Leftrightarrow (\exists y \forall x\colon E_{x}(y))$. (Bsp.: $E_{x}(y)$: „x ist verheiratet mit y“)

用例子读两边:

- **$\forall x \exists y\colon E_{x}(y)$**: 对每个人 x, 都**有某个人** y 和他结婚, 也就是「人人都已婚」. 不同的 x 可以有不同的 y.
- **$\exists y \forall x\colon E_{x}(y)$**: **存在一个人** y, 所有人 x 都和这同一个 y 结婚.

四个人组成两对夫妻时, 前者为真, 后者为假. 所以两边不等价. 不过一个方向总是成立的: 如果有一个 y 对所有 x 都行, 那么每个 x 当然都能找到 y (就用那一个), 即 $(\exists y \forall x\colon E_{x}(y)) \Rightarrow (\forall x \exists y\colon E_{x}(y))$; 反过来一般不行.

分析里几乎每个定义都有量词. 「$\forall \varepsilon > 0 \exists N$」读作「对每一个 $\varepsilon > 0$, 都存在一个 N」: 先给 ε 再找 N, N 可以依赖 ε. 写成「$\exists N \forall \varepsilon > 0$」就要求一个 N 对所有 ε 同时成立, 意思完全变了.

**Quantoren in der intensionalen Mengendarstellung.** Diese Quantoren sind hilfreich z. B. bei einer intensionalen Mengendarstellung. Bsp.: Menge aller grünen Äpfel: $\{m \mid E(m)\}$ mit E(m): „m ist ein grüner Apfel“, also $\{m \mid E_{1}(m) \land E_{2}(m)\}$ mit $E_{1}(m)$: „m ist ein Apfel“ und $E_{2}(m)$: „m ist grün“.

Anderes Bsp., mit $\mathbb{N} = \{1, 2, 3, \ldots \}$: $M = \{x \mid x \in \mathbb{N} \land \forall n \in \mathbb{N}\colon x \le n\} = \{1\}$. Weiteres Bsp.: $M = \{x \mid x \in \mathbb{N} \land (\forall n \in \mathbb{N}\colon x \ge n)\} = \emptyset$.

0.1 的内涵式「{元素 | 性质}」里, 性质可以用联结词和量词拼起来. 两个性质用 $\land$ 连起来, 就是要同时满足: 「是苹果」且「是绿的」.

**第一个例子**: 要找一个自然数 x, 它不大于**任何**自然数. 1 满足, 因为 $1 \le n$ 对所有 $n \in \mathbb{N}$ 成立; 2 不满足, 因为取 $n = 1$ 时 $2 \le 1$ 不成立. 所以集合是 $\{1\}$, 也就是 $\mathbb{N}$ 中最小的那个数. 如果 $\mathbb{N}$ 含 0, 结果就是 $\{0\}$, 所以 $\mathbb{N}$ 的约定会影响答案.

**第二个例子**: 要找一个自然数 x, 它不小于任何自然数, 即「最大的自然数」. 这样的 x 不存在: 对任意 x, 取 $n = x + 1$, 就有 $x \ge n$ 不成立. 所以这个集合一个元素也没有, 是空集 (见 0.1).

#### 以后写入

- 练习

### 0.3 集合运算 (Mengenoperationen)

**Vereinigung, Durchschnitt, Differenz.** x liegt in $A \cup B$, wenn x in A oder in B liegt. x liegt in $A \cap B$, wenn x in beiden liegt. x liegt in A \ B, wenn x in A und nicht in B liegt. Mit den Junktoren aus 0.2: $A \cup B = \{ x \mid x \in A \lor x \in B \}, A \cap B = \{ x \mid x \in A \land x \in B \}, A \setminus B = \{ x \mid x \in A \land \neg (x \in B) \}$.

**Teilmenge, logisch formuliert.** $A \subseteq B$ bedeutet: für alle x gilt $x \in A \Rightarrow x \in B$.

**Kartesisches Produkt.** $A \times B$ ist die Menge aller geordneten Paare (a, b) mit $a \in A$ und $b \in B$. Im Allgemeinen ist (a, b) von (b, a) verschieden. $\mathbb{R}^{2} = \mathbb{R} \times \mathbb{R}$ ist die Ebene der späteren Vektoren.

三个运算可以用 $A = \{1, 2\}$、$B = \{2, 3\}$ 一次看完. 并集 $A \cup B = \{1, 2, 3\}$, 至少属于一个. 交集 $A \cap B = \{2\}$, 两个都属于. 差集 $A \setminus B = \{1\}$, 留在 A 里、去掉也在 B 里的那些.

定义里用的正是 0.2 的联结词, 只是用在「x 属于……」上: $\cup$ 用 $\lor$, $\cap$ 用 $\land$, \ 用 $\land$ 加 $\neg$. 所以并集里「或」也包括「两个都属于」, 因为 $\lor$ 是包含的或.

子集也一样: $A \subseteq B$ 是「对所有 x: $x \in A \Rightarrow x \in B$」. 空集是任何集合的子集, 正是蕴含的规则: $x \in \emptyset$ 永远为假, 前提为假, 蕴含就为真. 0.1 里「空集拿不出反例」说的是同一件事.

笛卡尔积的元素是有序对, 顺序算数. `(1, 2)` 和 `(2, 1)` 一般是不同的元素. 平面 $\mathbb{R}^{2}$ 就是两个实数轴的笛卡尔积, 后面的向量住在这里.

#### 以后写入

- 德摩根定律 (集合版), 怎样证明两个集合相等
- 练习

### 0.4 映射 (Abbildungen)

**Abbildung.** Eine Abbildung $f\colon A \to B$ ordnet jedem Element von A genau ein Element von B zu. A heißt **Definitionsbereich**, B heißt **Zielmenge**.

Das **Bild** ist die Menge der tatsächlich getroffenen Werte: $\operatorname{Bild} (f) = \{ f(a) \mid a \in A \}$. Es ist eine Teilmenge der Zielmenge, nicht automatisch die ganze Zielmenge.

映射是一条规则: 定义域 A 里的每一个输入, 都指定目标集 B 里恰好一个输出. 不能一个输入对两个输出, 也不能有的输入没有输出.

定义域是出发的集合. 目标集是允许落地的集合, 它只规定「输出必须落在这里」, 不保证每个点都被落到.

分析里的 Funktion, 通常就是这种映射, 只是目标集取成实数 $\mathbb{R}$. 线性代数里的 lineare Abbildung 还要额外保住加法和数乘, 那是 1.6 的事.

像 Bild(f) 是真正被取到的那些值. 它一定是目标集的子集. 例如 f 把 $\{1, 2, 3\}$ 送到 $\{a, b, c\}$, 但 1 和 2 都送到 a、3 送到 b, 那么像是 $\{a, b\}$, c 留在目标集里, 却不在像里.

**Komposition.** $(g \circ f)(x) = g(f(x))$. Zuerst wird f angewendet, dann g. Die Reihenfolge im Symbol läuft von rechts nach links.

复合 $(g \circ f)(x)$ 先做右边的 f, 再把结果交给 g. 符号从右往左读, 「$g \circ f$」读作「g nach f」 (g 在 f 之后).

例: $f(x) = x + 1$, $g(x) = x^{2}$. $(g \circ f)(2) = g(3) = 9$; $(f \circ g)(2) = f(4) = 5$. 顺序一换, 结果不同, 所以复合一般不可交换.

复合要能接得上: $f\colon A \to B$, $g\colon B \to C$, f 的输出必须落在 g 的定义域里, $g \circ f$ 才是 $A \to C$ 的映射.

### 0.5 单射、满射、双射 (Injektivität, Surjektivität, Bijektivität)

**Injektiv.** f heißt injektiv, wenn aus $f(x) = f(y)$ stets $x = y$ folgt. Verschiedene Elemente von A landen auf verschiedenen Elementen von B.

**Surjektiv.** f heißt surjektiv, wenn $\operatorname{Bild} (f) = B$ ist. Jedes Element der Zielmenge wird getroffen.

**Bijektiv.** f heißt bijektiv, wenn f injektiv und surjektiv ist. Dann gibt es genau eine **Umkehrabbildung** $f^{-1}\colon B \to A$ mit $f^{-1}(f(a)) = a$ und $f(f^{-1}(b)) = b$.

单射看的是「会不会撞车」. 输出相同, 就能推回输入相同. 图中间: 2 和 3 都落到 b, 两个不同的输入共享一个输出, 所以不是单射.

满射看的是「目标集有没有人被落下」. 像必须等于整个目标集. 图右边: c 没有任何箭头指进来, 所以不是满射.

双射是两件同时成立. 图左边每一个起点恰好对一个终点, 每一个终点也恰好有一个起点. 这时可以按箭头倒回去, 得到唯一的逆映射.

有限集合里, 两边元素个数一样时, 单射、满射、双射会一起成立或一起失败. 个数不一样时, 三个词就要分开检查.

**同一条公式, 换定义域或目标集, 性质就变. ** $f(x) = x^{2}$:

| 映射 | 单射? | 满射? | 原因 |
|---|---|---|---|
$\vert  \mathbb{R} \to \mathbb{R} \vert $ 否 | 否 $\vert  f(-1) = f(1)$; 负数取不到 |
$\vert  \mathbb{R} \to [0, \infty ) \vert $ 否 | 是 | 目标集缩到像 |
$\vert  [0, \infty ) \to \mathbb{R} \vert $ 是 | 否 | 定义域去掉负数后不撞车 |
$\vert  [0, \infty ) \to [0, \infty ) \vert $ 是 | 是 | 双射, 逆映射是 $\sqrt{x} \vert $

所以写映射时, 定义域和目标集是定义的一部分, 不能省.

**证明的标准写法**: 证单射, 设 $f(x) = f(y)$, 推出 $x = y$. 证满射, 任取 $b \in B$, 构造出一个 a 使 $f(a) = b$.

#### 以后写入

- 单射、满射的进一步等价说法
- 复合之后, 单射和满射是否还保持
- 练习里的具体 $f\colon A \to B$

## 1 · 线性代数 (Lineare Algebra)

线性无关, 范数与度量, 向量空间, 矩阵, 然后是线性映射.

### 1.1 线性相关与线性无关 (Lineare Abhängigkeit)

Ein Vektor in $\mathbb{R}^{n}$ ist ein n-Tupel reeller Zahlen und wird als Pfeil vom Ursprung gezeichnet. Skalare sind hier reelle Zahlen. Addition und Skalarmultiplikation geschehen komponentenweise.

Eine **Linearkombination** von $v_{1},\ldots ,v_{k}$ ist eine Summe $c_{1}v_{1} + \ldots + c_{k}v_{k}$ mit reellen Koeffizienten $c_{i}$.

先只借两个词: 向量是从原点出发的箭头, 在 $\mathbb{R}^{n}$ 里写成 n 个实数. 标量是用来拉长或反向的实数. 加法和数乘都按分量做. 基、维数、子空间放到 1.3.

线性组合就是「先分别拉长, 再首尾相接」. 系数 $c_{i}$ 是每一次拉长的倍数.

Die Vektoren heißen **linear unabhängig**, wenn aus $c_{1}v_{1} + \ldots + c_{k}v_{k} = 0$ stets $c_{1} = \ldots = c_{k} = 0$ folgt. Andernfalls heißen sie linear abhängig: einer der Vektoren liegt schon in der linearen Hülle der übrigen.

线性无关的检查只有一句: 这些箭头怎样配系数, 才能加出零向量. 若唯一的办法是每个系数都取 0, 它们就线性无关. 零向量本身不提供新方向, 所以一组里面如果已经有零向量, 这组一定线性相关.

若某个箭头已经落在其余箭头张成的直线或平面里, 它就是多余的. 例如 (2, 0) 落在 (1, 0) 所在的那条横线上, $\{(1, 0), (2, 0)\}$ 线性相关, 因为 $2\cdot (1, 0) + (-1)\cdot (2, 0) = (0, 0)$.

**怎样实际检验**: 把 $c_{1}v_{1} + \ldots + c_{k}v_{k} = 0$ 写成关于 $c_{1},\ldots ,c_{k}$ 的方程组去解. 例: $v_{1} = (1, 2)$, $v_{2} = (3, 1)$. $c_{1}(1, 2) + c_{2}(3, 1) = (0, 0)$ 给出 $c_{1} + 3c_{2} = 0$ 和 $2c_{1} + c_{2} = 0$. 第一式得 $c_{1} = -3c_{2}$, 代入第二式 −$5c_{2} = 0$, 所以 $c_{2} = 0$、$c_{1} = 0$. 只有零解, 线性无关.

两条速记: $\mathbb{R}^{n}$ 里超过 n 个向量一定线性相关; 两个向量线性相关, 当且仅当其中一个是另一个的倍数.

#### 以后写入

- 从方程组读出一组向量是否线性无关
- 课堂例题

### 1.2 范数与度量 (Norm und Metrik)

**Norm.** Eine Norm ordnet jedem Vektor x eine reelle Zahl $\|x\|$ zu und erfüllt drei Regeln: $\|x\| \ge 0$, und $\|x\| = 0$ genau dann, wenn $x = 0$; $\|\lambda x\| = |\lambda|\, \|x\|$; $\|x + y\| \le \|x\| + \|y\|$.

Auf $\mathbb{R}^{n}$ ist die euklidische Norm $\|x\| = \sqrt{x_{1}^{2} + \ldots + x_{n}^{2}}$ die Länge des Pfeils.

范数给每个向量一个长度. 三条规则分开记: 长度不会是负数, 只有零向量的长度是 0; 数乘把长度乘上系数的绝对值, 反向不改变长度; 三角形两边之和至少等于第三边, 所以绕路不会比直走更短.

欧氏范数就是勾股定理. 平面上 (3, 4) 的长度是 $\sqrt{9 + 16} = 5$.

**Metrik.** Eine Metrik d misst den Abstand zweier Punkte: $d(x, y) \ge 0$, und $d(x, y) = 0$ genau für $x = y$; $d(x, y) = d(y, x)$; $d(x, z) \le d(x, y) + d(y, z)$. Jede Norm erzeugt durch $d(x, y) = \|x - y\|$ eine Metrik.

度量量的是两个点之间的距离, 不必须先有箭头. 它也有三条: 距离非负, 只有自己到自己是 0; 从 x 到 y 和从 y 到 x 一样远; 经过第三点不会更近.

有了范数, 距离可以定义成「两个向量之差的长度」. 统计里写误差, 用的就是这个距离. 别的范数如果以后用到, 写在下面, 不另开标题.

例: $x = (1, 2)$, $y = (4, 6)$. $x - y = (-3, -4)$, $d(x, y) = \|x - y\| = \sqrt{9 + 16} = 5$.

> **补充 · 另外两种常见范数**
>
$> 1$-范数 $\|x\|_{1} = |x_{1}| + \ldots + |x_{n}|$(「曼哈顿距离」, 只能沿网格走); 最大范数 $\|x\|_{\infty} = \max |x_{i}|$. 对 (3, 4): $\|\cdot \|_{1} = 7$, $\|\cdot \|_{2} = 5$, $\|\cdot \|_{\infty} = 4$. 三者都满足那三条规则, 只是量「长度」的方式不同. 统计里最小二乘用 2-范数, Lasso 回归用 1-范数.

#### 以后写入

- 别的范数, 以及它们和欧氏范数的比较
- 内积如果以后引入, 写在这里
- 练习

### 1.3 实向量空间 (Reelle Vektorräume)

$\mathbb{R}^{n}$ mit komponentenweiser Addition und Skalarmultiplikation ist ein reeller Vektorraum. Man schreibt ihn $(\mathbb{R}^{n}, +, \cdot )$: + ist die Addition, · die Skalarmultiplikation. Der Nullvektor ist (0,…,0).

$\mathbb{R}^{n}$ 是这一块的样本: 向量可以相加, 可以乘实数, 结果仍是 $\mathbb{R}^{n}$ 里的向量. 记作 $(\mathbb{R}^{n}, +, \cdot )$, 加号是向量加法, 点是数乘. 零向量每个分量都是 0, 它是加法的单位, 加它等于没走.

图的左边是加法. 先走完蓝色的 u, 再从箭头尖端接上橙色的 v, 黑线的终点就是 $u + v$. 虚线把平行四边形补全: 先走 v 再走 u, 终点相同.

图的右边是数乘. 2u 和 u 同一方向, 长度变成两倍. −u 转到相反方向, 长度不变.

Die **lineare Hülle** von $v_{1},\ldots ,v_{k}$ ist die Menge aller Linearkombinationen dieser Vektoren. Ein einzelner Vektor ungleich 0 spannt eine Gerade durch den Ursprung auf. Zwei nicht parallele Vektoren in der Ebene spannen die ganze Ebene auf.

Ein **Erzeugendensystem** erzeugt den ganzen Raum. Eine **Basis** ist ein linear unabhängiges Erzeugendensystem. Die **Dimension** ist die Anzahl der Vektoren in einer Basis; jede Basis desselben Raums hat dieselbe Anzahl.

线性张成是这组向量所有线性组合放在一起. 一个非零向量只张成过原点的一条直线. 平面上两个不平行的向量, 能走到平面上任意一点, 张成整张平面.

生成组要求「够用」: 空间里每个向量都能写出来. 基还要求「没有多余」, 也就是线性无关. 维数是一组基里向量的个数. 同一个空间可以换很多组基, 个数不会变. 平面的维数是 2, 所以任何一组基都恰好两个向量.

Die **Standardbasis** von $\mathbb{R}^{n}$ besteht aus den Vektoren $e_{i}$, die an der i-ten Stelle 1 und sonst 0 sind.

Ein **Unterraum** ist eine nichtleere Teilmenge, die unter Addition und Skalarmultiplikation abgeschlossen ist.

标准基最好认. 平面上 $e_{1} = (1, 0)$ 指向右, $e_{2} = (0, 1)$ 指向上. 任何 (x, y) 都是 $x e_{1} + y e_{2}$.

子空间要对加法和数乘**封闭**: 两个向量在里面, 相加还在里面; 一个向量在里面, 乘任何实数后还在里面. 过原点的直线、过原点的平面, 都是. 一条不穿过原点的直线不是, 因为零向量不在上面, 数乘也会把点带离那条线.

#### 以后写入

- 求一组向量的线性张成
- 把一组向量补成基, 或从中选出基
- 证明某个子集是子空间

### 1.4 一般向量空间 (Allgemeine Vektorräume)

Sei K ein Körper. In diesem Modul ist K zunächst $\mathbb{R}$, gelegentlich $\mathbb{C}$. Ein K-Vektorraum ist eine Menge V mit Addition und Skalarmultiplikation, sodass $(V, +)$ eine abelsche Gruppe ist. Das neutrale Element heißt Nullvektor. Außerdem gelten $\lambda (u + v) = \lambda u + \lambda v, (\lambda + \mu )v = \lambda v + \mu v, (\lambda \mu )v = \lambda (\mu v)$ und $1\cdot v = v$.

Linearkombination, lineare Unabhängigkeit, Basis und Dimension werden wörtlich wie in $\mathbb{R}^{n}$ definiert. Jeder n-dimensionale reelle Vektorraum ist zu $\mathbb{R}^{n}$ isomorph: nach Wahl einer Basis entspricht jeder Vektor genau einer Koordinatenspalte.

$\mathbb{R}^{n}$ 是一个例子, 不是定义本身. 定义只保留运算规则: 能加, 加法可以交换、有零向量、每个向量有相反向量; 能乘标量; 乘法和加法互相分配; 先乘两个标量再乘向量, 和分两步乘, 结果相同; 乘 1 等于不改变.

标量来自一个**域 (Körper) ** K: 一个能做加减乘除 (除数不为 0)、且满足通常运算律的数集. 这门课入门时 K 就是实数 $\mathbb{R}$, 偶尔用复数 $\mathbb{C}$. 有理数 $\mathbb{Q}$ 也是域; 整数 $\mathbb{Z}$ 不是, 因为 1 ÷ 2 不在 $\mathbb{Z}$ 里.

**abelsche Gruppe**就是上面加法那四条的总称: 结合律、交换律、有零元、每个元素有相反元. 名字来自数学家 Abel.

多项式可以相加、可以乘常数, 所以多项式也是向量. 函数、矩阵同样可以. 它们不是「一列数」, 但满足同一组规则, 线性组合、线性无关、基、维数这些词可以原样搬过去.

同构的意思是: 选定一组基之后, 每个抽象向量恰好对应 $\mathbb{R}^{n}$ 里的一列坐标. 结构一样, 只是写法换成了数. 坐标和表示矩阵的算法放在 1.6, 因为那里才有线性映射.

#### 以后写入

- 多项式空间、函数空间怎样验算公理
- 同构的证明
- 练习

### 1.5 矩阵计算 (Matrixrechnung)

Eine reelle $m\times n$-**Matrix** ist ein rechteckiges Schema mit m Zeilen und n Spalten. Der Plural lautet Matrizen. Addition und Skalarmultiplikation geschehen eintragsweise; dafür müssen die Formate übereinstimmen.

Die **Matrizenmultiplikation** ist die Hintereinanderausführung linearer Abbildungen. (AB) bedeutet: zuerst B, dann A. Die Spaltenzahl von A muss gleich der Zeilenzahl von B sein. Im Allgemeinen ist AB von BA verschieden.

矩阵是一张长方形的数表. $3\times 2$ 表示 3 行 2 列. 两个矩阵要同行同列, 才能相加; 加法、数乘都是对应位置分别做.

矩阵在这里的身份是线性映射的记录. 原点留在原点, 直线仍变成直线, 平行线仍平行, 方格变成平行四边形. 每一列回答一个标准基向量被送到哪里.

图里的矩阵是第一行 2、1, 第二行 0、1. 第一列 (2, 0) 是 $e_{1}$ 的落点, 水平方向拉长到 2 倍. 第二列 (1, 1) 是 $e_{2}$ 的落点, 原来朝上的箭头被送到右上方.

任意向量 (x, y) 先写成 $x e_{1} + y e_{2}$. 它的落点就是 x 乘第一列, 加上 y 乘第二列. 这就是矩阵乘向量.

两个矩阵相乘, 是两个变换接连做. (AB) 先做 B, 再做 A. 左边的列数必须等于右边的行数, 中间的那一维才接得上: $(m \times \mathbf{k}) \cdot (\mathbf{k} \times n)$ 得到 $m\times n$. 顺序换了, 通常是另一个变换, 所以 $AB \ne BA$ 是常态.

计算规则: (AB) 第 i 行第 j 列 = A 的第 i 行与 B 的第 j 列对应相乘再相加. 例:

$$
\begin{bmatrix} 1 & 2 \\ 3 & 4 \end{bmatrix}\begin{bmatrix} 5 & 6 \\ 7 & 8 \end{bmatrix} = \begin{bmatrix} 1\cdot 5+2\cdot 7 & 1\cdot 6+2\cdot 8 \\ 3\cdot 5+4\cdot 7 & 3\cdot 6+4\cdot 8 \end{bmatrix} = \begin{bmatrix} 19 & 22 \\ 43 & 50 \end{bmatrix}
$$

Die **transponierte Matrix** erfüllt $(A^{T})_{ij} = A_{ji}$. Eine quadratische Matrix hat gleich viele Zeilen und Spalten. Die **Einheitsmatrix** I hat Einsen auf der Diagonalen und sonst Nullen, und es gilt $AI = IA = A$.

转置把第 i 行第 j 列的数, 放到第 j 行第 i 列, 也就是沿对角线翻过去: 行变列, 列变行. $m\times n$ 矩阵转置后是 $n\times m$. 常用规则 $(AB)^{T} = B^{T}A^{T}$, 顺序要反过来.

方阵的行数和列数相同. 单位矩阵 I 的对角线是 1, 其余是 0. 作为变换, 它把每个向量送回自己, 所以乘它等于不改变, 相当于数里的 1.

Eine **inverse Matrix** erfüllt $A A^{-1} = A^{-1} A = I$. Nicht jede quadratische Matrix besitzt eine Inverse.

Der **Rang** ist die maximale Anzahl linear unabhängiger Spalten und ebenso der Zeilen. Er ist die Dimension des Bildes der zugehörigen Abbildung.

逆矩阵把变换倒回去. 网格若被压成一条线, 不同的输入撞到同一个输出, 就没有逆. 秩是输出那边还张开的维数: 压成一条线时秩是 1, 压成原点时秩是 0, 平面仍然铺满时秩是 2, 这时 $2\times 2$ 的方阵可逆.

$2\times 2$ 的情形有现成公式: $A = \begin{bmatrix} a & b \\ c & d \end{bmatrix}$, 若 $ad - bc \ne 0$, 则 $A^{-1} = \frac{1}{ad - bc} \cdot \begin{bmatrix} d & -b \\ -c & a \end{bmatrix}$. $ad - bc = 0$ 时网格被压扁, 不可逆.

#### 线性方程组 (Lineare Gleichungssysteme)

Ein lineares Gleichungssystem schreibt man als $Ax = b$. Gesucht sind alle Vektoren x, die von A auf b geschickt werden.

$Ax = b$ 问的是: 哪个输入向量会被 A 送到 b.

Zwei Gleichungen in zwei Unbekannten beschreiben zwei Geraden. Es gibt genau eine Lösung, keine Lösung, oder unendlich viele Lösungen.

Für $b = 0$ ist $x = 0$ immer eine Lösung. Die Lösungsmenge ist der Kern von A. Ist $b \ne 0$ und ist $x_{0}$ eine besondere Lösung, so entstehen alle weiteren Lösungen als $x_{0}$ plus eine Lösung der homogenen Gleichung.

平面上两个方程是两条直线. 左图相交于 (1, 1), 恰好一个解. 中图平行且不重合, 没有公共点, 没有解. 右图两条方程其实是同一条直线, 这条线上的点都是解.

$b = 0$ 时, 零向量一定是解. 全部解组成 1.6 里的核. b 不是 0 时, 先找一个特解 $x_{0}$, 其余解都是「$x_{0}$ 再加上一个被送到 0 的向量」.

#### 以后写入

- 高斯消元, 行最简形
- 逆矩阵的算法; 行列式如果以后引入
- 具体的方程组

### 1.6 像、核、表示矩阵 (Lineare Abbildungen)

Eine Abbildung $f\colon V \to W$ heißt **linear**, wenn $f(u + v) = f(u) + f(v)$ und $f(\lambda v) = \lambda f(v)$. Dann ist $f(0) = 0$.

Der **Kern** ist $\{ v \in V \mid f(v) = 0 \}$. Das **Bild** ist $\{ f(v) \mid v \in V \}$. Beide sind Unterräume.

线性映射是保住线性组合的映射. 先加再送走, 和先送走再加, 结果相同. 先拉长再送走, 和先送走再拉长, 结果也相同. 把这两条用到零向量上, 得到 $f(0) = 0$: 原点一定被送到原点.

核是被送到零向量的那些输入. 像是输出那边真正被取到的向量, 和 0.4 里「像」是同一个词, 只是现在两边都是向量空间. 核和像自己也是子空间.

**Dimensionsformel.** Ist V endlichdimensional, so gilt dim V = dim Kern(f) + dim Bild(f). Für eine Matrix mit n Spalten heißt das n = dim Kern(A) + Rang(A).

维数公式把输入的维数分成两部分. 被压扁掉的维数是核的维数, 仍然张在输出里的维数是像的维数, 加起来等于输入的维数. 对 n 列的矩阵, 像的维数就是秩, 所以 n = 核的维数 + 秩.

Nach Wahl von Basen gehört zu f genau eine **Darstellungsmatrix**. Ihre j-te Spalte ist die Koordinate von $f(b_{j})$.

Ein **Basiswechsel** ändert die Koordinaten, nicht die Abbildung. Stehen die neuen Basisvektoren als Spalten in P, so gilt $[v] = P[v]'$. Die Darstellungsmatrix wird zu $P^{-1}AP$, wenn derselbe Wechsel auf beiden Seiten stattfindet.

选定两边的基之后, 线性映射对应唯一一个矩阵. 第 j 列是「第 j 个输入基向量的像」在输出基下的坐标. 这和 1.5 里「列是 $e_{1}$、$e_{2}$ 的落点」是同一件事, 只是网格可以换成别的基.

基变换换的是描述用的网格, 不是箭头本身. 图里这根箭头在标准基下是 (3, 1). 新基取 $b_{1} = (1, 0)$、$b_{2} = (1, 1)$ 时, 同一根箭头写成 $2 b_{1} + b_{2}$, 新坐标是 (2, 1). P 的各列是新基在旧坐标里的写法. 旧坐标等于 P 乘新坐标. 同一个线性映射的矩阵, 从 A 改写成 $P^{-1}AP$.

#### 以后写入

- 求给定矩阵的核和像
- 在给定基下写出表示矩阵
- 基变换的计算题

## 2 · 一元分析 (Analysis in einer Variablen)

数列, 级数, 然后连续、可导, 最后是极值.

### 2.1 数列 (Folgen)

Eine **Folge** $(a_{n})$ ist eine durchnummerierte Liste reeller Zahlen.

Sie **konvergiert** gegen a, wenn für jedes $\varepsilon > 0$ ein Index N existiert, sodass $|a_{n} - a| < \varepsilon$ für alle $n \ge N$. Die Zahl a heißt **Grenzwert**. Sonst **divergiert** die Folge, auch wenn sie nach +$\infty$ oder −$\infty$ läuft.

数列是按 1、2、3… 编号的一串实数. 它和后面的级数不是同一个对象: 数列看每一项本身, 级数看把这些项加起来.

收敛的定义按这个顺序读. 先由你任意指定一个误差 ε, 不管多小. 然后必须存在一个编号 N. 从这个编号起, 后面每一项到 a 的距离都小于 ε. a 就叫极限.

图里 $a_{1}$、$a_{2}$、$a_{3}$ 还在蓝色带子外面. 从 $a_{4}$ 起, 后面的点都落进带子. 所以这里的 N 可以取 4. ε 如果画得更窄, N 通常要往后推, 这是允许的.

没有这样的有限 a, 就叫发散. 跑向正无穷或负无穷也算发散, 只是发散的方式可以单独写下来.

**例: 证明 $a_{n} = 1/n$ 收敛到 0. ** 任给 $\varepsilon > 0$. 要 $|1/n - 0| = 1/n < \varepsilon$, 只需 $n > 1/\varepsilon$. 所以取 N 为大于 $1/\varepsilon$ 的任一自然数, 则对所有 $n \ge N$ 有 $1/n \le 1/N < \varepsilon$. 比如 $\varepsilon = 0.01$ 时取 $N = 101$. 证明的结构永远是「任给 ε → 写出 N (依赖 ε) → 验证不等式」.

Sie ist **beschränkt**, wenn alle Glieder in einem festen endlichen Intervall liegen, und **monoton**, wenn sie durchgehend wächst oder fällt. Jede monotone und beschränkte reelle Folge konvergiert.

有界是全部项都待在某个固定的有限区间里. 单调是一直不减, 或一直不增. 实数数列只要两件同时成立, 就一定收敛. 1, 2, 3, … 单调, 但无界. $(-1)^{n}$ 有界, 但在 −1 和 1 之间来回, 既不单调, 也不收敛.

Eine **Cauchy-Folge** erfüllt: für jedes $\varepsilon > 0$ gibt es ein N, sodass $|a_{m} - a_{n}| < \varepsilon$ für alle $m, n \ge N$. In $\mathbb{R}$ sind das genau die konvergenten Folgen.

Eine **Teilfolge** behält die Reihenfolge und lässt Glieder aus. Jede Teilfolge einer konvergenten Folge hat denselben Grenzwert.

柯西列的句子里不先写出极限 a. 它只要求靠后的项彼此靠得很近. 在实数里, 这种数列和收敛数列是同一批.

子列是按原来的先后抽出一部分, 下标严格变大. 收敛列的每个子列都收敛到同一个极限.

#### 以后写入

- 用 ε-N 证明一个具体极限
- 单调有界定理的例子
- 练习

### 2.2 级数 (Reihen)

Die **Reihe** $\sum a_{n}$ untersucht die Summen der Folgenglieder. Die **Partialsumme** ist $s_{n} = a_{1} + \ldots + a_{n}$. Die Reihe konvergiert genau dann, wenn die Folge $(s_{n})$ konvergiert.

Die **geometrische Reihe** $\sum q^{n}$, beginnend bei $n = 0$, konvergiert für $|q| < 1$ gegen $1/(1 - q)$ und divergiert für $|q| \ge 1$.

级数不直接看 $(a_{n})$ 停在哪里. 它先做部分和 $s_{n}$, 也就是加到第 n 项的结果, 再问数列 $(s_{n})$ 是否收敛. 级数收敛, 就是这列新数收敛.

几何级数从 $n = 0$ 加起, 每一项是前一项乘公比 q. $|q| < 1$ 时, 总和是 $1/(1 - q)$. $|q| \ge 1$ 时发散. 公式的来历: 部分和 $s_{n} = 1 + q + \ldots + q^{n}$, 乘 (1 − q) 后中间全部消掉, 得 $s_{n} = (1 - q^{n+1})/(1 - q)$; $|q| < 1$ 时 $q^{n+1} \to 0$.

图是 $q = 1/2$. 部分和依次是 1, 1.5, 1.75, 1.875, …, 挤向 2. 每一步走掉剩余距离的一半. $1/(1 - 1/2) = 2$, 和图像一致.

Die **harmonische Reihe** $\sum 1/n$ divergiert. **Absolute Konvergenz** bedeutet, dass $\sum |a_{n}|$ konvergiert; daraus folgt die Konvergenz von $\sum a_{n}$.

调和级数是 $1 + 1/2 + 1/3 + 1/4 + \ldots$. 把项分组: $1/2$ 自己是 $1/2$; $1/4 + 1/4$ 又是 $1/2$; 接着四个 $1/8$ 还是 $1/2$. 可以不断切出新的 $1/2$, 部分和没有上限, 所以发散.

绝对收敛是把每一项换成绝对值之后, 那个新级数仍然收敛. 绝对收敛能推出原来的级数收敛. 交错调和级数 $1 - 1/2 + 1/3 - 1/4 + \ldots$ 收敛, 但绝对值组成的调和级数发散. 这种收敛叫条件收敛.

**Majorantenkriterium.** Aus $0 \le a_{n} \le b_{n}$ und der Konvergenz von $\sum b_{n}$ folgt die Konvergenz von $\sum a_{n}$.

**Quotientenkriterium.** Ist $q = \lim |a_{n+1} / a_{n}|$, so liegt absolute Konvergenz für $q < 1$ und Divergenz für $q > 1$ vor. Für $q = 1$ sagt das Kriterium nichts.

**Wurzelkriterium.** Derselbe Schluss gilt für $q = \lim \sqrt[n]{|a_{n}|}$.

比较判别法找一个更大、而且已知收敛的正项级数, 把原级数盖住.

比值判别法看相邻两项绝对值之比的极限 q. $q < 1$ 绝对收敛, $q > 1$ 发散, $q = 1$ 时这个办法不作结论: $\sum 1/n$(发散) 和 $\sum 1/n^{2}$(收敛) 的 q 都是 1. 例: $\sum 1/n!$ 的比值是 $1/(n+1) \to 0 < 1$, 所以收敛.

根值判别法把「比值」换成「绝对值的 n 次方根」, 结论相同.

**Leibniz-Kriterium.** Wechseln die Vorzeichen und fällt $|a_{n}|$ monoton gegen 0, so konvergiert die Reihe.

Eine **Potenzreihe** $\sum c_{n}(x - x_{0})^{n}$ hat einen **Konvergenzradius** R: für $|x - x_{0}| < R$ konvergiert sie, für $|x - x_{0}| > R$ divergiert sie. Die Randpunkte werden einzeln geprüft.

莱布尼茨判别法用于正负交替: 绝对值单调下降, 而且下降到 0, 级数就收敛.

幂级数的每一项带一个 $(x - x_{0})$ 的幂. 收敛半径 R 画出一个开区间: 到中心的距离小于 R 就收敛, 大于 R 就发散. 正好等于 R 的两个端点, 要另外检查, 半径本身不回答它们.

#### 以后写入

- 四个判别法的证明和应用题
- 幂级数在端点上的讨论
- 练习

### 2.3 实函数 (Reelle Funktionen)

Eine **Funktion** $f\colon D \to \mathbb{R}$ ist eine Abbildung mit reellen Werten. Der **Graph** besteht aus den Punkten (x, f(x)).

Die **Verkettung** ist $(g \circ f)(x) = g(f(x))$. Eine **Umkehrfunktion** gibt es, wenn f auf sein Bild bijektiv ist. Eine stetige, streng monotone Funktion auf einem Intervall besitzt dort eine Umkehrfunktion.

这里的函数就是 0.4 的映射, 输出规定为实数. 定义域 D 是允许输入的 x. 像是实际取到的函数值. 图像是平面上的点 (x, f(x)), 每个 x 只有一个高度.

复合和映射的复合是同一个运算. 反函数要求这个对应在像上是双射, 每个函数值恰好来自一个 x. 区间上的连续严格单调函数满足这件事 (严格单调保证不撞车), 所以在它的像上可以反解. 例: $\exp \colon \mathbb{R} \to (0, \infty )$ 严格递增, 反函数是 ln.

这门课反复出现多项式、有理函数 (多项式相除, 分母不为 0), 以及 exp、ln、sin、cos.

$\lim_{x \to a} f(x) = L$ bedeutet: für jedes $\varepsilon > 0$ gibt es ein $\delta > 0$, sodass aus $0 < |x - a| < \delta$ stets $|f(x) - L| < \varepsilon$ folgt. Der Punkt a muss nicht zu D gehören.

Der linksseitige Grenzwert betrachtet nur $x < a$, der rechtsseitige nur $x > a$. Der beidseitige Grenzwert existiert genau dann, wenn beide existieren und gleich sind.

函数极限把「第 n 项」换成「x 靠近 a」. 先给定误差 ε, 再找一个足够小的距离 δ. x 到 a 的距离小于 δ、但不等于 0 时, 函数值到 L 的距离就小于 ε. 条件写成 $0 < |x - a|$, 所以 a 自己可以不在定义域里. $1/x$ 在 0 附近可以谈极限, 尽管不能把 x 代入 0.

左极限只从左边靠近, 右极限只从右边靠近. 两边都存在, 而且是同一个数, 整个极限才存在.

#### 以后写入

- 具体函数的定义域和像
- 用 ε-δ 验证极限
- 左极限、右极限的例子

### 2.4 连续性 (Stetigkeit)

f heißt **stetig** in a, wenn a im Definitionsbereich liegt, der Grenzwert existiert und gleich f(a) ist.

连续是三件事同时成立. a 在定义域里, 所以 f(a) 有意义. x 靠近 a 时极限存在. 这个极限正好等于 f(a), 没有跳到别的高度.

|x| 在 0 满足这三件: 左右都挤向 0, 函数值也是 0. 图像在这里是一个尖角. 尖角不影响连续. 它影不影响可导, 是 2.5 的问题.

**Zwischenwertsatz.** Ist f auf [a, b] stetig und liegt c zwischen f(a) und f(b), so gibt es ein x in [a, b] mit $f(x) = c$. Haben f(a) und f(b) verschiedene Vorzeichen, so hat f dazwischen eine Nullstelle.

Eine auf [a, b] stetige Funktion nimmt dort Minimum und Maximum an. Auf einem offenen Intervall muss das nicht gelten: $1/x$ ist auf (0, 1] stetig und nach oben unbeschränkt.

介值定理说: 闭区间上的连续函数从 f(a) 走到 f(b), 中间每个高度都会经过. 两端一正一负时, 0 就在中间, 所以这段里有一个零点.

同一个闭区间上, 连续函数一定取到最大值和最小值, 而且取到的位置在区间里面, 包含端点. 开区间或半开区间不必如此. $1/x$ 在 (0, 1] 上连续, x 越靠近 0, 函数值越大, 没有上限, 也就没有最大值.

#### 以后写入

- 介值定理和最值定理的应用
- 不连续的例子: 跳开, 或把一点挖去
- 练习

### 2.5 可导性 (Differenzierbarkeit)

Der **Differenzenquotient** $(f(a+h) - f(a)) / h$ ist die Steigung der Sekante. Die **Ableitung** ist sein Grenzwert für $h \to 0$. Existiert er, so heißt f in a **differenzierbar**.

**Lokale Approximierbarkeit.** Gleichbedeutend ist: es gibt eine Zahl m mit $f(a+h) = f(a) + m h + r(h)$ und $\lim_{h \to 0} r(h)/h = 0$. Dann ist $m = f'(a)$. Die Abbildung $h \mapsto m h$ ist linear.

差商是两点连线的斜率. 分子是函数值改变了多少, 分母 h 是 x 走了多远. h 缩到 0, 这条割线转成切线. 切线斜率的极限就是导数 f'(a). 这个极限存在, 就叫在 a 可导.

同一句话可以写成局部线性逼近. 存在一个数 m, 使 $f(a+h) = f(a) + m h + r(h)$, 而且 $r(h)/h$ 趋向 0. m h 是过点 (a, f(a)) 的直线. r(h) 是曲线和这条直线的误差. 误差本身会变小, 还不够; 它必须比步长 h 更小一级. 这时 m 就是 f'(a). 乘上 m 是最简单的线性映射, 也就是 1.6 里那种保住加法和数乘的映射, 只是这里的空间是一条实数轴.

用 $f(x) = x^{2}$ 在 $a = 1$ 看. $f'(1) = 2$, 所以 $f(1+h) = (1+h)^{2} = 1 + 2h + h^{2}$. 这里 $m = 2$, $r(h) = h^{2}$, $r(h)/h = h$, h 趋向 0 时它也趋向 0. 左图里 h 还比较大, 竖线段就是看得见的误差. 右图把窗口收到 a 附近, 曲线和切线几乎叠在一起.

Differenzierbarkeit in a zieht Stetigkeit in a nach sich. Die Umkehrung gilt nicht.

可导能推出连续: 切线斜率都有了, 函数值不能在这里跳开. 反过来不必成立. |x| 在 0 连续, 左边斜率是 −1, 右边斜率是 +1. 任何一条直线只能贴住一侧, 找不到单独一个 m. 第二张图把这两条候选直线画在尖角下面.

**Summenregel** $(f+g)' = f' + g'$. **Produktregel** $(fg)' = f'g + fg'$. **Quotientenregel** $(f/g)' = (f'g - fg') / g^{2}$ für $g \ne 0$. **Kettenregel** $(g \circ f)'(x) = g'(f(x)) \cdot f'(x)$.

**Satz von Rolle.** Ist f auf [a, b] stetig, auf (a, b) differenzierbar und $f(a) = f(b)$, so gibt es ein c in (a, b) mit $f'(c) = 0$.

**Mittelwertsatz.** Unter denselben Voraussetzungen ohne $f(a) = f(b)$ gibt es ein c mit $f'(c) = (f(b) - f(a)) / (b - a)$.

四条求导规则按函数怎么组合来选. 和用和的导数. 积要两边分别求导再交叉加. 商的分母不能是 0, 分子是「上导下, 减上下导」. 复合用链式法则: 里面的函数先把步长乘上 f'(x), 外面的函数再乘上 g' 在该处的斜率, 两个倍数相乘.

罗尔定理: 两端一样高, 中间处处有切线, 就一定有一处切线是水平的.

中值定理把「两端点连线的斜率」写成中间某一点的导数. 罗尔定理是这条连线斜率为 0 的特殊情况. 后面判断函数升降, 用的就是中值定理.

> **补充 · 常用导数**
>
$> | f(x) | f'(x) | f(x) | f'(x) |$
$> |---|---|---|---|$
$> | x^{n} | n x^{n-1} | e^{x} | e^{x} |$
$> | \ln x$($x > 0$) $| 1/x | \sin x | \cos x |$
$> | \cos x | -\sin x | \sqrt{x} | 1/(2\sqrt{x}) |$

> 链式法则例: $(e^{x^{2}})' = e^{x^{2}} \cdot 2x$, 外层 $e^{u}$ 的导数是 $e^{u}$, 再乘内层 $u = x^{2}$ 的导数 2x.

#### 以后写入

- 基本函数的导数表
- 用定义计算 f'(a) 的例题
- 链式法则和中值定理的练习

### 2.6 曲线讨论与极值 (Kurvendiskussion und Extrema)

Ein **lokales Extremum** ist der größte oder kleinste Wert in einer Umgebung. Ein **globales Extremum** ist der größte oder kleinste Wert auf dem ganzen Definitionsbereich.

**Notwendige Bedingung.** Ist f nahe $x_{0}$ differenzierbar und hat dort ein lokales Extremum, so gilt $f'(x_{0}) = 0$. Auf einem abgeschlossenen Intervall sind zusätzlich die Randpunkte zu prüfen. Stellen ohne Ableitung sind ebenfalls kritisch.

$f'(x_{0}) = 0$ ist nicht hinreichend: für $f(x) = x^{3}$ gilt $f'(0) = 0$, aber 0 ist kein lokales Extremum.

局部极值只和这一点附近比. 附近的函数值都没有它大, 就是局部最大; 都没有它小, 就是局部最小. 全局极值要和整个定义域比.

必要条件用在内部、而且这里可导的时候: 如果它是局部极值, 切线必须是水平的, $f'(x_{0}) = 0$. 这句话不能倒过来用. $x^{3}$ 在 0 的导数是 0, 函数却从负穿到正, 0 不是局部最大, 也不是局部最小.

闭区间上的全局最值还要看端点, 以及导数不存在的点. 直线 $f(x) = x$ 在 [0, 1] 上的最大值在 $x = 1$, 导数处处是 1, 从来不为 0. 只找 $f' = 0$ 会把这个最大值漏掉.

**Hinreichende Bedingungen.** Wechselt f' von positiv nach negativ, so liegt ein lokales Maximum vor; von negativ nach positiv ein lokales Minimum. Gilt $f'(x_{0}) = 0$ und $f''(x_{0}) < 0$, so liegt ein lokales Maximum vor; gilt $f''(x_{0}) > 0$, so liegt ein lokales Minimum vor. Aus $f''(x_{0}) = 0$ folgt nichts.

**Monotonie.** Aus $f' \ge 0$ folgt Wachstum, aus $f' \le 0$ Fallen, aus $f' > 0$ strenges Wachstum.

充分条件可以看 f' 的变号. 由正变负, 函数从升变降, 是局部最大. 由负变正, 是局部最小. 也可以在 f' 已经是 0 的时候看 f'': $f'' < 0$ 是局部最大, $f'' > 0$ 是局部最小. $f'' = 0$ 时这个检验不作结论. $x^{3}$ 和 $x^{4}$ 在 0 的二阶导数都是 0, 前者不是极值, 后者是局部最小.

单调性由 f' 的符号读出. $f' \ge 0$ 时函数递增, $f' \le 0$ 时递减, $f' > 0$ 时严格递增. 区间两端的高度差, 等于中间某点的斜率乘上宽度, 这就是中值定理.

f heißt **konvex**, wenn die Sehne über dem Graphen liegt: $f(tx + (1-t)y) \le t f(x) + (1-t) f(y)$ für alle x, y und alle $t \in [0, 1]$. Existiert f'', so ist das $f'' \ge 0$. Bei einer **konkaven** Funktion liegt die Sehne darunter und es gilt $f'' \le 0$.

Ein **Wendepunkt** verlangt einen Vorzeichenwechsel von f''. $f''(x_{0}) = 0$ allein genügt nicht.

德语的 konvex 是碗口向上. 任取两点, 连接它们的弦在图像上方, 也就是函数值不超过弦上的高度. 二阶导数存在时, 这等价于 $f'' \ge 0$, $x^{2}$ 就是这样. konkav 是弦在图像下方, $f'' \le 0$. 中学口语里的「上凸」对应这里的 konkav.

拐点是凹凸改变的地方, f'' 要在这里变号. 只写 $f''(x_{0}) = 0$ 不够. $x^{4}$ 在 0 的二阶导数是 0, 但两侧都非负, 凹凸没有改变, 所以不是拐点. $x^{3}$ 在 0 从 $f'' < 0$ 变成 $f'' > 0$, 这才是拐点, 而且那里的切线不是水平的.

一条曲线按这个顺序看完: 定义域, 尤其分母何时为 0; 零点和 f(0); 对称性, $f(-x) = f(x)$ 关于 y 轴, $f(-x) = -f(x)$ 关于原点; 渐近线; 用 f' 划分单调区间; 用临界点、导数不存在的点和端点找极值, 再区分必要条件和充分条件; 用 f'' 看凹凸和拐点; 最后画图.

#### 例子: f(x) = x³ − 3x (Ein Beispiel)

f ist auf ganz $\mathbb{R}$ definiert und ungerade, denn $f(-x) = -f(x)$. Die Nullstellen sind 0 und $\pm \sqrt{3}$.

$f'(x) = 3x^{2} - 3 = 3(x - 1)(x + 1)$. Also wächst f auf $(-\infty , -1]$ und auf $[1, \infty )$ und fällt auf [−1, 1]. Bei $x = -1$ liegt ein lokales Maximum mit Wert 2, bei $x = 1$ ein lokales Minimum mit Wert −2.

$f''(x) = 6x$. Für $x < 0$ ist f konkav, für $x > 0$ konvex. Bei $x = 0$ wechselt f'' das Vorzeichen: dort liegt ein Wendepunkt. Die Tangente ist nicht waagerecht, denn $f'(0) = -3$.

定义域是全体实数, 没有分母要排除. $f(-x) = -f(x)$, 图像关于原点对称, 所以右边算完, 左边可以翻过去.

令 $f(x) = x(x^{2} - 3) = 0$, 零点是 0 以及 $\pm \sqrt{3}$, 大约是 $\pm 1.73$. 它们都画在横轴上.

$f'(x) = 3(x - 1)(x + 1)$. 在 $x < -1$ 和 $x > 1$ 时, 两个因式同号, $f' > 0$, 函数递增. 在 −1 和 1 之间, $f' < 0$, 函数递减.

$x = -1$ 是从升到降的转折, $f(-1) = 2$, 局部最大. $x = 1$ 是从降到升的转折, $f(1) = -2$, 局部最小. 这两处切线水平. 因为定义域是整条实数轴, 函数还能继续升到正无穷、降到负无穷, 所以这两个只是局部极值, 不是全局最大或最小.

$f''(x) = 6x$. $x < 0$ 时碗口向下, 是 konkav. $x > 0$ 时碗口向上, 是 konvex. $x = 0$ 处变号, 是拐点. $f'(0) = -3$, 拐点处的切线斜着走, 不是水平的.

#### 以后写入

- 必要条件和充分条件的课堂证明
- 完整的 Kurvendiskussion, 按八步写
- 闭区间上求全局最大、最小的题
