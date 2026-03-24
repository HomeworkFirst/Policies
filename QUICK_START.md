# 🚀 快速开始指南（5分钟上传）

## 文件清单 ✅

本目录包含以下文件，全部可直接上传：

```
📁 policies/
├── 📄 index.html         (4.0K)  - 导航主页
├── 📄 privacy.html       (10K)   - 隐私政策
├── 📄 terms.html         (11K)   - 服务条款
├── 📄 README.md          (1.7K)  - 仓库说明
├── 📄 UPLOAD_GUIDE.md    (5.0K)  - 详细上传指南
└── 📄 QUICK_START.md     (本文件) - 快速开始
```

## ⚠️ 上传前必读

**请先配置邮箱和 URL！** 查看 `CUSTOMIZATION_GUIDE.md` 了解详情。

快速替换（在终端执行）：
```bash
cd /Users/mashaoze/Projects/ios-app/HomeworkFirst/policies

# 替换邮箱
sed -i '' 's/souther217@gmail.com/YOUR_EMAIL@example.com/g' *.html

# 替换 GitHub 用户名（上传后再配置应用代码）
# 见下方"更新应用代码"步骤
```

## 🎯 三步上传（最简单）

### 步骤 1：创建 GitHub 仓库

1. 访问 https://github.com/new
2. 填写：
   - Repository name: `homeworkfirst-policies`
   - Public (公开)
   - ✅ Add a README file
3. 点击 **Create repository**

### 步骤 2：上传文件

1. 进入新建的仓库
2. 点击 **Add file** > **Upload files**
3. 拖拽以下文件到上传区域：
   ```
   index.html
   privacy.html
   terms.html
   ```
4. 点击 **Commit changes**

### 步骤 3：启用 GitHub Pages

1. 点击 **Settings** (设置)
2. 左侧菜单找到 **Pages**
3. 设置：
   - Source: **Deploy from a branch**
   - Branch: **main** / **(root)**
4. 点击 **Save**
5. 等待 3-5 分钟，刷新页面，会显示网址

## ✅ 验证

访问以下网址验证：

```
https://YOUR_USERNAME.github.io/homeworkfirst-policies/
https://YOUR_USERNAME.github.io/homeworkfirst-policies/privacy.html
https://YOUR_USERNAME.github.io/homeworkfirst-policies/terms.html
```

## 🔧 更新应用代码

打开 `HomeworkFirst/Views/Subscription/PaywallView.swift`

找到约第313行和第321行，替换 URL：

```swift
// 隐私政策链接 (第313行)
if let url = URL(string: "https://YOUR_USERNAME.github.io/homeworkfirst-policies/privacy.html") {

// 服务条款链接 (第321行)
if let url = URL(string: "https://YOUR_USERNAME.github.io/homeworkfirst-policies/terms.html") {
```

将 `YOUR_USERNAME` 替换为您的 GitHub 用户名。

## 🧪 测试

1. 在 Xcode 运行应用
2. 进入任何需要订阅的功能
3. 点击"开始试用"
4. 滚动到底部
5. 点击"隐私政策"和"服务条款"
6. 验证链接是否正确打开

## 📝 完整步骤

如果需要更详细的说明，请查看 `UPLOAD_GUIDE.md`。

## ❓ 常见问题

**Q: 我没有 GitHub 账号怎么办？**
A: 访问 https://github.com/signup 免费注册。

**Q: 上传后显示 404？**
A: 等待 5-10 分钟，GitHub Pages 需要时间构建。

**Q: 可以使用其他托管服务吗？**
A: 可以，任何静态网页托管服务都可以。参考 `UPLOAD_GUIDE.md` 中的其他方案。

**Q: 需要修改文档内容吗？**
A: 文档已基于实际代码撰写，可以直接使用。如需修改：
- 更新日期
- 联系邮箱 (souther217@gmail.com)
- 其他自定义内容

## 📋 检查清单

上传完成后确认：

- [ ] GitHub 仓库已创建
- [ ] 3个 HTML 文件已上传
- [ ] GitHub Pages 已启用
- [ ] 网址可以访问
- [ ] 应用代码 URL 已更新
- [ ] 应用中测试链接成功

## 🎉 完成！

上传成功后，您的隐私政策和服务条款就可以公开访问了。

下一步：
1. ✅ 在 App Store Connect 配置订阅产品
2. ✅ 更新应用描述
3. ✅ 准备提交审核

---

**需要帮助？** 查看详细的 `UPLOAD_GUIDE.md` 文档。
