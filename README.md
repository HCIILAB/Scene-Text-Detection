# Scene Text Detection
<!-- TOC depthFrom:1 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->
The English version is coming soon.
- [Scene Text Detection](#scene-text-detection)
	- [一.场景文本检测综述](#一场景文本检测综述)
	- [二.场景文本检测常用数据集](#二场景文本检测常用数据集)
	- [三.场景文本检测技术和结果汇总](#三场景文本检测技术和结果汇总)
	- [四.参考文献](#四参考文献)

<!-- /TOC -->
## 一.场景文本检测综述

场景文本检测是计算机视觉领域的一个基础任务，它的目的是定位自然场景中文本的具体位置，它在现实生活中有着广泛的应用，例如车牌检测、场景理解和自动驾驶等。传统的场景文本检测方法通常是基于文本区域的一些特定特征如颜色、边缘、纹理还有笔划等，使用MSER, SWT等传统方法检测自然场景中的文本。2014年以来，随着深度学习的发展，通用目标检测取得了突破性的进展，自然场景中的文本也可以视为通用目标的一类，但由于文本形状和分布的多样性，使得场景文本检测不是一个简单的通用目标检测任务。近年来，通过借鉴基于深度学习的通用目标检测方法和思想，设计出了许多适合文本检测的全新网络架构。目前的方法可以大体上分为三类，基于component、基于pixel还有基于bounding boxes。


## 二.场景文本检测常用数据集

**[1]USTB-SV1K**: 本数据集是英文街景数据集，基于单词级别标注，标注方式是任意四边形标注。[Link](http://prir.ustb.edu.cn/TexStar/MOMV-text-detection/)

**[2]SVT**:本数据集包含许多街景图片，图片特性变化多，且分辨率低，标注方式是任意四边形标注。[Link](http://www.iapr-tc11.org/mediawiki/index.php/The_Street_View_Text_Dataset)

**[3]ICDAR2011**: 本数据集是基于ICDAR2005扩充而成的，标注级别达到了character level，但数据集的规模不大。标注方式是水平矩形标注。[Link](http://www.cvc.uab.es/icdar2011competition/?com=downloads)

**[4]ICDAR2013**: 本数据集是与ICDAR 2011的场景文本集几乎一样，是ICDAR 2011的子集，但标注级别到达了pixel-level，标注质量有所提升，标注方式是水平矩形标注。[Link](http://rrc.cvc.uab.es/?ch=2)

**[5]ICDAR2015**: 本数据集是与ICDAR 2015首次提出的incidental英文场景文本集，意思是没有经过于预先准备好的拍摄，是随机拍摄的画面，意味着文本的透视效应更剧烈，其位置和视角是无约束的，检测难度大很多，标注级别只到达了word-level。[Link](http://rrc.cvc.uab.es/?ch=4)

**[6]MSRA-TD500**: 本数据集MSRA-TD500的图片分辨率比较高，从1296x864到1920x1080，其主要特点是具有复杂的背景，背景中还有植物和窗户等干扰性强的物体。基于文本行级别标注。[Link](http://pages.ucsd.edu/~ztu/Download_front.htm)

**[7]COCO-Text**: 本数据集基于MS COCO数据集制作而成，是英文数据集，标注方式是水平矩形标注。[Link](https://vision.cornell.edu/se3/coco-text-2/)

**[8]RCTW-17**: 本数据集是大规模中文街景数据集，基于文本行级别标注，标注方式是任意四边形标注。[Link](http://rctw.vlrlab.net/dataset/)

**[9]Total-Text**: 本数据集是英文数据集，基于单词级别标注，标注方式是任意四边形和曲线多边形标注。[Link](https://github.com/cs-chan/Total-Text-Dataset)

**[10]SCUT-CTW1500**: 本数据集包含中文和英文两个语种，有大量的曲线文本，基于单词级别进行标注。[Link](https://github.com/Yuliang-Liu/Curve-Text-Detector)

**[11]MLT**: 本数据集包含9个语种，基于单词级别标注，标注方式是任意四边形。[Link](http://rrc.cvc.uab.es/?ch=8)

**[12]OSTD**: 本数据集是英文数据集，基于文本行级别标注，标注方式是任意四边形标注。[Link](http://media-lab.ccny.cuny.edu/wordpress/cyi/project_scenetextdetection.html)

**[13]CTW**: 本数据集是大规模中文街景数据集，基于单词级别标注，标注方式是任意四边形标注。[Link](https://ctwdataset.github.io/)

**[14]MLT2019**: 本数据集包含1w张自然场景训练图片，一共有10个语种，每个语种1000张图片，基于单词级别标注，标注方式是任意四边形标注。[Link](http://rrc.cvc.uab.es/?ch=15)

**[15]ReCTS**: 本数据集是大规模中文街景商标数据集，基于中文单词和中文文本行级别标注，标注方式是任意四边形标注。[Link](http://rrc.cvc.uab.es/?ch=12)

**[16]LSVT**: 本数据集包含2w张完全标注好的训练图片和40w张弱标注的训练图片，基于单词和文本行级别标注，标注方式是任意四边形和任意多边形标注。[Link](http://rrc.cvc.uab.es/?ch=16)

## 三.场景文本检测技术和结果汇总

<table cellspacing="0" border="0">
	<colgroup width="123"></colgroup>
	<colgroup width="119"></colgroup>
	<colgroup span="62" width="85"></colgroup>
	<tr>
		<td rowspan=2 height="34" align="center" valign=middle sdnum="2052;0;@"><font face="Arial">Prediction Unit</font></td>
		<td rowspan=2 align="center" valign=middle sdnum="2052;0;@"><font face="Arial">Method</font></td>
		<td rowspan=2 align="center" valign=middle sdnum="2052;0;@"><font face="Arial">Model</font></td>
		<td colspan=13 rowspan=2 align="center" valign=middle sdnum="2052;0;@"><font face="Arial">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Abstract&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;</font></td>
		<td colspan=3 align="center" valign=middle sdnum="2052;0;@"><font face="Arial">Application</font></td>
		<td rowspan=2 align="center" valign=middle sdnum="2052;0;@"><font face="Arial">Category</font></td>
		<td colspan=3 align="center" valign=middle sdnum="2052;0;@"><font face="Arial">USTB-SV1K [65]</font></td>
		<td colspan=3 align="center" valign=middle sdnum="2052;0;@"><font face="Arial">SVT [66]</font></td>
		<td colspan=3 align="center" valign=middle sdnum="2052;0;@"><font face="Arial">IC05[67]</font></td>
		<td colspan=3 align="center" valign=middle sdnum="2052;0;@"><font face="Arial">IC11[68]</font></td>
		<td colspan=3 align="center" valign=middle sdnum="2052;0;@"><font face="Arial">IC13 [69]</font></td>
		<td colspan=3 align="center" valign=middle sdnum="2052;0;@"><font face="Arial">IC15 [70]</font></td>
		<td colspan=3 align="center" valign=middle sdnum="2052;0;@"><font face="Arial">MSRA-TD500 [71]</font></td>
		<td colspan=3 align="center" valign=middle sdnum="2052;0;@"><font face="Arial">COCO-Text [72]</font></td>
		<td colspan=3 align="center" valign=middle sdnum="2052;0;@"><font face="Arial">RCTW-17 [73]</font></td>
		<td colspan=3 align="center" valign=middle sdnum="2052;0;@"><font face="Arial">Total-text [74]</font></td>
		<td colspan=3 align="center" valign=middle sdnum="2052;0;@"><font face="Arial">SCUT-CTW1500 [75]</font></td>
		<td colspan=3 align="center" valign=middle sdnum="2052;0;@"><font face="Arial">MLT [76]</font></td>
		<td colspan=3 align="center" valign=middle sdnum="2052;0;@"><font face="Arial">OSTD[77]</font></td>
		<td colspan=3 align="center" valign=middle sdnum="2052;0;@"><font face="Arial">CTW [78]</font></td>
		<td rowspan=2 align="center" valign=middle sdnum="2052;0;@"><font face="Arial">Time</font></td>
		<td rowspan=2 align="center" valign=middle sdnum="2052;0;@"><font face="Arial">Source</font></td>
	</tr>
	<tr>
		<td align="center" valign=middle sdnum="2052;0;@"><font face="Arial">Horizontal text</font></td>
		<td align="center" valign=middle sdnum="2052;0;@"><font face="Arial">Multi-oriented text</font></td>
		<td align="center" valign=middle sdnum="2052;0;@"><font face="Arial">curved text</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">P</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">R</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">F</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">P</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">R</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">F</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">P</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">R</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">F</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">P</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">R</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">F</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">P</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">R</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">F</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">P</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">R</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">F</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">P</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">R</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">F</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">P</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">R</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">F</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">P</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">R</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">F</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">P</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">R</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">F</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">P</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">R</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">F</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">P</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">R</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">F</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">P</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">R</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">F</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">P</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">R</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">F</font></td>
		</tr>
	<tr>
		<td rowspan=17 height="302" align="center" valign=middle sdnum="2052;0;@"><font face="Arial">Component-level</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Yao et al. [1]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TD-Mixture</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">The algorithm is equipped with a two-level classification scheme and two sets of features specially designed for capturing both the intrinsic characteristics of texts. And it proposed a new scene text datasets and a protocol for evaluation.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">传统方法</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.69</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.66</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.67</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2012</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Yin et al. [2]</font></td>
		<td align="center"><br></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">A fast and effective pruning algorithm is designed to extract Maximally Stable Extremal Regions (MSERs) as character candidates using the strategy of minimizing regularized variations. Character candidates are grouped into text candidates by the single-link clustering algorithm, where distance weights and clustering threshold are learned automatically by a novel self-training distance metric learning algorithm.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">传统方法</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.86</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.68</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.76</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2013</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TPAMI</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Huang et al. [4]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">MSERs-CNN</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Combining MSERs with CNN. Much more efficient and effective than MSERs only.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">segmentation+传统方法</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.84</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.67</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.75</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.88</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.71</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.78</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2014</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ECCV</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Le et al. [5]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">HOCC</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Coarsely grouping MSERs based on their spatial alignment and appearance consistency, higherorder correlation clustering (HOCC) is used to partition the MSERs into text line candidates.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">传统方法</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.71</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.62</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.66</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.80</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.73</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.76</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2014</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Sun et al. [6]</font></td>
		<td align="center"><br></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Presenting a robust text detection approach based on color-enhanced contrasting extremal region (CER) and neural networks.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">传统方法+Neural Network</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.92</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.91</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.91</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.94</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.92</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.93</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2015</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">PR</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Yin et al. [7]</font></td>
		<td align="center"><br></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Presenting a unified distance metric learning framework for adaptive hierarchical clustering, which can simultaneously learn similarity weights (to adaptively combine different feature similarities) and the clustering threshold (to automatically determine the number of clusters).</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">传统方法</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.499</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.454</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.475</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.838</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.66</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.738</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.81</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.63</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.71</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2015</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TPAMI</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Wu et al. [9]</font></td>
		<td align="center"><br></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Exploring gradient directional symmetry at component level for smoothing edge components before text detection. Spatial information is preserved by forming Delaunay triangulation in a novel way at this level, which results in text candidates.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">传统方法</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.76</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.70</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.73</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.63</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.70</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.66</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2015</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TMM</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Tian et al. [11]</font></td>
		<td align="center"><br></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Text Flow utilizes the minimum cost (min-cost) flow network model. With character candidates detected by cascade boosting, the min-cost flow network model integrates the last three sequential steps (false character candidate removal, text line extraction, and text line verification) into a single process which solves the error accumulation problem at both character level and text line level effectively.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">regression</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.86</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.76</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.81</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.852</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.759</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.802</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2015</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ICCV</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Tian et al. [13]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CTPN</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">The CTPN detects a text line in a sequence of fine-scale text proposals directly in convolutional feature maps and develops a vertical anchor mechanism that jointly predicts location and text/non-text score of each fixed-width proposal. The sequential proposals are naturally connected by a recurrent neural network, which is seamlessly incorporated into the convolutional network, resulting in an end-to-end trainable model.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">regression</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.93</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.83</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.88</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.74</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.52</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.61</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2016</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ECCV</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Tian et al. [17]</font></td>
		<td align="center"><br></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Scene text is first detected locally in individual frames. Second, an optimal tracking trajectory is learned and linked globally with all detection, recognition and prediction information by dynamic programming.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">传统方法</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.537</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.488</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.51</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.95</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.58</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.721</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2016</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">IJCAI</font></td>
	</tr>
	<tr>
		<td align="center" valign=middle sdnum="2052;0;@"><font face="Arial">He et al. [19]</font></td>
		<td align="center" valign=middle><br></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">First ER detetctor detects regions and then we classify them to get coarse prediction of text regions. Then the local context is aggregated to classify the remaining regions in order to obtain a final prediction.</font></td>
		<td align="center" valign=middle sdnum="2052;0;@">✓</td>
		<td align="center" valign=middle sdnum="2052;0;@">✓</td>
		<td align="center" valign=middle sdnum="2052;0;@">✕</td>
		<td align="center" valign=middle sdnum="2052;0;@"><font face="Arial">regression</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.87</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.73</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.79</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.90</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.75</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.81</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2016</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ACCV</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Shi et al. [23]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">SegLink</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Decomposing text into two locally detectable elements, namely segments and links. A segment is an oriented bounding box that covers a part of a word or text line; A link connects two adjacent segments, indicating that they belong to the same word or line. Both elements are detected densely at multiple scales by an end-to-end trained, fully-convolutional neural network. Final detections are the combinations of segments that are connected by links.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">regression</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.877</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.83</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.853</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.731</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.768</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.75</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.86</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.70</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.77</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2017</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Tian et al. [30]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">WeText</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Proposing a weakly supervised scene text detection method (WeText) that trains robust and accurate scene text detection models by learning from unannotated or weakly annotated data.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Weak supervison</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.911</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.831</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.869</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2017</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ICCV</font></td>
	</tr>
	<tr>
		<td align="center" valign=middle sdnum="2052;0;@"><font face="Arial">Zhu et al. [31]</font></td>
		<td align="center" valign=middle sdnum="2052;0;@"><font face="Arial">RTN</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Mainly basing CTPN vertical vertical proposal mechanism and ResNet to produce hierarchy residual feature.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" valign=middle sdnum="2052;0;@"><font face="Arial">regression</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.94</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.89</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.91</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2017</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ICDAR</font></td>
	</tr>
	<tr>
		<td align="center" valign=middle sdnum="2052;0;@"><font face="Arial">Yang et al. [33]</font></td>
		<td align="center" valign=middle><br></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">First in each frame a multi-information fusion-based multi-orientation text detector will locate possible character candidates and extract text regions with multiple channels and scales. Then an optimal tracking trajectory is learned and linked globally over consecutive frames by dynamic programming to finally refine the detection results.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" valign=middle sdnum="2052;0;@">传统方法</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.54</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.49</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.51</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.95</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.58</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.72</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2017</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TIP</font></td>
	</tr>
	<tr>
		<td align="center" valign=middle sdnum="2052;0;@"><font face="Arial">Ren et al. [34]</font></td>
		<td align="center" valign=middle><br></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">This paper presents a novel text detection algorithm for Chinese characters based on a specific designed convolutional neural network (CNN). The CNN contains a text structure component detector layer, a spatial pyramid layer, and a multi-input-layer deep belief network (DBN)</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" valign=middle sdnum="2052;0;@"><font face="Arial">regression</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.78</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.67</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.72</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.81</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.67</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.73</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2017</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TMM</font></td>
	</tr>
	<tr>
		<td align="center" valign=middle sdnum="2052;0;@"><font face="Arial">Baek et al. [62]</font></td>
		<td align="center" valign=middle sdnum="2052;0;@"><font face="Arial">CRAFT</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Proposing CRAFT effectively detect text area by exploring each character and affinity between characters. It is designed with a convolutional neural network producing the character region score and affinity score. The region score is used to localize individual characters in the image, and the affinity score is used to group each character into a single instance.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" valign=middle sdnum="2052;0;@"><font face="Arial">segmentation</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.974</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.931</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.952</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.898</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.843</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.869</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.882</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.782</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.829</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.876</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.799</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.836</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.860</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.811</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.835</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.806</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.682</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.739</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2019</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
	</tr>
	<tr>
		<td rowspan=29 height="341" align="left" valign=middle sdnum="2052;0;@"><font face="Arial">Pixel-level</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Li et al. [3]</font></td>
		<td align="center"><br></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">(1)develop three novel cues that are tailored for character detection and a Bayesian method for their integration; (2)design a Markov random field model to exploit the inherent dependencies between characters.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">segmentation</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.80</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.62</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.70</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2014</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TIP</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Liang et al. [8]</font></td>
		<td align="center"><br></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">A new idea of convolving Laplacian with wavelet sub-bands at different levels in the frequency domain for enhancing low resolution text pixels. Exploring maxima stable extreme regions along with stroke width transform for detecting candidate text regions.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">传统方法</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.77</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.68</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.71</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.76</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.68</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.72</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.74</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.66</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.70</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2015</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TIP</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Zhang et al. [10]</font></td>
		<td align="center"><br></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">The proposed algorithm exploits the symmetry property of character groups and allows for direct extraction of text lines from natural images.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">传统方法+Neural Network</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.84</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.76</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.80</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.88</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.74</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.80</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2015</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Michal et al.[12]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">FASText</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">The paper proposed a novel easy-to-implement stroke detector which is significantly faster and produces significantly less false detections than the detectors commonly used by scene text localization methods. Following the observation that text in virtually any script is formed of strokes, stroke keypoints are efficiently detected and then exploited to obtain stroke segmentations.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">传统方法</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.84</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.69</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.77</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2015</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ICCV</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Zhang et al. [14]</font></td>
		<td align="center"><br></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">First, using a FCN model to predict the salient map of text regions in a holistic manner. Then text line are estimated by combining the salient map and character components. Finally, another FCN classifier is used to predict the centroid of each character, in order to remove the false hypotheses.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">segmentation</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.88</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.78</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.83</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.71</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.43</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.54</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.83</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.67</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.74</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2016</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Zhu et al. [16]</font></td>
		<td align="center"><br></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">First the method uses convolutional features to incorporates coarse-to-fine detection of character pixels, then extracts connected components from characters using edge and color features, and finally performs a graph-based segmentation of connected components into words (Word-Graph).</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">segmentation+传统方法</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.81</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.91</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.85</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2016</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">He et al. [18]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Text-CNN</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Developing a new learning mechanism to train the Text-CNN with multi-level and rich supervised information, including text region mask, character label, and binary text/non-text information.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">segmentation+传统方法</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.87</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.73</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.79</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.91</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.74</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.82</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.93</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.73</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.82</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.76</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.61</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.69</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2016</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TIP</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Yao et al. [21]</font></td>
		<td align="center"><br></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Proposing to localize text in a holistic manner, by casting scene text detection as a semantic segmentation problem.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">segmentation</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.889</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.802</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.843</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.723</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.587</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.648</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.765</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.753</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.759</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.432</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.27</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.333</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2016</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">arXiv</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Hu et al. [27]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">WordSup</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Proposing a weakly supervised framework that can utilize word annotations, either in tight quadrangles or the more loose bounding boxes, for character detector training. Then the detected characters are fed to a text structure analysis module, which is application dependent.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Segmentation + Weak supervison</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.933</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.875</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.903</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.793</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.77</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.782</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.452</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.309</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.368</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2017</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ICCV</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Wu et al. [28]</font></td>
		<td align="center"><br></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Analyzing the insufficiencies of the classic non-text and text settings for text detection. And then introducing the border class to the text detection problem for the first time, and validate that the decoding process is largely simplified with the help of text border.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">segmentation</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.91</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.78</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.84</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.77</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.78</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.77</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2017</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ICCV</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">He et al. [29]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">SSTD</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Proposing an attention mechanism which roughly identifies text regions via an automatically learned attentional map. Then developing a hierarchical inception module which efficiently aggregates multi-scale inception features.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">regression</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.89</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.86</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.88</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.80</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.73</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.77</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.46</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.31</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.37</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2017</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ICCV</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Tang et al.[32]</font></td>
		<td align="center"><br></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">A text-aware candidate text region(CTR) extraction model and a CTR refinement model are devised to extract CTRs and obtain precise text segmentation results.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">segmentation</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.90</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.86</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.88</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.92</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.87</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.89</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2017</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TIP</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Dai et al. [35]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">FTSN</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Detecting and segmenting the text instance jointly and simultaneously, leveraging merits from both semantic segmentation task and region proposal based object detection task.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">segmentation</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.886</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.80</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.841</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.876</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.771</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.82</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.847</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.78</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.813</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2017</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">arXiv</font></td>
	</tr>
	<tr>
		<td align="center" valign=middle sdnum="2052;0;@"><font face="Arial">Wang et al. [38]</font></td>
		<td align="center" valign=middle><br></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">This paper proposes a novel character candidate extraction method based on super-pixel segmentation and hierarchical clustering.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" valign=middle sdnum="2052;0;@"><font face="Arial">segmentation</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.87</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.78</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.82</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.87</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.82</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.84</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2017</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ICDAR</font></td>
	</tr>
	<tr>
		<td align="center" valign=middle sdnum="2052;0;@"><font face="Arial">Deng et al. [40]</font></td>
		<td align="center" valign=middle sdnum="2052;0;@"><font face="Arial">PixelLink</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">PixelLink, a novel scene text detection algorithm based on instance segmentation, is proposed. Text instances are first segmented out by linking pixels wthin the same instance together</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" valign=middle sdnum="2052;0;@"><font face="Arial">segmentation</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.886</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.875</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.881</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.855</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.820</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.837</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.830</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.732</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.778</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2018</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">AAAI</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Liu et al. [42]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">MCN</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">MCN predicts instance-level bounding boxes by firstly converting an image into a Stochastic Flow Graph (SFG) and then performing Markov Clustering on this graph.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">segmentation+传统方法</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.88</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.87</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.88</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.72</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.80</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.76</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.88</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.79</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.83</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2018</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Lyu et al. [43]</font></td>
		<td align="center"><br></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">We propose to detect scene text by localizing corner points of text bounding boxes and segmenting text regions in relative positions.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">segmentation</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.92</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.844</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.880</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.895</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.797</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.843</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.876</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.762</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.815</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.351</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.348</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.349</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.743</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.706</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.724</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2018</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Chu et al. [45]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Border</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">The paper presents a novel scene text detection technique that makes use of semantics-aware text borders and bootstrapping based text segment augmentation.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">segmentation</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.915</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.871</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.892</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.830</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.774</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.801</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.782</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.588</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.671</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.777</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.621</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.690</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2018</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ECCV</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Long et al. [46]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TextSnake</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">The paper proposes a more flexible representation for scene text, termed as TextSnake, which is able to effectively represent text instances in horizontal, oriented and curved forms.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">segmentation</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.849</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.804</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.826</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.832</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.739</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.783</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.827</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.745</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.784</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.679</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.853</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.756</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2018</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ECCV</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Yang et al. [47]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">IncepText</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Designing a novel Inception-Text module and introduce deformable PSROI pooling to deal with multi-oriented text detection.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">segmentation</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.938</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.873</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.905</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.875</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.790</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.830</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.785</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.569</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.660</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2018</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">IJCAI</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Yue et al. [48]</font></td>
		<td align="center"><br></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Proposing a general framework for text detection called Guided CNN to achieve the two goals simultaneously.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">segmentation + regression</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.691</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.660</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.675</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.885</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.846</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.870</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.866</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.789</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.823</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2018</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">BMVC</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Tang et al. [52]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">SSFT</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Proposing a novel scene text detection method that involves superpixel-based stroke feature transform (SSFT) and deep learning based region classification (DLRC).</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">segmentation + regression</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.541</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.758</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.631</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.906</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.847</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.876</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.911</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.861</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.885</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2018</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TMM</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Zhong et al. [53]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">AF-RPN</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Presenting AF-RPN(anchor-free) as an anchor-free and scale-friendly region proposal network for the Faster R-CNN framework.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">segmentation</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.94</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.90</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.92</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.89</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.83</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.86</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.75</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.66</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.70</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2018</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">arXiv</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Wang et al. [54]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">PSENet</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Proposing a novel Progressive Scale Expansion Network (PSENet), designed as a segmentation-based detector with multiple predictions for each text instance.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">segmentation</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.8692</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.845</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.8569</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.840</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.779</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.809</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.848</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.797</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.822</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.7535</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.6918</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.7213</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2019</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Xu et al.[57]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TextField</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Presenting a novel direction field which can represent scene texts of arbitrary shapes. This direction field encodes both binary text mask and direction information facilitating the subsequent text grouping process. Then proposing TextField for detecting irregular scene texts.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">segmentation</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.843</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.805</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.824</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.874</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.759</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.813</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.812</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.799</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.806</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.830</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.798</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.814</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2018</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">arXiv</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Tian et al. [58]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">FTDN</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Proposing a Focal Text Detection Network (FTDN), which could be trained well without abundant data. FTDN is able to segment text region and simultaneously regress text box at pixel-level.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">segmentation</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.847</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.773</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.809</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2018</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ICIP</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Xie et al.[61]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">SPCNet</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Basing on Mask R-CNN, this paper proposes Text Context module and Re-Score mechanism, which can effectively suppress false positives.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">segmentation</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.94</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.91</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.92</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.89</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.86</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.87</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.83</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.83</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.83</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.806</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.686</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.741</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2019</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">AAAI</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Liu et al. [64]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">PMTD</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Basing on Mask R-CNN, this paper proposes to perform “soft” semantic segmentation between the text region and the background region. It assigns a soft pyramid label (i.e., a real value between 0 and 1) for each pixel within text instance. The value of the soft pyramid label is determined by the distance to the boundary of the text box.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">segmentation</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.913</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.874</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.893</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.844</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.763</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.801</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2019</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">arXiv</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Liu et al. [80]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">SBD</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">To address label confusion for text detection, basing on Mask R-CNN, this paper proposes Sequential-free Box Discretization(SBD) by discretizing the bounding box into key edges.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">segmentation</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.894</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.838</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.865</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.896</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.805</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.848</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.836</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.701</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.763</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2019</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">IJCAI</font></td>
	</tr>
	<tr>
		<td rowspan=20 height="341" align="left" valign=middle sdnum="2052;0;@"><font face="Arial">Text-instance-level</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Gupta et al. [15]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">FCRN</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Proposing a fast and scalable engine to generate synthetic images of text in clutter; Training a Fully-Convolutional Regression Network (FCRN) which efficiently performs text detection and bounding-box regression at all locations and multiple scales in an image.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">regression</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.651</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.599</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.624</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.94</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.77</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.85</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.938</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.764</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.842</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2016</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Zhong et al. [20]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">DeepText</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Proposing the inception region proposal network (Inception-RPN) and design a set of text characteristic prior bounding boxes to achieve high word recall. Presenting a powerful text detection network that embeds ambiguous text category (ATC) information and multilevel region-of-interest pooling (MLRP) for text and non-text classification and accurate localization.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">regression</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.87</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.83</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.85</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.85</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.81</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.83</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center"><br></td>
		<td align="center"><br></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2016</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">arXiv</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Liao et al. [22]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TextBoxes</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Mainly basing SSD object detection framework.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">regression</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.89</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.82</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.86</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.89</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.83</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.86</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2017</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">AAAI</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Zhou et al. [24]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">EAST</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">The pipeline directly predicts words or text lines of arbitrary orientations and quadrilateral shapes in full images with instance segmentation.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">segmentation+regression</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.93</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.83</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.870</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.833</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.783</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.807</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.873</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.674</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.761</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.504</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.324</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.395</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2017</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Liu et al. [25]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">DMPNet</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Using quadrilateral sliding windows in several specific intermediate convolutional layers to roughly recall the text with higher overlapping area and then a shared Monte-Carlo method is proposed for fast and accurate computing of the polygonal areas. After that, designing a sequential protocol for relative regression which can exactly predict text with compact quadrangle. Moreover, a auxiliary smooth Ln loss is also proposed for further regressing the position of text, which has better overall performance than L2 loss and smooth L1 loss in terms of robustness and stability.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">regression</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.732</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.682</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.706</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2017</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">He et al. [26]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">DDR</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Proposing a deep direct regression based method for multi-oriented scene text detection. The fully convolutional network is optimized in an end-to-end way and has bi-task outputs where one is pixel-wise classification between text and non-text, and the other is direct regression to determine the vertex coordinates of quadrilateral text boundaries.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">regression</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.92</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.81</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.86</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.82</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.80</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.81</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.77</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.70</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.74</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2017</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ICCV</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Jiang et al. [36]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">R2CNN</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Basing on Faster R-CNN architecture. First, using the Region Proposal Network (RPN) to generate axis-aligned bounding boxes that enclose the texts with different orientations. Second, for each axis-aligned text box proposed by RPN, extracting its pooled features with different pooled sizes and the concatenated features are used to simultaneously predict the text/non-text score, axis-aligned box and inclined minimum area box. At last, using an inclined non-maximum suppression to get the detection results.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">regression</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.826</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.936</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.877</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.856</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.797</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.825</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2017</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">arXiv</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Xing et al. [37]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ArbiText</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Adopting the circle anchors rather than the rectangular ones to represent bounding boxes. Subsequently, incorporating a pyramid pooling module into the Single Shot MultiBox Detector framework, in order to simultaneously explore the local and global visual information, which can therefore generate more confidential detection results.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">regression</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.792</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.735</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.759</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.78</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.72</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.75</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2017</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">arXiv</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Zhang et al. [39]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">FEN</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Proposing a refined scene text detector with a novel Feature Enhancement Network (FEN) for Region Proposal and Text Detection Refinement.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">regression</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.896</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.889</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.892</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.941</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.893</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.916</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2018</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">AAAI</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Wang et al. [41]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ITN</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">A novel Instance Transformation Network (ITN) is presented to learn the geometry-aware representation encoding the unique geometric configurations of scene text instances with in-network transformation embedding</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">regression</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.857</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.741</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.795</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.903</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.723</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.803</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2018</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Liao et al. [44]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">RRD</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">The regression branch extracts rotation-sensitive features by actively rotating the convolutional filters, while the classification branch extracts rotation-invariant features by pooling the rotation sensitive features.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">regression</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.92</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.86</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.89</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.88</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.8</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.838</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.876</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.73</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.79</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.775</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.591</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.670</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2018</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Liao et al. [49]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TextBoxes++</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Mainly basing SSD object detection framework and it replaces the rectangular box representation in conventional object detector by a quadrilateral or oriented rectangle representation.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">regression</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.91</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.84</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.88</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.878</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.785</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.829</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.61</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.57</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.59</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2018</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TIP</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">He et al. [50]</font></td>
		<td align="center"><br></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Proposing a scene text detection framework based on fully convolutional network with a bi-task prediction module, in which one is a pixel-wise classification between the text and non-text and the other is pixel-wise regression to determine the vertex coordinates of quadrilateral text boundaries.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">regression</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.95</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.89</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.91</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.85</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.80</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.82</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.91</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.81</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.86</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.7669</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.5794</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.6601</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2018</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TIP</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Ma et al. [51]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">RRPN</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Presenting the Rotation Region Proposal Networks (RRPN) to generate inclined proposals with text orientation angle information. The angle information is then adapted for bounding box regression to make the proposals more accurately fit into the text region in orientation. The Rotation Region-of-Interest (RRoI) pooling layer is proposed to project arbitrary-oriented proposals to the feature map for a text region classifier.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">regression</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.90</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.72</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.80</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.822</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.732</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.774</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.821</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.677</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.742</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2018</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TMM</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Zhu et al. [55]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">SLPR</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">SLPR regresses multiple points on the edge of text line and then utilizes these points to sketch the outlines of the text.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">regression</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.855</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.836</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.845</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.801</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.701</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.748</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2018</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">arXiv</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Deng et al. [56]</font></td>
		<td align="center"><br></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">The paper proposes a Corner-based RPN(CRPN) that employs corners to estimate the possible locations of text instances instead of shifting a set of default anchors. And it also designs a embedded data augmentation module inside region-wise subnetwork.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">regression</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.92</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.84</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.876</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.89</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.81</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.845</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.555</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.633</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.591</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2018</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">arXiv</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Cai et al. [59]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">FFN</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Proposing a Feature Fusion Network to deal with text regions differing in enormous sizes.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">regression</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.89</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.77</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.83</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.43</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.35</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.39</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2018</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ICIP</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Sabyasachi et al. [60]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">RGC</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Proposing a novel recurrent architecture to improve the learnings of a feature map at a given time, by using global and local information from the same feature map at the previous time, for detecting occluded texts and long words.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">regression</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.83</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.81</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.82</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.85</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.76</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.80</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2018</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ICIP</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Liu et al. [63]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CTD</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Constructing a curve text dataset named CTW1500. Based on this dataset, proposing a polygon based curve text detector (CTD) which can directly detect curve text without empirical combination. Moreover, by seamlessly integrating the recurrent transverse and longitudinal offset connection (TLOC), the proposed method can learn the inherent connection among the position offsets. Proposing two simple but effective post-processing methods named nonpolygon suppress (NPS) and polygonal non-maximum suppression (PNMS) to further improve the detection accuracy.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">regression</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.774</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.698</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.734</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2019</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">PR</font></td>
	</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Xie et al.[79]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">DeRPN</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Proposing a novel dimension-decomposition region proposal network(DeRPN). It utilizes an anchor string mechanism to independently match object widths and heights.</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">regression</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.937</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.878</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.901</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.586</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.557</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.571</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Liberation Serif">2019</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">AAAI</font></td>
	</tr>
</table>



## 四.参考文献

| 方法论文                                                     |
| ------------------------------------------------------------ |
| **[1]** Yao C, Bai X, Liu W, et al. **Detecting texts of arbitrary orientations in natural images**. 2012 IEEE               Conference on Computer Vision and Pattern Recognition(CVPR), 2012: 1083-1090. [Paper](https://ieeexplore.ieee.org/document/6247787) |
| **[2]** Yin X C, Yin X, Huang K, et al. **Robust text detection in natural scene images**. IEEE Transactions on Pattern Analysis & Machine Intelligence, 2013, 36(5):   970-83. [Paper](https://arxiv.org/pdf/1301.2628.pdf) |
| **[3]** Li Y, Jia W, Shen C, et al. **Characterness: An indicator of text in the wild**. IEEE transactions on image processing, 2014, 23(4): 1666-1677. [Paper](https://arxiv.org/pdf/1309.6691.pdf) |
| **[4]** Huang W, Qiao Y, Tang X. **Robust scene text detection with convolution neural network induced mser trees**. European Conference on Computer Vision(ECCV), 2014: 497-511. [Paper](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.724.6859&rep=rep1&type=pdf) |
| **[5]** Kang L, Li Y, Doermann D. **Orientation robust text line detection in natural images**. Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition. 2014: 4034-4041. [Paper](https://ieeexplore.ieee.org/document/6909910) |
| **[6]** Sun L, Huo Q, Jia W, et al. **A robust approach for text detection from natural scene images**.   Pattern Recognition, 2015, 48(9): 2906-2920. [Paper](https://www.sciencedirect.com/science/article/abs/pii/S0031320315001260) |
| **[7]** Yin X C, Pei W Y, Zhang J, et al. **Multi-orientation scene text detection with adaptive clustering**. IEEE Transactions on Pattern Analysis & Machine Intelligence, 2015 (9): 1930-1937. [Paper](https://ieeexplore.ieee.org/document/7001081) |
| **[8]** Liang G, Shivakumara P, Lu T, et al. **Multi-spectral fusion based approach for  arbitrarily oriented scene text detection in video images**. IEEE Transactions on Image Processing, 2015, 24(11): 4488-4501. [Paper](https://ieeexplore.ieee.org/document/7180356) |
| **[9]** Wu L, Shivakumara P, Lu T, et al. **A New Technique for Multi-Oriented Scene Text Line Detection and Tracking in Video**. IEEE Trans. Multimedia, 2015, 17(8): 1137-1152. [Paper](https://ieeexplore.ieee.org/document/7121019) |
| **[10]** Zheng Z, Wei S, et al. **Symmetry-based text line detection in natural scenes**. IEEE Conference on Computer Vision & Pattern Recognition(CVPR), 2015. [Paper](https://ieeexplore.ieee.org/document/7298871) |
| **[11]** Tian S, Pan Y, Huang C, et al. **Text flow: A unified text detection system in natural scene images**. Proceedings of the IEEE international conference on computer vision(ICCV). 2015: 4651-4659. [Paper](https://arxiv.org/pdf/1604.06877.pdf) |
| **[12]** Buta M, et al. **FASText: Efficient unconstrained scene text detector**. 2015 IEEE International Conference on Computer Vision (ICCV). 2015: 1206-1214. [Paper](https://ieeexplore.ieee.org/document/7410500) |
| **[13]** Tian Z, Huang   W, He T, et al. **Detecting text in natural image with connectionist text proposal network**. European conference on computer vision(ECCV), 2016: 56-72. [Paper](https://arxiv.org/pdf/1609.03605.pdf) [Code](https://github.com/tianzhi0549/CTPN) |
| **[14]** Zhang Z, Zhang C, Shen W, et al. **Multi-oriented text detection with fully convolutional networks.** Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition(CVPR). 2016: 4159-4167. [Paper](https://arxiv.org/pdf/1604.04018.pdf) |
| **[15]** Gupta A, Vedaldi A, Zisserman A. **Synthetic data for text localisation in natural images**. Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition(CVPR). 2016: 2315-2324. [Paper](https://arxiv.org/pdf/1604.06646.pdf) [Code](https://github.com/ankush-me/SynthText) |
| **[16]** S. Zhu and R. Zanibbi, **A Text Detection System for Natural Scenes with Convolutional Feature Learning and Cascaded Classification**, 2016 IEEE Conference on Computer Vision and Pattern Recognition (CVPR), 2016: 625-632. [Paper](https://ieeexplore.ieee.org/document/7780443) |
| **[17]** Tian S, Pei W Y, Zuo Z Y, et al. **Scene Text Detection in Video by Learning Locally and Globally**. IJCAI. 2016: 2647-2653. [Paper](https://www.ijcai.org/Proceedings/16/Papers/376.pdf) |
| **[18]** He T, Huang W, Qiao Y, et al. **Text-attentional convolutional neural network for scene text detection**. IEEE transactions on image processing, 2016, 25(6):   2529-2541. [Paper](https://arxiv.org/pdf/1510.03283.pdf) |
| **[19]** He, Dafang and Yang, Xiao and Huang, Wenyi and Zhou, Zihan and Kifer, Daniel and Giles, C Lee. **Aggregating local context for accurate scene text detection**. ACCV, 2016. [Paper](http://www.cse.psu.edu/~duk17/papers/accv2016.pdf) |
| **[20]** Zhong Z, Jin L, Zhang S, et al. **Deeptext: A unified framework for text proposal generation and text detection in natural images**. arXiv preprint arXiv:1605.07314, 2016. [Paper](https://arxiv.org/pdf/1605.07314.pdf) |
| **[21]** Yao C, Bai X, Sang N, et al. **Scene text detection via holistic, multi-channel prediction**. arXiv preprint arXiv:1606.09002, 2016. [Paper](https://arxiv.org/pdf/1606.09002.pdf) |
| **[22]** Liao M, Shi B, Bai X, et al. **TextBoxes: A Fast Text Detector with a Single Deep Neural  Network**. AAAI. 2017: 4161-4167. [Paper](https://arxiv.org/abs/1611.06779) [Code](https://github.com/MhLiao/TextBoxes) |
| **[23]** Shi B, Bai X, Belongie S. **Detecting Oriented Text in Natural Images by Linking Segments**. 2017 IEEE Conference on Computer Vision and Pattern Recognition (CVPR). IEEE, 2017: 3482-3490. [Paper](https://arxiv.org/abs/1703.06520) [Code](https://github.com/dengdan/seglink) |
| **[24]** Zhou X, Yao C, Wen H, et al. **EAST: an efficient and accurate scene text detector**. CVPR, 2017: 2642-2651. [Paper](https://arxiv.org/abs/1704.03155) [Code](https://github.com/argman/EAST) |
| **[25]** Liu Y, Jin L. **Deep matching prior network: Toward tighter multi-oriented text detection**. CVPR, 2017: 3454-3461. [Paper](https://arxiv.org/abs/1703.01425) |
| **[26]** He W, Zhang X Y, Yin F, et al. **Deep Direct Regression for Multi-Oriented Scene Text Detection**. Proceedings of the IEEE International Conference on Computer Vision (ICCV). 2017: 745-753. [Paper](https://arxiv.org/abs/1703.08289) |
| **[27]** Hu H, Zhang C, Luo Y, et al. **Wordsup: Exploiting word annotations for character based text detection**. ICCV, 2017. [Paper](https://arxiv.org/abs/1708.06720) |
| **[28]** Wu Y,   Natarajan P. **Self-organized text detection with minimal post-processing via border learning**. ICCV, 2017. [Paper](http://openaccess.thecvf.com/content_ICCV_2017/papers/Wu_Self-Organized_Text_Detection_ICCV_2017_paper.pdf) |
| **[29]** He P, Huang W, He T, et al. **Single shot text detector with regional attention**. The IEEE   International Conference on Computer Vision (ICCV). 2017, 6(7). [Paper](https://arxiv.org/abs/1709.00138) [Code](https://github.com/BestSonny/SSTD) |
| **[30]** Tian S, Lu S, Li C. **Wetext: Scene text detection under weak supervision**. ICCV, 2017. [Paper](https://arxiv.org/abs/1710.04826) |
| **[31]** Zhu, Xiangyu and Jiang, Yingying et al. **Deep Residual Text Detection Network for Scene Text**. ICDAR, 2017.  [Paper](https://arxiv.org/abs/1711.04147) |
| **[32]** Tang Y , Wu X. **Scene Text Detection and Segmentation Based on Cascaded Convolution Neural Networks**. IEEE Transactions on Image Processing, 2017, 26(3):1509-1520. [Paper](https://ieeexplore.ieee.org/document/7828014) |
| **[33]** Yang C, Yin X C, Pei W Y, et al. **Tracking Based Multi-Orientation Scene Text Detection: A Unified Framework with Dynamic Programming**. IEEE Transactions on Image Processing, 2017. [Paper](https://ieeexplore.ieee.org/document/7903596) |
| **[34]** X. Ren, Y. Zhou, J. He, K. Chen, X. Yang and J. Sun, **A Convolutional Neural Network-Based Chinese Text Detection Algorithm via Text Structure Modeling**. in IEEE Transactions on Multimedia, vol. 19, no. 3, pp. 506-518, March 2017. [Paper](https://ieeexplore.ieee.org/document/7733055) |
| **[35]** Dai Y, Huang Z, Gao Y, et al. **Fused text segmentation networks for multi-oriented scene text detection**. arXiv preprint arXiv:1709.03272, 2017. [Paper](https://arxiv.org/abs/1709.03272) |
| **[36]** Jiang Y, Zhu X, Wang X, et al. **R2CNN: rotational region CNN for orientation robust scene text detection**. arXiv preprint arXiv:1706.09579, 2017. [Paper](https://arxiv.org/abs/1706.09579) |
| **[37]** Xing D, Li Z, Chen X, et al. **ArbiText: Arbitrary-Oriented Text Detection in Unconstrained Scene**. arXiv preprint arXiv:1711.11249, 2017. [Paper](https://arxiv.org/abs/1711.11249) |
| **[38]** C. Wang, F. Yin and C. Liu, **Scene Text Detection with Novel Superpixel Based Character Candidate Extraction**. in 2017 14th IAPR International Conference on Document Analysis and Recognition (ICDAR),  2017, pp. 929-934. [Paper](https://ieeexplore.ieee.org/document/8270087) |
| **[39]** Sheng Zhang, Yuliang Liu, Lianwen Jin et al. **Feature Enhancement Network: A Refined Scene Text Detector**. In AAAI 2018. [Paper](https://arxiv.org/abs/1711.04249) |
| **[40]** Dan Deng et al. **PixelLink: Detecting Scene Text via Instance Segmentation**. In AAAI 2018. [Paper](https://arxiv.org/abs/1801.01315) [Code](https://github.com/ZJULearning/pixel_link) |
| **[41]** Fangfang Wang, Liming Zhao, Xi L et al. **Geometry-Aware Scene Text Detection with Instance Transformation Network**. In CVPR 2018. [Paper](http://openaccess.thecvf.com/content_cvpr_2018/CameraReady/1653.pdf) |
| **[42]** Zichuan Liu,   Guosheng Lin, Sheng Yang et al. **Learning Markov Clustering Networks for Scene Text Detection**. In CVPR 2018. [Paper](https://arxiv.org/abs/1805.08365) |
| **[43]** Pengyuan Lyu, Cong Yao, Wenhao Wu et al. **Multi-Oriented Scene Text Detection via Corner   Localization and Region Segmentation**. In CVPR 2018. [Paper](https://arxiv.org/abs/1802.08948) |
| **[44]** Minghui L, Zhen Z, Baoguang S. **Rotation-Sensitive Regression for Oriented Scene Text Detection**. In CVPR 2018. [Paper](https://arxiv.org/abs/1803.05265) |
| **[45]** Chuhui Xue et al. **Accurate Scene Text Detection through Border Semantics Awareness and   Bootstrapping**. In ECCV 2018. [Paper](https://arxiv.org/abs/1807.03547) |
| **[46]** Long, Shangbang and Ruan, Jiaqiang, et al. **TextSnake: A Flexible Representation for Detecting Text of Arbitrary Shapes**. In ECCV, 2018. [Paper](https://arxiv.org/abs/1807.01544) |
| **[47]** Qiangpeng Yang, Mengli Cheng et al. **IncepText: A New Inception-Text Module with       Deformable PSROI Pooling for Multi-Oriented Scene Text Detection**. In IJCAI 2018. [Paper](https://arxiv.org/abs/1805.01167) |
| **[48]** Xiaoyu Yue et al. **Boosting up Scene Text Detectors with Guided CNN**. In BMVC 2018. [Paper](https://arxiv.org/abs/1805.04132) |
| **[49]** Liao M, Shi B , Bai X. **TextBoxes++: A Single-Shot Oriented Scene Text Detector**. IEEE Transactions on Image Processing, 2018, 27(8):3676-3690. [Paper](https://arxiv.org/abs/1801.02765) [Code](https://github.com/MhLiao/TextBoxes_plusplus) |
| **[50]** W. He, X. Zhang, F. Yin and C. Liu, **Multi-Oriented and Multi-Lingual Scene Text Detection With Direct Regression**, in IEEE Transactions on Image Processing, vol. 27, no. 11, pp.5406-5419, 2018. [Paper](https://ieeexplore.ieee.org/document/8410577) |
| **[51]** Ma J, Shao W, Ye H, et al. **Arbitrary-oriented scene text detection via rotation proposals**.in IEEE Transactions on Multimedia, 2018. [Paper](https://arxiv.org/abs/1703.01086) [Code](https://github.com/mjq11302010044/RRPN) |
| **[52]** Youbao Tang and Xiangqian Wu. **Scene Text Detection Using Superpixel-Based Stroke Feature Transform and Deep Learning Based Region Classification**. In TMM, 2018. [Paper](https://ieeexplore.ieee.org/document/8281640) |
| **[53]** Zhuoyao Zhong, Lei Sun and Qiang Huo. **An Anchor-Free Region Proposal Network for Faster R-CNN based Text Detection Approaches**. arXiv preprint arXiv:1804.09003. 2018. [Paper](https://arxiv.org/abs/1804.09003) |
| **[54]** Wenhai W, Enze X, et al. **Shape Robust Text Detection with Progressive Scale Expansion   Network**. In CVPR 2019. [Paper](https://arxiv.org/abs/1903.12473) [Code](https://github.com/whai362/PSENet) |
| **[55]** Zhu Y, Du J. **Sliding Line Point Regression for Shape Robust Scene Text Detection**. arXiv preprint arXiv:1801.09969, 2018. [Paper](https://arxiv.org/abs/1801.09969) |
| **[56]** Linjie D, Yanxiang Gong, et al. **Detecting Multi-Oriented Text with Corner-based Region Proposals**.  arXiv preprint arXiv: 1804.02690, 2018. [Paper](https://arxiv.org/abs/1804.02690) [Code](https://github.com/xhzdeng/crpn) |
| **[57]** Yongchao Xu, Yukang Wang, Wei Zhou, et al. **TextField: Learning A Deep Direction Field for Irregular Scene Text Detection**. arXiv preprint arXiv: 1812.01393, 2018. [Paper](https://arxiv.org/abs/1812.01393) |
| **[58]** Xiaowei Tian, Dao Wu, Rui Wang, Xiaochun Cao. **Focal Text: an Accurate Text Detection with Focal Loss**. In ICIP 2018. [Paper](https://ieeexplore.ieee.org/document/8451241) |
| **[59]** Chenqin C, Pin L, Bing S. **Feature Fusion Network for Scene Text Detection**. In ICIP, 2018. [Paper](https://ieeexplore.ieee.org/document/8451402) |
| **[60]** Sabyasachi Mohanty et al. **Recurrent Global Convolutional Network for Scene Text Detection**. In ICIP 2018. [Paper](https://ieeexplore.ieee.org/document/8451058) |
| **[61]** Enze Xie, et al. **Scene Text Detection with Supervised Pyramid Context Network**. In AAAI 2019. [Paper](https://arxiv.org/abs/1811.08605) |
| **[62]** Youngmin Baek, Bado Lee, et al. **Character Region Awareness for Text Detection**. In CVPR 2019. [Paper](https://arxiv.org/abs/1904.01941) |
| **[63]** Yuliang L, Lianwen J, Shuaitao Z, et al. **Detecting curve text in the wild: New dataset and new solution**. Pattern Recognition, 2019. [Paper](https://arxiv.org/abs/1712.02170) [Code](https://github.com/Yuliang-Liu/Curve-Text-Detector) |
| **[64]** Jingchao Liu, Xuebo Liu, et al, **Pyramid Mask Text Detector**. arXiv preprint arXiv:1903.11800, 2019. [Paper](https://arxiv.org/abs/1903.11800) |
| **[79]** Lele Xie, Yuliang Liu, Lianwen Jin, Zecheng Xie, **DeRPN: Taking a further step toward more general object detection**. In AAAI, 2019. [Paper](https://arxiv.org/abs/1811.06700) [Code](https://github.com/HCIILAB/DeRPN)|
| **[80]** Yuliang Liu, Lianwen Jin, et al, **Omnidirectional Scene Text Detction with Sequential-free Box Discretizationr**. In IJCAI, 2019.|
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**数据集论文** |
| **USTB-SV1K[65]**：Xu-Cheng Yin, Xuwang Yin, Kaizhu Huang, and Hong-Wei Hao, **Robust text detection   in natural scene images**, IEEE Trans. Pattern Analysis and Machine Intelligence (TPAMI), priprint, 2013. [Paper](https://ieeexplore.ieee.org/document/6247787) |
| **SVT[66]**:  Wang,Kai, and S. Belongie. **Word Spotting in the Wild**. European Conference on Computer Vision(ECCV), 2010: 591-604.  [Paper](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.168.4897&rep=rep1&type=pdf) |
| **ICDAR2005[67]**:  Lucas, S: **ICDAR 2005 text locating competition results**. In: ICDAR ,2005. [Paper](https://ieeexplore.ieee.org/document/1575514) |
| **ICDAR2011[68]**:  Shahab, A, Shafait, F, Dengel, A: **ICDAR 2011 robust reading competition challenge 2: Reading text in scene images**. In: ICDAR, 2011. [Paper](https://ieeexplore.ieee.org/document/6065556) |
| **ICDAR2013[69]**：D. Karatzas, F. Shafait, S. Uchida, et al. **ICDAR 2013 robust reading competition**. In ICDAR, 2013. [Paper](https://ieeexplore.ieee.org/document/6628859) |
| **ICDAR2015[70]**：D. Karatzas, L. Gomez-Bigorda, A. Nicolaou, S. K. Ghosh, A. D.Bagdanov, M. Iwamura, J. Matas, L. Neumann, V. R. Chandrasekhar, S. Lu, F. Shafait, S. Uchida, and E. Valveny. **ICDAR 2015 competition on robust reading**. In ICDAR, pages 1156–1160, 2015. [Paper](https://ieeexplore.ieee.org/document/7333942) |
| **MSRA-TD500[71]**：C. Yao, X. Bai, W. Liu, Y. Ma, and Z. Tu, **Detecting texts of arbitrary orientations in natural images**. in Proc. IEEE Conf. Computer Vision and Pattern Recognition, 2012, pp.1083–1090.[Paper](http://pages.ucsd.edu/~ztu/publication/cvpr12_textdetection.pdf) |
| **COCO-Text[72]**：Veit A, Matera T, Neumann L, et al. **Coco-text: Dataset and benchmark for text   detection and recognition in natural images**. arXiv preprint arXiv:1601.07140, 2016. [Paper](https://arxiv.org/abs/1601.07140) |
| **RCTW-17[73]**：Shi B, Yao C, Liao M, et al. **ICDAR2017 competition on reading chinese text in the wild (RCTW-17)**. Document Analysis and Recognition (ICDAR), 2017 14th IAPR International Conference on. IEEE, 2017, 1: 1429-1434. [Paper](https://arxiv.org/abs/1708.09585) |
| **Total-Text[74]**：Chee C K, Chan C S. **Total-text: A comprehensive dataset for scene text detection and recognition**.Document Analysis and Recognition (ICDAR), 2017 14th IAPR International Conference on. IEEE, 2017, 1: 935-942.[Paper](https://arxiv.org/abs/1710.10400) |
| **SCUT-CTW1500[75]**：Yuliang L, Lianwen J, Shuaitao Z, et al. **Detecting curve text in the wild: New dataset and new solution**. Pattern Recognition, 2019.[Paper](https://arxiv.org/abs/1712.02170) |
| **MLT[76]**:  Nayef, N; Yin, F; Bizid, I; et al. **ICDAR2017 robust reading challenge on multi-lingual scene text detection and script identiﬁcation-rrc-mlt**. In Document Analysis and Recognition (ICDAR), 2017 14th IAPR International Conference on, volume 1, 1454–1459. IEEE. [Paper](https://ieeexplore.ieee.org/document/8270168) |
| **OSTD[77]**: Chucai Yi and YingLi Tian, **Text string detection from natural scenes by structure-based partition and grouping**, In IEEE Transactions on Image Processing, vol. 20, no. 9, pp. 2594–2605, 2011. [Paper](https://ieeexplore.ieee.org/abstract/document/5729827) |
| **CTW[78]**: Yuan T L, Zhu Z, Xu K, et al. **Chinese Text in the Wild**. arXiv preprint arXiv:1803.00085, 2018. [Paper](https://arxiv.org/abs/1803.00085) |
