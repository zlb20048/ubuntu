## Gerrit更改Branch
```
#!/bin/bash

pre_project="NJ-projects/C8/app"
new_branch="parallel"
revision="c8"

[ -f 1.log ] && rm -rf 1.log
grep  '<project' default.xml | awk -F"name=" '{print $2}' | awk '{print $1}' | awk -F'/>' '{print $1}' | sed -e "s/\"//g" > 1.log
for line in `cat 1.log`
do
        projectname=$pre_project'/'$line
    echo $projectname
    if [ x$projectname != x$pre_project'/' ]
    then
        ssh -p 29418 172.19.168.104 gerrit create-branch "$projectname" $new_branch $revision
        echo 1
        fi
done
```

## Gerrit更改组
```
#!/bin/bash

pre_project="NJ-projects/qcom/asop"
#auth_project="atc_bsp_auth"
#auth_project="app_auth"
#auth_project="bsp_read_auth"
#auth_project="b20b_app_auth"
#auth_project="b20b_bsp_auth"
#auth_project="platform_auth"
auth_project="ecar_auth"

[ -f 1.log ] && rm -rf 1.log
grep  '<project' default.xml | awk -F"name=" '{print $2}' | awk '{print $1}' | awk -F'/>' '{print $1}' | sed -e "s/\"//g" > 1.log
for line in `cat 1.log`
do
    projectname=$pre_project'/'$line
    echo $projectname
    if [ x$projectname != x$pre_project'/' ]
    then
        ssh -p 29418 172.19.168.104 gerrit set-project-parent --parent $auth_project "$projectname" > /dev/null
        echo 1
    fi
done
```
