# ubuntu

[SSR相关配置](./ssr.md)
[ss配置的一些坑](./Ubutun配置shadowSocket更改相关的坑.md)

## git相关
### git系统配置
```Bash
function gitpush {
    branch=`git branch -r |grep 'm/' |awk -F'-> ' '{print $2}'` &&
        l=`echo $branch | awk -F'/' '{print $1}'` &&
        rr=`echo $branch | awk -F'/' '{print $2}'` &&
        echo "git push ${l} `git rev-parse --abbrev-ref HEAD`:refs/for/${rr}" && git push ${l} `git rev-parse --abbrev-ref HEAD`:refs/for/${rr}
}

function gitrebase {
    branch=`git branch -r | grep 'm/' | awk -F'-> ' '{print $2}'` &&
        l=`echo $branch | awk -F'/' '{print $1}'` &&
        rr=`echo $branch | awk -F'/' '{print $2}'` &&
        echo "git pull --rebase ${l} ${rr}" &&
        git pull --rebase ${l} ${rr}

}
```
### git环境配置
```Bash
[alias]
        st = status
        br = branch
        co = checkout
        ci = commit
        lg = log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit --
```

### git工具
gitk gitg

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
