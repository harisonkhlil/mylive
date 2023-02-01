# 每天一个命令行命令-echo

## Function

输出你所指定的字符或者变量

```shell
echo "Hello World"
echo $HOEM
echo $PATH
```

## Syntax

```shell
echo [-n] [string ...]
```

## Seclect

```shell
-e：启用转义字符。
-E: 不启用转义字符（默认）
-n: 结尾不换行
```

使用`-e`选项时，若字符串中出现以下字符，则特别加以处理，而不会将它当成一般文字输出：

- `\a` 发出警告声；
- `\b` 删除前一个字符；
- `\c` 不产生进一步输出 (\c 后面的字符不会输出)；
- `\f` 换行但光标仍旧停留在原来的位置；
- `\n` 换行且光标移至行首；
- `\r` 光标移至行首，但不换行；
- `\t` 插入tab；
- `\v` 与\f相同；
- `\\` 插入\字符；
- `\nnn` 插入 `nnn`（八进制）所代表的ASCII字符；

## Color

颜色码：重置=0，黑色=30，红色=31，绿色=32，黄色=33，蓝色=34，洋红=35，青色=36，白色=37

```shell
echo -e "\x1b[30;1m 0 黑色 \x1b[0m"\
"\x1b[31;1m 1 红色 \x1b[0m"\
"\x1b[32;1m 2 绿色 \x1b[0m"\
"\x1b[33;1m 3 黄色 \x1b[0m"\
"\x1b[34;1m 4 蓝色 \x1b[0m"\
"\x1b[35;1m 5 洋红 \x1b[0m"\
"\x1b[36;1m 6 青色 \x1b[0m"\
"\x1b[37;1m 7 白色 \x1b[0m"
```

<!--这个 \x1b 是什么玩意儿-->

**背景色** ：

```shell
echo -e "\e[1;42mGreed Background\e[0m"
Greed Background
```

![CleanShot 2023-01-31 at 15.08.48@2x](https://raw.githubusercontent.com/harisonkhlil/oss/main/uPic/CleanShot%202023-01-31%20at%2015.08.48@2x.png)

颜色码：重置=0，黑色=40，红色=41，绿色=42，黄色=43，蓝色=44，洋红=45，青色=46，白色=47

**文字闪动：**

```shell
echo -e "\033[37;31;5mMySQL Server Stop...\033[39;49;0m"
```

红色数字处还有其他数字参数：0 关闭所有属性、1 设置高亮度（加粗）、4 下划线、5 闪烁、7 反显、8 消隐

**输出内容结尾不添加换行符**

```shell
echo -n 'hello'
```