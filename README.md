<div align="center">
  <img src="/img/logo.jpg" alt="Logo" width="600">
</div>

# 🀄 GuoFeng Webnovel: A Discourse-Level and Multilingual Corpus of Web Fiction

<div align="center">
<img src="https://img.shields.io/badge/License-CC%20BY%204.0-green.svg" alt="License">
<img src="https://img.shields.io/github/stars/longyuewangdcu/GuoFeng-Webnovel?color=yellow" alt="Stars">
<img src="https://img.shields.io/github/issues/longyuewangdcu/GuoFeng-Webnovel?color=red" alt="Issues">


<!-- **Affiliations:** -->

<br>

**¹ Tencent AI Lab, ² China Literature Ltd.**

_<sup>*</sup>**Longyue Wang**¹ is the corresponding author: [vinnlywang@tencent.com](mailto:{vinnlywang@tencent.com)_
</div>

<div align="left">  

GuoFeng Webnovel is a publicly copyrighted, high-quality, discourse-level and multilingual corpus of web fiction. Specifically, its distinguishing feature lies in:
- **Rich Linguistic and Cultural Phenomena**: literary texts contain more complex linguistic and cultural knowledge than non-literary ones.
- **Long-Range Context**: literature such as novels have much longer contexts than texts in other domains.
- **Artificial General Intelligence**: we anticipate that this dataset will not only advance existing research in the fields of machine translation but also inspire novel studies with Large Language Models.

## News 🤩🤩🤩

- \[20/05/2024\] 🛰️🛰️🛰️ **GuoFeng Webnovel Corpus V2** is released: two discourse-level datasets for **Chinese→German** and **Chinese→Russian**.
- \[15/05/2023\] WMT23 Shared Task: Discourse-Level Literary Translation
- \[15/05/2024\] 🎉🎉🎉 GuoFeng Github is online now 🎉🎉🎉
- \[06/05/2023\] 🚀🚀🚀 **GuoFeng Webnovel Corpus V1** is released: a discourse-level dataset with sentence-level alignment for **Chinese→English**. 
- \[14/04/2023\] WMT23 Shared Task: Discourse-Level Literary Translation

### Overview of GuoFeng Webnovel Corpus 💕

The dataset covers **14 genres** such as fantasy science and romance. The detailed statistics are shown as follows.

<div align="center">
  <img src="/img/domain-distribution.jpg" alt="domain" width="600">
</div>

The **word cloud** of high-frequency words in different langauges as shown follows.

<div align="center">
  <img src="/img/word-map.png" alt="word" width="800">
</div>

The **data example** sampled from Chinese-English set, and the colored words demonstrate rich linguistic phenomena.

<div align="center">
  <img src="/img/dis-example.png" alt="word" width="500">
</div>

## Copyright and Licence
Copyright is a crucial consideration when it comes to releasing literary texts, and we (Tencent AI Lab and China Literature Ltd.) are the rightful copyright owners of the web fictions included in this dataset. We are pleased to make this data available to the research community, subject to certain terms and conditions.

- 🔔 GuoFeng Webnovel Corpus is copyrighted by Tencent AI Lab and China Literature Limited. 
- 🚦 After completing the registration process with your institute information, WMT participants or researchers are granted permission to use the dataset solely for non-commercial research purposes and must comply with the principles of fair use ([CC-BY 4.0](https://creativecommons.org/licenses/by/4.0)). 
- 🔒 Modifying or redistributing the dataset is strictly prohibited. If you plan to make any changes to the dataset, such as adding more annotations, with the intention of publishing it publicly, please contact us first to obtain written consent.
- 🚧 By using this dataset, you agree to the terms and conditions outlined above. We take copyright infringement very seriously and will take legal action against any unauthorized use of our data.  

### Citation ❗❗❗
📝 If you use the GuoFeng Webnovel Corpus, please cite the following papers and claim the original download link:

```bibtex
@inproceedings{wang2023findings,
  title={Findings of the WMT 2023 Shared Task on Discourse-Level Literary Translation: A Fresh Orb in the Cosmos of LLMs},
  author={Wang, Longyue and Tu, Zhaopeng and Gu, Yan and Liu, Siyou and Yu, Dian and Ma, Qingsong and Lyu, Chenyang and Zhou, Liting and Liu, Chao-Hong and Ma, Yufeng and others},
  booktitle={Proceedings of the Eighth Conference on Machine Translation},
  pages={55--67},
  year={2023}
}

@inproceedings{wang2024findings,
  title={Findings of the WMT 2024 Shared Task on Discourse-Level Literary Translation},
  author={Wang, Longyue and Liu, Siyou and Wu, Minghao and Jiao, Wenxiang and Wang, Xing and Xu, Jiahao and Tu, Zhaopeng and Zhou, Liting and Gu, Yan and Chen, Weiyu and Koehn, Philipp and Way, Andy and Yuan, Yulin},
  booktitle={Proceedings of the Ninth Conference on Machine Translation},
  year={2024}
}

Download Link: https://github.com/longyuewangdcu/GuoFeng-Webnovel.
```

## Data Processing

💌 The web novels are originally written in Chinese by novel writers and then translated into other languages by professional translators. Taking Chinese-English for instance, we processed the data using automatic and manual methods:
1. we match Chinese books with its English counterparts based on bilingual titles; 
2. within each book, Chinese-English chapters are aligned using Chapter ID numbers; 
3. within each chapter, we build a MT-based sentence aligner to align sentences in parallel, preserving the sentence order in the chapter; 
4. human annotators are engaged to review and correct any discrepancies in sentence-level alignment.

💡 Note that:
1. Some sentences may have no aligned translations because human translators translate novels in a document way;
2. For Chinese-German and Chinese-Russian, we currently skip 3~4 steps and only keep chapter-level parallel data. The current version may contain some translation errors, e.g. mistranslation.

<div align="center">
  <img src="/img/data-create.jpg" alt="Logo" width="300">
</div>

## Data Description (GuoFeng Webnovel Corpus V1)

### **Chinese→English**

We release 22,567 continuous chapters from 179 web novels, covering 14 genres such as fantasy science and romance. **The data are document-level with cross-sentence alignment information.** The data statistics are listed as follows. 

| Table1   | Book | Chapter | Sentence | Notes |
| -- | ---- | ------- | -------- | ----- |
| Train	|179|22,567   |	1,939,187|covering 14 genres |
| Valid |1	|22       |	22	755	 |same books with Train |
| Test  |1	|26	      |22	697	   |same books with Train |
| Valid |2	|10	      |10	853	   |different books with Train |
| Test  |2	|12	      |12	917	   |different books with Train |
| Testing Input | - | - | - | TBA |

### Data Format 💾
Taking "train.en" for exaple, the data format is shown as follows: **&lt;BOOK id=""&gt; &lt;/BOOK&gt;** indicates a book boundary, which contains a number of continous chapters with the tag **\<CHAPTER id=""\> \</CHAPTER\>**. The contents are splited into sentences and manually aligned to Chinese sentences in "train.zh".

```HTML
<BOOK id="100-jdxx">
<CHAPTER id="jdxx_0001">
Chapter 1 Make Your Choice, Youth
"Implode reality, pulverize thy spirit. By banishing this world, comply with the blood pact, I will summon forth thee, O' young Demon King!"
At a park during sunset, a childlike, handsome youth placed his left hand on his chest, while his right hand was stretched out with his fingers wide open, as though he was about to release something amazing from his palm. He looked serious and solemn.
... ...
</CHAPTER>
<CHAPTER id="jdxx_0002">
....
</CHAPTER>
</BOOK>
```

## Data Description (GuoFeng Webnovel Corpus V2)

We release ~19K continuous chapters from ~120 web novels, covering 14 genres such as fantasy science and romance. **The data are document-level without alignment information**. The data statistics are listed as follows.

**Chinese→German**

|**Subset** | **# Book**| **# Chapter** | **# Word** | **Notes**|
| -- | ---- | ------- | -------- | ----- |
|Train | 118 | 19,101 | DE: 25,562,039 | covering 14 genres|
|Valid | -- | -- | -- | --|
|Test | -- | -- | -- | --|
|Testing Input | -- | -- | -- | --|


**Chinese→Russian**

|**Subset** | **# Book**| **# Chapter** | **# Word** | **Notes**|
| -- | ---- | ------- | -------- | ----- |
|Train | 122 | 19,971 | RU: 23,521,169 | covering 14 genres|
|Valid | -- | -- | -- | --|
|Test | -- | -- | -- | --|
|Testing Input | -- | -- | -- | --|

### Data Format 💾

```HTML
.
    ├── 1-ac                       # Book ID - English Title
    │   ├── 15-jlws_0001-CH.txt    # Chapter ID - Chinese
    │   ├── 15-jlws_0001-DE.txt    # Chapter ID - German
    │   ├── ......                 # more chapters
    ├── 2-ccg                      # Book ID - English Title
    │   ├── 62-xzltq_0002-CH.txt   # Chapter ID - Chinese
    │   ├── 62-xzltq_0002-DE.txt   # Chapter ID - German
    │   ├── ......                 # more chapters
    ├── ......                     # more books
	
15-jlws_0001-CH.txt

第一章 李戴
李戴走出考场，穿梭在密密麻麻的人群当中。看着周围那一张张春风得意的脸，耳边响起路人兴高采烈的讨论声，李戴心中却愈加的沮丧。
“哎，考砸了！想进入到面试是肯定没戏了。”李戴揉了揉太阳穴，头脑中那种沉甸甸的感觉却愈发的浓郁。

15-jlws_0001-DE.txt

Kapitel 1: Li Dai
Li Dai verließ das Prüfungszentrum und bewegte sich durch die dichte Menschenmenge. Er sah die triumphierenden Gesichter um ihn herum und hörte die enthusiastischen Diskussionen der Passanten, doch in seinem Herzen wurde er immer deprimierter.
"Oh, ich habe die Prüfung vergeigt! Eine Chance auf ein Vorstellungsgespräch gibt es sicherlich nicht mehr." Li Dai massierte seine Schläfen, das schwere Gefühl in seinem Kopf wurde immer intensiver.
```

### Pretrained Models 🔢
We provide three types of in-domain pretrained models (same as last year) and large language models (new in this year):

| Version | Layer | Hidden Size | Vocab | Continuous Train |
| ------- | ----- | ----------- | ----- | ---------------- |
| Chinese-Llama-2-7B | 32 | 4096 | 32000 | Chinese and English literary texts (115B tokens) |
| RoBERTa | base | 12 enc | 768 | 21128 |
| Chinese literary text (84B tokens) | mBARTCC25 | 12 enc + 12 dec | 1024 | 250000 |

## Download ⏬

### Data Download 👨‍👩

🎈 <a href="https://forms.gle/YqJPkfLgGmACbnbU6" style="text-decoration: none;">
  <button style="background-color: #4CAF50; color: white; padding: 10px 20px; text-align: center; text-decoration: none; display: inline-block; font-size: 16px; margin: 4px 2px; cursor: pointer; border: none; border-radius: 8px;">
    Download GuoFeng Webnovel Corpus (via Google Form and Dropbox)
  </button>🎈
</a>
<br>
🎈 <a href="https://docs.qq.com/form/page/DSUxDa1F3VWFmbnVT" style="text-decoration: none;">
  <button style="background-color: #4CAF50; color: white; padding: 10px 20px; text-align: center; text-decoration: none; display: inline-block; font-size: 16px; margin: 4px 2px; cursor: pointer; border: none; border-radius: 8px;">
    Download GuoFeng Webnovel Corpus (via Tencent Form and Weiyun)
  </button>🎈
</a>

### Models Download 🤖

🎈 <a href="https://github.com/longyuewangdcu/Chinese-Llama-2" style="text-decoration: none;">
  <button style="background-color: #4CAF50; color: white; padding: 10px 20px; text-align: center; text-decoration: none; display: inline-block; font-size: 16px; margin: 4px 2px; cursor: pointer; border: none; border-radius: 8px;">
    Download Chinese-Llama-2
  </button>
</a>🎈
<br>
🎈 <a href="https://www.dropbox.com/sh/1qvukp4cmhp36t4/AABKjGLa9rmDs-NQkA0zWHoKa?Submit=Click+here+to+download+the+models" style="text-decoration: none;">
  <button style="background-color: #4CAF50; color: white; padding: 10px 20px; text-align: center; text-decoration: none; display: inline-block; font-size: 16px; margin: 4px 2px; cursor: pointer; border: none; border-radius: 8px;">
    Download RoBERTa & mBART
  </button>
</a> 🎈


## Committee 
### Data Team 🧑🏻‍💼
[Longyue Wang*](http://longyuewang.com/) ([vincentwang0229@gmail.com](mailto:vincentwang0229@gmail.com)) (Tencent AI Lab)  
[Zhaopeng Tu](http://www.zptu.net/) (Tencent AI Lab)  
[Yan Gu](https://github.com/drow931) (China Literature Limited)  
Weiyu Chen (China Literature Limited)  

### Technical Team 🧑‍🏫 
[Jiahao Xu](https://lemaoliu.github.io/homepage/lat.html) (Tencent AI Lab)
[Wenxiang Jiao](https://wxjiao.github.io/) (Tencent AI Lab)
[Xiang Wang](https://www.xingwang4nlp.com/) (Tencent AI Lab)

### Contact ☎️ 
If you have any further questions or suggestions, please do not hesitate to send an email to **Longyue Wang (vincentwang0229@gmail.com or vinnylywang@tencent.com)**.


## Sponsors 🙏🙏🙏
<div align="center">
  <img src="/img/literary-translation-task-logo1.png" alt="Logo" width="250">
  <img src="/img/literary-translation-task-logo2.png" alt="Logo" width="250">
</div>