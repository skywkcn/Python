# Pipenv
pipenv适合于一个项目使用一个虚拟环境，尽量不要多个项目使用同一个虚拟环境
## 安装pipenv
推荐使用python3版本
pip3 install pipenv
参看是否安装成功及版本
pipenv --version
## 创建虚拟环境
进入到需要创建虚拟环境的目录
```
mkdir test
cd test
```
创建虚拟环境
pipenv install（默认安装本地版本的python）
pipenv install '--python 3.8'（安装指定版本的python）
## 进入虚拟环境
在环境所在目录执行以下命令：
pipenv shell
## 包管理
- 安装第三方包：pipenv install numpy
- 参看安装包信息：pipenv graph
- 更新第三方包：pipenv update numpy
- 更新所有包：pipenv update
- 删除第三方包：pipenv uninstall numpy
## 退出虚拟环境
exit
## 删除虚拟环境
pipenv --rm
## 其他命令
- 查看项目位置：pipenv --where
- 查看虚拟环境位置：pipenv --venv
- 查看虚拟环境python解释器位置：pipenv --py
## Pycharm中配置创建好的pipenv环境
文件>设置>项目>Python解释器>Pipenv环境>基本解释器>选择pipenv --venv所指向的路径

## 团队共享
在团队中共享项目，只需要下载项目到本地，将pipfile和pipfile.lock放到本地目录，运行pipenv install便可以安装项目所依赖的包。
## 资源
[Pipenv使用指南:轻量级虚拟环境管理工具详解](https://blog.csdn.net/master_hunter/article/details/128198145);
[Python虚拟环境（pipenv、venv、conda一网打尽）](https://cloud.tencent.com/developer/article/2124483);
[Python包管理工具之pipenv](https://zhuanlan.zhihu.com/p/534995798);
[用pipenv创建虚拟环境，并在pycharm里应用](https://blog.csdn.net/weixin_43843657/article/details/124984280);
[python项目使用pipenv管理环境，如何使用pycharm调试模式](https://blog.csdn.net/FloraCHY/article/details/129087502);
[在 Pycharm 中配置并使用 pipenv 虚拟环境](https://zhuanlan.zhihu.com/p/368565719);
[Virtualenv、pipenv、conda虚拟环境设置方法及原理](https://zhuanlan.zhihu.com/p/157595132);