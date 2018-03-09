# Paper reading

[TOC]

## CNN 分类

### LeNet

得分解释：得分高的神经元组合成的路径为一条可能的解释路径

bias/norm能够保证平移不变性

subsampling：减轻小变化所带来的影响，减小敏感性

### AlexNet

在cpu上做出图像变换，喂给gpu；测试的时候将图片经过不同变换之后取预测概率平均值

dropout：每个神经元dropout概率为0.5，测试的时候每个的输出×2

### ZFNet

反卷积：“Adaptive deconvolutional networks for mid and high level feature learning”，根据可视化的特征进行网络结构的修改

前面的层收敛，然后后面的层再收敛：越深收敛越慢，不是同时以相同速度收敛的（梯度弥散 => sudden jumps）

卷积核太大：会把noise（低频与高频）吸收进来，冲淡原始signal

？网络对图片操作具有鲁棒性（较高层次提取的feature对于平移和尺度变化具有不变性，对非中心对称的旋转不具有不变性）：应该是学会了参数化命题？还是原始图像变换之后的数据喂的好？（AlexNet里面说没做图像变换效果很差） => 给出差异，神经网络能够从中学出共性

### VGG

Train：