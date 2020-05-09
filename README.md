# convert_tf_bert_model_to_pytorch
将 tensorflow 版本的预训练 bert model 转化为 pytorch 版本

## 0.安装python依赖
```
pip install -r requirement.txt
```

## 1.第一步
下载 tensorflow 版本的预训练 bert model : [chinese_L-12_H-768_A-12](https://storage.googleapis.com/bert_models/2018_11_03/chinese_L-12_H-768_A-12.zip)

解压后放在当前目录下：
```
├── convert_tf_bert_model_to_pytorch
|  └── chinese_L-12_H-768_A-12
|  |  └── bert_config.json
|  |  └── bert_model.ckpt.data-00000-of-00001
|  |  └── bert_model.ckpt.index
|  |  └── ......

```

## 2.第二步
运行该代码：
```
python convert_tf_checkpoint_to_pytorch.py
```
转换成功的 pytorch 版本的与训练 model 会保存在：
```
├── convert_tf_bert_model_to_pytorch
|  └── chinese_L-12_H-768_A-12
|  |  └── pytorch_model.bin
|  |  └── ......
```

## 注意：
如果地址出现错误，请修改如下代码为自定义地址：
windows版本地址：
```py
args.tf_checkpoint_path = "chinese_L-12_H-768_A-12\\bert_model.ckpt"
args.bert_config_file = "chinese_L-12_H-768_A-12\\bert_config.json"
args.pytorch_dump_path = "chinese_L-12_H-768_A-12\pytorch_model.bin"
```

linux版本地址：
```py
args.tf_checkpoint_path = "./chinese_L-12_H-768_A-12/bert_model.ckpt"
args.bert_config_file = "./chinese_L-12_H-768_A-12/bert_config.json"
args.pytorch_dump_path = "./chinese_L-12_H-768_A-12/pytorch_model.bin"
```



## 也可以直接下载转换好的model:
config: https://s3.amazonaws.com/models.huggingface.co/bert/bert-base-chinese-config.json 

vocab: https://s3.amazonaws.com/models.huggingface.co/bert/bert-base-chinese-vocab.txt 

model: https://s3.amazonaws.com/models.huggingface.co/bert/bert-base-chinese-pytorch_model.bin


项目代码来自：https://github.com/huggingface
