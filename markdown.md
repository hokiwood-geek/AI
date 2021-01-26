# 论文综述
## 论文1（2020） SHG,带有<u>风格</u>的标题生成
@ACL2020: Hooks in the Headline: Learning to Generate Headlines with Controlled Styles
 **主要利用Style-Guided Encoder Attention方法**
* [x] code
* [x] data

**来源于2020ACL顶会**
[项目代码](https://github.com/jind11/TitleStylist)
同时提供数据集
[作者讲解视频](https://www.youtube.com/watch?v=c73Z0prqNsM)

摘要：
>目前的摘要系统只能产生简洁、真实的标题，但不能满足创造令人难忘的标题以增加曝光率的实际需要。为了吸引更多的读者，我们提出了一个新的任务，即文体型标题生成(SHG)，用幽默、浪漫和点击诱饵三种风格来丰富标题。在没有特定风格的文章标题对(只有一个标准的标题摘要数据集和单一风格的语料库)的情况下，我们的方法TitleStylist通过将摘要和重构任务合并到一个多任务框架中来生成特定风格的标题。我们还引入了一种新的参数共享方案来进一步从文本中分离风格。通过自动评估和人工评估，我们证明了TitleStylist可以生成三种目标风格的相关、流畅的标题:幽默、浪漫和点击诱饵。我们的模型生成的标题的吸引力得分比最先进的摘要模型高出9.68%，甚至超过了人类书写的参考
>![82cf9f49f743ea698971eac8c0dc925d.png](en-resource://database/4918:1)


## 论文2(2020) SHEG增强抽象机制的混合模型 && 强化学习

SHEG: summarization and headline generation of news articles using deep learning
* [x] code
* [x] data
**perform：**
![c595ac61424caec7cad542bfab70868a.png](en-resource://database/4914:1)
![1472e14e463e516f6184c99b643defb0.png](en-resource://database/4916:1)

**RL：**
Attractive or Faithful? Popularity-Reinforced Learning for Inspired Headline Generation
## 论文3 bert预训练(2019)
[**Fine-tune BERT for Extractive Summarization**](
https://arxiv.org/abs/1903.10318)

* [x] [code](https://github.com/nlpyang/BertSum?utm_source=catalyzex.com)
* [x] data(CNN/mail)
![2b0ee7d2883f6dea94f851705ed7824c.png](en-resource://database/4910:1)

## 论文4 指针神经网络(2017,经典)

[Get to the point: summa-rization with pointer-generator network](https://arxiv.org/abs/1903.10318)
* [x] [code](
https://github.com/abisee/pointer-generator?utm_source=catalyzex.com)

## 论文5 多产出transform模型（2020）

Diverse, Controllable, and Keyphrase-Aware: A Corpus and Method for News Multi-Headline Generation

**摘要**：
>新闻头条新闻的目的是制作一个简短的句子，以吸引读者阅读新闻。一篇新闻文章通常包含多个不同用户感兴趣的关键词，这些关键词自然可以有多个合理的头条新闻。然而，大多数现有方法都侧重于单一标题生成。在本文中，我们提出了用户兴趣的关键词来生成多个头条新闻，其主要思路是首先为新闻生成多个用户感兴趣的关键词，然后生成多个与关键词相关的头条新闻。我们提出了一个多源 Transformer 解码器，它以三个来源作为输入：(a) 关键词，(b) 关键词过滤文章，(c) 原创文章，以生成与关键词相关、高质量和多样化的标题。此外，我们提出了一种简单有效的方法来挖掘新闻文章中感兴趣的关键词，并构建第一个大规模的关键词感知新闻标题语料库，其中包含 180K 对齐的\ (<\) news article, headline, keyphrase\ (>\) 三倍以上。对实际数据集进行广泛的实验比较表明，该方法在质量和多样性方面取得了最先进的结果

# 论文精读
## 前言
摘要：
>目前的摘要系统只能产生简洁、真实的标题，但不能满足创造令人难忘的标题以增加曝光率的实际需要。为了吸引更多的读者，我们提出了一个新的任务，即文体型标题生成(SHG)，用幽默、浪漫和点击诱饵三种风格来丰富标题。在没有特定风格的文章标题对(只有一个标准的标题摘要数据集和单一风格的语料库)的情况下，我们的方法TitleStylist通过将摘要和重构任务合并到一个多任务框架中来生成特定风格的标题。我们还引入了一种新的参数共享方案来进一步从文本中分离风格。通过自动评估和人工评估，我们证明了TitleStylist可以生成三种目标风格的相关、流畅的标题:幽默、浪漫和点击诱饵。我们的模型生成的标题的吸引力得分比最先进的摘要模型高出9.68%，甚至超过了人类书写的参考

介绍：
目前标题生成的state-of-art只能生成高度概括性但死板的标题，无法吸引人。
最近有一些增加风格色彩的论文，利用强化学习的方法。
即使有风格生成优秀的方法也需要特定风格的新闻数据集。
本文不仅利用未分类的带有特定风格的数据集，还在人工评判的标准下取得了优秀效果。
## 方法
主要是在en-decoder以及transform的基础上增加了多层框架，DAE噪声训练以及encoder模型共享的创新。
![c2c73c0856ecf97f984dfd2c7b7033e8.jpeg](en-resource://database/4920:1)

## 结果
![d99dfe30674d6e93ef8fd455393be336.png](en-resource://database/4922:1)
在人工评判下，生成的标题流畅且吸引人。
常用指标中，部分结果也不亚于NHG的baseline的结果。

