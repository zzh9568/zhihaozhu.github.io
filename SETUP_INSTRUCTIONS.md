# 个人主页设置说明

## 重要提示

由于网络限制，我无法直接克隆完整的模板仓库。你需要手动获取完整的模板文件。

## 推荐方案：直接 Fork 模板仓库

最简单的方法是直接在 GitHub 上操作：

1. **访问模板仓库**：https://github.com/michaelsdr/michaelsdr.github.io
2. **点击 Fork 按钮**，将仓库 Fork 到你的账户
3. **重命名仓库**：
   - 进入你 Fork 的仓库
   - 点击 Settings（设置）
   - 将仓库名改为 `YOUR_USERNAME.github.io`（将 YOUR_USERNAME 替换为你的 GitHub 用户名）
4. **克隆到本地**：
   ```bash
   git clone https://github.com/YOUR_USERNAME/YOUR_USERNAME.github.io.git
   cd YOUR_USERNAME.github.io
   ```
5. **编辑配置文件**：
   - 编辑 `_config.yml`，修改个人信息
   - 编辑 `_data/author.yml`，更新作者信息
   - 根据需要编辑其他页面文件

## 方案二：使用当前创建的文件

如果你想使用我已经创建的基本文件，需要：

1. **安装 Minimal Mistakes 主题**：
   在 `_config.yml` 中已经配置了主题，但需要确保 Gemfile 正确。

2. **安装依赖**：
   ```bash
   sudo apt install ruby-dev ruby-bundler nodejs
   bundle install
   ```

3. **获取主题文件**（如果需要）：
   主题文件通常通过 gem 自动安装，但如果遇到问题，可能需要手动添加主题文件。

## 配置步骤

### 1. 修改 `_config.yml`

打开 `_config.yml` 文件，修改以下内容：

- `title`: 你的网站标题
- `name`: 你的姓名
- `description`: 网站描述
- `url`: 改为 `https://YOUR_USERNAME.github.io`
- `author` 部分的所有信息

### 2. 创建作者信息文件

创建 `_data/author.yml` 文件（如果不存在）：

```yaml
name: "Your Name"
bio: "Your bio"
avatar: "/assets/images/bio-photo.jpg"
```

### 3. 添加内容

- **关于页面**：编辑 `about.md`
- **出版物**：在 `_publications/` 目录添加 Markdown 文件
- **博客文章**：在 `_posts/` 目录添加文章
- **演讲**：在 `_talks/` 目录添加演讲信息

## 部署到 GitHub Pages

1. **创建 GitHub 仓库**：
   - 仓库名必须是 `YOUR_USERNAME.github.io`
   - 设置为 Public

2. **推送代码**：
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/YOUR_USERNAME.github.io.git
   git push -u origin main
   ```

3. **启用 GitHub Pages**：
   - 进入仓库 Settings → Pages
   - Source 选择 "Deploy from a branch"
   - Branch 选择 "main" 和 "/ (root)"
   - 点击 Save

4. **等待部署**：
   几分钟后，访问 `https://YOUR_USERNAME.github.io` 查看你的网站

## 本地测试

在推送到 GitHub 之前，可以在本地测试：

```bash
bundle exec jekyll serve
```

然后访问 http://localhost:4000

## 需要帮助？

如果遇到问题，请参考：
- 模板仓库的 README：https://github.com/michaelsdr/michaelsdr.github.io
- Jekyll 文档：https://jekyllrb.com/docs/
- Minimal Mistakes 主题文档：https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/
