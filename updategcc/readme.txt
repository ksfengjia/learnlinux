how to update gcc,g++,gfortran:

参考网址: http://www.linuxidc.com/Linux/2016-11/136840.htm


1.添加源
添加toolchain/test下的ppa到库：
sudo add-apt-repository ppa:ubuntu-toolchain-r/test
sudo apt-get update

2.安装新版gcc/g++
sudo apt-get install gcc-7 g++-7
sudo apt-get install gfortran-7

3.切换gcc/g+gcc版本
# 命令最后的 20和50是优先级，如果使用auto选择模式，系统将默认使用优先级高的
sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-5 20
sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-7 50

查询系统中安装有哪些版本
sudo update-alternatives --query gcc

使用交互方式的命令选择默认使用的版本
sudo update-alternatives --config gcc

取消相互关联
sudo update-alternatives --remove g++ /usr/bin/gfortran-7
