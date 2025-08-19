# Git学习文档

## 一、基础操作

### 1. 初始化本地仓库
```bash
git init
```

### 2. 克隆远程仓库
```bash
git clone 仓库地址
```
例：  
```bash
git clone https://github.com/用户名/仓库名.git
```

### 3. 查看仓库状态
```bash
git status
```

### 4. 添加文件到暂存区
```bash
git add 文件名
# 添加全部文件
git add .
```

### 5. 提交更改
```bash
git commit -m "提交说明"
```

### 6. 查看提交历史
```bash
git log
```

## 二、分支管理

### 1. 查看分支
```bash
git branch
```

### 2. 创建新分支
```bash
git branch 分支名
```

### 3. 切换分支
```bash
git checkout 分支名
```

### 4. 合并分支
```bash
git merge 分支名
```

## 三、远程操作

### 1. 查看远程仓库
```bash
git remote -v
```

### 2. 添加远程仓库
```bash
git remote add origin 仓库地址
```

### 3. 推送到远程仓库
```bash
git push origin 分支名
# 首次推送并建立关联
git push -u origin 分支名
```

### 4. 拉取远程更新
```bash
git pull origin 分支名
```

## 四、冲突解决

- 当合并或拉取时出现冲突，手动编辑冲突文件，保存后：
```bash
git add 冲突文件
git commit -m "解决冲突"
```

## 五、标签管理

### 1. 创建标签
```bash
git tag 标签名
```

### 2. 推送标签到远程
```bash
git push origin 标签名
```

## 六、撤销与恢复

### 1. 撤销暂存区文件
```bash
git reset HEAD 文件名
```

### 2. 撤销工作区修改
```bash
git checkout -- 文件名
```

### 3. 回退到某次提交
```bash
git reset --hard 提交ID
```

## 七、常用技巧

- 查看简洁日志：`git log --oneline`
- 查看文件修改历史：`git log 文件名`
- 比较差异：`git diff`
- 配置全局用户名邮箱：
  ```bash
  git config --global user.name "你的用户名"
  git config --global user.email "你的邮箱"
  ```

---

如需更多帮助，建议查阅 [Git官方文档](https://git-scm.com/doc) 或 [GitHub官方文档](https://docs.github.com/en/get-started)。