# ubuntu18、Centos7一键脚本离线安装Flask完整步骤与依赖解决

V0.0.2.20210713

------

## 项目简介

> ubuntu18、Centos7离线安装Flash
>
> 离线包下载地址 https://pypi.org/project/

## 安装前准备

* 首先保证系统中安装了完整的python3，带pip3，离线安装python3并不知

* centos 下在线安装 python3

  ```
  yum install python3
  ```

* ubuntu 下在线安装 python3

  ```
  apt install python3
  ```

## 安装的版本

```shell
[root@bogon Flask]# flask --version
Python 3.6.8
Flask 2.0.1
Werkzeug 2.0.1
[root@bogon Flask]# 
```

## 在以下系统经历了测试

```
[root@bogon Flask]# uname -a
Linux bogon 3.10.0-1062.el7.x86_64 #1 SMP Wed Aug 7 18:08:02 UTC 2019 x86_64 x86_64 x86_64 GNU/Linux
[root@bogon Flask]# cat /etc/centos-release
CentOS Linux release 7.7.1908 (Core)
[root@bogon Flask]# 
```

> 在ubuntu18中依然尝试过，但并没有测试脚本自动，不过依赖的内容均是一样的

## 脚本自动安装方法

```
chmod +x ./install.sh			# 为脚本增加可执行权限
./install.sh 					# 执行该脚本即可
```

```shell
[root@bogon Flask]# ./install.sh 
pip3 是 /usr/bin/pip3
WARNING: Running pip install with root privileges is generally not a good idea. Try `pip3 install --user` instead.
Processing ./MarkupSafe-2.0.1-cp36-cp36m-manylinux1_x86_64.whl
Installing collected packages: MarkupSafe
Successfully installed MarkupSafe-2.0.1
WARNING: Running pip install with root privileges is generally not a good idea. Try `pip3 install --user` instead.
Processing ./Jinja2-3.0.1-py3-none-any.whl
Requirement already satisfied: MarkupSafe>=2.0 in /usr/local/lib64/python3.6/site-packages (from Jinja2==3.0.1)
Installing collected packages: Jinja2
Successfully installed Jinja2-3.0.1
WARNING: Running pip install with root privileges is generally not a good idea. Try `pip3 install --user` instead.
Processing ./pytz-2021.1-py2.py3-none-any.whl
Installing collected packages: pytz
Successfully installed pytz-2021.1
WARNING: Running pip install with root privileges is generally not a good idea. Try `pip3 install --user` instead.
Processing ./Babel-2.9.1-py2.py3-none-any.whl
Requirement already satisfied: pytz>=2015.7 in /usr/local/lib/python3.6/site-packages (from Babel==2.9.1)
Installing collected packages: Babel
Successfully installed Babel-2.9.1
WARNING: Running pip install with root privileges is generally not a good idea. Try `pip3 install --user` instead.
Processing ./itsdangerous-2.0.1-py3-none-any.whl
Installing collected packages: itsdangerous
Successfully installed itsdangerous-2.0.1
WARNING: Running pip install with root privileges is generally not a good idea. Try `pip3 install --user` instead.
Processing ./typing_extensions-3.10.0.0-py3-none-any.whl
Installing collected packages: typing-extensions
Successfully installed typing-extensions-3.10.0.0
WARNING: Running pip install with root privileges is generally not a good idea. Try `pip3 install --user` instead.
Processing ./zipp-3.5.0-py3-none-any.whl
Installing collected packages: zipp
Successfully installed zipp-3.5.0
WARNING: Running pip install with root privileges is generally not a good idea. Try `pip3 install --user` instead.
Processing ./importlib_metadata-4.6.1-py3-none-any.whl
Requirement already satisfied: zipp>=0.5 in /usr/local/lib/python3.6/site-packages (from importlib-metadata==4.6.1)
Requirement already satisfied: typing-extensions>=3.6.4; python_version < "3.8" in /usr/local/lib/python3.6/site-packages (from importlib-metadata==4.6.1)
Installing collected packages: importlib-metadata
Successfully installed importlib-metadata-4.6.1
WARNING: Running pip install with root privileges is generally not a good idea. Try `pip3 install --user` instead.
Processing ./click-8.0.1-py3-none-any.whl
Requirement already satisfied: importlib-metadata; python_version < "3.8" in /usr/local/lib/python3.6/site-packages (from click==8.0.1)
Requirement already satisfied: typing-extensions>=3.6.4; python_version < "3.8" in /usr/local/lib/python3.6/site-packages (from importlib-metadata; python_version < "3.8"->click==8.0.1)
Requirement already satisfied: zipp>=0.5 in /usr/local/lib/python3.6/site-packages (from importlib-metadata; python_version < "3.8"->click==8.0.1)
Installing collected packages: click
Successfully installed click-8.0.1
WARNING: Running pip install with root privileges is generally not a good idea. Try `pip3 install --user` instead.
Processing ./dataclasses-0.8-py3-none-any.whl
Installing collected packages: dataclasses
Successfully installed dataclasses-0.8
WARNING: Running pip install with root privileges is generally not a good idea. Try `pip3 install --user` instead.
Collecting MarkupSafe-2.0.1-cp36-cp36m-manylinux
  Could not find a version that satisfies the requirement MarkupSafe-2.0.1-cp36-cp36m-manylinux (from versions: )
No matching distribution found for MarkupSafe-2.0.1-cp36-cp36m-manylinux
WARNING: Running pip install with root privileges is generally not a good idea. Try `pip3 install --user` instead.
Processing ./Werkzeug-2.0.1-py3-none-any.whl
Requirement already satisfied: dataclasses; python_version < "3.7" in /usr/local/lib/python3.6/site-packages (from Werkzeug==2.0.1)
Installing collected packages: Werkzeug
Successfully installed Werkzeug-2.0.1
WARNING: Running pip install with root privileges is generally not a good idea. Try `pip3 install --user` instead.
Processing ./Flask-2.0.1-py3-none-any.whl
Requirement already satisfied: Werkzeug>=2.0 in /usr/local/lib/python3.6/site-packages (from Flask==2.0.1)
Requirement already satisfied: itsdangerous>=2.0 in /usr/local/lib/python3.6/site-packages (from Flask==2.0.1)
Requirement already satisfied: Jinja2>=3.0 in /usr/local/lib/python3.6/site-packages (from Flask==2.0.1)
Requirement already satisfied: click>=7.1.2 in /usr/local/lib/python3.6/site-packages (from Flask==2.0.1)
Requirement already satisfied: dataclasses; python_version < "3.7" in /usr/local/lib/python3.6/site-packages (from Werkzeug>=2.0->Flask==2.0.1)
Requirement already satisfied: MarkupSafe>=2.0 in /usr/local/lib64/python3.6/site-packages (from Jinja2>=3.0->Flask==2.0.1)
Requirement already satisfied: importlib-metadata; python_version < "3.8" in /usr/local/lib/python3.6/site-packages (from click>=7.1.2->Flask==2.0.1)
Requirement already satisfied: zipp>=0.5 in /usr/local/lib/python3.6/site-packages (from importlib-metadata; python_version < "3.8"->click>=7.1.2->Flask==2.0.1)
Requirement already satisfied: typing-extensions>=3.6.4; python_version < "3.8" in /usr/local/lib/python3.6/site-packages (from importlib-metadata; python_version < "3.8"->click>=7.1.2->Flask==2.0.1)
Installing collected packages: Flask
Successfully installed Flask-2.0.1
[root@bogon Flask]# 

```

## 脚本内容

* 直接将下面的代码框内容复制到新建的.sh即可

  ```shell
  #!/bin/bash
  
  # 离线安装python3插件，所有插件均是20210713时刻的最新版
  #
  # 测试环境
  #	[root@localhost ~]# uname -a
  #	Linux localhost.localdomain 3.10.0-1062.el7.x86_64 #1 SMP Wed Aug 7 18:08:02 UTC 2019 x86_64 x86_64 x86_64 GNU/Linux
  #	[root@localhost ~]# cat /etc/centos-release
  #	CentOS Linux release 7.7.1908 (Core)
  #
  
  SUDO="sudo"		# 看需不需要sudo了，理论上不需要，当不需要时候可以直接修改这里
  
  if ! type pip3
  then
  		echo "需要先安装python3 or pip3";
  		exit 1;
  fi
  
  # 以下需要按照顺序安装
  ${SUDO} pip3 install MarkupSafe-2.0.1-cp36-cp36m-manylinux1_x86_64.whl		# 1
  ${SUDO} pip3 install Jinja2-3.0.1-py3-none-any.whl							# 2
  ${SUDO} pip3 install pytz-2021.1-py2.py3-none-any.whl						# 3
  ${SUDO} pip3 install Babel-2.9.1-py2.py3-none-any.whl						# 4
  ${SUDO} pip3 install itsdangerous-2.0.1-py3-none-any.whl					# 5
  ${SUDO} pip3 install typing_extensions-3.10.0.0-py3-none-any.whl			# 6
  ${SUDO} pip3 install zipp-3.5.0-py3-none-any.whl		 					# 7
  ${SUDO} pip3 install importlib_metadata-4.6.1-py3-none-any.whl				# 8
  ${SUDO} pip3 install click-8.0.1-py3-none-any.whl							# 9
  ${SUDO} pip3 install dataclasses-0.8-py3-none-any.whl						# 10
  ${SUDO} pip3 install Werkzeug-2.0.1-py3-none-any.whl						# 11
  ${SUDO} pip3 install Flask-2.0.1-py3-none-any.whl							# 12
  
  # 可能遇到的问题
  
  # 	需要依赖
  #		示例
  #			[root@bogon Flask]# pip3 install Flask-2.0.1-py3-none-any.whl 
  #			WARNING: Running pip install with root privileges is generally not a good idea. Try `pip3 install --user` instead.
  #			Processing ./Flask-2.0.1-py3-none-any.whl
  #			Requirement already satisfied: click>=7.1.2 in /usr/local/lib/python3.6/site-packages (from Flask==2.0.1)
  #			Collecting Werkzeug>=2.0 (from Flask==2.0.1)
  #		分析
  #			还需要安装 Werkzeug 版本号大于 2.0
  #		安装
  #			pip3 install Werkzeug-2.0.1-py3-none-any.whl
  
  # 最后安装成功示例
  # 	[root@bogon Flask]# pip3 install Flask-2.0.1-py3-none-any.whl 
  # 	WARNING: Running pip install with root privileges is generally not a good idea. Try `pip3 install --user` instead.
  #	Processing ./Flask-2.0.1-py3-none-any.whl
  # 	Requirement already satisfied: Jinja2>=3.0 in /usr/local/lib64/python3.6/site-packages (from Flask==2.0.1)
  # 	Requirement already satisfied: click>=7.1.2 in /usr/local/lib/python3.6/site-packages (from Flask==2.0.1)
  # 	Requirement already satisfied: itsdangerous>=2.0 in /usr/local/lib/python3.6/site-packages (from Flask==2.0.1)
  # 	Requirement already satisfied: Werkzeug>=2.0 in /usr/local/lib/python3.6/site-packages (from Flask==2.0.1)
  # 	Requirement already satisfied: MarkupSafe>=2.0 in /usr/local/lib64/python3.6/site-packages (from Jinja2>=3.0->Flask==2.0.1)
  # 	Requirement already satisfied: importlib-metadata; python_version < "3.8" in /usr/local/lib/python3.6/site-packages (from click>=7.1.2->Flask==2.0.1)
  # 	Requirement already satisfied: dataclasses; python_version < "3.7" in /usr/local/lib/python3.6/site-packages (from Werkzeug>=2.0->Flask==2.0.1)
  # 	Requirement already satisfied: typing-extensions>=3.6.4; python_version < "3.8" in /usr/local/lib/python3.6/site-packages (from importlib-metadata; python_version < "3.8"->click>=7.1.2->Flask==2.0.1)
  #	Requirement already satisfied: zipp>=0.5 in /usr/local/lib/python3.6/site-packages (from importlib-metadata; python_version < "3.8"->click>=7.1.2->Flask==2.0.1)
  # 	Installing collected packages: Flask
  # 	Successfully installed Flask-2.0.1
  
  ```

## 可能遇到的问题

* 依赖依然有问题

  ```
  # 可能遇到的问题
  
  # 	需要依赖
  #		示例
  #			[root@bogon Flask]# pip3 install Flask-2.0.1-py3-none-any.whl 
  #			WARNING: Running pip install with root privileges is generally not a good idea. Try `pip3 install --user` instead.
  #			Processing ./Flask-2.0.1-py3-none-any.whl
  #			Requirement already satisfied: click>=7.1.2 in /usr/local/lib/python3.6/site-packages (from Flask==2.0.1)
  #			Collecting Werkzeug>=2.0 (from Flask==2.0.1)
  #		分析
  #			还需要安装 Werkzeug 版本号大于 2.0
  #		安装
  #			pip3 install Werkzeug-2.0.1-py3-none-any.whl
  ```

* 离线的包下载地址

  * 官方地址：https://pypi.org/project/
  * 我用到的离线包
    * https://download.csdn.net/download/weixin_42544902/20254707
    * 已设置免积分，如果遇到问题，直接发邮件向我索取即可

## 使用说明

## 维护说明

## 注意

## 关于作者

>Autho: KiraSkyler
>Email: kiraskyler@outlook.com / kiraskyler@qq.com

## 贡献者/贡献组织

## 鸣谢

## 版权信息

> 该项目签署了GPL 授权许可，详情请参阅官网

>This program is free software: you can redistribute it and/or modify
>it under the terms of the GNU General Public License as published by
>the Free Software Foundation, either version 3 of the License, or
>(at your option) any later version.
>This program is distributed in the hope that it will be useful,
>but WITHOUT ANY WARRANTY; without even the implied warranty of
>MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
>GNU General Public License for more details.
>You should have received a copy of the GNU General Public License
>along with this program.  If not, see <https://www.gnu.org/licenses/>.

## 更新日志

* V0.0.0.20210101