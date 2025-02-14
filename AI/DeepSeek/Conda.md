# Conda安装

## Conda、Anaconda和Miniconda的区别

 * Conda：是一个包管理器和环境管理器，可以用于安装和管理软件包和虚拟环境。
 * Anaconda：是一个基于Conda的数据科学发行版，它包含了Conda、Python以及大量的数据科学相关的软件包。Anaconda适合需要完整数据科学栈的用户。
 * Miniconda：是一个轻量级的Anaconda替代品，它只包含Conda、Python和少量必要的软件包。Miniconda适合只需要基础Python环境和Conda管理功能的用户，用户可以根据自己的需要安装其他软件包。

## 安装
 * [Conda](https://docs.conda.io/projects/conda/en/latest/index.html)
 * [miniconda doc](https://docs.anaconda.com/miniconda/)
 * [Miniconda清华镜像](https://mirrors.tuna.tsinghua.edu.cn/anaconda/miniconda/?C=M&O=A)

以下载清华镜像为例，选择自己对应的系统相关文件，比如Linux x86_64, 选择Miniconda3-latest-Linux-x86_64.sh下载
```bash
# 下载相关文件
wget https://mirrors.tuna.tsinghua.edu.cn/anaconda/miniconda/Miniconda3-latest-Linux-x86_64.sh

# 安装
bash Miniconda3-latest-Linux-aarch64.sh

# 安装完成后激活环境变量
source ~/.bashrc

# 查看conda版本
conda --version
```



