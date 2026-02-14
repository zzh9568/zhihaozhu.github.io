# 启用 GitHub Pages 的步骤

## 问题
访问 https://zhihaozhu.github.io 显示 "There isn't a GitHub Pages site here."

## 解决方案

### 方法一：使用 GitHub Actions（推荐）

你的仓库已经有 GitHub Actions workflow 文件（`.github/workflows/jekyll.yml`），按以下步骤启用：

1. **访问仓库设置页面**：
   https://github.com/zzh9568/zhihaozhu.github.io/settings/pages

2. **配置 Pages 设置**：
   - 在 "Source" 部分，选择 **"GitHub Actions"**（不是 "Deploy from a branch"）
   - 如果看不到 "GitHub Actions" 选项，可能需要先运行一次 workflow

3. **触发 workflow**：
   - 访问 Actions 页面：https://github.com/zzh9568/zhihaozhu.github.io/actions
   - 如果看到 "Deploy Jekyll site to Pages" workflow，点击它
   - 点击 "Run workflow" 按钮手动触发一次
   - 或者直接推送一个小的更改来触发 workflow

4. **等待部署完成**：
   - 在 Actions 页面查看 workflow 运行状态
   - 等待 "Deploy Jekyll site to Pages" workflow 完成（通常需要 1-3 分钟）
   - 完成后，网站应该就可以访问了

### 方法二：使用分支部署（备选）

如果 GitHub Actions 方法不工作，可以尝试：

1. **访问仓库设置**：
   https://github.com/zzh9568/zhihaozhu.github.io/settings/pages

2. **选择分支部署**：
   - Source 选择 "Deploy from a branch"
   - Branch 选择 "master"
   - Folder 选择 "/ (root)"
   - 点击 Save

3. **等待几分钟**让 GitHub Pages 构建

## 检查部署状态

- **Actions 页面**：https://github.com/zzh9568/zhihaozhu.github.io/actions
  - 查看 workflow 是否成功运行
  - 如果有错误，查看日志

- **Pages 设置页面**：https://github.com/zzh9568/zhihaozhu.github.io/settings/pages
  - 查看 "Your site is live at" 部分
  - 应该显示：https://zhihaozhu.github.io

## 常见问题

### 如果 workflow 运行失败
- 检查 Actions 页面的错误日志
- 确保 Gemfile 和 _config.yml 配置正确
- 可能需要更新 workflow 文件中的 Ruby 版本

### 如果仍然显示 404
- 等待 5-10 分钟让 DNS 传播
- 清除浏览器缓存
- 检查仓库是否为 Public（GitHub Pages 需要公开仓库）

## 快速触发部署

如果你想立即触发一次部署，可以运行：

```bash
# 在本地做一个小改动
echo "# Test" >> README.md
git add README.md
git commit -m "Trigger GitHub Pages deployment"
git push
```

这会触发 workflow 自动运行并部署网站。
