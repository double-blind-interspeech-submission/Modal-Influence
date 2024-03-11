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
``` bash
$ bash run_log_test.sh
```
