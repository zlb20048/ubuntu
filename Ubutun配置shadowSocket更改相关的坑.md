## Ubutun配置shadowSocket更改相关的坑

1. 安装ShadowScoket

2. 安装生成PAC文件，可以直接使用GWF上的（这样简单，默认配置）

3. Ubutun的Chrome无法识别file或者data，因此使用nginx来进行服务配置

   1. 安装nginx
      sudo apt-get install nginx

   2. 修改nginx.cnf配置文件
      sudo vim /etc/nginx/nginx.conf
      在nginx.conf的`http{...}`代码块中输入:

      ```nginx
      server{
          listen 80; #注意这里不用":"隔开，listen后面没有冒号
          server_name 127.0.0.1; #注意这里不用":"隔开，server_name后面没有冒号
          location /autoproxy.pac {
              alias 绝对路径/autoproxy.pac;
          }
      }
      ```

   3. 重启nginx
      sudo nginx -s reload

   4. 设置
      把`http://127.0.0.1/autoproxy.pac`填写到系统设置->网络->代理设置->自动代理中

