# Liwen Zhang Academic Homepage

这是张立文教授与 AIFin Lab 的 GitHub Pages 学术主页，基于 Jekyll / Academic Pages 构建，发布地址为 <https://aifinlab.github.io/>。

## 页面与文件对应关系

| 网页栏目 | 主要内容文件 |
| --- | --- |
| Home | `_pages/about.md` |
| Publications | `_data/publications.yml` |
| Teaching | `_data/teaching.yml` |
| Supervision 学生与导师 | `_data/people.yml` |
| Supervision 招生说明 | `_pages/supervision.md` |
| Lab Members | `_data/people.yml` |
| Talks | `_data/talks.yml` |
| 顶部导航 | `_data/navigation.yml` |
| 姓名、头像、邮箱等全站信息 | `_config.yml` |
| 本站新增样式 | `_sass/layout/_profile_custom.scss` |
| 完整改版与制作规范 | `docs/个人学术主页设计与制作说明.md` |

## 日常更新方法

1. 在 GitHub 仓库中打开要更新的 Markdown 文件。
2. 点击右上角铅笔图标（Edit this file）。
3. 修改对应的 Markdown 或 YAML 数据；不要改变现有缩进，也不要删除 Markdown 文件最上方两行 `---` 之间的页面配置。
4. 选择 **Commit changes**，填写简短说明并提交到新分支。
5. 创建 Pull Request，预览改动无误后合并到 `master`。
6. GitHub Pages 通常会在数分钟内自动更新网站。

## 添加常见内容

### 添加论文

在 `_data/publications.yml` 的 `publications` 或 `preprints` 中复制一条现有记录，再替换年份、题目、作者、会议/期刊和资源链接。正式发表或已接收论文放在 `publications`；尚未正式接收的论文放在 `preprints`。页面会自动按类型和年份生成统一列表。

### 添加实验室成员

在 `_data/people.yml` 对应分组的 `members` 中增加成员。Supervision 分组强调指导关系、培养层次和研究方向；Lab Members 分组强调实验室岗位、工作职责和参与项目。发布前请获得成员同意，并核对姓名、照片和链接。

### 添加报告

在 `_data/talks.yml` 的 `academic.items` 或 `industry.items` 中复制一条记录，填写日期、活动、地点、题目和可选链接。页面会自动使用统一的讲座清单格式。

### 添加课程或教学奖项

在 `_data/teaching.yml` 的 `courses` 中增加一次实际开课记录；同一课程在不同学期讲授时分别记录。在 `awards` 中增加经过核验的教学奖项。不要保留“待补充学期”等占位信息作为正式发布内容。

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
