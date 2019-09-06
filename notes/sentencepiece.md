SentencePiece: A simple and language independent subword tokenizer and detokenizer for Neural Text Processing

## 1 Intro:

NMT is awesome

but still relying on **language-dependent** pre- and postprocessors

these tools are mainly designed for European languages(whitespaces), for Chinese we need to run word segmenters independently

NMT approaches are standardized and moving forward to more language-agnostic architectures

👉 we need a simple, efficient, reproducible and language independent pre- and postprocessor

**algorithms:**

- BPE
- unigram language model

## 2 System Overview

Normalizer, Trainer, Encoder, Decoder

Normalizer(Text): return normalized text

Trainer(nomalized corpus): train and save model

Encoder(text, model): normalized_text = Normalizer(text); return model.encode(normalized_text)

Decode(subword sequence, model): return model.decode(subword sequence)

corpus -> **Normalizer** -> **Trainer** -> model

model and text -> **Encoder(internally use Normalizer)** -> subword sequence -> **Decoder** -> normalized text

## 3 Library Design

### 3.1 Lossless Tokenization

- old tokenization

    - Raw Text: Hello world.
    - Tokenized: [Hello] [world] [.]
    - Reverse: Hello world. or Hello world .

- lossless tokenization

    - Raw Text: Hello_world.

    - Tokenized: [Hello] [_wor] [ld] [.]

    - Reverse: Hello_world.

        `''.join(toknes).replace('_', ' ')`

### 3.2 efficient subword training and segmentation

### 3.3 Vocabulary id management

- parameter:
    - subword-nmt specifies `number of merge operations`
    - sentence-piece specifies `final size of vocabulary`

- reserve vocabulary

    \<unk> \<s> \</s> \<pad>

### 3.4 Customizable character normalization

WTF NFC NFKC

and use define tsv

### 3.5 Self-contained models

preprocess schemes can widely change BLEU scores, but it is not alway stated how the data was preprocessed.

sentencepiece save all the rules and parameters in model file, solve the reproduce problem(self-contained)

### 3.6 Library API for on-the-fly processing

off-line preprocessing has two problems:

- not directly integrated into user-facing NMT applications
- hard to employ subsentence level data augmentation and noise injection