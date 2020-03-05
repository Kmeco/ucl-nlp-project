## The PyTorch Implementation Of SummaRuNNer

[![License](https://img.shields.io/badge/license-MIT-000000.svg)](https://opensource.org/licenses/MIT)

### Models

1. RNN_RNN
<div  align="center">
<img src="images/RNN_RNN.jpg" width = "350" height = "350" align=center />
</div>

2. CNN_RNN
<div  align="center">
<img src="images/CNN_RNN.png" width = "350" height = "260" align=center />
</div>

3. Hierarchical Attention Networks
<div  align="center">
<img src="images/Hiarchical_Attn.png" width = "350" height = "350" align=center />
</div>

### Setup

Requires [pipenv](https://docs.pipenv.org/). Use `pip install pipenv` if not installed.

```
pipenv install
pipenv shell
```

### Usage  

```shell
# train
python main.py -device 0 -batch_size 32 -model RNN_RNN -seed 1 -save_dir checkpoints/XXX.pt
# test
python main.py -device 0 -batch_size 1 -test -load_dir checkpoints/XXX.pt
# predict
python main.py -batch_size 1 -predict -filename x.txt -load_dir checkpoints/RNN_RNN_seed_1.pt
```

## pretrained models

1. RNN_RNN(`checkpoints/RNN_RNN_seed_1.pt`)
2. CNN_RNN(`checkpoints/CNN_RNN_seed_1.pt`)
2. AttnRNN(`checkpoints/AttnRNN_seed_1.pt`)

## Result

#### DailyMail(75 bytes)  

| model  | ROUGE-1   | ROUGE-2 | ROUGE-L |
| ------ | :-----:   | :----:  | :----:  |
|SummaRNNer(Nallapati)|26.2|10.8|14.4|
|RNN-RNN|26.0|11.5|13.8|
|CNN-RNN|25.8|11.3|13.8|
|Hierarchical Attn Net|26.0|11.4|13.8|

### Download Data: 

Download this folder and paste its content in the data folder in the current directory. It contains the pretrained 
embeddings, word2id, and dailymail train/test/val json splits.
+ Google Driver:[data.tar.gz](https://drive.google.com/file/d/1JgsboIAs__r6XfCbkDWgmberXJw8FBWE/view?usp=sharing)

### Evaluation

+ [Tools](https://github.com/hpzhao/nlp-metrics)