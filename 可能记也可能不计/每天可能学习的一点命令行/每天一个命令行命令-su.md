# 每天一个命令行命令-su

## Syntax

```other
su(选项)(参数)
```

![CleanShot 2023-01-26 at 13.43.00@2x.png](https://res.craft.do/user/full/fe7bf519-c214-88e4-80f3-cc9ee2c45fa1/doc/ea4d2fd6-fb06-47aa-82b9-d11c1d7a8114/2284ce93-5bdf-431e-a34e-e4951cc46388)

## Flass

```other
-c<指令>或--command=<指令>：执行完指定的指令后，即恢复原来的身份；
-f或——fast：适用于csh与tsch，使shell不用去读取启动文件；
-l或——login：改变身份时，也同时变更工作目录，以及HOME,SHELL,USER,logname。此外，也会变更PATH变量；
-m,-p或--preserve-environment：变更身份时，不要变更环境变量；
-s<shell>或--shell=<shell>：指定要执行的shell；
--help：显示帮助；
--version；显示版本信息。
```

这个没有什么实例

