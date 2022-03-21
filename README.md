## Multilingual Speech Recognition: End-to-End Automatic Speech Recognition
This notebook uses the end-to-end (E2E) speech processing toolkit [ESPnet](https://github.com/espnet/espnet) for the natural language processing task automatic speech recognition (ASR)< which enables human beings to use their voices to speak with a computer interface in a way that resembles normal human conversation.<br>

About the data: The training data used is the Vietnamese [Mozilla Commonvoice dataset](https://commonvoice.mozilla.org/en/datasets), comprised of 15 minutes of audio data from 14 different speakers. These datasets are publically available and enable the advancement of speech-enabled applications. 

## Requirements
A GPU that can install CUDA_VERSION=10.2 for the latest PyTorch (1.10.1)

## Code
This code can be run on either an AWS server or via Google Colab (for small datasets) and installs on dependencies. 

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1f0vRkvWROCbvkop4yOpkuulBiY24_q0h?usp=sharing)

## Evaluation
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

**1) Baseline Model**
### WER for baseline model 

|dataset|Snt|Wrd|Corr|Sub|Del|Ins|Err|S.Err|
|---|---|---|---|---|---|---|---|---|
|inference_asr_model_valid.acc.ave/dev_vi|25|152|0.0|63.2|36.8|0.0|100.0|100.0|
|inference_asr_model_valid.acc.ave/test_vi|57|420|0.0|62.1|37.9|3.6|103.6|100.0|

### CER for baseline model 

|dataset|Snt|Wrd|Corr|Sub|Del|Ins|Err|S.Err|
|---|---|---|---|---|---|---|---|---|
|inference_asr_model_valid.acc.ave/dev_vi|25|619|22.1|19.9|58.0|0.5|78.4|100.0|
|inference_asr_model_valid.acc.ave/test_vi|57|1737|20.6|22.9|56.6|1.2|80.7|100.0|
--------------------------------------------------------------------------------------------
**2) Model with lowest WER: Using Word instead of BPE for token**

### WER

|dataset|Snt|Wrd|Corr|Sub|Del|Ins|Err|S.Err|
|---|---|---|---|---|---|---|---|---|
|inference_asr_model_valid.acc.ave/dev_vi|25|152|2.0|5.3|92.8|0.0|98.0|100.0|
|inference_asr_model_valid.acc.ave/test_vi|57|420|0.7|9.8|89.5|0.0|99.3|100.0|

### CER

|dataset|Snt|Wrd|Corr|Sub|Del|Ins|Err|S.Err|
|---|---|---|---|---|---|---|---|---|
|inference_asr_model_valid.acc.ave/dev_vi|25|619|3.7|2.3|94.0|0.0|96.3|100.0|
|inference_asr_model_valid.acc.ave/test_vi|57|1737|4.5|3.9|91.5|0.3|95.7|100.0|

--------------------------------------------------------------------------------------------
**3) Model with lowest CER: Encoder Number of Blocks = 14, Decoder Number of Blocks = 7**
### WER: 

|dataset|Snt|Wrd|Corr|Sub|Del|Ins|Err|S.Err|
|---|---|---|---|---|---|---|---|---|
|inference_asr_model_valid.acc.ave/dev_vi|25|152|0.0|71.7|28.3|0.7|100.7|100.0|
|inference_asr_model_valid.acc.ave/test_vi|57|420|0.0|73.3|26.7|4.3|104.3|100.0|

### CER

|dataset|Snt|Wrd|Corr|Sub|Del|Ins|Err|S.Err|
|---|---|---|---|---|---|---|---|---|
|inference_asr_model_valid.acc.ave/dev_vi|25|619|24.2|27.0|48.8|0.8|76.6|100.0|
|inference_asr_model_valid.acc.ave/test_vi|57|1737|23.5|31.0|45.5|2.0|78.5|100.0|
