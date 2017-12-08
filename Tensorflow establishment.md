# Tensorflow establishment on server

2017/12/08


## 1 - install anaconda
从师姐那里拷了个Anaconda2的安装包，5.0.0.1版本的，重新安装到自己的目录

```markdown
\home\grz\anaconda2\
```
对应了 `~/.bashrc`中的`PATH`
但是有点后悔没有在home下新建一个programs文件夹=。=用来放所有的程序。

## 2 - create environment
在多次失败和尝试后，拟装python3.6版本的tensorflow。（之前一直报错libcudar.so.7.0找不到，猜想应该是版本不匹配）
于是，先创建一个虚拟环境`tensorflow`

```markdown
# 创建环境
conda create -n tensorflow python=3.6
# 启用虚拟环境Tensorflow
source activate tensorflow
# 关闭环境
source deactivate
# 删除环境
conda remove -n tensorflow --all
```

## 3 - check cuda & cudnn
由于实验室服务器上的cuda和cudnn已经装好了，所以这一步非常省事（幸福o(*￣▽￣*)o

检查了一下，cuda是8.0的，其目录要写在```LD_LIBRARY_PATH```中

## 4 - install tensorflow

最后用的tensorflow安装命令十分简单

```markdown
pip install https://storage.googleapis.com/tensorflow/linux/gpu/tensorflow_gpu-1.0.0-cp36-cp36m-linux_x86_64.whl
```

之后简单测试一下发现装好了=。=

## 5 - assign gpu
分配一个GPU给它，我用了GPU0



```markdown
export CUDA_VISIBLE_DEVICES='0'
```

