# FaceRank
##最近在做一个FaceRank的研究，使用的是华南理工大学公开的SCUT -FBP5500数据集
下载地址：https://github.com/HCIILAB/SCUT-FBP5500-Database-Release
数据集中包含了(2000亚洲女性，2000张亚洲男性，750张高加索女性，750张高加索男性的面部照片 )并且由60个人给这些图片打分，最后得到每一张图片对应的分数。现在需要做的是利用卷积神经网络训练这些图片对新的面部得出预测分数。神经网络采用的是LeNet-5模型。
将原始数据集中以4:1的比例划分训练集和测试集，原始数据集中的得分为1-5，我将得分扩大为1-10分，然后对原始数据进行一些处理，利用face_recognition库截取他们的面部，重新设置面部大小为64*64的图片，最后将处理后的喂入神经网络中训练并将训练好的模型保存下来用于测试。
split_image_data.py用于分割数据集
rename.py将原始数据图片以标签-图片名重命名
find_face.py将原始图像中的面部截取出来重新保存
resize_image.py截取出来的面部图片大小设置为64*64
data.py用于读取图片数据转换为像素矩阵以及读取标签并且存储在队列中
train.py实现了Lenet-5模型训练网络
test.py用于测试模型准确率
app.py根据图片路径给出预测得分

