# Evaluating Tokenization Efficiency for Sanskrit

A comparative evaluation of 15 multilingual tokenizers on a Sanskrit corpus.

## Overview

Tokenization directly influences sequence length, context-window utilization, memory requirements, and computational cost.
Self-attention complexity grows quadratically with sequence length (n), i.e., 𝑂(𝑛2).

Attention Cost ∝ 𝑛^2

This project investigates how efficiently different tokenizers represent Sanskrit text. Tokenizers were evaluated using intrinsic metrics including:

* Fertility (tokens per word)
* Token count
* Characters per token
* Tokens per character
* Reconstruction quality

## Key Findings

* Sanskrit-specific tokenizers consistently outperformed multilingual tokenizers.
* The Sanskrit-English Qwen tokenizer achieved the best overall performance.
* Claude produced the highest token fragmentation.
* Vocabulary size alone was not a reliable predictor of tokenizer efficiency.

| Tokenizer             | Fertility |
| --------------------- | --------- |
| Sanskrit-English Qwen | 1.52      |
| SentencePiece-SA      | 2.78      |
| SansGPT               | 3.53      |
| Claude                | 9.30      |

<img width="867" height="497" alt="image" src="https://github.com/user-attachments/assets/be5c381a-37e8-4cf1-8626-9955c6160049" />


## Evaluated Tokenizers

<img width="558" height="462" alt="image" src="https://github.com/user-attachments/assets/539fd3c1-ef24-4a8a-8a23-39b6daec189d" />

SansGPT, SentencePiece-SA, Sanskrit-Qwen, Sanskrit-English Qwen, SUTRA, Airavata, mT5, mBART, Aya, Llama 3.1, Gemma, Tiny Mistral, Claude, cl100k_base, and o200k_base.

## Main Result

<img width="927" height="600" alt="image" src="https://github.com/user-attachments/assets/2c46e103-463c-4840-a290-06b03496e890" />

The Sanskrit-English Qwen tokenizer achieved approximately **6× lower fertility than Claude**, allowing substantially more Sanskrit text to fit within a fixed LLM context window.

## Author

Nikhila Gadge
