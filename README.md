# AI 碎碎念 · 博客搭建手册

> 为非程序员准备的、从零到上线的一份保姆级操作指南。
> 只要照着命令敲，大约 1 小时内可以让 `https://19800818xyz.github.io` 上线。

---

## 📁 这个目录里都有什么

```
myblog/
├── hugo.toml                        ← 站点主配置（标题、菜单、评论等）
├── .gitignore                       ← Git 忽略文件清单
├── archetypes/                      ← 新建文章的模板
│   ├── default.md
│   └── post.md
├── content/                         ← 所有正文内容
│   ├── post/hello-ai/index.md       ← 第一篇示例文章
│   ├── about/index.md               ← "关于"页面
│   └── search.md                    ← 搜索页入口
├── layouts/                         ← 自定义模板（Mermaid 支持）
│   ├── _default/_markup/
│   │   └── render-codeblock-mermaid.html
│   └── partials/footer/custom.html
├── .github/workflows/hugo.yml       ← GitHub Actions 自动部署
└── README.md                        ← 你正在读的这个文件
```

---

## 🧰 第 0 步：安装基础工具（一次性）

你需要在本机装好这三件东西：

### 1. Git

- Windows：下载 [Git for Windows](https://git-scm.com/download/win)，一路下一步即可。
- macOS：打开"终端"输入 `git --version`，系统会弹窗提示安装。

### 2. Hugo（**一定要装 extended 版本**，Stack 主题需要）

- Windows（推荐用 Scoop）：
  ```powershell
  # 先装 scoop（管理员权限打开 PowerShell）
  Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
  irm get.scoop.sh | iex

  # 用 scoop 装 Hugo
  scoop install hugo-extended
  ```
- macOS：
  ```bash
  brew install hugo
  ```
- 验证：终端输入 `hugo version`，看到 `extended` 字样就对了。

### 3. 一个顺手的 Markdown 编辑器（可选）

推荐 [Typora](https://typoraio.cn/) 或 VS Code。不装也行，记事本也能写。

---

## 🐙 第 1 步：在 GitHub 上创建仓库

1. 登录 [GitHub](https://github.com/)。
2. 点右上角 `+` → **New repository**。
3. 仓库名 **必须**是：`19800818xyz.github.io`（和你的用户名一致，这是 GitHub Pages 个人主页专用命名规则）。
4. 设置为 **Public**。
5. ⚠️ 先不要勾 "Add a README"、"Add .gitignore"、"Choose a license"（我们本地已经有 README 了，免得冲突）。
6. 点 **Create repository**。

---

## 💻 第 2 步：把本地项目推到 GitHub

把本项目整个 `myblog/` 文件夹 **复制**到你平时放代码的地方，比如 `D:\code\myblog\` 或 `~/code/myblog/`。
然后打开终端，**cd 到那个位置**，执行：

```bash
# 初始化 Git 仓库
git init
git branch -M main

# 把 Stack 主题当作子模块加入 ← 关键一步
git submodule add https://github.com/CaiJimmy/hugo-theme-stack.git themes/hugo-theme-stack

# 关联远程仓库（注意替换成你的，如果我写错了）
git remote add origin https://github.com/19800818xyz/19800818xyz.github.io.git

# 提交并推送
git add .
git commit -m "初始化博客：Hugo + Stack"
git push -u origin main
```

首次 push 会让你登录 GitHub，按提示操作即可（Windows 会弹浏览器授权）。

---

## 🚀 第 3 步：开启 GitHub Pages

1. 打开仓库页面 → 点上方 **Settings**。
2. 左侧找到 **Pages**。
3. **Build and deployment** → **Source** 改成 **GitHub Actions**。
4. 保存即可。（不需要做其它设置）

推完 `main` 分支几秒后，仓库主页上方会出现 **Actions** 标签，点进去能看到正在运行的工作流。
绿色勾代表部署成功，大约 1~2 分钟内你访问 `https://19800818xyz.github.io` 就能看到博客了。

---

## 👀 第 4 步：本地实时预览（推荐）

每次修改后，不需要 push 就能看效果：

```bash
hugo server -D
```

然后浏览器打开 `http://localhost:1313`，保存文件后页面自动刷新。
`-D` 是把 `draft: true` 的草稿也显示出来。

---

## ✍️ 第 5 步：写一篇新文章

```bash
hugo new post/我的第二篇文章/index.md
```

这会用 `archetypes/post.md` 模板帮你生成一个新文件。
打开它，把 `draft: true` 改成 `draft: false` 就能发布。

目录结构推荐用 **文件夹 + index.md** 的形式（叫 page bundle），这样图片可以直接放同目录下：

```
content/post/我的第二篇文章/
├── index.md
├── cover.jpg
└── diagram.png
```

然后在 index.md 顶部加一行 `image: "cover.jpg"`，封面图就自动显示了。

---

## 🎨 第 6 步：放一张你的头像（强烈推荐）

找一张正方形头像，命名为 `avatar.png`，放到：

```
myblog/assets/img/avatar.png
```

`assets/` 目录 Hugo 建站初始没有，**自己创建就行**。
推完之后，侧边栏那个大圆就变成你的头像了。

---

## 💬 第 7 步：配 Giscus 评论（部署成功后再做）

Giscus 利用 GitHub Discussions 做评论区，对你来说零成本零运维。

1. 到仓库 **Settings → General → Features**，勾选 **Discussions**。
2. 到 [https://github.com/apps/giscus](https://github.com/apps/giscus) 安装 Giscus App 到你的仓库。
3. 打开 [https://giscus.app](https://giscus.app)，语言选"简体中文"，按页面提示操作：
   - 仓库填：`19800818xyz/19800818xyz.github.io`
   - Discussion 分类：选 `Announcements`（或自己建一个 `Comments`）
   - 页面映射：选 **pathname**
4. 页面会生成一段代码，里面有 4 个值你需要复制下来：
   - `data-repo`
   - `data-repo-id`
   - `data-category`
   - `data-category-id`
5. 打开 `hugo.toml`，找到 `[params.comments.giscus]`，把对应的值填进去：
   ```toml
   repo = "19800818xyz/19800818xyz.github.io"
   repoID = "这里填 data-repo-id"
   category = "Announcements"
   categoryID = "这里填 data-category-id"
   ```
6. 提交推送。每篇文章底部就会出现评论框。

---

## 🧮 关于数学公式 · Mermaid 图 · 代码高亮

已经全部配好，你在文章里可以直接用：

**数学公式**（记得 front matter 里加 `math: true`）：
```markdown
行内公式：质能方程 $E=mc^2$
块级公式：
$$
\nabla \cdot \mathbf{E} = \frac{\rho}{\varepsilon_0}
$$
```

**Mermaid 图表**：
```markdown
​```mermaid
flowchart LR
  A --> B --> C
​```
```

**代码高亮**：
```markdown
​```python
def hello():
    print("hi")
​```
```

---

## 🧭 常见问题速查

| 现象 | 可能原因 / 解决 |
| --- | --- |
| 推送成功但页面 404 | GitHub Pages 部署需要 1~2 分钟；看 Actions 里工作流是否绿勾 |
| 侧边栏头像不显示 | `assets/img/avatar.png` 没有放；放进去重新 `git push` |
| 公式渲染成原始 `$...$` | 文章 front matter 里漏了 `math: true` |
| 本地预览报错 "extended needed" | 装的是普通版 Hugo，改装 `hugo-extended` |
| 评论框空白 | Giscus 的 4 个 ID 没填对；重新去 giscus.app 生成 |
| 改完主题配置没生效 | 清除 `/public/` 和 `/resources/_gen/` 重新 `hugo server` |

---

## 📚 延伸阅读

- Hugo 官方文档：https://gohugo.io/documentation/
- Stack 主题文档：https://stack.jimmycai.com/config/
- Giscus：https://giscus.app
- KaTeX 语法：https://katex.org/docs/supported.html

---

祝你写得开心。第一篇文章能让多少人恍然大悟，决定这个博客能走多远。

—— 配置模板作者 Claude · 2026-04-18
