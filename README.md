# Distracted-Driver-Detection
MLND capstone

本项目使用Anaconda开发环境，用到的开发包有python3，keras，OpenCV等。

训练数据来自kaggle竞赛：https://www.kaggle.com/c/state-farm-distracted-driver-detection/data

我导出的特征向量可以从百度云下载：https://pan.baidu.com/s/1pLQgxsv 
其中gap为未经数据增强的图片集，gap_aug为图片增强后，增加了一倍图片数量的图片集。

以下为在AWS的p2.xlarge实例上运行的时间：

迁移学习方法1：在ResNet50后接自己的全连接层分类器。经过一倍数量的数据增强，训练10代。需要约1小时。训练得到的模型保存为my_model.h5

迁移学习方法2：用ResNet50，VGG16，InceptionV3导出训练图片的特征向量，经过模型融合后，用全连接神经网络分类。导出一次训练图片约10分钟，导出一次测试图片约40分钟。特征向量在本地分类器训练很快，可以忽略。
