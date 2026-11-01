# my-tensorflow-environment
using for myself  
我从图书馆借了《深度学习程序设计实战》，在踩了许多坑后，我总结了一些安装书中学习环境的经验。我将直接给出配置命令。  
1.安装miniconda，安装时记得勾选环境变量之类的东西，不然后续命令用不了。  
2.输入一堆脚本！  
 - `conda create -n tf114 python=3.6.9 -y`
 - `conda activate tf114`
 - `pip install numpy==1.16.6 h5py==2.10.0 protobuf==3.12.0 -i https://pypi.tuna.tsinghua.edu.cn/simple`
 - `pip install tensorflow==1.14.0 -i https://pypi.tuna.tsinghua.edu.cn/simple`
 - `pip install keras==2.2.4 -i https://pypi.tuna.tsinghua.edu.cn/simple`
3.差不多完成了。如果用vscode，记得ctrl+shift+p，输入python:interpreter，选择正确的python解释器
