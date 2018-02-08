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



# Calendar

```
defaults write com.apple.iCal AppleLanguages '(zh-CN)'
```



