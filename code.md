压缩文件
```python
import os
import zipfile
def zip_file(path, zip_name):
    """
    path：需要压缩的文件的目录
    zip_name：压缩文件保存目录+xxx.zip（xxx.zip不能在需要压缩的文件的目录中，即不能在path中）
    """
    z = zipfile.ZipFile(zip_name,'w')
    for root, dirs, files in os.walk(path):
        fpath = root.replace(path, '')  #这一句很重要，不replace的话，就从根目录开始复制
        for file in files:
            z.write(os.path.join(root, file), os.path.join(fpath, file))
    z.close()
    print('压缩成功')
 zip_file(path, zip_name)
```