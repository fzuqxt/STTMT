## Environment
Cuda   11.4

Python 3.8.11

torch  1.9.0 or higher


## Installation
```
$ git clone https://github.com/fzuqxt/STTMT.git
$ pip install -r requirements.txt
```

Note that the torch version must be compatible to the cuda version, not necessary to be 1.9.0 here. For example, with cuda version 11.X, torch 1.9.0 is too old to use, may cause problems like
```
Cuda error: no kernel image is available for execution on the device 
```

## Dataset Preparation
Download vimeo90k Septuplet dataset for training and evaluation:

http://toflow.csail.mit.edu/index.html#septuplet

Choose "The original training + test set (82GB)".

```
cp datasets/vimeo_septuplet/*.txt /path/to/vimeo/
```
```
python ./datasets/prepare_vimeo.py --path /path/to/vimeo/
```

Download Vid4 dataset for evaluation:

https://drive.google.com/drive/folders/10-gUO6zBeOpWEamrWKCtSkkUFukB9W5m

## Train
Make sure writing a yml file with settings pointing to correct paths, for example:
```
python train.py --config ./configs/STTMT-L/STTMT-L.yml
```

## Evaluation
###checkpoints:

[https://pan.baidu.com/s/1CyYZwOZP7N49gMLng3gYTw] 提取码: 2693

### Vid4:
Make sure writing a yml file with settings pointing to correct paths, for example:
```
python eval_vid4.py --config ./configs/STTMT-L/STTMT-L-eval-vid4.yml
```
### Vimeo90k:
Make sure writing a yml file with settings pointing to correct paths, for example:
```
python eval_vimeo90k.py --config ./configs/STTMT-L/STTMT-L-eval-vimeo90k.yml
```

