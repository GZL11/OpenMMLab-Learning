README

### 作业内容:

#### 1.  题目：

基于 ResNet50 的水果分类

#### 2. 背景：

使用基于卷积的深度神经网络 ResNet50 对 30 种水果进行分类

#### 3. 任务

划分训练集和验证集；
按照 MMPreTrain CustomDataset 格式组织训练集和验证集；
使用 MMPreTrain 算法库，编写配置文件，正确加载预训练模型；
在水果数据集上进行微调训练；
使用 MMPreTrain 的 ImageClassificationInferencer 接口，对网络水果图像，或自己拍摄的水果图像，使用训练好的模型进行分类。

需提交的验证集评估指标（不能低于 60%）

**ResNet-50**

#### 4.  作业数据集下载：

链接：(https://pan.baidu.com/s/1YgoU1M_v7ridtXB9xxbA1Q)
[百度网盘地址](https://pan.baidu.com/s/1YgoU1M_v7ridtXB9xxbA1Q?pwd=52m9)
提取码：52m9

课程中猫狗数据集下载地址：

https://download.openmmlab.com/mmclassification/dataset/cats_dogs_dataset.tar

#### 5. 提交方式

请将作业内容上传到你自己的github仓库，并把对应的链接回复在评论区


### 作业:

1.构建config文件

配置文件主要包括model settings, dataset settings, schedules, default_runtime四部分,本次使用的是resnet50作为backbone.

2.构建训练集,验证集与测试集数据  

3.模型训练train:  

~~~

python tools/train.py project/Fruit_classification/resnet50_finetune.py  --work-dir=./output

~~~

4.验证(结果见precison_result.png):

~~~

python tools/test.py project/Fruit_classification/resnet50_finetune.py --checkpoint output/best_accuracy_top1_epoch_160.pth

~~~

5.模型推理(结果见detection_result.png)

~~~

python tools/analysis_tools/analyze_results.py project/Fruit_classification/resnet50_finetune.py result.pkl --out-dir analyze

~~~
