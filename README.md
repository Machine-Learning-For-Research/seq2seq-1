[[README doc for English Version]](README4English.md)

### 简介：

这是我在一个简单项目下使用seq2seq来学习方法来创建语言翻译模型的首次尝试。

你可以通过我的博客来了解更多详细内容：

* [使用seq2seq方法来创建一个语言翻译模型](https://chunml.github.io/ChunML.github.io/project/Sequence-To-Sequence/)

### 数据集：

我使用了Europarl的平行语料库进行训练。为了让源代码立即工作，您必须在下面的链接中使用最新版本(在撰写时发布v8)(以下链接将启动一个180 mb的下载)：

* [Europarl v8](http://www.statmt.org/wmt15/europarl-v8.fi-en.tgz)

您可以自由地将默认数据集更改为您自己的任何人。只是不要忘记修改代码！

### 参数列表：

* max_len: 指定从文本中提取的句子的最大长度。
  默认值：200
* vocab_size: 指定词汇表中最常使用的单词的数量。
  默认值：20000
* batch_size: 指定批大小。
  默认值：1000
* layer_num: 指定解码器网络中重复的层数。
  默认值：3
* hidden_dim: 指定隐藏状态的维数。
  默认值：1000
* np_epoch: 指定培训的数量。
  默认值：20
* mode: 指定是否对模型进行培训或测试。
  默认值：train

### 训练模型：

* 基于默认配置：

```python
python seq2seq.py
```

* 基于用户自定义的配置：

```python
# Max length:= 300, number of recurrent layers:= 2, dimension of hidden state:= 500
python seq2seq.py -max_len 300 -layer_num 2 -hidden_dim 500
```

### 测试模型：

网络必须要至少训练一次（训练权重必须存在！）

* 如果网路是基于配置训练的：

```python
python seq2seq.py -mode test
```

* 如果网络时基于用户自定义配置训练的：

```python
# Max length:= 300, number of recurrent layers:= 2, dimension of hidden state:= 500
python seq2seq.py -mode test -max_len 300 -layer_num 2 -hidden_dim 500
```
