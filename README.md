# Overview
 The Modal-Influence repository is for the double-blind-submission to INTERSPEECH 2024.

 # Installation
 1. The project is developed based on [s3prl](https://github.com/s3prl/s3prl#installation) toolkit, please install it first.
    * Please follow the [instrution](https://s3prl.github.io/s3prl/tutorial/installation.html#editable-installation) to do editable installation
      ```
      git clone https://github.com/s3prl/s3prl.git
      cd s3prl
      pip install -e .
      ```
2. Move the ```emo``` folder into the path ```s3prl/s3prl/downstream```
3. Move the ```data folder``` into the path ```s3prl/s3prl/``` 
   * Download wav files into the folder for each database (e.g., ```data/IEMOCAP/Audios```)by submiting the EULA form for the six databases.
   * [CREMA-D](https://github.com/CheyneyComputerScience/CREMA-D)


## Training Models 
### Use the command line. We take the **fbank** as an example.
```
for upstream in fbank; do 
 for test_fold in fold1 fold2 fold3 fold4 fold5; do
  for corpus in CREMAD; do
  # The default config is "downstream/emotion/config.yaml"
  python3 run_downstream.py -n ${upstream}_${corpus}_$test_fold -m train -u ${upstream} -d emo -c downstream/emotion/config_${corpus}.yaml -o "config.downstream_expert.datarc.test_fold='$test_fold'"
  python3 run_downstream.py -m evaluate -e result/downstream/${upstream}_${corpus}_$test_fold/dev-best.ckpt
  done;
 done;
done
```

## Cross-testing
``` bash
$ bash run_log_test.sh
```
