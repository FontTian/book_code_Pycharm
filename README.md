# ReadMe

## 1. 项目说明

1. 本项目 forked from huaxz1986/git_book 是对华校专《Python大战机器学习：数据科学家的一个小目标》书中源码的维护,主要是为了解决原有代码的部分内容适应新版本类库的问题
2. 内容包括,代码的版本更新,以及对源代码的错误修改,以后还会增加例子
3. 维护后的代码不包括对sphinx使用的维护,仅仅保证pycharm下运行相关文件或者使用,不存在问题
4. fork时间为： 2017/08/15 至第三次提交,本项目的sklearn的0.19.X版本已经基本全部完成,并添加了部分新的例子

## 2.修改记录
1. 2017/8/15 修改 chapters/Linear下所有文件至sklearn 0.19.X
2. 2017/12/22 更改 chapters/Bayesian 下所有文件
3. 2018/3/15 将本地文件夹同步到GitHub,基本已经更新完毕,同时包含部分新增演示示例.

## 3. 源码结构

这里给出主要的目录结构。其中 `sphinx` 自动生成的目录和文件未全部列出。

```
book/
		docs/ 	.......................> 说明文档
				make.bat ...............> sphinx 脚本
				build/...................> sphinx 生成的文档所在目录
						html/............> sphinx 生成的 HTML文档的目录
				source/..................> sphinx 的配置文件以及生成的 .rst 文件
						conf.py..........> sphinx 的配置文件
		chapters/ ........................> 源代码
				Bayesian/...................> 朴素贝叶斯和贝叶斯网络	
				Cluster_EM/.................> 聚类和 EM 算法
				Decision_Tree/..............> 决策树
			 	Ensemble/...................> 集成学习
				KNN_Dimension_Reduction/....> KNN和降维
				Linear/.....................> 线性模型
				Model_Selection/............> 模型选择
				Perceptron_Neural_Network/..> 感知机和神经网络
				PreProcessing/..............> 数据预处理
				Semi_Supervised_Learning....> 半监督学习
				SVM/........................> 支持向量机
				Kaggle/.....................> Kaggle 实战
```

## 4. 使用 sphinx 


使用 `sphinx`自动生成文档主要利用了 `sphix`的 `autodoc` 功能。这里的 `conf.py` 已经配置好。生成文档需要两步：

1. 进入命令行后，切换到 `book/`文件夹下
2. 在命令行中输入命令：

	```
	sphinx-apidoc -o docs/source chapters
	```
	该命令将会从 `chapters`目录下的`.py`文件中的抽取注释生成`.rst`文档（这些文档将被存放在 `docs/source/`目录下）

3. 在命令行中输入命令：

	```
	cd docs
	make html
	```
	其中第一行命令是进入`docs/`目录。第二行命令是根据`.rst`文档生成 `html`文档（这些`html`文档位于`docs/build/html/`目录下

## 5. 修改主题

你可以修改生成的`HTML`文件的样式，这是通过修改`sphinx`的主题来实现的。

修改 `conf.py`的 `html_theme = 'classic'` 就能实现修改主题。这里我采用经典主题`'classic'`。内建的主题有：

```
'alabaster'、'sphinx_rtd_theme'、'classic'、'sphinxdoc'、'scrolls'、'agogo'、
'traditional'、 'nature'、 'haiku'、'pyramid bizstyle'

```

## 6. 源码注释

源码注释的格式为：

```
def func(a,b):
    '''
	函数的描述
    
    :param a:  参数 a 的描述
    :param b: 参数 b 的描述 
    :return:  返回值的描述
    '''
    pass
```

这里要注意空行的空格的存在。如果没有这些空格和空行，则 `sphinx`可能会误判这些注释的意义。
