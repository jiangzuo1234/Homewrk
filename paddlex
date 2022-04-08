# 查看工作区文件, 该目录下的变更将会持久保存. 请及时清理不必要的文件, 避免加载过慢.
! pip install paddlex==1.3.11
Looking in indexes: https://pypi.tuna.tsinghua.edu.cn/simple

数据加载

In [2]
# 加载数据
!wget https://bj.bcebos.com/paddlex/examples2/rebar_count/dataset_reinforcing_steel_bar_counting.zip
!unzip dataset_reinforcing_steel_bar_counting.zip
--2022-04-07 15:50:00--  https://bj.bcebos.com/paddlex/examples2/rebar_count/dataset_reinforcing_steel_bar_counting.zip
正在解析主机 bj.bcebos.com (bj.bcebos.com)... 182.61.200.229, 182.61.200.195, 2409:8c04:1001:1002:0:ff:b001:368a
正在连接 bj.bcebos.com (bj.bcebos.com)|182.61.200.229|:443... 已连接。
已发出 HTTP 请求，正在等待回应... 200 OK
长度： 376232294 (359M) [application/octet-stream]
正在保存至: “dataset_reinforcing_steel_bar_counting.zip”

dataset_reinforcing 100%[===================>] 358.80M  39.0MB/s    in 9.7s    

2022-04-07 15:50:10 (36.9 MB/s) - 已保存 “dataset_reinforcing_steel_bar_counting.zip” [376232294/376232294])

Archive:  dataset_reinforcing_steel_bar_counting.zip
   creating: dataset_reinforcing_steel_bar_counting/
  inflating: dataset_reinforcing_steel_bar_counting/.DS_Store  
  inflating: dataset_reinforcing_steel_bar_counting/labels.txt  
   creating: dataset_reinforcing_steel_bar_counting/Annotations/
   creating: dataset_reinforcing_steel_bar_counting/JPEGImages/
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/1E45CAAA.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/3EA15847.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/B109F092.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/EDB2FA69.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/46D2A288.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/02EDEB01.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/01D4FEFB.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/881B376F.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/DCCA8144.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/8654EDAC.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/C7915946.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/A47F943C.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/BB4402AE.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/F8C0AD90.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/BB917D5A.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/E636D4C4.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/256C1DBD.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/07DD5503.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/9F1740D8.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/F1477D62.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/99E783B2.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/603CC53F.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/679C0C8D.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/570D8DA2.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/BA9F0F0D.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/13641B22.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/D2B83E2C.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/C3FCD4A6.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/D0D2EED9.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/CCB5DBEF.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/6000BA04.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/EAAB35B1.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/C03D16D6.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/94DD9B86.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/97652B3F.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/4CF58401.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/0E8C93E4.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/6DA0B6D4.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/.DS_Store  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/F2011360.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/C2871199.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/3ABBD9FD.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/B3C96BEB.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/3C398D0A.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/7B5B8E84.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/4718DA7F.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/F5164D4F.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/9446D773.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/CCF6E9EE.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/98D5984B.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/3BF8EE47.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/ACEA2A10.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/C911FE0A.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/1DFCCF4B.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/1E0FA40B.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/A6F01C78.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/1E5FB1FF.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/AC90DBBB.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/9CC98D4D.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/03CF22F1.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/550E6EB2.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/DFE17F7D.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/ABB2195A.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/2338148B.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/E42F504E.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/4976E3AB.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/162EF44D.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/AD351F54.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/1F68F120.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/000C7C0E.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/E646C7E9.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/2798F642.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/41B2160E.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/5858D941.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/3EB92931.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/8777E599.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/E802A308.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/F5501E38.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/85295B74.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/0B4F3CC3.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/65E9CDC8.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/8509E501.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/8ADCAE58.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/7EBD1524.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/038D7000.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/6B898244.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/727C2F0F.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/147DAD30.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/5A589275.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/8EF392EA.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/92AB4085.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/0BFB817C.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/3A73D147.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/C211CFD4.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/F6E0119D.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/C99C4D23.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/20CC2D44.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/C2A82415.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/A48928D0.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/738E01F9.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/62167111.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/D6378505.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/B3DF643D.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/5BCDAEB8.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/D4C4E4DB.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/67B4B0A2.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/F0779891.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/04BD494B.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/BB32A6B9.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/5A7370CF.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/A3EEA8A1.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/C374F841.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/2FDC9E0E.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/AEF131E0.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/6D51E30D.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/DBA90206.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/1688B30E.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/EB8ECF1A.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/DB8345F7.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/F5129F56.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/18C1A02C.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/6B91D242.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/92A107D5.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/D8146090.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/52575287.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/2C1FC077.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/34AEBFA3.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/E8A7BB7D.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/B4EEFB95.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/CE4841E1.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/3F343E06.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/0C7CB7B9.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/38ED68D2.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/0631BF82.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/9EA71EB4.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/C85E0C57.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/5C94381A.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/A8658634.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/982B1C73.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/3D218F21.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/296A3EA4.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/E46D744F.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/353E85DF.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/8A057EB9.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/49AD1015.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/A49FFA35.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/4B145787.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/898E0058.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/95D0521E.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/A6EE237B.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/C969355E.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/F4CDD578.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/EFE77AB2.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/ED64EFB9.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/8DF7800C.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/469EB470.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/AFD1AE2E.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/08F7E2BB.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/638FA776.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/09B27635.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/D4E8F388.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/5BE19523.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/9D496EBE.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/DEBA2239.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/FE4C5D3F.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/8DE6C059.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/F8656E74.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/C378D66B.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/2A35EC79.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/88292AF2.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/60639D0F.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/0009496A.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/F2179DD4.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/8702EAB5.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/7099AEF0.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/F6309AF1.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/0EDF9500.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/9F1F4BE9.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/C32AC471.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/8DA1B939.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/B9E60B56.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/E6D7C4C8.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/BF5A2B05.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/8D9FAC03.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/6F76366B.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/35346247.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/0EAC74AF.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/66D2893E.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/C06245D1.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/BD968624.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/FAC06BA2.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/840B846E.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/574E9C80.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/4463FA64.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/2723542B.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/0EED02C3.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/DD6C6F82.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/4FA1275D.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/452A534A.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/926A4C0C.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/474BD568.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/A1A37A49.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/1594D4CC.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/B943B927.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/E05ABCF0.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/EAC26CCD.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/1B82FF85.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/9538AC60.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/36A7E5D4.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/8E24C2B6.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/554F4CE0.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/DF9DBCB9.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/8BD7A993.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/8128955A.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/046F4967.xml  
  inflating: dataset_reinforcing_steel_bar_counting/Annotations/C39C9B97.xml  

  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/DEBA2239.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/9D496EBE.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/5BE19523.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/D4E8F388.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/F8656E74.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/FE4C5D3F.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/8DE6C059.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/C378D66B.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/88292AF2.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/2A35EC79.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/F2179DD4.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/0009496A.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/60639D0F.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/8702EAB5.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/F6309AF1.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/7099AEF0.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/C32AC471.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/8DA1B939.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/9F1F4BE9.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/0EDF9500.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/B9E60B56.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/E6D7C4C8.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/BF5A2B05.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/6F76366B.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/8D9FAC03.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/35346247.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/66D2893E.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/0EAC74AF.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/574E9C80.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/840B846E.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/FAC06BA2.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/BD968624.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/C06245D1.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/4463FA64.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/2723542B.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/0EED02C3.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/4FA1275D.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/DD6C6F82.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/926A4C0C.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/452A534A.jpg  

  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/7E0BEC70.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/2E15279D.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/41CF3100.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/F766C97D.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/2A7090FC.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/54CE2153.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/C1F90358.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/9BC2B7EC.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/3794BD4B.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/CD496125.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/2E197EF1.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/408EAD06.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/52CC0B19.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/08923C9F.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/9D46BC0C.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/9D66CF7D.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/8343D02C.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/FCE7645C.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/21B83F9D.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/4D3BE5D5.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/B7DC39A4.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/0492570A.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/3BA38AEA.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/57CC2B0B.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/CC61344D.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/B905D0AB.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/A2A2E11D.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/7421D3CD.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/BFC85CA0.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/720333BC.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/1099EFCE.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/1EFC66A0.jpg  
  inflating: dataset_reinforcing_steel_bar_counting/JPEGImages/88C4F6E4.jpg  
  
使用gpu训练

In [3]
# 设置使用0号GPU卡（如无GPU，执行此代码后仍然会使用CPU训练模型）
import matplotlib
matplotlib.use('Agg') 
import os
os.environ['CUDA_VISIBLE_DEVICES'] = '0'
数据增强处理

In [4]
# 定义数据处理模块
from paddlex.det import transforms
import paddlex as pdx
train_transforms = transforms.Compose([
    transforms.MixupImage(mixup_epoch=-1),
    transforms.RandomDistort(),
    transforms.RandomExpand(),
    transforms.RandomCrop(),
    transforms.Resize(
        target_size=480, interp='RANDOM'),
    transforms.RandomHorizontalFlip(),
    transforms.Normalize(),
])

eval_transforms = transforms.Compose([
    transforms.Resize(
        target_size=480, interp='CUBIC'),
    transforms.Normalize(),
])
In [5]
# 划分数据集
!paddlex --split_dataset --format VOC --dataset_dir dataset_reinforcing_steel_bar_counting --val_value 0.2 --test_value 0.1
Dataset Split Done.
Train samples: 175
Eval samples: 50
Test samples: 25
Split files saved in dataset_reinforcing_steel_bar_counting
In [6]
# 定义训练和验证所需的数据集 
train_dataset = pdx.datasets.VOCDetection(
    data_dir='dataset_reinforcing_steel_bar_counting',
    file_list='dataset_reinforcing_steel_bar_counting/train_list.txt',
    label_list='dataset_reinforcing_steel_bar_counting/labels.txt',
    transforms=train_transforms,
    shuffle=True)

eval_dataset = pdx.datasets.VOCDetection(
    data_dir='dataset_reinforcing_steel_bar_counting',
    file_list='dataset_reinforcing_steel_bar_counting/val_list.txt',
    label_list='dataset_reinforcing_steel_bar_counting/labels.txt',
    transforms=eval_transforms,
    shuffle=False)
2022-04-07 15:50:16 [INFO]	Starting to read file list from dataset...
2022-04-07 15:50:27 [INFO]	175 samples in file dataset_reinforcing_steel_bar_counting/train_list.txt
creating index...
index created!
2022-04-07 15:50:27 [INFO]	Starting to read file list from dataset...
2022-04-07 15:50:30 [INFO]	50 samples in file dataset_reinforcing_steel_bar_counting/val_list.txt
creating index...
index created!
训练，此处backbone替换为RestNet3*

In [7]
#初始化模型并进行训练
num_classes = len(train_dataset.labels)
model = pdx.det.YOLOv3(num_classes=num_classes, backbone='ResNet34', label_smooth=True, ignore_threshold=0.7)

model.train(
    num_epochs=10,                      # 训练轮次
    train_dataset=train_dataset,         # 训练数据
    eval_dataset=eval_dataset,           # 验证数据
    train_batch_size=2,                  # 批大小
    pretrain_weights='COCO',             # 预训练权重
    learning_rate=0.000125,              # 学习率
    warmup_steps=1000,                   # 预热步数
    warmup_start_lr=0.0,                 # 预热起始学习率
    save_interval_epochs=5,              # 每5个轮次保存一次，有验证数据时，自动评估
    lr_decay_epochs=[210, 240],          # step学习率衰减
    save_dir='output/yolov3_ResNet34', # 保存路径
    use_vdl=True)                        # 其用visuadl进行可视化训练记录
2022-04-07 15:50:32 [INFO]	Downloading yolov3_r34.tar from https://paddlemodels.bj.bcebos.com/object_detection/yolov3_r34.tar
100%|██████████| 165690/165690 [00:03<00:00, 47246.40KB/s]
2022-04-07 15:50:36 [INFO]	Decompressing output/yolov3_ResNet34/pretrain/yolov3_r34.tar...
W0407 15:50:36.414028  2500 device_context.cc:447] Please NOTE: device: 0, GPU Compute Capability: 7.0, Driver API Version: 10.1, Runtime API Version: 10.1
W0407 15:50:36.419672  2500 device_context.cc:465] device: 0, cuDNN Version: 7.6.
2022-04-07 15:50:40 [INFO]	Load pretrain weights from output/yolov3_ResNet34/pretrain/yolov3_r34.
2022-04-07 15:50:40 [WARNING]	[SKIP] Shape of pretrained weight output/yolov3_ResNet34/pretrain/yolov3_r34/yolo_output.0.conv.weights doesn't match.(Pretrained: (255, 1024, 1, 1), Actual: (18, 1024, 1, 1))
2022-04-07 15:50:40 [WARNING]	[SKIP] Shape of pretrained weight output/yolov3_ResNet34/pretrain/yolov3_r34/yolo_output.0.conv.bias doesn't match.(Pretrained: (255,), Actual: (18,))
2022-04-07 15:50:40 [WARNING]	[SKIP] Shape of pretrained weight output/yolov3_ResNet34/pretrain/yolov3_r34/yolo_output.1.conv.weights doesn't match.(Pretrained: (255, 512, 1, 1), Actual: (18, 512, 1, 1))
2022-04-07 15:50:40 [WARNING]	[SKIP] Shape of pretrained weight output/yolov3_ResNet34/pretrain/yolov3_r34/yolo_output.1.conv.bias doesn't match.(Pretrained: (255,), Actual: (18,))
2022-04-07 15:50:40 [WARNING]	[SKIP] Shape of pretrained weight output/yolov3_ResNet34/pretrain/yolov3_r34/yolo_output.2.conv.weights doesn't match.(Pretrained: (255, 256, 1, 1), Actual: (18, 256, 1, 1))
2022-04-07 15:50:40 [WARNING]	[SKIP] Shape of pretrained weight output/yolov3_ResNet34/pretrain/yolov3_r34/yolo_output.2.conv.bias doesn't match.(Pretrained: (255,), Actual: (18,))
2022-04-07 15:50:41 [INFO]	There are 285 varaibles in output/yolov3_ResNet34/pretrain/yolov3_r34 are loaded.
2022-04-07 15:50:52 [INFO]	[TRAIN] Epoch=1/10, Step=2/87, loss=10682.856445, lr=0.0, time_each_step=5.35s, eta=1:21:46
2022-04-07 15:50:53 [INFO]	[TRAIN] Epoch=1/10, Step=4/87, loss=7027.673828, lr=0.0, time_each_step=2.92s, eta=0:44:36
2022-04-07 15:50:55 [INFO]	[TRAIN] Epoch=1/10, Step=6/87, loss=8562.766602, lr=1e-06, time_each_step=2.31s, eta=0:35:14
2022-04-07 15:51:00 [INFO]	[TRAIN] Epoch=1/10, Step=8/87, loss=2972.757812, lr=1e-06, time_each_step=2.34s, eta=0:35:30
2022-04-07 15:51:05 [INFO]	[TRAIN] Epoch=1/10, Step=10/87, loss=3296.901611, lr=1e-06, time_each_step=2.38s, eta=0:36:5
2022-04-07 15:51:07 [INFO]	[TRAIN] Epoch=1/10, Step=12/87, loss=1916.642578, lr=1e-06, time_each_step=2.17s, eta=0:32:53
2022-04-07 15:51:10 [INFO]	[TRAIN] Epoch=1/10, Step=14/87, loss=1719.550171, lr=2e-06, time_each_step=2.03s, eta=0:30:36
2022-04-07 15:51:12 [INFO]	[TRAIN] Epoch=1/10, Step=16/87, loss=1444.47168, lr=2e-06, time_each_step=1.9s, eta=0:28:42
2022-04-07 15:51:14 [INFO]	[TRAIN] Epoch=1/10, Step=18/87, loss=873.693176, lr=2e-06, time_each_step=1.85s, eta=0:27:48
2022-04-07 15:51:19 [INFO]	[TRAIN] Epoch=1/10, Step=20/87, loss=917.661987, lr=2e-06, time_each_step=1.9s, eta=0:28:33
2022-04-07 15:51:21 [INFO]	[TRAIN] Epoch=1/10, Step=22/87, loss=688.934204, lr=3e-06, time_each_step=1.44s, eta=0:21:33
2022-04-07 15:51:23 [INFO]	[TRAIN] Epoch=1/10, Step=24/87, loss=678.630615, lr=3e-06, time_each_step=1.53s, eta=0:22:50
2022-04-07 15:51:25 [INFO]	[TRAIN] Epoch=1/10, Step=26/87, loss=742.062622, lr=3e-06, time_each_step=1.5s, eta=0:22:21
2022-04-07 15:51:28 [INFO]	[TRAIN] Epoch=1/10, Step=28/87, loss=615.0354, lr=3e-06, time_each_step=1.41s, eta=0:20:53
2022-04-07 15:51:29 [INFO]	[TRAIN] Epoch=1/10, Step=30/87, loss=395.344238, lr=4e-06, time_each_step=1.22s, eta=0:18:9
2022-04-07 15:51:32 [INFO]	[TRAIN] Epoch=1/10, Step=32/87, loss=575.938049, lr=4e-06, time_each_step=1.26s, eta=0:18:34
2022-04-07 15:51:35 [INFO]	[TRAIN] Epoch=1/10, Step=34/87, loss=687.855835, lr=4e-06, time_each_step=1.25s, eta=0:18:27
2022-04-07 15:51:37 [INFO]	[TRAIN] Epoch=1/10, Step=36/87, loss=551.354797, lr=4e-06, time_each_step=1.26s, eta=0:18:29
2022-04-07 15:51:39 [INFO]	[TRAIN] Epoch=1/10, Step=38/87, loss=503.363007, lr=5e-06, time_each_step=1.21s, eta=0:17:51
2022-04-07 15:51:41 [INFO]	[TRAIN] Epoch=1/10, Step=40/87, loss=673.19751, lr=5e-06, time_each_step=1.1s, eta=0:16:7
2022-04-07 15:51:43 [INFO]	[TRAIN] Epoch=1/10, Step=42/87, loss=646.458435, lr=5e-06, time_each_step=1.12s, eta=0:16:27
2022-04-07 15:51:48 [INFO]	[TRAIN] Epoch=1/10, Step=44/87, loss=472.060883, lr=5e-06, time_each_step=1.24s, eta=0:18:1
2022-04-07 15:51:49 [INFO]	[TRAIN] Epoch=1/10, Step=46/87, loss=529.631165, lr=6e-06, time_each_step=1.22s, eta=0:17:45
2022-04-07 15:51:53 [INFO]	[TRAIN] Epoch=1/10, Step=48/87, loss=559.429199, lr=6e-06, time_each_step=1.26s, eta=0:18:18
2022-04-07 15:51:56 [INFO]	[TRAIN] Epoch=1/10, Step=50/87, loss=493.07135, lr=6e-06, time_each_step=1.34s, eta=0:19:30
2022-04-07 15:51:59 [INFO]	[TRAIN] Epoch=1/10, Step=52/87, loss=518.146729, lr=6e-06, time_each_step=1.35s, eta=0:19:32
2022-04-07 15:52:03 [INFO]	[TRAIN] Epoch=1/10, Step=54/87, loss=535.271423, lr=7e-06, time_each_step=1.41s, eta=0:20:21
2022-04-07 15:52:05 [INFO]	[TRAIN] Epoch=1/10, Step=56/87, loss=475.007141, lr=7e-06, time_each_step=1.42s, eta=0:20:26
2022-04-07 15:52:07 [INFO]	[TRAIN] Epoch=1/10, Step=58/87, loss=480.834656, lr=7e-06, time_each_step=1.42s, eta=0:20:24
2022-04-07 15:52:10 [INFO]	[TRAIN] Epoch=1/10, Step=60/87, loss=250.369415, lr=7e-06, time_each_step=1.45s, eta=0:20:46
2022-04-07 15:52:14 [INFO]	[TRAIN] Epoch=1/10, Step=62/87, loss=497.982971, lr=8e-06, time_each_step=1.55s, eta=0:22:10
2022-04-07 15:52:17 [INFO]	[TRAIN] Epoch=1/10, Step=64/87, loss=395.609131, lr=8e-06, time_each_step=1.44s, eta=0:20:33
2022-04-07 15:52:20 [INFO]	[TRAIN] Epoch=1/10, Step=66/87, loss=356.686218, lr=8e-06, time_each_step=1.51s, eta=0:21:25
2022-04-07 15:52:24 [INFO]	[TRAIN] Epoch=1/10, Step=68/87, loss=359.893097, lr=8e-06, time_each_step=1.54s, eta=0:21:48
2022-04-07 15:52:25 [INFO]	[TRAIN] Epoch=1/10, Step=70/87, loss=392.012054, lr=9e-06, time_each_step=1.45s, eta=0:20:32
2022-04-07 15:52:30 [INFO]	[TRAIN] Epoch=1/10, Step=72/87, loss=429.690674, lr=9e-06, time_each_step=1.53s, eta=0:21:37
2022-04-07 15:52:32 [INFO]	[TRAIN] Epoch=1/10, Step=74/87, loss=339.331818, lr=9e-06, time_each_step=1.47s, eta=0:20:43
2022-04-07 15:52:36 [INFO]	[TRAIN] Epoch=1/10, Step=76/87, loss=354.362274, lr=9e-06, time_each_step=1.56s, eta=0:21:52

2022-04-07 16:09:29 [INFO]	[TRAIN] Epoch=9/10, Step=42/87, loss=260.693787, lr=9.2e-05, time_each_step=1.31s, eta=0:3:25
2022-04-07 16:09:35 [INFO]	[TRAIN] Epoch=9/10, Step=44/87, loss=295.062195, lr=9.2e-05, time_each_step=1.37s, eta=0:3:25
2022-04-07 16:09:36 [INFO]	[TRAIN] Epoch=9/10, Step=46/87, loss=245.189117, lr=9.3e-05, time_each_step=1.39s, eta=0:3:23
2022-04-07 16:09:41 [INFO]	[TRAIN] Epoch=9/10, Step=48/87, loss=283.830536, lr=9.3e-05, time_each_step=1.46s, eta=0:3:23
2022-04-07 16:09:45 [INFO]	[TRAIN] Epoch=9/10, Step=50/87, loss=222.844223, lr=9.3e-05, time_each_step=1.51s, eta=0:3:22
2022-04-07 16:09:47 [INFO]	[TRAIN] Epoch=9/10, Step=52/87, loss=226.690613, lr=9.3e-05, time_each_step=1.56s, eta=0:3:21
2022-04-07 16:09:50 [INFO]	[TRAIN] Epoch=9/10, Step=54/87, loss=301.434845, lr=9.4e-05, time_each_step=1.5s, eta=0:3:16
2022-04-07 16:09:54 [INFO]	[TRAIN] Epoch=9/10, Step=56/87, loss=234.613968, lr=9.4e-05, time_each_step=1.63s, eta=0:3:17
2022-04-07 16:09:57 [INFO]	[TRAIN] Epoch=9/10, Step=58/87, loss=304.456238, lr=9.4e-05, time_each_step=1.67s, eta=0:3:15
2022-04-07 16:09:59 [INFO]	[TRAIN] Epoch=9/10, Step=60/87, loss=241.465668, lr=9.4e-05, time_each_step=1.63s, eta=0:3:10
2022-04-07 16:10:02 [INFO]	[TRAIN] Epoch=9/10, Step=62/87, loss=337.345032, lr=9.5e-05, time_each_step=1.65s, eta=0:3:8
2022-04-07 16:10:06 [INFO]	[TRAIN] Epoch=9/10, Step=64/87, loss=307.073914, lr=9.5e-05, time_each_step=1.52s, eta=0:3:1
2022-04-07 16:10:09 [INFO]	[TRAIN] Epoch=9/10, Step=66/87, loss=292.109497, lr=9.5e-05, time_each_step=1.63s, eta=0:3:0
2022-04-07 16:10:11 [INFO]	[TRAIN] Epoch=9/10, Step=68/87, loss=271.787231, lr=9.5e-05, time_each_step=1.49s, eta=0:2:54
2022-04-07 16:10:13 [INFO]	[TRAIN] Epoch=9/10, Step=70/87, loss=212.66478, lr=9.6e-05, time_each_step=1.41s, eta=0:2:50
2022-04-07 16:10:16 [INFO]	[TRAIN] Epoch=9/10, Step=72/87, loss=260.644928, lr=9.6e-05, time_each_step=1.48s, eta=0:2:48
2022-04-07 16:10:18 [INFO]	[TRAIN] Epoch=9/10, Step=74/87, loss=279.683411, lr=9.6e-05, time_each_step=1.41s, eta=0:2:44
2022-04-07 16:10:23 [INFO]	[TRAIN] Epoch=9/10, Step=76/87, loss=318.560699, lr=9.6e-05, time_each_step=1.44s, eta=0:2:42
2022-04-07 16:10:27 [INFO]	[TRAIN] Epoch=9/10, Step=78/87, loss=289.151917, lr=9.7e-05, time_each_step=1.52s, eta=0:2:40
2022-04-07 16:10:29 [INFO]	[TRAIN] Epoch=9/10, Step=80/87, loss=311.072784, lr=9.7e-05, time_each_step=1.5s, eta=0:2:37
2022-04-07 16:10:33 [INFO]	[TRAIN] Epoch=9/10, Step=82/87, loss=279.553375, lr=9.7e-05, time_each_step=1.51s, eta=0:2:34
2022-04-07 16:10:37 [INFO]	[TRAIN] Epoch=9/10, Step=84/87, loss=252.225555, lr=9.7e-05, time_each_step=1.57s, eta=0:2:31
2022-04-07 16:10:41 [INFO]	[TRAIN] Epoch=9/10, Step=86/87, loss=266.879303, lr=9.8e-05, time_each_step=1.6s, eta=0:2:28
2022-04-07 16:10:42 [INFO]	[TRAIN] Epoch 9 finished, loss=281.209778, lr=9.2e-05 .
2022-04-07 16:10:50 [INFO]	[TRAIN] Epoch=10/10, Step=1/87, loss=417.67865, lr=9.8e-05, time_each_step=1.91s, eta=0:3:0
2022-04-07 16:10:51 [INFO]	[TRAIN] Epoch=10/10, Step=3/87, loss=421.255371, lr=9.8e-05, time_each_step=1.85s, eta=0:2:52
2022-04-07 16:10:53 [INFO]	[TRAIN] Epoch=10/10, Step=5/87, loss=307.59903, lr=9.8e-05, time_each_step=1.79s, eta=0:2:43
2022-04-07 16:10:55 [INFO]	[TRAIN] Epoch=10/10, Step=7/87, loss=176.800507, lr=9.9e-05, time_each_step=1.83s, eta=0:2:42
2022-04-07 16:10:57 [INFO]	[TRAIN] Epoch=10/10, Step=9/87, loss=281.249634, lr=9.9e-05, time_each_step=1.7s, eta=0:2:28
2022-04-07 16:11:01 [INFO]	[TRAIN] Epoch=10/10, Step=11/87, loss=368.303802, lr=9.9e-05, time_each_step=1.63s, eta=0:2:20
2022-04-07 16:11:04 [INFO]	[TRAIN] Epoch=10/10, Step=13/87, loss=291.787292, lr=9.9e-05, time_each_step=1.69s, eta=0:2:21
2022-04-07 16:11:06 [INFO]	[TRAIN] Epoch=10/10, Step=15/87, loss=284.001221, lr=0.0001, time_each_step=1.62s, eta=0:2:13
2022-04-07 16:11:09 [INFO]	[TRAIN] Epoch=10/10, Step=17/87, loss=226.374619, lr=0.0001, time_each_step=1.57s, eta=0:2:6
2022-04-07 16:11:12 [INFO]	[TRAIN] Epoch=10/10, Step=19/87, loss=321.287262, lr=0.0001, time_each_step=1.54s, eta=0:2:1
2022-04-07 16:11:15 [INFO]	[TRAIN] Epoch=10/10, Step=21/87, loss=313.046448, lr=0.0001, time_each_step=1.25s, eta=0:1:39
2022-04-07 16:11:18 [INFO]	[TRAIN] Epoch=10/10, Step=23/87, loss=325.471436, lr=0.000101, time_each_step=1.35s, eta=0:1:42
2022-04-07 16:11:20 [INFO]	[TRAIN] Epoch=10/10, Step=25/87, loss=312.86853, lr=0.000101, time_each_step=1.37s, eta=0:1:41
2022-04-07 16:11:23 [INFO]	[TRAIN] Epoch=10/10, Step=27/87, loss=312.809387, lr=0.000101, time_each_step=1.38s, eta=0:1:39
2022-04-07 16:11:25 [INFO]	[TRAIN] Epoch=10/10, Step=29/87, loss=317.167267, lr=0.000101, time_each_step=1.4s, eta=0:1:37
2022-04-07 16:11:27 [INFO]	[TRAIN] Epoch=10/10, Step=31/87, loss=217.029541, lr=0.000102, time_each_step=1.34s, eta=0:1:31
2022-04-07 16:11:28 [INFO]	[TRAIN] Epoch=10/10, Step=33/87, loss=185.123322, lr=0.000102, time_each_step=1.22s, eta=0:1:22
2022-04-07 16:11:31 [INFO]	[TRAIN] Epoch=10/10, Step=35/87, loss=307.941467, lr=0.000102, time_each_step=1.26s, eta=0:1:22
2022-04-07 16:11:33 [INFO]	[TRAIN] Epoch=10/10, Step=37/87, loss=307.858948, lr=0.000102, time_each_step=1.2s, eta=0:1:16
2022-04-07 16:11:36 [INFO]	[TRAIN] Epoch=10/10, Step=39/87, loss=310.233704, lr=0.000103, time_each_step=1.18s, eta=0:1:13
2022-04-07 16:11:39 [INFO]	[TRAIN] Epoch=10/10, Step=41/87, loss=230.776367, lr=0.000103, time_each_step=1.19s, eta=0:1:11
2022-04-07 16:11:42 [INFO]	[TRAIN] Epoch=10/10, Step=43/87, loss=236.810211, lr=0.000103, time_each_step=1.19s, eta=0:1:8
2022-04-07 16:11:44 [INFO]	[TRAIN] Epoch=10/10, Step=45/87, loss=258.301758, lr=0.000103, time_each_step=1.19s, eta=0:1:6
2022-04-07 16:11:47 [INFO]	[TRAIN] Epoch=10/10, Step=47/87, loss=273.026215, lr=0.000104, time_each_step=1.21s, eta=0:1:4
2022-04-07 16:11:49 [INFO]	[TRAIN] Epoch=10/10, Step=49/87, loss=172.751022, lr=0.000104, time_each_step=1.2s, eta=0:1:2
2022-04-07 16:11:51 [INFO]	[TRAIN] Epoch=10/10, Step=51/87, loss=172.933075, lr=0.000104, time_each_step=1.18s, eta=0:0:59
2022-04-07 16:11:54 [INFO]	[TRAIN] Epoch=10/10, Step=53/87, loss=188.870728, lr=0.000104, time_each_step=1.29s, eta=0:1:0
2022-04-07 16:11:57 [INFO]	[TRAIN] Epoch=10/10, Step=55/87, loss=285.409424, lr=0.000105, time_each_step=1.31s, eta=0:0:58
2022-04-07 16:12:01 [INFO]	[TRAIN] Epoch=10/10, Step=57/87, loss=209.884979, lr=0.000105, time_each_step=1.38s, eta=0:0:58
2022-04-07 16:12:05 [INFO]	[TRAIN] Epoch=10/10, Step=59/87, loss=146.096481, lr=0.000105, time_each_step=1.46s, eta=0:0:57
2022-04-07 16:12:08 [INFO]	[TRAIN] Epoch=10/10, Step=61/87, loss=292.788727, lr=0.000105, time_each_step=1.49s, eta=0:0:55
2022-04-07 16:12:11 [INFO]	[TRAIN] Epoch=10/10, Step=63/87, loss=148.518738, lr=0.000106, time_each_step=1.46s, eta=0:0:51
2022-04-07 16:12:15 [INFO]	[TRAIN] Epoch=10/10, Step=65/87, loss=261.051483, lr=0.000106, time_each_step=1.56s, eta=0:0:50
2022-04-07 16:12:19 [INFO]	[TRAIN] Epoch=10/10, Step=67/87, loss=229.439514, lr=0.000106, time_each_step=1.58s, eta=0:0:48
2022-04-07 16:12:23 [INFO]	[TRAIN] Epoch=10/10, Step=69/87, loss=255.530869, lr=0.000106, time_each_step=1.68s, eta=0:0:46
2022-04-07 16:12:27 [INFO]	[TRAIN] Epoch=10/10, Step=71/87, loss=235.853699, lr=0.000107, time_each_step=1.78s, eta=0:0:45
2022-04-07 16:12:28 [INFO]	[TRAIN] Epoch=10/10, Step=73/87, loss=312.567902, lr=0.000107, time_each_step=1.71s, eta=0:0:40
2022-04-07 16:12:31 [INFO]	[TRAIN] Epoch=10/10, Step=75/87, loss=282.65097, lr=0.000107, time_each_step=1.67s, eta=0:0:36
2022-04-07 16:12:33 [INFO]	[TRAIN] Epoch=10/10, Step=77/87, loss=254.448868, lr=0.000107, time_each_step=1.59s, eta=0:0:32
2022-04-07 16:12:35 [INFO]	[TRAIN] Epoch=10/10, Step=79/87, loss=298.261536, lr=0.000108, time_each_step=1.5s, eta=0:0:28
2022-04-07 16:12:38 [INFO]	[TRAIN] Epoch=10/10, Step=81/87, loss=316.754517, lr=0.000108, time_each_step=1.49s, eta=0:0:25
2022-04-07 16:12:41 [INFO]	[TRAIN] Epoch=10/10, Step=83/87, loss=289.572021, lr=0.000108, time_each_step=1.5s, eta=0:0:22
2022-04-07 16:12:43 [INFO]	[TRAIN] Epoch=10/10, Step=85/87, loss=314.332031, lr=0.000108, time_each_step=1.39s, eta=0:0:19
2022-04-07 16:12:45 [INFO]	[TRAIN] Epoch=10/10, Step=87/87, loss=237.739395, lr=0.000109, time_each_step=1.33s, eta=0:0:16
2022-04-07 16:12:46 [INFO]	[TRAIN] Epoch 10 finished, loss=265.321045, lr=0.000103 .
2022-04-07 16:12:46 [INFO]	Start to evaluating(total_samples=50, total_steps=25)...
100%|██████████| 25/25 [00:09<00:00,  2.77it/s]
2022-04-07 16:12:56 [INFO]	[EVAL] Finished, Epoch=10, bbox_map=54.451859 .
2022-04-07 16:12:59 [INFO]	Model saved in output/yolov3_ResNet34/best_model.
2022-04-07 16:13:00 [INFO]	Model saved in output/yolov3_ResNet34/epoch_10.
2022-04-07 16:13:00 [INFO]	Current evaluated best model in eval_dataset is epoch_10, bbox_map=54.4518594330016
In [8]
import glob
import numpy as np
import threading
import time
import random
import os
import base64
import cv2
import json
import paddlex as pdx

image_name = 'dataset_reinforcing_steel_bar_counting/JPEGImages/02B90DB7.jpg'

model = pdx.load_model('output/yolov3_ResNet34/best_model')

img = cv2.imread(image_name)
result = model.predict(img)

keep_results = []
areas = []
f = open('result.txt','a')
count = 0
for dt in np.array(result):
    cname, bbox, score = dt['category'], dt['bbox'], dt['score']
    if score < 0.5:
        continue
    keep_results.append(dt)
    count+=1
    f.write(str(dt)+'\n')
    f.write('\n')
    areas.append(bbox[2] * bbox[3])
areas = np.asarray(areas)
sorted_idxs = np.argsort(-areas).tolist()
keep_results = [keep_results[k]
                for k in sorted_idxs] if len(keep_results) > 0 else []
print(keep_results)
print(count)
f.write("the total number is :"+str(int(count)))
f.close()
# 可视化保存
pdx.det.visualize(image_name, result, threshold=0.5, save_dir='./output/ResNet34')
2022-04-07 16:13:01 [INFO]	Model[YOLOv3] loaded.
[{'category_id': 0, 'bbox': [1958.9007568359375, 1030.212158203125, 106.0797119140625, 121.240966796875], 'score': 0.5277771353721619, 'category': 'rebar'}]
1
/opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages/matplotlib/cbook/__init__.py:2349: DeprecationWarning: Using or importing the ABCs from 'collections' instead of from 'collections.abc' is deprecated, and in 3.8 it will stop working
  if isinstance(obj, collections.Iterator):
2022-04-07 16:13:02 [INFO]	The visualized result is saved as ./output/ResNet34/visualize_02B90DB7.jpg
1649319236648.jpg

In [ ]
请点击此处查看本环境基本用法.
Please click here for more detailed instructions.
