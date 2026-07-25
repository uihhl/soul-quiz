# 🎭 你与哪位不朽的主角共享灵魂？

> Which immortal protagonist shares your soul?

一个移动端优先的趣味人格测试网站。回答 10 道选择题，发现你的灵魂与 12 位文学与历史上的不朽人物中——哪一位共鸣最深。

**[🔗 在线体验]()** ← 部署后更新此链接

---

## ✨ 功能

- 🎯 **10 道精心设计的选择题**，根据你的选择匹配灵魂角色
- 👥 **12 位高人气角色**：小王子、哈姆雷特、斯嘉丽、霍尔顿、比尔·盖茨、福尔摩斯、伊丽莎白、盖茨比、哈利·波特、堂吉诃德、乔布斯、孙悟空
- 🌐 **中英双语**，一键切换
- 📊 **结果页**展示：角色介绍、匹配度、灵魂金句、性格标签、推荐阅读
- 🖼 **Canvas 生成分享海报**，长按保存分享到朋友圈
- 📱 **移动端优先**，渐变背景 + 大卡片设计，明亮显眼
- ⚡ **零依赖**，单个 HTML 文件即可运行

---

## 🚀 部署到 GitHub Pages

### 方法一：直接上传

1. 在 GitHub 新建仓库（如 `soul-quiz`）
2. 将本目录下的文件推送到仓库：
   ```bash
   cd quiz-site
   git init
   git add index.html README.md
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/你的用户名/soul-quiz.git
   git push -u origin main
   ```
3. 在仓库 **Settings → Pages** 中：
   - Source 选择 `Deploy from a branch`
   - Branch 选择 `main`，文件夹选择 `/ (root)`
   - 点击 Save
4. 等待 1-2 分钟，访问 `https://你的用户名.github.io/soul-quiz/`

### 方法二：使用 gh CLI

```bash
cd quiz-site
git init
git add .
git commit -m "Initial commit"
gh repo create soul-quiz --public --push --source .
gh api repos/$(gh auth status 2>&1 | head -1)/pages -F source='{"branch":"main","path":"/"}'
```

---

## 🛠 本地开发

直接用浏览器打开 `index.html` 即可预览。

```bash
open index.html        # macOS
start index.html       # Windows
xdg-open index.html    # Linux
```

或用任意静态服务器：

```bash
npx serve .            # Node.js
python3 -m http.server # Python
```

---

## 📂 文件结构

```
quiz-site/
├── index.html    # 主文件（HTML + CSS + JS）
└── README.md     # 本文件
```

---

## 🎨 自定义

### 添加/修改角色

编辑 `index.html` 中 `characters` 数组，每个角色包含：
- `id` - 唯一标识
- `nameZH` / `nameEN` - 中英文名
- `emoji` - 角色图标
- `color` / `colorDark` - 主题色（用于结果卡和海报）
- `source` - 出处
- `descZH` / `descEN` - 角色描述
- `traitsZH` / `traitsEN` - 性格标签数组
- `quoteZH` / `quoteEN` - 灵魂金句
- `bookZH` / `bookEN` - 推荐阅读

### 修改题目

编辑 `questions` 数组，每个选项的 `scores` 对象键为角色 ID，值为得分。

---

## 📄 License

MIT — 自由使用和修改。
