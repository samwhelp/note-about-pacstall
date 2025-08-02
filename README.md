

# 首頁

| Link | GitHub |
| ---- | ------ |
| [Pacstall 探索筆記](https://samwhelp.github.io/note-about-pacstall/) | [GitHub](https://github.com/samwhelp/note-about-pacstall) |
| [Ubuntu / ISO Builder / 探索筆記](https://samwhelp.github.io/note-about-ubuntu-iso-builder/) | [GitHub](https://github.com/samwhelp/note-about-ubuntu-iso-builder) |




## Pacstall

* [Pacstall](https://pacstall.dev/)
* [Wiki](https://github.com/pacstall/pacstall/wiki)
* GitHub / [Pacstall](https://github.com/pacstall)
* GitHub / Pacstall / [pacstall](https://github.com/pacstall/pacstall)
* GitHub / Pacstall / [pacstall-programs](https://github.com/pacstall/pacstall-programs)




## 主題

* [主程式打包](#主程式打包)
* [pacscript 打包實作範例](#pacscript-打包實作範例)
* [Known Issue](#known-issue)
* [相關筆記](#相關筆記)




## 主程式打包

| 主程式打包 |
| --------- |
| [pacstall-packaging](https://github.com/samwhelp/pacstall-packaging) |




## pacscript 打包實作範例

| pacscript 打包實作範例 |
| ------- |
| [pacstall-demo-repository](https://github.com/samwhelp/pacstall-demo-repository) |
| [deb-coffee](https://github.com/samwhelp/deb-coffee) |
| [deb-coffee-maccity](https://github.com/samwhelp/deb-coffee-maccity) |
| [deb-coffee-wincity](https://github.com/samwhelp/deb-coffee-wincity) |
| [deb-coffee-fancy](https://github.com/samwhelp/deb-coffee-fancy) |
| [deb-coffee-gruvbox](https://github.com/samwhelp/deb-coffee-gruvbox) |
| [deb-coffee-grub](https://github.com/samwhelp/deb-coffee-grub) |
| [deb-coffee-sddm](https://github.com/samwhelp/deb-coffee-sddm) |




## Known Issue

> 在使用「`pacstall`」時，發現會有卡住的情形

執行

``` sh
sudo pacstall -S bean
```

發現會卡住，按下「`Ctrl + c`」，接著會顯示如下的訊息

```
E: Could not get lock /var/lib/apt/lists/lock. It is held by process 1333 (apt-get)
E: Unable to lock directory /var/lib/apt/lists/
```

後來執行下面的指令，

``` sh
sudo rm /var/lib/apt/lists/lock
```

再執行「`pacstall`」就沒有卡住的情形了


發現這個情形，所使用的版本

``` sh
pacstall --version
```

顯示

```
6.3.4 Icterine
```




## 相關筆記

| Link | GitHub |
| ---- | ------ |
| [Rhino Linux 探索筆記](https://samwhelp.github.io/note-about-rhinolinux/) | [GitHub](https://github.com/samwhelp/note-about-rhinolinux/) |
| [Debian 探索筆記](https://samwhelp.github.io/note-about-debian/) | [GitHub](https://github.com/samwhelp/note-about-debian) |




## Samwhelp

* [個人筆記](https://samwhelp.github.io/book/)
