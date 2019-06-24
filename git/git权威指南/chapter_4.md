# 第四章 Git初始化

```sh
# git 版本号
git --version

# git 当前用户的姓名和密码
git config --global user.name "Cui Kaihua"
git config --global user.email cuikaihua2019@163.com

# 设置 git 命令别名，例如：输入 git ci 相当于 git commit
# 全部用户
git config --system alias.ci commit
# 当前用户
git config --global alias.ci commit
```

```sh
# 初始化本地仓库
mkdir demo
cd demo
git init
echo "hello" > welcome.txt
git add welcome.txt
git commit -m "init"
```

```sh
git rev-parse --git-dir
```





