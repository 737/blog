## 1502-Windows下使用Beyond Compare作为git的比对与合并工具

我的思路为直接对git的config文件进行设置

* 打开.git/config文件

* 增加如下代码


1.  代码比较
```
[diff]
	tool = bc3
[difftool "bc3"]
	cmd = \"E:/Program Files/Beyond Compare 3/BCompare.exe\" \"$LOCAL\" \"$REMOTE\" \"$BASE\" \"$MERGED\"
	trustExitCode = true
```

2. 代码合并
````
[merge]
	tool = bc3
[mergetool "bc3"]
	cmd = \"E:/Program Files/Beyond Compare 3/BCompare.exe\" \"$LOCAL\" \"$REMOTE\" \"$BASE\" \"$MERGED\"
	trustExitCode = true
```

* 其中：
    + `E:/Program Files/Beyond Compare 3/BCompare.exe\` 为tool的安装路径
    + `\"$LOCAL\" \"$REMOTE\" \"$BASE\" \"$MERGED\"` 为在Beyond Compare中打开的窗口，
    + 依次为：本地代码窗口、远程仓库代码窗口、基础窗口、最终合并窗口


