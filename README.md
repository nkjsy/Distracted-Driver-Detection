# Distracted-Driver-Detection
MLND capstone

本项目使用Anaconda开发环境，用到的开发包有python3，基于TensorFlow的keras，OpenCV等。

训练数据来自kaggle竞赛：https://www.kaggle.com/c/state-farm-distracted-driver-detection/data

一共13个模型的代码分别为M1.ipynb到M13.ipynb，其训练结果分别为my_submission1.csv到my_submission13.csv
另外还有最后用来做模型融合的Merger.ipynb,输出f_submission为多个模型融合后的结果。
CAM Analysis.ipynb利用CAM可视化技术展示了一些模型误判的图片，以及数据增强后的图片。

使用迁移学习方法，在ResNet50，InceptionV3，Xception，InceptionResNetV2预训练模型后分别接GAP，dropout和全连接层分类器。训练中采用early stopping，最多5代。在AWS p2.xlarge实例上训练，使用4个worker并行，每一代训练需要约30分钟。训练得到的模型保存为my_model1.h5到my_model13.h5

最终融合后的模型提交到kaggle上，private score 0.22 排名91。
