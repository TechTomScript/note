[Maven](https://maven.apache.org/download.cgi)

---

## 1. 配置环境变量

1. MAVEN_HOME:(**Maven安装路径**)

2. MAVEN_OPTS:-Dfile.encoding=UTF-8

3. Path:%MAVEN_HOME%\bin

## 2. Maven镜像仓库
修改 **MAVEN_HOME/conf/settings.xml** 文件
**阿里云仓库**
```xml
<mirror>  
    <id>aliyun-repos</id>
    <name>Aliyun Public Repository</name>
    <url>https://maven.aliyun.com/repository/public/</url>
    <mirrorOf>central</mirrorOf>
</mirror>
```