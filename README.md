linux命令
===

### 文件及目录管理

#### 列出目录项
* 查看当前目录下文件个数
```
find ./ | wc -l
```
* 列出目录项 (显示文件大小(K,M,G))
```
ll -h
```
* 按时间排序，显示目录项
```
ls -lrt
```
* 给常用的命令设置快捷方式
```
>>>locate .bashrc  # 查找文件路径
>>>vi /home/用户名/.bashrc  # 写入该文件中
e.g. alias lsl='ls -lrt'  # 后期只需要输入: * lsl *
```
* 给文件前面增加一个ID编号
```
ls | cat -n
```
#### 查找文件
* 通过文件索引查找文件
```
locate [file]
注：locate是根据为文件系统建立索引数据库，如果文件更新，需要定期执行更新命令来更新索引库
>>>updatedb  # 更新文件索引库
```
* 查找文件
```
find ./ -name '[file]'
```
#### 查看文件内容
* 显示使同时显示行号
```
cat -n [file]
```
* 按页显示列表内容
```
ls -al | more [file]
more [file]
```
* 显示前一部分(具体前多少行)
```
head -[num]
e.g. head -10 [file]  # 只看文件前10行
```
* 显示后一部分(具体后多少行)
```
tail -[num] [file]
e.g. tail -10 [file]  # 只看文件后10行
```
* 查看两个文件的不同
```
diff [file1] [file2]
```
* 重定向
```
echo aa >> a.txt
ping www.baidu.com > b.txt  # 将反馈结果重定向到文件中
```

### 文本处理

#### find文件查找
* 查找txt文件
```
find . \( -name "*.txt" \) -print
```
* 查找所有非txt文本
```
find . ! -name "*.txt" -print
```
* 列出所有文件夹下所有目录
```
find . -type d -print
```
* 查看最近被访问过的文件
```
find . -atime [num] -type f -print
e.g. find . -atime 7 -type f -print  # 查询第7天被访问的所有文件
e.g. find . -atime -7 -type f -print  # 查询7天内被访问的所有文件
e.g. find . -atime +7 -type f -print  # 查询7天前被访问的所有文件
```
* 按大小搜索(K, M, G)
```
find . -type f -size +[file_size]
e.g. find . -type f -size +2k  # 寻找大于2k的文件
```









