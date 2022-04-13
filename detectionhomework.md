一、环境准备
In [1]
#克隆PaddleDetection
!git clone https://gitee.com/paddlepaddle/PaddleDetection.git
正克隆到 'PaddleDetection'...
remote: Enumerating objects: 23165, done.
remote: Counting objects: 100% (3635/3635), done.
remote: Compressing objects: 100% (1765/1765), done.
remote: Total 23165 (delta 2580), reused 2667 (delta 1863), pack-reused 19530
接收对象中: 100% (23165/23165), 261.63 MiB | 38.55 MiB/s, 完成.
处理 delta 中: 100% (17129/17129), 完成.
检查连接... 完成。
In [2]
# 安装其他依赖
%cd PaddleDetection
!pip install -r requirements.txt
/home/aistudio/PaddleDetection
Looking in indexes: https://pypi.tuna.tsinghua.edu.cn/simple
Requirement already satisfied: tqdm in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from -r requirements.txt (line 1)) (4.27.0)
Collecting typeguard
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/9a/bb/d43e5c75054e53efce310e79d63df0ac3f25e34c926be5dffb7d283fb2a8/typeguard-2.13.3-py3-none-any.whl (17 kB)
Requirement already satisfied: visualdl>=2.1.0 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from -r requirements.txt (line 3)) (2.2.3)
Requirement already satisfied: opencv-python in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from -r requirements.txt (line 4)) (4.1.1.26)
Requirement already satisfied: PyYAML in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from -r requirements.txt (line 5)) (5.1.2)
Collecting shapely
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/9d/4d/4b0d86ed737acb29c5e627a91449470a9fb914f32640db3f1cb7ba5bc19e/Shapely-1.8.1.post1-cp37-cp37m-manylinux_2_12_x86_64.manylinux2010_x86_64.whl (2.0 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 2.0/2.0 MB 2.9 MB/s eta 0:00:0000:0100:01
Requirement already satisfied: scipy in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from -r requirements.txt (line 7)) (1.6.3)
Collecting terminaltables
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/c4/fb/ea621e0a19733e01fe4005d46087d383693c0f4a8f824b47d8d4122c87e0/terminaltables-3.1.10-py2.py3-none-any.whl (15 kB)
Requirement already satisfied: Cython in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from -r requirements.txt (line 9)) (0.29)
Collecting pycocotools
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/75/5c/ac61ea715d7a89ecc31c090753bde28810238225ca8b71778dfe3e6a68bc/pycocotools-2.0.4.tar.gz (106 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 106.6/106.6 KB 1.9 MB/s eta 0:00:00a 0:00:01
  Installing build dependencies ... done
  Getting requirements to build wheel ... done
  Preparing metadata (pyproject.toml) ... done
Requirement already satisfied: setuptools>=42.0.0 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from -r requirements.txt (line 12)) (56.2.0)
Collecting lap
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/bf/64/d9fb6a75b15e783952b2fec6970f033462e67db32dc43dfbb404c14e91c2/lap-0.4.0.tar.gz (1.5 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 1.5/1.5 MB 2.1 MB/s eta 0:00:00a 0:00:01
  Preparing metadata (setup.py) ... done
Requirement already satisfied: sklearn in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from -r requirements.txt (line 14)) (0.0)
Collecting motmetrics
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/45/41/b019fe934eb811b9aba9b335f852305b804b9c66f098d7e35c2bdb09d1c8/motmetrics-1.2.5-py3-none-any.whl (161 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 161.1/161.1 KB 588.5 kB/s eta 0:00:00a 0:00:01
Requirement already satisfied: openpyxl in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from -r requirements.txt (line 16)) (3.0.5)
Requirement already satisfied: pandas in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from visualdl>=2.1.0->-r requirements.txt (line 3)) (1.1.5)
Requirement already satisfied: pre-commit in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from visualdl>=2.1.0->-r requirements.txt (line 3)) (1.21.0)
Requirement already satisfied: requests in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from visualdl>=2.1.0->-r requirements.txt (line 3)) (2.24.0)
Requirement already satisfied: numpy in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from visualdl>=2.1.0->-r requirements.txt (line 3)) (1.19.5)
Requirement already satisfied: matplotlib in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from visualdl>=2.1.0->-r requirements.txt (line 3)) (2.2.3)
Requirement already satisfied: bce-python-sdk in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from visualdl>=2.1.0->-r requirements.txt (line 3)) (0.8.53)
Requirement already satisfied: shellcheck-py in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from visualdl>=2.1.0->-r requirements.txt (line 3)) (0.7.1.1)
Requirement already satisfied: flask>=1.1.1 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from visualdl>=2.1.0->-r requirements.txt (line 3)) (1.1.1)
Requirement already satisfied: six>=1.14.0 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from visualdl>=2.1.0->-r requirements.txt (line 3)) (1.16.0)
Requirement already satisfied: flake8>=3.7.9 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from visualdl>=2.1.0->-r requirements.txt (line 3)) (4.0.1)
Requirement already satisfied: Pillow>=7.0.0 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from visualdl>=2.1.0->-r requirements.txt (line 3)) (8.2.0)
Requirement already satisfied: Flask-Babel>=1.0.0 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from visualdl>=2.1.0->-r requirements.txt (line 3)) (1.0.0)
Requirement already satisfied: protobuf>=3.11.0 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from visualdl>=2.1.0->-r requirements.txt (line 3)) (3.14.0)
Requirement already satisfied: scikit-learn in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from sklearn->-r requirements.txt (line 14)) (0.24.2)
Collecting xmltodict>=0.12.0
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/28/fd/30d5c1d3ac29ce229f6bdc40bbc20b28f716e8b363140c26eff19122d8a5/xmltodict-0.12.0-py2.py3-none-any.whl (9.2 kB)
Requirement already satisfied: jdcal in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from openpyxl->-r requirements.txt (line 16)) (1.4.1)
Requirement already satisfied: et-xmlfile in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from openpyxl->-r requirements.txt (line 16)) (1.0.1)
Requirement already satisfied: pycodestyle<2.9.0,>=2.8.0 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from flake8>=3.7.9->visualdl>=2.1.0->-r requirements.txt (line 3)) (2.8.0)
Requirement already satisfied: mccabe<0.7.0,>=0.6.0 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from flake8>=3.7.9->visualdl>=2.1.0->-r requirements.txt (line 3)) (0.6.1)
Requirement already satisfied: pyflakes<2.5.0,>=2.4.0 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from flake8>=3.7.9->visualdl>=2.1.0->-r requirements.txt (line 3)) (2.4.0)
Requirement already satisfied: importlib-metadata<4.3 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from flake8>=3.7.9->visualdl>=2.1.0->-r requirements.txt (line 3)) (4.2.0)
Requirement already satisfied: Jinja2>=2.10.1 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from flask>=1.1.1->visualdl>=2.1.0->-r requirements.txt (line 3)) (3.0.0)
Requirement already satisfied: itsdangerous>=0.24 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from flask>=1.1.1->visualdl>=2.1.0->-r requirements.txt (line 3)) (1.1.0)
Requirement already satisfied: click>=5.1 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from flask>=1.1.1->visualdl>=2.1.0->-r requirements.txt (line 3)) (7.0)
Requirement already satisfied: Werkzeug>=0.15 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from flask>=1.1.1->visualdl>=2.1.0->-r requirements.txt (line 3)) (0.16.0)
Requirement already satisfied: Babel>=2.3 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from Flask-Babel>=1.0.0->visualdl>=2.1.0->-r requirements.txt (line 3)) (2.9.1)
Requirement already satisfied: pytz in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from Flask-Babel>=1.0.0->visualdl>=2.1.0->-r requirements.txt (line 3)) (2022.1)
Requirement already satisfied: kiwisolver>=1.0.1 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from matplotlib->visualdl>=2.1.0->-r requirements.txt (line 3)) (1.1.0)
Requirement already satisfied: python-dateutil>=2.1 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from matplotlib->visualdl>=2.1.0->-r requirements.txt (line 3)) (2.8.2)
Requirement already satisfied: cycler>=0.10 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from matplotlib->visualdl>=2.1.0->-r requirements.txt (line 3)) (0.10.0)
Requirement already satisfied: pyparsing!=2.0.4,!=2.1.2,!=2.1.6,>=2.0.1 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from matplotlib->visualdl>=2.1.0->-r requirements.txt (line 3)) (3.0.7)
Requirement already satisfied: future>=0.6.0 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from bce-python-sdk->visualdl>=2.1.0->-r requirements.txt (line 3)) (0.18.0)
Requirement already satisfied: pycryptodome>=3.8.0 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from bce-python-sdk->visualdl>=2.1.0->-r requirements.txt (line 3)) (3.9.9)
Requirement already satisfied: virtualenv>=15.2 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from pre-commit->visualdl>=2.1.0->-r requirements.txt (line 3)) (16.7.9)
Requirement already satisfied: identify>=1.0.0 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from pre-commit->visualdl>=2.1.0->-r requirements.txt (line 3)) (1.4.10)
Requirement already satisfied: cfgv>=2.0.0 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from pre-commit->visualdl>=2.1.0->-r requirements.txt (line 3)) (2.0.1)
Requirement already satisfied: nodeenv>=0.11.1 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from pre-commit->visualdl>=2.1.0->-r requirements.txt (line 3)) (1.3.4)
Requirement already satisfied: toml in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from pre-commit->visualdl>=2.1.0->-r requirements.txt (line 3)) (0.10.0)
Requirement already satisfied: aspy.yaml in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from pre-commit->visualdl>=2.1.0->-r requirements.txt (line 3)) (1.3.0)
Requirement already satisfied: certifi>=2017.4.17 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from requests->visualdl>=2.1.0->-r requirements.txt (line 3)) (2021.10.8)
Requirement already satisfied: chardet<4,>=3.0.2 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from requests->visualdl>=2.1.0->-r requirements.txt (line 3)) (3.0.4)
Requirement already satisfied: urllib3!=1.25.0,!=1.25.1,<1.26,>=1.21.1 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from requests->visualdl>=2.1.0->-r requirements.txt (line 3)) (1.25.11)
Requirement already satisfied: idna<3,>=2.5 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from requests->visualdl>=2.1.0->-r requirements.txt (line 3)) (2.10)
Requirement already satisfied: joblib>=0.11 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from scikit-learn->sklearn->-r requirements.txt (line 14)) (0.14.1)
Requirement already satisfied: threadpoolctl>=2.0.0 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from scikit-learn->sklearn->-r requirements.txt (line 14)) (2.1.0)
Requirement already satisfied: typing-extensions>=3.6.4 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from importlib-metadata<4.3->flake8>=3.7.9->visualdl>=2.1.0->-r requirements.txt (line 3)) (4.1.1)
Requirement already satisfied: zipp>=0.5 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from importlib-metadata<4.3->flake8>=3.7.9->visualdl>=2.1.0->-r requirements.txt (line 3)) (3.7.0)
Requirement already satisfied: MarkupSafe>=2.0.0rc2 in /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages (from Jinja2>=2.10.1->flask>=1.1.1->visualdl>=2.1.0->-r requirements.txt (line 3)) (2.0.1)
Building wheels for collected packages: pycocotools, lap
  Building wheel for pycocotools (pyproject.toml) ... done
  Created wheel for pycocotools: filename=pycocotools-2.0.4-cp37-cp37m-linux_x86_64.whl size=273788 sha256=638927d7eecd87b6a6e1b8e8c41c6a33e44507947c1038785d94d58a1ba6e2bb
  Stored in directory: /home/aistudio/.cache/pip/wheels/c0/01/5f/670dfd20204fc9cc6bf843db4e014acb998f411922e3abc49f
  Building wheel for lap (setup.py) ... done
  Created wheel for lap: filename=lap-0.4.0-cp37-cp37m-linux_x86_64.whl size=1593869 sha256=8559a310b82d99cbdf877078263946ce4dd9676508fd89dc8b768d101b46d8a1
  Stored in directory: /home/aistudio/.cache/pip/wheels/5c/d0/d2/e331d17a999666b1e2eb99743cfa1742629f9d26c55c657001
Successfully built pycocotools lap
Installing collected packages: lap, xmltodict, typeguard, terminaltables, shapely, pycocotools, motmetrics
Successfully installed lap-0.4.0 motmetrics-1.2.5 pycocotools-2.0.4 shapely-1.8.1.post1 terminaltables-3.1.10 typeguard-2.13.3 xmltodict-0.12.0
In [3]
# 切换到develop分支
!git checkout develop
分支 develop 设置为跟踪来自 origin 的远程分支 develop。
切换到一个新分支 'develop'
In [4]
# 编译安装paddledet
!python setup.py install
running install
running bdist_egg
running egg_info
creating paddledet.egg-info
writing paddledet.egg-info/PKG-INFO
writing dependency_links to paddledet.egg-info/dependency_links.txt
writing requirements to paddledet.egg-info/requires.txt
writing top-level names to paddledet.egg-info/top_level.txt
writing manifest file 'paddledet.egg-info/SOURCES.txt'
adding license file 'LICENSE' (matched pattern 'LICEN[CS]E*')
reading manifest file 'paddledet.egg-info/SOURCES.txt'
writing manifest file 'paddledet.egg-info/SOURCES.txt'
installing library code to build/bdist.linux-x86_64/egg
running install_lib
running build_py
creating build
creating build/lib
creating build/lib/ppdet
copying ppdet/optimizer.py -> build/lib/ppdet
copying ppdet/__init__.py -> build/lib/ppdet
copying ppdet/version.py -> build/lib/ppdet
creating build/lib/ppdet/core
copying ppdet/core/workspace.py -> build/lib/ppdet/core
copying ppdet/core/__init__.py -> build/lib/ppdet/core
creating build/lib/ppdet/engine
copying ppdet/engine/env.py -> build/lib/ppdet/engine
copying ppdet/engine/trainer.py -> build/lib/ppdet/engine
copying ppdet/engine/tracker.py -> build/lib/ppdet/engine
copying ppdet/engine/callbacks.py -> build/lib/ppdet/engine
copying ppdet/engine/__init__.py -> build/lib/ppdet/engine
copying ppdet/engine/export_utils.py -> build/lib/ppdet/engine
creating build/lib/ppdet/utils
copying ppdet/utils/cli.py -> build/lib/ppdet/utils
copying ppdet/utils/logger.py -> build/lib/ppdet/utils
copying ppdet/utils/colormap.py -> build/lib/ppdet/utils
copying ppdet/utils/profiler.py -> build/lib/ppdet/utils
copying ppdet/utils/download.py -> build/lib/ppdet/utils
copying ppdet/utils/visualizer.py -> build/lib/ppdet/utils
copying ppdet/utils/check.py -> build/lib/ppdet/utils
copying ppdet/utils/voc_utils.py -> build/lib/ppdet/utils
copying ppdet/utils/__init__.py -> build/lib/ppdet/utils
copying ppdet/utils/checkpoint.py -> build/lib/ppdet/utils
copying ppdet/utils/stats.py -> build/lib/ppdet/utils
creating build/lib/ppdet/data
copying ppdet/data/shm_utils.py -> build/lib/ppdet/data
copying ppdet/data/reader.py -> build/lib/ppdet/data
copying ppdet/data/__init__.py -> build/lib/ppdet/data
creating build/lib/ppdet/slim
copying ppdet/slim/quant.py -> build/lib/ppdet/slim
copying ppdet/slim/distill.py -> build/lib/ppdet/slim
copying ppdet/slim/ofa.py -> build/lib/ppdet/slim
copying ppdet/slim/unstructured_prune.py -> build/lib/ppdet/slim
copying ppdet/slim/__init__.py -> build/lib/ppdet/slim
copying ppdet/slim/prune.py -> build/lib/ppdet/slim
creating build/lib/ppdet/modeling
copying ppdet/modeling/keypoint_utils.py -> build/lib/ppdet/modeling
copying ppdet/modeling/initializer.py -> build/lib/ppdet/modeling
copying ppdet/modeling/ops.py -> build/lib/ppdet/modeling
copying ppdet/modeling/bbox_utils.py -> build/lib/ppdet/modeling
copying ppdet/modeling/__init__.py -> build/lib/ppdet/modeling
copying ppdet/modeling/shape_spec.py -> build/lib/ppdet/modeling
copying ppdet/modeling/layers.py -> build/lib/ppdet/modeling
copying ppdet/modeling/post_process.py -> build/lib/ppdet/modeling
creating build/lib/ppdet/metrics
copying ppdet/metrics/mot_metrics.py -> build/lib/ppdet/metrics
copying ppdet/metrics/keypoint_metrics.py -> build/lib/ppdet/metrics
copying ppdet/metrics/mcmot_metrics.py -> build/lib/ppdet/metrics
copying ppdet/metrics/metrics.py -> build/lib/ppdet/metrics
copying ppdet/metrics/widerface_utils.py -> build/lib/ppdet/metrics
copying ppdet/metrics/munkres.py -> build/lib/ppdet/metrics
copying ppdet/metrics/coco_utils.py -> build/lib/ppdet/metrics
copying ppdet/metrics/__init__.py -> build/lib/ppdet/metrics
copying ppdet/metrics/json_results.py -> build/lib/ppdet/metrics
copying ppdet/metrics/map_utils.py -> build/lib/ppdet/metrics
creating build/lib/ppdet/model_zoo
copying ppdet/model_zoo/model_zoo.py -> build/lib/ppdet/model_zoo
copying ppdet/model_zoo/__init__.py -> build/lib/ppdet/model_zoo
creating build/lib/ppdet/core/config
copying ppdet/core/config/yaml_helpers.py -> build/lib/ppdet/core/config
copying ppdet/core/config/__init__.py -> build/lib/ppdet/core/config
copying ppdet/core/config/schema.py -> build/lib/ppdet/core/config
creating build/lib/ppdet/data/source
copying ppdet/data/source/sniper_coco.py -> build/lib/ppdet/data/source
copying ppdet/data/source/widerface.py -> build/lib/ppdet/data/source
copying ppdet/data/source/__init__.py -> build/lib/ppdet/data/source
copying ppdet/data/source/keypoint_coco.py -> build/lib/ppdet/data/source
copying ppdet/data/source/coco.py -> build/lib/ppdet/data/source
copying ppdet/data/source/dataset.py -> build/lib/ppdet/data/source
copying ppdet/data/source/category.py -> build/lib/ppdet/data/source
copying ppdet/data/source/voc.py -> build/lib/ppdet/data/source
copying ppdet/data/source/mot.py -> build/lib/ppdet/data/source
creating build/lib/ppdet/data/crop_utils
copying ppdet/data/crop_utils/annotation_cropper.py -> build/lib/ppdet/data/crop_utils
copying ppdet/data/crop_utils/__init__.py -> build/lib/ppdet/data/crop_utils
copying ppdet/data/crop_utils/chip_box_utils.py -> build/lib/ppdet/data/crop_utils
creating build/lib/ppdet/data/transform
copying ppdet/data/transform/autoaugment_utils.py -> build/lib/ppdet/data/transform
copying ppdet/data/transform/op_helper.py -> build/lib/ppdet/data/transform
copying ppdet/data/transform/atss_assigner.py -> build/lib/ppdet/data/transform
copying ppdet/data/transform/mot_operators.py -> build/lib/ppdet/data/transform
copying ppdet/data/transform/operators.py -> build/lib/ppdet/data/transform
copying ppdet/data/transform/__init__.py -> build/lib/ppdet/data/transform
copying ppdet/data/transform/gridmask_utils.py -> build/lib/ppdet/data/transform
copying ppdet/data/transform/batch_operators.py -> build/lib/ppdet/data/transform
copying ppdet/data/transform/keypoint_operators.py -> build/lib/ppdet/data/transform
creating build/lib/ppdet/modeling/heads
copying ppdet/modeling/heads/sparsercnn_head.py -> build/lib/ppdet/modeling/heads
copying ppdet/modeling/heads/ttf_head.py -> build/lib/ppdet/modeling/heads
copying ppdet/modeling/heads/detr_head.py -> build/lib/ppdet/modeling/heads
copying ppdet/modeling/heads/bbox_head.py -> build/lib/ppdet/modeling/heads
copying ppdet/modeling/heads/fcos_head.py -> build/lib/ppdet/modeling/heads
copying ppdet/modeling/heads/keypoint_hrhrnet_head.py -> build/lib/ppdet/modeling/heads
copying ppdet/modeling/heads/retina_head.py -> build/lib/ppdet/modeling/heads
copying ppdet/modeling/heads/centernet_head.py -> build/lib/ppdet/modeling/heads
copying ppdet/modeling/heads/tood_head.py -> build/lib/ppdet/modeling/heads
copying ppdet/modeling/heads/s2anet_head.py -> build/lib/ppdet/modeling/heads
copying ppdet/modeling/heads/ppyoloe_head.py -> build/lib/ppdet/modeling/heads
copying ppdet/modeling/heads/roi_extractor.py -> build/lib/ppdet/modeling/heads
copying ppdet/modeling/heads/ssd_head.py -> build/lib/ppdet/modeling/heads
copying ppdet/modeling/heads/yolo_head.py -> build/lib/ppdet/modeling/heads
copying ppdet/modeling/heads/face_head.py -> build/lib/ppdet/modeling/heads
copying ppdet/modeling/heads/solov2_head.py -> build/lib/ppdet/modeling/heads
copying ppdet/modeling/heads/__init__.py -> build/lib/ppdet/modeling/heads
copying ppdet/modeling/heads/mask_head.py -> build/lib/ppdet/modeling/heads
copying ppdet/modeling/heads/pico_head.py -> build/lib/ppdet/modeling/heads
copying ppdet/modeling/heads/simota_head.py -> build/lib/ppdet/modeling/heads
copying ppdet/modeling/heads/cascade_head.py -> build/lib/ppdet/modeling/heads
copying ppdet/modeling/heads/gfl_head.py -> build/lib/ppdet/modeling/heads
creating build/lib/ppdet/modeling/architectures
copying ppdet/modeling/architectures/solov2.py -> build/lib/ppdet/modeling/architectures
copying ppdet/modeling/architectures/tood.py -> build/lib/ppdet/modeling/architectures
copying ppdet/modeling/architectures/yolo.py -> build/lib/ppdet/modeling/architectures
copying ppdet/modeling/architectures/meta_arch.py -> build/lib/ppdet/modeling/architectures
copying ppdet/modeling/architectures/faster_rcnn.py -> build/lib/ppdet/modeling/architectures
copying ppdet/modeling/architectures/keypoint_hrhrnet.py -> build/lib/ppdet/modeling/architectures
copying ppdet/modeling/architectures/centernet.py -> build/lib/ppdet/modeling/architectures
copying ppdet/modeling/architectures/picodet.py -> build/lib/ppdet/modeling/architectures
copying ppdet/modeling/architectures/keypoint_hrnet.py -> build/lib/ppdet/modeling/architectures
copying ppdet/modeling/architectures/detr.py -> build/lib/ppdet/modeling/architectures
copying ppdet/modeling/architectures/blazeface.py -> build/lib/ppdet/modeling/architectures
copying ppdet/modeling/architectures/jde.py -> build/lib/ppdet/modeling/architectures
copying ppdet/modeling/architectures/gfl.py -> build/lib/ppdet/modeling/architectures
copying ppdet/modeling/architectures/ssd.py -> build/lib/ppdet/modeling/architectures
copying ppdet/modeling/architectures/cascade_rcnn.py -> build/lib/ppdet/modeling/architectures
copying ppdet/modeling/architectures/fairmot.py -> build/lib/ppdet/modeling/architectures
copying ppdet/modeling/architectures/mask_rcnn.py -> build/lib/ppdet/modeling/architectures
copying ppdet/modeling/architectures/__init__.py -> build/lib/ppdet/modeling/architectures
copying ppdet/modeling/architectures/s2anet.py -> build/lib/ppdet/modeling/architectures
copying ppdet/modeling/architectures/bytetrack.py -> build/lib/ppdet/modeling/architectures
copying ppdet/modeling/architectures/sparse_rcnn.py -> build/lib/ppdet/modeling/architectures
copying ppdet/modeling/architectures/fcos.py -> build/lib/ppdet/modeling/architectures
copying ppdet/modeling/architectures/deepsort.py -> build/lib/ppdet/modeling/architectures
copying ppdet/modeling/architectures/retinanet.py -> build/lib/ppdet/modeling/architectures
copying ppdet/modeling/architectures/ttfnet.py -> build/lib/ppdet/modeling/architectures
creating build/lib/ppdet/modeling/backbones
copying ppdet/modeling/backbones/ghostnet.py -> build/lib/ppdet/modeling/backbones
copying ppdet/modeling/backbones/esnet.py -> build/lib/ppdet/modeling/backbones
copying ppdet/modeling/backbones/lcnet.py -> build/lib/ppdet/modeling/backbones
copying ppdet/modeling/backbones/shufflenet_v2.py -> build/lib/ppdet/modeling/backbones
copying ppdet/modeling/backbones/darknet.py -> build/lib/ppdet/modeling/backbones
copying ppdet/modeling/backbones/swin_transformer.py -> build/lib/ppdet/modeling/backbones
copying ppdet/modeling/backbones/mobilenet_v3.py -> build/lib/ppdet/modeling/backbones
copying ppdet/modeling/backbones/dla.py -> build/lib/ppdet/modeling/backbones
copying ppdet/modeling/backbones/hardnet.py -> build/lib/ppdet/modeling/backbones
copying ppdet/modeling/backbones/hrnet.py -> build/lib/ppdet/modeling/backbones
copying ppdet/modeling/backbones/name_adapter.py -> build/lib/ppdet/modeling/backbones
copying ppdet/modeling/backbones/cspresnet.py -> build/lib/ppdet/modeling/backbones
copying ppdet/modeling/backbones/senet.py -> build/lib/ppdet/modeling/backbones
copying ppdet/modeling/backbones/mobilenet_v1.py -> build/lib/ppdet/modeling/backbones
copying ppdet/modeling/backbones/__init__.py -> build/lib/ppdet/modeling/backbones
copying ppdet/modeling/backbones/lite_hrnet.py -> build/lib/ppdet/modeling/backbones
copying ppdet/modeling/backbones/res2net.py -> build/lib/ppdet/modeling/backbones
copying ppdet/modeling/backbones/blazenet.py -> build/lib/ppdet/modeling/backbones
copying ppdet/modeling/backbones/vgg.py -> build/lib/ppdet/modeling/backbones
copying ppdet/modeling/backbones/resnet.py -> build/lib/ppdet/modeling/backbones
creating build/lib/ppdet/modeling/reid
copying ppdet/modeling/reid/resnet_embedding.py -> build/lib/ppdet/modeling/reid
copying ppdet/modeling/reid/jde_embedding_head.py -> build/lib/ppdet/modeling/reid
copying ppdet/modeling/reid/pyramidal_embedding.py -> build/lib/ppdet/modeling/reid
copying ppdet/modeling/reid/fairmot_embedding_head.py -> build/lib/ppdet/modeling/reid
copying ppdet/modeling/reid/__init__.py -> build/lib/ppdet/modeling/reid
copying ppdet/modeling/reid/pplcnet_embedding.py -> build/lib/ppdet/modeling/reid
copying ppdet/modeling/reid/resnet.py -> build/lib/ppdet/modeling/reid
creating build/lib/ppdet/modeling/coders
copying ppdet/modeling/coders/delta_bbox_coder.py -> build/lib/ppdet/modeling/coders
copying ppdet/modeling/coders/__init__.py -> build/lib/ppdet/modeling/coders
creating build/lib/ppdet/modeling/mot
copying ppdet/modeling/mot/utils.py -> build/lib/ppdet/modeling/mot
copying ppdet/modeling/mot/visualization.py -> build/lib/ppdet/modeling/mot
copying ppdet/modeling/mot/__init__.py -> build/lib/ppdet/modeling/mot
creating build/lib/ppdet/modeling/tests
copying ppdet/modeling/tests/test_mstest.py -> build/lib/ppdet/modeling/tests
copying ppdet/modeling/tests/test_yolov3_loss.py -> build/lib/ppdet/modeling/tests
copying ppdet/modeling/tests/test_architectures.py -> build/lib/ppdet/modeling/tests
copying ppdet/modeling/tests/__init__.py -> build/lib/ppdet/modeling/tests
copying ppdet/modeling/tests/test_base.py -> build/lib/ppdet/modeling/tests
copying ppdet/modeling/tests/test_ops.py -> build/lib/ppdet/modeling/tests
creating build/lib/ppdet/modeling/losses
copying ppdet/modeling/losses/gfocal_loss.py -> build/lib/ppdet/modeling/losses
copying ppdet/modeling/losses/fcos_loss.py -> build/lib/ppdet/modeling/losses
copying ppdet/modeling/losses/jde_loss.py -> build/lib/ppdet/modeling/losses
copying ppdet/modeling/losses/fairmot_loss.py -> build/lib/ppdet/modeling/losses
copying ppdet/modeling/losses/ssd_loss.py -> build/lib/ppdet/modeling/losses
copying ppdet/modeling/losses/yolo_loss.py -> build/lib/ppdet/modeling/losses
copying ppdet/modeling/losses/iou_loss.py -> build/lib/ppdet/modeling/losses
copying ppdet/modeling/losses/smooth_l1_loss.py -> build/lib/ppdet/modeling/losses
copying ppdet/modeling/losses/focal_loss.py -> build/lib/ppdet/modeling/losses
copying ppdet/modeling/losses/varifocal_loss.py -> build/lib/ppdet/modeling/losses
copying ppdet/modeling/losses/solov2_loss.py -> build/lib/ppdet/modeling/losses
copying ppdet/modeling/losses/__init__.py -> build/lib/ppdet/modeling/losses
copying ppdet/modeling/losses/keypoint_loss.py -> build/lib/ppdet/modeling/losses
copying ppdet/modeling/losses/ctfocal_loss.py -> build/lib/ppdet/modeling/losses
copying ppdet/modeling/losses/detr_loss.py -> build/lib/ppdet/modeling/losses
copying ppdet/modeling/losses/iou_aware_loss.py -> build/lib/ppdet/modeling/losses
copying ppdet/modeling/losses/sparsercnn_loss.py -> build/lib/ppdet/modeling/losses
creating build/lib/ppdet/modeling/proposal_generator
copying ppdet/modeling/proposal_generator/rpn_head.py -> build/lib/ppdet/modeling/proposal_generator
copying ppdet/modeling/proposal_generator/anchor_generator.py -> build/lib/ppdet/modeling/proposal_generator
copying ppdet/modeling/proposal_generator/__init__.py -> build/lib/ppdet/modeling/proposal_generator
copying ppdet/modeling/proposal_generator/proposal_generator.py -> build/lib/ppdet/modeling/proposal_generator
copying ppdet/modeling/proposal_generator/target_layer.py -> build/lib/ppdet/modeling/proposal_generator
copying ppdet/modeling/proposal_generator/target.py -> build/lib/ppdet/modeling/proposal_generator
creating build/lib/ppdet/modeling/transformers
copying ppdet/modeling/transformers/utils.py -> build/lib/ppdet/modeling/transformers
copying ppdet/modeling/transformers/position_encoding.py -> build/lib/ppdet/modeling/transformers
copying ppdet/modeling/transformers/detr_transformer.py -> build/lib/ppdet/modeling/transformers
copying ppdet/modeling/transformers/deformable_transformer.py -> build/lib/ppdet/modeling/transformers
copying ppdet/modeling/transformers/__init__.py -> build/lib/ppdet/modeling/transformers
copying ppdet/modeling/transformers/matchers.py -> build/lib/ppdet/modeling/transformers
creating build/lib/ppdet/modeling/necks
copying ppdet/modeling/necks/yolo_fpn.py -> build/lib/ppdet/modeling/necks
copying ppdet/modeling/necks/bifpn.py -> build/lib/ppdet/modeling/necks
copying ppdet/modeling/necks/custom_pan.py -> build/lib/ppdet/modeling/necks
copying ppdet/modeling/necks/lc_pan.py -> build/lib/ppdet/modeling/necks
copying ppdet/modeling/necks/blazeface_fpn.py -> build/lib/ppdet/modeling/necks
copying ppdet/modeling/necks/csp_pan.py -> build/lib/ppdet/modeling/necks
copying ppdet/modeling/necks/__init__.py -> build/lib/ppdet/modeling/necks
copying ppdet/modeling/necks/fpn.py -> build/lib/ppdet/modeling/necks
copying ppdet/modeling/necks/hrfpn.py -> build/lib/ppdet/modeling/necks
copying ppdet/modeling/necks/es_pan.py -> build/lib/ppdet/modeling/necks
copying ppdet/modeling/necks/ttf_fpn.py -> build/lib/ppdet/modeling/necks
copying ppdet/modeling/necks/centernet_fpn.py -> build/lib/ppdet/modeling/necks
creating build/lib/ppdet/modeling/assigners
copying ppdet/modeling/assigners/utils.py -> build/lib/ppdet/modeling/assigners
copying ppdet/modeling/assigners/atss_assigner.py -> build/lib/ppdet/modeling/assigners
copying ppdet/modeling/assigners/max_iou_assigner.py -> build/lib/ppdet/modeling/assigners
copying ppdet/modeling/assigners/__init__.py -> build/lib/ppdet/modeling/assigners
copying ppdet/modeling/assigners/task_aligned_assigner.py -> build/lib/ppdet/modeling/assigners
copying ppdet/modeling/assigners/simota_assigner.py -> build/lib/ppdet/modeling/assigners
creating build/lib/ppdet/modeling/mot/tracker
copying ppdet/modeling/mot/tracker/deepsort_tracker.py -> build/lib/ppdet/modeling/mot/tracker
copying ppdet/modeling/mot/tracker/base_jde_tracker.py -> build/lib/ppdet/modeling/mot/tracker
copying ppdet/modeling/mot/tracker/jde_tracker.py -> build/lib/ppdet/modeling/mot/tracker
copying ppdet/modeling/mot/tracker/__init__.py -> build/lib/ppdet/modeling/mot/tracker
copying ppdet/modeling/mot/tracker/base_sde_tracker.py -> build/lib/ppdet/modeling/mot/tracker
creating build/lib/ppdet/modeling/mot/motion
copying ppdet/modeling/mot/motion/kalman_filter.py -> build/lib/ppdet/modeling/mot/motion
copying ppdet/modeling/mot/motion/__init__.py -> build/lib/ppdet/modeling/mot/motion
creating build/lib/ppdet/modeling/mot/matching
copying ppdet/modeling/mot/matching/deepsort_matching.py -> build/lib/ppdet/modeling/mot/matching
copying ppdet/modeling/mot/matching/jde_matching.py -> build/lib/ppdet/modeling/mot/matching
copying ppdet/modeling/mot/matching/__init__.py -> build/lib/ppdet/modeling/mot/matching
creating build/lib/ppdet/model_zoo/tests
copying ppdet/model_zoo/tests/__init__.py -> build/lib/ppdet/model_zoo/tests
copying ppdet/model_zoo/tests/test_get_model.py -> build/lib/ppdet/model_zoo/tests
copying ppdet/model_zoo/tests/test_list_model.py -> build/lib/ppdet/model_zoo/tests
copying ppdet/model_zoo/MODEL_ZOO -> build/lib/ppdet/model_zoo
creating build/bdist.linux-x86_64
creating build/bdist.linux-x86_64/egg
creating build/bdist.linux-x86_64/egg/ppdet
copying build/lib/ppdet/optimizer.py -> build/bdist.linux-x86_64/egg/ppdet
creating build/bdist.linux-x86_64/egg/ppdet/core
copying build/lib/ppdet/core/workspace.py -> build/bdist.linux-x86_64/egg/ppdet/core
creating build/bdist.linux-x86_64/egg/ppdet/core/config
copying build/lib/ppdet/core/config/yaml_helpers.py -> build/bdist.linux-x86_64/egg/ppdet/core/config
copying build/lib/ppdet/core/config/__init__.py -> build/bdist.linux-x86_64/egg/ppdet/core/config
copying build/lib/ppdet/core/config/schema.py -> build/bdist.linux-x86_64/egg/ppdet/core/config
copying build/lib/ppdet/core/__init__.py -> build/bdist.linux-x86_64/egg/ppdet/core
creating build/bdist.linux-x86_64/egg/ppdet/engine
copying build/lib/ppdet/engine/env.py -> build/bdist.linux-x86_64/egg/ppdet/engine
copying build/lib/ppdet/engine/trainer.py -> build/bdist.linux-x86_64/egg/ppdet/engine
copying build/lib/ppdet/engine/tracker.py -> build/bdist.linux-x86_64/egg/ppdet/engine
copying build/lib/ppdet/engine/callbacks.py -> build/bdist.linux-x86_64/egg/ppdet/engine
copying build/lib/ppdet/engine/__init__.py -> build/bdist.linux-x86_64/egg/ppdet/engine
copying build/lib/ppdet/engine/export_utils.py -> build/bdist.linux-x86_64/egg/ppdet/engine
creating build/bdist.linux-x86_64/egg/ppdet/utils
copying build/lib/ppdet/utils/cli.py -> build/bdist.linux-x86_64/egg/ppdet/utils
copying build/lib/ppdet/utils/logger.py -> build/bdist.linux-x86_64/egg/ppdet/utils
copying build/lib/ppdet/utils/colormap.py -> build/bdist.linux-x86_64/egg/ppdet/utils
copying build/lib/ppdet/utils/profiler.py -> build/bdist.linux-x86_64/egg/ppdet/utils
copying build/lib/ppdet/utils/download.py -> build/bdist.linux-x86_64/egg/ppdet/utils
copying build/lib/ppdet/utils/visualizer.py -> build/bdist.linux-x86_64/egg/ppdet/utils
copying build/lib/ppdet/utils/check.py -> build/bdist.linux-x86_64/egg/ppdet/utils
copying build/lib/ppdet/utils/voc_utils.py -> build/bdist.linux-x86_64/egg/ppdet/utils
copying build/lib/ppdet/utils/__init__.py -> build/bdist.linux-x86_64/egg/ppdet/utils
copying build/lib/ppdet/utils/checkpoint.py -> build/bdist.linux-x86_64/egg/ppdet/utils
copying build/lib/ppdet/utils/stats.py -> build/bdist.linux-x86_64/egg/ppdet/utils
creating build/bdist.linux-x86_64/egg/ppdet/data
creating build/bdist.linux-x86_64/egg/ppdet/data/source
copying build/lib/ppdet/data/source/sniper_coco.py -> build/bdist.linux-x86_64/egg/ppdet/data/source
copying build/lib/ppdet/data/source/widerface.py -> build/bdist.linux-x86_64/egg/ppdet/data/source
copying build/lib/ppdet/data/source/__init__.py -> build/bdist.linux-x86_64/egg/ppdet/data/source
copying build/lib/ppdet/data/source/keypoint_coco.py -> build/bdist.linux-x86_64/egg/ppdet/data/source
copying build/lib/ppdet/data/source/coco.py -> build/bdist.linux-x86_64/egg/ppdet/data/source
copying build/lib/ppdet/data/source/dataset.py -> build/bdist.linux-x86_64/egg/ppdet/data/source
copying build/lib/ppdet/data/source/category.py -> build/bdist.linux-x86_64/egg/ppdet/data/source
copying build/lib/ppdet/data/source/voc.py -> build/bdist.linux-x86_64/egg/ppdet/data/source
copying build/lib/ppdet/data/source/mot.py -> build/bdist.linux-x86_64/egg/ppdet/data/source
creating build/bdist.linux-x86_64/egg/ppdet/data/crop_utils
copying build/lib/ppdet/data/crop_utils/annotation_cropper.py -> build/bdist.linux-x86_64/egg/ppdet/data/crop_utils
copying build/lib/ppdet/data/crop_utils/__init__.py -> build/bdist.linux-x86_64/egg/ppdet/data/crop_utils
copying build/lib/ppdet/data/crop_utils/chip_box_utils.py -> build/bdist.linux-x86_64/egg/ppdet/data/crop_utils
copying build/lib/ppdet/data/shm_utils.py -> build/bdist.linux-x86_64/egg/ppdet/data
copying build/lib/ppdet/data/reader.py -> build/bdist.linux-x86_64/egg/ppdet/data
creating build/bdist.linux-x86_64/egg/ppdet/data/transform
copying build/lib/ppdet/data/transform/autoaugment_utils.py -> build/bdist.linux-x86_64/egg/ppdet/data/transform
copying build/lib/ppdet/data/transform/op_helper.py -> build/bdist.linux-x86_64/egg/ppdet/data/transform
copying build/lib/ppdet/data/transform/atss_assigner.py -> build/bdist.linux-x86_64/egg/ppdet/data/transform
copying build/lib/ppdet/data/transform/mot_operators.py -> build/bdist.linux-x86_64/egg/ppdet/data/transform
copying build/lib/ppdet/data/transform/operators.py -> build/bdist.linux-x86_64/egg/ppdet/data/transform
copying build/lib/ppdet/data/transform/__init__.py -> build/bdist.linux-x86_64/egg/ppdet/data/transform
copying build/lib/ppdet/data/transform/gridmask_utils.py -> build/bdist.linux-x86_64/egg/ppdet/data/transform
copying build/lib/ppdet/data/transform/batch_operators.py -> build/bdist.linux-x86_64/egg/ppdet/data/transform
copying build/lib/ppdet/data/transform/keypoint_operators.py -> build/bdist.linux-x86_64/egg/ppdet/data/transform
copying build/lib/ppdet/data/__init__.py -> build/bdist.linux-x86_64/egg/ppdet/data
creating build/bdist.linux-x86_64/egg/ppdet/slim
copying build/lib/ppdet/slim/quant.py -> build/bdist.linux-x86_64/egg/ppdet/slim
copying build/lib/ppdet/slim/distill.py -> build/bdist.linux-x86_64/egg/ppdet/slim
copying build/lib/ppdet/slim/ofa.py -> build/bdist.linux-x86_64/egg/ppdet/slim
copying build/lib/ppdet/slim/unstructured_prune.py -> build/bdist.linux-x86_64/egg/ppdet/slim
copying build/lib/ppdet/slim/__init__.py -> build/bdist.linux-x86_64/egg/ppdet/slim
copying build/lib/ppdet/slim/prune.py -> build/bdist.linux-x86_64/egg/ppdet/slim
copying build/lib/ppdet/__init__.py -> build/bdist.linux-x86_64/egg/ppdet
creating build/bdist.linux-x86_64/egg/ppdet/modeling
copying build/lib/ppdet/modeling/keypoint_utils.py -> build/bdist.linux-x86_64/egg/ppdet/modeling
creating build/bdist.linux-x86_64/egg/ppdet/modeling/heads
copying build/lib/ppdet/modeling/heads/sparsercnn_head.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/heads
copying build/lib/ppdet/modeling/heads/ttf_head.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/heads
copying build/lib/ppdet/modeling/heads/detr_head.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/heads
copying build/lib/ppdet/modeling/heads/bbox_head.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/heads
copying build/lib/ppdet/modeling/heads/fcos_head.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/heads
copying build/lib/ppdet/modeling/heads/keypoint_hrhrnet_head.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/heads
copying build/lib/ppdet/modeling/heads/retina_head.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/heads
copying build/lib/ppdet/modeling/heads/centernet_head.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/heads
copying build/lib/ppdet/modeling/heads/tood_head.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/heads
copying build/lib/ppdet/modeling/heads/s2anet_head.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/heads
copying build/lib/ppdet/modeling/heads/ppyoloe_head.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/heads
copying build/lib/ppdet/modeling/heads/roi_extractor.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/heads
copying build/lib/ppdet/modeling/heads/ssd_head.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/heads
copying build/lib/ppdet/modeling/heads/yolo_head.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/heads
copying build/lib/ppdet/modeling/heads/face_head.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/heads
copying build/lib/ppdet/modeling/heads/solov2_head.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/heads
copying build/lib/ppdet/modeling/heads/__init__.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/heads
copying build/lib/ppdet/modeling/heads/mask_head.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/heads
copying build/lib/ppdet/modeling/heads/pico_head.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/heads
copying build/lib/ppdet/modeling/heads/simota_head.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/heads
copying build/lib/ppdet/modeling/heads/cascade_head.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/heads
copying build/lib/ppdet/modeling/heads/gfl_head.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/heads
copying build/lib/ppdet/modeling/initializer.py -> build/bdist.linux-x86_64/egg/ppdet/modeling
copying build/lib/ppdet/modeling/ops.py -> build/bdist.linux-x86_64/egg/ppdet/modeling
copying build/lib/ppdet/modeling/bbox_utils.py -> build/bdist.linux-x86_64/egg/ppdet/modeling
creating build/bdist.linux-x86_64/egg/ppdet/modeling/architectures
copying build/lib/ppdet/modeling/architectures/solov2.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/architectures
copying build/lib/ppdet/modeling/architectures/tood.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/architectures
copying build/lib/ppdet/modeling/architectures/yolo.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/architectures
copying build/lib/ppdet/modeling/architectures/meta_arch.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/architectures
copying build/lib/ppdet/modeling/architectures/faster_rcnn.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/architectures
copying build/lib/ppdet/modeling/architectures/keypoint_hrhrnet.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/architectures
copying build/lib/ppdet/modeling/architectures/centernet.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/architectures
copying build/lib/ppdet/modeling/architectures/picodet.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/architectures
copying build/lib/ppdet/modeling/architectures/keypoint_hrnet.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/architectures
copying build/lib/ppdet/modeling/architectures/detr.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/architectures
copying build/lib/ppdet/modeling/architectures/blazeface.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/architectures
copying build/lib/ppdet/modeling/architectures/jde.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/architectures
copying build/lib/ppdet/modeling/architectures/gfl.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/architectures
copying build/lib/ppdet/modeling/architectures/ssd.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/architectures
copying build/lib/ppdet/modeling/architectures/cascade_rcnn.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/architectures
copying build/lib/ppdet/modeling/architectures/fairmot.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/architectures
copying build/lib/ppdet/modeling/architectures/mask_rcnn.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/architectures
copying build/lib/ppdet/modeling/architectures/__init__.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/architectures
copying build/lib/ppdet/modeling/architectures/s2anet.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/architectures
copying build/lib/ppdet/modeling/architectures/bytetrack.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/architectures
copying build/lib/ppdet/modeling/architectures/sparse_rcnn.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/architectures
copying build/lib/ppdet/modeling/architectures/fcos.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/architectures
copying build/lib/ppdet/modeling/architectures/deepsort.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/architectures
copying build/lib/ppdet/modeling/architectures/retinanet.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/architectures
copying build/lib/ppdet/modeling/architectures/ttfnet.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/architectures
creating build/bdist.linux-x86_64/egg/ppdet/modeling/backbones
copying build/lib/ppdet/modeling/backbones/ghostnet.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/backbones
copying build/lib/ppdet/modeling/backbones/esnet.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/backbones
copying build/lib/ppdet/modeling/backbones/lcnet.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/backbones
copying build/lib/ppdet/modeling/backbones/shufflenet_v2.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/backbones
copying build/lib/ppdet/modeling/backbones/darknet.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/backbones
copying build/lib/ppdet/modeling/backbones/swin_transformer.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/backbones
copying build/lib/ppdet/modeling/backbones/mobilenet_v3.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/backbones
copying build/lib/ppdet/modeling/backbones/dla.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/backbones
copying build/lib/ppdet/modeling/backbones/hardnet.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/backbones
copying build/lib/ppdet/modeling/backbones/hrnet.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/backbones
copying build/lib/ppdet/modeling/backbones/name_adapter.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/backbones
copying build/lib/ppdet/modeling/backbones/cspresnet.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/backbones
copying build/lib/ppdet/modeling/backbones/senet.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/backbones
copying build/lib/ppdet/modeling/backbones/mobilenet_v1.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/backbones
copying build/lib/ppdet/modeling/backbones/__init__.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/backbones
copying build/lib/ppdet/modeling/backbones/lite_hrnet.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/backbones
copying build/lib/ppdet/modeling/backbones/res2net.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/backbones
copying build/lib/ppdet/modeling/backbones/blazenet.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/backbones
copying build/lib/ppdet/modeling/backbones/vgg.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/backbones
copying build/lib/ppdet/modeling/backbones/resnet.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/backbones
creating build/bdist.linux-x86_64/egg/ppdet/modeling/reid
copying build/lib/ppdet/modeling/reid/resnet_embedding.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/reid
copying build/lib/ppdet/modeling/reid/jde_embedding_head.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/reid
copying build/lib/ppdet/modeling/reid/pyramidal_embedding.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/reid
copying build/lib/ppdet/modeling/reid/fairmot_embedding_head.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/reid
copying build/lib/ppdet/modeling/reid/__init__.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/reid
copying build/lib/ppdet/modeling/reid/pplcnet_embedding.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/reid
copying build/lib/ppdet/modeling/reid/resnet.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/reid
creating build/bdist.linux-x86_64/egg/ppdet/modeling/coders
copying build/lib/ppdet/modeling/coders/delta_bbox_coder.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/coders
copying build/lib/ppdet/modeling/coders/__init__.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/coders
copying build/lib/ppdet/modeling/__init__.py -> build/bdist.linux-x86_64/egg/ppdet/modeling
creating build/bdist.linux-x86_64/egg/ppdet/modeling/mot
copying build/lib/ppdet/modeling/mot/utils.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/mot
copying build/lib/ppdet/modeling/mot/visualization.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/mot
creating build/bdist.linux-x86_64/egg/ppdet/modeling/mot/tracker
copying build/lib/ppdet/modeling/mot/tracker/deepsort_tracker.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/mot/tracker
copying build/lib/ppdet/modeling/mot/tracker/base_jde_tracker.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/mot/tracker
copying build/lib/ppdet/modeling/mot/tracker/jde_tracker.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/mot/tracker
copying build/lib/ppdet/modeling/mot/tracker/__init__.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/mot/tracker
copying build/lib/ppdet/modeling/mot/tracker/base_sde_tracker.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/mot/tracker
creating build/bdist.linux-x86_64/egg/ppdet/modeling/mot/motion
copying build/lib/ppdet/modeling/mot/motion/kalman_filter.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/mot/motion
copying build/lib/ppdet/modeling/mot/motion/__init__.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/mot/motion
creating build/bdist.linux-x86_64/egg/ppdet/modeling/mot/matching
copying build/lib/ppdet/modeling/mot/matching/deepsort_matching.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/mot/matching
copying build/lib/ppdet/modeling/mot/matching/jde_matching.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/mot/matching
copying build/lib/ppdet/modeling/mot/matching/__init__.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/mot/matching
copying build/lib/ppdet/modeling/mot/__init__.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/mot
copying build/lib/ppdet/modeling/shape_spec.py -> build/bdist.linux-x86_64/egg/ppdet/modeling
creating build/bdist.linux-x86_64/egg/ppdet/modeling/tests
copying build/lib/ppdet/modeling/tests/test_mstest.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/tests
copying build/lib/ppdet/modeling/tests/test_yolov3_loss.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/tests
copying build/lib/ppdet/modeling/tests/test_architectures.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/tests
copying build/lib/ppdet/modeling/tests/__init__.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/tests
copying build/lib/ppdet/modeling/tests/test_base.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/tests
copying build/lib/ppdet/modeling/tests/test_ops.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/tests
creating build/bdist.linux-x86_64/egg/ppdet/modeling/losses
copying build/lib/ppdet/modeling/losses/gfocal_loss.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/losses
copying build/lib/ppdet/modeling/losses/fcos_loss.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/losses
copying build/lib/ppdet/modeling/losses/jde_loss.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/losses
copying build/lib/ppdet/modeling/losses/fairmot_loss.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/losses
copying build/lib/ppdet/modeling/losses/ssd_loss.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/losses
copying build/lib/ppdet/modeling/losses/yolo_loss.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/losses
copying build/lib/ppdet/modeling/losses/iou_loss.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/losses
copying build/lib/ppdet/modeling/losses/smooth_l1_loss.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/losses
copying build/lib/ppdet/modeling/losses/focal_loss.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/losses
copying build/lib/ppdet/modeling/losses/varifocal_loss.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/losses
copying build/lib/ppdet/modeling/losses/solov2_loss.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/losses
copying build/lib/ppdet/modeling/losses/__init__.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/losses
copying build/lib/ppdet/modeling/losses/keypoint_loss.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/losses
copying build/lib/ppdet/modeling/losses/ctfocal_loss.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/losses
copying build/lib/ppdet/modeling/losses/detr_loss.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/losses
copying build/lib/ppdet/modeling/losses/iou_aware_loss.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/losses
copying build/lib/ppdet/modeling/losses/sparsercnn_loss.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/losses
creating build/bdist.linux-x86_64/egg/ppdet/modeling/proposal_generator
copying build/lib/ppdet/modeling/proposal_generator/rpn_head.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/proposal_generator
copying build/lib/ppdet/modeling/proposal_generator/anchor_generator.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/proposal_generator
copying build/lib/ppdet/modeling/proposal_generator/__init__.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/proposal_generator
copying build/lib/ppdet/modeling/proposal_generator/proposal_generator.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/proposal_generator
copying build/lib/ppdet/modeling/proposal_generator/target_layer.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/proposal_generator
copying build/lib/ppdet/modeling/proposal_generator/target.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/proposal_generator
creating build/bdist.linux-x86_64/egg/ppdet/modeling/transformers
copying build/lib/ppdet/modeling/transformers/utils.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/transformers
copying build/lib/ppdet/modeling/transformers/position_encoding.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/transformers
copying build/lib/ppdet/modeling/transformers/detr_transformer.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/transformers
copying build/lib/ppdet/modeling/transformers/deformable_transformer.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/transformers
copying build/lib/ppdet/modeling/transformers/__init__.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/transformers
copying build/lib/ppdet/modeling/transformers/matchers.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/transformers
copying build/lib/ppdet/modeling/layers.py -> build/bdist.linux-x86_64/egg/ppdet/modeling
copying build/lib/ppdet/modeling/post_process.py -> build/bdist.linux-x86_64/egg/ppdet/modeling
creating build/bdist.linux-x86_64/egg/ppdet/modeling/necks
copying build/lib/ppdet/modeling/necks/yolo_fpn.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/necks
copying build/lib/ppdet/modeling/necks/bifpn.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/necks
copying build/lib/ppdet/modeling/necks/custom_pan.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/necks
copying build/lib/ppdet/modeling/necks/lc_pan.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/necks
copying build/lib/ppdet/modeling/necks/blazeface_fpn.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/necks
copying build/lib/ppdet/modeling/necks/csp_pan.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/necks
copying build/lib/ppdet/modeling/necks/__init__.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/necks
copying build/lib/ppdet/modeling/necks/fpn.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/necks
copying build/lib/ppdet/modeling/necks/hrfpn.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/necks
copying build/lib/ppdet/modeling/necks/es_pan.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/necks
copying build/lib/ppdet/modeling/necks/ttf_fpn.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/necks
copying build/lib/ppdet/modeling/necks/centernet_fpn.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/necks
creating build/bdist.linux-x86_64/egg/ppdet/modeling/assigners
copying build/lib/ppdet/modeling/assigners/utils.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/assigners
copying build/lib/ppdet/modeling/assigners/atss_assigner.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/assigners
copying build/lib/ppdet/modeling/assigners/max_iou_assigner.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/assigners
copying build/lib/ppdet/modeling/assigners/__init__.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/assigners
copying build/lib/ppdet/modeling/assigners/task_aligned_assigner.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/assigners
copying build/lib/ppdet/modeling/assigners/simota_assigner.py -> build/bdist.linux-x86_64/egg/ppdet/modeling/assigners
copying build/lib/ppdet/version.py -> build/bdist.linux-x86_64/egg/ppdet
creating build/bdist.linux-x86_64/egg/ppdet/metrics
copying build/lib/ppdet/metrics/mot_metrics.py -> build/bdist.linux-x86_64/egg/ppdet/metrics
copying build/lib/ppdet/metrics/keypoint_metrics.py -> build/bdist.linux-x86_64/egg/ppdet/metrics
copying build/lib/ppdet/metrics/mcmot_metrics.py -> build/bdist.linux-x86_64/egg/ppdet/metrics
copying build/lib/ppdet/metrics/metrics.py -> build/bdist.linux-x86_64/egg/ppdet/metrics
copying build/lib/ppdet/metrics/widerface_utils.py -> build/bdist.linux-x86_64/egg/ppdet/metrics
copying build/lib/ppdet/metrics/munkres.py -> build/bdist.linux-x86_64/egg/ppdet/metrics
copying build/lib/ppdet/metrics/coco_utils.py -> build/bdist.linux-x86_64/egg/ppdet/metrics
copying build/lib/ppdet/metrics/__init__.py -> build/bdist.linux-x86_64/egg/ppdet/metrics
copying build/lib/ppdet/metrics/json_results.py -> build/bdist.linux-x86_64/egg/ppdet/metrics
copying build/lib/ppdet/metrics/map_utils.py -> build/bdist.linux-x86_64/egg/ppdet/metrics
creating build/bdist.linux-x86_64/egg/ppdet/model_zoo
copying build/lib/ppdet/model_zoo/model_zoo.py -> build/bdist.linux-x86_64/egg/ppdet/model_zoo
copying build/lib/ppdet/model_zoo/MODEL_ZOO -> build/bdist.linux-x86_64/egg/ppdet/model_zoo
copying build/lib/ppdet/model_zoo/__init__.py -> build/bdist.linux-x86_64/egg/ppdet/model_zoo
creating build/bdist.linux-x86_64/egg/ppdet/model_zoo/tests
copying build/lib/ppdet/model_zoo/tests/__init__.py -> build/bdist.linux-x86_64/egg/ppdet/model_zoo/tests
copying build/lib/ppdet/model_zoo/tests/test_get_model.py -> build/bdist.linux-x86_64/egg/ppdet/model_zoo/tests
copying build/lib/ppdet/model_zoo/tests/test_list_model.py -> build/bdist.linux-x86_64/egg/ppdet/model_zoo/tests
byte-compiling build/bdist.linux-x86_64/egg/ppdet/optimizer.py to optimizer.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/core/workspace.py to workspace.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/core/config/yaml_helpers.py to yaml_helpers.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/core/config/__init__.py to __init__.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/core/config/schema.py to schema.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/core/__init__.py to __init__.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/engine/env.py to env.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/engine/trainer.py to trainer.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/engine/tracker.py to tracker.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/engine/callbacks.py to callbacks.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/engine/__init__.py to __init__.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/engine/export_utils.py to export_utils.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/utils/cli.py to cli.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/utils/logger.py to logger.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/utils/colormap.py to colormap.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/utils/profiler.py to profiler.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/utils/download.py to download.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/utils/visualizer.py to visualizer.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/utils/check.py to check.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/utils/voc_utils.py to voc_utils.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/utils/__init__.py to __init__.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/utils/checkpoint.py to checkpoint.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/utils/stats.py to stats.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/data/source/sniper_coco.py to sniper_coco.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/data/source/widerface.py to widerface.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/data/source/__init__.py to __init__.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/data/source/keypoint_coco.py to keypoint_coco.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/data/source/coco.py to coco.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/data/source/dataset.py to dataset.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/data/source/category.py to category.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/data/source/voc.py to voc.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/data/source/mot.py to mot.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/data/crop_utils/annotation_cropper.py to annotation_cropper.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/data/crop_utils/__init__.py to __init__.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/data/crop_utils/chip_box_utils.py to chip_box_utils.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/data/shm_utils.py to shm_utils.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/data/reader.py to reader.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/data/transform/autoaugment_utils.py to autoaugment_utils.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/data/transform/op_helper.py to op_helper.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/data/transform/atss_assigner.py to atss_assigner.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/data/transform/mot_operators.py to mot_operators.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/data/transform/operators.py to operators.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/data/transform/__init__.py to __init__.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/data/transform/gridmask_utils.py to gridmask_utils.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/data/transform/batch_operators.py to batch_operators.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/data/transform/keypoint_operators.py to keypoint_operators.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/data/__init__.py to __init__.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/slim/quant.py to quant.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/slim/distill.py to distill.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/slim/ofa.py to ofa.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/slim/unstructured_prune.py to unstructured_prune.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/slim/__init__.py to __init__.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/slim/prune.py to prune.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/__init__.py to __init__.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/keypoint_utils.py to keypoint_utils.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/heads/sparsercnn_head.py to sparsercnn_head.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/heads/ttf_head.py to ttf_head.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/heads/detr_head.py to detr_head.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/heads/bbox_head.py to bbox_head.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/heads/fcos_head.py to fcos_head.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/heads/keypoint_hrhrnet_head.py to keypoint_hrhrnet_head.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/heads/retina_head.py to retina_head.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/heads/centernet_head.py to centernet_head.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/heads/tood_head.py to tood_head.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/heads/s2anet_head.py to s2anet_head.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/heads/ppyoloe_head.py to ppyoloe_head.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/heads/roi_extractor.py to roi_extractor.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/heads/ssd_head.py to ssd_head.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/heads/yolo_head.py to yolo_head.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/heads/face_head.py to face_head.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/heads/solov2_head.py to solov2_head.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/heads/__init__.py to __init__.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/heads/mask_head.py to mask_head.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/heads/pico_head.py to pico_head.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/heads/simota_head.py to simota_head.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/heads/cascade_head.py to cascade_head.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/heads/gfl_head.py to gfl_head.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/initializer.py to initializer.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/ops.py to ops.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/bbox_utils.py to bbox_utils.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/architectures/solov2.py to solov2.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/architectures/tood.py to tood.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/architectures/yolo.py to yolo.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/architectures/meta_arch.py to meta_arch.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/architectures/faster_rcnn.py to faster_rcnn.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/architectures/keypoint_hrhrnet.py to keypoint_hrhrnet.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/architectures/centernet.py to centernet.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/architectures/picodet.py to picodet.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/architectures/keypoint_hrnet.py to keypoint_hrnet.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/architectures/detr.py to detr.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/architectures/blazeface.py to blazeface.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/architectures/jde.py to jde.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/architectures/gfl.py to gfl.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/architectures/ssd.py to ssd.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/architectures/cascade_rcnn.py to cascade_rcnn.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/architectures/fairmot.py to fairmot.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/architectures/mask_rcnn.py to mask_rcnn.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/architectures/__init__.py to __init__.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/architectures/s2anet.py to s2anet.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/architectures/bytetrack.py to bytetrack.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/architectures/sparse_rcnn.py to sparse_rcnn.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/architectures/fcos.py to fcos.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/architectures/deepsort.py to deepsort.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/architectures/retinanet.py to retinanet.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/architectures/ttfnet.py to ttfnet.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/backbones/ghostnet.py to ghostnet.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/backbones/esnet.py to esnet.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/backbones/lcnet.py to lcnet.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/backbones/shufflenet_v2.py to shufflenet_v2.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/backbones/darknet.py to darknet.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/backbones/swin_transformer.py to swin_transformer.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/backbones/mobilenet_v3.py to mobilenet_v3.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/backbones/dla.py to dla.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/backbones/hardnet.py to hardnet.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/backbones/hrnet.py to hrnet.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/backbones/name_adapter.py to name_adapter.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/backbones/cspresnet.py to cspresnet.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/backbones/senet.py to senet.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/backbones/mobilenet_v1.py to mobilenet_v1.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/backbones/__init__.py to __init__.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/backbones/lite_hrnet.py to lite_hrnet.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/backbones/res2net.py to res2net.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/backbones/blazenet.py to blazenet.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/backbones/vgg.py to vgg.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/backbones/resnet.py to resnet.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/reid/resnet_embedding.py to resnet_embedding.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/reid/jde_embedding_head.py to jde_embedding_head.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/reid/pyramidal_embedding.py to pyramidal_embedding.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/reid/fairmot_embedding_head.py to fairmot_embedding_head.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/reid/__init__.py to __init__.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/reid/pplcnet_embedding.py to pplcnet_embedding.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/reid/resnet.py to resnet.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/coders/delta_bbox_coder.py to delta_bbox_coder.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/coders/__init__.py to __init__.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/__init__.py to __init__.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/mot/utils.py to utils.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/mot/visualization.py to visualization.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/mot/tracker/deepsort_tracker.py to deepsort_tracker.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/mot/tracker/base_jde_tracker.py to base_jde_tracker.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/mot/tracker/jde_tracker.py to jde_tracker.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/mot/tracker/__init__.py to __init__.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/mot/tracker/base_sde_tracker.py to base_sde_tracker.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/mot/motion/kalman_filter.py to kalman_filter.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/mot/motion/__init__.py to __init__.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/mot/matching/deepsort_matching.py to deepsort_matching.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/mot/matching/jde_matching.py to jde_matching.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/mot/matching/__init__.py to __init__.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/mot/__init__.py to __init__.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/shape_spec.py to shape_spec.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/tests/test_mstest.py to test_mstest.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/tests/test_yolov3_loss.py to test_yolov3_loss.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/tests/test_architectures.py to test_architectures.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/tests/__init__.py to __init__.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/tests/test_base.py to test_base.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/tests/test_ops.py to test_ops.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/losses/gfocal_loss.py to gfocal_loss.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/losses/fcos_loss.py to fcos_loss.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/losses/jde_loss.py to jde_loss.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/losses/fairmot_loss.py to fairmot_loss.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/losses/ssd_loss.py to ssd_loss.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/losses/yolo_loss.py to yolo_loss.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/losses/iou_loss.py to iou_loss.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/losses/smooth_l1_loss.py to smooth_l1_loss.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/losses/focal_loss.py to focal_loss.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/losses/varifocal_loss.py to varifocal_loss.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/losses/solov2_loss.py to solov2_loss.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/losses/__init__.py to __init__.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/losses/keypoint_loss.py to keypoint_loss.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/losses/ctfocal_loss.py to ctfocal_loss.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/losses/detr_loss.py to detr_loss.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/losses/iou_aware_loss.py to iou_aware_loss.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/losses/sparsercnn_loss.py to sparsercnn_loss.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/proposal_generator/rpn_head.py to rpn_head.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/proposal_generator/anchor_generator.py to anchor_generator.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/proposal_generator/__init__.py to __init__.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/proposal_generator/proposal_generator.py to proposal_generator.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/proposal_generator/target_layer.py to target_layer.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/proposal_generator/target.py to target.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/transformers/utils.py to utils.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/transformers/position_encoding.py to position_encoding.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/transformers/detr_transformer.py to detr_transformer.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/transformers/deformable_transformer.py to deformable_transformer.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/transformers/__init__.py to __init__.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/transformers/matchers.py to matchers.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/layers.py to layers.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/post_process.py to post_process.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/necks/yolo_fpn.py to yolo_fpn.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/necks/bifpn.py to bifpn.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/necks/custom_pan.py to custom_pan.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/necks/lc_pan.py to lc_pan.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/necks/blazeface_fpn.py to blazeface_fpn.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/necks/csp_pan.py to csp_pan.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/necks/__init__.py to __init__.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/necks/fpn.py to fpn.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/necks/hrfpn.py to hrfpn.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/necks/es_pan.py to es_pan.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/necks/ttf_fpn.py to ttf_fpn.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/necks/centernet_fpn.py to centernet_fpn.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/assigners/utils.py to utils.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/assigners/atss_assigner.py to atss_assigner.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/assigners/max_iou_assigner.py to max_iou_assigner.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/assigners/__init__.py to __init__.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/assigners/task_aligned_assigner.py to task_aligned_assigner.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/modeling/assigners/simota_assigner.py to simota_assigner.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/version.py to version.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/metrics/mot_metrics.py to mot_metrics.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/metrics/keypoint_metrics.py to keypoint_metrics.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/metrics/mcmot_metrics.py to mcmot_metrics.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/metrics/metrics.py to metrics.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/metrics/widerface_utils.py to widerface_utils.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/metrics/munkres.py to munkres.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/metrics/coco_utils.py to coco_utils.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/metrics/__init__.py to __init__.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/metrics/json_results.py to json_results.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/metrics/map_utils.py to map_utils.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/model_zoo/model_zoo.py to model_zoo.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/model_zoo/__init__.py to __init__.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/model_zoo/tests/__init__.py to __init__.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/model_zoo/tests/test_get_model.py to test_get_model.cpython-37.pyc
byte-compiling build/bdist.linux-x86_64/egg/ppdet/model_zoo/tests/test_list_model.py to test_list_model.cpython-37.pyc
creating build/bdist.linux-x86_64/egg/EGG-INFO
copying paddledet.egg-info/PKG-INFO -> build/bdist.linux-x86_64/egg/EGG-INFO
copying paddledet.egg-info/SOURCES.txt -> build/bdist.linux-x86_64/egg/EGG-INFO
copying paddledet.egg-info/dependency_links.txt -> build/bdist.linux-x86_64/egg/EGG-INFO
copying paddledet.egg-info/requires.txt -> build/bdist.linux-x86_64/egg/EGG-INFO
copying paddledet.egg-info/top_level.txt -> build/bdist.linux-x86_64/egg/EGG-INFO
zip_safe flag not set; analyzing archive contents...
ppdet.data.transform.__pycache__.autoaugment_utils.cpython-37: module MAY be using inspect.stack
ppdet.modeling.tests.__pycache__.test_mstest.cpython-37: module references __file__
ppdet.modeling.tests.__pycache__.test_ops.cpython-37: module references __file__
ppdet.modeling.tests.__pycache__.test_yolov3_loss.cpython-37: module references __file__
creating dist
creating 'dist/paddledet-2.4.0-py3.7.egg' and adding 'build/bdist.linux-x86_64/egg' to it
removing 'build/bdist.linux-x86_64/egg' (and everything under it)
Processing paddledet-2.4.0-py3.7.egg
creating /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages/paddledet-2.4.0-py3.7.egg
Extracting paddledet-2.4.0-py3.7.egg to /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Adding paddledet 2.4.0 to easy-install.pth file

Installed /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages/paddledet-2.4.0-py3.7.egg
Processing dependencies for paddledet==2.4.0
Searching for typeguard==2.13.3
Best match: typeguard 2.13.3
Adding typeguard 2.13.3 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for visualdl==2.2.3
Best match: visualdl 2.2.3
Adding visualdl 2.2.3 to easy-install.pth file
Installing visualdl script to /opt/conda/envs/python35-paddle120-env/bin

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for openpyxl==3.0.5
Best match: openpyxl 3.0.5
Adding openpyxl 3.0.5 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for motmetrics==1.2.5
Best match: motmetrics 1.2.5
Adding motmetrics 1.2.5 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for sklearn==0.0
Best match: sklearn 0.0
Adding sklearn 0.0 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for lap==0.4.0
Best match: lap 0.4.0
Adding lap 0.4.0 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for setuptools==56.2.0
Best match: setuptools 56.2.0
Adding setuptools 56.2.0 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for pycocotools==2.0.4
Best match: pycocotools 2.0.4
Adding pycocotools 2.0.4 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for Cython==0.29
Best match: Cython 0.29
Adding Cython 0.29 to easy-install.pth file
Installing cygdb script to /opt/conda/envs/python35-paddle120-env/bin
Installing cython script to /opt/conda/envs/python35-paddle120-env/bin
Installing cythonize script to /opt/conda/envs/python35-paddle120-env/bin

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for terminaltables==3.1.10
Best match: terminaltables 3.1.10
Adding terminaltables 3.1.10 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for scipy==1.6.3
Best match: scipy 1.6.3
Adding scipy 1.6.3 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for Shapely==1.8.1.post1
Best match: Shapely 1.8.1.post1
Adding Shapely 1.8.1.post1 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for PyYAML==5.1.2
Best match: PyYAML 5.1.2
Adding PyYAML 5.1.2 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for opencv-python==4.1.1.26
Best match: opencv-python 4.1.1.26
Adding opencv-python 4.1.1.26 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for tqdm==4.27.0
Best match: tqdm 4.27.0
Adding tqdm 4.27.0 to easy-install.pth file
Installing tqdm script to /opt/conda/envs/python35-paddle120-env/bin

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for shellcheck-py==0.7.1.1
Best match: shellcheck-py 0.7.1.1
Adding shellcheck-py 0.7.1.1 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for numpy==1.19.5
Best match: numpy 1.19.5
Adding numpy 1.19.5 to easy-install.pth file
Installing f2py script to /opt/conda/envs/python35-paddle120-env/bin
Installing f2py3 script to /opt/conda/envs/python35-paddle120-env/bin
Installing f2py3.7 script to /opt/conda/envs/python35-paddle120-env/bin

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for Pillow==8.2.0
Best match: Pillow 8.2.0
Adding Pillow 8.2.0 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for pandas==1.1.5
Best match: pandas 1.1.5
Adding pandas 1.1.5 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for pre-commit==1.21.0
Best match: pre-commit 1.21.0
Adding pre-commit 1.21.0 to easy-install.pth file
Installing pre-commit script to /opt/conda/envs/python35-paddle120-env/bin
Installing pre-commit-validate-config script to /opt/conda/envs/python35-paddle120-env/bin
Installing pre-commit-validate-manifest script to /opt/conda/envs/python35-paddle120-env/bin

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for six==1.16.0
Best match: six 1.16.0
Adding six 1.16.0 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for Flask==1.1.1
Best match: Flask 1.1.1
Adding Flask 1.1.1 to easy-install.pth file
Installing flask script to /opt/conda/envs/python35-paddle120-env/bin

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for requests==2.24.0
Best match: requests 2.24.0
Adding requests 2.24.0 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for protobuf==3.14.0
Best match: protobuf 3.14.0
Adding protobuf 3.14.0 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for Flask-Babel==1.0.0
Best match: Flask-Babel 1.0.0
Adding Flask-Babel 1.0.0 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for flake8==4.0.1
Best match: flake8 4.0.1
Adding flake8 4.0.1 to easy-install.pth file
Installing flake8 script to /opt/conda/envs/python35-paddle120-env/bin

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for bce-python-sdk==0.8.53
Best match: bce-python-sdk 0.8.53
Adding bce-python-sdk 0.8.53 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for matplotlib==2.2.3
Best match: matplotlib 2.2.3
Adding matplotlib 2.2.3 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for jdcal==1.4.1
Best match: jdcal 1.4.1
Adding jdcal 1.4.1 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for et-xmlfile==1.0.1
Best match: et-xmlfile 1.0.1
Adding et-xmlfile 1.0.1 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for xmltodict==0.12.0
Best match: xmltodict 0.12.0
Adding xmltodict 0.12.0 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for scikit-learn==0.24.2
Best match: scikit-learn 0.24.2
Adding scikit-learn 0.24.2 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for pytz==2022.1
Best match: pytz 2022.1
Adding pytz 2022.1 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for python-dateutil==2.8.2
Best match: python-dateutil 2.8.2
Adding python-dateutil 2.8.2 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for toml==0.10.0
Best match: toml 0.10.0
Adding toml 0.10.0 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for cfgv==2.0.1
Best match: cfgv 2.0.1
Adding cfgv 2.0.1 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for importlib-metadata==4.2.0
Best match: importlib-metadata 4.2.0
Adding importlib-metadata 4.2.0 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for identify==1.4.10
Best match: identify 1.4.10
Adding identify 1.4.10 to easy-install.pth file
Installing identify-cli script to /opt/conda/envs/python35-paddle120-env/bin

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for virtualenv==16.7.9
Best match: virtualenv 16.7.9
Adding virtualenv 16.7.9 to easy-install.pth file
Installing virtualenv script to /opt/conda/envs/python35-paddle120-env/bin

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for aspy.yaml==1.3.0
Best match: aspy.yaml 1.3.0
Adding aspy.yaml 1.3.0 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for nodeenv==1.3.4
Best match: nodeenv 1.3.4
Adding nodeenv 1.3.4 to easy-install.pth file
Installing nodeenv script to /opt/conda/envs/python35-paddle120-env/bin

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for Werkzeug==0.16.0
Best match: Werkzeug 0.16.0
Adding Werkzeug 0.16.0 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for itsdangerous==1.1.0
Best match: itsdangerous 1.1.0
Adding itsdangerous 1.1.0 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for Jinja2==3.0.0
Best match: Jinja2 3.0.0
Adding Jinja2 3.0.0 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for Click==7.0
Best match: Click 7.0
Adding Click 7.0 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for certifi==2021.10.8
Best match: certifi 2021.10.8
Adding certifi 2021.10.8 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for chardet==3.0.4
Best match: chardet 3.0.4
Adding chardet 3.0.4 to easy-install.pth file
Installing chardetect script to /opt/conda/envs/python35-paddle120-env/bin

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for urllib3==1.25.11
Best match: urllib3 1.25.11
Adding urllib3 1.25.11 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for idna==2.10
Best match: idna 2.10
Adding idna 2.10 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for Babel==2.9.1
Best match: Babel 2.9.1
Adding Babel 2.9.1 to easy-install.pth file
Installing pybabel script to /opt/conda/envs/python35-paddle120-env/bin

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for pycodestyle==2.8.0
Best match: pycodestyle 2.8.0
Adding pycodestyle 2.8.0 to easy-install.pth file
Installing pycodestyle script to /opt/conda/envs/python35-paddle120-env/bin

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for pyflakes==2.4.0
Best match: pyflakes 2.4.0
Adding pyflakes 2.4.0 to easy-install.pth file
Installing pyflakes script to /opt/conda/envs/python35-paddle120-env/bin

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for mccabe==0.6.1
Best match: mccabe 0.6.1
Adding mccabe 0.6.1 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for future==0.18.0
Best match: future 0.18.0
Adding future 0.18.0 to easy-install.pth file
Installing futurize script to /opt/conda/envs/python35-paddle120-env/bin
Installing pasteurize script to /opt/conda/envs/python35-paddle120-env/bin

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for pycryptodome==3.9.9
Best match: pycryptodome 3.9.9
Adding pycryptodome 3.9.9 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for cycler==0.10.0
Best match: cycler 0.10.0
Adding cycler 0.10.0 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for pyparsing==3.0.7
Best match: pyparsing 3.0.7
Adding pyparsing 3.0.7 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for kiwisolver==1.1.0
Best match: kiwisolver 1.1.0
Adding kiwisolver 1.1.0 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for threadpoolctl==2.1.0
Best match: threadpoolctl 2.1.0
Adding threadpoolctl 2.1.0 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for joblib==0.14.1
Best match: joblib 0.14.1
Adding joblib 0.14.1 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for typing-extensions==4.1.1
Best match: typing-extensions 4.1.1
Adding typing-extensions 4.1.1 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for zipp==3.7.0
Best match: zipp 3.7.0
Adding zipp 3.7.0 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Searching for MarkupSafe==2.0.1
Best match: MarkupSafe 2.0.1
Adding MarkupSafe 2.0.1 to easy-install.pth file

Using /opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages
Finished processing dependencies for paddledet==2.4.0
二、模型下载
In [5]
#下载检测模型
!wget https://bj.bcebos.com/v1/paddledet/models/pipeline/mot_ppyoloe_l_36e_pipeline.zip

#下载属性模型
!wget https://bj.bcebos.com/v1/paddledet/models/pipeline/strongbaseline_r50_30e_pa100k.zip

#下载关键点模型
!wget https://bj.bcebos.com/v1/paddledet/models/pipeline/dark_hrnet_w32_256x192.zip

#下载行为识别模型
!wget https://bj.bcebos.com/v1/paddledet/models/pipeline/STGCN.zip
--2022-04-13 21:44:36--  https://bj.bcebos.com/v1/paddledet/models/pipeline/mot_ppyoloe_l_36e_pipeline.zip
正在解析主机 bj.bcebos.com (bj.bcebos.com)... 100.67.200.6
正在连接 bj.bcebos.com (bj.bcebos.com)|100.67.200.6|:443... 已连接。
已发出 HTTP 请求，正在等待回应... 200 OK
长度： 190820031 (182M) [application/zip]
正在保存至: “mot_ppyoloe_l_36e_pipeline.zip”

mot_ppyoloe_l_36e_p 100%[===================>] 181.98M   121MB/s    in 1.5s    

2022-04-13 21:44:37 (121 MB/s) - 已保存 “mot_ppyoloe_l_36e_pipeline.zip” [190820031/190820031])

--2022-04-13 21:44:38--  https://bj.bcebos.com/v1/paddledet/models/pipeline/strongbaseline_r50_30e_pa100k.zip
正在解析主机 bj.bcebos.com (bj.bcebos.com)... 100.67.200.6
正在连接 bj.bcebos.com (bj.bcebos.com)|100.67.200.6|:443... 已连接。
已发出 HTTP 请求，正在等待回应... 200 OK
长度： 87757409 (84M) [application/zip]
正在保存至: “strongbaseline_r50_30e_pa100k.zip”

strongbaseline_r50_ 100%[===================>]  83.69M   128MB/s    in 0.7s    

2022-04-13 21:44:38 (128 MB/s) - 已保存 “strongbaseline_r50_30e_pa100k.zip” [87757409/87757409])

--2022-04-13 21:44:39--  https://bj.bcebos.com/v1/paddledet/models/pipeline/dark_hrnet_w32_256x192.zip
正在解析主机 bj.bcebos.com (bj.bcebos.com)... 100.67.200.6
正在连接 bj.bcebos.com (bj.bcebos.com)|100.67.200.6|:443... 已连接。
已发出 HTTP 请求，正在等待回应... 200 OK
长度： 106364080 (101M) [application/zip]
正在保存至: “dark_hrnet_w32_256x192.zip”

dark_hrnet_w32_256x 100%[===================>] 101.44M   122MB/s    in 0.8s    

2022-04-13 21:44:40 (122 MB/s) - 已保存 “dark_hrnet_w32_256x192.zip” [106364080/106364080])

--2022-04-13 21:44:40--  https://bj.bcebos.com/v1/paddledet/models/pipeline/STGCN.zip
正在解析主机 bj.bcebos.com (bj.bcebos.com)... 100.67.200.6
正在连接 bj.bcebos.com (bj.bcebos.com)|100.67.200.6|:443... 已连接。
已发出 HTTP 请求，正在等待回应... 200 OK
长度： 22876940 (22M) [application/zip]
正在保存至: “STGCN.zip”

STGCN.zip           100%[===================>]  21.82M  94.9MB/s    in 0.2s    

2022-04-13 21:44:40 (94.9 MB/s) - 已保存 “STGCN.zip” [22876940/22876940])

In [6]
#解压至./output_inference文件夹
!unzip -d output_inference mot_ppyoloe_l_36e_pipeline.zip
!unzip -d output_inference strongbaseline_r50_30e_pa100k.zip
!unzip -d output_inference dark_hrnet_w32_256x192.zip
!unzip -d output_inference STGCN.zip
Archive:  mot_ppyoloe_l_36e_pipeline.zip
   creating: output_inference/mot_ppyoloe_l_36e_pipeline/
  inflating: output_inference/mot_ppyoloe_l_36e_pipeline/infer_cfg.yml  
  inflating: output_inference/mot_ppyoloe_l_36e_pipeline/model.pdmodel  
  inflating: output_inference/mot_ppyoloe_l_36e_pipeline/model.pdiparams  
  inflating: output_inference/mot_ppyoloe_l_36e_pipeline/model.pdiparams.info  
Archive:  strongbaseline_r50_30e_pa100k.zip
   creating: output_inference/strongbaseline_r50_30e_pa100k/
  inflating: output_inference/__MACOSX/._strongbaseline_r50_30e_pa100k  
  inflating: output_inference/strongbaseline_r50_30e_pa100k/model.pdmodel  
  inflating: output_inference/strongbaseline_r50_30e_pa100k/model.pdiparams.info  
  inflating: output_inference/strongbaseline_r50_30e_pa100k/model.pdiparams  
  inflating: output_inference/strongbaseline_r50_30e_pa100k/infer_cfg.yml  
Archive:  dark_hrnet_w32_256x192.zip
   creating: output_inference/dark_hrnet_w32_256x192/
  inflating: output_inference/dark_hrnet_w32_256x192/infer_cfg.yml  
  inflating: output_inference/dark_hrnet_w32_256x192/model.pdiparams.info  
  inflating: output_inference/dark_hrnet_w32_256x192/model.pdiparams  
  inflating: output_inference/dark_hrnet_w32_256x192/model.pdmodel  
Archive:  STGCN.zip
   creating: output_inference/STGCN/
  inflating: output_inference/STGCN/STGCN.pdiparams.info  
  inflating: output_inference/STGCN/STGCN.pdmodel  
  inflating: output_inference/STGCN/infer_cfg.yml  
  inflating: output_inference/STGCN/model.pdiparams  
  inflating: output_inference/STGCN/model.pdmodel  
  inflating: output_inference/STGCN/STGCN.pdiparams  
三、图片属性分析
In [7]
#图片行人属性识别
!python deploy/pphuman/pipeline.py \
    --config deploy/pphuman/config/infer_cfg.yml \
    --model_dir mot=output_inference/mot_ppyoloe_l_36e_pipeline/ attr=output_inference/strongbaseline_r50_30e_pa100k/ \
    --image_file=/home/aistudio/beatles.jpeg \
    --enable_attr=True \
    --device=gpu
deploy/pphuman/pipeline.py:26: DeprecationWarning: Using or importing the ABCs from 'collections' instead of from 'collections.abc' is deprecated, and in 3.8 it will stop working
  from collections import Sequence
-----------  Running Arguments -----------
ACTION:
  batch_size: 1
  coord_size:
  - 384
  - 512
  display_frames: 80
  max_frames: 50
  model_dir: output_inference/STGCN
ATTR:
  batch_size: 8
  model_dir: output_inference/strongbaseline_r50_30e_pa100k/
DET:
  batch_size: 1
  model_dir: output_inference/mot_ppyoloe_l_36e_pipeline/
KPT:
  batch_size: 8
  model_dir: output_inference/dark_hrnet_w32_256x192/
MOT:
  batch_size: 1
  model_dir: output_inference/mot_ppyoloe_l_36e_pipeline/
  tracker_config: deploy/pphuman/config/tracker_config.yml
REID:
  batch_size: 16
  model_dir: output_inference/reid_model/
attr_thresh: 0.5
crop_thresh: 0.5
kpt_thresh: 0.2
visual: true
warmup_frame: 50

------------------------------------------
Attribute Recognition enabled
-----------  Model Configuration -----------
Model Arch: YOLO
Transform Order: 
--transform op: Resize
--transform op: Permute
--------------------------------------------
-----------  Model Configuration -----------
Model Arch: StrongBaseline
Transform Order: 
--transform op: Resize
--transform op: NormalizeImage
--transform op: Permute
--------------------------------------------
class_id:0, confidence:0.9709, left_top:[165.28,111.02],right_bottom:[288.72,344.02]
class_id:0, confidence:0.9653, left_top:[17.16,110.43],right_bottom:[161.69,356.66]
class_id:0, confidence:0.9629, left_top:[285.92,118.63],right_bottom:[429.37,351.74]
class_id:0, confidence:0.9552, left_top:[425.18,111.36],right_bottom:[566.17,358.13]
save result to: output/beatles.jpeg
------------------ Inference Time Info ----------------------
total_time(ms): 0.0, img_num: 1
average latency time(ms): 0.00, QPS: 0.000000
推理结果：/home/aistudio/.jupyter/lab/workspaces/PaddleDetection/output/beatles.jpeg

In [9]
#展示结果
import matplotlib.pyplot as plt
import matplotlib.image as mpimg 
%matplotlib inline
# 预测结果展示
img = mpimg.imread("/home/aistudio/PaddleDetection/output/beatles.jpeg")
plt.figure(figsize=(5,5))
plt.imshow(img) 
plt.axis('off') 
plt.show()

<Figure size 360x360 with 1 Axes>
四、视频属性分析
In [10]

#视频行人属性识别
!python deploy/pphuman/pipeline.py \
    --config deploy/pphuman/config/infer_cfg.yml \
    --model_dir mot=output_inference/mot_ppyoloe_l_36e_pipeline/ attr=output_inference/strongbaseline_r50_30e_pa100k/ \
    --video_file=/home/aistudio/walkingpeople.mp4 \
    --enable_attr=True \
    --device=gpu
deploy/pphuman/pipeline.py:26: DeprecationWarning: Using or importing the ABCs from 'collections' instead of from 'collections.abc' is deprecated, and in 3.8 it will stop working
  from collections import Sequence
-----------  Running Arguments -----------
ACTION:
  batch_size: 1
  coord_size:
  - 384
  - 512
  display_frames: 80
  max_frames: 50
  model_dir: output_inference/STGCN
ATTR:
  batch_size: 8
  model_dir: output_inference/strongbaseline_r50_30e_pa100k/
DET:
  batch_size: 1
  model_dir: output_inference/mot_ppyoloe_l_36e_pipeline/
KPT:
  batch_size: 8
  model_dir: output_inference/dark_hrnet_w32_256x192/
MOT:
  batch_size: 1
  model_dir: output_inference/mot_ppyoloe_l_36e_pipeline/
  tracker_config: deploy/pphuman/config/tracker_config.yml
REID:
  batch_size: 16
  model_dir: output_inference/reid_model/
attr_thresh: 0.5
crop_thresh: 0.5
kpt_thresh: 0.2
visual: true
warmup_frame: 50

------------------------------------------
Attribute Recognition enabled
-----------  Model Configuration -----------
Model Arch: YOLO
Transform Order: 
--transform op: Resize
--transform op: Permute
--------------------------------------------
-----------  Model Configuration -----------
Model Arch: StrongBaseline
Transform Order: 
--transform op: Resize
--transform op: NormalizeImage
--transform op: Permute
--------------------------------------------
video fps: 30, frame_count: 178
frame id:  0
Frame id: 1, Total count: 8
Frame id: 2, Total count: 8
Frame id: 3, Total count: 8
Frame id: 4, Total count: 8
Frame id: 5, Total count: 8
Frame id: 6, Total count: 8
Frame id: 7, Total count: 8
Frame id: 8, Total count: 9
Frame id: 9, Total count: 10
Frame id: 10, Total count: 10
frame id:  10
Frame id: 11, Total count: 10
Frame id: 12, Total count: 10
Frame id: 13, Total count: 10
Frame id: 14, Total count: 10
Frame id: 15, Total count: 10
Frame id: 16, Total count: 10
Frame id: 17, Total count: 10
Frame id: 18, Total count: 10
Frame id: 19, Total count: 10
Frame id: 20, Total count: 10
frame id:  20
Frame id: 21, Total count: 10
Frame id: 22, Total count: 11
Frame id: 23, Total count: 11
Frame id: 24, Total count: 11
Frame id: 25, Total count: 11
Frame id: 26, Total count: 12
Frame id: 27, Total count: 12
Frame id: 28, Total count: 12
Frame id: 29, Total count: 12
Frame id: 30, Total count: 12
frame id:  30
Frame id: 31, Total count: 12
Frame id: 32, Total count: 12
Frame id: 33, Total count: 12
Frame id: 34, Total count: 12
Frame id: 35, Total count: 12
Frame id: 36, Total count: 12
Frame id: 37, Total count: 12
Frame id: 38, Total count: 14
Frame id: 39, Total count: 14
Frame id: 40, Total count: 14
frame id:  40
Frame id: 41, Total count: 14
Frame id: 42, Total count: 14
Frame id: 43, Total count: 14
Frame id: 44, Total count: 14
Frame id: 45, Total count: 16
Frame id: 46, Total count: 16
Frame id: 47, Total count: 16
Frame id: 48, Total count: 16
Frame id: 49, Total count: 16
Frame id: 50, Total count: 16
frame id:  50
Frame id: 51, Total count: 16
Frame id: 52, Total count: 16
Frame id: 53, Total count: 16
Frame id: 54, Total count: 16
Frame id: 55, Total count: 16
Frame id: 56, Total count: 16
Frame id: 57, Total count: 16
Frame id: 58, Total count: 16
Frame id: 59, Total count: 17
Frame id: 60, Total count: 17, Count during 2 secs: 17
frame id:  60
Frame id: 61, Total count: 17
Frame id: 62, Total count: 17
Frame id: 63, Total count: 17
Frame id: 64, Total count: 17
Frame id: 65, Total count: 17
Frame id: 66, Total count: 17
Frame id: 67, Total count: 17
Frame id: 68, Total count: 17
Frame id: 69, Total count: 17
Frame id: 70, Total count: 17
frame id:  70
Frame id: 71, Total count: 17
Frame id: 72, Total count: 17
Frame id: 73, Total count: 17
Frame id: 74, Total count: 17
Frame id: 75, Total count: 23
Frame id: 76, Total count: 23
Frame id: 77, Total count: 23
Frame id: 78, Total count: 23
Frame id: 79, Total count: 24
Frame id: 80, Total count: 24
frame id:  80
Frame id: 81, Total count: 24
Frame id: 82, Total count: 24
Frame id: 83, Total count: 24
Frame id: 84, Total count: 24
Frame id: 85, Total count: 24
Frame id: 86, Total count: 24
Frame id: 87, Total count: 25
Frame id: 88, Total count: 25
Frame id: 89, Total count: 25
Frame id: 90, Total count: 25
frame id:  90
Frame id: 91, Total count: 25
Frame id: 92, Total count: 25
Frame id: 93, Total count: 25
Frame id: 94, Total count: 25
Frame id: 95, Total count: 25
Frame id: 96, Total count: 25
Frame id: 97, Total count: 25
Frame id: 98, Total count: 25
Frame id: 99, Total count: 26
Frame id: 100, Total count: 26
frame id:  100
Frame id: 101, Total count: 26
Frame id: 102, Total count: 26
Frame id: 103, Total count: 26
Frame id: 104, Total count: 26
Frame id: 105, Total count: 26
Frame id: 106, Total count: 26
Frame id: 107, Total count: 26
Frame id: 108, Total count: 26
Frame id: 109, Total count: 27
Frame id: 110, Total count: 27
frame id:  110
Frame id: 111, Total count: 27
Frame id: 112, Total count: 27
Frame id: 113, Total count: 27
Frame id: 114, Total count: 27
Frame id: 115, Total count: 27
Frame id: 116, Total count: 27
Frame id: 117, Total count: 27
Frame id: 118, Total count: 27
Frame id: 119, Total count: 27
Frame id: 120, Total count: 31, Count during 2 secs: 21
frame id:  120
Frame id: 121, Total count: 31
Frame id: 122, Total count: 31
Frame id: 123, Total count: 31
Frame id: 124, Total count: 31
Frame id: 125, Total count: 31
Frame id: 126, Total count: 31
Frame id: 127, Total count: 31
Frame id: 128, Total count: 31
Frame id: 129, Total count: 31
Frame id: 130, Total count: 31
frame id:  130
Frame id: 131, Total count: 32
Frame id: 132, Total count: 35
Frame id: 133, Total count: 35
Frame id: 134, Total count: 35
Frame id: 135, Total count: 36
Frame id: 136, Total count: 36
Frame id: 137, Total count: 37
Frame id: 138, Total count: 37
Frame id: 139, Total count: 37
Frame id: 140, Total count: 38
frame id:  140
Frame id: 141, Total count: 38
Frame id: 142, Total count: 38
Frame id: 143, Total count: 38
Frame id: 144, Total count: 38
Frame id: 145, Total count: 38
Frame id: 146, Total count: 38
Frame id: 147, Total count: 38
Frame id: 148, Total count: 39
Frame id: 149, Total count: 39
Frame id: 150, Total count: 39
frame id:  150
Frame id: 151, Total count: 39
Frame id: 152, Total count: 39
Frame id: 153, Total count: 39
Frame id: 154, Total count: 39
Frame id: 155, Total count: 39
Frame id: 156, Total count: 39
Frame id: 157, Total count: 39
Frame id: 158, Total count: 39
Frame id: 159, Total count: 39
Frame id: 160, Total count: 39
frame id:  160
Frame id: 161, Total count: 39
Frame id: 162, Total count: 39
Frame id: 163, Total count: 39
Frame id: 164, Total count: 39
Frame id: 165, Total count: 39
Frame id: 166, Total count: 39
Frame id: 167, Total count: 41
Frame id: 168, Total count: 41
Frame id: 169, Total count: 41
Frame id: 170, Total count: 41
frame id:  170
Frame id: 171, Total count: 41
Frame id: 172, Total count: 41
Frame id: 173, Total count: 41
Frame id: 174, Total count: 41
Frame id: 175, Total count: 41
Frame id: 176, Total count: 41
Frame id: 177, Total count: 41
Frame id: 178, Total count: 41
save result to output/walkingpeople.mp4
------------------ Inference Time Info ----------------------
total_time(ms): 12906.3, img_num: 127
mot time(ms): 6306.3
attr time(ms): 6569.3
average latency time(ms): 101.62, QPS: 9.840156
视频检测结果：/home/aistudio/.jupyter/lab/workspaces/PaddleDetection/output/walkingpeople.mp4

五、摔倒检测
In [11]
#摔倒检测
!python deploy/pphuman/pipeline.py \
    --config deploy/pphuman/config/infer_cfg.yml \
    --model_dir mot=output_inference/mot_ppyoloe_l_36e_pipeline/ kpt=output_inference/dark_hrnet_w32_256x192/ action=output_inference/STGCN \
    --video_file=/home/aistudio/小胖摔跤.mp4 \
    --enable_action=True \
    --device=gpu
deploy/pphuman/pipeline.py:26: DeprecationWarning: Using or importing the ABCs from 'collections' instead of from 'collections.abc' is deprecated, and in 3.8 it will stop working
  from collections import Sequence
-----------  Running Arguments -----------
ACTION:
  batch_size: 1
  coord_size:
  - 384
  - 512
  display_frames: 80
  max_frames: 50
  model_dir: output_inference/STGCN
ATTR:
  batch_size: 8
  model_dir: output_inference/strongbaseline_r50_30e_pa100k/
DET:
  batch_size: 1
  model_dir: output_inference/mot_ppyoloe_l_36e_pipeline/
KPT:
  batch_size: 8
  model_dir: output_inference/dark_hrnet_w32_256x192/
MOT:
  batch_size: 1
  model_dir: output_inference/mot_ppyoloe_l_36e_pipeline/
  tracker_config: deploy/pphuman/config/tracker_config.yml
REID:
  batch_size: 16
  model_dir: output_inference/reid_model/
attr_thresh: 0.5
crop_thresh: 0.5
kpt_thresh: 0.2
visual: true
warmup_frame: 50

------------------------------------------
Action Recognition enabled
-----------  Model Configuration -----------
Model Arch: YOLO
Transform Order: 
--transform op: Resize
--transform op: Permute
--------------------------------------------
-----------  Model Configuration -----------
Model Arch: HRNet
Transform Order: 
--transform op: TopDownEvalAffine
--transform op: Permute
--------------------------------------------
-----------  Model Configuration -----------
Model Arch: STGCN
Transform Order: 
--transform op: AutoPadding
--------------------------------------------
video fps: 30, frame_count: 194
frame id:  0
Frame id: 1, Total count: 1
Frame id: 2, Total count: 1
Frame id: 3, Total count: 1
Frame id: 4, Total count: 1
Frame id: 5, Total count: 1
Frame id: 6, Total count: 1
Frame id: 7, Total count: 1
Frame id: 8, Total count: 1
Frame id: 9, Total count: 1
Frame id: 10, Total count: 1
frame id:  10
Frame id: 11, Total count: 1
Frame id: 12, Total count: 1
Frame id: 13, Total count: 1
Frame id: 14, Total count: 1
Frame id: 15, Total count: 1
Frame id: 16, Total count: 1
Frame id: 17, Total count: 1
Frame id: 18, Total count: 1
Frame id: 19, Total count: 1
Frame id: 20, Total count: 1
frame id:  20
Frame id: 21, Total count: 1
Frame id: 22, Total count: 1
Frame id: 23, Total count: 1
Frame id: 24, Total count: 1
Frame id: 25, Total count: 1
Frame id: 26, Total count: 1
Frame id: 27, Total count: 1
Frame id: 28, Total count: 1
Frame id: 29, Total count: 1
Frame id: 30, Total count: 1
frame id:  30
Frame id: 31, Total count: 1
Frame id: 32, Total count: 1
Frame id: 33, Total count: 1
Frame id: 34, Total count: 1
Frame id: 35, Total count: 1
Frame id: 36, Total count: 1
Frame id: 37, Total count: 1
Frame id: 38, Total count: 1
Frame id: 39, Total count: 1
Frame id: 40, Total count: 1
frame id:  40
Frame id: 41, Total count: 1
Frame id: 42, Total count: 1
Frame id: 43, Total count: 1
Frame id: 44, Total count: 1
Frame id: 45, Total count: 1
Frame id: 46, Total count: 1
Frame id: 47, Total count: 1
Frame id: 48, Total count: 1
Frame id: 49, Total count: 1
Frame id: 50, Total count: 1
frame id:  50
Frame id: 51, Total count: 1
Frame id: 52, Total count: 1
Frame id: 53, Total count: 1
Frame id: 54, Total count: 1
Frame id: 55, Total count: 1
Frame id: 56, Total count: 1
Frame id: 57, Total count: 1
Frame id: 58, Total count: 1
Frame id: 59, Total count: 1
Frame id: 60, Total count: 1, Count during 2 secs: 1
frame id:  60
Frame id: 61, Total count: 1
Frame id: 62, Total count: 1
Frame id: 63, Total count: 1
Frame id: 64, Total count: 1
Frame id: 65, Total count: 1
Frame id: 66, Total count: 1
Frame id: 67, Total count: 1
Frame id: 68, Total count: 1
Frame id: 69, Total count: 1
Frame id: 70, Total count: 1
frame id:  70
Frame id: 71, Total count: 1
Frame id: 72, Total count: 1
Frame id: 73, Total count: 1
Frame id: 74, Total count: 1
Frame id: 75, Total count: 1
Frame id: 76, Total count: 1
Frame id: 77, Total count: 1
Frame id: 78, Total count: 1
Frame id: 79, Total count: 1
Frame id: 80, Total count: 1
frame id:  80
Frame id: 81, Total count: 1
Frame id: 82, Total count: 1
Frame id: 83, Total count: 1
Frame id: 84, Total count: 1
Frame id: 85, Total count: 1
Frame id: 86, Total count: 1
Frame id: 87, Total count: 1
Frame id: 88, Total count: 1
Frame id: 89, Total count: 1
Frame id: 90, Total count: 1
frame id:  90
Frame id: 91, Total count: 1
Frame id: 92, Total count: 1
Frame id: 93, Total count: 1
Frame id: 94, Total count: 1
Frame id: 95, Total count: 1
Frame id: 96, Total count: 1
Frame id: 97, Total count: 1
Frame id: 98, Total count: 1
Frame id: 99, Total count: 1
Frame id: 100, Total count: 1
frame id:  100
Frame id: 101, Total count: 1
Frame id: 102, Total count: 1
Frame id: 103, Total count: 1
Frame id: 104, Total count: 1
Frame id: 105, Total count: 1
Frame id: 106, Total count: 1
Frame id: 107, Total count: 1
Frame id: 108, Total count: 1
Frame id: 109, Total count: 1
Frame id: 110, Total count: 1
frame id:  110
Frame id: 111, Total count: 1
Frame id: 112, Total count: 1
Frame id: 113, Total count: 1
Frame id: 114, Total count: 1
Frame id: 115, Total count: 1
Frame id: 116, Total count: 1
Frame id: 117, Total count: 1
Frame id: 118, Total count: 1
Frame id: 119, Total count: 1
Frame id: 120, Total count: 1, Count during 2 secs: 1
frame id:  120
Frame id: 121, Total count: 1
Frame id: 122, Total count: 1
Frame id: 123, Total count: 1
Frame id: 124, Total count: 1
Frame id: 125, Total count: 1
Frame id: 126, Total count: 1
Frame id: 127, Total count: 1
Frame id: 128, Total count: 1
Frame id: 129, Total count: 1
Frame id: 130, Total count: 1
frame id:  130
Frame id: 131, Total count: 1
Frame id: 132, Total count: 1
Frame id: 133, Total count: 1
Frame id: 134, Total count: 1
Frame id: 135, Total count: 1
Frame id: 136, Total count: 1
Frame id: 137, Total count: 1
Frame id: 138, Total count: 1
Frame id: 139, Total count: 1
Frame id: 140, Total count: 1
frame id:  140
Frame id: 141, Total count: 1
Frame id: 142, Total count: 1
Frame id: 143, Total count: 1
Frame id: 144, Total count: 1
Frame id: 145, Total count: 1
Frame id: 146, Total count: 1
Frame id: 147, Total count: 1
Frame id: 148, Total count: 1
Frame id: 149, Total count: 1
Frame id: 150, Total count: 1
frame id:  150
Frame id: 151, Total count: 1
Frame id: 152, Total count: 1
Frame id: 153, Total count: 1
Frame id: 154, Total count: 1
Frame id: 155, Total count: 1
Frame id: 156, Total count: 1
Frame id: 157, Total count: 1
Frame id: 158, Total count: 1
Frame id: 159, Total count: 1
Frame id: 160, Total count: 1
frame id:  160
Frame id: 161, Total count: 1
Frame id: 162, Total count: 1
Frame id: 163, Total count: 1
Frame id: 164, Total count: 1
Frame id: 165, Total count: 1
Frame id: 166, Total count: 1
Frame id: 167, Total count: 1
Frame id: 168, Total count: 1
Frame id: 169, Total count: 1
Frame id: 170, Total count: 1
frame id:  170
Frame id: 171, Total count: 1
Frame id: 172, Total count: 1
Frame id: 173, Total count: 1
Frame id: 174, Total count: 1
Frame id: 175, Total count: 1
Frame id: 176, Total count: 1
Frame id: 177, Total count: 1
Frame id: 178, Total count: 1
Frame id: 179, Total count: 1
Frame id: 180, Total count: 1, Count during 2 secs: 1
frame id:  180
Frame id: 181, Total count: 1
Frame id: 182, Total count: 1
Frame id: 183, Total count: 1
Frame id: 184, Total count: 1
Frame id: 185, Total count: 1
Frame id: 186, Total count: 1
Frame id: 187, Total count: 2
Frame id: 188, Total count: 2
Frame id: 189, Total count: 2
Frame id: 190, Total count: 2
frame id:  190
Frame id: 191, Total count: 2
Frame id: 192, Total count: 2
Frame id: 193, Total count: 2
Frame id: 194, Total count: 2
save result to output/小胖摔跤.mp4
------------------ Inference Time Info ----------------------
total_time(ms): 10074.5, img_num: 143
mot time(ms): 7022.700000000001
kpt time(ms): 3001.1
action time(ms): 28.9
average latency time(ms): 70.45, QPS: 14.194253
请点击此处查看本环境基本用法.
Please click here for more detailed instructions.
