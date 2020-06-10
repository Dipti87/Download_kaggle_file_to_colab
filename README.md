## Please refer the below process to download a file to colab from kaggle dataset.
============= ============= ============= ============= ============= ============= 
```sh
 !pip install kaggle
 import os
```

*allows us to upload files into colab \n
*we'll need to upload the kaggle.json file
*in kaggle, under accounts, click 'create new API token'
*upload the kaggle.json file that is automatically downloaded

```python
from google.colab import files
files.upload()
```
> ensure its there
```
!ls -lha kaggle.json
```

- The Kaggle API client expects this file to be in ~/.kaggle,
- so lets move it there.
```python
!mkdir -p ~/.kaggle
!cp kaggle.json ~/.kaggle/
```
This permissions change avoids a warning on Kaggle tool startup.
```
> !chmod 600 ~/.kaggle/kaggle.json
```
now download our dataset
```
> !kaggle competitions download -c tgs-salt-identification-challenge 
```
- and we'll need those training images unzipped
```
> !ls
> !unzip train.zip
```
