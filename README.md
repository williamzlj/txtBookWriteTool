# txtBookWriteTool

English | [简体中文](#简体中文)

txtBookWriteTool is a local writing tool for Chinese writers. It uses a regular folder as your manuscript directory, writes in `.txt` / `.md` files with Markdown syntax, and can merge everything into a book and export to PDF / HTML / Markdown.

If you write long-form content — novels, papers, technical docs — and want a tool that keeps everything as plain text files on your own disk, with zero installation, zero cloud, and zero lock-in, this is for you.

## Features

- **Single-file HTML app**: one `txtBookWriteTool.html`, double-click to open. No install, no dependencies, no network.
- **Folder-based projects**: pick any local folder as your book root; all `.txt` / `.md` files inside are auto-managed as a directory tree.
- **Four work modes**: Edit (Markdown editor + live preview), Preview, Read (merge all files into one continuous book), Outline (drag-and-drop chapter reordering).
- **Smart file numbering**: three-digit prefixes (`110.txt`, `120-正文.txt`) with 10-increment spacing — insert new chapters anytime without renumbering everything.
- **Draft management**: files / folders prefixed with `_` are drafts — fully editable and searchable, but excluded from book view and exports.
- **Writing aids**: image paste & drop (auto-saved to `assets/`), table insert, color palette, find & replace (single file or whole project), full-width space, comments, merge & split files.
- **Book layout settings**: book title, subtitle, author, date, cover page, TOC page, chapter page breaks, auto heading numbering, first-line indent.
- **Style customization**: built-in color presets, custom fonts (13 common font stacks), book themes (classic / modern / academic / phone), user-defined CSS.
- **Export**: PDF (with headers, footers, page numbers, cover, TOC), standalone HTML, and merged Markdown.
- **Data safety**: recycle bin (`.trash`), version history (`.history`, last 40 versions per file), history follows rename/move.
- **Local & private**: everything lives in your folder — `.trash`, `.history`, `assets`, `settings.json`, `style.css` are all visible and portable. Backup = copy the folder.
- **Auto-resume**: reopens the last folder and last edited file automatically.
- **Task & outline overview**: cross-file task list filtering, outline view, click-to-jump navigation.
- **Encryption**: AES-256-GCM text encryption/decryption for sensitive content.

## Requirements

| Item | Requirement |
|---|---|
| Browser | Microsoft Edge or Google Chrome (File System Access API support required) |
| OS | Windows 10 / 11 (also works on macOS / Linux with Chrome or Edge) |
| Runtime | None — pure HTML / CSS / JavaScript, no framework, no build step |

## Quick Start

1. Download `txtBookWriteTool.html` from the [latest release](https://github.com/williamzlj/txtBookWriteTool/releases/latest)
2. Open it with Edge or Chrome (double-click, or drag into the browser)
3. Click **「选择写作文件夹」** and pick a local folder — click **Allow** in the permission dialog
4. Click **「新建 txt」** to start writing — use Markdown syntax, preview updates in real time on the right
5. Switch to **「大纲」** mode to drag-and-drop reorder chapters
6. Switch to **「阅览」** mode to see the merged book, then **「导出 PDF」** to produce the final file

## Usage

### File numbering

Files are sorted by a three-digit numeric prefix: `110.txt` comes before `120-正文.txt`. The number controls sort order; the text after the dash is just a label. New files auto-get the max number + 10, leaving room to insert later.

Folders can also be numbered (`120-正文`) to interleave with files, e.g. `110-序言.txt` → `120-正文/` → `130-后记.txt`.

### Drafts

Prefix a file or folder name with `_` (e.g. `_灵感.txt`) to mark it as a draft. Drafts are editable and searchable but **excluded** from Read mode and all exports. Remove the `_` to promote it back to a regular file.

### Four modes

| Mode | What it does |
|---|---|
| **Edit** | Markdown editor on the left, live preview on the right. Auto-saves (debounced 900 ms). |
| **Preview** | Preview only — no editor, clean reading view of the current file. |
| **Read** | Merges the whole project (by number order) into one continuous book. Left side = table of contents. Final preview before PDF export. |
| **Outline** | Card overview of the entire book. Folders = volumes, files = chapters. Drag cards to reorder; numbers auto-adjust. |

### Images

Paste or drag an image into the editor — it's auto-saved to the project's `assets/` folder and a Markdown reference is inserted. Syntax: `![](path =600x400 center)` — width/height are optional, alignment can be `center` / `left` / `right`.

### Merge & split

- **Merge**: Ctrl+click to select multiple files → merge into the first one, others go to recycle bin.
- **Split**: split by heading level (`#`) or line keyword into multiple files (`xxx-split-0.txt`, `xxx-split-1.txt`…). Original goes to recycle bin (recoverable).

### Book layout (排版设置)

Configure in the **排版设置** dialog: book title (blank = folder name), subtitle, author, date, cover page, TOC, chapter page breaks, heading auto-numbering, first-line indent. Settings are saved to `settings.json` in the project root.

### Export formats

| Format | How |
|---|---|
| **PDF** | In Read mode, click 导出 PDF → in the print dialog choose "Save as PDF". Includes cover, TOC, headers, page numbers. |
| **HTML** | Standalone single-file HTML with left-side TOC and your custom styles. |
| **Markdown** | Merges all files (by order) into one `.md` file. |

## Data files (all in your project folder)

| File / Folder | Purpose |
|---|---|
| `settings.json` | Book layout settings (title, author, pagination options) |
| `style.css` | Custom styles (color scheme, fonts, book theme) |
| `assets/` | Images pasted or dragged into the editor |
| `.trash/` | Recycle bin — deleted files and merge/split leftovers (with `.tbwt` suffix) |
| `.history/` | Auto-saved version history (last 40 versions per file, with `.tbwt` suffix) |

To move to another computer or back up: copy the whole project folder. Everything is plain text — Git-friendly, human-readable, no lock-in.

## FAQ

**Q: Why `.txt` instead of `.md`?**
Windows Explorer can preview `.txt` files natively. The tool parses them as Markdown anyway, so you get the best of both: system-level preview + rich Markdown rendering. You can also use `.md` if you prefer.

**Q: Does it work offline?**
Yes. The tool is a single HTML file with no network calls. All data stays in your local folder. Marked.js is bundled inline.

**Q: Where is my data stored?**
Everything is in the folder you selected. There is no cloud, no database server, no hidden storage. The browser's IndexedDB only remembers which folder you last opened (per HTML file URL).

**Q: Can I use it for multiple projects?**
Yes. Copy `txtBookWriteTool.html` and rename each copy with a project note (e.g. `txtBookWriteTool-小说.html`). Each copy remembers its own working folder independently (IndexedDB is keyed by the HTML file's URL).

**Q: Mobile support?**
The tool requires the File System Access API, which is desktop-only (Edge / Chrome on Windows / macOS / Linux). A full-screen notice is shown on mobile.

## License

[MIT](LICENSE)

---

<a id="简体中文"></a>
## 简体中文

txtBookWriteTool 是一款面向中文写作者的本地写作工具。它以一个普通文件夹作为书稿目录，用 `.txt` / `.md` 文件按 Markdown 语法写作，最终可合并成书、导出 PDF / HTML / Markdown。

如果你在写长篇内容——小说、论文、技术文档——希望所有内容都以纯文本文件存在自己的磁盘上，零安装、零云端、零锁定，这个工具就是为你准备的。

## 功能特性

- **单文件 HTML 应用**：一个 `txtBookWriteTool.html`，双击即开。无需安装、无需依赖、无需联网。
- **文件夹即项目**：选择任意本地文件夹作为书稿根目录，其内所有 `.txt` / `.md` 文件自动按目录树管理。
- **四种工作模式**：编辑（Markdown 编辑器 + 实时预览）、预览、阅览（全部文件合并成一本连续的书）、大纲（拖拽调整章节顺序）。
- **智能文件编号**：三位数字前缀（`110.txt`、`120-正文.txt`），以 10 为增量间隔——随时插入新章节，无需全部重排。
- **草稿管理**：文件名以 `_` 开头即为草稿（如 `_灵感.txt`），可正常编辑搜索，但**不参与**阅览和导出。
- **写作辅助**：图片粘贴拖入（自动存入 `assets/`）、表格插入、调色盘、查找替换（单文件或全项目）、全角空格、注释、文件合并与拆分。
- **成书排版设置**：书名、副标题、作者、日期、封面页、目录页、章节分页、标题自动编号、首行缩进。
- **样式定制**：内置配色预设、自定义字体（13 种常见字体栈）、书主题（经典 / 现代 / 学术 / 手机）、用户自定义 CSS。
- **导出**：PDF（含页眉页脚、页码、封面、目录）、独立 HTML、合并 Markdown。
- **数据安全**：回收站（`.trash`）、历史版本（`.history`，每文件保留最近 40 版），重命名/移动时历史跟随。
- **本地私密**：所有数据都在你的文件夹内——`.trash`、`.history`、`assets`、`settings.json`、`style.css` 全部可见可移植。备份 = 复制文件夹。
- **自动恢复**：打开页面自动恢复上次的文件夹和上次编辑的文件。
- **任务与大纲总览**：跨文件待办筛选、大纲视图、点击跳转。
- **加密**：AES-256-GCM 文本加解密，保护敏感内容。

## 环境要求

| 项目 | 要求 |
|---|---|
| 浏览器 | Microsoft Edge 或 Google Chrome（需支持 File System Access API） |
| 操作系统 | Windows 10 / 11（macOS / Linux 上的 Chrome 或 Edge 也可用） |
| 运行时 | 无——纯 HTML / CSS / JavaScript，无框架、无构建步骤 |

## 快速开始

1. 从[最新 Release](https://github.com/williamzlj/txtBookWriteTool/releases/latest) 下载 `txtBookWriteTool.html`
2. 用 Edge 或 Chrome 打开（双击，或拖入浏览器）
3. 点击 **「选择写作文件夹」**，选择一个本地文件夹——在权限弹窗中点 **允许**
4. 点击 **「新建 txt」** 开始写作——用 Markdown 语法，右侧实时预览
5. 切换到 **「大纲」** 模式，拖拽卡片调整章节顺序
6. 切换到 **「阅览」** 模式查看合并后的成书效果，点击 **「导出 PDF」** 生成最终文件

## 使用说明

### 文件编号

文件按三位数字前缀排序：`110.txt` 在 `120-正文.txt` 之前。数字决定排序，横线后的文字仅作标签。新建文件自动取当前最大编号 +10，留出插入空位。

文件夹也可编号（如 `120-正文`），与文件统一排序，实现 `110-序言.txt` → `120-正文/` → `130-后记.txt` 的穿插结构。

### 草稿

文件名或文件夹名以 `_` 开头（如 `_灵感.txt`）即为草稿。草稿可正常编辑和搜索，但**不参与**阅览模式和所有导出。去掉 `_` 前缀即恢复为正式文件。

### 四种模式

| 模式 | 说明 |
|---|---|
| **编辑** | 左侧 Markdown 编辑器，右侧实时预览。自动保存（防抖 900ms）。 |
| **预览** | 仅预览——不显示编辑器，纯净阅读当前文件。 |
| **阅览** | 按编号顺序将整个项目合并成一本连续的书。左侧生成目录。导出 PDF 前的最终预览。 |
| **大纲** | 全书卡片纵览。文件夹是卷、文件是章节。拖动卡片调整顺序，编号自动重排。 |

### 图片

粘贴或拖入图片——自动存入项目的 `assets/` 文件夹并插入 Markdown 引用。语法：`![](路径 =600x400 center)`——宽高可选，对齐用 center / left / right。

### 合并与拆分

- **合并**：Ctrl+点击多选文件 → 合并到第一个文件，其余移入回收站。
- **拆分**：按标题级别（`#`）或行首关键词拆成多个文件（`xxx-split-0.txt`、`xxx-split-1.txt`…）。原文件移入回收站（可恢复）。

### 成书排版（排版设置）

在 **排版设置** 对话框中配置：书名（留空=文件夹名）、副标题、作者、日期、封面页、目录页、章节分页、标题自动编号、首行缩进。设置保存在项目根目录的 `settings.json`。

### 导出格式

| 格式 | 方式 |
|---|---|
| **PDF** | 阅览模式下点「导出 PDF」→ 打印对话框选「另存为 PDF」。含封面、目录、页眉、页码。 |
| **HTML** | 独立单文件 HTML，含左侧目录和自定义样式。 |
| **Markdown** | 按顺序合并所有文件为一个 `.md` 文件。 |

## 数据文件（全部在项目文件夹内）

| 文件 / 文件夹 | 作用 |
|---|---|
| `settings.json` | 成书排版设置（书名、作者、分页选项等） |
| `style.css` | 自定义样式（配色、字体、书主题） |
| `assets/` | 编辑器中粘贴或拖入的图片 |
| `.trash/` | 回收站——删除的文件和合并/拆分的剩余文件（带 `.tbwt` 后缀） |
| `.history/` | 自动保存的历史版本（每文件最近 40 版，带 `.tbwt` 后缀） |

换电脑或备份：复制整个项目文件夹即可。所有内容都是纯文本——Git 友好、人类可读、无锁定。

## 常见问题

**Q：为什么用 `.txt` 而不是 `.md`？**
Windows 资源管理器可以原生预览 `.txt` 文件。工具本身按 Markdown 解析，两全其美：系统级预览 + 富文本 Markdown 渲染。如果你偏好 `.md` 也完全可以。

**Q：离线能用吗？**
能。工具是单个 HTML 文件，无任何网络请求。所有数据都在本地文件夹。Marked.js 已内联打包。

**Q：数据存在哪里？**
所有数据都在你选择的文件夹里。没有云端、没有数据库服务器、没有隐藏存储。浏览器的 IndexedDB 只记住你上次打开的文件夹（按 HTML 文件 URL 隔离）。

**Q：能用于多个项目吗？**
能。复制 `txtBookWriteTool.html` 并按项目改名（如 `txtBookWriteTool-小说.html`）。每个副本各自独立记忆工作目录（IndexedDB 按 HTML 文件 URL 隔离）。

**Q：手机能用吗？**
工具需要 File System Access API，仅桌面端可用（Windows / macOS / Linux 上的 Edge / Chrome）。手机端会显示全屏提示。

## 许可证

[MIT](LICENSE)
