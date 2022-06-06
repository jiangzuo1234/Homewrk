【OCR】PaddleOCR文字识别¶
# 1.1 环境准备
首先，安装PaddleOCR的依赖库。
%cd ~ 
!unzip PaddleOCR-dygraph.zip
# 安装依赖库
!pip install -r requirements.txt -i https://mirror.baidu.com/pypi/simple
### 1.2. 准备inference model和测试数据

我们已经为您准备好了中文轻量级OCR模型的inference model，并放在了~/inference 目录下，可以调用如下命令在测试图像上得到识别结果。
您也可以通过以下指令下载最新的inference model。
!mkdir inference
%cd /home/aistudio/PaddleOCR/inference
