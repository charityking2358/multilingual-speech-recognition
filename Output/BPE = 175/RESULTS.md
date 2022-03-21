<!-- Generated by scripts/utils/show_asr_result.sh -->
# RESULTS
## Environments
- date: `Fri Mar 18 02:58:42 UTC 2022`
- python version: `3.9.7 (default, Sep 16 2021, 13:09:58)  [GCC 7.5.0]`
- espnet version: `espnet 0.10.7a1`
- pytorch version: `pytorch 1.10.1`
- Git hash: `21d19be00089678ca27f7fce474ef8d787689512`
  - Commit date: `Wed Mar 16 08:06:52 2022 -0400`

## asr_train_asr_conformer5_raw_vi_bpe175_sp
### WER

|dataset|Snt|Wrd|Corr|Sub|Del|Ins|Err|S.Err|
|---|---|---|---|---|---|---|---|---|
|inference_asr_model_valid.acc.ave/dev_vi|25|152|0.0|80.9|19.1|0.7|100.7|100.0|
|inference_asr_model_valid.acc.ave/test_vi|57|420|0.0|71.7|28.3|5.2|105.2|100.0|

### CER

|dataset|Snt|Wrd|Corr|Sub|Del|Ins|Err|S.Err|
|---|---|---|---|---|---|---|---|---|
|inference_asr_model_valid.acc.ave/dev_vi|25|619|26.7|29.4|43.9|1.1|74.5|100.0|
|inference_asr_model_valid.acc.ave/test_vi|57|1737|23.0|28.6|48.5|1.7|78.8|100.0|

### TER

|dataset|Snt|Wrd|Corr|Sub|Del|Ins|Err|S.Err|
|---|---|---|---|---|---|---|---|---|
|inference_asr_model_valid.acc.ave/dev_vi|25|369|8.7|59.1|32.2|1.4|92.7|100.0|
|inference_asr_model_valid.acc.ave/test_vi|57|1049|7.1|53.4|39.5|2.3|95.1|100.0|
