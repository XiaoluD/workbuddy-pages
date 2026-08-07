# WorkBuddy Pages

> WorkBuddy AI 生成的静态页面，通过 GitHub Pages 自动发布为永久链接。

**在线地址**：https://xiaolud.github.io/workbuddy-pages/

---

## 这是什么

由 WorkBuddy 对话生成的 HTML 页面（报告、仪表盘、图表等），推送到此仓库后自动部署上线。适合正式交付场景，链接永久有效，不像 CloudStudio 临时沙箱那样会过期。

---

## 怎么用

### 方式一：对话让 WorkBuddy 帮你做（推荐）

直接在 WorkBuddy 里说：

| 你要做什么 | 直接说 |
|---|---|
| 生成并部署新页面 | 「帮我做一个 XX 报告页面，部署到 workbuddy-pages」 |
| 部署已有的 HTML | 「帮我把这个页面推送到 workbuddy-pages」 |
| 更新现有页面 | 「帮我更新 report.html，推送到 workbuddy-pages」 |

WorkBuddy 会生成 HTML → git push → 自动上线，一分钟搞定。

### 方式二：手动推送

```bash
git clone https://github.com/XiaoluD/workbuddy-pages.git
cd workbuddy-pages
# 放入你的 HTML 文件
git add .
git commit -m "add new page"
git push origin main
```

推送后 GitHub Pages 自动编译部署，访问 `https://xiaolud.github.io/workbuddy-pages/文件名.html`。

---

## 与 CloudStudio 的区别

| | CloudStudio | GitHub Pages |
|---|---|---|
| 链接 | 临时沙箱 | **永久有效** ✅ |
| 交付客户 | 不适合 | **适合** ✅ |
| 版本管理 | ❌ | ✅ git 自动记录 |
| 部署方式 | WorkBuddy 内置工具 | git push |

---

## 部署原理

```
WorkBuddy 生成 HTML
    ↓
git push → main 分支
    ↓
GitHub Actions 自动构建
    ↓
https://xiaolud.github.io/workbuddy-pages/ 上线
```
