# 环境

python项目环境最好隔离，这里推荐使用anconda隔离环境

### 下载

```bash
wget https://repo.anaconda.com/archive/Anaconda3-2020.07-Linux-x86_64.sh
```

```bash
bash Anaconda3-2020.07-Linux-x86_64.sh
```

过程中一直enter

### 激活

一般情况下，anaconda会自动将环境变量添加到PATH里面。（当然，这里说一班情况，那肯定有二班的情况。）如果后面你发现输出conda提示没有该命令，那么你需要手动添加：

1） source ~/.bashrc 这样就是更新环境变量，就可以正常使用了。

2）如果发现这样还是没用，那么需要手动添加环境变量
编辑~/.basrc 文件（通过vim编辑），在最后面加上

```bash
export PATH=/home/XXX/anaconda3/bin:$PATH
```

这里 /home/XXX/anaconda3 是你的anaconda3 保存地址。保存退出后输入命令行指令：source ~/.bashrc
再次输入conda list测试看看，应该就是没有问题啦！

安装后可以查看conda版本和更新conda

```haskell
#查看conda版本
conda --version

#更新conda
conda update conda
```

### base环境的使用

source ～/.bashrc 更新环境变量后，命令行前会出现（base）字样。之后每次进入系统，都会默认进入到该base环境。

如果想取消命令行前出现的base，回到系统原有环境，或者取消每次启动自动激活conda的基础环境，有如下两个方法：

方法一：

每次在命令行通过conda deactivate退出base环境回到系统自带的环境

方法二

1，通过将auto_activate_base参数设置为false实现：

conda config --set auto_activate_base false

2，那要进入的话通过conda activate base

3，如果反悔了还是希望base一直留着的话通过conda config --set auto_activate_base true来恢复

# 虚拟环境配置

安装好Anaconda之后，便可以利用conda命令进行虚拟环境的配置。具体流程及常用操作如下。

1. 新建虚拟环境
   conda create --name <env_name> <package_names>

备注： <env_name>即创建的环境名。建议以英文命名，且不加空格，名称两边不加尖括号“<>”。
<package_names>即安装在环境中的包名。名称两边不加尖括号“<>”。如果要安装指定的版本号，则只需要在包名后面以=和版本号的形式执行。

例如：

conda create --name py36 python=3.6
此时则新建了名为py36的虚拟环境，基于python3.6.

如果要在新创建的环境中创建多个包，则直接在<package_names>后以空格隔开，添加多个包名即可。如：

conda create -n conda-test python=3.6 numpy pandas
即创建一个名为“conda-test ”的环境，环境中安装版本为3.6的python，同时也安装了numpy和pandas。 –name同样可以替换为-n。

2. 切换和退出conda虚拟环境

# 切换conda环境

conda activate env_name

# 退出conda环境

conda deactivate

3. 显示、复制（克隆）、删除虚拟环境
   1） 显示安装过的所有虚拟环境

conda info --envs
或
conda info -e
或
conda env list
2）复制/克隆环境

conda create --name new_env_name --clone copied_env_name
备注：
copied_env_name即为被复制/克隆环境名。

new_env_name即为复制之后新环境的名称。

3）删除环境

conda remove --name env_name --all

4. 在虚拟环境中安装包
   1）在base下指定环境安装包

conda install --name 环境名 要安装的包名
2）进入指定环境后，在当前环境下安装包

# conda安装

conda install 要安装的包名

#pip安装
pip install 安装的包名
