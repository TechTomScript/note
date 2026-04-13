## 1、查找包名

哔哩哔哩有多个版本，下面是几个常见版本的包名

|  版本  |        包名         |
| :----: | :-----------------: |
| 国内版 |   tv.danmaku.bili   |
| Play版 | com.bilibili.app.in |

小米查找包名步骤：
设置 -> 应用设置 -> 搜索应用 -> 哔哩哔哩 -> 右上角三个点 -> 应用详情 -> 应用包名

## 2、找到视频文件的`audio.m4s`和`video.m4s`文件

使用MT2管理器打开如下路径:`/storage/emulated/0/Android/data/com.bilibili.app.in/download`(这里具体的包名是Play版的哔哩哔哩),下面的每个数字命名的文件夹就是一个视频，找到需要下载的视频(可以点进去根据里面的`entry.json`的文件判断视频)

## 3、下载FFmpeg并解压

[下载链接](http://ffmpeg.org/download.html)
选择Windows图标，然后点击`Windows builds from gyan.dev`,在跳转的新页面中点击`ffmpeg-release-essentials.7z`下载文件后并解压到任意目录下

## 4、 配置环境变量(可选)

## 5、合并`audio.m4s`和`video.m4s`文件

1. 在FFmpeg的文件夹任务栏输入CMD
2. 进入CMD窗口后，输入`dir`，结果输出中有bin，doc，presets等文件夹就说明路径正确，否则请检查第一步的操作
3. 输入`.\bin\ffmpeg -i video.m4s的路径 -i audio.m4s的路径 -codec copy 视频名称.mp4`
