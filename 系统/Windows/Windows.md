# 一、系统激活篇

## 1、Windows11跳过联网激活

1. 按`Shift + F10`打开命令提示符
2. 输入：`oobe\BypassNRO.cmd`
3. 重启后，在联网界面会有“我没有Internet连接”选项，点击此选项即可跳过联网

## 二、Windows11切换Windows10的右键菜单

**打开`CMD`**，输入下面内容

```bash
reg add HKCU\Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}\InprocServer32 /ve /d "" /f
taskkill /f /im explorer.exe & start explorer.exe
```

## 三、Windows激活

### 1. 测试KMS服务器

> ping 测试服务器地址

```http
zh.us.to 
kms.03k.org 
kms.chinancce.com 
kms.shuax.com 
kms.dwhd.org 
kms.luody.info 
kms.digiboy.ir 
kms.lotro.cc 
ss.yechiu.xin 
www.zgbs.cc 
cy2617.jios.org 
```

### 2. 输入产品产品密钥

> [产品密钥](https://learn.microsoft.com/zh-cn/windows-server/get-started/kms-client-activation-keys?tabs=server2025%2Cwindows1110ltsc%2Cversion1803%2Cwindows81)

| **操作系统版本** | **KMS 客户端产品密钥**               |
| ---------- | ----------------------------- |
| 家庭版        | TX9XD-98N7V-6WMQ6-BX7FG-H8Q99 |
| 专业版        | W269N-WFGWX-YVC9B-4J6C9-T83GX |

```bash
slmgr /ipk W269N-WFGWX-YVC9B-4J6C9-T83GX
```

### 3. 设置KMS服务器

> 选一个在第1步中测试正常的地址

```bash
slmgr /skms zh.us.to
```

### 4. 激活系统

```bash
slmgr /ato
```

## 四、Windows暂停更新

**打开`CMD`**，输入下面内容

```bash
reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\WindowsUpdate\UX\Settings" /v FlightSettingsMaxPauseDays /t reg_dword /d 3000 /f
```

## 五、Windows11启用administrator账户
```bash
net user administrator /active:yes
```
## 六、Windows开机自启项管理

**添加或关闭win10的开机自启项有以下两种常用方式：**

1. winkey + R，输入shell:startup, 即可进入开始菜单的启动文件夹中，在其中添加对应exe的快捷方式，即可实现添加开机启动项的功能。
2. 启动项对应着注册表的键值，添加或删除键值即可删除启动项。
   1. 计算机\HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run
   2. 计算机\HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run
   3. 计算机\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Run
   4. 计算机\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\RunOnce

## 七、Win11删除主文件夹和图库

1. 删除主文件夹
创建后缀为`.reg`的文件 

```properties
Windows Registry Editor Version 5.00
 
[-HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\Desktop\NameSpace\{f874310e-b6b7-47dc-bc84-b9e6b38f5903}]
```

2. 删除图库
创建后缀为`.reg`的文件 
```properties
```

## Windows根据端口号杀死进程
1. 查看端口
```bash
netstat -ano | findstr 9091
```

![image-20250113100114931](.\Windows.assets\image-20250113100114931.png)

2. 根据pid查看进程

```bash
task | findstr 18076
```

![image-20250113100319544](.\Windows.assets\image-20250113100319544.png)

3. 杀掉指定进程

```bash
taskkill /F /PID 18076
```

![image-20250113100406253](.\Windows.assets\image-20250113100406253.png)

## Windows启动IE浏览器
新建一个文件，名称为`IE.vbs`，输入内容
```vbs
CreateObject("InternetExplorer.Application").Visible = True
```
打开`IE.vbs`文件