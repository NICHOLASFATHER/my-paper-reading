# Multimodal Intelligence: Representation Learning, Information Fusion, and Applications

该文章是多模态领域的综述文章，成文于2020年。

## 1.摘要

### 1.1深度学习取得的进展

语音识别/图像识别/自然语言处理

### 1.2存在的问题

传统任务的输入都是单模态的信号，然而现实世界总是复杂的。

### 1.3当今的热门话题

计算机视觉和自然语言处理的融合

### 1.4本文的主要工作

#### 1.4.1多模态表征

概述了嵌入表示的重要概念，即如何将多模态的信号统一在同一个向量空间。本文还分析了适用于不同下游任务的嵌入表示。

#### 1.4.2多模态信号融合

本文主要介绍对于特定任务的特征融合特殊架构。

#### 1.4.3多模态应用

- 图像-文本的字幕生成
- 文本-图像的创作
- 视觉问答

## 2.特征表示

### 2.1单模态特征表示

就是要使用一个向量来表示一个概念，这个向量的每个元素都可以分别调整，因此可以在一个向量空间内来表示多个不同的概念。

与之相近的是使用one-hot码表示的元素，而embedding要做的也包括把one-hot码映射成分布式表示。

#### 2.1.1图像特征表示

常见的CNN就是一种特征表示手段，在CNN的末端就是图像的特征表示

R-CNN

#### 2.1.2文本特征表示

- RNN-based
- BERT

- 不仅可以对词，也可以考虑对词组，句子甚至段落进行embedding

### 2.2多模态特征表示

- 无监督方法
- 有监督方法
- zero-shot
- 基于Transformer

## 3.特征融合

多模态特征表示与特征融合有密切的联系，或者说没有十分明显的界限，我们称那些专注于融合特定任务单模态特征的网络架构为特征融合。

- 简单融合方法：例如联接，加权和
- 基于注意力的方法
  - 图像注意力
  - 图像和文本均衡注意力
  - 双峰Transformer
- 基于张量的方法：bilinear polling

## 4.多模态应用

- 图片->文字描述（image-captioning）
- 文字->图片（text to image generation）
- 图像问答（VQA）

### 4.1image captioning

- 常用编码器-解码器架构

### 4.2text to image

最初来源于人们渴望生成手写体

#### 4.2.1两大主要任务

- 高质量图片生成
- 自然语言理解

#### 4.2.2常用模型

- deep recurrent attentive writer（DRAW）
- GAN生成对抗网络
  - CGAN
  - GAN-INT-CLS
  - StackGAN
  - AttnGAN
  - DAMSM
  - HDGAN
  - TAC-GAN
  - Text-SeGAN
  - MirrorGAN
  - Obj-GAN

- Attribute2Image用于人脸生成，此外可以选择年龄和性别等参数，其技术可以用于人脸修图，如不要胡须或者改变发色。
- Text2Scene没有使用GAN，可以生成卡通图片

### 4.3visual question answering

回答基于图片或者视频信息的问题，被认为是一种图片图灵测试，然而在实际操作中有点退化为了分类问题。



## 5.扩展阅读

1. 情感识别
2. zero-shot
3. region-based CNN(RCNN)
4. pytorch embedding的具体做法
5. BERT（bidirectional encoder representations for transformer）
6. **GAN（generative adversarial network）**
7. 说话人识别，及安全问题，86-106
8. **DAL-E 2**
9. 神经网络架构搜索
10. 模型轻量化
11. vilBERT
12. **VAE生成模型**

## 6.Idea

小样本学习（人类对某些重要样本只需要一次就能学会）

视频说话人识别，视频字幕（结合口型识别，多传感器阵列位置识别）

考虑建模“记忆”，机器仅凭看图来生成描述，或者进行识别任务，对机器未免太困难，考虑是否可以使用一种弹性的知识库