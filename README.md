## Multilingual Speech Recognition: End-to-End Automatic Speech Recognition
This notebook uses the end-to-end (E2E) speech processing toolkit [ESPnet](https://github.com/espnet/espnet) for the natural language processing task automatic speech recognition (ASR)< which enables human beings to use their voices to speak with a computer interface in a way that resembles normal human conversation.<br>

About the data: The training data used is the Vientamese [Mozilla Commonvoice dataset](https://commonvoice.mozilla.org/en/datasets), comprised of 15 minutes of audio data from 14 different speakers. These datasets are publically available and enable the advancement of speech-enabled applications. 


## Requirements
A GPU that can install CUDA_VERSION=10.2 for the latest PyTorch (1.10.1)

## Code
This code can be run on either an AWS server or via Google Colab (for small datasets). 

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1f0vRkvWROCbvkop4yOpkuulBiY24_q0h?usp=sharing)


### Training
This codebase does not contain any trained models. For the first run, use the follow command line. 
The language codes available are {en, es, cs, ar, af, lt, hy, ta}. <br> 
`python main.py --mode train --lang <language_code>`

### Evaluating
You can find word error rate (WER), character error rate (CER), token error rate (TER) etc. for each test set. If accuracy is low for a given dataset, it can be helpful to use both the WER and CER to determine model performance. 

`sclite` from [SCTK](https://github.com/usnistgov/SCTK) is used for scoring.

General idea is to compute the edit-distance between the hypothesis and the reference sequences. When two sequences are aligned, there are four types of alignment relationships at each position:
* Correct (Corr)
* Substitution (Sub)
* Deletion (Del)
* Insersion (Ins)

error_rate: Err = (#Sub + #Del + #Ins) / (#Corr + #Sub + #Del), where (#Corr + #Sub + #Del) is equal to the length of the reference.

The final results of all error rates can be found in the file `exp/asr_train_asr_conformer5_raw_as_bpe150_sp/RESULTS.md`, where the columns mean:
 - Snt  : total number of sentences,
 - Wrd : total number of words, 
 - Corr : number of correct words,
 - Sub  : number of substitutions,
 - Del : number of deletions,
 - Ins : number of insertions,
 - **Err : word error rate**,
 - S.Err: sentence error rate.

Note: the column **Err** is the final error rate we usually check.

```
|dataset|Snt|Wrd|Corr|Sub|Del|Ins|Err|S.Err|                   
|---|---|---|---|---|---|---|---|---|                                                  
|decode_asr_lm_lm_train_lm_as_bpe150_valid.loss.ave_asr_model_valid.acc.ave/dev_as|124|1010|0.0|13.6|86.4|0.0|100.0|100.0|
|decode_asr_lm_lm_train_lm_as_bpe150_valid.loss.ave_asr_model_valid.acc.ave/test_as|41|314|0.0|14.3|85.7|0.0|100.0|100.0|
```
