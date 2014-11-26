物理
******************


物理在目前科幻里面出镜率大概可以可匹敌生物，再加上我的专业背景，所以如果将来没有其他人加入到这个文档的编辑中来的话，这大概也会是内容最多的一章了。


:index:`太空旅行`
=================



:index:`曲率推进`
--------------------------------------

这是一个在科幻中几乎用烂了的点子，然而这背后确实是有相关的科学研究的，主要是基于广义相对论的研究。关于这部分，在 `《星际移民之书》 <http://interimm.org/InterImmBook/tech/propulsion.html>`_ 中有过简短的介绍。

曲率推进的主要的理论依据是广义相对论。Alcubierre 在二十世纪末提出了相关的理论，但是由于当时技术的限制，并不能对这类引擎进行试验。[1]_

Alcubierre 类推进的主要原理是产生一个时空泡泡，然后通过移动这个时空泡泡来移动飞船。其实就是通过操控 **空间** 来从一个地方移动到另一个地方的推进技术。


.. figure:: https://upload.wikimedia.org/wikipedia/commons/c/c4/Alcubierre.png
   :align: center

   Alcubierre 推进



如果把 **空间** 看作是橡皮膜，那么 warp drive 实际上就是在通过压缩前方的空间，拉伸后方的空间来「移动」的。就是说，我们想从 A 点出发到达 B 点，实际上我们只需要把飞船前方的空间压缩一下，全部拿到飞船的后方来，不就可以到达 B 点了么。有点像是，「我不过去，山会过来」。如果我们仅仅操控空间，而不影响时间，那么就太好了，我们可以从 A 以任意 **速度** 到达 B 地点，但是总会花费一点时间，因为我们把空间这块 **橡皮膜** 压缩起来或者伸展开去总需要一定的时间吧。

这种推进有种很大的优势，那就是飞船里面的人不会察觉到飞船移动状况的改变，因为局域的来看，我们实际上根本没动。




.. [1] `The warp drive: hyper-fast travel within general relativity <http://arxiv.org/abs/gr-qc/0009013>`_ By Miguel Alcubierre.


.. admonition:: 曲率推进进阶
   :class: note

	Warp drive 可以达到很多倍的光速，而且时间膨胀效应很小，所以 warp drive 就是我们理想的载人航行器！

	Miguel Alcubierre 提出了一种神秘的度规，这种度规恰好可以帮我们实现曲率推进，该度规就被称为 Alcubierre metric.

	Alcubierre 度规是像是一个可以将飞船包裹起来的时空泡泡，泡泡内部还是正常的闵氏时空，然而这个时空泡泡却有一个时空剧烈变动的外壳。

	Einstein 的场方程的两端可以分别是物质和时空，现在要做的只是设计一个合理的度规，然后按照上面的方程解出所需要的物质的分布和特性。





	**推进器的重要参数 —— warp factor**


	在 Star Trek 中，速度一直是使用 warp N 来表示的，warp 1 表示一倍光速，其他的按照
	
	.. math::
	   v=w^3c

	来计算，其中 :math:`v` 是闵氏时空中的测量速度，:math:`c` 是光速，:math:`w` 便是 warp factor（扭曲因子，wikipedia 上翻译为「曲率层级」，我觉得不够直观）。一开始的时候，开到 warp 5 就已经不得了了呢。

	后来的剧集中，Okuda 更改了 warp factor 的定义，新的定义为 warp factor 为 1-9 时
	
	.. math::
	   v=w^{10/3}c

	而超过 9 就直接手绘了一条趋向无穷的曲线。到了 1995 年，有人给出了一个解析公式。下图是 `wikipedia 中的新旧 warp factor 的对照表以及其能量需求等等量直接的关系 <http://en.wikipedia.org/wiki/File:Warptable.gif>`_ 。

	.. figure:: http://upload.wikimedia.org/wikipedia/en/4/4b/Warptable.gif
	   :align: center

	   Warp Factor




	**Alcubierre 度规**

	Alcubierre 度规可以从 ADM 形式中猜出来，但是这个 Alcubierre 前辈已经写出来了，所以只需要把前辈的那个抄过来，
	
	.. math::
	   \mathrm ds^2 = -\mathrm dt^2+(\mathrm dx - v_s f(r_s)\mathrm dt)^2 + \mathrm dy^2 + \mathrm dz^2
	
	其中，

	.. math::
	   v_s=\mathrm dx_s/\mathrm dt

	.. math::
	   r_s=((x -x_s)^2 + y^2 + z^2)^{1/2}
	
	.. math::
	   f(r_s)=[\tanh(\sigma(r_s + R))-\tanh(\sigma(r_s - R))]/[2\tanh(\sigma R)]

	并且 :math:`\sigma>0`，:math:`R>0`。

	怎么看这个度规呢，其实我们可以把飞船看做一个点，放在 :math:`x_s` 并让飞船的轨迹沿着 x 轴，然后 :math:`r_s` 可以看做是离开飞船的距离。然后我们看一下 :math:`f(r_s)` 这个函数的渐进行为。这个函数里面的 :math:`\sigma` 这个参数是用来调节 :math:`\tanh` 函数的陡峭程度的，同时也可以调节 :math:`f(r_s)` 这个函数的陡峭程度。下面我们看一个极端情况

	.. math::
	   \lim_{\sigma\rightarrow\infty} f(r_s)=\begin{cases} 1 & r_s\in [-R, R]\\0 & \text{其他.} \end{cases}

	也就是说，这是一个帽子函数。:math:`\sigma` 越大，这个帽子就越陡，而且中心越平坦。
	实际上这保证了离飞船比较远的地方依然是闵氏时空。

	有了 metric ，你就可以依据这个 metric 来计算所需要的物质了，然后就是如何得到这种物质并且给出特定的分布。在这之前，你需要检验一下这个度规是否真的满足我们的需求，对不对？

	首先，检查一下飞船远处的时空状况。此时 :math:`r_s` 很大，度规退化成
	
	.. math::
	   \mathrm ds^2 = -\mathrm dt^2+\mathrm dx ^2 + \mathrm dy^2 + \mathrm dz^2

	恰是闵氏度规。

	这样形象的来看，飞船就是被包裹在一个「时空蛋壳」里了。那么这个飞船可以行进多快呢？答案是想多快就多快。

	因为飞船的移动完全依赖于 :math:`v_s` 的大小，我们通过调节这个参数的大小，就可以调节飞船在无穷远的人看来的「移动速度」。而且，Alcubierre 证明，这种移动没有时间上的膨胀效应，也就是说，在无穷远的人看来，如果飞船花了一天从 A 地点到达了 B 地点，那么飞船上的人也是同样这么认为的。







:index:`Krasnikov 通道`
------------------------------------------

Krasnikov 通道是一种通过对时空进行修改从而达到一次修建多次使用的技术。[2]_

通过修改时空来缩短两点之间的距离，使得时空形成一条稳定的管道，从而达到在两点之间快速移动的目的。

Krasnikov 仔细分析了管道的修建和因果关系，所以这类通道叫做 Krasnikov 通道。




.. [2] `The quantum inequalities do not forbid spacetime shortcuts <http://arxiv.org/abs/gr-qc/0207057>`_ By S. Krasnikov.



:index:`Heim 理论`
---------------------------------------

在二十世纪 B. Heim 的几何化的场论为我们提供了描述两种不同于引力、电磁力、弱相互作用、强相互作用四种力的新的相互作用，并且提供了电磁相互作用和引力的更加紧密的联系的描述。这使得我们可以通过电磁力来操控引力。[3]_

Heim 的理论中，通过在不同的能量之间相互转换，既可以将飞船移动，不消耗推进剂也可以推进飞船。




.. [3] `Physical principles of advanced space propulsion based on Heins' field theory <http://www.hpcc-space.com/publications/documents/PrinciplesOfAdvancedSpacePropulsionAIAA-paper-2002-4094.pdf>`_





:index:`Gamma-Ray Burst Propulsion`
:index:`Interstellar War`


Gamma-Ray Burst 与星际飞船和星际战争
===============================================



.. admonition:: Gamma-ray Burst，伽玛射线暴
   :class: note

   Gamma-ray burst 是现代天体物理中一个尚未解决的难题。在极短的时间天空中某点的加玛射线强度突然剧增，然后又骤减，释放巨大的能量。

   .. figure:: ./assets/ph/GRB-BATSE-2704.jpg
      :align: center

      BATSE 的 GRB 结果。可见这些爆发在宇宙中是各向同性的。图片来源 `File:BATSE 2704.jpg on Wikipedia <https://commons.wikimedia.org/wiki/File:BATSE_2704.jpg>`_ 。


   现在的理论暗示了某些类型的 GRB 可能跟 core collapse 过程有关，或许与 core collapse 超新星爆发有关。而我们也确实观测到了这样的例子：GRB 980425，红移为 :math:`z = 0.0085`，同样的方向发现的超新星爆发是 1998 bw，为 Type Ic 型。



GRB 作为星际战争中的武器
-----------------------------------

由于能量之巨大，我们可以将 GRB（伽玛暴）跟宇宙战争联系起来。然而 GRB 是各向同性的，也就是说在各个方向的 GRB 的数密度大致相同，倘若这是战争，那么就说明战争在我们周围均匀的发生着，然而这是非常难以理解的。因为 GRB 能量之巨大，用来杀害确实是效率之高，但是为了防止射线伤害到自己，需要让射线有一定的方向性。

.. admonition:: GRB 方向性
   :class: note

   而实际上我们的天体物理理论中，也是考虑 GRB 可能是带有方向性的，因为它的能量太大了，超过了超新星的所有能释放的能量，这是极难理解的。所以理论的解释是，GRB 是由高速运动的物质的 relativistic beaming effect 产生的，这种 beaming effect 可以是的能量的释放集中在物质前进的方向，而且会产生蓝移使得辐射光子的能量变高。这样正好符合 GRB 的要求：集中在某个方向释放能量，不用担心整体的能量太高（太高的话甚至超过超新星的话我们就要担心能量来源了），而且是在高能光子波段。


设想这样一个场景，帝国 A 与帝国 B 发生了星际战争，帝国 A 为了消灭帝国 B 在一个星系中的据点，便朝向那个方向发射 GRB，高能射线杀死对方绝大多数有生力量。不巧这个 GRB 的方向对准了地球，就被我们看到了。倘若战争这种事情发生非常频繁的话，在整个宇宙尺度上，从地球看来各项同性也就不是那么难以理解了。

.. admonition:: 极端古老的智慧生命
   :class: note

   在 *The highest redshift gamma-ray bursts* 一文中，可以发现有些 GRB 可以发生在非常古老的宇宙中，GRB 最古老的可以接近红移 10。[4]_ 

   那个时候产生智慧生命还要爆发战争是难以理解的。而且即使产生了，他们也要发展出跟当前相同的武器，也是难以理解的。除非，古老的文明一直延续到今天，或者虽然灭亡了但是遗迹被后来的文明发现，复制出了这种武器。

   而或许，这种武器就是让恒星坍缩而已，是很容易想到的一种威力巨大的武器。

   .. [4] `The highest redshift gamma-ray bursts <http://arxiv.org/abs/1307.6156>`_ - Tanvir, N.R. arXiv:1307.6156 [astro-ph.CO]






GRB 作为星际飞船推进器的残留
-----------------------------------



星际航行需要消耗的能量非常多，然而更加重要的是，快速的星际航行所需要的能量密度也非常大，这样的过程几乎全部都有光子辐射，如果能量密度很大，产生的会是伽玛光子。例如采用正反物质湮灭作为能源的话，要产生大量的伽马射线，而为了飞船的安全，必然要把这些有害射线导向远离飞船驾驶员的方向，而如果这个方向正好是地球的方向，那么我们就看到了。


如果要解释为外星飞船的话，Mia Molvray 在 1994 年写的这篇 `Gamma Ray Bursters: Unexplained Lights in the Sky <http://www.molvray.com/sf/grb/grblog2.htm>`_ 无疑提供了一些思路。

Mia Molvray 提到了，倘若要往一些遥远的殖民地运动物资，可以使用高速飞行的无人飞船（这样的话也无人在乎狭义相对论的时间效应，因为是无人的）。不管他们使用的是什么能源，不同的发动机有不同的特征，包括 gamma 射线能量随着时间变化的曲线、能量谱等等，会有些许差异。我们或许能够将这些飞船从其他的 GRB 中区分出来。


.. admonition:: 关于 GRB 来自星际飞船的疑问
   :class: note

   然而如果这些 GRB 中真的有些是外星飞船产生的，那么有几个问题难以解释。

   1. 如果是飞船，很可能有船坞，也就是说飞船可能会从相同的地方发射。这与我们会看到同一地点出现多次 GRB，这是没有被观测到的。[citation needed] 或许解释是，由于 GRB 的方向性，恰巧对准地球只是一个巧合，由于船坞在轨道上，会转动、移动，大多时候不会朝向地球。
   2. GRB 是漫天都是的，而且均匀分布。这个无法解释。唯一可以安慰的就是，飞船产生的只是其中非常非常少的一部分，另一些可能是自然的，可能是战争的，可能是其他的。
   3. 为什么是一个爆发，而不是持续的？这个可能的解释的或许飞船并不是完全由这种引擎推动的，或许这种引擎只是用来引发某种效应。例如可能飞船需要点燃引擎几秒钟，然后可以进入超空间了。所以我们只能观测到非常短暂的 GRB。
   4. 为什么他们不来找我们地球？这就归结到费米悖论了。不过或许，像《基地》里面的银河帝国一样，这些文明来自地球，但是由于种种原因，他们已经忘却了地球，不想回到地球，被某些谣言所恐吓，想要保存地球这种新生的文明等等。






:index:`外星生命和外星文明`
===========================



:index:`费米悖论`
------------------

.. admonition:: 相关故事
   :class: hint

   1. 黑暗森林出现在了刘慈欣的《三体》系列中。
   2. 电影《黑衣人》系列虽然略带搞笑风格，但是也是一种潜在的可能的解释：外星人就在我们身边，但是我们不知道。
   3. 电影《2001太空漫游》的说法是外星智慧跟我们想象的形式完全不同。
   
   以上是经典作品。

   1. 拙作 `《梦与新世界》 <http://multiverse.lamost.org/blog/6455>`_ 是尝试使用在银河系的旋臂外缘的文明相隔太远，谁也没法飞到对方星系这样的设定。但是这是一个费米悖论局域的解释，也就是说，这个或许只是对于我们太阳系有效，如果靠近银河系银心，恒星数密度更大了，或许大家相距更近些。
   2. 关于使用上面的理论来解释费米悖论应用到近未来科幻的一些想法：`我们将看到的地外文明 <http://www.guokr.com/blog/793766/>`_ 。


   这里部分参考了 `《科幻概念解读：费米悖论》 <http://www.guokr.com/article/283356/>`_ 这篇文章。



.. admonition:: 说明
   :class: note

   关于费米悖论，星际移民中心的 `《系外行星文档》 <http://interimm.org/exoplanets>`_ 描述过多种不同的解释。以下为摘录。

   **为了做更多的讨论，我们提出推广的费米悖论：宇宙如此之大，如果一个文明没有发现外星文明，他们或许会问为什么。这样推广之后就不再是基于地球人了，因为这个问题的具体的解释可能跟一个行星的地理位置等有关。**



我们发现了这么多的行星，可是为什么我们还没有遇到外星人呢？他们都到哪里去了？

1950年，费米问出这个问题（Whre are they?）的时候，我们并没有观测到太阳系之外的行星，在那样一个年代，这样的问题似乎并不是那么有趣。

现在我们已经确认了一千多颗系外行星，几千颗候选，而且这些数字还在继续增长。时至今日，费米的这个问题越来越重要，如果有那么多的栖居地，大家都在哪里呢？

.. admonition:: 费米悖论
   :class: note

       宇宙显著的尺度和年龄意味着高等地外文明应该存在。

       The apparent size and age of the universe suggest that many technologically advanced extraterrestrial civilizations ought to exist.

       但是，这个假设得不到充分的证据支持。

       However, this hypothesis seems inconsistent with the lack of observational evidence to support it.

       -- `费米悖论|维基百科 <http://zh.wikipedia.org/wiki/%E8%B4%B9%E7%B1%B3%E6%82%96%E8%AE%BA>`_


.. index:: Great Silence

David Brin 的 Great Silence
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


.. admonition: 评论
   :class: note

   这些比较老的研究和讨论中，大多在讨论能够通过监测外星智慧生命主动发射的通信或其他用途的电磁波探测到，或者有星际飞行能力来到地球附近从而被我们发现这样的事件。然而，随着现在科学和技术的进展，我们现在能够探测系外行星的大气层的一些细节甚至行星表面的细节，这使得我们可以讨论的探测方式由对方主动发射电磁波被我们探测到转变为我们可以直接探测系外行星上的生命的活动痕迹。而这样的探测甚至不需要智慧生命掌握电磁波通信能力，例如，我们可以直接探测可能的化石燃料燃烧的痕迹等。

   然而，这也只是在短短几年间发展起来的技术。或许，在很快的将来，我们可以看到系外行星的更多细节，那时候，也许，我们观测的外星生命，却没有能力看到我们。技术的不平等，将会给我们提供很多的契机。



Glen David Brin 在 1983 年曾经发表过一篇名为 `The Great Silence - the Controversy Concerning Extraterrestrial Intelligent Life <http://www.brin-l.com/downloads/silence.pdf>`_ 的论文。在篇论文中，David Brin 导出了一个类似用来描述在当前人类接触到 ETIS，即 Extraterrestrial Intelligent Species，的几率。


.. admonition:: Drake 方程
   :class: note

   Drake 方程是用来计算（描述）一个完整范围内（例如一个星系）存在可以被探测到的智慧文明的地点（例如行星）的数目：

   .. math::
      E = R f_g n_e f_1 f_i f_c L，

   其中各个参数的意思在下面的列表中指明。

   * :math:`R`，该完整范围内的恒星的产生率；
   * :math:`f_g`，有行星的稳定的（矮）恒星；
   * :math:`n_e`，每个恒星系中的潜在的可以利用的行星；
   * :math:`f_1`，上面提到的行星中能产生生命的比率；
   * :math:`f_i`，所有产生的生命中，演化出智能的比率；
   * :math:`f_c`，上面提到的智慧生命中制造出可以被检测到的技术的比率；
   * :math:`L`，带有这样的技术的种类的寿命。


当前（电磁波通信，低速飞船这样的技术水平）人类遇到外星智慧生命的概率（更严格的说是 likelihood）可以用下式计算，

.. math::
   C = \frac{1}{N^*}\sum_{j=1}^{E} A_j (n_j+1).

公式中的 :math:`E` 就是 Drake 方程计算出来的存在可以探测到的智慧文明的栖居点。:math:`A_j` 是第 j 种演化出来的智慧生命栖居的或者排出的机器人（例如 von Neuman robot）所占据的栖居点的数目，之所以有个 :math:`+1` 是因为我们假定这个种类的生命是在其母星上演化出来的，所以他们总共在 :math:`n_j+1` 个行星上留下了痕迹。:math:`A_j` 是这类智慧生命的“接触截面”（contact cross-section），是这类生命跟其他的生命有接触的可能性的一个参数。:math:`N^*` 是“归一化”系数，这里选用有效的恒星数目，去掉了那些不合适的恒星（例如短寿命的恒星，太过靠近的双星等等）。


David Brin 提出了 :math:`n_j` 的一个形式，

.. math::
   n_j = B f_g n_e 4 \pi \int_0^{R_j} e^{-(R_j-r)/v L'}\mathrm d r,


:math:`B` 是恒星的数密度，:math:`R_j` 是该种类的生命的扩展范围的半径，:math:`v` 是他们的扩展速度（与他们的飞船的速度、繁殖速度等有关），:math:`L'` 是每个栖居点上面的寿命（与 :math:`L` 有关）。


这样总结下来，我们关心的量 C，即当前人类遇到外星智慧生命的 likelihood 与这些的参数相关：:math:`f_g`、:math:`n_e`、:math:`f_1`、:math:`f_c`、:math:`f_i`、:math:`L`、:math:`A`. 要解决这个问题，就要分别讨论这些量。



.. admonition:: 关于为什么我们接触不到外星智慧生命
   :class: note

   有很多关于这个问题的讨论。下面从 David Brin 的论文中节选一些列举出来。

   1. 外星智慧生命可能故意躲开我们这样的低级的智能或技术。毕竟相遇之后我们大多在获取新的信息，而不能提供给他们新的信息。
   2. 由于电磁波很容易被检测到，所以智慧生命可能会使用 `Bracewell probe <https://en.wikipedia.org/wiki/Bracewell_probe>`_ 来传递信息，从而减少电磁波的使用和泄露，而且他们也会很注意少使用用来扩展殖民地的机器人（可能会叛变失去控制）。
   3. 因为我们的探测方式不对。
   4. 外星智慧生命故意隔离我们。可能的原因例如，把我们太阳系当作一个大型的野生动物园来看待（Ball, John A., 1973. Icarus, 19, 347），想要让地球独立发展以期待新的类型的事物出现（Kuiper, T.B.H. & Morris, M., 1977. Science, 196, 616）。也可能是等待地球上的社会发展成熟，或者觉得地球上人类太过危险（获得与社会发展以及人类心智不相匹配的科技之后）。
   5. Macrolife：摒弃了在行星上生活的方式。例如建造大型飞船游走在太空中，甚至拆解行星作为自己的飞船的原料。例如小说 Macrolife.
   6. 某些种类可能害怕太空，在行星上极力发展其他的技术并达到了出神入化的程度，但是依然没有离开自己的行星。例如虽然有过一个短暂的扩展时期，但是很快就蜗居在自己的母星上不出门了。
   7. 地球并不是他们想要的地方或者地球无法接近。例如这些智慧生命依靠某种类似虫洞的技术来快速穿越在不同的地方，但是由于某些原因，这类技术不能在地球附近建造，从而与地球没有接触。






.. admonition:: 小知识：星系围绕银河系中心的公转
   :class: note

   由于公转的角速度不一样，所以径向方向的邻居会变化。







.. index:: 黑暗森林

刘慈欣的黑暗森林
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~




:index:`Randall Munroe (xkcd) 的 Fish`
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


.. figure:: http://imgs.xkcd.com/comics/fish.png
   :align: center
   :alt: Randall Munroe's Fish

   Randall Munroe 的 `1377号 <http://xkcd.com/1377/>`_ 漫画。


.. index:: 智慧扩张模型

Bezsudnov 和 Snarskii 的智慧扩张模型
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~



他们的论文在这里：`Where is everybody? -- Wait a moment ... New approach to the Fermi paradox <http://arxiv.org/abs/1007.2774>`_ .


果壳网有一篇相关的科普文：`为什么我们还没遇到外星人？ <http://www.guokr.com/article/129942/>`_ 。

















