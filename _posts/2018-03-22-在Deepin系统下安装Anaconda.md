---
layout: post
title: 在Deepin系统中安装Anaconda
categories: Deepin
description: Deepin安装Anaconda
keywords: Deepin, Anaconda
---
# 在Deepin系统中安装Anaconda
## 运行安装Anaconda
```
bash Anaconda3-4.3.1-Linux-x86_64.sh
```
## 安装具体步骤
在执行上一步骤之后会出现以下：
```
Welcome to Anaconda3 5.0.1

In order to continue the installation process, please review the license
agreement.
Please, press ENTER to continue
>>> 
```
按ENTER继续，然后按ENTER读取许可证。读完许可证后，系统会提示您批准许可条款：
```
Do you accept the license terms? [yes|no]
```
选择yes继续安装
此时，系统将提示您选择安装的位置。您可以按ENTER接受默认位置，或指定其他位置以进行修改。
在这里我选择了其它路径的安装，安装过程需要一些时间
```
[/root/anaconda3] >>> /home/wenbin/anaconda3
PREFIX=/home/wenbin/anaconda3

installing: python-3.6.3-hc9025b9_1 ...
Python 3.6.3 :: Anaconda, Inc.
installing: ca-certificates-2017.08.26-h1d4fec5_0 ...
installing: conda-env-2.6.0-h36134e3_1 ...
installing: intel-openmp-2018.0.0-h15fc484_7 ...
installing: libgcc-ng-7.2.0-h7cc24e2_2 ...
installing: libgfortran-ng-7.2.0-h9f7466a_2 ...
installing: libstdcxx-ng-7.2.0-h7a57d05_2 ...
installing: bzip2-1.0.6-h0376d23_1 ...
installing: expat-2.2.4-hc00ebd1_1 ...
installing: gmp-6.1.2-hb3b607b_0 ...
.......................
```
完成后，您将收到以下输出：
```
installation finished.
Do you wish the installer to prepend the Anaconda3 install location
to PATH in your /root/.bashrc ? [yes|no]
[no] >>> yes
```
键入yes ，以便可以使用conda命令。接下来将看到以下输出：
```
Appending source /home/wenbin/anaconda3/bin/activate to /root/.bashrc
A backup will be made to: /root/.bashrc-anaconda3.bak


For this change to become active, you have to open a new terminal.

Thank you for installing Anaconda3!
```
如果你选择了no，那么你就需要手动的将Anaconda3添加的环境变量当中
请打开文本编辑器并从主目录打开文件.bashrc或.bash_profile。添加该行。
```
export PATH="/<path to anaconda>/bin:$PATH"
```
注意：将``<path-to-anaconda>``替换为安装的anaconda文件的实际路径。
保存文件。如果您打开任何终端窗口，请关闭它们，然后打开一个新窗口。您可能需要重新启动计算机才能使PATH更改生效。

为了激活安装，你应该来源~/.bashrc文件：
```
source ~/.bashrc
```
之后你可以验证你的安装通过使用conda命令，例如与list ：
```
wenbin@wenbin:~$ conda list
# packages in environment at /home/wenbin/anaconda3:
#
_ipyw_jlab_nb_ext_conf    0.1.0            py36he11e457_0  
alabaster                 0.7.10           py36h306e16b_0  
anaconda                  5.0.1            py36hd30a520_1  
anaconda-client           1.6.5            py36h19c0dcd_0  
anaconda-navigator        1.6.9            py36h11ddaaa_0 
..............
```
## 设置Anaconda环境
查看可用的Python解释器版本：
```
conda search "^python$"
```
使用最新版本的Python 3创建一个环境。我们可以通过将版本3分配给python参数来实现。 我们将调用环境my_python ，但是您可能希望为您的环境使用更具描述性的名称，特别是如果您使用环境来访问多个版本的Python。
```
conda create --name my_python python=3
```
通过一下命令来激活环境
```
source activate my_python
```
通过一下命令添加其他包，比如requests
```
conda install --name my_python requests
```