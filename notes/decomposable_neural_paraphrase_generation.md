Decomposable Neural Paraphrase Generation

## 1 Introduction

![1566543099608](../../assets/1566543099608.png)

**sentence-level pattern and phrase-level pattern**

sentence-level: general and abstractive

word/phrase-level: diverse and domain-specific

and they can be decoupled



**Decomposable Neural Paraphrase Generator**

*separator*, multiple *encoders* and *decoders*, and an *aggregator*

input sentence -> *separator*  -> different granularities segments -> *multiple granularity-specific encoders and decoders* -> output -> *aggregator* -> paraphrase



**Three Advantages**

- **Interpretable**
- **Controllable**
- **Domain-adaptable**

## 2 Decomposable Neural Paraphrase Generator

Model Overview

![1566544784274](../../assets/1566544784274.png)

2.2 Separator

sequence labeling process

2.3 Multi-granularity encoder and decoder

2.4 Aggregator

2.5 Learning of Separator and Aggregator