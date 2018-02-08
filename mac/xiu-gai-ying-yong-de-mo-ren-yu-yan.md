当我把macbook pro的默认系统语言从中文改成英文后,其他的应用的语言也都变成了英文了.

但是比如地图应用,我还是希望用中文呢?

# 将地图Maps应用的语言改成中文

第一步

```
You don't need to change language setting. 
You can simply set it in the Maps App's Menu at [View]-> [Labels]-> [Always Show Labels in English].
 Then cancel it.
```

第二步

```
defaults write com.apple.Maps AppleLanguages '(zh-CN)'
```

---

```
# 英文 -> 简体中文
defaults write com.google.Chrome AppleLanguages '(zh-CN)'

# 简体中文 -> 英文
defaults write com.google.Chrome AppleLanguages '(en-US)'

# 英文优先，简体中文第二。反之改一下顺序
defaults write com.google.Chrome AppleLanguages "(en-US,zh-CN)"
```

# Calendar

```
defaults write com.apple.iCal AppleLanguages '(zh-CN)'
```

那么问题来了,从上面可以知道只要修改每个应用的系统语言即可

# 如何找到应用的包名

以_**滴答清单**_为例

```
# 在""双引号中输入应用名称,执行下面的命令即可返回应用的包名
hushiwei@hsw ~  osascript -e 'id of app "Wunderlist"'
com.wunderkinder.wunderlistdesktop
```

知道了应用的包名,那么就可以执行上面的命令来修改应用的语言了

```
defaults write com.wunderkinder.wunderlistdesktop AppleLanguages '(zh-CN)'
```



