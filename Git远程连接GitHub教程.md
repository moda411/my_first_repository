# Git远程连接GitHub教程

## 1. 安装Git

- 访问 [Git官网](https://git-scm.com/) 下载并安装适合你操作系统的Git。
- 安装完成后，在终端（Windows可用Git Bash或CMD）输入以下命令检查安装：
  ```
  git --version
  ```

## 2. 注册并登录GitHub

- 访问 [GitHub官网](https://github.com/) 注册账号并登录。

## 3. 配置Git用户信息

在终端输入以下命令，设置你的用户名和邮箱（与GitHub账号一致）：
```
git config --global user.name "你的GitHub用户名"
git config --global user.email "你的GitHub邮箱"
```

## 4. 生成SSH密钥（推荐）

### 4.1 检查是否已有SSH密钥
```
ls ~/.ssh
```
如有 `id_rsa` 或 `id_ed25519` 文件可跳过生成步骤。

### 4.2 生成新的SSH密钥
```
ssh-keygen -t ed25519 -C "你的GitHub邮箱"
```
按提示操作，生成密钥。

### 4.3 添加SSH密钥到GitHub
- 复制公钥内容：
  ```
  cat ~/.ssh/id_ed25519.pub
  ```
- 登录GitHub，进入 `Settings` -> `SSH and GPG keys` -> `New SSH key`，粘贴公钥。

### 4.4 测试连接
```
ssh -T git@github.com
```
如显示 `Hi 用户名! You've successfully authenticated...` 即连接成功。

## 5. 创建本地仓库并连接远程仓库

### 5.1 新建本地仓库
```
git init
```

### 5.2 创建GitHub远程仓库
- 登录GitHub，点击右上角 `+` -> `New repository`，填写仓库信息并创建。

### 5.3 连接远程仓库
```
git remote add origin git@github.com:你的用户名/仓库名.git
```
或使用HTTPS方式：
```
git remote add origin https://github.com/你的用户名/仓库名.git
```

## 6. 推送本地代码到GitHub

```
git add .
git commit -m "首次提交"
git push -u origin master
```
如遇分支名为 `main`，请将 `master` 改为 `main`。

## 7. 常见问题

- **认证失败**：检查SSH密钥是否添加到GitHub。
- **推送失败**：确认远程仓库地址正确，且本地分支与远程分支一致。

---

如有疑问，可参考 [GitHub官方文档](https://docs.github.com/en/get-started) 或留言交流