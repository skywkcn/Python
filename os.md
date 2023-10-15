[Python OS 文件/目录方法](https://www.runoob.com/python/os-file-methods.html);
# os.walk()
```python
os.walk(top[, topdown=True[, onerror=None[, followlinks=False]]])
```
- **top** ： 是你所要遍历的目录的地址, 返回的是一个三元组(root,dirs,files)
	- root 所指的是当前正在遍历的这个文件夹的本身的地址
	- dirs 是一个 list ，内容是该文件夹中所有的目录的名字(不包括子目录)
	- files 同样是 list , 内容是该文件夹中所有的文件(不包括子目录)
- **topdown** ：可选，为 True，则优先遍历 top 目录，否则优先遍历 top 的子目录(默认为开启)。如果 topdown 参数为 True，walk 会遍历top文件夹，与top 文件夹中每一个子目录
- **onerror** ：可选，需要一个 callable 对象，当 walk 需要异常时，会调用
- **followlinks** ：可选，如果为 True，则会遍历目录下的快捷方式(linux 下是软连接 symbolic link )实际所指的目录(默认关闭)，如果为 False，则优先遍历 top 的子目录

os.walk()一般与for循环结合使用，某文件夹的层级关系如下图，os.walk()的循环顺序为：
第一次循环：root为更目录，dirs为root下的子目录列表，files为root下的文件列表
第二次循环：root为更目录下的第一个子目录的地址，dirs为root下的子目录列表，files为root下的文件列表
第三次循环：root为更目录下的第二个子目录的地址，dirs为root下的子目录列表，files为root下的文件列表
以此类推
层级关系图：
- 0
	- 1
		- 11.txt
		- 12.txt
	- 2
		- 21.txt
	- 3.txt
	- 4.txt

```python
path = 'D:\\0'  
a = 1  
for (root, dirs, files) in os.walk(path):  
    print('第{}次循环'.format(a))  
    print('root为：', root)  
    print('dirs为：', dirs)  
    print('files为：', files)  
    a = a + 1  
# 输出结果
# 第1次循环  
# root为： D:\0
# dirs为： ['1', '2']
# files为： ['3.txt', '4.txt', '5.txt']
# 第2次循环  
# root为： D:\0\1
# dirs为： []
# files为： ['11.txt', '12.txt']
# 第3次循环  
# root为： D:\0\2
# dirs为： []
# files为： ['21.txt']
```
# os.path()
os.path 模块主要用于获取文件的属性；参考：[Python os.path 模块](https://www.runoob.com/python/python-os-path.html);

|语句|功能|备注|
|-----|-----|-----|
|os.path.abspath(path)|返回绝对路径|
|os.path.basename(path)|返回文件名|
|os.path.dirname(path)|返回文件路径|
|os.path.exists(path)|如果路径 path 存在，返回 True；如果路径 path 不存在或损坏，返回 False|
|os.path.join(path1[, path2[, ...]])|把目录和文件名合成一个路径|[os.path.join()用法](https://www.cnblogs.com/an-ning0920/p/10037790.html);|
|os.path.split(path)|把路径分割成 dirname 和 basename，返回一个元组|
|os.path.splitext(path)|分割路径，返回路径名和文件扩展名的元组|


