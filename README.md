<div align="center">
  <img src="/img/logo.jpg" alt="Logo" width="600">
</div>

# GuoFeng Webnovel: A Discourse-Level and Multilingual Corpus of Web Fiction

<div align="center">
<img src="https://img.shields.io/badge/License-CC%20BY%204.0-green.svg" alt="License">
<img src="https://img.shields.io/github/stars/lyuchenyang/Macaw-LLM?color=yellow" alt="Stars">
<img src="https://img.shields.io/github/issues/lyuchenyang/Macaw-LLM?color=red" alt="Issues">


<div align="left">  


GuoFeng Webnovel is a discourse-level and multilingual corpus of web fiction in three directions: **Chinese→English**, **Chinese→German**, **Chinese→Russian**.
Specifically,

- **GuoFeng Webnovel Corpus v1:** a in-domain, discourse-level and human-translated training dataset with sentence-level alignment for Chinese→English.
- **GuoFeng Webnovel Corpus v2:** two in-domain and discourse-level training dataset for Chinese→German and Chinese→Russian.

## Copyright and Licence
Copyright is a crucial consideration when it comes to releasing literary texts, and we (Tencent AI Lab and China Literature Ltd.) are the rightful copyright owners of the web fictions included in this dataset. We are pleased to make this data available to the research community, subject to certain terms and conditions.

- 🔔 GuoFeng Webnovel Corpus is copyrighted by Tencent AI Lab and China Literature Limited. 
- 🚦 After completing the registration process with your institute information, WMT participants or researchers are granted permission to use the dataset solely for non-commercial research purposes and must comply with the principles of fair use (CC-BY 4.0). 
- 🔒 Modifying or redistributing the dataset is strictly prohibited. If you plan to make any changes to the dataset, such as adding more annotations, with the intention of publishing it publicly, please contact us first to obtain written consent.    
- 🚧 By using this dataset, you agree to the terms and conditions outlined above. We take copyright infringement very seriously and will take legal action against any unauthorized use of our data.  

### Important!
📝 If you use our datasets, please cite the following papers and claim the original download link (http://www2.statmt.org/wmt23/literary-translation-task.html):

- Longyue Wang, ‪Chenyang Lyu, Zefeng Du, Dian Yu, Liting Zhou, Siyou Liu, ‪Yan Gu, Yufeng Ma, Weiyu Chen, Yulin Yuan, Bonnie Webber, Philipp Koehn, Yvette Graham, Andy Way, Shuming Shi, Zhaopeng Tu. Findings of the WMT 2023 Shared Task on Discourse-Level Literary Translation. Proceedings of the Eighth Conference on Machine Translation (WMT). 2023. [bib]  
- Longyue Wang, Zefeng Du, DongHuai Liu, Deng Cai, Dian Yu, Haiyun Jiang, Yan Wang, Shuming Shi, Zhaopeng Tu. GuoFeng: A Discourse-aware Evaluation Benchmark for Language Understanding, Translation and Generation. 2023. [bib]

## Description (GuoFeng Webnovel Corpus)

<div align="center">
  <img src="/img/data-create.jpg" alt="Logo" width="300">
</div>

💌 The web novels are originally written in Chinese by novel writers and then translated into English by professional translators. As shown in Figure 2, we processed the data using automatic and manual methods:
1. align Chinese books with their English versions by title information;
2. In each book, align Chinese-English chapters according to Chapter ID numbers;
3. Build an MT-based sentence aligner to generate parallel sentences;
4. ask human annotators to check and revise the alignment errors.

💡 Note that:
1. some sentences may have no aligned translations because human translators translate novels in a document way;
2. we keep all document-level information such as continuous chapters and sentences.

## Download  
We release 22,567 continuous chapters from 179 web novels, covering 14 genres such as fantasy science and romance. The data statistics are listed in Table 1.

| Table1   | Book | Chapter | Sentence | Notes |
| -- | ---- | ------- | -------- | ----- |
| Train	|179|22,567   |	1,939,187|covering 14 genres |
| Valid |1	|22       |	22	755	 |same books with Train |
| Test  |1	|26	      |22	697	   |same books with Train |
| Valid |2	|10	      |10	853	   |different books with Train |
| Test  |2	|12	      |12	917	   |different books with Train |
| Testing Input | - | - | - | - |

[**Click here to download the corpus (via Google Form)**](https://docs.google.com/forms/d/e/1FAIpQLSeopt1UqpJXoRysLtxJW7ZzHeVvBEyHjqFN_pebWG_jlF9Ahw/viewform?usp=sf_link)
[**Click here to download the corpus (via Tencent Form)**](https://docs.qq.com/form/page/DSWttd3pkR3RZdWtj)


### Data Format
Taking "train.en" for exaple, the data format is shown as follows: <font color=red> &lt;BOOK id=""&gt; &lt;/BOOK&gt; </font> indicates a book boundary, which contains a number of continous chapters with the tag <font color=blue> \<CHAPTER id=""\> \</CHAPTER\></font>. The contents are splited into sentences and manually aligned to Chinese sentences in "train.zh".

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


## COMMITTEE
### Organization Team
‪Longyue Wang (vincentwang0229@gmail.com) (Tencent AI Lab)  
Zhaopeng Tu (Tencent AI Lab)  
Dian Yu (Tencent AI Lab)  
Shuming Shi (Tencent AI Lab)  
‪Yan Gu (China Literature Limited)  
Yufeng Ma (China Literature Limited)  
Weiyu Chen (China Literature Limited)  

### Evaluation Team
‪Liting Zhou (Dublin City University)  
‪Chenyang Lyu (Dublin City University)  
‪Siyou Liu (Macao Polytechnic University)  
‪Zefeng Du (University of Macau)  

### Advisory Committee
Yulin Yuan (University of Macau)  
Bonnie Webber (University of Edinburgh)  
Philipp Koehn (Johns Hopkins University)  
Andy Way (Dublin City University)  
Yvette Graham (Trinity College Dublin)  

## Sponsors
<div align="center">
  <img src="/img/literary-translation-task-logo1.png" alt="Logo" width="200">
  <img src="/img/literary-translation-task-logo2.png" alt="Logo" width="200">
</div>


## TASK DESCRIPTION
The shared task will be the translation of web fiction texts in three directions: Chinese→English, Chinese→German, Chinese→Russian.

#### First, Participants will be provided with two types of training datasets:
- **GuoFeng Webnovel Corpus v1**: we release an in-domain, discourse-level, and human-translated training dataset with sentence-level alignment for Chinese→English (same as last year).
- **GuoFeng Webnovel Corpus v2**: we release two in-domain and discourse-level training datasets for Chinese→German and Chinese→Russian (new in this year).
- **General MT Track Parallel Training Data**: you can use all sentence-/document-level parallel training data of the general translation task (please go to General MT).

#### Second, we provide two types of validation/testing datasets:
- **Simple Set** contains unseen chapters in the same web novels as the training data.
- **Difficult Set** contains chapters in different web novels from the training data.

#### Third, we provide two types of in-domain pretrained models for Chinese→English (same as last year). You can also use the WMT allowed general-domain LMs/LLMs:
- **Chinese-Llama-2 (7B)**: The Llama-2 model is continuously pretrained on 400GB Chinese and English literary texts, and then fine-tuned on the Chinese instruction dataset (BAAI/COIG) and Chinese-English Document-level translation dataset, without changing the vocabulary.
- **In-domain RoBERTa (base)**: 12 layer encoder, hidden size 768, vocabulary size 21,128, whole word masking. It was originally pretrained on Chinese Wikipedia. We continuously train it with Chinese literary texts (84B tokens).
- **In-domain mBART (CC25)**: 12 layer encoder and 12 layer decoder, hidden size 1024, vocabulary size 250,000. It was originally trained with 25 language web corpus. We continuously train it with English and Chinese literary texts (114B tokens).
- **General-domain LMs/LLMs**: Llama-2-7B, Llama-2-13B, Mistral-7B; mBART, BERT, RoBERTa, XLM-RoBERTa, sBERT, LaBSE (please go to The limitations for the constrained systems track).

#### In the final testing stage, participants use their systems to translate an official testing set (mixed with Simple and Difficult unseen testsets). The translation quality is measured as follows. All systems will be ranked by human judgement or A/B testing according to our professional guidelines.
- manual evaluation by human translators, e.g. MQM;
- automatic evaluation metrics with two references;
- A/B testing by web fiction readers (new in this year).

#### Besides, The task has Constrained Track and Unconstrained Track with different constraints on the training of the models. Participants can submit either constrained or unconstrained systems with flags, and we will distinguish their submissions. For example, if you fine-tuned Llama-2-7B on the above data, it is Constrained Tack.
- **Constrained Tack**: You may ONLY use the training data specified above.
- **Unconstrained Tack**: It allows the participation with a system trained without any limitations.

