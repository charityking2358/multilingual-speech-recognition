<!-- Generated by scripts/utils/show_asr_result.sh -->
# RESULTS
## Environments
- date: `Fri Mar 18 01:14:14 UTC 2022`
- python version: `3.9.7 (default, Sep 16 2021, 13:09:58)  [GCC 7.5.0]`
- espnet version: `espnet 0.10.7a1`
- pytorch version: `pytorch 1.10.1`
- Git hash: `21d19be00089678ca27f7fce474ef8d787689512`
  - Commit date: `Wed Mar 16 08:06:52 2022 -0400`

## asr_train_asr_conformer5_raw_vi_bpe100_sp
### WER

|dataset|Snt|Wrd|Corr|Sub|Del|Ins|Err|S.Err|
|---|---|---|---|---|---|---|---|---|
|inference_asr_model_valid.acc.ave/dev_vi|25|152|0.0|100.0|0.0|143.4|243.4|100.0|
|inference_asr_model_valid.acc.ave/test_vi|57|420|0.0|100.0|0.0|140.0|240.0|100.0|

### CER

|dataset|Snt|Wrd|Corr|Sub|Del|Ins|Err|S.Err|
|---|---|---|---|---|---|---|---|---|
|inference_asr_model_valid.acc.ave/dev_vi|25|619|30.9|63.3|5.8|21.3|90.5|100.0|
|inference_asr_model_valid.acc.ave/test_vi|57|1737|30.5|58.3|11.2|24.0|93.6|100.0|

### TER

|dataset|Snt|Wrd|Corr|Sub|Del|Ins|Err|S.Err|
|---|---|---|---|---|---|---|---|---|
|inference_asr_model_valid.acc.ave/dev_vi|25|548|23.9|75.2|0.9|35.9|112.0|100.0|
|inference_asr_model_valid.acc.ave/test_vi|57|1537|22.8|71.8|5.5|36.6|113.9|100.0|

