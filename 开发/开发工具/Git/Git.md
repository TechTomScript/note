## 一、安装
[Git](https://git-scm.com/)
[GitHub Desktop](https://desktop.github.com/)

## 二、文档
[Git Document](https://git-scm.com/docs)
[GitHub Training Kit](https://training.github.com/)
[Git Cheatsheet](https://ndpsoftware.com/git-cheatsheet.html)

## 三、设置和配置
`.gitconfig`
```bash
# 设置提交用户名
git config --global user.name [用户名]
# 设置提交邮箱
git config --global user.email [邮箱]
# 设置彩色命令行输出
git config --global color.ui auto
# 默认分支名称
git config --global init.defaultbranch main
```

`.gitconfig`
```config
[core]
    editor = C:\\Users\\HuangChi\\AppData\\Local\\Programs\\Microsoft VS Code\\bin\\code
    autocrlf = true
[filter "lfs"]
    smudge = git-lfs smudge -- %f
    process = git-lfs filter-process
    required = true
    clean = git-lfs clean -- %f
[user]
    name = HuangChi
    email = 13152060392@163.com
[init]
    defaultBranch = main
[color]
    ui = auto
```

## 四、验证Github配置ssh
```bash
HuangChi: ~ ❯ ssh -T git@github.com
Hi HuangChi1! You've successfully authenticated, but GitHub does not provide shell access.
```