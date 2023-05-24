# Vim Tab => <space>

#vim #tab #space

```vim
:set ts=4
:set expandtab
:%retab!
```

>  `set ts=4`表示 TAB 键为 4 个空格，`set expandtab` 表示将 TAB 键替换为空格，`%retab!` 表示重置 TAB 键配置，就是让上面的配置生效，最后的 ! 表示处理非空白字符后的 TAB，否则只对行首的 TAB 键生效。

# Vim Tab => Tab

#vim #tab

```vim
:set noexpandtab
```



