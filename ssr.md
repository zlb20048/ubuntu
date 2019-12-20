## 配置代理
```bash
vim /etc/privoxy/config
最后面增加，更改端口，默认端口为1080，目前不可用，需要更改
forward-socks5 / 127.0.0.1:1081 .
```
