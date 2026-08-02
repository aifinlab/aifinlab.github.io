# Liwen Zhang Academic Homepage

这是张立文教授与 AIFin Lab 的 GitHub Pages 学术主页，基于 Jekyll / Academic Pages 构建，发布地址为 <https://aifinlab.github.io/>。

## 页面与文件对应关系

| 网页栏目 | 内容文件 |
| --- | --- |
| Home | `_pages/about.md` |
| Publications | `_pages/publications.md` |
| Teaching | `_pages/teaching.md` |
| Supervision | `_pages/supervision.md` |
| Lab Members | `_pages/lab-members.md` |
| Talks | `_pages/talks.md` |
| 顶部导航 | `_data/navigation.yml` |
| 姓名、头像、邮箱等全站信息 | `_config.yml` |
| 本站新增样式 | `_sass/layout/_profile_custom.scss` |

## 日常更新方法

1. 在 GitHub 仓库中打开要更新的 Markdown 文件。
2. 点击右上角铅笔图标（Edit this file）。
3. 修改正文；不要删除文件最上方两行 `---` 之间的页面配置。
4. 选择 **Commit changes**，填写简短说明并提交到新分支。
5. 创建 Pull Request，预览改动无误后合并到 `master`。
6. GitHub Pages 通常会在数分钟内自动更新网站。

## 添加常见内容

### 添加论文

在 `_pages/publications.md` 对应小节中复制一条现有论文，并替换题目、作者、状态、论文链接和代码链接。尚未正式接收的论文应放在 **Some Preprints**；正式发表或已接收论文放在 **Publications / Accepted Manuscripts**。

### 添加实验室成员

在 `_pages/lab-members.md` 中按照现有成员卡片模板填写姓名、身份、研究方向、个人主页和起止年份。发布前请获得成员同意，并核对英文姓名和链接。

### 添加报告

在 `_pages/talks.md` 的 **Industry Lectures** 或 **Academic Conferences & Seminars** 下复制一条现有记录，统一使用“日期 — 报告题目 — 主办单位/地点 — 链接”的格式。

### 更新首页研究路线

编辑 `_pages/about.md` 中的 **Research RoadMap**。四个阶段分别覆盖数据基础、模型与推理、评测与安全、决策与应用；新增项目时同时补充可访问的论文或代码链接。

## 本地预览

建议使用 Ruby 3.1 或更高版本：

```bash
bundle config set --local path 'vendor/bundle'
bundle install
bundle exec jekyll serve -l -H localhost
```

浏览器打开 <http://localhost:4000>。修改 `_config.yml` 后需要重启 Jekyll。

## 发布检查

提交前至少确认：

- 六个导航链接均可打开；
- 新增论文和报告的外部链接有效；
- 中英文姓名、单位、年份和论文状态准确；
- 没有公开学生的私人联系方式；
- `bundle exec jekyll build --strict_front_matter` 能成功运行。

模板版权和许可证信息见 [`LICENSE`](LICENSE)。
