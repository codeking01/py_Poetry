## 1.Poetry(推荐)

这个是升级了Pipenv

0.如果不想污染本地的python基础解释器，也可以先去安装pipx，

然后`pipx install poetry`

1.正常安装 poetry

```
pip install poetry
```

2.用法

- 创建环境：先执行 poetry init，一路回车确认。然后使用 poetry shell 创建环境

- 激活环境：pipenv shell（没有环境就创建环境并激活，有环境就直接激活）

- 退出环境：exit

- 删除环境：pipenv env remove <ENV_NAME>（ENV_NAME 可通过 poetry env list 查看）

3.配置环境,找到项目的 `xxx.toml`去加入下面内容

```
# 这个是镜像源配置
[[tool.poetry.source]]
name = "aliyun"
url = "https://mirrors.aliyun.com/pypi/simple/"
```

4.如何使用

拉去了python项目后，去使用下面的命令

```
poetry install 
```

5.常见命令

```poetry
# 安装包，并且添加到toml。Adds a new dependency to pyproject.toml.
poetry add 包名
# 删除的话，
poetry remove 包名
# 更新环境
poetry update
# 
```



## 2.Pipenv

```
# 安装
pip install pipenv
# 激活
pipenv shell
# 退出环境
exit
# 删除环境
pipenv --rm
```

`pipenv install `命令会根据系统默认 Python 版本来创建虚拟环境，并生成用于依赖包管理的` Pipfile 和 Pipfile.lock 文件`。当你将项目分享给他人的时候，执行` pipenv install `命令会创建一个虚拟环境并自动安装 Pipfile 中指定的依赖包。

安装包：

- 用包名安装并写入 Pipfile 的生产环境：pipenv install requests

- 用包名安装并写入 Pipfile 的开发环境：pipenv install pytest --dev

- 安装 Pipfile 中列出的所有生产环境包：pipenv install

- 安装 Pipfile 中列出的所有开发环境包：pipenv install --dev

卸载包：

- 卸载指定包并从 Pipfile 中移除：pipenv uninstall requests

- 卸载所有生产环境包(不从Pipfile中移除)：pipenv uninstall --all

- 卸载所有开发环境包并从 Pipfile 中移除：pipenv uninstall --all-dev

镜像源,将 `Pipfile` 和 `Pipfile.lock` 中对应的 pypi 源（https://pypi.org/simple）修改为国内镜像源，可以解决包下载速度慢的问题。

```
清华大学：https://pypi.tuna.tsinghua.edu.cn/simple
阿里云：http://mirrors.aliyun.com/pypi/simple/
中国科技大学 https://pypi.mirrors.ustc.edu.cn/simple/
豆瓣：http://pypi.douban.com/simple/
```
