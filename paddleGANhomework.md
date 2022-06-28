!git clone https://gitee.com/PaddlePaddle/PaddleGAN
正克隆到 'PaddleGAN'...
remote: Enumerating objects: 4397, done.
remote: Counting objects: 100% (453/453), done.
remote: Compressing objects: 100% (274/274), done.
remote: Total 4397 (delta 206), reused 401 (delta 169), pack-reused 3944
接收对象中: 100% (4397/4397), 162.51 MiB | 3.67 MiB/s, 完成.
处理 delta 中: 100% (2823/2823), 完成.
检查连接... 完成。
In [2]
# 查看工作区文件, 该目录下的变更将会持久保存. 请及时清理不必要的文件, 避免加载过慢.
# View personal work directory. 
# All changes under this directory will be kept even after reset. 
# Please clean unnecessary files in time to speed up environment loading. 
%cd /home/aistudio/PaddleGAN
!pip install -r requirements.txt
/home/aistudio/PaddleGAN
Looking in indexes: https://pypi.tuna.tsinghua.edu.cn/simple
Requirement already satisfied: tqdm in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from -r requirements.txt (line 1)) (4.27.0)
Requirement already satisfied: PyYAML>=5.1 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from -r requirements.txt (line 2)) (5.1.2)
Collecting scikit-image>=0.14.0
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/2d/ba/63ce953b7d593bd493e80be158f2d9f82936582380aee0998315510633aa/scikit_image-0.19.3-cp37-cp37m-manylinux_2_12_x86_64.manylinux2010_x86_64.whl (13.5 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 13.5/13.5 MB 2.6 MB/s eta 0:00:0000:0100:01
Requirement already satisfied: scipy>=1.1.0 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from -r requirements.txt (line 4)) (1.6.3)
Requirement already satisfied: opencv-python in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from -r requirements.txt (line 5)) (4.1.1.26)
Collecting imageio==2.9.0
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/6e/57/5d899fae74c1752f52869b613a8210a2480e1a69688e65df6cb26117d45d/imageio-2.9.0-py3-none-any.whl (3.3 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 3.3/3.3 MB 3.2 MB/s eta 0:00:0000:0100:01
Requirement already satisfied: imageio-ffmpeg in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from -r requirements.txt (line 7)) (0.3.0)
Collecting librosa==0.8.1
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/54/19/a0e2bdc94bc0d1555e4f9bc4099a0751da83fa6e1e6157ec005564f8a98a/librosa-0.8.1-py3-none-any.whl (203 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 203.8/203.8 KB 4.1 MB/s eta 0:00:00a 0:00:01
Collecting numba==0.53.1
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/bb/73/d9c127eddbe3c105a33379d425b88f9dca249a6eddf39ce886494d49c3f9/numba-0.53.1-cp37-cp37m-manylinux2014_x86_64.whl (3.4 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 3.4/3.4 MB 3.5 MB/s eta 0:00:0000:0100:01
Requirement already satisfied: easydict in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from -r requirements.txt (line 10)) (1.9)
Collecting munch
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/cc/ab/85d8da5c9a45e072301beb37ad7f833cd344e04c817d97e0cc75681d248f/munch-2.5.0-py2.py3-none-any.whl (10 kB)
Collecting natsort
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/a9/76/0f624b7326f4458a249580c55e5654756084ec4572ce37a05f799b96bc24/natsort-8.1.0-py3-none-any.whl (37 kB)
Requirement already satisfied: numpy in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from imageio==2.9.0->-r requirements.txt (line 6)) (1.19.5)
Requirement already satisfied: pillow in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from imageio==2.9.0->-r requirements.txt (line 6)) (8.2.0)
Requirement already satisfied: audioread>=2.0.0 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from librosa==0.8.1->-r requirements.txt (line 8)) (2.1.8)
Collecting pooch>=1.0
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/8d/64/8e1bfeda3ba0f267b2d9a918e8ca51db8652d0e1a3412a5b3dbce85d90b6/pooch-1.6.0-py3-none-any.whl (56 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 56.3/56.3 KB 7.2 MB/s eta 0:00:00
Requirement already satisfied: decorator>=3.0.0 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from librosa==0.8.1->-r requirements.txt (line 8)) (4.4.2)
Requirement already satisfied: joblib>=0.14 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from librosa==0.8.1->-r requirements.txt (line 8)) (0.14.1)
Requirement already satisfied: resampy>=0.2.2 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from librosa==0.8.1->-r requirements.txt (line 8)) (0.2.2)
Requirement already satisfied: soundfile>=0.10.2 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from librosa==0.8.1->-r requirements.txt (line 8)) (0.10.3.post1)
Requirement already satisfied: packaging>=20.0 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from librosa==0.8.1->-r requirements.txt (line 8)) (21.3)
Requirement already satisfied: scikit-learn!=0.19.0,>=0.14.0 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from librosa==0.8.1->-r requirements.txt (line 8)) (0.24.2)
Collecting llvmlite<0.37,>=0.36.0rc1
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/54/25/2b4015e2b0c3be2efa6870cf2cf2bd969dd0e5f937476fc13c102209df32/llvmlite-0.36.0-cp37-cp37m-manylinux2010_x86_64.whl (25.3 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 25.3/25.3 MB 2.5 MB/s eta 0:00:0000:0100:01
Requirement already satisfied: setuptools in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from numba==0.53.1->-r requirements.txt (line 9)) (56.2.0)
Collecting tifffile>=2019.7.26
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/d8/38/85ae5ed77598ca90558c17a2f79ddaba33173b31cf8d8f545d34d9134f0d/tifffile-2021.11.2-py3-none-any.whl (178 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 178.9/178.9 KB 2.4 MB/s eta 0:00:00a 0:00:01
Requirement already satisfied: networkx>=2.2 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from scikit-image>=0.14.0->-r requirements.txt (line 3)) (2.4)
Collecting PyWavelets>=1.1.1
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/ae/56/4441877073d8a5266dbf7b04c7f3dc66f1149c8efb9323e0ef987a9bb1ce/PyWavelets-1.3.0-cp37-cp37m-manylinux_2_5_x86_64.manylinux1_x86_64.manylinux_2_12_x86_64.manylinux2010_x86_64.whl (6.4 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 6.4/6.4 MB 2.6 MB/s eta 0:00:0000:0100:01
Requirement already satisfied: six in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from munch->-r requirements.txt (line 11)) (1.16.0)
Requirement already satisfied: pyparsing!=3.0.5,>=2.0.2 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from packaging>=20.0->librosa==0.8.1->-r requirements.txt (line 8)) (3.0.8)
Requirement already satisfied: requests>=2.19.0 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from pooch>=1.0->librosa==0.8.1->-r requirements.txt (line 8)) (2.24.0)
Collecting appdirs>=1.3.0
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/3b/00/2344469e2084fb287c2e0b57b72910309874c3245463acd6cf5e3db69324/appdirs-1.4.4-py2.py3-none-any.whl (9.6 kB)
Requirement already satisfied: threadpoolctl>=2.0.0 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from scikit-learn!=0.19.0,>=0.14.0->librosa==0.8.1->-r requirements.txt (line 8)) (2.1.0)
Requirement already satisfied: cffi>=1.0 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from soundfile>=0.10.2->librosa==0.8.1->-r requirements.txt (line 8)) (1.15.0)
Requirement already satisfied: pycparser in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from cffi>=1.0->soundfile>=0.10.2->librosa==0.8.1->-r requirements.txt (line 8)) (2.21)
Requirement already satisfied: idna<3,>=2.5 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from requests>=2.19.0->pooch>=1.0->librosa==0.8.1->-r requirements.txt (line 8)) (2.8)
Requirement already satisfied: chardet<4,>=3.0.2 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from requests>=2.19.0->pooch>=1.0->librosa==0.8.1->-r requirements.txt (line 8)) (3.0.4)
Requirement already satisfied: certifi>=2017.4.17 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from requests>=2.19.0->pooch>=1.0->librosa==0.8.1->-r requirements.txt (line 8)) (2019.9.11)
Requirement already satisfied: urllib3!=1.25.0,!=1.25.1,<1.26,>=1.21.1 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from requests>=2.19.0->pooch>=1.0->librosa==0.8.1->-r requirements.txt (line 8)) (1.25.6)
Installing collected packages: appdirs, tifffile, PyWavelets, natsort, munch, llvmlite, imageio, scikit-image, pooch, numba, librosa
  Attempting uninstall: llvmlite
    Found existing installation: llvmlite 0.31.0
    Uninstalling llvmlite-0.31.0:
      Successfully uninstalled llvmlite-0.31.0
  Attempting uninstall: imageio
    Found existing installation: imageio 2.6.1
    Uninstalling imageio-2.6.1:
      Successfully uninstalled imageio-2.6.1
  Attempting uninstall: numba
    Found existing installation: numba 0.48.0
    Uninstalling numba-0.48.0:
      Successfully uninstalled numba-0.48.0
  Attempting uninstall: librosa
    Found existing installation: librosa 0.7.2
    Uninstalling librosa-0.7.2:
      Successfully uninstalled librosa-0.7.2
Successfully installed PyWavelets-1.3.0 appdirs-1.4.4 imageio-2.9.0 librosa-0.8.1 llvmlite-0.36.0 munch-2.5.0 natsort-8.1.0 numba-0.53.1 pooch-1.6.0 scikit-image-0.19.3 tifffile-2021.11.2
WARNING: You are using pip version 22.0.4; however, version 22.1.2 is available.
You should consider upgrading via the '/opt/conda/envs/python35-paddle120-env/bin/python -m pip install --upgrade pip' command.
In [9]
!python applications/tools/lapstyle.py  \
        --content_img '/home/aistudio/老六.jpeg' \
        --output_path '/home/aistudio/老七' \
        --style 'stars' \
        --style_image_path '/home/aistudio/水星.png'
        # --weight_path None \
        # --style_image_path '/home/aistudio/星球图片/月球.png'
W0628 16:15:44.618012 12116 gpu_context.cc:278] Please NOTE: device: 0, GPU Compute Capability: 7.0, Driver API Version: 11.2, Runtime API Version: 10.1
W0628 16:15:44.622674 12116 gpu_context.cc:306] device: 0, cuDNN Version: 7.6.
[06/28 16:15:48] ppgan INFO: Found /home/aistudio/.cache/ppgan/vgg_normalised.pdparams
[06/28 16:15:48] ppgan INFO: Downloading lapstyle_stars.pdparams from https://paddlegan.bj.bcebos.com/models/lapstyle_stars.pdparams to /home/aistudio/.cache/ppgan/lapstyle_stars.pdparams
100%|████████████████████████████████| 123264/123264 [00:10<00:00, 11330.69it/s]
Model LapStyle output images path: /home/aistudio/老七/LapStyle
###训练自定义风格

In [ ]
#解压数据集
!unzip -oq /home/aistudio/data/data97273/annotations_trainval2017.zip
!unzip -oq /home/aistudio/data/data97273/train2017.zip
!unzip /home/aistudio/data/data7122/test2017.zip
In [ ]
#训练第一个模型
!python -u tools/main.py --config-file configs/lapstyle_draft.yaml
In [ ]
#训练第二个模型
!python -u tools/main.py --config-file configs/lapstyle_rev_first.yaml --resume output_dir/lapstyle_rev_first-2021-09-09-18-02/iter_20000_checkpoint.pdparams
In [ ]
#训练第三个模型
!python -u tools/main.py --config-file configs/lapstyle_rev_second.yaml --r
