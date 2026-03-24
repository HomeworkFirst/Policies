# 📤 GitHub Pages 上传指南

本指南帮助您将法律文档上传到 GitHub Pages。

## 步骤 1：创建 GitHub 仓库

### 1.1 登录 GitHub
访问 https://github.com 并登录您的账户。

### 1.2 创建新仓库
1. 点击右上角的 `+` 按钮
2. 选择 `New repository`
3. 填写仓库信息：
   ```
   Repository name: homeworkfirst-policies
   Description: Privacy Policy and Terms of Service for HomeworkFirst iOS App
   Public (必须是公开仓库才能使用 GitHub Pages)
   ✅ Initialize this repository with a README
   ```
4. 点击 `Create repository`

## 步骤 2：上传文件

### 方法 A：使用 GitHub 网页界面（推荐，最简单）

1. 进入您刚创建的仓库
2. 点击 `Add file` > `Upload files`
3. 将以下文件拖拽到上传区域：
   ```
   - index.html
   - privacy.html
   - terms.html
   ```
4. 在底部填写提交信息：
   ```
   Commit message: Add legal documents
   ```
5. 点击 `Commit changes`

### 方法 B：使用 Git 命令行

如果您熟悉 Git，可以使用命令行：

```bash
# 1. 克隆仓库
cd ~/Projects
git clone https://github.com/YOUR_USERNAME/homeworkfirst-policies.git
cd homeworkfirst-policies

# 2. 复制文件
cp /Users/mashaoze/Projects/ios-app/HomeworkFirst/policies/*.html .

# 3. 提交并推送
git add index.html privacy.html terms.html
git commit -m "Add legal documents"
git push origin main
```

## 步骤 3：启用 GitHub Pages

1. 进入仓库，点击 `Settings`（设置）
2. 在左侧菜单找到 `Pages`
3. 在 `Source` 部分：
   ```
   Source: Deploy from a branch
   Branch: main
   Folder: / (root)
   ```
4. 点击 `Save`
5. 等待几分钟，页面会显示：
   ```
   Your site is live at https://YOUR_USERNAME.github.io/homeworkfirst-policies/
   ```

## 步骤 4：验证网站

访问以下 URL 验证网站是否正常：

```
主页：https://YOUR_USERNAME.github.io/homeworkfirst-policies/
隐私政策：https://YOUR_USERNAME.github.io/homeworkfirst-policies/privacy.html
服务条款：https://YOUR_USERNAME.github.io/homeworkfirst-policies/terms.html
```

## 步骤 5：更新应用代码

### 5.1 找到 PaywallView.swift

文件路径：
```
HomeworkFirst/Views/Subscription/PaywallView.swift
```

### 5.2 替换 URL

找到以下代码（约第313-324行）：

```swift
Button("隐私政策") {
    if let url = URL(string: "https://shaozema.github.io/homeworkfirst-policies/privacy.html") {
        UIApplication.shared.open(url)
    }
}

Button("服务条款") {
    if let url = URL(string: "https://shaozema.github.io/homeworkfirst-policies/terms.html") {
        UIApplication.shared.open(url)
    }
}
```

替换为您的实际 URL：

```swift
Button("隐私政策") {
    if let url = URL(string: "https://YOUR_USERNAME.github.io/homeworkfirst-policies/privacy.html") {
        UIApplication.shared.open(url)
    }
}

Button("服务条款") {
    if let url = URL(string: "https://YOUR_USERNAME.github.io/homeworkfirst-policies/terms.html") {
        UIApplication.shared.open(url)
    }
}
```

### 5.3 测试链接

1. 在 Xcode 中运行应用
2. 进入订阅页面
3. 点击"隐私政策"和"服务条款"链接
4. 验证是否正确打开网页

## 步骤 6：（可选）自定义域名

如果您有自己的域名：

1. 在仓库根目录创建 `CNAME` 文件
2. 文件内容填写您的域名：
   ```
   policies.yourdomain.com
   ```
3. 在域名服务商添加 DNS 记录：
   ```
   Type: CNAME
   Name: policies
   Value: YOUR_USERNAME.github.io
   ```
4. 等待 DNS 生效（可能需要几小时）

## 常见问题

### Q1: 网站显示 404
**A:** 等待 5-10 分钟，GitHub Pages 需要时间构建和部署。

### Q2: 样式显示不正常
**A:** 检查文件是否正确上传，确保 HTML 文件包含完整的 CSS。

### Q3: 如何更新文档？
**A:** 
1. 编辑本地 HTML 文件
2. 在 GitHub 网页上传新文件（会自动覆盖）
3. 或使用 Git 命令：
   ```bash
   git add privacy.html
   git commit -m "Update privacy policy"
   git push origin main
   ```

### Q4: 是否支持 HTTPS？
**A:** 是的，GitHub Pages 自动支持 HTTPS。

### Q5: 如何查看访问统计？
**A:** GitHub Pages 不提供访问统计，可以集成 Google Analytics（但会违背隐私承诺）。

## 检查清单

上传完成后，请检查：

- [ ] 仓库已创建并设置为公开
- [ ] 所有 HTML 文件已上传
- [ ] GitHub Pages 已启用
- [ ] 主页可以正常访问
- [ ] 隐私政策页面可以正常访问
- [ ] 服务条款页面可以正常访问
- [ ] 页面在手机上显示正常（响应式设计）
- [ ] 应用代码中的 URL 已更新
- [ ] 应用中的链接测试通过

## 下一步

完成上传后：

1. ✅ 更新 App Store Connect 中的隐私政策链接
2. ✅ 在应用描述中提及隐私保护
3. ✅ 准备提交审核

## 需要帮助？

如果遇到问题：

1. 查看 [GitHub Pages 文档](https://docs.github.com/en/pages)
2. 检查仓库的 Actions 标签页查看构建日志
3. 确保仓库是公开的（Private 仓库需要 GitHub Pro）

---

**祝您上传顺利！** 🎉
