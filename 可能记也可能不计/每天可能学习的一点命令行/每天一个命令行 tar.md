# 每天一个命令行命令 tar

## Compress

```shell
tar -czvf nvim.tar.gz nvim/
```

> 说明：将 nvim 文件夹压缩为 nvim.tar.gz 
>
> 参数说明：
>
> * -c 创建一个 tar 文件意思是打包
> * -z 使用 gzip 压缩
> * -v 详细输出信息
> * -f 指定一个名字

## Decompress

```sh
tar -xzvf nvim.tar.gz
```

> 其中，-x 表示解压缩，-z 表示使用 gzip 进行解压缩，-v 表示显示详细信息，-f 表示指定要解压缩的文件名。可以将 nvim.tar.gz 文件解压缩到当前目录。



