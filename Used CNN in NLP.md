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

1. 准备Sample Code及所需语料、词向量等<br/>
  1. 从github检出代码
  
      >git clone https://github.com/894939677/deeplearning_by_diye.git<br/>
      
  1. 下载语料：http://www.qwone.com/~jason/20Newsgroups/20news-19997.tar.gz<br/>
  1. 下载词向量：http://nlp.stanford.edu/data/glove.6B.zip<br/>
  1. 解压缩语料及词向量文件，形成目录结构如下<br/>
  
    * deeplearning_by_diye/<br/>
      * 20_newsgroups/<br/>
        * ...<br/>
      * glove.6B/<br/>
        * glove.6B.50d.txt<br/>
      * pre_merge_3.py<br/>
      * ...<br/>
      
1. 运行sample code

  进入deeplearning_by_diye目录中运行：  

    >python pre_merge_3.py
    
  Notice: 下载语料的目录名是“20_newsgroup**s**", code中（pre_merge_3.py)读取的语料目录是"20_newsgroup", 需要稍加修改。
