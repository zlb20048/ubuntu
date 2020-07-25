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
