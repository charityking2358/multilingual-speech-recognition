<!-- Generated by scripts/utils/show_asr_result.sh -->
# RESULTS
## Environments
- date: `Fri Mar 18 02:07:52 UTC 2022`
- python version: `3.9.7 (default, Sep 16 2021, 13:09:58)  [GCC 7.5.0]`
- espnet version: `espnet 0.10.7a1`
- pytorch version: `pytorch 1.10.1`
- Git hash: `21d19be00089678ca27f7fce474ef8d787689512`
  - Commit date: `Wed Mar 16 08:06:52 2022 -0400`

## asr_train_asr_conformer5_raw_vi_bpe125_sp
### WER

|dataset|Snt|Wrd|Corr|Sub|Del|Ins|Err|S.Err|
|---|---|---|---|---|---|---|---|---|
|inference_asr_model_valid.acc.ave/dev_vi|25|152|0.0|90.8|9.2|6.6|106.6|100.0|
|inference_asr_model_valid.acc.ave/test_vi|57|420|0.5|82.4|17.1|10.7|110.2|100.0|

### CER

|dataset|Snt|Wrd|Corr|Sub|Del|Ins|Err|S.Err|
|---|---|---|---|---|---|---|---|---|
|inference_asr_model_valid.acc.ave/dev_vi|25|619|29.1|37.3|33.6|3.6|74.5|100.0|
|inference_asr_model_valid.acc.ave/test_vi|57|1737|26.0|37.2|36.8|4.4|78.4|100.0|

### TER

|dataset|Snt|Wrd|Corr|Sub|Del|Ins|Err|S.Err|
|---|---|---|---|---|---|---|---|---|
|inference_asr_model_valid.acc.ave/dev_vi|25|430|14.9|58.6|26.5|4.4|89.5|100.0|
|inference_asr_model_valid.acc.ave/test_vi|57|1181|11.1|59.9|29.0|4.7|93.6|100.0|

