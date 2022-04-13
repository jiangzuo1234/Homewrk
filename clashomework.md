一、环境配置
In [1]
# 下载paddleclass
!git clone https://gitee.com/paddlepaddle/PaddleClas.git -b release/2.3
正克隆到 'PaddleClas'...
remote: Enumerating objects: 25293, done.
remote: Counting objects: 100% (5176/5176), done.
remote: Compressing objects: 100% (1840/1840), done.
remote: Total 25293 (delta 3636), reused 4691 (delta 3319), pack-reused 20117
接收对象中: 100% (25293/25293), 155.60 MiB | 10.93 MiB/s, 完成.
处理 delta 中: 100% (17421/17421), 完成.
检查连接... 完成。
In [2]
#安装python依赖库
%cd PaddleClas/
!pip install --upgrade -r requirements.txt -i https://mirror.baidu.com/pypi/simple
/home/aistudio/PaddleClas
Looking in indexes: https://mirror.baidu.com/pypi/simple
Requirement already satisfied: prettytable in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from -r requirements.txt (line 1)) (0.7.2)
Collecting prettytable
  Using cached https://mirror.baidu.com/pypi/packages/96/53/91638391af5a68d27402b920ccc3fdfae51dd3e333476b414393d4478a70/prettytable-3.2.0-py3-none-any.whl (26 kB)
Requirement already satisfied: ujson in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from -r requirements.txt (line 2)) (5.1.0)
Collecting ujson
  Using cached https://mirror.baidu.com/pypi/packages/66/ee/4c06c86fc3b7a6175d2681efa877be48d146edcebfd5889afc4af6a8674a/ujson-5.2.0-cp37-cp37m-manylinux_2_17_x86_64.manylinux2014_x86_64.whl (45 kB)
Collecting opencv-python==4.4.0.46
  Using cached https://mirror.baidu.com/pypi/packages/1b/2d/62eba161d3d713e1720504de1c25d439b02c85159804d9ecead10be5d87e/opencv_python-4.4.0.46-cp37-cp37m-manylinux2014_x86_64.whl (49.5 MB)
Requirement already satisfied: pillow in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from -r requirements.txt (line 4)) (8.2.0)
Collecting pillow
  Downloading https://mirror.baidu.com/pypi/packages/10/e8/360519e53809ed7d6658605efff9e2423aff136516b6f0afac9b79c1a5ed/Pillow-9.1.0-cp37-cp37m-manylinux_2_17_x86_64.manylinux2014_x86_64.whl (4.3 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 4.3/4.3 MB 9.9 MB/s eta 0:00:00:00:0100:01
Requirement already satisfied: tqdm in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from -r requirements.txt (line 5)) (4.27.0)
Collecting tqdm
  Downloading https://mirror.baidu.com/pypi/packages/8a/c4/d15f1e627fff25443ded77ea70a7b5532d6371498f9285d44d62587e209c/tqdm-4.64.0-py2.py3-none-any.whl (78 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 78.4/78.4 KB 12.6 MB/s eta 0:00:00
Requirement already satisfied: PyYAML in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from -r requirements.txt (line 6)) (5.1.2)
Collecting PyYAML
  Downloading https://mirror.baidu.com/pypi/packages/eb/5f/6e6fe6904e1a9c67bc2ca5629a69e7a5a0b17f079da838bab98a1e548b25/PyYAML-6.0-cp37-cp37m-manylinux_2_5_x86_64.manylinux1_x86_64.manylinux_2_12_x86_64.manylinux2010_x86_64.whl (596 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 596.3/596.3 KB 12.1 MB/s eta 0:00:00a 0:00:01
Requirement already satisfied: visualdl>=2.2.0 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from -r requirements.txt (line 7)) (2.2.3)
Requirement already satisfied: scipy in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from -r requirements.txt (line 8)) (1.6.3)
Collecting scipy
  Downloading https://mirror.baidu.com/pypi/packages/58/4f/11f34cfc57ead25752a7992b069c36f5d18421958ebd6466ecd849aeaf86/scipy-1.7.3-cp37-cp37m-manylinux_2_12_x86_64.manylinux2010_x86_64.whl (38.1 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 38.1/38.1 MB 7.5 MB/s eta 0:00:00:00:0100:01
Collecting scikit-learn==0.23.2
  Downloading https://mirror.baidu.com/pypi/packages/f4/cb/64623369f348e9bfb29ff898a57ac7c91ed4921f228e9726546614d63ccb/scikit_learn-0.23.2-cp37-cp37m-manylinux1_x86_64.whl (6.8 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 6.8/6.8 MB 9.5 MB/s eta 0:00:00:00:0100:01
Requirement already satisfied: gast==0.3.3 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from -r requirements.txt (line 10)) (0.3.3)
Collecting faiss-cpu==1.7.1.post2
  Downloading https://mirror.baidu.com/pypi/packages/4c/d6/072a9d18430b8c68c99ffb49fe14fbf89c62f71dcd4f5f692c7691447a14/faiss_cpu-1.7.1.post2-cp37-cp37m-manylinux_2_17_x86_64.manylinux2014_x86_64.whl (8.4 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 8.4/8.4 MB 9.6 MB/s eta 0:00:00:00:0100:01
Requirement already satisfied: numpy>=1.14.5 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from opencv-python==4.4.0.46->-r requirements.txt (line 3)) (1.19.5)
Requirement already satisfied: threadpoolctl>=2.0.0 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from scikit-learn==0.23.2->-r requirements.txt (line 9)) (2.1.0)
Requirement already satisfied: joblib>=0.11 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from scikit-learn==0.23.2->-r requirements.txt (line 9)) (0.14.1)
Requirement already satisfied: importlib-metadata in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from prettytable->-r requirements.txt (line 1)) (4.2.0)
Requirement already satisfied: wcwidth in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from prettytable->-r requirements.txt (line 1)) (0.1.7)
Requirement already satisfied: protobuf>=3.11.0 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from visualdl>=2.2.0->-r requirements.txt (line 7)) (3.14.0)
Requirement already satisfied: flake8>=3.7.9 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from visualdl>=2.2.0->-r requirements.txt (line 7)) (4.0.1)
Requirement already satisfied: pandas in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from visualdl>=2.2.0->-r requirements.txt (line 7)) (1.1.5)
Requirement already satisfied: requests in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from visualdl>=2.2.0->-r requirements.txt (line 7)) (2.24.0)
Requirement already satisfied: pre-commit in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from visualdl>=2.2.0->-r requirements.txt (line 7)) (1.21.0)
Requirement already satisfied: matplotlib in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from visualdl>=2.2.0->-r requirements.txt (line 7)) (2.2.3)
Requirement already satisfied: Flask-Babel>=1.0.0 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from visualdl>=2.2.0->-r requirements.txt (line 7)) (1.0.0)
Requirement already satisfied: six>=1.14.0 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from visualdl>=2.2.0->-r requirements.txt (line 7)) (1.16.0)
Requirement already satisfied: bce-python-sdk in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from visualdl>=2.2.0->-r requirements.txt (line 7)) (0.8.53)
Requirement already satisfied: flask>=1.1.1 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from visualdl>=2.2.0->-r requirements.txt (line 7)) (1.1.1)
Requirement already satisfied: shellcheck-py in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from visualdl>=2.2.0->-r requirements.txt (line 7)) (0.7.1.1)
Requirement already satisfied: pyflakes<2.5.0,>=2.4.0 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from flake8>=3.7.9->visualdl>=2.2.0->-r requirements.txt (line 7)) (2.4.0)
Requirement already satisfied: mccabe<0.7.0,>=0.6.0 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from flake8>=3.7.9->visualdl>=2.2.0->-r requirements.txt (line 7)) (0.6.1)
Requirement already satisfied: pycodestyle<2.9.0,>=2.8.0 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from flake8>=3.7.9->visualdl>=2.2.0->-r requirements.txt (line 7)) (2.8.0)
Requirement already satisfied: click>=5.1 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from flask>=1.1.1->visualdl>=2.2.0->-r requirements.txt (line 7)) (7.0)
Requirement already satisfied: itsdangerous>=0.24 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from flask>=1.1.1->visualdl>=2.2.0->-r requirements.txt (line 7)) (1.1.0)
Requirement already satisfied: Jinja2>=2.10.1 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from flask>=1.1.1->visualdl>=2.2.0->-r requirements.txt (line 7)) (3.0.0)
Requirement already satisfied: Werkzeug>=0.15 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from flask>=1.1.1->visualdl>=2.2.0->-r requirements.txt (line 7)) (0.16.0)
Requirement already satisfied: Babel>=2.3 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from Flask-Babel>=1.0.0->visualdl>=2.2.0->-r requirements.txt (line 7)) (2.9.1)
Requirement already satisfied: pytz in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from Flask-Babel>=1.0.0->visualdl>=2.2.0->-r requirements.txt (line 7)) (2022.1)
Requirement already satisfied: zipp>=0.5 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from importlib-metadata->prettytable->-r requirements.txt (line 1)) (3.7.0)
Requirement already satisfied: typing-extensions>=3.6.4 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from importlib-metadata->prettytable->-r requirements.txt (line 1)) (4.1.1)
Requirement already satisfied: pycryptodome>=3.8.0 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from bce-python-sdk->visualdl>=2.2.0->-r requirements.txt (line 7)) (3.9.9)
Requirement already satisfied: future>=0.6.0 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from bce-python-sdk->visualdl>=2.2.0->-r requirements.txt (line 7)) (0.18.0)
Requirement already satisfied: kiwisolver>=1.0.1 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from matplotlib->visualdl>=2.2.0->-r requirements.txt (line 7)) (1.1.0)
Requirement already satisfied: cycler>=0.10 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from matplotlib->visualdl>=2.2.0->-r requirements.txt (line 7)) (0.10.0)
Requirement already satisfied: pyparsing!=2.0.4,!=2.1.2,!=2.1.6,>=2.0.1 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from matplotlib->visualdl>=2.2.0->-r requirements.txt (line 7)) (3.0.7)
Requirement already satisfied: python-dateutil>=2.1 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from matplotlib->visualdl>=2.2.0->-r requirements.txt (line 7)) (2.8.2)
Requirement already satisfied: cfgv>=2.0.0 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from pre-commit->visualdl>=2.2.0->-r requirements.txt (line 7)) (2.0.1)
Requirement already satisfied: virtualenv>=15.2 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from pre-commit->visualdl>=2.2.0->-r requirements.txt (line 7)) (16.7.9)
Requirement already satisfied: nodeenv>=0.11.1 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from pre-commit->visualdl>=2.2.0->-r requirements.txt (line 7)) (1.3.4)
Requirement already satisfied: toml in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from pre-commit->visualdl>=2.2.0->-r requirements.txt (line 7)) (0.10.0)
Requirement already satisfied: identify>=1.0.0 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from pre-commit->visualdl>=2.2.0->-r requirements.txt (line 7)) (1.4.10)
Requirement already satisfied: aspy.yaml in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from pre-commit->visualdl>=2.2.0->-r requirements.txt (line 7)) (1.3.0)
Requirement already satisfied: chardet<4,>=3.0.2 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from requests->visualdl>=2.2.0->-r requirements.txt (line 7)) (3.0.4)
Requirement already satisfied: certifi>=2017.4.17 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from requests->visualdl>=2.2.0->-r requirements.txt (line 7)) (2021.10.8)
Requirement already satisfied: urllib3!=1.25.0,!=1.25.1,<1.26,>=1.21.1 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from requests->visualdl>=2.2.0->-r requirements.txt (line 7)) (1.25.11)
Requirement already satisfied: idna<3,>=2.5 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from requests->visualdl>=2.2.0->-r requirements.txt (line 7)) (2.10)
Requirement already satisfied: MarkupSafe>=2.0.0rc2 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from Jinja2>=2.10.1->flask>=1.1.1->visualdl>=2.2.0->-r requirements.txt (line 7)) (2.0.1)
Requirement already satisfied: setuptools in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from kiwisolver>=1.0.1->matplotlib->visualdl>=2.2.0->-r requirements.txt (line 7)) (56.2.0)
Installing collected packages: faiss-cpu, ujson, tqdm, scipy, PyYAML, pillow, opencv-python, scikit-learn, prettytable
  Attempting uninstall: ujson
    Found existing installation: ujson 5.1.0
    Uninstalling ujson-5.1.0:
      Successfully uninstalled ujson-5.1.0
  Attempting uninstall: tqdm
    Found existing installation: tqdm 4.27.0
    Uninstalling tqdm-4.27.0:
      Successfully uninstalled tqdm-4.27.0
  Attempting uninstall: scipy
    Found existing installation: scipy 1.6.3
    Uninstalling scipy-1.6.3:
      Successfully uninstalled scipy-1.6.3
  Attempting uninstall: PyYAML
    Found existing installation: PyYAML 5.1.2
    Uninstalling PyYAML-5.1.2:
      Successfully uninstalled PyYAML-5.1.2
  Attempting uninstall: pillow
    Found existing installation: Pillow 8.2.0
    Uninstalling Pillow-8.2.0:
      Successfully uninstalled Pillow-8.2.0
  Attempting uninstall: opencv-python
    Found existing installation: opencv-python 4.1.1.26
    Uninstalling opencv-python-4.1.1.26:
      Successfully uninstalled opencv-python-4.1.1.26
  Attempting uninstall: scikit-learn
    Found existing installation: scikit-learn 0.24.2
    Uninstalling scikit-learn-0.24.2:
      Successfully uninstalled scikit-learn-0.24.2
  Attempting uninstall: prettytable
    Found existing installation: prettytable 0.7.2
    Uninstalling prettytable-0.7.2:
      Successfully uninstalled prettytable-0.7.2
ERROR: pip's dependency resolver does not currently take into account all the packages that are installed. This behaviour is the source of the following dependency conflicts.
parl 1.4.1 requires pyzmq==18.1.1, but you have pyzmq 22.3.0 which is incompatible.
paddlefsl 1.0.0 requires pillow==8.2.0, but you have pillow 9.1.0 which is incompatible.
paddlefsl 1.0.0 requires tqdm~=4.27.0, but you have tqdm 4.64.0 which is incompatible.
Successfully installed PyYAML-6.0 faiss-cpu-1.7.1.post2 opencv-python-4.4.0.46 pillow-9.1.0 prettytable-3.2.0 scikit-learn-0.23.2 scipy-1.7.3 tqdm-4.64.0 ujson-5.2.0
In [3]
%cd deploy
/home/aistudio/PaddleClas/deploy
二、准备数据模型
In [4]

%mkdir models
%cd models
# 下载通用检测 inference 模型并解压
!wget https://paddle-imagenet-models-name.bj.bcebos.com/dygraph/rec/models/inference/picodet_PPLCNet_x2_5_mainbody_lite_v1.0_infer.tar && tar -xf picodet_PPLCNet_x2_5_mainbody_lite_v1.0_infer.tar
# 下载识别 inference 模型并解压
!wget https://paddle-imagenet-models-name.bj.bcebos.com/dygraph/rec/models/inference/general_PPLCNet_x2_5_lite_v1.0_infer.tar && tar -xf general_PPLCNet_x2_5_lite_v1.0_infer.tar
/home/aistudio/PaddleClas/deploy/models
--2022-04-13 17:54:04--  https://paddle-imagenet-models-name.bj.bcebos.com/dygraph/rec/models/inference/picodet_PPLCNet_x2_5_mainbody_lite_v1.0_infer.tar
正在解析主机 paddle-imagenet-models-name.bj.bcebos.com (paddle-imagenet-models-name.bj.bcebos.com)... 182.61.200.229, 182.61.200.195, 2409:8c04:1001:1002:0:ff:b001:368a
正在连接 paddle-imagenet-models-name.bj.bcebos.com (paddle-imagenet-models-name.bj.bcebos.com)|182.61.200.229|:443... 已连接。
已发出 HTTP 请求，正在等待回应... 200 OK
长度： 30638080 (29M) [application/x-tar]
正在保存至: “picodet_PPLCNet_x2_5_mainbody_lite_v1.0_infer.tar”

picodet_PPLCNet_x2_ 100%[===================>]  29.22M  10.2MB/s    in 2.9s    

2022-04-13 17:54:07 (10.2 MB/s) - 已保存 “picodet_PPLCNet_x2_5_mainbody_lite_v1.0_infer.tar” [30638080/30638080])

--2022-04-13 17:54:07--  https://paddle-imagenet-models-name.bj.bcebos.com/dygraph/rec/models/inference/general_PPLCNet_x2_5_lite_v1.0_infer.tar
正在解析主机 paddle-imagenet-models-name.bj.bcebos.com (paddle-imagenet-models-name.bj.bcebos.com)... 182.61.200.195, 182.61.200.229, 2409:8c04:1001:1002:0:ff:b001:368a
正在连接 paddle-imagenet-models-name.bj.bcebos.com (paddle-imagenet-models-name.bj.bcebos.com)|182.61.200.195|:443... 已连接。
已发出 HTTP 请求，正在等待回应... 200 OK
长度： 34242560 (33M) [application/x-tar]
正在保存至: “general_PPLCNet_x2_5_lite_v1.0_infer.tar”

general_PPLCNet_x2_ 100%[===================>]  32.66M  60.1MB/s    in 0.5s    

2022-04-13 17:54:08 (60.1 MB/s) - 已保存 “general_PPLCNet_x2_5_lite_v1.0_infer.tar” [34242560/34242560])

In [5]
%cd /home/aistudio/PaddleClas/deploy/
/home/aistudio/PaddleClas/deploy
In [6]
# 下载 demo 数据并解压
!wget https://paddle-imagenet-models-name.bj.bcebos.com/dygraph/rec/data/drink_dataset_v1.0.tar && tar -xf drink_dataset_v1.0.tar
--2022-04-13 17:54:08--  https://paddle-imagenet-models-name.bj.bcebos.com/dygraph/rec/data/drink_dataset_v1.0.tar
正在解析主机 paddle-imagenet-models-name.bj.bcebos.com (paddle-imagenet-models-name.bj.bcebos.com)... 182.61.200.229, 182.61.200.195, 2409:8c04:1001:1002:0:ff:b001:368a
正在连接 paddle-imagenet-models-name.bj.bcebos.com (paddle-imagenet-models-name.bj.bcebos.com)|182.61.200.229|:443... 已连接。
已发出 HTTP 请求，正在等待回应... 200 OK
长度： 48189440 (46M) [application/x-tar]
正在保存至: “drink_dataset_v1.0.tar”

drink_dataset_v1.0. 100%[===================>]  45.96M  33.8MB/s    in 1.4s    

2022-04-13 17:54:10 (33.8 MB/s) - 已保存 “drink_dataset_v1.0.tar” [48189440/48189440])

In [7]
%cd /home/aistudio/PaddleClas/deploy
/home/aistudio/PaddleClas/deploy
In [8]
#使用下载的服务端商品识别模型进行索引库构建
!python3.7 python/build_gallery.py -c configs/inference_general.yaml -o Global.rec_inference_model_dir=./models/general_PPLCNet_x2_5_lite_v1.0_infer
/opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages/paddle/vision/transforms/functional_pil.py:36: DeprecationWarning: NEAREST is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.NEAREST or Dither.NONE instead.
  'nearest': Image.NEAREST,
/opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages/paddle/vision/transforms/functional_pil.py:37: DeprecationWarning: BILINEAR is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.BILINEAR instead.
  'bilinear': Image.BILINEAR,
/opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages/paddle/vision/transforms/functional_pil.py:38: DeprecationWarning: BICUBIC is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.BICUBIC instead.
  'bicubic': Image.BICUBIC,
/opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages/paddle/vision/transforms/functional_pil.py:39: DeprecationWarning: BOX is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.BOX instead.
  'box': Image.BOX,
/opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages/paddle/vision/transforms/functional_pil.py:40: DeprecationWarning: LANCZOS is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.LANCZOS instead.
  'lanczos': Image.LANCZOS,
/opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages/paddle/vision/transforms/functional_pil.py:41: DeprecationWarning: HAMMING is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.HAMMING instead.
  'hamming': Image.HAMMING
2022-04-13 17:54:12 INFO: 
===========================================================
==        PaddleClas is powered by PaddlePaddle !        ==
===========================================================
==                                                       ==
==   For more info please go to the following website.   ==
==                                                       ==
==       https://github.com/PaddlePaddle/PaddleClas      ==
===========================================================

2022-04-13 17:54:12 INFO: DetPostProcess : 
2022-04-13 17:54:12 INFO: DetPreProcess : 
2022-04-13 17:54:12 INFO:     transform_ops : 
2022-04-13 17:54:12 INFO:         DetResize : 
2022-04-13 17:54:12 INFO:             interp : 2
2022-04-13 17:54:12 INFO:             keep_ratio : False
2022-04-13 17:54:12 INFO:             target_size : [640, 640]
2022-04-13 17:54:12 INFO:         DetNormalizeImage : 
2022-04-13 17:54:12 INFO:             is_scale : True
2022-04-13 17:54:12 INFO:             mean : [0.485, 0.456, 0.406]
2022-04-13 17:54:12 INFO:             std : [0.229, 0.224, 0.225]
2022-04-13 17:54:12 INFO:         DetPermute : 
2022-04-13 17:54:12 INFO: Global : 
2022-04-13 17:54:12 INFO:     batch_size : 1
2022-04-13 17:54:12 INFO:     cpu_num_threads : 10
2022-04-13 17:54:12 INFO:     det_inference_model_dir : ./models/picodet_PPLCNet_x2_5_mainbody_lite_v1.0_infer
2022-04-13 17:54:12 INFO:     enable_benchmark : True
2022-04-13 17:54:12 INFO:     enable_mkldnn : True
2022-04-13 17:54:12 INFO:     enable_profile : False
2022-04-13 17:54:12 INFO:     gpu_mem : 8000
2022-04-13 17:54:12 INFO:     image_shape : [3, 640, 640]
2022-04-13 17:54:12 INFO:     infer_imgs : ./drink_dataset_v1.0/test_images/nongfu_spring.jpeg
2022-04-13 17:54:12 INFO:     ir_optim : True
2022-04-13 17:54:12 INFO:     labe_list : ['foreground']
2022-04-13 17:54:12 INFO:     max_det_results : 5
2022-04-13 17:54:12 INFO:     rec_inference_model_dir : ./models/general_PPLCNet_x2_5_lite_v1.0_infer
2022-04-13 17:54:12 INFO:     rec_nms_thresold : 0.05
2022-04-13 17:54:12 INFO:     threshold : 0.2
2022-04-13 17:54:12 INFO:     use_fp16 : False
2022-04-13 17:54:12 INFO:     use_gpu : True
2022-04-13 17:54:12 INFO:     use_tensorrt : False
2022-04-13 17:54:12 INFO: IndexProcess : 
2022-04-13 17:54:12 INFO:     batch_size : 32
2022-04-13 17:54:12 INFO:     data_file : ./drink_dataset_v1.0/gallery/drink_label.txt
2022-04-13 17:54:12 INFO:     delimiter : 	
2022-04-13 17:54:12 INFO:     dist_type : IP
2022-04-13 17:54:12 INFO:     embedding_size : 512
2022-04-13 17:54:12 INFO:     image_root : ./drink_dataset_v1.0/gallery/
2022-04-13 17:54:12 INFO:     index_dir : ./drink_dataset_v1.0/index
2022-04-13 17:54:12 INFO:     index_method : HNSW32
2022-04-13 17:54:12 INFO:     index_operation : new
2022-04-13 17:54:12 INFO:     return_k : 5
2022-04-13 17:54:12 INFO:     score_thres : 0.5
2022-04-13 17:54:12 INFO: RecPostProcess : None
2022-04-13 17:54:12 INFO: RecPreProcess : 
2022-04-13 17:54:12 INFO:     transform_ops : 
2022-04-13 17:54:12 INFO:         ResizeImage : 
2022-04-13 17:54:12 INFO:             size : 224
2022-04-13 17:54:12 INFO:         NormalizeImage : 
2022-04-13 17:54:12 INFO:             mean : [0.485, 0.456, 0.406]
2022-04-13 17:54:12 INFO:             order : 
2022-04-13 17:54:12 INFO:             scale : 0.00392157
2022-04-13 17:54:12 INFO:             std : [0.229, 0.224, 0.225]
2022-04-13 17:54:12 INFO:         ToCHWImage : None
/home/aistudio/PaddleClas/deploy/python/preprocess.py:65: DeprecationWarning: NEAREST is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.NEAREST or Dither.NONE instead.
  'nearest': Image.NEAREST,
/home/aistudio/PaddleClas/deploy/python/preprocess.py:66: DeprecationWarning: BILINEAR is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.BILINEAR instead.
  'bilinear': Image.BILINEAR,
/home/aistudio/PaddleClas/deploy/python/preprocess.py:67: DeprecationWarning: BICUBIC is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.BICUBIC instead.
  'bicubic': Image.BICUBIC,
/home/aistudio/PaddleClas/deploy/python/preprocess.py:68: DeprecationWarning: BOX is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.BOX instead.
  'box': Image.BOX,
/home/aistudio/PaddleClas/deploy/python/preprocess.py:69: DeprecationWarning: LANCZOS is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.LANCZOS instead.
  'lanczos': Image.LANCZOS,
/home/aistudio/PaddleClas/deploy/python/preprocess.py:70: DeprecationWarning: HAMMING is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.HAMMING instead.
  'hamming': Image.HAMMING
100%|████████████████████████████████████████| 987/987 [00:07<00:00, 140.92it/s]
2022-04-13 17:54:21 WARNING: The HNSW32 method dose not support 'remove' operation
In [9]
!pip install faiss-cpu==1.7.1post2
Looking in indexes: https://pypi.tuna.tsinghua.edu.cn/simple
Requirement already satisfied: faiss-cpu==1.7.1post2 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (1.7.1.post2)
三、单张图像识别
In [10]
!python3.7 python/predict_system.py -c configs/inference_general.yaml
/opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages/paddle/vision/transforms/functional_pil.py:36: DeprecationWarning: NEAREST is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.NEAREST or Dither.NONE instead.
  'nearest': Image.NEAREST,
/opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages/paddle/vision/transforms/functional_pil.py:37: DeprecationWarning: BILINEAR is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.BILINEAR instead.
  'bilinear': Image.BILINEAR,
/opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages/paddle/vision/transforms/functional_pil.py:38: DeprecationWarning: BICUBIC is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.BICUBIC instead.
  'bicubic': Image.BICUBIC,
/opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages/paddle/vision/transforms/functional_pil.py:39: DeprecationWarning: BOX is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.BOX instead.
  'box': Image.BOX,
/opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages/paddle/vision/transforms/functional_pil.py:40: DeprecationWarning: LANCZOS is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.LANCZOS instead.
  'lanczos': Image.LANCZOS,
/opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages/paddle/vision/transforms/functional_pil.py:41: DeprecationWarning: HAMMING is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.HAMMING instead.
  'hamming': Image.HAMMING
2022-04-13 17:54:27 INFO: 
===========================================================
==        PaddleClas is powered by PaddlePaddle !        ==
===========================================================
==                                                       ==
==   For more info please go to the following website.   ==
==                                                       ==
==       https://github.com/PaddlePaddle/PaddleClas      ==
===========================================================

2022-04-13 17:54:27 INFO: DetPostProcess : 
2022-04-13 17:54:27 INFO: DetPreProcess : 
2022-04-13 17:54:27 INFO:     transform_ops : 
2022-04-13 17:54:27 INFO:         DetResize : 
2022-04-13 17:54:27 INFO:             interp : 2
2022-04-13 17:54:27 INFO:             keep_ratio : False
2022-04-13 17:54:27 INFO:             target_size : [640, 640]
2022-04-13 17:54:27 INFO:         DetNormalizeImage : 
2022-04-13 17:54:27 INFO:             is_scale : True
2022-04-13 17:54:27 INFO:             mean : [0.485, 0.456, 0.406]
2022-04-13 17:54:27 INFO:             std : [0.229, 0.224, 0.225]
2022-04-13 17:54:27 INFO:         DetPermute : 
2022-04-13 17:54:27 INFO: Global : 
2022-04-13 17:54:27 INFO:     batch_size : 1
2022-04-13 17:54:27 INFO:     cpu_num_threads : 10
2022-04-13 17:54:27 INFO:     det_inference_model_dir : ./models/picodet_PPLCNet_x2_5_mainbody_lite_v1.0_infer
2022-04-13 17:54:27 INFO:     enable_benchmark : True
2022-04-13 17:54:27 INFO:     enable_mkldnn : True
2022-04-13 17:54:27 INFO:     enable_profile : False
2022-04-13 17:54:27 INFO:     gpu_mem : 8000
2022-04-13 17:54:27 INFO:     image_shape : [3, 640, 640]
2022-04-13 17:54:27 INFO:     infer_imgs : ./drink_dataset_v1.0/test_images/nongfu_spring.jpeg
2022-04-13 17:54:27 INFO:     ir_optim : True
2022-04-13 17:54:27 INFO:     labe_list : ['foreground']
2022-04-13 17:54:27 INFO:     max_det_results : 5
2022-04-13 17:54:27 INFO:     rec_inference_model_dir : ./models/general_PPLCNet_x2_5_lite_v1.0_infer
2022-04-13 17:54:27 INFO:     rec_nms_thresold : 0.05
2022-04-13 17:54:27 INFO:     threshold : 0.2
2022-04-13 17:54:27 INFO:     use_fp16 : False
2022-04-13 17:54:27 INFO:     use_gpu : True
2022-04-13 17:54:27 INFO:     use_tensorrt : False
2022-04-13 17:54:27 INFO: IndexProcess : 
2022-04-13 17:54:27 INFO:     batch_size : 32
2022-04-13 17:54:27 INFO:     data_file : ./drink_dataset_v1.0/gallery/drink_label.txt
2022-04-13 17:54:27 INFO:     delimiter : 	
2022-04-13 17:54:27 INFO:     dist_type : IP
2022-04-13 17:54:27 INFO:     embedding_size : 512
2022-04-13 17:54:27 INFO:     image_root : ./drink_dataset_v1.0/gallery/
2022-04-13 17:54:27 INFO:     index_dir : ./drink_dataset_v1.0/index
2022-04-13 17:54:27 INFO:     index_method : HNSW32
2022-04-13 17:54:27 INFO:     index_operation : new
2022-04-13 17:54:27 INFO:     return_k : 5
2022-04-13 17:54:27 INFO:     score_thres : 0.5
2022-04-13 17:54:27 INFO: RecPostProcess : None
2022-04-13 17:54:27 INFO: RecPreProcess : 
2022-04-13 17:54:27 INFO:     transform_ops : 
2022-04-13 17:54:27 INFO:         ResizeImage : 
2022-04-13 17:54:27 INFO:             size : 224
2022-04-13 17:54:27 INFO:         NormalizeImage : 
2022-04-13 17:54:27 INFO:             mean : [0.485, 0.456, 0.406]
2022-04-13 17:54:27 INFO:             order : 
2022-04-13 17:54:27 INFO:             scale : 0.00392157
2022-04-13 17:54:27 INFO:             std : [0.229, 0.224, 0.225]
2022-04-13 17:54:27 INFO:         ToCHWImage : None
/home/aistudio/PaddleClas/deploy/python/preprocess.py:65: DeprecationWarning: NEAREST is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.NEAREST or Dither.NONE instead.
  'nearest': Image.NEAREST,
/home/aistudio/PaddleClas/deploy/python/preprocess.py:66: DeprecationWarning: BILINEAR is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.BILINEAR instead.
  'bilinear': Image.BILINEAR,
/home/aistudio/PaddleClas/deploy/python/preprocess.py:67: DeprecationWarning: BICUBIC is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.BICUBIC instead.
  'bicubic': Image.BICUBIC,
/home/aistudio/PaddleClas/deploy/python/preprocess.py:68: DeprecationWarning: BOX is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.BOX instead.
  'box': Image.BOX,
/home/aistudio/PaddleClas/deploy/python/preprocess.py:69: DeprecationWarning: LANCZOS is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.LANCZOS instead.
  'lanczos': Image.LANCZOS,
/home/aistudio/PaddleClas/deploy/python/preprocess.py:70: DeprecationWarning: HAMMING is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.HAMMING instead.
  'hamming': Image.HAMMING
Inference: 43.79987716674805 ms per batch image
[{'bbox': [244, 49, 509, 964], 'rec_docs': '农夫山泉-饮用天然水', 'rec_scores': 0.7585665}]
In [11]
#可视化识别结果
import matplotlib.pyplot as plt
import matplotlib.image as mpimg 
%matplotlib inline
# 预测结果展示
img = mpimg.imread("output/nongfu_spring.jpeg")
plt.figure(figsize=(10,10))
plt.imshow(img) 
plt.axis('off') 
plt.show()

<Figure size 720x720 with 1 Axes>
四、批量图像识别
In [12]
# 使用下面的命令使用 GPU 进行预测，如果希望使用 CPU 预测，可以在命令后面添加 -o Global.use_gpu=False
!python3.7 python/predict_system.py -c configs/inference_general.yaml -o Global.infer_imgs="./drink_dataset_v1.0/test_images/"
/opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages/paddle/vision/transforms/functional_pil.py:36: DeprecationWarning: NEAREST is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.NEAREST or Dither.NONE instead.
  'nearest': Image.NEAREST,
/opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages/paddle/vision/transforms/functional_pil.py:37: DeprecationWarning: BILINEAR is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.BILINEAR instead.
  'bilinear': Image.BILINEAR,
/opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages/paddle/vision/transforms/functional_pil.py:38: DeprecationWarning: BICUBIC is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.BICUBIC instead.
  'bicubic': Image.BICUBIC,
/opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages/paddle/vision/transforms/functional_pil.py:39: DeprecationWarning: BOX is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.BOX instead.
  'box': Image.BOX,
/opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages/paddle/vision/transforms/functional_pil.py:40: DeprecationWarning: LANCZOS is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.LANCZOS instead.
  'lanczos': Image.LANCZOS,
/opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages/paddle/vision/transforms/functional_pil.py:41: DeprecationWarning: HAMMING is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.HAMMING instead.
  'hamming': Image.HAMMING
2022-04-13 17:54:37 INFO: 
===========================================================
==        PaddleClas is powered by PaddlePaddle !        ==
===========================================================
==                                                       ==
==   For more info please go to the following website.   ==
==                                                       ==
==       https://github.com/PaddlePaddle/PaddleClas      ==
===========================================================

2022-04-13 17:54:37 INFO: DetPostProcess : 
2022-04-13 17:54:37 INFO: DetPreProcess : 
2022-04-13 17:54:37 INFO:     transform_ops : 
2022-04-13 17:54:37 INFO:         DetResize : 
2022-04-13 17:54:37 INFO:             interp : 2
2022-04-13 17:54:37 INFO:             keep_ratio : False
2022-04-13 17:54:37 INFO:             target_size : [640, 640]
2022-04-13 17:54:37 INFO:         DetNormalizeImage : 
2022-04-13 17:54:37 INFO:             is_scale : True
2022-04-13 17:54:37 INFO:             mean : [0.485, 0.456, 0.406]
2022-04-13 17:54:37 INFO:             std : [0.229, 0.224, 0.225]
2022-04-13 17:54:37 INFO:         DetPermute : 
2022-04-13 17:54:37 INFO: Global : 
2022-04-13 17:54:38 INFO:     batch_size : 1
2022-04-13 17:54:38 INFO:     cpu_num_threads : 10
2022-04-13 17:54:38 INFO:     det_inference_model_dir : ./models/picodet_PPLCNet_x2_5_mainbody_lite_v1.0_infer
2022-04-13 17:54:38 INFO:     enable_benchmark : True
2022-04-13 17:54:38 INFO:     enable_mkldnn : True
2022-04-13 17:54:38 INFO:     enable_profile : False
2022-04-13 17:54:38 INFO:     gpu_mem : 8000
2022-04-13 17:54:38 INFO:     image_shape : [3, 640, 640]
2022-04-13 17:54:38 INFO:     infer_imgs : ./drink_dataset_v1.0/test_images/
2022-04-13 17:54:38 INFO:     ir_optim : True
2022-04-13 17:54:38 INFO:     labe_list : ['foreground']
2022-04-13 17:54:38 INFO:     max_det_results : 5
2022-04-13 17:54:38 INFO:     rec_inference_model_dir : ./models/general_PPLCNet_x2_5_lite_v1.0_infer
2022-04-13 17:54:38 INFO:     rec_nms_thresold : 0.05
2022-04-13 17:54:38 INFO:     threshold : 0.2
2022-04-13 17:54:38 INFO:     use_fp16 : False
2022-04-13 17:54:38 INFO:     use_gpu : True
2022-04-13 17:54:38 INFO:     use_tensorrt : False
2022-04-13 17:54:38 INFO: IndexProcess : 
2022-04-13 17:54:38 INFO:     batch_size : 32
2022-04-13 17:54:38 INFO:     data_file : ./drink_dataset_v1.0/gallery/drink_label.txt
2022-04-13 17:54:38 INFO:     delimiter : 	
2022-04-13 17:54:38 INFO:     dist_type : IP
2022-04-13 17:54:38 INFO:     embedding_size : 512
2022-04-13 17:54:38 INFO:     image_root : ./drink_dataset_v1.0/gallery/
2022-04-13 17:54:38 INFO:     index_dir : ./drink_dataset_v1.0/index
2022-04-13 17:54:38 INFO:     index_method : HNSW32
2022-04-13 17:54:38 INFO:     index_operation : new
2022-04-13 17:54:38 INFO:     return_k : 5
2022-04-13 17:54:38 INFO:     score_thres : 0.5
2022-04-13 17:54:38 INFO: RecPostProcess : None
2022-04-13 17:54:38 INFO: RecPreProcess : 
2022-04-13 17:54:38 INFO:     transform_ops : 
2022-04-13 17:54:38 INFO:         ResizeImage : 
2022-04-13 17:54:38 INFO:             size : 224
2022-04-13 17:54:38 INFO:         NormalizeImage : 
2022-04-13 17:54:38 INFO:             mean : [0.485, 0.456, 0.406]
2022-04-13 17:54:38 INFO:             order : 
2022-04-13 17:54:38 INFO:             scale : 0.00392157
2022-04-13 17:54:38 INFO:             std : [0.229, 0.224, 0.225]
2022-04-13 17:54:38 INFO:         ToCHWImage : None
/home/aistudio/PaddleClas/deploy/python/preprocess.py:65: DeprecationWarning: NEAREST is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.NEAREST or Dither.NONE instead.
  'nearest': Image.NEAREST,
/home/aistudio/PaddleClas/deploy/python/preprocess.py:66: DeprecationWarning: BILINEAR is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.BILINEAR instead.
  'bilinear': Image.BILINEAR,
/home/aistudio/PaddleClas/deploy/python/preprocess.py:67: DeprecationWarning: BICUBIC is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.BICUBIC instead.
  'bicubic': Image.BICUBIC,
/home/aistudio/PaddleClas/deploy/python/preprocess.py:68: DeprecationWarning: BOX is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.BOX instead.
  'box': Image.BOX,
/home/aistudio/PaddleClas/deploy/python/preprocess.py:69: DeprecationWarning: LANCZOS is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.LANCZOS instead.
  'lanczos': Image.LANCZOS,
/home/aistudio/PaddleClas/deploy/python/preprocess.py:70: DeprecationWarning: HAMMING is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.HAMMING instead.
  'hamming': Image.HAMMING
Inference: 38.21897506713867 ms per batch image
[{'bbox': [345, 95, 524, 586], 'rec_docs': '红牛-强化型', 'rec_scores': 0.80164653}]
Inference: 28.63907814025879 ms per batch image
[{'bbox': [233, 0, 372, 436], 'rec_docs': '康师傅矿物质水', 'rec_scores': 0.72513926}]
Inference: 27.467012405395508 ms per batch image
[{'bbox': [138, 40, 573, 1198], 'rec_docs': '乐虎功能饮料', 'rec_scores': 0.78559446}]
Inference: 33.64396095275879 ms per batch image
[{'bbox': [328, 7, 467, 272], 'rec_docs': '脉动', 'rec_scores': 0.5829516}]
Inference: 29.42061424255371 ms per batch image
[{'bbox': [242, 82, 498, 726], 'rec_docs': '味全_每日C', 'rec_scores': 0.7558144}]
Inference: 44.74997520446777 ms per batch image
[{'bbox': [437, 71, 660, 728], 'rec_docs': '元气森林', 'rec_scores': 0.8478891}, {'bbox': [221, 72, 449, 701], 'rec_docs': '元气森林', 'rec_scores': 0.6790612}, {'bbox': [794, 104, 979, 652], 'rec_docs': '元气森林', 'rec_scores': 0.62925816}]
Inference: 28.14006805419922 ms per batch image
[{'bbox': [295, 281, 504, 863], 'rec_docs': '脉动', 'rec_scores': 0.5877435}]
Inference: 44.25811767578125 ms per batch image
[{'bbox': [233, 57, 525, 1038], 'rec_docs': '康师傅冰红茶', 'rec_scores': 0.5823581}]
Inference: 29.671669006347656 ms per batch image
[{'bbox': [189, 17, 495, 793], 'rec_docs': '康师傅冰红茶', 'rec_scores': 0.7761423}, {'bbox': [493, 13, 803, 829], 'rec_docs': '康师傅冰红茶', 'rec_scores': 0.7739582}]
Inference: 27.353286743164062 ms per batch image
[{'bbox': [219, 48, 385, 470], 'rec_docs': '味全_每日C', 'rec_scores': 0.67050844}]
Inference: 28.495073318481445 ms per batch image
[]
Inference: 27.443408966064453 ms per batch image
[{'bbox': [244, 49, 509, 964], 'rec_docs': '农夫山泉-饮用天然水', 'rec_scores': 0.7585665}]
Inference: 27.995586395263672 ms per batch image
[]
五、自定义图像识别
In [13]
!python3.7 python/build_gallery.py -c configs/inference_general.yaml -o IndexProcess.data_file="./drink_dataset_v1.0/gallery/drink_label_all.txt" -o IndexProcess.index_dir="./drink_dataset_v1.0/index_all"
/opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages/paddle/vision/transforms/functional_pil.py:36: DeprecationWarning: NEAREST is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.NEAREST or Dither.NONE instead.
  'nearest': Image.NEAREST,
/opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages/paddle/vision/transforms/functional_pil.py:37: DeprecationWarning: BILINEAR is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.BILINEAR instead.
  'bilinear': Image.BILINEAR,
/opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages/paddle/vision/transforms/functional_pil.py:38: DeprecationWarning: BICUBIC is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.BICUBIC instead.
  'bicubic': Image.BICUBIC,
/opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages/paddle/vision/transforms/functional_pil.py:39: DeprecationWarning: BOX is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.BOX instead.
  'box': Image.BOX,
/opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages/paddle/vision/transforms/functional_pil.py:40: DeprecationWarning: LANCZOS is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.LANCZOS instead.
  'lanczos': Image.LANCZOS,
/opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages/paddle/vision/transforms/functional_pil.py:41: DeprecationWarning: HAMMING is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.HAMMING instead.
  'hamming': Image.HAMMING
2022-04-13 17:54:55 INFO: 
===========================================================
==        PaddleClas is powered by PaddlePaddle !        ==
===========================================================
==                                                       ==
==   For more info please go to the following website.   ==
==                                                       ==
==       https://github.com/PaddlePaddle/PaddleClas      ==
===========================================================

2022-04-13 17:54:55 INFO: DetPostProcess : 
2022-04-13 17:54:55 INFO: DetPreProcess : 
2022-04-13 17:54:55 INFO:     transform_ops : 
2022-04-13 17:54:55 INFO:         DetResize : 
2022-04-13 17:54:55 INFO:             interp : 2
2022-04-13 17:54:55 INFO:             keep_ratio : False
2022-04-13 17:54:55 INFO:             target_size : [640, 640]
2022-04-13 17:54:55 INFO:         DetNormalizeImage : 
2022-04-13 17:54:55 INFO:             is_scale : True
2022-04-13 17:54:55 INFO:             mean : [0.485, 0.456, 0.406]
2022-04-13 17:54:55 INFO:             std : [0.229, 0.224, 0.225]
2022-04-13 17:54:55 INFO:         DetPermute : 
2022-04-13 17:54:55 INFO: Global : 
2022-04-13 17:54:55 INFO:     batch_size : 1
2022-04-13 17:54:55 INFO:     cpu_num_threads : 10
2022-04-13 17:54:55 INFO:     det_inference_model_dir : ./models/picodet_PPLCNet_x2_5_mainbody_lite_v1.0_infer
2022-04-13 17:54:55 INFO:     enable_benchmark : True
2022-04-13 17:54:55 INFO:     enable_mkldnn : True
2022-04-13 17:54:55 INFO:     enable_profile : False
2022-04-13 17:54:55 INFO:     gpu_mem : 8000
2022-04-13 17:54:55 INFO:     image_shape : [3, 640, 640]
2022-04-13 17:54:55 INFO:     infer_imgs : ./drink_dataset_v1.0/test_images/nongfu_spring.jpeg
2022-04-13 17:54:55 INFO:     ir_optim : True
2022-04-13 17:54:55 INFO:     labe_list : ['foreground']
2022-04-13 17:54:55 INFO:     max_det_results : 5
2022-04-13 17:54:55 INFO:     rec_inference_model_dir : ./models/general_PPLCNet_x2_5_lite_v1.0_infer
2022-04-13 17:54:55 INFO:     rec_nms_thresold : 0.05
2022-04-13 17:54:55 INFO:     threshold : 0.2
2022-04-13 17:54:55 INFO:     use_fp16 : False
2022-04-13 17:54:55 INFO:     use_gpu : True
2022-04-13 17:54:55 INFO:     use_tensorrt : False
2022-04-13 17:54:55 INFO: IndexProcess : 
2022-04-13 17:54:55 INFO:     batch_size : 32
2022-04-13 17:54:55 INFO:     data_file : ./drink_dataset_v1.0/gallery/drink_label_all.txt
2022-04-13 17:54:55 INFO:     delimiter : 	
2022-04-13 17:54:55 INFO:     dist_type : IP
2022-04-13 17:54:55 INFO:     embedding_size : 512
2022-04-13 17:54:55 INFO:     image_root : ./drink_dataset_v1.0/gallery/
2022-04-13 17:54:55 INFO:     index_dir : ./drink_dataset_v1.0/index_all
2022-04-13 17:54:55 INFO:     index_method : HNSW32
2022-04-13 17:54:55 INFO:     index_operation : new
2022-04-13 17:54:55 INFO:     return_k : 5
2022-04-13 17:54:55 INFO:     score_thres : 0.5
2022-04-13 17:54:55 INFO: RecPostProcess : None
2022-04-13 17:54:55 INFO: RecPreProcess : 
2022-04-13 17:54:55 INFO:     transform_ops : 
2022-04-13 17:54:55 INFO:         ResizeImage : 
2022-04-13 17:54:55 INFO:             size : 224
2022-04-13 17:54:55 INFO:         NormalizeImage : 
2022-04-13 17:54:55 INFO:             mean : [0.485, 0.456, 0.406]
2022-04-13 17:54:55 INFO:             order : 
2022-04-13 17:54:55 INFO:             scale : 0.00392157
2022-04-13 17:54:55 INFO:             std : [0.229, 0.224, 0.225]
2022-04-13 17:54:55 INFO:         ToCHWImage : None
/home/aistudio/PaddleClas/deploy/python/preprocess.py:65: DeprecationWarning: NEAREST is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.NEAREST or Dither.NONE instead.
  'nearest': Image.NEAREST,
/home/aistudio/PaddleClas/deploy/python/preprocess.py:66: DeprecationWarning: BILINEAR is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.BILINEAR instead.
  'bilinear': Image.BILINEAR,
/home/aistudio/PaddleClas/deploy/python/preprocess.py:67: DeprecationWarning: BICUBIC is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.BICUBIC instead.
  'bicubic': Image.BICUBIC,
/home/aistudio/PaddleClas/deploy/python/preprocess.py:68: DeprecationWarning: BOX is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.BOX instead.
  'box': Image.BOX,
/home/aistudio/PaddleClas/deploy/python/preprocess.py:69: DeprecationWarning: LANCZOS is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.LANCZOS instead.
  'lanczos': Image.LANCZOS,
/home/aistudio/PaddleClas/deploy/python/preprocess.py:70: DeprecationWarning: HAMMING is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.HAMMING instead.
  'hamming': Image.HAMMING
100%|██████████████████████████████████████| 1068/1068 [00:07<00:00, 146.27it/s]
2022-04-13 17:55:05 WARNING: The HNSW32 method dose not support 'remove' operation
In [14]
# 使用下面的命令使用 GPU 进行预测，如果希望使用 CPU 预测，可以在命令后面添加 -o Global.use_gpu=False
!python3.7 python/predict_system.py -c configs/inference_general.yaml -o Global.infer_imgs="././drink_dataset_v1.0/test_images/mosilian.jpeg" -o IndexProcess.index_dir="./drink_dataset_v1.0/index_all"
/opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages/paddle/vision/transforms/functional_pil.py:36: DeprecationWarning: NEAREST is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.NEAREST or Dither.NONE instead.
  'nearest': Image.NEAREST,
/opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages/paddle/vision/transforms/functional_pil.py:37: DeprecationWarning: BILINEAR is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.BILINEAR instead.
  'bilinear': Image.BILINEAR,
/opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages/paddle/vision/transforms/functional_pil.py:38: DeprecationWarning: BICUBIC is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.BICUBIC instead.
  'bicubic': Image.BICUBIC,
/opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages/paddle/vision/transforms/functional_pil.py:39: DeprecationWarning: BOX is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.BOX instead.
  'box': Image.BOX,
/opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages/paddle/vision/transforms/functional_pil.py:40: DeprecationWarning: LANCZOS is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.LANCZOS instead.
  'lanczos': Image.LANCZOS,
/opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages/paddle/vision/transforms/functional_pil.py:41: DeprecationWarning: HAMMING is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.HAMMING instead.
  'hamming': Image.HAMMING
2022-04-13 17:55:08 INFO: 
===========================================================
==        PaddleClas is powered by PaddlePaddle !        ==
===========================================================
==                                                       ==
==   For more info please go to the following website.   ==
==                                                       ==
==       https://github.com/PaddlePaddle/PaddleClas      ==
===========================================================

2022-04-13 17:55:08 INFO: DetPostProcess : 
2022-04-13 17:55:08 INFO: DetPreProcess : 
2022-04-13 17:55:08 INFO:     transform_ops : 
2022-04-13 17:55:08 INFO:         DetResize : 
2022-04-13 17:55:08 INFO:             interp : 2
2022-04-13 17:55:08 INFO:             keep_ratio : False
2022-04-13 17:55:08 INFO:             target_size : [640, 640]
2022-04-13 17:55:08 INFO:         DetNormalizeImage : 
2022-04-13 17:55:08 INFO:             is_scale : True
2022-04-13 17:55:08 INFO:             mean : [0.485, 0.456, 0.406]
2022-04-13 17:55:08 INFO:             std : [0.229, 0.224, 0.225]
2022-04-13 17:55:08 INFO:         DetPermute : 
2022-04-13 17:55:08 INFO: Global : 
2022-04-13 17:55:08 INFO:     batch_size : 1
2022-04-13 17:55:08 INFO:     cpu_num_threads : 10
2022-04-13 17:55:08 INFO:     det_inference_model_dir : ./models/picodet_PPLCNet_x2_5_mainbody_lite_v1.0_infer
2022-04-13 17:55:08 INFO:     enable_benchmark : True
2022-04-13 17:55:08 INFO:     enable_mkldnn : True
2022-04-13 17:55:08 INFO:     enable_profile : False
2022-04-13 17:55:08 INFO:     gpu_mem : 8000
2022-04-13 17:55:08 INFO:     image_shape : [3, 640, 640]
2022-04-13 17:55:08 INFO:     infer_imgs : ././drink_dataset_v1.0/test_images/mosilian.jpeg
2022-04-13 17:55:08 INFO:     ir_optim : True
2022-04-13 17:55:08 INFO:     labe_list : ['foreground']
2022-04-13 17:55:08 INFO:     max_det_results : 5
2022-04-13 17:55:08 INFO:     rec_inference_model_dir : ./models/general_PPLCNet_x2_5_lite_v1.0_infer
2022-04-13 17:55:08 INFO:     rec_nms_thresold : 0.05
2022-04-13 17:55:08 INFO:     threshold : 0.2
2022-04-13 17:55:08 INFO:     use_fp16 : False
2022-04-13 17:55:08 INFO:     use_gpu : True
2022-04-13 17:55:08 INFO:     use_tensorrt : False
2022-04-13 17:55:08 INFO: IndexProcess : 
2022-04-13 17:55:08 INFO:     batch_size : 32
2022-04-13 17:55:08 INFO:     data_file : ./drink_dataset_v1.0/gallery/drink_label.txt
2022-04-13 17:55:08 INFO:     delimiter : 	
2022-04-13 17:55:08 INFO:     dist_type : IP
2022-04-13 17:55:08 INFO:     embedding_size : 512
2022-04-13 17:55:08 INFO:     image_root : ./drink_dataset_v1.0/gallery/
2022-04-13 17:55:08 INFO:     index_dir : ./drink_dataset_v1.0/index_all
2022-04-13 17:55:08 INFO:     index_method : HNSW32
2022-04-13 17:55:08 INFO:     index_operation : new
2022-04-13 17:55:08 INFO:     return_k : 5
2022-04-13 17:55:08 INFO:     score_thres : 0.5
2022-04-13 17:55:08 INFO: RecPostProcess : None
2022-04-13 17:55:08 INFO: RecPreProcess : 
2022-04-13 17:55:08 INFO:     transform_ops : 
2022-04-13 17:55:08 INFO:         ResizeImage : 
2022-04-13 17:55:08 INFO:             size : 224
2022-04-13 17:55:08 INFO:         NormalizeImage : 
2022-04-13 17:55:08 INFO:             mean : [0.485, 0.456, 0.406]
2022-04-13 17:55:08 INFO:             order : 
2022-04-13 17:55:08 INFO:             scale : 0.00392157
2022-04-13 17:55:08 INFO:             std : [0.229, 0.224, 0.225]
2022-04-13 17:55:08 INFO:         ToCHWImage : None
/home/aistudio/PaddleClas/deploy/python/preprocess.py:65: DeprecationWarning: NEAREST is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.NEAREST or Dither.NONE instead.
  'nearest': Image.NEAREST,
/home/aistudio/PaddleClas/deploy/python/preprocess.py:66: DeprecationWarning: BILINEAR is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.BILINEAR instead.
  'bilinear': Image.BILINEAR,
/home/aistudio/PaddleClas/deploy/python/preprocess.py:67: DeprecationWarning: BICUBIC is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.BICUBIC instead.
  'bicubic': Image.BICUBIC,
/home/aistudio/PaddleClas/deploy/python/preprocess.py:68: DeprecationWarning: BOX is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.BOX instead.
  'box': Image.BOX,
/home/aistudio/PaddleClas/deploy/python/preprocess.py:69: DeprecationWarning: LANCZOS is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.LANCZOS instead.
  'lanczos': Image.LANCZOS,
/home/aistudio/PaddleClas/deploy/python/preprocess.py:70: DeprecationWarning: HAMMING is deprecated and will be removed in Pillow 10 (2023-07-01). Use Resampling.HAMMING instead.
  'hamming': Image.HAMMING
Inference: 41.14580154418945 ms per batch image
[{'bbox': [290, 297, 564, 919], 'rec_docs': '光明_莫斯利安', 'rec_scores': 0.738433}]
In [15]
#可视化识别结果
import matplotlib.pyplot as plt
import matplotlib.image as mpimg 
%matplotlib inline
# 预测结果展示
img = mpimg.imread("output/mosilian.jpeg")
plt.figure(figsize=(10,10))
plt.imshow(img) 
plt.axis('off') 
plt.show()

<Figure size 720x720 with 1 Axes>
请点击此处查看本环境基本用法.
Please click here for more detailed instructions.
