# 部署到 GitHub Pages 说明

## 当前状态

✅ 模板文件已克隆到本地
✅ 配置文件已更新（GitHub 用户名：zzh9568）
✅ 个人信息已配置

## 下一步操作

### 1. 在 GitHub 上创建仓库

1. 登录 GitHub
2. 点击右上角的 "+" → "New repository"
3. 仓库名必须设置为：`zzh9568.github.io`
4. 设置为 Public（GitHub Pages 需要）
5. 不要初始化 README、.gitignore 或 license（因为本地已有文件）
6. 点击 "Create repository"

### 2. 更新本地 Git 远程仓库地址

当前仓库的远程地址还是指向模板仓库，需要更新为你自己的仓库：

```bash
# 移除旧的远程仓库
git remote remove origin

# 添加你的仓库作为远程仓库
git remote add origin git@github.com:zzh9568/zzh9568.github.io.git

# 验证远程仓库
git remote -v
```

### 3. 提交并推送代码

```bash
# 添加所有更改
git add .

# 提交更改
git commit -m "Initial setup: configure personal website"

# 推送到 GitHub（如果是第一次推送）
git push -u origin master

# 或者如果 GitHub 默认分支是 main
git branch -M main
git push -u origin main
```

### 4. 启用 GitHub Pages

1. 进入你的仓库页面：https://github.com/zzh9568/zzh9568.github.io
2. 点击 "Settings"（设置）
3. 在左侧菜单找到 "Pages"
4. 在 "Source" 部分：
   - 选择 "Deploy from a branch"
   - Branch 选择 "master"（或 "main"，取决于你的默认分支）
   - Folder 选择 "/ (root)"
5. 点击 "Save"

### 5. 等待部署

- GitHub Pages 通常需要几分钟来构建和部署
- 部署完成后，访问：https://zzh9568.github.io
- 如果看到 404，等待几分钟后刷新

## 本地测试（可选）

在推送到 GitHub 之前，可以在本地测试网站：

```bash
# 安装依赖（如果还没安装）
sudo apt install ruby-dev ruby-bundler nodejs
bundle install

# 启动本地服务器
bundle exec jekyll serve

# 访问 http://localhost:4000 查看网站
```

## 自定义内容

### 更新个人信息

1. **编辑 `_config.yml`**：
   - 修改 `title`、`name`、`description`
   - 更新 `author` 部分的详细信息

2. **编辑 `_data/authors.yml`**：
   - 更新作者信息

3. **编辑 `about.md`**：
   - 添加你的个人简介、教育背景、研究兴趣等

### 添加内容

- **出版物**：在 `_publications/` 目录添加 Markdown 文件
- **博客文章**：在 `_posts/` 目录添加文章
- **演讲**：在 `_talks/` 目录添加演讲信息
- **教学**：在 `_teaching/` 目录添加课程信息
- **作品集**：在 `_portfolio/` 目录添加项目

### 上传文件

- 将 PDF、图片等文件放到 `files/` 或 `images/` 目录
- 访问地址：`https://zzh9568.github.io/files/yourfile.pdf`

## 常见问题

### 网站显示 404

- 等待几分钟让 GitHub Pages 完成构建
- 检查仓库名是否正确（必须是 `username.github.io`）
- 检查 Settings → Pages 中的配置

### 样式不显示

- 确保 `_config.yml` 中的 `url` 和 `baseurl` 配置正确
- 清除浏览器缓存

### 本地运行出错

- 确保安装了 Ruby 和 Bundler
- 运行 `bundle install` 安装依赖
- 如果 Gemfile.lock 有问题，删除后重新运行 `bundle install`

## 参考资源

- 模板仓库：https://github.com/michaelsdr/michaelsdr.github.io
- Jekyll 文档：https://jekyllrb.com/docs/
- Minimal Mistakes 主题：https://mmistakes.github.io/minimal-mistakes/
