# OpenMMLab-Learning
The recore of learning and practising OpenMMLab

This is the first assignment for OpenMMLab, and the assignment description is as follows:
### 题目：基于RTMPose的耳朵穴位关键点检测  

**背景**：根据中医的“倒置胎儿”学说，耳朵的穴位反映了人体全身脏器的健康，耳穴按摩可以缓解失眠多梦、内分泌失调等疾病。耳朵面积较小，但穴位密集，涉及耳舟、耳轮、三角窝、耳甲艇、对耳轮等三维轮廓，普通人难以精准定位耳朵穴位。  

**任务**  
1.Labelme标注关键点检测数据集（子豪兄已经帮你完成了）  
2.划分训练集和测试集（子豪兄已经帮你完成了）  
3.Labelme标注转MS COCO格式（子豪兄已经帮你完成了）  
4.使用MMDetection算法库，训练RTMDet耳朵目标检测算法，提交测试集评估指标  
5.使用MMPose算法库，训练RTMPose耳朵关键点检测算法，提交测试集评估指标  
6.用自己耳朵的图像预测，将预测结果发到群里  
7.用自己耳朵的视频预测，将预测结果发到群里  
需提交的测试集评估指标（不能低于baseline指标的50%）  

**数据集**  
耳朵穴位关键点检测数据集，MS COCO格式，划分好了训练集和测试集，并写好了样例config配置文件
链接: [数据集百度网盘](https://pan.baidu.com/s/1swTLpArj7XEDXW4d0lo7Mg) 提取码: 741p
标注人：张子豪、田文博

## Processing  
本次使用的是RTMDet和RTMPose算法，首先在**mmdetection**中创建**data文件夹**将数据，标签和模型配置文件放**data文件夹**中，训练时会自动创建**work_dir文件夹**，训练过程中日志文件和模型训练权重都放在了这个文件夹中。  
对于**mmpose**也是一样的流程。  
#### train:
~~~
python tools/train.py data/rtmdet_tiny_ear.py 
~~~
#### test:  
~~~
python tools/test.py data/rtmdet_tiny_ear.py work_dirs/rtmdet_tiny_ear/best_coco_bbox_mAP_epoch_198.pth 
~~~
测试结果如下：  
[图片](/home/duxing/图片/test.png "测试集结果")
