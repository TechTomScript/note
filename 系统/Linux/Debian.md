
## Deban卸载软件

```sh
# 查找
dpkg -l | grep <包名>

# 卸载
dpkg -r <包名>

# 清理数据(可选)
dpkg --purge $(dpkg -l | grep edge | awk '{print $2}')

# 清理所有已卸载包数据
dpkg --purge $(dpkg -l | grep '^rc' | awk '{print $2}')
```
## Debian修改语言为中文

```sh
# 下载
apt -y install locales  

# 设置zh_CN.UTF-8 UTF-8
dpkg-reconfigure locales
```
