# Used CNN in NLP
--------------------------------
## [CNN在NLP领域的实践（1） 文本分类](http://lib.csdn.net/article/deeplearning/53863)Sample Code的运行
1. Keras环境安装  
建议使用Ubuntu作为测试环境，Windows环境安装Keras略复杂。  
参考[Keras安装和配置指南(Linux)](https://keras-cn.readthedocs.io/en/latest/getting_started/keras_linux/)  
主要步骤：
  1. 安装python基础开发包<br/>
    >sudo apt install -y python-dev python-pip python-nose gcc g++ git gfortran vim
    
  1. 安装运算加速库<br/>
    >sudo apt install -y libopenblas-dev liblapack-dev libatlas-base-dev<br/>
    
  1. Keras框架搭建, 相关开发包安装<br/>
    > sudo pip install -U --pre pip setuptools wheel<br/>
    > sudo pip install -U --pre numpy scipy matplotlib scikit-learn scikit-image<br/>
    > sudo pip install -U --pre theano<br/>
    > sudo pip install -U --pre keras<br/>
    
  1. Keras环境设置
  
    1. 修改默认keras后端<br/>
      >gedit ~/.keras/keras.json
    
      安装默认使用了theano, 如果不需要更改这一步可以略过。<br/>
    1. 配置theano文件<br/>
      >gedit ~/.theanorc
      
      写入如下内容<br/>
      >[global]<br/>
      >openmp=True<br/>
      >device = cpu<br/>
      >floatX = float32<br/>
      >allow_input_downcast=True<br/>
      >[blas]<br/>
      >ldflags= -lopenblas<br/>
      
  1. 验证keras是否安装成功
  
    在命令行中输入Python命令进入Python变成命令行环境：
   
      > ">>>import keras"
      
    没有报错，那么Keras就已经成功安
