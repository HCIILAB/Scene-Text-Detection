# Scene Text Detection Resources

<p align='right'>Author: Chongyu Liu</p>

<!-- MarkdownTOC -->

- [1.Datasets](#1-datasets)
    - [1.1 Horizontal-Text Datasets](#11-Horizontal-Text-Datasets)
    - [1.2 Arbitrary-Quadrilateral-Text Datasets](#12-Arbitrary-Quadrilateral-Text-Datasets)
    - [1.3 Irregular-Text Datasets](#13-Irregular-Text-Datasets)
    - [1.4 Synthetic Datasets](#14-synthetic-datasets)
    - [1.5 Comparison of Datasets](#15-comparison-of-datasets)
- [2. Summary of Scene Text Detection Resources](#2-summary-of-scene-text-detection-results)
    - [2.1 Comparison of Methods](#21-comparison-of-methods)
        - [2.1.1 Traditional Methods](#211-traditional-methods)
        - [2.1.2 Segmentation-based Methods](#212-Pixel-level-methods)
        - [2.1.3 Regression-based Methods](#213-regression-methods)
        - [2.1.4 Hybrid Methods](#214-hybrid-methods)
    - [2.2 Detection Results](#22-detection-result)
        - [2.2.1 Detection Results on Horizontal-Text Datasets](#221-Detection-Results-on-Horizontal-Text-Datasets)
        - [2.2.2 Detection Results on Arbitrary-Quadrilateral-Text Datasets](#222-Detection-Results-on-Arbitrary-Quadrilateral-Text-Datasets)
        - [2.2.3 Detection Results on Irregular-Text Datasets](#223-Detection-Results-on-Irregular-Text-Datasets)
- [3. Survey](#3-survey)
- [4. Evaluation](#4-Evaluation)
- [5. OCR Service](#5-ocr-service)
- [6. References and Code](#6-references)

<!-- /MarkdownTOC -->

------

<a id="1-datasets"></a>
## 1. Datasets

<a id="11-Horizontal-Text-Datasets"></a>
### 1.1 Horizontal-Text Datasets

- ICDAR 2003(IC03)：
  * **Introduction:** It contains 509 images in total, 258 for training and 251 for testing. Specifically, it contains 1110 text instance in training set, while 1156 in testing set. It has word-level annotation. IC03 only consider English text instance.
  * **Link:** [IC03-download](http://www.iapr-tc11.org/mediawiki/index.php?title=ICDAR_2003_Robust_Reading_Competitions)

- ICDAR 2011(IC11):
  * **Introduction:** IC11 is an English dataset for text detection.  It contains 484 images, 229 for training and 255 for testing. There are 1564 text instance in this dataset. It provides both word-level and character-level annotation.
  * **Link:** [IC11-download](http://www.cvc.uab.es/icdar2011competition/?com=downloads)   

- ICDAR 2013(IC13)：
  * **Introduction:** IC13 is almost the same as IC11. It contains 462 images in total, 229 for training and 233 for testing. Specifically, it contains 849 text instance in training set, while 1095 in testing set.
  * **Link:** [IC13-download](http://dagdata.cvc.uab.es/icdar2013competition/?ch=2&com=downloads)

<a id="12-Arbitrary-Quadrilateral-Text-Datasets"></a>
### 1.2 Arbitrary-Quadrilateral-Text Datasets

- USTB-SV1K：
  * **Introduction:** USTB-SV1K is an English dataset.  It contains 1000 street images from Google Street View  with  2955 text instance  in total. It only provides word-level annotations.  
  * **Link:** [USTB-SV1K-download](http://prir.ustb.edu.cn/TexStar/MOMV-text-detection/)

- SVT：
  * **Introduction:** It contains 350 images with 725 English text intance in total. SVT has both character-level and word-level annotations. The images of SVT are harvested from Google Street View and have low resolution.
  * **Link:** [SVT-download](http://vision.ucsd.edu/~kai/grocr/)

- SVT-P：
  - **Introduction:** It contains 639 cropped word images for testing. Images were selected from the side-view angle snapshots in Google Street View. Therefore, most images are heavily distorted by the non-frontal view angle. It is the imporved datasets of SVT.
  - **Link:** [SVT-P-download](https://pan.baidu.com/s/1rhYUn1mIo8OZQEGUZ9Nmrg )  \(Password : vnis)

- ICDAR 2015(IC15)：
  - **Introduction:** It contains 1500 images in total, 1000 for training and 500 for testing. Specifically, it contains 17548 text instance. It provides word-level annotations. IC15 is the first incidental scene text dataset and it only considers English words.
  - **Link:** [IC15-download](http://rrc.cvc.uab.es/?ch=4&com=downloads)

- COCO-Text：
  - **Introduction:** It contains 63686 images in total, 43686 for training, 10000 for validating and 10000 for testing. Specifically, it contains 145859  cropped word images for testing, including handwritten and printed, clear and blur, English and non-English.
  - **Link:** [COCO-Text-download](https://vision.cornell.edu/se3/coco-text-2/)

- MSRA-TD500：
  - **Introduction:** It contains 500 images in total. It provides text-line-level annotation rather than word, and polygon boxes rather than axis-aligned rectangles for text region annootation. It contains both English and Chinese text instance.
  - **Link:** [MSRA-TD500-download](http://pages.ucsd.edu/~ztu/Download_front.htm)

- MLT 2017：
  - **Introduction:** It contains 10000 natural images in total. It provides word-level annotation. There are 9 languages for MLT. It is a more real and complex datasets for scene text detection and recognition..
  - **Link:** [MLT-download](http://rrc.cvc.uab.es/?ch=8)

- MLT 2019:
  - **Introduction:** It contains 18000 images in total. It provides word-level annotation. Compared to MLT,  this dataset has 10 languages. It is a more real and complex datasets for scene text detection and recognition..
  - **Link:** [MLT-2019-download](http://rrc.cvc.uab.es/?ch=15)

- CTW：
  - **Introduction:** It contains 32285 high resolution street view images of Chinese text, with 1018402 character instances in total. All images are annotated at the character level, including its underlying character type, bouding box, and 6 other attributes. These attributes indicate whether its background is complex, whether it’s raised, whether it’s hand-written or printed, whether it’s occluded, whether it’s distorted, whether it uses word-art.
  - **Link:** [CTW-download](https://ctwdataset.github.io/)

- RCTW-17：
  - **Introduction:** It contains 12514 images in total, 11514 for training and 1000 for testing. Images in RCTW-17 were mostly collected by camera or mobile phone, and others were generated images. Text instances are annotated with parallelograms. It is the first large scale Chinese dataset, and was also the largest published one by then.
  - **Link:** [RCTW-17-download](http://rctw.vlrlab.net/dataset/)

- ReCTS：
  - **Introduction:** This data set is a large-scale Chinese Street View Trademark Data Set. It is based on Chinese words and Chinese text line-level labeling. The labeling method is arbitrary quadrilateral labeling. It contains 20000 images in total.
  - **Link:** [ReCTS-download](http://rrc.cvc.uab.es/?ch=12)

<a id="13-Irregular-Text-Datasets"></a>
### 1.3 Irregular-Text Datasets

- CUTE80：
  - **Introduction:** It contains 80 high-resolution images taken in natural scenes. Specifically, it contains 288 cropped word images for testing. The dataset focuses on curved text. No lexicon is provided.
  - **Link:** [CUTE80-download](http://cs-chan.com/downloads_CUTE80_dataset.html)

- Total-Text：
  - **Introduction:** It contains 1,555 images in total. Specifically, it contains 11,459  cropped word images with more than three different text orientations: horizontal, multi-oriented and curved.
  - **Link:** [Total-Text-download](https://github.com/cs-chan/Total-Text-Dataset)

- SCUT-CTW1500：
  - **Introduction:** It contains 1500 images in total, 1000 for training and 500 for testing. Specifically, it contains 10751 cropped word images for testing. Annotations in CTW-1500 are polygons with 14 vertexes. The dataset mainly consists of Chinese and English.
  - **Link:** [CTW-1500-download](https://github.com/Yuliang-Liu/Curve-Text-Detector)

- LSVT：
  - **Introduction:** LSVT consists of 20,000 testing data, 30,000 training data in full annotations and 400,000 training data in weak annotations, which are referred to as partial labels. The labeled text regions demonstrate the diversity of text: horizontal, multi-oriented and curved.
  - **Link:** [LSVT-download](https://rrc.cvc.uab.es/?ch=16)

- ArT：
  - **Introduction:** ArT consists of 10,166 images, 5,603 for training and 4,563 for testing. They were collected with text shape diversity in mind and all text shapes have high number of existence in ArT.
  - **Link:** [ArT-download](https://rrc.cvc.uab.es/?ch=14)

<a id="14-synthetic-datasets"></a>
### 1.4 Synthetic Datasets

* Synth80k :
  * **Introduction:** It contains 800 thousands images with approximately 8 million synthetic word instances. Each text instance is annotated with its text-string, word-level and character-level bounding-boxes.
  * **Link:** [Synth80k-download](http://www.robots.ox.ac.uk/~vgg/data/scenetext/)

* SynthText :
  * **Introduction:** It contains 6 million cropped word images. The generation process is similar to that of Synth90k. It is also annotated in horizontal-style.  
  * **Link:** [SynthText-download](https://github.com/ankush-me/SynthText)

<a id="15-comparison-of-datasets"></a>

### 1.5 Comparison of Datasets

<body>
<table cellspacing="0" border="0">
	<colgroup width="85"></colgroup>
	<colgroup width="119"></colgroup>
	<colgroup span="7" width="85"></colgroup>
	<colgroup width="153"></colgroup>
	<colgroup width="104"></colgroup>
	<colgroup span="3" width="85"></colgroup>
	<tr>
		<td colspan=14 height="20" align="center"><b>Comparison of Datasets</b></td>
		</tr>
	<tr>
		<td rowspan=2 height="39" align="center" valign=top><b>Datasets</b></td>
		<td rowspan=2 align="center" valign=top><b>Language</b></td>
		<td colspan=3 align="center"><b>Image</b></td>
		<td colspan=3 align="center"><b>Text instance </b></td>
		<td colspan=3 align="center"><b>Text Shape</b></td>
		<td colspan=3 align="center"><b>Annotation level</b></td>
		</tr>
	<tr>
		<td align="center"><b>Total</b></td>
		<td align="center"><b>Train</b></td>
		<td align="center"><b>Test</b></td>
		<td align="center"><b>Total</b></td>
		<td align="center"><b>Train</b></td>
		<td align="center"><b>Test</b></td>
		<td align="center"><b>Horizontal</b></td>
		<td align="center"><b>Arbitrary-Quadrilateral</b></td>
		<td align="center"><b>Multi-oriented</b></td>
		<td align="center"><b>Char</b></td>
		<td align="center"><b>Word</b></td>
		<td align="center"><b>Text-Line</b></td>
	</tr>
	<tr>
		<td height="20" align="center"><b>IC03</b></td>
		<td align="center">English</td>
		<td align="center" sdval="509" sdnum="2052;">509</td>
		<td align="center" sdval="258" sdnum="2052;">258</td>
		<td align="center" sdval="251" sdnum="2052;">251</td>
		<td align="center" sdval="2266" sdnum="2052;">2266</td>
		<td align="center" sdval="1110" sdnum="2052;">1110</td>
		<td align="center" sdval="1156" sdnum="2052;">1156</td>
		<td align="center">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
	</tr>
	<tr>
		<td height="20" align="center"><b>IC11</b></td>
		<td align="center">English</td>
		<td align="center" sdval="484" sdnum="2052;">484</td>
		<td align="center" sdval="229" sdnum="2052;">229</td>
		<td align="center" sdval="255" sdnum="2052;">255</td>
		<td align="center" sdval="1564" sdnum="2052;">1564</td>
		<td align="center">～</td>
		<td align="center">～</td>
		<td align="center">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center">✓</td>
		<td align="center">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
	</tr>
	<tr>
		<td height="20" align="center"><b>IC13</b></td>
		<td align="center">English</td>
		<td align="center" sdval="462" sdnum="2052;">462</td>
		<td align="center" sdval="229" sdnum="2052;">229</td>
		<td align="center" sdval="233" sdnum="2052;">233</td>
		<td align="center" sdval="1944" sdnum="2052;">1944</td>
		<td align="center" sdval="849" sdnum="2052;">849</td>
		<td align="center" sdval="1095" sdnum="2052;">1095</td>
		<td align="center">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center">✓</td>
		<td align="center">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
	</tr>
	<tr>
		<td height="20" align="center"><b>USTB-SV1K</b></td>
		<td align="center">English</td>
		<td align="center" sdval="1000" sdnum="2052;">1000</td>
		<td align="center" sdval="500" sdnum="2052;">500</td>
		<td align="center" sdval="500" sdnum="2052;">500</td>
		<td align="center" sdval="2955" sdnum="2052;">2955</td>
		<td align="center">～</td>
		<td align="center">～</td>
		<td align="center">✓</td>
		<td align="center">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
	</tr>
	<tr>
		<td height="20" align="center"><b>SVT</b></td>
		<td align="center">English</td>
		<td align="center" sdval="350" sdnum="2052;">350</td>
		<td align="center" sdval="100" sdnum="2052;">100</td>
		<td align="center" sdval="250" sdnum="2052;">250</td>
		<td align="center" sdval="725" sdnum="2052;">725</td>
		<td align="center" sdval="211" sdnum="2052;">211</td>
		<td align="center" sdval="514" sdnum="2052;">514</td>
		<td align="center">✓</td>
		<td align="center">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center">✓</td>
		<td align="center">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
	</tr>
	<tr>
		<td height="20" align="center"><b>SVT-P</b></td>
		<td align="center">English</td>
		<td align="center" sdval="238" sdnum="2052;">238</td>
		<td align="center">～</td>
		<td align="center">～</td>
		<td align="center" sdval="639" sdnum="2052;">639</td>
		<td align="center">～</td>
		<td align="center">～</td>
		<td align="center">✓</td>
		<td align="center">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
	</tr>
	<tr>
		<td height="20" align="center"><b>IC15</b></td>
		<td align="center">English</td>
		<td align="center" sdval="1500" sdnum="2052;">1500</td>
		<td align="center" sdval="1000" sdnum="2052;">1000</td>
		<td align="center" sdval="500" sdnum="2052;">500</td>
		<td align="center" sdval="17548" sdnum="2052;">17548</td>
		<td align="center" sdval="122318" sdnum="2052;">122318</td>
		<td align="center" sdval="5230" sdnum="2052;">5230</td>
		<td align="center">✓</td>
		<td align="center">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
	</tr>
	<tr>
		<td height="20" align="center"><b>COCO-Text</b></td>
		<td align="center">English</td>
		<td align="center" sdval="63686" sdnum="2052;">63686</td>
		<td align="center" sdval="43686" sdnum="2052;">43686</td>
		<td align="center" sdval="20000" sdnum="2052;">20000</td>
		<td align="center" sdval="145859" sdnum="2052;">145859</td>
		<td align="center" sdval="118309" sdnum="2052;">118309</td>
		<td align="center" sdval="27550" sdnum="2052;">27550</td>
		<td align="center">✓</td>
		<td align="center">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
	</tr>
	<tr>
		<td height="20" align="center"><b>MSRA-TD500</b></td>
		<td align="center">English/Chinese</td>
		<td align="center" sdval="500" sdnum="2052;">500</td>
		<td align="center" sdval="300" sdnum="2052;">300</td>
		<td align="center" sdval="200" sdnum="2052;">200</td>
		<td align="center">～</td>
		<td align="center">～</td>
		<td align="center">～</td>
		<td align="center">✓</td>
		<td align="center">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center">✓</td>
	</tr>
	<tr>
		<td height="20" align="center"><b>MLT 2017</b></td>
		<td align="center">Multi-lingual</td>
		<td align="center" sdval="18000" sdnum="2052;">18000</td>
		<td align="center" sdval="7200" sdnum="2052;">7200</td>
		<td align="center" sdval="10800" sdnum="2052;">10800</td>
		<td align="center">～</td>
		<td align="center">～</td>
		<td align="center">～</td>
		<td align="center">✓</td>
		<td align="center">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
	</tr>
	<tr>
		<td height="20" align="center"><b>MLT 2019</b></td>
		<td align="center">Multi-lingual</td>
		<td align="center" sdval="20000" sdnum="2052;">20000</td>
		<td align="center" sdval="10000" sdnum="2052;">10000</td>
		<td align="center" sdval="10000" sdnum="2052;">10000</td>
		<td align="center">～</td>
		<td align="center">～</td>
		<td align="center">～</td>
		<td align="center">✓</td>
		<td align="center">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
	</tr>
	<tr>
		<td height="20" align="center"><b>CTW</b></td>
		<td align="center">Chinese</td>
		<td align="center" sdval="32285" sdnum="2052;">32285</td>
		<td align="center" sdval="25887" sdnum="2052;">25887</td>
		<td align="center" sdval="6398" sdnum="2052;">6398</td>
		<td align="center" sdval="1018402" sdnum="2052;">1018402</td>
		<td align="center" sdval="812872" sdnum="2052;">812872</td>
		<td align="center" sdval="205530" sdnum="2052;">205530</td>
		<td align="center">✓</td>
		<td align="center">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center">✓</td>
		<td align="center">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
	</tr>
	<tr>
		<td height="20" align="center"><b>RCTW-17</b></td>
		<td align="center">English/Chinese</td>
		<td align="center" sdval="12514" sdnum="2052;">12514</td>
		<td align="center" sdval="15114" sdnum="2052;">15114</td>
		<td align="center" sdval="1000" sdnum="2052;">1000</td>
		<td align="center">～</td>
		<td align="center">～</td>
		<td align="center">～</td>
		<td align="center">✓</td>
		<td align="center">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center">✓</td>
	</tr>
	<tr>
		<td height="20" align="center"><b>ReCTS</b></td>
		<td align="center">Chinese</td>
		<td align="center" sdval="20000" sdnum="2052;">20000</td>
		<td align="center">～</td>
		<td align="center">～</td>
		<td align="center">～</td>
		<td align="center">～</td>
		<td align="center">～</td>
		<td align="center">✓</td>
		<td align="center">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center">✓</td>
		<td align="center">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
	</tr>
	<tr>
		<td height="20" align="center"><b>CUTE80</b></td>
		<td align="center">English</td>
		<td align="center" sdval="80" sdnum="2052;">80</td>
		<td align="center">～</td>
		<td align="center">～</td>
		<td align="center">～</td>
		<td align="center">～</td>
		<td align="center">～</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center">✓</td>
		<td align="center">✓</td>
	</tr>
	<tr>
		<td height="20" align="center"><b>Total-Text</b></td>
		<td align="center">English</td>
		<td align="center" sdval="1525" sdnum="2052;">1525</td>
		<td align="center" sdval="1225" sdnum="2052;">1225</td>
		<td align="center" sdval="300" sdnum="2052;">300</td>
		<td align="center" sdval="9330" sdnum="2052;">9330</td>
		<td align="center">～</td>
		<td align="center">～</td>
		<td align="center">✓</td>
		<td align="center">✓</td>
		<td align="center">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center">✓</td>
		<td align="center">✓</td>
	</tr>
	<tr>
		<td height="20" align="center"><b>CTW-1500</b></td>
		<td align="center">English/Chinese</td>
		<td align="center" sdval="1500" sdnum="2052;">1500</td>
		<td align="center" sdval="1000" sdnum="2052;">1000</td>
		<td align="center" sdval="500" sdnum="2052;">500</td>
		<td align="center" sdval="10751" sdnum="2052;">10751</td>
		<td align="center">～</td>
		<td align="center">～</td>
		<td align="center">✓</td>
		<td align="center">✓</td>
		<td align="center">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center">✓</td>
		<td align="center">✓</td>
	</tr>
	<tr>
		<td height="20" align="center"><b>LSVT</b></td>
		<td align="center">English/Chinese</td>
		<td align="center" sdval="450000" sdnum="2052;">450000</td>
		<td align="center" sdval="430000" sdnum="2052;">430000</td>
		<td align="center" sdval="20000" sdnum="2052;">20000</td>
		<td align="center">～</td>
		<td align="center">～</td>
		<td align="center">～</td>
		<td align="center">✓</td>
		<td align="center">✓</td>
		<td align="center">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center">✓</td>
		<td align="center">✓</td>
	</tr>
  <tr>
    <td height="20" align="center"><b>ArT</b></td>
    <td align="center">English/Chinese</td>
    <td align="center" sdval="450000" sdnum="2052;">10166</td>
    <td align="center" sdval="430000" sdnum="2052;">5603</td>
    <td align="center" sdval="20000" sdnum="2052;">4563</td>
    <td align="center">～</td>
    <td align="center">～</td>
    <td align="center">～</td>
    <td align="center">✓</td>
    <td align="center">✓</td>
    <td align="center">✓</td>
    <td align="center" sdnum="2052;0;@">✕</td>
    <td align="center">✓</td>
    <td align="center">✕</td>
  </tr>
	<tr>
		<td height="20" align="center"><b>Synth80k</b></td>
		<td align="center">English</td>
		<td align="center">80k</td>
		<td align="center">～</td>
		<td align="center">～</td>
		<td align="center">8m</td>
		<td align="center">～</td>
		<td align="center">～</td>
		<td align="center">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center">✓</td>
		<td align="center">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
	</tr>
	<tr>
		<td height="20" align="center"><b>SynthText </b></td>
		<td align="center">English</td>
		<td align="center">800k</td>
		<td align="center">～</td>
		<td align="center">～</td>
		<td align="center">6m</td>
		<td align="center">～</td>
		<td align="center">～</td>
		<td align="center">✓</td>
		<td align="center">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
	</tr>
</table>

<a id="2-summary-of-scene-text-detection-results"></a>
## 2. Summary of Scene Text Detection Resources

<a id="21-comparison-of-methods"></a>

### 2.1 Comparison of Methods
Scene text detection methods can be devided into four parts:

 **(a) Traditional methods;**

 **(b) Segmentation-based methods;**

 **(c) Regression-based methods;**

 **(d) Hybrid methods.**

It is important to notice that:  (1) "Hori" stands for horizontal scene text datasets. (2) "Quad" stands for arbitrary-quadrilateral-text datasets. (3) "Irreg" stands for  irregular scence text datasets. (4) "Traditional method" stands for the methods that don't rely on deep learning.

<a id="#211-traditional-methods"></a>
#### 2.1.1 Traditional Methods

<table cellspacing="0" border="0">
	<colgroup width="106"></colgroup>
	<colgroup span="7" width="85"></colgroup>
	<colgroup width="807"></colgroup>
	<tr>
		<td height="20" align="center"><b><font face="Arial">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Method&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</font></b></td>
		<td align="center"><b><font face="Arial">&nbsp;&nbsp;&nbsp;&nbsp;Model&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</font></b></td>
		<td align="center"><b><font face="Arial">Code</font></b></td>
		<td align="center"><b><font face="Arial">Hori</font></b></td>
		<td align="center"><b><font face="Arial">Quad</font></b></td>
		<td align="center"><b><font face="Arial">Irreg</font></b></td>
		<td align="center"><b><font face="Arial">Source </font></b></td>
		<td align="center"><b><font face="Arial">Time</font></b></td>
		<td align="center"><b><font face="Arial">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Highlight&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</font></b></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Yao et al. [1]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TD-Mixture</font></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2012</font></td>
		<td align="left"><font face="Arial">1) A new dataset MSRA-TD500 and  protocol for evaluation. 2) Equipped a two-level classification scheme and two sets of features extractor.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Yin et al. [2]</font></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TPAMI</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2013</font></td>
		<td align="left"><font face="Arial">Extract Maximally Stable Extremal Regions (MSERs) as character candidates and group them together.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Le et al. [5]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">HOCC</font></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2014</font></td>
		<td align="left"><font face="Arial">HOCC + MSERs</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Yin et al. [7]</font></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TPAMI</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2015</font></td>
		<td align="left"><font face="Arial">Presenting a unified distance metric learning framework for adaptive hierarchical clustering.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Wu et al. [9]</font></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TMM</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2015</font></td>
		<td align="left"><font face="Arial">Exploring gradient directional symmetry at component level for smoothing edge components before text detection. </font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Tian et al. [17]</font></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">IJCAI</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2016</font></td>
		<td align="left"><font face="Arial">Scene text is first detected locally in individual frames and finally linked by an optimal tracking trajectory.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" valign=middle sdnum="2052;0;@"><font face="Arial">Yang et al. [33]</font></td>
		<td align="center" valign=middle><br></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TIP</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2017</font></td>
		<td align="left"><font face="Arial">A text detector will locate character candidates and extract text regions. Then they will linked  by an optimal tracking trajectory.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Times New Roman">Liang et al. [8]</font></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center">✓</td>
		<td align="center"><font face="Arial">TIP</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2015</font></td>
		<td align="left"><font face="Arial">Exploring maxima stable extreme regions along with stroke width transform for detecting candidate text regions.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Times New Roman">Michal et al.[12]</font></td>
		<td align="center"><font face="Arial">FASText</font></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center">✕</td>
		<td align="center"><font face="Arial">ICCV</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2015</font></td>
		<td align="left"><font face="Arial">Stroke keypoints are efficiently detected and then exploited to obtain stroke segmentations.</font></td>
	</tr>
</table>


<a id="212-Pixel-level-methods"></a>
#### 2.1.2 Segmentation-based Methods

<table cellspacing="0" border="0">
	<colgroup width="147"></colgroup>
	<colgroup span="7" width="85"></colgroup>
	<colgroup width="633"></colgroup>
	<tr>
		<td height="20" align="center"><b><font face="Arial">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Method&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</font></b></td>
		<td align="center"><b><font face="Arial">&nbsp;&nbsp;&nbsp;&nbsp;Model&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</font></b></td>
		<td align="center"><b><font face="Arial">Code</font></b></td>
		<td align="center"><b><font face="Arial">Hori</font></b></td>
		<td align="center"><b><font face="Arial">Quad</font></b></td>
		<td align="center"><b><font face="Arial">Irreg</font></b></td>
		<td align="center"><b><font face="Arial">Source </font></b></td>
		<td align="center"><b><font face="Arial">Time</font></b></td>
		<td align="center"><b><font face="Arial">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Highlight&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</font></b></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Li et al. [3]</font></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TIP</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2014</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">(1)develop three novel cues that are tailored for character detection and a Bayesian method for their integration; (2)design a Markov random field model to exploit the inherent dependencies between characters.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Zhang et al. [14]</font></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2016</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Utilizing FCN for salient map detection and  centroid of each character prediction.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Zhu et al. [16]</font></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2016</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Performs a graph-based segmentation of connected components into words (Word-Graph).</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">He et al. [18]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Text-CNN</font></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TIP</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2016</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Developing a new learning mechanism to train the Text-CNN with multi-level and rich supervised information.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Yao et al. [21]</font></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">arXiv</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2016</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Proposing to localize text in a holistic manner, by casting scene text detection as a semantic segmentation problem.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Hu et al. [27]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">WordSup</font></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ICCV</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2017</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Proposing a weakly supervised framework that can utilize word annotations. Then the detected characters are fed to a text structure analysis module.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Wu et al. [28]</font></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ICCV</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2017</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Introducing the border class to the text detection problem for the first time, and validate that the decoding process is largely simplified with the help of text border.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Tang et al.[32]</font></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TIP</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2017</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">A text-aware candidate text region(CTR) extraction model + CTR refinement model.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Dai et al. [35]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">FTSN</font></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">arXiv</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2017</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Detecting and segmenting the text instance jointly and simultaneously, leveraging merits from both semantic segmentation task and region proposal based object detection task.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" valign=middle sdnum="2052;0;@"><font face="Arial">Wang et al. [38]</font></td>
		<td align="center" valign=middle><br></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ICDAR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2017</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">This paper proposes a novel character candidate extraction method based on super-pixel segmentation and hierarchical clustering.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" valign=middle sdnum="2052;0;@"><font face="Arial">Deng et al. [40]</font></td>
		<td align="center" valign=middle sdnum="2052;0;@"><font face="Arial">PixelLink</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">AAAI</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Text instances are first segmented out by linking pixels wthin the same instance together.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Liu et al. [42]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">MCN</font></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Stochastic Flow Graph (SFG) + Markov Clustering.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Lyu et al. [43]</font></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Detect scene text by localizing corner points of text bounding boxes and segmenting text regions in relative positions.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Chu et al. [45]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Border</font></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ECCV</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">The paper presents a novel scene text detection technique that makes use of semantics-aware text borders and bootstrapping based text segment augmentation.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Long et al. [46]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TextSnake</font></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ECCV</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">The paper proposes TextSnake, which is able to effectively represent text instances in horizontal, oriented and curved forms based on symmetry axis.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Yang et al. [47]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">IncepText</font></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">IJCAI</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Designing a novel Inception-Text module and introduce deformable PSROI pooling to deal with multi-oriented text detection.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Yue et al. [48]</font></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">BMVC</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Proposing a general framework for text detection called Guided CNN to achieve the two goals simultaneously.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Zhong et al. [53]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">AF-RPN</font></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">arXiv</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Presenting AF-RPN(anchor-free) as an anchor-free and scale-friendly region proposal network for the Faster R-CNN framework.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Wang et al. [54]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">PSENet</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2019</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Proposing a novel Progressive Scale Expansion Network (PSENet), designed as a segmentation-based detector with multiple predictions for each text instance.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Xu et al.[57]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TextField</font></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">arXiv</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Presenting a novel direction field which can represent scene texts of arbitrary shapes.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Tian et al. [58]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">FTDN</font></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ICIP</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">FTDN is able to segment text region and simultaneously regress text box at pixel-level.</font></td>
	</tr>
	<tr>
		<td height="20" align="center"><font face="Arial">Tian et al. [83]</font></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center"><font face="Arial">CVPR</font></td>
		<td align="center" sdval="2019" sdnum="2052;"><font face="Arial">2019</font></td>
		<td align="left"><font face="Arial">Constraining embedding feature of pixels inside the same text region to share similar properties.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Huang et al. [4]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">MSERs-CNN</font></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ECCV</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2014</font></td>
		<td align="left"><font face="Arial">Combining MSERs with CNN</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Sun et al. [6]</font></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">PR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2015</font></td>
		<td align="left"><font face="Arial">Presenting a robust text detection approach based on color-enhanced CER and neural networks.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" valign=middle sdnum="2052;0;@"><font face="Arial">Baek et al. [62]</font></td>
		<td align="center" valign=middle sdnum="2052;0;@"><font face="Arial">CRAFT</font></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2019</font></td>
		<td align="left"><font face="Arial">Proposing CRAFT effectively detect text area by exploring each character and affinity between characters.</font></td>
	</tr>
</table>

<a id="213-regression-methods"></a>
#### 2.1.3 Regression-based Methods

<table cellspacing="0" border="0">
	<colgroup width="118"></colgroup>
	<colgroup span="7" width="85"></colgroup>
	<colgroup width="797"></colgroup>
	<tr>
		<td height="20" align="center"><b><font face="Arial">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Method&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</font></b></td>
		<td align="center"><b><font face="Arial">&nbsp;&nbsp;&nbsp;&nbsp;Model&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</font></b></td>
		<td align="center"><b><font face="Arial">Code</font></b></td>
		<td align="center"><b><font face="Arial">Hori</font></b></td>
		<td align="center"><b><font face="Arial">Quad</font></b></td>
		<td align="center"><b><font face="Arial">Irreg</font></b></td>
		<td align="center"><b><font face="Arial">Source </font></b></td>
		<td align="center"><b><font face="Arial">Time</font></b></td>
		<td align="center"><b><font face="Arial">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Highlight&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</font></b></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Gupta et al. [15]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">FCRN</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2016</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">(a) Proposing a fast and scalable engine to generate synthetic images of text in clutter; (b) FCRN. </font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Zhong et al. [20]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">DeepText</font></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">arXiv</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2016</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">(a) Inception-RPN; (b) Utilize ambiguous text category (ATC) information and multilevel region-of-interest pooling (MLRP).</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Liao et al. [22]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TextBoxes</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">AAAI</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2017</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Mainly basing SSD object detection framework.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Liu et al. [25]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">DMPNet</font></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2017</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Quadrilateral sliding windows + shared Monte-Carlo method for fast and accurate computing of the polygonal areas + a sequential protocol for relative regression.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">He et al. [26]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">DDR</font></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ICCV</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2017</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Proposing an FCN that has bi-task outputs where one is pixel-wise classification between text and non-text, and the other is direct regression to determine the vertex coordinates of quadrilateral text boundaries.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Jiang et al. [36]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">R2CNN</font></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">arXiv</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2017</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Using the Region Proposal Network (RPN) to generate axis-aligned bounding boxes that enclose the texts with different orientations.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Xing et al. [37]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ArbiText</font></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">arXiv</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2017</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Adopting the circle anchors and incorporating a pyramid pooling module into the Single Shot MultiBox Detector framework.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Zhang et al. [39]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">FEN</font></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">AAAI</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Proposing a refined scene text detector with a novel Feature Enhancement Network (FEN) for Region Proposal and Text Detection Refinement.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Wang et al. [41]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ITN</font></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">ITN is presented to learn the geometry-aware representation encoding the unique geometric configurations of scene text instances with in-network transformation embedding.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Liao et al. [44]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">RRD</font></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">The regression branch extracts rotation-sensitive features, while the classification branch extracts rotation-invariant features by pooling the rotation sensitive features.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Liao et al. [49]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TextBoxes++</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TIP</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Mainly basing SSD object detection framework and it replaces the rectangular box representation in conventional object detector by a quadrilateral or oriented rectangle representation.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">He et al. [50]</font></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TIP</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Proposing a scene text detection framework based on fully convolutional network with a bi-task prediction module.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Ma et al. [51]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">RRPN</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TMM</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">RRPN + RRoI Pooling.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Zhu et al. [55]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">SLPR</font></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">arXiv</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">SLPR regresses multiple points on the edge of text line and then utilizes these points to sketch the outlines of the text.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Deng et al. [56]</font></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">arXiv</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">CRPN employs corners to estimate the possible locations of text instances. And it also designs a embedded data augmentation module inside region-wise subnetwork.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Cai et al. [59]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">FFN</font></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ICIP</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Proposing a Feature Fusion Network to deal with text regions differing in enormous sizes.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Sabyasachi et al. [60]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">RGC</font></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ICIP</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Proposing a novel recurrent architecture to improve the learnings of a feature map at a given time.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Liu et al. [63]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CTD</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">PR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2019</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">CTD + TLOC + PNMS</font></td>
	</tr>
	<tr>
		<td height="20" align="center"><font face="Arial">Xie et al. [79]</font></td>
		<td align="center"><font face="Arial">DeRPN</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center"><font face="Arial">AAAI</font></td>
		<td align="center" sdval="2019" sdnum="2052;"><font face="Arial">2019</font></td>
		<td align="left"><font face="Arial">DeRPN utilizes anchor string mechanism instead of anchor box in RPN.</font></td>
	</tr>
	<tr>
		<td height="20" align="center"><font face="Arial">Wang et al. [82]</font></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center"><font face="Arial">CVPR</font></td>
		<td align="center" sdval="2019" sdnum="2052;"><font face="Arial">2019</font></td>
		<td align="left"><font face="Arial">Text-RPN  + RNN</font></td>
	</tr>
	<tr>
		<td height="20" align="center"><font face="Arial">Liu et al. [84]</font></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center"><font face="Arial">CVPR</font></td>
		<td align="center" sdval="2019" sdnum="2052;"><font face="Arial">2019</font></td>
		<td align="left">CSE mechanism</td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">He et al. [29]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">SSTD</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ICCV</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2017</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Proposing an attention mechanism. Then developing a hierarchical inception module which efficiently aggregates multi-scale inception features.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Tian et al. [11]</font></td>
		<td align="center" sdnum="2052;0;@"><br></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ICCV</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2015</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Cascade boosting detects character candidates, and  the min-cost flow network model get the final result.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Tian et al. [13]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CTPN</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ECCV</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2016</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">1) RPN + LSTM. 2) RPN incorporate a new vertical anchor mechanism and LSTM connects the region to get the final result.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">He et al. [19]</font></td>
		<td align="center" sdnum="2052;0;@"><br></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ACCV</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2016</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">ER detetctor detects regions to get coarse prediction of text regions. Then the local context is aggregated to classify the remaining regions to obtain a final prediction.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Shi et al. [23]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">SegLink</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2017</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Decomposing text into segments and links. A link connects two adjacent segments. </font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Tian et al. [30]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">WeText</font></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ICCV</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2017</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Proposing a weakly supervised scene text detection method (WeText).</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Zhu et al. [31]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">RTN</font></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ICDAR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2017</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Mainly basing CTPN vertical vertical proposal mechanism.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Ren et al. [34]</font></td>
		<td align="center" sdnum="2052;0;@"><br></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TMM</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2017</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Proposing a CNN-based detector. It contains a text structure component detector layer, a spatial pyramid layer, and a multi-input-layer deep belief network (DBN).</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Zhang et al. [10]</font></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
		<td align="center" sdval="2015" sdnum="2052;">2015</td>
		<td align="left" sdnum="2052;0;@"><font face="Arial">The proposed algorithm exploits the symmetry property of character groups and allows for direct extraction of text lines from natural images.</font></td>
	</tr>
</table>

<a id="214-hybrid-methods"></a>
#### 2.1.4 Hybrid Methods

<table cellspacing="0" border="0">
	<colgroup width="118"></colgroup>
	<colgroup width="135"></colgroup>
	<colgroup span="6" width="85"></colgroup>
	<colgroup width="268"></colgroup>
	<tr>
		<td height="20" align="center"><b><font face="Arial">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Method&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</font></b></td>
		<td align="center"><b><font face="Arial">&nbsp;&nbsp;&nbsp;&nbsp;Model&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</font></b></td>
		<td align="center"><b><font face="Arial">Code</font></b></td>
		<td align="center"><b><font face="Arial">Hori</font></b></td>
		<td align="center"><b><font face="Arial">Quad</font></b></td>
		<td align="center"><b><font face="Arial">Irreg</font></b></td>
		<td align="center"><b><font face="Arial">Source </font></b></td>
		<td align="center"><b><font face="Arial">Time</font></b></td>
		<td align="center"><b><font face="Arial">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Highlight&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</font></b></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Tang et al. [52]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">SSFT</font></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TMM</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Proposing a novel scene text detection method that involves superpixel-based stroke feature transform (SSFT) and deep learning based region classification (DLRC).</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Xie et al.[61]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">SPCNet</font></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">AAAI</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2019</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Text Context module + Re-Score mechanism.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Liu et al. [64]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">PMTD</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">arXiv</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2019</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Perform “soft” semantic segmentation. It assigns a soft pyramid label (i.e., a real value between 0 and 1) for each pixel within text instance.</font></td>
	</tr>
	<tr>
		<td height="20" align="center"><font face="Arial">Liu et al. [80]</font></td>
		<td align="center"><font face="Arial">BDN</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center"><font face="Arial">IJCAI</font></td>
		<td align="center" sdval="2019" sdnum="2052;"><font face="Arial">2019</font></td>
		<td align="left"><font face="Arial">Discretizing bouding boxes into key edges to address label confusion for text detection.</font></td>
	</tr>
	<tr>
		<td height="20" align="center"><font face="Arial">Zhang et al. [81]</font></td>
		<td align="center"><font face="Arial">LOMO</font></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center"><font face="Arial">CVPR</font></td>
		<td align="center" sdval="2019" sdnum="2052;"><font face="Arial">2019</font></td>
		<td align="left"><font face="Arial">DR + IRM + SEM</font></td>
	</tr>
	<tr>
		<td height="20" align="center"><font face="Arial">Zhou et al. [24]</font></td>
		<td align="center"><font face="Arial">EAST</font></td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center"><font face="Arial">CVPR</font></td>
		<td align="center"><font face="Arial">2017</font></td>
		<td align="left"><font face="Arial">The pipeline directly predicts words or text lines of arbitrary orientations and quadrilateral shapes in full images with instance segmentation.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Yue et al. [48]</font></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">BMVC</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Proposing a general framework for text detection called Guided CNN to achieve the two goals simultaneously.</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Zhong et al. [53]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">AF-RPN</font></td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✓</td>
		<td align="center" sdnum="2052;0;@">✕</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">arXiv</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td colspan=13 align="left" sdnum="2052;0;@"><font face="Arial">Presenting AF-RPN(anchor-free) as an anchor-free and scale-friendly region proposal network for the Faster R-CNN framework.</font></td>
	</tr>
</table>

<a id="22-detection-result"></a>
### 2.2 Detection Results

<a id="221-Detection-Results-on-Horizontal-Text-Datasets"></a>
#### 2.2.1 Detection Results on Horizontal-Text Datasets

<table cellspacing="0" border="0">
	<colgroup width="192"></colgroup>
	<colgroup span="3" width="85"></colgroup>
	<colgroup width="161"></colgroup>
	<colgroup span="9" width="85"></colgroup>
	<tr>
		<td rowspan=2 height="39" align="center" valign=middle><b>Method&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</b></td>
		<td rowspan=2 align="center" valign=middle><b>Model</b></td>
		<td rowspan=2 align="center" valign=middle><b>Source</b></td>
		<td rowspan=2 align="center" valign=middle><b>Time</b></td>
		<td rowspan=2 align="center" valign=middle><b>Method Category</b></td>
		<td colspan=3 align="center" valign=middle sdnum="2052;0;@"><b><font face="Arial">IC11[68]</font></b></td>
		<td colspan=3 align="center" valign=middle sdnum="2052;0;@"><b><font face="Arial">IC13 [69]</font></b></td>
		<td colspan=3 align="center" valign=middle sdnum="2052;0;@"><b><font face="Arial">IC05[67]</font></b></td>
		</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><b><font face="Arial">P</font></b></td>
		<td align="center" sdnum="2052;0;@"><b><font face="Arial">R</font></b></td>
		<td align="center" sdnum="2052;0;@"><b><font face="Arial">F</font></b></td>
		<td align="center" sdnum="2052;0;@"><b><font face="Arial">P</font></b></td>
		<td align="center" sdnum="2052;0;@"><b><font face="Arial">R</font></b></td>
		<td align="center" sdnum="2052;0;@"><b><font face="Arial">F</font></b></td>
		<td align="center" sdnum="2052;0;@"><b><font face="Arial">P</font></b></td>
		<td align="center" sdnum="2052;0;@"><b><font face="Arial">R</font></b></td>
		<td align="center" sdnum="2052;0;@"><b><font face="Arial">F</font></b></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Yao et al. [1]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TD-Mixture</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2012</font></td>
		<td rowspan=6 align="center" valign=middle sdnum="2052;0;@"><font face="Arial">Traditional </font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.69</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.66</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.67</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Yin et al. [2]</font></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TPAMI</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2013</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.86</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.68</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.76</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Yin et al. [7]</font></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TPAMI</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2015</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.838</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.66</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.738</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Wu et al. [9]</font></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TMM</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2015</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.76</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.70</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.73</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Liang et al. [8]</font></td>
		<td align="center"><br></td>
		<td align="center"><font face="Arial">TIP</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2015</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.77</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.68</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.71</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.76</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.68</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.72</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Michal et al.[12]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">FASText</font></td>
		<td align="center"><font face="Arial">ICCV</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2015</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.84</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.69</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.77</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Li et al. [3]</font></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TIP</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2014</font></td>
		<td rowspan=14 align="center" valign=middle>Segmentation</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.80</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.62</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.70</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Zhang et al. [14]</font></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2016</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.88</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.78</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.83</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">He et al. [18]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Text-CNN</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TIP</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2016</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.91</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.74</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.82</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.93</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.73</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.82</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.87</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.73</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.79</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Yao et al. [21]</font></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">arXiv</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2016</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.889</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.802</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.843</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Hu et al. [27]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">WordSup</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ICCV</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2017</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.933</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.875</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.903</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Tang et al.[32]</font></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TIP</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2017</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.90</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.86</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.88</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.92</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.87</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.89</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" valign=middle sdnum="2052;0;@"><font face="Arial">Wang et al. [38]</font></td>
		<td align="center" valign=middle><br></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ICDAR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2017</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.87</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.78</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.82</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.87</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.82</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.84</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" valign=middle sdnum="2052;0;@"><font face="Arial">Deng et al. [40]</font></td>
		<td align="center" valign=middle sdnum="2052;0;@"><font face="Arial">PixelLink</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">AAAI</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.886</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.875</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.881</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Liu et al. [42]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">MCN</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.88</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.87</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.88</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Lyu et al. [43]</font></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.92</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.844</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.880</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Chu et al. [45]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Border</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ECCV</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.915</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.871</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.892</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Wang et al. [54]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">PSENet</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2019</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.94</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.90</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.92</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Huang et al. [4]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">MSERs-CNN</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ECCV</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2014</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.88</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.71</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.78</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.84</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.67</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.75</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Sun et al. [6]</font></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">PR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2015</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.92</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.91</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.91</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.94</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.92</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.93</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Gupta et al. [15]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">FCRN</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2016</font></td>
		<td rowspan=24 align="center" valign=middle>Regression</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.94</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.77</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.85</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.938</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.764</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.842</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Zhong et al. [20]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">DeepText</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">arXiv</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2016</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.87</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.83</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.85</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.85</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.81</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.83</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Liao et al. [22]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TextBoxes</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">AAAI</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2017</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.89</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.82</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.86</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.89</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.83</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.86</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Liu et al. [25]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">DMPNet</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2017</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.93</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.83</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.870</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Jiang et al. [36]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">R2CNN</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">arXiv</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2017</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.92</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.81</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.86</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Xing et al. [37]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ArbiText</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">arXiv</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2017</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.826</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.936</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.877</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Wang et al. [41]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ITN</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.896</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.889</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.892</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.941</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.893</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.916</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Liao et al. [49]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TextBoxes++</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TIP</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.92</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.86</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.89</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">He et al. [50]</font></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TIP</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.91</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.84</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.88</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Ma et al. [51]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">RRPN</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TMM</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.95</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.89</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.91</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Zhu et al. [55]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">SLPR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">arXiv</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.90</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.72</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.80</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Cai et al. [59]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">FFN</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ICIP</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.92</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.84</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.876</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Sabyasachi et al. [60]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">RGC</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ICIP</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.89</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.77</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.83</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center"><font face="Arial">Wang et al. [82]</font></td>
		<td align="center"><br></td>
		<td align="center"><font face="Arial">CVPR</font></td>
		<td align="center" sdval="2019" sdnum="2052;"><font face="Arial">2019</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdval="0.937" sdnum="2052;"><font face="Arial">0.937</font></td>
		<td align="center" sdval="0.878" sdnum="2052;"><font face="Arial">0.878</font></td>
		<td align="center" sdval="0.907" sdnum="2052;"><font face="Arial">0.907</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center"><font face="Arial">Liu et al. [84]</font></td>
		<td align="center"><br></td>
		<td align="center"><font face="Arial">CVPR</font></td>
		<td align="center" sdval="2019" sdnum="2052;"><font face="Arial">2019</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdval="0.937" sdnum="2052;">0.937</td>
		<td align="center" sdval="0.897" sdnum="2052;">0.897</td>
		<td align="center" sdval="0.917" sdnum="2052;">0.917</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">He et al. [29]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">SSTD</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ICCV</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2017</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.89</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.86</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.88</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Tian et al. [11]</font></td>
		<td align="center" sdnum="2052;0;@"><br></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ICCV</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2015</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.86</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.76</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.81</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.852</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.759</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.802</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Tian et al. [13]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CTPN</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ECCV</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2016</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.93</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.83</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.88</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">He et al. [19]</font></td>
		<td align="center" sdnum="2052;0;@"><br></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ACCV</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2016</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.90</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.75</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.81</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Shi et al. [23]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">SegLink</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2017</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.877</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.83</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.853</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Tian et al. [30]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">WeText</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ICCV</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2017</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.911</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.831</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.869</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Zhu et al. [31]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">RTN</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ICDAR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2017</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.94</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.89</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.91</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Ren et al. [34]</font></td>
		<td align="center" sdnum="2052;0;@"><br></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TMM</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2017</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.78</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.67</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.72</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.81</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.67</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.73</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Zhang et al. [10]</font></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
		<td align="center" sdval="2015" sdnum="2052;">2015</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.84</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.76</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.80</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.88</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.74</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.80</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Tang et al. [52]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">SSFT</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TMM</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td rowspan=6 align="center" valign=middle>Hybrid</td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.906</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.847</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.876</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.911</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.861</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.885</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Xie et al.[61]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">SPCNet</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">AAAI</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2019</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.94</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.91</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.92</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center"><font face="Arial">Liu et al. [80]</font></td>
		<td align="center"><font face="Arial">BDN</font></td>
		<td align="center"><font face="Arial">IJCAI</font></td>
		<td align="center" sdval="2019" sdnum="2052;"><font face="Arial">2019</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.887</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.894</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.89</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center"><font face="Arial">Zhou et al. [24]</font></td>
		<td align="center"><font face="Arial">EAST</font></td>
		<td align="center"><font face="Arial">CVPR</font></td>
		<td align="center"><font face="Arial">2017</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.93</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.83</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.870</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Yue et al. [48]</font></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">BMVC</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.885</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.846</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.870</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Zhong et al. [53]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">AF-RPN</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">arXiv</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.94</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.90</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.92</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
</table>

<a id="222-Detection-Results-on-Arbitrary-Quadrilateral-Text-Datasets"></a>
#### 2.2.2 Detection Results on Arbitrary-Quadrilateral-Text Datasets

<table cellspacing="0" border="0">
	<colgroup width="116"></colgroup>
	<colgroup span="3" width="85"></colgroup>
	<colgroup width="129"></colgroup>
	<colgroup span="7" width="85"></colgroup>
	<colgroup width="141"></colgroup>
	<colgroup span="4" width="85"></colgroup>
	<tr>
		<td rowspan=2 height="39" align="center" valign=middle><b><font face="Arial">Method&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</font></b></td>
		<td rowspan=2 align="center" valign=middle><b><font face="Arial">Model</font></b></td>
		<td rowspan=2 align="center" valign=middle><b>Source</b></td>
		<td rowspan=2 align="center" valign=middle><b>Time</b></td>
		<td rowspan=2 align="center" valign=middle><b>Method Category</b></td>
		<td colspan=3 align="center" valign=middle sdnum="2052;0;@"><b><font face="Arial">IC15 [70]</font></b></td>
		<td colspan=3 align="center" valign=middle sdnum="2052;0;@"><b><font face="Arial">MSRA-TD500 [71]</font></b></td>
		<td colspan=3 align="center" valign=middle sdnum="2052;0;@"><b><font face="Arial">USTB-SV1K [65]</font></b></td>
		<td colspan=3 align="center" valign=middle sdnum="2052;0;@"><b><font face="Arial">SVT [66]</font></b></td>
		</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><b><font face="Arial">P</font></b></td>
		<td align="center" sdnum="2052;0;@"><b><font face="Arial">R</font></b></td>
		<td align="center" sdnum="2052;0;@"><b><font face="Arial">F</font></b></td>
		<td align="center" sdnum="2052;0;@"><b><font face="Arial">P</font></b></td>
		<td align="center" sdnum="2052;0;@"><b><font face="Arial">R</font></b></td>
		<td align="center" sdnum="2052;0;@"><b><font face="Arial">F</font></b></td>
		<td align="center" sdnum="2052;0;@"><b><font face="Arial">P</font></b></td>
		<td align="center" sdnum="2052;0;@"><b><font face="Arial">R</font></b></td>
		<td align="center" sdnum="2052;0;@"><b><font face="Arial">F</font></b></td>
		<td align="center" sdnum="2052;0;@"><b><font face="Arial">P</font></b></td>
		<td align="center" sdnum="2052;0;@"><b><font face="Arial">R</font></b></td>
		<td align="center" sdnum="2052;0;@"><b><font face="Arial">F</font></b></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Le et al. [5]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">HOCC</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2014</font></td>
		<td rowspan=6 align="center" valign=middle><font face="Arial">Traditional</font></td>
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
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Yin et al. [7]</font></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TPAMI</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2015</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.81</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.63</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.71</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.499</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.454</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.475</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Wu et al. [9]</font></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TMM</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2015</font></td>
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
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Tian et al. [17]</font></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">IJCAI</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2016</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.95</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.58</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.721</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.537</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.488</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.51</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" valign=middle sdnum="2052;0;@"><font face="Arial">Yang et al. [33]</font></td>
		<td align="center" valign=middle><br></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TIP</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2017</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.95</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.58</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.72</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.54</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.49</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.51</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Times New Roman">Liang et al. [8]</font></td>
		<td align="center"><br></td>
		<td align="center"><font face="Arial">TIP</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2015</font></td>
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
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Zhang et al. [14]</font></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2016</font></td>
		<td rowspan=18 align="center" valign=middle><font face="Arial">Segmentation</font></td>
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
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Zhu et al. [16]</font></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2016</font></td>
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
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">He et al. [18]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Text-CNN</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TIP</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2016</font></td>
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
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Yao et al. [21]</font></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">arXiv</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2016</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.723</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.587</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.648</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.765</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.753</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.759</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Hu et al. [27]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">WordSup</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ICCV</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2017</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.793</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.77</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.782</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Wu et al. [28]</font></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ICCV</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2017</font></td>
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
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Dai et al. [35]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">FTSN</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">arXiv</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2017</font></td>
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
	</tr>
	<tr>
		<td height="20" align="center" valign=middle sdnum="2052;0;@"><font face="Arial">Deng et al. [40]</font></td>
		<td align="center" valign=middle sdnum="2052;0;@"><font face="Arial">PixelLink</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">AAAI</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
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
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Liu et al. [42]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">MCN</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
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
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Lyu et al. [43]</font></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.895</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.797</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.843</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.876</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.762</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.815</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Chu et al. [45]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Border</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ECCV</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.830</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.774</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.801</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Long et al. [46]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TextSnake</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ECCV</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
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
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Yang et al. [47]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">IncepText</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">IJCAI</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.938</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.873</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.905</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.875</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.790</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.830</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Wang et al. [54]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">PSENet</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2019</font></td>
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
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Xu et al.[57]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TextField</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">arXiv</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
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
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Tian et al. [58]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">FTDN</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ICIP</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
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
	</tr>
	<tr>
		<td height="20" align="center"><font face="Arial">Tian et al. [83]</font></td>
		<td align="center"><br></td>
		<td align="center"><font face="Arial">CVPR</font></td>
		<td align="center" sdval="2019" sdnum="2052;"><font face="Arial">2019</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.883</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.850</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.866</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.842</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.817</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.829</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" valign=middle sdnum="2052;0;@"><font face="Arial">Baek et al. [62]</font></td>
		<td align="center" valign=middle sdnum="2052;0;@"><font face="Arial">CRAFT</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2019</font></td>
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
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Gupta et al. [15]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">FCRN</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2016</font></td>
		<td rowspan=18 align="center" valign=middle><font face="Arial">Regression</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.651</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.599</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.624</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Liu et al. [25]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">DMPNet</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2017</font></td>
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
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">He et al. [26]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">DDR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ICCV</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2017</font></td>
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
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Jiang et al. [36]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">R2CNN</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">arXiv</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2017</font></td>
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
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Xing et al. [37]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ArbiText</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">arXiv</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2017</font></td>
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
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Wang et al. [41]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ITN</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
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
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Liao et al. [44]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">RRD</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.88</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.8</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.838</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.876</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.73</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.79</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Liao et al. [49]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TextBoxes++</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TIP</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.878</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.785</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.829</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">He et al. [50]</font></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TIP</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
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
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Ma et al. [51]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">RRPN</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TMM</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
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
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Zhu et al. [55]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">SLPR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">arXiv</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
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
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Deng et al. [56]</font></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">arXiv</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.89</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.81</font></td>
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
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Sabyasachi et al. [60]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">RGC</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ICIP</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
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
	</tr>
	<tr>
		<td height="20" align="center"><font face="Arial">Wang et al. [82]</font></td>
		<td align="center"><br></td>
		<td align="center"><font face="Arial">CVPR</font></td>
		<td align="center" sdval="2019" sdnum="2052;"><font face="Arial">2019</font></td>
		<td align="center" sdval="0.892" sdnum="2052;"><font face="Arial">0.892</font></td>
		<td align="center" sdval="0.86" sdnum="2052;"><font face="Arial">0.86</font></td>
		<td align="center" sdval="0.876" sdnum="2052;"><font face="Arial">0.876</font></td>
		<td align="center" sdval="0.852" sdnum="2052;"><font face="Arial">0.852</font></td>
		<td align="center" sdval="0.821" sdnum="2052;"><font face="Arial">0.821</font></td>
		<td align="center" sdval="0.836" sdnum="2052;"><font face="Arial">0.836</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">He et al. [29]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">SSTD</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ICCV</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2017</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.80</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.73</font></td>
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
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Tian et al. [13]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CTPN</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ECCV</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2016</font></td>
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
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">He et al. [19]</font></td>
		<td align="center" sdnum="2052;0;@"><br></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ACCV</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2016</font></td>
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
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.73</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.79</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Shi et al. [23]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">SegLink</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2017</font></td>
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
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Tang et al. [52]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">SSFT</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TMM</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td rowspan=8 align="center" valign=middle><font face="Arial">Hybrid</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.541</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.758</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.631</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Xie et al.[61]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">SPCNet</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">AAAI</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2019</font></td>
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
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Liu et al. [64]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">PMTD</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">arXiv</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2019</font></td>
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
	</tr>
	<tr>
		<td height="20" align="center"><font face="Arial">Liu et al. [80]</font></td>
		<td align="center"><font face="Arial">BDN</font></td>
		<td align="center"><font face="Arial">IJCAI</font></td>
		<td align="center" sdval="2019" sdnum="2052;"><font face="Arial">2019</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.881</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.846</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.863</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.87</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.815</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.842</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center"><font face="Arial">Zhang et al. [81]</font></td>
		<td align="center"><font face="Arial">LOMO</font></td>
		<td align="center"><font face="Arial">CVPR</font></td>
		<td align="center" sdval="2019" sdnum="2052;"><font face="Arial">2019</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.878</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.876</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.877</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center"><font face="Arial">Zhou et al. [24]</font></td>
		<td align="center"><font face="Arial">EAST</font></td>
		<td align="center"><font face="Arial">CVPR</font></td>
		<td align="center"><font face="Arial">2017</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.833</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.783</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.807</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.873</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.674</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.761</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Yue et al. [48]</font></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">BMVC</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.866</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.789</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.823</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.691</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.660</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.675</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Zhong et al. [53]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">AF-RPN</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">arXiv</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
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
	</tr>
</table>

<table cellspacing="0" border="0">
	<colgroup width="115"></colgroup>
	<colgroup width="110"></colgroup>
	<colgroup span="2" width="85"></colgroup>
	<colgroup width="123"></colgroup>
	<colgroup span="12" width="85"></colgroup>
	<tr>
		<td rowspan=2 height="39" align="center" valign=middle><b><font face="Arial">Method&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</font></b></td>
		<td rowspan=2 align="center" valign=middle><b><font face="Arial">Model</font></b></td>
		<td rowspan=2 align="center" valign=middle><b>Source</b></td>
		<td rowspan=2 align="center" valign=middle><b>Time</b></td>
		<td rowspan=2 align="center" valign=middle><b>Method Category</b></td>
		<td colspan=3 align="center" valign=middle sdnum="2052;0;@"><b><font face="Arial">COCO-Text [72]</font></b></td>
		<td colspan=3 align="center" valign=middle sdnum="2052;0;@"><b><font face="Arial">RCTW-17 [73]</font></b></td>
		<td colspan=3 align="center" valign=middle sdnum="2052;0;@"><b><font face="Arial">MLT [76]</font></b></td>
		<td colspan=3 align="center" valign=middle sdnum="2052;0;@"><b><font face="Arial">OSTD[77]</font></b></td>
		</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><b><font face="Arial">P</font></b></td>
		<td align="center" sdnum="2052;0;@"><b><font face="Arial">R</font></b></td>
		<td align="center" sdnum="2052;0;@"><b><font face="Arial">F</font></b></td>
		<td align="center" sdnum="2052;0;@"><b><font face="Arial">P</font></b></td>
		<td align="center" sdnum="2052;0;@"><b><font face="Arial">R</font></b></td>
		<td align="center" sdnum="2052;0;@"><b><font face="Arial">F</font></b></td>
		<td align="center" sdnum="2052;0;@"><b><font face="Arial">P</font></b></td>
		<td align="center" sdnum="2052;0;@"><b><font face="Arial">R</font></b></td>
		<td align="center" sdnum="2052;0;@"><b><font face="Arial">F</font></b></td>
		<td align="center" sdnum="2052;0;@"><b><font face="Arial">P</font></b></td>
		<td align="center" sdnum="2052;0;@"><b><font face="Arial">R</font></b></td>
		<td align="center" sdnum="2052;0;@"><b><font face="Arial">F</font></b></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Le et al. [5]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">HOCC</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2014</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">Traditional</font></td>
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
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Yao et al. [21]</font></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">arXiv</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2016</font></td>
		<td rowspan=7 align="center" valign=middle><font face="Arial">Segmentation</font></td>
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
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Hu et al. [27]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">WordSup</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ICCV</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2017</font></td>
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
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Lyu et al. [43]</font></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.351</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.348</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.349</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.743</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.706</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.724</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Chu et al. [45]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">Border</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ECCV</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.782</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.588</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.671</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.777</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.621</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.690</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Yang et al. [47]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">IncepText</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">IJCAI</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
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
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Wang et al. [54]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">PSENet</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2019</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.7535</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.6918</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.7213</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" valign=middle sdnum="2052;0;@"><font face="Arial">Baek et al. [62]</font></td>
		<td align="center" valign=middle sdnum="2052;0;@"><font face="Arial">CRAFT</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2019</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.806</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.682</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.739</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">He et al. [29]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">SSTD</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ICCV</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2017</font></td>
		<td rowspan=8 align="center" valign=middle><font face="Arial">Regression</font></td>
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
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Gupta et al. [15]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">FCRN</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2016</font></td>
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
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Liao et al. [49]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TextBoxes++</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TIP</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
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
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Ma et al. [51]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">RRPN</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TMM</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
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
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Deng et al. [56]</font></td>
		<td align="center"><br></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">arXiv</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
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
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Cai et al. [59]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">FFN</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ICIP</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
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
	</tr>
	<tr>
		<td height="20" align="center"><font face="Arial">Xie et al. [79]</font></td>
		<td align="center"><font face="Arial">DeRPN</font></td>
		<td align="center"><font face="Arial">AAAI</font></td>
		<td align="center" sdval="2019" sdnum="2052;"><font face="Arial">2019</font></td>
		<td align="center" sdval="0.586" sdnum="2052;"><font face="Arial">0.586</font></td>
		<td align="center" sdval="0.557" sdnum="2052;"><font face="Arial">0.557</font></td>
		<td align="center" sdval="0.571" sdnum="2052;"><font face="Arial">0.571</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">He et al. [29]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">SSTD</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ICCV</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2017</font></td>
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
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Xie et al.[61]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">SPCNet</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">AAAI</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2019</font></td>
		<td rowspan=6 align="center" valign=middle><font face="Arial">Hybrid</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.806</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.686</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.741</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Liu et al. [64]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">PMTD</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">arXiv</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2019</font></td>
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
	</tr>
	<tr>
		<td height="20" align="center"><font face="Arial">Liu et al. [80]</font></td>
		<td align="center"><font face="Arial">BDN</font></td>
		<td align="center"><font face="Arial">IJCAI</font></td>
		<td align="center" sdval="2019" sdnum="2052;"><font face="Arial">2019</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.791</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.698</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.742</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center"><font face="Arial">Zhang et al. [81]</font></td>
		<td align="center"><font face="Arial">LOMO</font></td>
		<td align="center"><font face="Arial">CVPR</font></td>
		<td align="center" sdval="2019" sdnum="2052;"><font face="Arial">2019</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.791</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.602</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.684</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.802</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.672</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.731</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
	<tr>
		<td height="20" align="center"><font face="Arial">Zhou et al. [24]</font></td>
		<td align="center"><font face="Arial">EAST</font></td>
		<td align="center"><font face="Arial">CVPR</font></td>
		<td align="center"><font face="Arial">2017</font></td>
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
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Zhong et al. [53]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">AF-RPN</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">arXiv</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
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
	</tr>
</table>

<a id="223-Detection-Results-on-Irregular-Text-Datasets"></a>
#### 2.2.3 Detection Results on Irregular-Text Datasets

In this section, we only select those methods suitable for irregular text detection.

<table cellspacing="0" border="0">
	<colgroup width="111"></colgroup>
	<colgroup span="3" width="85"></colgroup>
	<colgroup width="117"></colgroup>
	<colgroup span="6" width="85"></colgroup>
	<tr>
		<td rowspan=2 height="39" align="center" valign=middle sdnum="2052;0;@"><b><font face="Arial">Method&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</font></b></td>
		<td rowspan=2 align="center" valign=middle sdnum="2052;0;@"><b><font face="Arial">Model</font></b></td>
		<td rowspan=2 align="center" valign=middle><b>Source</b></td>
		<td rowspan=2 align="center" valign=middle><b>Time</b></td>
		<td rowspan=2 align="center" valign=middle><b>Method Category</b></td>
		<td colspan=3 align="center" valign=middle sdnum="2052;0;@"><b><font face="Arial">Total-text [74]</font></b></td>
		<td colspan=3 align="center" valign=middle sdnum="2052;0;@"><b><font face="Arial">SCUT-CTW1500 [75]</font></b></td>
		</tr>
	<tr>
		<td align="center" sdnum="2052;0;@"><b><font face="Arial">P</font></b></td>
		<td align="center" sdnum="2052;0;@"><b><font face="Arial">R</font></b></td>
		<td align="center" sdnum="2052;0;@"><b><font face="Arial">F</font></b></td>
		<td align="center" sdnum="2052;0;@"><b><font face="Arial">P</font></b></td>
		<td align="center" sdnum="2052;0;@"><b><font face="Arial">R</font></b></td>
		<td align="center" sdnum="2052;0;@"><b><font face="Arial">F</font></b></td>
	</tr>
	<tr>
		<td height="20" align="center" valign=middle sdnum="2052;0;@"><font face="Arial">Baek et al. [62]</font></td>
		<td align="center" valign=middle sdnum="2052;0;@"><font face="Arial">CRAFT</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2019</font></td>
		<td rowspan=4 align="center" valign=middle sdnum="2052;0;@"><font face="Arial">Segmentation</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.876</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.799</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.836</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.860</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.811</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.835</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Long et al. [46]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">TextSnake</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">ECCV</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.827</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.745</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.784</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.679</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.853</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.756</font></td>
	</tr>
	<tr>
		<td height="20" align="center">Tian et al. [83]</td>
		<td align="center"><br></td>
		<td align="center"><font face="Arial">CVPR</font></td>
		<td align="center" sdval="2019" sdnum="2052;"><font face="Arial">2019</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdval="81.7" sdnum="2052;">81.7</td>
		<td align="center" sdval="84.2" sdnum="2052;">84.2</td>
		<td align="center" sdval="80.1" sdnum="2052;">80.1</td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Wang et al. [54]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">PSENet</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CVPR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2019</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.840</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.779</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.809</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.848</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.797</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.822</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Zhu et al. [55]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">SLPR</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">arXiv</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2018</font></td>
		<td rowspan=4 align="center" valign=middle sdnum="2052;0;@"><font face="Arial">Regression</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.801</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.701</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.748</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Liu et al. [63]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">CTD+TLOC</font></td>
		<td align="center"><font face="Arial">PR</font></td>
		<td align="center" sdval="2019" sdnum="2052;"><font face="Arial">2019</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.774</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.698</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.734</font></td>
	</tr>
	<tr>
		<td height="20" align="center">Wang et al. [82]</td>
		<td align="center"><br></td>
		<td align="center"><font face="Arial">CVPR</font></td>
		<td align="center" sdval="2019" sdnum="2052;"><font face="Arial">2019</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdval="80.1" sdnum="2052;">80.1</td>
		<td align="center" sdval="80.2" sdnum="2052;">80.2</td>
		<td align="center" sdval="80.1" sdnum="2052;">80.1</td>
	</tr>
	<tr>
		<td height="20" align="center">Liu et al. [84]</td>
		<td align="center"><br></td>
		<td align="center"><font face="Arial">CVPR</font></td>
		<td align="center" sdval="2019" sdnum="2052;"><font face="Arial">2019</font></td>
		<td align="center" sdval="0.814" sdnum="2052;">0.814</td>
		<td align="center" sdval="0.791" sdnum="2052;">0.791</td>
		<td align="center" sdval="0.802" sdnum="2052;">0.802</td>
		<td align="center" sdval="0.787" sdnum="2052;">0.787</td>
		<td align="center" sdval="0.761" sdnum="2052;">0.761</td>
		<td align="center" sdval="0.774" sdnum="2052;">0.774</td>
	</tr>
	<tr>
		<td height="20" align="center">Zhang et al. [81]</td>
		<td align="center">LOMO</td>
		<td align="center"><font face="Arial">CVPR</font></td>
		<td align="center" sdval="2019" sdnum="2052;"><font face="Arial">2019</font></td>
		<td rowspan=2 align="center" valign=middle><font face="Arial">Hybrid</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">87.6</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">79.3</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">83.3</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">85.7</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">76.5</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">80.8</font></td>
	</tr>
	<tr>
		<td height="20" align="center" sdnum="2052;0;@"><font face="Arial">Xie et al.[61]</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">SPCNet</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">AAAI</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Times New Roman">2019</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.83</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.83</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">0.83</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
		<td align="center" sdnum="2052;0;@"><font face="Arial">~</font></td>
	</tr>
</table>


<a id="3-survey"></a>
## 3. Survey

**[A] \[TPAMI-2015]** Ye Q, Doermann D. **Text detection and recognition in imagery: A survey**[J]. IEEE transactions on pattern analysis and machine intelligence, 2015, 37(7): 1480-1500. [paper](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=6945320)

**[B] \[Frontiers-Comput. Sci-2016]** Zhu Y, Yao C, Bai X. **Scene text detection and recognition: Recent advances and future trends**[J]. Frontiers of Computer Science, 2016, 10(1): 19-36. [paper](https://link.springer.com/article/10.1007/s11704-015-4488-0)

**[C] \[arXiv-2018]** Long S, He X, Ya C. **Scene Text Detection and Recognition: The Deep Learning Era**[J]. arXiv preprint arXiv:1811.04256, 2018. [paper](https://arxiv.org/pdf/1811.04256.pdf)

<a id="4-Evaluation"></a>
## 4. Evaluation

If you are insterested in developing better scene text detection metrics, some references recommended here might be useful.

**[A]** Wolf, Christian, and Jean-Michel Jolion. "**Object count/area graphs for the evaluation of object detection and segmentation algorithms.**" International Journal of Document Analysis and Recognition (IJDAR) 8.4 (2006): 280-296. [paper](https://link.springer.com/article/10.1007/s10032-006-0014-0)

**[B]** D. Karatzas, L. Gomez-Bigorda, A. Nicolaou, S. K. Ghosh, A. D.Bagdanov, M. Iwamura, J. Matas, L. Neumann, V. R. Chandrasekhar, S. Lu, F. Shafait, S. Uchida, and E. Valveny. **ICDAR 2015 competition on robust reading**. In ICDAR, pages 1156–1160, 2015. [paper](https://ieeexplore.ieee.org/document/7333942)

**[C]** Calarasanu, Stefania, Jonathan Fabrizio, and Severine Dubuisson. "**What is a good evaluation protocol for text localization systems? Concerns, arguments, comparisons and solutions.**" Image and Vision Computing 46 (2016): 1-17. [paper](https://www.sciencedirect.com/science/article/pii/S0262885615001377)

**[D]** Shi, Baoguang, et al. "**ICDAR2017 competition on reading chinese text in the wild (RCTW-17).**" 2017 14th IAPR International Conference on Document Analysis and Recognition (ICDAR). Vol. 1. IEEE, 2017. [paper](https://ieeexplore.ieee.org/abstract/document/8270164)

**[E]** Nayef, N; Yin, F; Bizid, I; et al. **ICDAR2017 robust reading challenge on multi-lingual scene text detection and script identiﬁcation-rrc-mlt**. In Document Analysis and Recognition (ICDAR), 2017 14th IAPR International Conference on, volume 1, 1454–1459. IEEE.
[paper](https://ieeexplore.ieee.org/document/8270168)

**[F]** Dangla, Aliona, et al. "**A first step toward a fair comparison of evaluation protocols for text detection algorithms.**" 2018 13th IAPR International Workshop on Document Analysis Systems (DAS). IEEE, 2018. [paper](https://ieeexplore.ieee.org/abstract/document/8395220)

**[G]** He,Mengchao and Liu, Yuliang, et al. **ICPR2018 Contest on Robust Reading for Multi-Type Web images.** ICPR 2018. [paper](https://www.researchgate.net/publication/329316151_ICPR2018_Contest_on_Robust_Reading_for_Multi-Type_Web_Images)

**[H]** Liu, Yuliang and Jin, Lianwen, et al. "**Tightness-aware Evaluation Protocol for Scene Text Detection**" Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition (CVPR). 2019. [paper](https://arxiv.org/abs/1904.00813) [code](https://github.com/Yuliang-Liu/TIoU-metric)



<a id="5-ocr-service"></a>
## 5. OCR Service

|                             OCR                              | API  | Free |
| :----------------------------------------------------------: | :--: | :--: |
| [Tesseract OCR Engine](https://github.com/tesseract-ocr/tesseract) |  ×   |  √   |
| [Azure](https://azure.microsoft.com/zh-cn/services/cognitive-services/computer-vision/#Analysis) |  √   |  √   |
| [ABBYY](https://www.abbyy.cn/real-time-recognition-sdk/technical-specifications/) |  √   |  √   |
|               [OCR Space](https://ocr.space/)                |  √   |  √   |
|       [SODA PDF OCR](https://www.sodapdf.com/ocr-pdf/)       |  √   |  √   |
|          [Free Online OCR](https://www.newocr.com/)          |  √   |  √   |
|           [Online OCR](https://www.onlineocr.net/)           |  √   |  √   |
|             [Super Tools](https://www.wdku.net/)             |  √   |  √   |
|          [Online Chinese Recognition](http://chongdata.com/ocr/)           |  √   |  √   |
|   [Calamari OCR](https://github.com/Calamari-OCR/calamari)   |  ×   |  √   |
|   [Tencent OCR](https://cloud.tencent.com/product/ocr?lang=cn)   |  √   |  ×   |


<a id="6-references"></a>
## 6. References and Code

|                                                     |
| -- |
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
| **[63]** Yuliang L, Lianwen J, Shuaitao Z, et al. **Curved Scene Text Detection via Transverse and Longitudinal Sequence Connection**. Pattern Recognition, 2019. [Paper](https://arxiv.org/abs/1712.02170) [Code](https://github.com/Yuliang-Liu/Curve-Text-Detector) |
| **[64]** Jingchao Liu, Xuebo Liu, et al, **Pyramid Mask Text Detector**. arXiv preprint arXiv:1903.11800, 2019. [Paper](https://arxiv.org/abs/1903.11800) [Code](https://github.com/STVIR/PMTD) |
| **[79]** Lele Xie, Yuliang Liu, Lianwen Jin, Zecheng Xie, **DeRPN: Taking a further step toward more general object detection**. In AAAI, 2019. [Paper](https://arxiv.org/abs/1811.06700) [Code](https://github.com/HCIILAB/DeRPN)|
| **[80]** Yuliang Liu, Lianwen Jin, et al, **Omnidirectional Scene Text Detction with Sequential-free Box Discretization**. In IJCAI, 2019.[Paper](https://arxiv.org/abs/1906.02371) [Code](https://github.com/Yuliang-Liu/Box_Discretization_Network)|
| **[81]** Chengquan Zhang, Borong Liang, et al, **Look More Than Once: An Accurate Detector for Text of Arbitrary Shapes**. In CVPR, 2019.[Paper](https://arxiv.org/abs/1904.06535)|
| **[82]** Xiaobing Wang, Yingying Jiang, et al, **Arbitrary Shape Scene Text Detection with Adaptive Text Region Representation**. In CVPR, 2019. [Paper](https://arxiv.org/abs/1905.05980?context=cs.CV)|
| **[83]** Zhuotao Tian, Michelle Shu, et al, **Learning Shape-Aware Embedding for Scene Text Detection**. In CVPR, 2019. [Paper](http://jiaya.me/papers/textdetection_cvpr19.pdf)|
| **[84]** Zichuan Liu, Guosheng Lin, et al, **Towards Robust Curve Text Detection with Conditional Spatial Expansion**. In CVPR, 2019. [Paper](https://arxiv.org/abs/1903.08836)|
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Datasets** |
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
| **SCUT-CTW1500[75]**：Yuliang L, Lianwen J, Shuaitao Z, et al. **Curved Scene Text Detection via Transverse and Longitudinal Sequence Connection**. Pattern Recognition, 2019.[Paper](https://arxiv.org/abs/1712.02170) |
| **MLT 2017[76]**:  Nayef, N; Yin, F; Bizid, I; et al. **ICDAR2017 robust reading challenge on multi-lingual scene text detection and script identiﬁcation-rrc-mlt**. In Document Analysis and Recognition (ICDAR), 2017 14th IAPR International Conference on, volume 1, 1454–1459. IEEE. [Paper](https://ieeexplore.ieee.org/document/8270168) |
| **OSTD[77]**: Chucai Yi and YingLi Tian, **Text string detection from natural scenes by structure-based partition and grouping**, In IEEE Transactions on Image Processing, vol. 20, no. 9, pp. 2594–2605, 2011. [Paper](https://ieeexplore.ieee.org/abstract/document/5729827) |
| **CTW[78]**: Yuan T L, Zhu Z, Xu K, et al. **Chinese Text in the Wild**. arXiv preprint arXiv:1803.00085, 2018. [Paper](https://arxiv.org/abs/1803.00085) |


If you find any problems in our resources, or any good papers/codes we have missed, please inform us at    **liuchongyu1996@gmail.com**. Thank you for your contribution. 



### Copyright

Copyright © 2019 SCUT-DLVC. All Rights Reserved.

<p align="center">
    <img src="scut-dlvc.jpeg" alt="Sample"  width="150" height="75">
    <p align="center">
        <em></em>
    </p>
</p>
