---
layout:     post
title:      "TOPIC AWARE NEURAL CONVERSATION MODEL"
subtitle:   ""
date:       2014-08-24 12:00:00
author:     "liuxuan0526"
header-img: "img/post-bg-04.jpg"
---

#### paper
https://arxiv.org/pdf/1606.08340v2.pdf

#### Abstract
We consider incorporating topic information into the
sequence-to-sequence framework to generate informative and
interesting responses for chatbots. To this end, we propose
a topic aware sequence-to-sequence (TA-Seq2Seq) model.
The model utilizes topics to simulate prior knowledge of human
that guides them to form informative and interesting responses
in conversation, and leverages the topic information
in generation by a joint attention mechanism and a biased
generation probability. The joint attention mechanism summarizes
the hidden vectors of an input message as context
vectors by message attention, synthesizes topic vectors by
topic attention from the topic words of the message obtained
from a pre-trained LDA model, and let these vectors jointly
affect the generation of words in decoding. To increase the
possibility of topic words appearing in responses, the model
modifies the generation probability of topic words by adding
an extra probability item to bias the overall distribution. Empirical
study on both automatic evaluation metrics and human
annotations shows that TA-Seq2Seq can generate more
informative and interesting responses, and significantly outperform
the-state-of-the-art response generation models.

#### introduction
MT models such as Seq2Seq with attention tends to generate trivial responses like 'me too', 'I see' due to the hight frequency of these patterns in data

unlike Li who try to **passively** avoid generating trivial responses by penalizing their generation probabilities, we consider solving the problem by **actively** bringing content into responses by topics.

Given an input message, we predict possible topics that can be talked about in responses, and generate responses with the topics.

In human-human conversation, people often associate an input message with topically related concepts in their mind. Based on the concepts, they organize content and select words for their responses. 

#### model
![image]({{ site.baseurl }}/img/1.png)
