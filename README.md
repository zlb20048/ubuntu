# ubuntu

[SSR相关配置](./ssr.md)


[ss配置的一些坑](./Ubutun配置shadowSocket更改相关的坑.md)

[git相关](./git相关.md)

## 常用工具
1. geany 可视化的文本编辑工具，主要是用来进行日志的过滤
2. meld Ubuntu的对比工具

## ubuntu安装微信
```Bash
  cd ~/.wine
  cd .wine
  cd winetricks
  wine regedit font.reg
  winetricks
  winetricks riched30
  winetricks riched20
  cp -rfv winetricks/msls31 ~/.cache/winetricks
  cp -rfv winetricks/win2ksp4 ~/.cache/winetricks
  winetricks riched20
  winetricks riched32
  winetricks
  wine
  winecfg
```
