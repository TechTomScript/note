# 开源地址
1. GitHub地址:[docker-easyconnect](https://github.com/docker-easyconnect/docker-easyconnect)
2. DockerHub地址:[hagb/docker-easyconnect](https://hub.docker.com/r/hagb/docker-easyconnect)

# 图形界面版
1. Docker拉取镜像
   `docker pull hagb/docker-easyconnect:7.6.7`
2. 运行EasyConnect容器
   `docker run -e PASSWORD=123456 -p 5901:5901 -p 1080:1080 --privileged=true --device /dev/net/tun --cap-add NET_ADMIN --name easyconnect -d hagb/docker-easyconnect:7.6.7`
3. VNC连接Docker容器 `127.0.0.1:5901`
4. Clash配置
[参考配置](https://clash.wiki/configuration/configuration-reference.html)
```yaml
mixed-port: 7890
allow-lan: true
bind-address: "*"
mode: rule
log-level: info
external-controller: 127.0.0.1:9090

proxies:
    - { name: "EasyConnect", type: socks5, server: 127.0.0.1, port: 1080 }

rules:
    - IP-CIDR,10.16.51.0/24,EasyConnect
```