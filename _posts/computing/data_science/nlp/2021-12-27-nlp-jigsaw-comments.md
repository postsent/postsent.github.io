---
title: Kaggle - NLP 
date: 2021-12-27
categories:
  - Kaggle
excerpt: My journey with the 2021 Jigsaw kaggle competition
last_modified_at: 2021-12-27
---

[Jigsaw Rate Severity of Toxic Comments](https://www.kaggle.com/c/jigsaw-toxic-severity-rating/overview)

# Description

This is about **sentiment analysis**. This is a continuation from the previous one which determines whether a comment is toxic. This new one rates how toxic a comment is.

**End goal** is to have a rating similar to the experts in the field.

Related work section gives [a relevant dataset](https://aclanthology.org/2021.acl-long.210/). ["Constructing Interval Variables via Faceted Rasch Measurement and Multitask Deep Learning: a Hate Speech Application"](https://arxiv.org/pdf/2009.10277.pdf) may help as well.

Google Jiasaw is where the name comes from.

# TODO

## Pre-trained word embedding 

[glove standford](https://nlp.stanford.edu/projects/glove/)

word2vec
- [nlp-in-practice](https://github.com/kavgan/nlp-in-practice)
- [how to use](https://github.com/kavgan/nlp-in-practice/blob/master/pre-trained-embeddings/Pre-trained%20embeddings.ipynb)
  
All
[comprehensive](https://github.com/Separius/awesome-sentence-embedding#word-embeddings)
[More concise](https://github.com/msgi/nlp-journey)

## Text cleaning

https://github.com/jfilter/clean-text

[Jigsaw-Ridge Ensemble + TFIDF + FastText [0.868]](https://www.kaggle.com/nkitgupta/jigsaw-ridge-ensemble-tfidf-fasttext-0-868/notebook)
- data argumentation [nlpaug](https://nlpaug.readthedocs.io/en/latest/augmenter/word/random.html)

[[RAPIDS] TFIDF_linear_model_ensemble](https://www.kaggle.com/tenffe/rapids-tfidf-linear-model-ensemble/notebook)

For words duplicates, shorten to one and add new col/feature counting number of times. 
E.g. happy is less happy than happy*5.


## Past winning solution

Toxic Comment Classification Challenge
- [1st](https://www.kaggle.com/c/jigsaw-toxic-comment-classification-challenge/discussion/52557)
- [2nd](https://www.kaggle.com/c/jigsaw-toxic-comment-classification-challenge/discussion/52612)
- [3rd](https://www.kaggle.com/c/jigsaw-toxic-comment-classification-challenge/discussion/52644), [code](https://www.kaggle.com/larryfreeman/toxic-comments-code-for-alexander-s-9872-model)

## Reading 

Pre-trained word embedding
- https://github.com/Hironsan/awesome-embedding-models

Comprehensive pre-processing
- https://www.kaggle.com/vinayakshanawad/text-preprocess-py
- https://www.kaggle.com/xbf6xbf/processing-helps-boosting-about-0-0005-on-lb
- [machinelearningmastery](https://machinelearningmastery.com/clean-text-machine-learning-python/)
  
[gensim](https://github.com/RaRe-Technologies/gensim)
# Mis

Start with a simple model, here I used: [Incredibly Simple Naive Bayes [0.768]](https://www.kaggle.com/julian3833/jigsaw-incredibly-simple-naive-bayes-0-768)