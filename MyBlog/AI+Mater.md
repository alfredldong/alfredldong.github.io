**Nature Com.: 深度神经网络准确预测材料结构稳定性**

Ye, W., et al. (2018). "Deep neural networks for accurate predictions of crystal stability." Nat Commun 9(1): 3800.

https://doi.org/10.1038/s41467-018-06322-x

预测材料结构稳定性是材料科学核心问题之一。传统预测稳定性的方法是通过第一性原理计算。然而随着晶体原子数和结构复杂度的增加，这样的计算会变得十分昂贵。近年来，机器学习因其能从已知数据中分析规律，并对未知数据进行预测的能力而备受瞩目。
 
加州大学圣地亚哥分校Shyue Ping Ong教授课题组利用机器学习中的神经网络模型，实现了准确预测晶体材料的形成能。以$\rm C_3A_2D_3O_{12}$石榴石和$\rm ABO_3$钙钛矿为示例，其预测误差分别在7-10 meV/atom和20-34 meV/atom之内。
 
![](https://media.springernature.com/lw900/springer-static/image/art%3A10.1038%2Fs41467-018-06322-x/MediaObjects/41467_2018_6322_Fig1_HTML.png)

图1：$\rm C_3A_2D_3O_{12}$石榴石和$\rm ABO_3$钙钛矿晶体结构。
 
采用机器学习来预测材料结构能量近年来十分热门，然而大多数工作的预测误差都在70-100 meV/atom，使得其很难用于有效预测材料的稳定性。来自加州大学圣地亚哥分校的Shyue Ping Ong课题组认为，较高的误差可能来自于对特征向量，学习目标以及算法的不当选择。该课题组研究人员从Pauling规则和Goldschmidt半径规则中汲取灵感，选择了晶体中占据每个Wycoff位置原子的电负性和离子半径作为晶体的特征元素，进行模型优化。同时，他们重新定义了以二元化合物为参照物的形成能作为模型学习目标。在算法方面，研究人员在确定了特征向量和学习目标之间为复杂非线性关系之后，合理选择了可以模拟任意复杂度非线性方程的神经网络模型（图2）。

![](https://media.springernature.com/m685/springer-static/image/art%3A10.1038%2Fs41467-018-06322-x/MediaObjects/41467_2018_6322_Fig2_HTML.png)
 
图2：神经网络结构
 
基于以上设定，针对635个unmix（各wycoff 位置为单一元素占据）石榴石，研究人员实现了 7-10 meV/atom的预测误差（图3），远低于现有模型 （误差约100meV/atom）。在加入了772个mix（其中一个Wycoff位置以特定比例为两种元素占据）石榴石结构后，研究人员引入了新颖的二进制独热编码，以增加最少特征元素为原则，编码对应mix化学式的穷举得到的结构，得到的误差也与unmix模型接近（图3）。

![](https://media.springernature.com/m685/springer-static/image/art%3A10.1038%2Fs41467-018-06322-x/MediaObjects/41467_2018_6322_Fig3_HTML.png)
 
图3：神经网络模型预测$\rm C_3A_2D_3O_{12}$石榴石和$\rm ABO_3$钙钛矿形成能

 
基于对形成能的准确预测，研究人员进一步用预测的形成能计算出Ehull, 并作为判断结构是否稳定的判据。从图4可以看出，在严格选择Ehull = 0 为稳定相的判据时，用最优化的模型对各种石榴石结构稳定性的预测准确率均在90%以上。 在穷举的8427个混合石榴石化学式中，基于Ehull预测得到2307个潜在的稳定结构。
 
为证明该方法的普适性，研究人员用包含240个unmix和302个mix钙钛矿数据集，用相同的方式训练了三个模型。模型对于unmix和整体数据集的预测误差都在21-39 meV/atom内（图3）。类似的，基于Ehull=0为判据预测稳定相的准确率达到了80%以上。

![](https://media.springernature.com/m685/springer-static/image/art%3A10.1038%2Fs41467-018-06322-x/MediaObjects/41467_2018_6322_Fig4_HTML.png)
 
图4：基于Ehull预测晶体稳定性准确率
 
该工作实现了机器学习预测材料稳定性的高准确度，可实现取代高通量第一性原理计算的目标，大大加速新材料的发现。更重要的是，该方法指出了在应用机器学习解决化学问题时，应理性选择晶体特征向量，善用领域知识，以得到最紧凑、有效的晶体结构特征表达，避免得到包含多达几十甚至几百参数的臃肿特征向量。其次，对于学习目标的选择，也应妥善考虑目标值域，并加以变通。另一方面，该方法提出了对于含有混合占有率的无序结构进行特征编码的新颖方法，使得对该类结构的预测保持与有序结构接近的误差水平。这大大扩展了模型的可预测化学空间，极大提高了预测新材料的效率。最后，虽然文章只用了两种石榴石和钙钛矿结构所谓演示，但理论上该方法可适用于任意结构模型。

**苏大尹万健Adv. Funct. Mater. : 高通量计算和机器学习研究卤化物双钙钛矿的热力学稳定性**

Thermodynamic Stability Landscape of Halide Double Perovskites via High-Throughput Computing and Machine Learning (Adv. Funct. Mater., 2019, DOI: 10.1002/adfm.201807280)

https://doi.org/10.1002/adfm.201807280.

【引言】

以CH3NH3PbI3为代表的卤化物钙钛矿在潮湿、空气、高温和光下易分解，导致电池性能快速降低，这一点反映于其几乎为零的分解能中。为解决稳定性问题，研究人员采用双重钙钛矿和混合钙钛矿两种策略以设计出新颖稳定的钙钛矿。以A2B(I)B(III)X6表示的卤化物双钙钛矿可认为是单价B(I)和三价B(III)阳离子取代了AB(II)X3中的二价B阳离子，提供了许多(最多≈104)钙钛矿候选物。此外，基于密度泛函理论(DFT)的第一性原理计算已成为筛选稳定的卤化钙钛矿的有用工具。到目前为止，实验和理论研究只研究了大约102种类型的化合物，远远少于可能的候选化合物数量(≈104)。因此，需要高通量快速筛选方法来加速新稳定钙钛矿的发现。除元素替代外，ABX3钙钛矿的成分合金化还产生了大量复合钙钛矿，与其单一的钙钛矿对应物相比，表现出增强的稳定性。因此，需要进一步了解元素混合的影响并为稳定性调控提供指导，特别是在混合元素的类型及其浓度选择的方面提供有意义的指导。

【成果简介】

近日，苏州大学尹万健教授(通讯作者)等通过高通量密度泛函理论(DFT)计算，建立了一个包含与354个卤化钙钛矿候选物热力学稳定性密切相关的分解能数据库，并在Adv. Funct. Mater.上发表了题为“Thermodynamic Stability Landscape of Halide Double Perovskites via High-Throughput Computing and Machine Learning”的研究论文。为对应结构和化学特征与分解能之间的基本关系，作者基于上述理论数据库训练了一个功能良好的机器学习(ML)模型，并通过钙钛矿可成形性(F1分数，95.9 %)的实验观察进一步验证不存在于训练数据库中的246种A2B(I)B(III)X6化合物；该模型比经验描述符[如容忍因子t (F1分数，77.5%)]表现更好。该工作表明筛选稳定钙钛矿可依赖于从高通量DFT计算得到的训练数据，比材料合成的实验尝试更加经济和有效。该工作与日本国立材料研究所侯柱锋博士合作完成，第一作者为李珍珠博士，参与人包括孙庆德博士以及徐其琛硕士。

【图文简介】

![](https://wol-prod-cdn.literatumonline.com/cms/attachment/8c0dbd9b-6c8e-4d94-80b7-eaeb99ed05e8/adfm201807280-fig-0001-m.jpg)

图1 基于DFT的ML原理及其用于卤化钙钛矿稳定性高通量筛选示意图
 
通过DFT计算354种钙钛矿的分解能(ΔHD)，然后将其作为ML模型的数据集，与半经验描述符的性能相比，预测14190种卤化双钙钛矿的稳定性，绘制混合钙钛矿稳定性的元素和组成图集。

![](https://wol-prod-cdn.literatumonline.com/cms/attachment/886ef1e4-6051-4ecd-b5d4-9deab8baaff9/adfm201807280-fig-0002-m.jpg)

图2 半经验描述符与ML的拟合情况比较
 
A) DFT计算与描述符-t-预测当前研究的354种钙钛矿ΔHD的相关性；

B) DFT计算与描述符-(μ+ t)η-预测当前研究的354种钙钛矿ΔHD的相关性；

C) DFT计算与基于(RA，RB,eff和RX)的特征ML预测当前研究的354种钙钛矿ΔHD的相关性，图中的红/蓝点表示ML方法中的验证(71数据集)和训练(283数据集)数据(下同)；

D) DFT计算与基于(RA，RB1，RB2，RX)的特征ML预测当前研究的354种钙钛矿ΔHD的相关性。

![](https://wol-prod-cdn.literatumonline.com/cms/attachment/6f16b11c-2234-41e1-93c6-f8056eb39e85/adfm201807280-fig-0003-m.jpg)

图3 DFT计算和ML预测的74种随机选择的钙钛矿分解能比较
 
DFT计算和ML预测的74种随机选择的钙钛矿分解能比较，黑点是A2B(I)B(III)X6(A =碱金属元素)。

![](https://wol-prod-cdn.literatumonline.com/cms/attachment/e018785d-f49a-4864-bd72-bf605e398a4a/adfm201807280-fig-0004-m.jpg)

图4 稀土元素相关卤化物双钙钛矿的可合成性、ML预测的分解能以及描述符t预测的比较
 
A) 稀土元素相关卤化物双钙钛矿的可合成性；

B) 稀土元素相关卤化物双钙钛矿的ML预测的分解能；

C) 稀土元素相关卤化物双钙钛矿的描述符t预测。

![](https://wol-prod-cdn.literatumonline.com/cms/attachment/8c59869e-ef72-4fce-b1e2-b1ceb540f472/adfm201807280-fig-0005-m.jpg)

图5 ML预测的混合钙钛矿分解能
 
A) ML预测的混合钙钛矿ABI3的分解能，x/y轴是A/B的离子半径；

B) ML预测的混合钙钛矿APbX3的分解能，x/y轴是A/X的离子半径。

【小结】

综上所述，作者提出了一种结合ML和第一性原理DFT计算的策略来设计稳定的卤化物钙钛矿。作者选择354种钙钛矿的DFT结果作为训练集，建立了钙钛矿稳定性和组成离子半径之间的ML映射，其表现出比持久容忍因子t和最近提出的(μ+ t)η描述符更好的性能。 通过与不在354种DFT计算范围内的246种钙钛矿实验可成形性进行比较，验证了该ML模型。ML模型预测的稳定性趋势与现有的实验数据非常一致，表明当前ML模型的普适化潜力。ML模型还用于绘制混合钙钛矿的整体稳定性图集，并合理化该领域的各种实验结果。该工作表明，基于DFT计算数据的ML方法可为调控合成稳定的钙钛矿提供指导。

团队在该领域近期工作

1. Qingde Sun, Wan-Jian Yin*. Thermodynamic stability trend of cubic perovskites. J. Am. Chem. Soc., 139, 14905, 2017.
2. Qingde Sun, Jiang Wang, Wan-Jian Yin*, Yanfa Yan*. Bandgap Engineering of Stable Lead-Free Oxide Double Perovskites for Photovoltaics. Adv. Mater., 2018, 1705901.
3. Qichen Xu, Zhenzhu Li, Wan-Jian Yin*. Rationalizing perovskite data for machine learning and materials design. J. Phys. Chem. Lett., 2018, 9, 6948-6954. (进行准确机器学习的先决条件：构建可靠的钙钛矿材料数据库)
4. Fazel Shojaei, Wan-Jian Yin*. Stability trend of tilted perovskites. J. Phys. Chem. C., 2018, 122, 15214-15219.
5. Zhengbao Huo, Su-Huai Wei, Wan-Jian Yin. High-throughput screening of chalcogenide single perovskites by first-principles calculations for photovoltaics. J. Phys. D.: Appl. Phys.,2018, 51, 474003.
6. Wan-Jian Yin, Baicheng Weng, Jie Ge, Qingde Sun, Zhenzhu Li, Yanfa Yan*. Oxide perovskites, double perovskites and derivatives for electrocatalysis, photocatalysis, and photovoltaics. Energy Environ. Sci., 2019,  DOI:10.1039/C8EE01574K.
7. Qingde Sun, Hangyan Chen, Wan-Jian Yin*. Do chalcogenide double perovskites work as solar cell absorbers: A first-principles study. Chem. Mater.,2019, 31, 244-250.


**斯坦福张首晟：机器学习助力新材料发现！**
 
Zhou Q, Tang P, Liu S, et al. Learning atoms for materials discovery[J]. Proceedings of the National Academy of Sciences, 2018: 201801181.
DOI: 10.1073/pnas.1801181115

https://doi.org/10.1073/pnas.1801181115
 
研究亮点:

1. 提出Atom2Vec，机器可以从已知化合物和材料的庞大数据库中自己学习原子的基本属性。 
2. 使用原子向量作为神经网络和其他机器学习模型的基本输入单元，这些模型被设计和训练以预测材料属性，展示了显著的准确性。
 
在过去的20年中，通过实验探索和数值模拟，在材料科学中积累了前所未有的大量数据。庞大的数据集还需要基于数据的统计方法来实现。因此，出现了一种新的范例，旨在利用人工智能（AI）和机器学习（ML）技术来辅助材料的研究和发现。
 
尽管到目前为止取得了成功，但这些工作在很大程度上依赖于研究人员明智地选择相关描述，因此，从理论的角度来看，智力程度仍然非常有限。实际上对于机器来说，额外的计算通常是不可避免的，以解释和理解这些以抽象的人类知识形式存在的原子描述符号。
 
有鉴于此，斯坦福大学的Shou-Cheng Zhang教授为了创建更高级别的AI并克服实际限制，提出了Atom2Vec，它允许机器从数据中学习他们自己的原子知识。

![](https://www.pnas.org/content/pnas/115/28/E6411/F1.large.jpg?width=800&height=600&carousel=1)

图1. Atom2Vec从材料数据库中学习原子的工作流程
 
Atom2Vec仅考虑材料数据库中化合物的存在，而不考虑材料的任何特定属性。这个庞大的数据集以无人监督的方式用于材料科学的学习。由于缺少材料属性标签，Atom2Vec不会偏向于某个方面。因此，只要数据集足够大且具有代表性，所学习的知识原则上可以产生原子完整和通用的描述。
 
Atom2Vec遵循核心思想，即原子的属性可以从它所处的环境中推断出来，这类似于语言学中的分布假设。在化合物中，每个原子可以被选择作为目标类型，而环境是指所有剩余的原子以及它们相对于目标原子的位置。直观地说，类似的原子倾向于出现在相似的环境中，这使我们的Atom2Vec能够从原子和环境之间的关联中提取知识，然后以矢量形式表示它。
 
所学习的特征向量不仅很好地捕捉了向量空间中原子的相似性和性质，而且在用于材料科学的ML问题时也显示出它们优于简单经验描述符的优越性。预计其有效性和广泛的适用性可以极大地推动当今材料科学中的数据驱动方法，特别是对于最近提出的深度神经网络方法。
 
这里有关于特征学习方法的几个方向值得在将来探讨。例如，元素-环境矩阵可以推广到更高阶的张量，其中额外的阶数描绘了组合的不同部分。这样的张量应该包含比矩阵更精细的信息，如何从这个高阶对象中提取特征仍然是一个悬而未决的问题。
 
此外，更加合理的环境描述对于改进无模型和基于模型的方法都是必要的。必须考虑结构信息，以准确地模拟原子如何结合在一起形成环境或化合物，其中对在递归和基于图形的神经网络上的发展可能有所帮助。

![](https://www.pnas.org/content/pnas/115/28/E6411/F2.large.jpg?width=800&height=600&carousel=1)
 
图2. 通过无模型方法学习主要元素的原子向量

![](https://www.pnas.org/content/pnas/115/28/E6411/F3.large.jpg?width=800&height=600&carousel=1)
 
图3. 对预测ABC2D6形成能量的主要元素原子向量评估
 
![](https://www.pnas.org/content/pnas/115/28/E6411/F4.large.jpg?width=800&height=600&carousel=1)

图4通过无模型方法和评估半赫斯勒化合物中学习主要群体之外的官能团和元素的原子向量
 
总之，该研究从已知现有材料的数据库中引入无监督的原子学习，并通过AI重新发现周期表。研究中的ML模型被设计和训练以预测材料属性，展示了显著的准确性。

**npj: 机器学习—热电材料的回过与预测**

Miller, S. A., et al. (2018). "Empirical modeling of dopability in diamond-like semiconductors." npj Computational Materials 4(1).

https://doi.org/10.1038/s41524-018-0123-6

载流子浓度的优化一直是新型半导体开发应用中（应用于诸如热电、透明导体和光伏等）的重要挑战。这个瓶颈在高通量的材料性能预测中尤其严重，由于计算量巨大，载流子浓度通常只能被假定为自由参数，其掺杂极限无法预测。

来自美国西北大学、科罗拉多矿业学院和美国国家可再生能源实验室的研究团队，探索了机器学习在载流子浓度预测方面的应用。他们将类金刚石半导体材料体系中127种化合物的载流子浓度的实验极限值用作机器学习数据集，采用多种统计和机器学习方法对数据进行分析，进而准确预测了类金刚石半导体材料的掺杂性能。其预测精度，不论对于p型还是n型，与实验值偏差都在一个数量级以内。最后他们通过将掺杂性能预测与高通量的品质因子预测相结合，预测出了一些新型的热电材料，这些材料值得后续实验研究关注。

![](https://media.springernature.com/m685/springer-static/image/art%3A10.1038%2Fs41524-018-0123-6/MediaObjects/41524_2018_123_Fig1_HTML.png)

![](https://media.springernature.com/m685/springer-static/image/art%3A10.1038%2Fs41524-018-0123-6/MediaObjects/41524_2018_123_Fig5_HTML.png)

**npj: 机器学习—快速精确预测电子结构问题**

Chandrasekaran, A., et al. (2019). "Solving the electronic structure problem with machine learning." npj Computational Materials 5(1).
	
https://doi.org/10.1038/s41524-019-0162-7

基于求解密度泛函理论（DFT）Kohn-Sham（KS）方程的模拟，已成为现代材料学和化学研究和开发组合过程的重要组成部分。尽管KS方程具有很强的普适性，但由于求解计算量很大，常规DFT计算一般只限于几百个原子。

来自佐治亚理工学院的Rampi Ramprasad领导的团队，报道了一种基于机器学习的方法，可以不直接求解KS方程而有效预测电子结构。该方法利用新的旋转不变表示，将格点周围的原子环境映射到该格点处的电子密度和局部态密度，并使用预先计算得到的带有几百万的格点信息的DFT结果来训练的神经网络来获得该映射。上述方法可以精确模拟实际求解KS方程的结果，但是速度快几个数量级。此外，由于该方法的计算量与系统尺寸严格成线性关系，因而有望用于大型体系的电子结构预测。

![](https://media.springernature.com/lw900/springer-static/image/art%3A10.1038%2Fs41524-019-0162-7/MediaObjects/41524_2019_162_Fig1_HTML.png)

![](https://media.springernature.com/lw900/springer-static/image/art%3A10.1038%2Fs41524-019-0162-7/MediaObjects/41524_2019_162_Fig2_HTML.png)

![](https://media.springernature.com/lw900/springer-static/image/art%3A10.1038%2Fs41524-019-0162-7/MediaObjects/41524_2019_162_Fig3_HTML.png)

![](https://media.springernature.com/lw900/springer-static/image/art%3A10.1038%2Fs41524-019-0162-7/MediaObjects/41524_2019_162_Fig4_HTML.png)

![](https://media.springernature.com/lw900/springer-static/image/art%3A10.1038%2Fs41524-019-0162-7/MediaObjects/41524_2019_162_Fig5_HTML.png)

**npj: 预测材料性质—大规模蒙特卡洛模拟**

蒙特卡洛方法是现代计算物理学中最早、应用最广泛的算法之一。在凝聚态物理中，这种技术最受欢迎的是Metropolis蒙卡方法。虽然Metropolis抽样方法具有很强的鲁棒性和可操作性，但它并不适用于能量和力的计算。

为了寻找一种更有效的计算方法，来自美国阿肯色大学的Laurent Bellaiche团队，在有限温度下，对具有长程相互作用的固态系统（如铁电、弛豫铁电体和多铁材料）的有效哈密顿模型进行了杂化蒙特卡洛（HMC）采样。他们探索了杂化蒙特卡罗采样方法（一种广泛用于量子电动力学的算法）在长程相互作用系统的结构预测方案方面的能力。他们的研究结果表明，在选定的模型案例中，HMC方案明显优于Metropolis蒙卡算法（MMC）和热分子动力学（MD），而且可以弥补材料科学应用中的MD。通过对面向GPU的并行化架构实现的HMC算法，可以对粒子数达到106 的体系进行大规模的HMC仿真。该算法也可用于大规模密度泛函理论计算，从而开辟更广阔的应用空间。

![](https://media.springernature.com/m685/springer-static/image/art%3A10.1038%2Fs41524-018-0137-0/MediaObjects/41524_2018_137_Fig5_HTML.png)
 
![](https://media.springernature.com/m685/springer-static/image/art%3A10.1038%2Fs41524-018-0137-0/MediaObjects/41524_2018_137_Fig6_HTML.png)

**npj: 人工智能—4D显微图像的多维学习**

Li, X., et al. (2019). "Manifold learning of four-dimensional scanning transmission electron microscopy." npj Computational Materials 5(1).
	
https://doi.org/10.1038/s41524-018-0139-y

显示局部原子衍射图的四维扫描透射电子显微镜（4D-STEM）正在成为探测原子结构和原子电场复杂细节的有力技术。然而，大量数据的有效处理和解释仍然具有挑战性，特别是对于二维或轻质材料，其记录在像素化阵列上的衍射信号很弱。

由美国橡树岭国家实验室的Sergei V. Kalinin（本刊副主编）领导的国际团队，使用计算机协议进行数据分析（他们将该方法称为多维学习，manifoold learning），通过电子束照射石墨烯的超薄层来收集大量图像中的周期性特征，然后由计算机自动将这些特征与原子相对位置有关的信息链接。稍具体来说，他们采用数据驱动的多维学习方法，对4D-STEM数据集进行直观的可视化和探索分析，从像素化探测器上记录的具有单一掺杂原子的单层石墨烯中，提取原子分辨偏转模式的实空间相邻效应。这些提取的图案涉及单个原子位置和子晶格结构，可通过多模式视图有效地区分单个掺杂剂的异常。这样，该技术不仅可用于识别可能引起异常光电或磁性能的材料局部结构变化，而且可用来探索生成这些图像的实验条件如何进一步改善，以从高分辨显微技术中获得最多信息。他们认为，采用多维学习分析法将加速物理学新发现，这些新的发现将会把铁电、拓扑自旋和范德华异质结等材料与数据丰富的成像机制联系起来。

![](https://media.springernature.com/m685/springer-static/image/art%3A10.1038%2Fs41524-018-0139-y/MediaObjects/41524_2018_139_Fig1_HTML.png)

![](https://media.springernature.com/m685/springer-static/image/art%3A10.1038%2Fs41524-018-0139-y/MediaObjects/41524_2018_139_Fig3_HTML.png)

**npj: 神经网络——细探晶体**

Vasudevan, R. K., et al. (2018). "Mapping mesoscopic phase evolution during E-beam induced transformations via deep learning of atomically resolved images." npj Computational Materials 4(1).
	
https://doi.org/10.1038/s41524-018-0086-7

相形成和演化是固体化学、物理学、电化学和材料科学的关键过程之一，具有基础重要性，但目前尚没有在原子尺度上探索其机制。
近年来，（扫描）透射电子显微镜（（S）TEM）的进步使得人们能够在多个固态过程中观察到原子动力学对电子束辐射的响应。之前，要了解电子束照射下的相转换需要实时绘制结构相及其演变，需要靠手动尝试逐帧分析，不仅困难重重，还耗时费力、单调乏味、极易出错。美国橡树岭国家实验室的Rama Vasudevan等，受计算机视觉启发，猜测神经网络可能有所助益。他们采用深层卷积神经网络（DCNN）计算，自动确定在原子分辨图像中存在的布拉维晶格对称性。在给定输入图像的2D快速傅立叶变换情况下，对DCNN进行训练，识别出布拉维晶格类别；另外采用蒙特卡洛分析来确定预测概率和统计偏差，以展示（S）TEM的模拟图像和真实原子分辨图像的比较结果，他们发现该网络正确而快速地预测了晶格。然后，他们将训练好的网络应用于研究电子轰击下的WS2结构，发现在此过程中其菱形结构消失，与实际观察的数据一致。可见，这种神经网络有可能是分析实时电子显微镜数据用于材料优化和设计的强大工具。

![](https://media.springernature.com/m685/springer-static/image/art%3A10.1038%2Fs41524-018-0086-7/MediaObjects/41524_2018_86_Fig1_HTML.png)
