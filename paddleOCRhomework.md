【OCR】PaddleOCR文字识别¶
# 1.1 环境准备
首先，安装PaddleOCR的依赖库。
%cd ~ 
!unzip PaddleOCR-dygraph.zip
# 安装依赖库
!pip install -r requirements.txt -i https://mirror.baidu.com/pypi/simple
### 1.2. 准备inference model和测试数据

我们已经为您准备好了中文轻量级OCR模型的inference model，并放在了~/inference 目录下，可以调用如下命令在测试图像上得到识别结果。
您也可以通过以下指令下载最新的inference model
!mkdir inference
%cd /home/aistudio/PaddleOCR/inference
# 下载超轻量中文检测模型：
!wget  https://paddleocr.bj.bcebos.com/PP-OCRv3/chinese/ch_PP-OCRv3_det_infer.tar
!tar xf ch_PP-OCRv3_det_infer.tar
# 下载超轻量中文识别模型：
!wget  https://paddleocr.bj.bcebos.com/PP-OCRv3/chinese/ch_PP-OCRv3_rec_infer.tar
!tar xf ch_PP-OCRv3_rec_infer.tar
import matplotlib.pyplot as plt
from PIL import Image

## 显示原图，读取名称为11.jpg的测试图像
img_path= "./doc/imgs/11.jpg"
img = Image.open(img_path)
plt.figure("test_img", figsize=(30,30))
plt.imshow(img)
plt.show()
### 1.3. 测试单张图像
下面开始调用tools/infer/predict_system.py 完成图像文本识别，共需要传入三个参数：
- image_dir： 指定要测试的图像
- det_model_dir： 指定轻量检测模型的inference model
- rec_model_dir： 指定轻量识别模型的inference model
%cd /home/aistudio/PaddleOCR/
# 快速运行
# 注意 PP-OCRv3的识别模型使用的输入shape为3,48,320, 如果使用其他识别模型，则需根据模型设置参数--rec_image_shape。此外，PP-OCRv3的识别模型默认使用的rec_algorithm为SVTR_LCNet，注意和原始SVTR的区别。
# 以超轻量中文OCR模型推理为例，在执行预测时，需要通过参数image_dir指定单张图像或者图像集合的路径、参数det_model_dir,cls_model_dir和rec_model_dir分别指定检测，方向分类和识别的inference模型路径。参数use_angle_cls用于控制是否启用方向分类模型。use_mp表示是否使用多进程。total_process_num表示在使用多进程时的进程数。可视化识别结果默认保存到 ./inference_results 文件夹里面。
#!python3 tools/infer/predict_system.py --image_dir="./doc/imgs/11.jpg" --det_model_dir="./inference/ch_det_mv3_db/"  --rec_model_dir="./inference/ch_rec_mv3_crnn/"
# 使用方向分类器
#python3 tools/infer/predict_system.py --image_dir="./doc/imgs/00018069.jpg" --det_model_dir="./ch_PP-OCRv3_det_infer/" --cls_model_dir="./cls/" --rec_model_dir="./ch_PP-OCRv3_rec_infer/" --use_angle_cls=true
# 不使用方向分类器
!python3 tools/infer/predict_system.py --image_dir="./doc/imgs/11.jpg" --det_model_dir="./inference/ch_PP-OCRv3_det_infer" --rec_model_dir="./inference/ch_PP-OCRv3_rec_infer" --use_angle_cls=false
# 使用多进程
#python3 tools/infer/predict_system.py --image_dir="./doc/imgs/00018069.jpg" --det_model_dir="./ch_PP-OCRv3_det_infer/" --rec_model_dir="./ch_PP-OCRv3_rec_infer/" --use_angle_cls=false --use_mp=True --total_process_num=6
输出结果中有两列数据，第一列表示PaddleOCR识别出的文字，第二列表示识别出当前文字的置信度。置信度的数据范围是[0-1]，置信度越接近1表示文本识别对的“信心”越大。

如下输出结果中：
```
纯臻营养护发素, 0.944
产品信息/参数, 0.984
```
表示识别文本为 “纯臻营养护发素” 的置信度是0.944， 识别“产品信息/参数” 的置信度是0.984。

同时，识别结果会可视化在图像中并保存在./inference_results文件夹下，可以通过左边的目录结构选择要打开的文件，
也可以通过如下代码将可视化后的图像显示出来，观察OCR文本识别的效果。
## 显示轻量级模型识别结果
img_path= "./inference_results/11.jpg"
img = Image.open(img_path)
plt.figure("results_img", figsize=(30,30))
plt.imshow(img)
plt.show()
### 1.4 测试多张图像
image_dir支持传入单张图像和图像所在的文件目录，当image_dir指定的是图像目录时，运行上述指令会预测当前文件夹下的所有图像中的文字，并将预测的可视化结果保存在inference_results文件夹下。
# 预测doc/imgs文件夹下的所有图像
!python3 tools/infer/predict_system.py --image_dir="./doc/imgs/" --det_model_dir="./inference/ch_PP-OCRv3_det_infer/" --rec_model_dir="./inference/ch_PP-OCRv3_rec_infer/" --use_angle_cls=false
## 显示轻量级模型识别结果
## 可视化1.jpg的文本识别效果
img_path= "./inference_results/00015504.jpg"
img = Image.open(img_path)
plt.figure("results_img", figsize=(20,20))
plt.imshow(img)
plt.show()
## 显示轻量级模型识别结果
## 可视化12.jpg的文本识别效果
img_path= "./inference_results/00057937.jpg"
img = Image.open(img_path)
plt.figure("results_img", figsize=(20,20))
plt.imshow(img)
plt.show()
## 2. 训练文字检测模型

本节以icdar15数据集为例，介绍如何完成PaddleOCR中文字检测模型的训练、评估与测试。

### 2.1. 数据准备
我们已经为您准备好了icdar15的数据集，存放在 ~/data/data34815/icdar2015.tar 中，可以运行如下指令完成数据集解压。
!cd ~/data/data34815/ && tar xf icdar2015.tar && mv icdar2015  ~/PaddleOCR/train_data/
# !tar -xf /home/aistudio/data/data34815/icdar2015.tar
# !mv icdar2015  ~/PaddleOCR/train_data/icdar2015/
### 2.2 快速启动训练

首先下载pretrain model，PaddleOCR的检测模型目前支持两种backbone，分别是MobileNetV3、ResNet50_vd，
您可以根据需求使用[PaddleClas](https://github.com/PaddlePaddle/PaddleClas/tree/master/ppcls/modeling/architectures)中的模型更换backbone。
# 下载MobileNetV3的预训练模型
!wget -P ./pretrain_models/ https://paddleocr.bj.bcebos.com/pretrained/MobileNetV3_large_x0_5_pretrained.pdparams 
# 单机单卡训练 mv3_db 模型
!python3 tools/train.py -c configs/det/det_mv3_db.yml \
     -o Global.pretrained_model=./pretrain_models/MobileNetV3_large_x0_5_pretrained
     ### 2.3 指标评估

PaddleOCR计算三个OCR检测相关的指标，分别是：Precision、Recall、Hmean（F-Score）。

训练中模型参数默认保存在Global.save_model_dir目录下。在评估指标时，需要设置Global.checkpoints指向保存的参数文件。
!python3 tools/eval.py -c configs/det/det_mv3_db.yml  -o Global.checkpoints="./output/db_mv3/latest.pdparams"
# 2.4 测试检测效果
## 可视化00006737.jpg的文本识别效果
img_path= "./output/det_db/det_results/00006737.jpg"
img = Image.open(img_path)
plt.figure("results_img", figsize=(20,20))
plt.imshow(img)
plt.show()
# 2.5 模型导出与预测
inference 模型（paddle.jit.save保存的模型） 一般是模型训练，把模型结构和模型参数保存在文件中的固化模型，多用于预测部署场景。 训练过程中保存的模型是checkpoints模型，保存的只有模型的参数，多用于恢复训练等。 与checkpoints模型相比，inference 模型会额外保存模型的结构信息，在预测部署、加速推理上性能优越，灵活方便，适合于实际系统集成。

检测模型转inference 模型方式：
# 加载配置文件`det_mv3_db.yml`，从`output/det_db`目录下加载`best_accuracy`模型，inference模型保存在`./output/det_db_inference`目录下
python3 tools/export_model.py -c configs/det/det_mv3_db.yml -o Global.pretrained_model="./output/det_db/best_accuracy" Global.save_inference_dir="./output/det_db_inference/"
!python3 tools/infer_det.py -c configs/det/det_mv3_db.yml -o TestReader.infer_img="./doc/imgs_en/"  Global.checkpoints="./output/det_db/best_accuracy"
## 3. 训练文字识别模型


### 3.1. 数据准备
我们在 ~/data/data34824/ 目录下准备了数据集，可以使用如下指令解压数据文件。
!cd ./train_data/ && mkdir -p ic15_data && cd ic15_data && cp ~/data/data34824/ic15_rec.zip ./ && unzip -o -q ic15_rec.zip && tar xf ic15.tar
### 3.2. 快速启动训练

首先下载pretrain model，PaddleOCR的检测模型目前支持两种backbone，分别是MobileNetV3、ResNet50_vd，
您可以根据需求使用[PaddleClas](https://github.com/PaddlePaddle/PaddleClas/tree/master/ppcls/modeling/architectures)中的模型更换backbone。
本节将以 CRNN 识别模型为例：

首先下载pretrain model，您可以下载训练好的模型在 icdar2015 数据上进行finetune。
!wget -P ./pretrain_models/ https://paddleocr.bj.bcebos.com/rec_mv3_none_bilstm_ctc.tar
!cd pretrain_models && tar -xf rec_mv3_none_bilstm_ctc.tar && rm -rf rec_mv3_none_bilstm_ctc.tar
!python3 tools/train.py -c configs/rec/rec_icdar15_train.yml
