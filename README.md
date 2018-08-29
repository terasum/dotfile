# terasum's dotfile

## SECTION 1: VIM cheat sheet

> 如果你在使用本`.vimrc`，你可以参考本使用文档
> 直接将`vimrc`文件放到$HOME并命名为`.vimrc`即可


### 阅读前说明

1. 如果你看到一条命令是`:` (半角冒号)开头的话，请不要犹豫，直接先输入`:`(半角冒号)
2. 在本配置中，`<Leader>` 键是`,`(半角逗号)
3. 半角符号即英文符号
4. 尖括号的中命令表示需要按下，例如`<F3>` 表示需要按下键盘上的`F3`
5. `<C-R>` 表示要按下 `Ctrl + R` 请注意是`R`而不是小写的`r`，因此需要同时按下
`Ctrl` + `shift` + `r`

6. `S-t` 表示需要按下 `shift` + `t`
7. `<leader>f` 表示需要按下 `,` + `f`

### 通用部分

#### 插件安装

一般使用本vimrc的话，初次启动vim 会自动帮你安装插件，你不需要特别输入相关命令。
如果vim没有帮你自动安装的话，你可以输入：

```
:PlugInstall
```

进行安装。

#### 自动纠正

一般来说，你肯定会遇到保存文件的时候不小心输入了类似`Wq`
这样的命令，本配置文件会自动帮助你纠正这种简单的输入错误：

纠错映射表如下：

```
W!           w!
Q!           q!
Qall!        qall!
Wq           wq
Wa           wa
wQ           wq
WQ           wq
W            w
Q            q
Qall         qall
```


#### NERDTree

NERDTree 即文件树，存在如下命令：

```
F2   文件树搜索
F3   展开或者隐藏文件树
```


#### grep文件搜索

搜索的时候会跳过`.git` 和`node_modules`以及`*.log`和`*.db`

```
<leader>f
```

#### 终端

在vim中可以使用vimshell,来执行命令，相关命令是:

```
<leader>sh
```
可以进入vimshell,进入之后可以随意输入相关命令并执行，执行完毕想退出，请退出`insert`模式并按`q`


#### Split (屏幕划分)

```
<leader>h 垂直划分
<leader>v 水平划分

在不同的划分window中进行光标移动:

C-w j 向下移动
C-w k 向上移动
C-w h 向左移动
C-w l 向右移动
```

#### Git相关命令

当前配置中安装了git插件，并配置了相关的alias,可以快速使用git相关命令

```
<Leader>ga       git add
<Leader>gc       git commit
<Leader>gsh      git push
<Leader>gll      git pull
<Leader>gs       git status
<Leader>gb       git blame
<Leader>gd       git diff
<Leader>gr       git remove
```


#### TAB相关命令

我个人觉得TAB相关命令是最实用的：

```
<Tab>   下一个TAB
<S-Tab> 上一个TAB
<S-t>   新建TAB
```

注意: 这里的`<Tab>` 就是键盘上的`tab`

#### SESSION相关命令

SESSION就是会话，你可以把当前的编辑状态保存为会话，然后需要的时候可以恢复

```
" session management
<leader>so 打开一个会话
<leader>ss 保存一个会话
<leader>sd 删除一个会话
<leader>sc 关闭一个会话
```

#### 设置当前工作目录

```
<leader>.
```


#### 从当前的工作目录打开一个文件进行编辑：

打开的文件将会覆盖当前编辑的文件窗口

```
<leader>e
```

#### 从当前目录打开一个文件进行编辑(tab)

打开的文件将会新建一个TAB打开

```
<leader>te
```

#### 打开符号定义窗口(Tagbar)

```
<F4>
```

#### 复制粘贴

当前配置能够自动读取剪贴板中的内容进行粘贴，如果粘贴的时候会自动缩进，
请在粘贴之前输入：

```
:paste
```

#### buffer 导航

buffer类似于tab，但有区别:

 A buffer is the in-memory text of a file.
 A window is a viewport on a buffer.
 A tab page is a collection of windows.

```
buffer导航
<leader>z 下一个buffer
<leader>q 下一个buffer
<leader>x 上一个buffer
<leader>w 上一个buffer

关闭buffer
<leader>c :bd<CR>
```

#### 搜索高亮清除

当我们搜索之后，会有高亮字符，可以用下面的方式清除所有高亮

```
<leader><space>
```

#### window切换

前面也说过如何切换当前焦点的window, 这个也有快捷键

```
"" Switching windows
<C-j>  向下切换
<C-k>  向上切换
<C-l>  向左切换
<C-h>  向右切换
```

#### visual模式缩进

在visual模式下，可能希望将一段代码整体缩进，这个时候可以通过visual模式选中一段代码之后，利用`<`
和`>`进行缩进调整。


#### visual模式代码整行移动

在visual模式下，可以通过大写的`J` 和`K`将当前选中的代码进行上移或者下移



### GO语言相关快捷键


#### 定义跳转

```
  <Leader>dd go-def
  <Leader>dv go-doc
  <Leader>db go-doc-browser

```

#### Go相关命令

```
  <leader>r  go-run
  <leader>t  go-test
  <Leader>gt go-coverage-toggle
  <Leader>i  go-info
  <Leader>l  go-metalinter
```

#### Go相关声明

```
  <C-g>         GoDecls
  <leader>dr    GoDeclsDir
  <leader>rb    build_go_files()
```


