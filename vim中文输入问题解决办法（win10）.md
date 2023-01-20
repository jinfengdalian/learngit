vim中文输入问题解决办法（win10）
====

1. 把动态链接库copy到gvim.exe所在的文件夹里。

[动态琏接库地址](https://github.com/DeXP/xkb-switch-win/releases)。

这有两个文件，分别是32位和64位的，如果不知道自己的操作系统和vim是多少位的，可以两个文件都copy进去。


2. 在_vimrc里添加：

> let g:XkbSwitchLib = 'c:\path\to\dll\libxkbswitch32.dll 


3. 存在问题：

这个方法从inset切到nomal模式是正常的，可以从五笔自动调整到英文。但反过来，从nomal模式下进入到inset时不正常，输入法还是在英文模式，不过这时养成习惯再切一下就不麻烦了。
