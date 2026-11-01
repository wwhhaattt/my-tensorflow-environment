# my-tensorflow-environment
注：以下命令大量用到清华的镜像源，适合中国国内使用。若不在大陆可尝试把命令末尾的`-i https://pypi.tuna.tsinghua.edu.cn/simple`删掉

初次尝试
=
我从图书馆借了《深度学习程序设计实战》，在踩了许多坑后，我总结了一些安装书中学习环境的经验。我将直接给出配置命令。  
1.安装miniconda，安装时记得**勾选环境变量**之类的东西，不然后续命令用不了。  
2.输入一堆脚本！  
 - `conda create -n tf114 python=3.6.9 -y`
 - `conda activate tf114`
 - `pip install numpy==1.16.6 h5py==2.10.0 protobuf==3.12.0 -i https://pypi.tuna.tsinghua.edu.cn/simple`
 - `pip install tensorflow==1.14.0 -i https://pypi.tuna.tsinghua.edu.cn/simple`
 - `pip install keras==2.2.4 -i https://pypi.tuna.tsinghua.edu.cn/simple`

3.差不多完成了。如果用vscode，记得ctrl+shift+p，输入python:interpreter，选择正确的python解释器。

后记
=
啊呀呀呀呀呀呀呀！当时选择python3.6.9是因为据说兼容性最好，结果现在发现vscode的新版debugpy已经不支持了！所以只能手动降版本。  
 - `conda activate tf114`
 - `pip install "debugpy==1.5.1" -i https://pypi.tuna.tsinghua.edu.cn/simple`
 - 在launch.json加`"debugAdapterPath": "C:\\Users\\用户名\\.conda\\envs\\tf114\\Lib\\site-packages\\debugpy\\adapter"`
代价：1.5.1 是 2022 年的版本，跟 VS Code 1.144 的 DAP 协议有些新特性对不上（个别边缘功能、比如某些数据断点可能不灵），基础断点/单步/变量查看没问题。
也许最佳选择是选择python3.7重装环境，但我实在是累了，就这样凑合用吧😭

后后记
=
阿弥诺斯！我还是忍不住尝试了python3.7.9，结果现在vscode的新版debugpy还是不支持！还是得手动降版本！不过这次至少可以用新一点的版本，与vscode的兼容性问题应该会少一点吧...  
这里贴出配置python3.7.9+tensorflow1.14.0的命令和方法：  
 - `conda create -n tf114 python=3.7.9 -y`
 - `conda activate tf114`
 - `pip install numpy==1.16.6 h5py==2.10.0 protobuf==3.10.0 keras==2.2.4 -i https://pypi.tuna.tsinghua.edu.cn/simple`
 - `pip install tensorflow==1.14.0 -i https://pypi.tuna.tsinghua.edu.cn/simple`
 - 到这里其实已经把环境配好了。接下来的步骤是为了兼容vscode的调试。
 - `conda activate tf114`
 - `pip install "debugpy==1.7.0" -i https://pypi.tuna.tsinghua.edu.cn/simple`
 - 在launch.json加`"debugAdapterPath": "C:\\Users\\用户名\\.conda\\envs\\tf114\\Lib\\site-packages\\debugpy\\adapter"`  
这下应该不会再折腾环境了，要好好学习书里的内容了。
