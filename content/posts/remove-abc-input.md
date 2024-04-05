+++
title = "移除默认输入法"
date = "2024-04-05"
+++

## 背景
在MacOS中，会有一个输入法默认无法删除，例如ABC，这里删除按钮是灰色的。

![](https://ilikemac.obs.ap-southeast-1.myhuaweicloud.com/Screenshot_2024-04-05_at_18.23.47.png)

要删除这个默认输入法，就需要编辑二进制的Plist文件，可以在[这里](https://www.fatcatsoftware.com/plisteditpro/)下载免费的Plist Editor软件。

## 步骤

主要分为两步，一是删除默认输入法，二是重启系统。

### 删除默认输入法
打开Terminal，输入以下命令，打开文件编辑。

```bash
sudo open ~/Library/Preferences/com.apple.HIToolbox.plist -a PlistEdit\ Pro
```

找到`AppleEnabledInputSources`节点，展开，在子项中找到`KeyboardLayout Name`值为你要删除的输入法名称的项，例如我这里是`ABC`，然后点击菜单上的Delete删掉，再按Cmd+S保存即可。

![](https://ilikemac.obs.ap-southeast-1.myhuaweicloud.com/Screenshot_2024-04-05_at_18.24.29.png)

### 重启系统
重启后，可以看到默认无法删除的ABC输入法已经被我们移出了。

![](https://ilikemac.obs.ap-southeast-1.myhuaweicloud.com/Screenshot_2024-04-05_at_18.35.24.png)

## 总结
通过编辑系统配置文件，我们就可以移出不让删除的默认输入法了。

