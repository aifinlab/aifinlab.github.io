# Liwen Zhang Academic Homepage

张立文教授与 AIFin Lab 的个人学术主页，基于 Jekyll、Academic Pages 和 GitHub Pages 构建。

- 网站地址：<https://aifinlab.github.io/>
- GitHub 仓库：<https://github.com/aifinlab/aifinlab.github.io>
- 完整设计规范：[`docs/个人学术主页设计与制作说明.md`](docs/个人学术主页设计与制作说明.md)

## 网站结构

网站包含六个核心页面。顶部不显示独立的 Home，点击左上角 **Liwen Zhang (张立文) | AIFin Lab** 返回首页。

| 页面 | 路径 | 内容来源 |
| --- | --- | --- |
| Home | `/` | `_pages/about.md` |
| Publications | `/publications/` | `_data/publications.yml` |
| Teaching | `/teaching/` | `_data/teaching.yml` |
| Supervision | `/supervision/` | `_data/people.yml`、`_pages/supervision.md` |
| Lab Members | `/lab-members/` | `_data/people.yml` |
| Talks | `/talks/` | `_data/talks.yml` |

其他主要文件：

| 功能 | 文件 |
| --- | --- |
| 全站姓名、头像、邮箱、网址 | `_config.yml` |
| 顶部导航 | `_data/navigation.yml` |
| 页脚 | `_includes/footer.html` |
| 论文条目组件 | `_includes/publication-entry.html` |
| 导师/负责人组件 | `_includes/featured-person.html` |
| 成员卡片组件 | `_includes/member-card.html` |
| 课程条目组件 | `_includes/teaching-entry.html` |
| 讲座条目组件 | `_includes/talk-entry.html` |
| 主页和内容页面样式 | `_sass/layout/_profile_custom.scss` |
| 页脚样式 | `_sass/layout/_footer.scss` |

## 维护原则

1. 优先修改 `_data/*.yml` 中的数据，不要为每条论文或成员复制页面代码。
2. YAML 使用两个空格缩进，不允许使用 Tab。
3. 不要删除 Markdown 文件开头两组 `---` 之间的 Front Matter。
4. 不要直接修改 `_site/`，它是构建生成目录，会在下次构建时被覆盖。
5. 不要直接修改压缩后的 CSS 或 JavaScript。
6. 论文状态、作者顺序、任职、奖项和成员去向必须经过核验。
7. 发布成员姓名、照片、研究方向和去向前，应获得本人同意。
8. 没有数据的人员分组会自动隐藏，不需要创建虚构占位成员。

## 更新首页

首页内容位于：

```text
_pages/about.md
```

可以在这里更新：

- 中英文个人简介；
- Current Appointments；
- Education & Experience；
- 招生简介；
- Research Roadmap；
- Selected Research Systems；
- Selected Honors。

首页按钮目前包括 Publications、Join the Group、GitHub 和 Official Profile。按钮链接也在该文件中维护。

全站通用个人资料位于 `_config.yml` 的 `author` 字段，包括：

```yaml
author:
  avatar: "/images/profile/liwen-zhang.webp"
  name: "Liwen Zhang (张立文)"
  bio: "Professor of Statistics | AI + Finance | Large Language Models"
  location: "Shanghai, China"
  employer: "Shanghai University of Finance and Economics"
  uri: "https://example.com"
  email: "name@example.com"
  github: "aifinlab"
```

建议最终将头像保存到 `images/profile/`，避免依赖外部学校网站的图片地址。

## 更新论文

论文数据位于：

```text
_data/publications.yml
```

### 分类规则

- `publications`：正式发表或已经正式接收的论文；
- `preprints`：尚未正式接收的预印本；
- `books`：专著。

论文从 Preprint 转为正式发表后，应将记录从 `preprints` 移动到 `publications`，不要在两个类别中重复保留。

### 论文记录示例

```yaml
publications:
  - year: 2026
    venue_short: "NAACL"
    title: "Paper Title"
    authors: "First Author, Second Author, Liwen Zhang."
    self_author: "Liwen Zhang"
    author_mark: "†"
    venue: "NAACL 2026, Long Papers."
    paper: "https://example.com/paper"
    code: "https://github.com/example/project"
    data: "https://github.com/example/project"
    model: "https://example.com/model"
```

字段说明：

| 字段 | 是否必填 | 说明 |
| --- | --- | --- |
| `year` | 是 | 用于年份分组和排序 |
| `title` | 是 | 论文正式标题 |
| `authors` | 是 | 完整作者字符串 |
| `self_author` | 是 | 在作者字符串中需要加粗、下划线的姓名形式 |
| `author_mark` | 否 | `*` 表示共同贡献，`†` 表示通讯作者，使用前须核验 |
| `venue_short` | 否 | 会议或期刊简称；Preprint 可不填 |
| `venue` | 是 | 完整发表或预印本信息 |
| `paper` | 否 | 论文、DOI、出版社或 arXiv 链接 |
| `code` | 否 | 代码仓库 |
| `data` | 否 | 数据集 |
| `model` | 否 | 模型地址 |
| `project` | 否 | 项目主页 |

`publications` 和 `preprints` 内部应保持年份倒序。同一年内将最新或最重要的记录放在前面。

## 更新课程和教学奖项

课程与教学奖项位于：

```text
_data/teaching.yml
```

### 课程记录示例

```yaml
courses:
  - term: "2025–2026 秋"
    institution: "上海财经大学"
    code: "105494"
    name: "概率论"
    school: "统计与数据科学学院"
    audience: "本科生必修课"
    role: "授课教师"
    url: "https://example.com/course"
```

- 每次实际开课单独记录；
- 同一课程在不同学期讲授时不要合并；
- 课程按时间从早到晚排列；
- `code`、`institution` 和 `url` 没有时可以省略；
- 正式发布前必须替换“待补充学期”。

### 教学奖项示例

```yaml
awards:
  - year: 2025
    title: "教学奖项正式名称"
    organization: "颁发单位"
    description: "可选的简短说明"
```

这里只放教学、课程建设或学生指导相关奖项，不放普通科研论文奖。

## 更新 Supervision

Supervision 展示张立文教授直接指导的学生，数据位于 `_data/people.yml` 的：

```yaml
supervision_groups:
```

现有分组：

- `postdocs`：博士后；
- `phd`：博士研究生；
- `masters`：硕士研究生；
- `interns`：研究实习生；
- `alumni`：已毕业学生。

### 指导学生示例

将成员添加到对应分组的 `members` 中：

```yaml
  - key: "phd"
    title: "PhD Students / 博士研究生"
    members:
      - name_en: "English Name"
        name_zh: "中文姓名"
        photo: "/images/members/english-name.webp"
        role: "PhD Student"
        period: "2024.09–Present"
        research: "Financial large language models"
        projects:
          - "Fin-R1"
          - "FinEval"
        homepage: "https://example.com"
        github: "https://github.com/example"
        scholar: "https://scholar.google.com/example"
```

毕业生还可以增加：

```yaml
destination: "Current verified affiliation"
```

招生方向、指导流程、申请邮件和联系方式仍在 `_pages/supervision.md` 中维护。

## 更新 Lab Members

Lab Members 展示完整 AIFin Lab 团队，包括教师、研究人员、行政人员、工程人员、量化研究人员和学生成员。

数据位于 `_data/people.yml` 的：

```yaml
lab_groups:
```

现有分组：

- `faculty`：教师与研究人员；
- `administration`：行政与运营；
- `engineering`：工程团队；
- `quant`：量化研究团队；
- `students`：学生研究成员；
- `alumni`：离组成员。

### 团队成员示例

```yaml
  - key: "engineering"
    title: "Engineering Team / 工程团队"
    members:
      - name_en: "English Name"
        name_zh: "中文姓名"
        photo: "/images/members/english-name.webp"
        role: "Large-Model Engineer"
        period: "2025.03–Present"
        focus: "Model training, inference and deployment"
        projects:
          - "Fin-R1"
        github: "https://github.com/example"
```

Supervision 和 Lab Members 可以出现同一个人，但内容侧重点不同：

- Supervision 强调培养层次、指导时间和研究方向；
- Lab Members 强调实验室岗位、工作职责和参与项目。

行政人员使用 `focus` 描述职责，不需要强行填写 `research`。

## 成员照片规范

- 保存目录：`images/members/`；
- 推荐比例：4:5；
- 推荐尺寸：800×1000 像素；
- 推荐格式：WebP 或压缩 JPG；
- 建议单张不超过 200KB；
- 文件名使用小写英文和连字符，例如 `zhaowei-liu.webp`；
- 照片构图尽量保证人脸位于画面中上部；
- 发布前获得本人授权；
- 没有照片时可以暂时省略 `photo`，页面会显示统一占位区域。

## 更新 Talks

讲座数据位于：

```text
_data/talks.yml
```

- `academic.items`：学术会议与研讨会；
- `industry.items`：产业讲座。

示例：

```yaml
academic:
  title: "Academic Conferences & Seminars / 学术会议与研讨会"
  items:
    - date: "2026.02.04"
      event: "Event or Host Institution"
      location: "Shanghai"
      invited: true
      title: "Talk Title"
      url: "https://example.com/event"
```

- 每个类别内部按时间倒序；
- `invited: true` 会显示邀请报告标记；
- 没有活动页面时省略 `url`，不要填写空链接；
- 同一个题目在不同机构报告时分别记录。

## 修改导航和页脚

顶部导航位于 `_data/navigation.yml`：

```yaml
main:
  - title: "Publications"
    url: /publications/
```

不要添加独立 Home。站点标题已经链接首页，页眉模板也会过滤标题为 `Home` 或地址为 `/` 的重复导航项。

页脚位于 `_includes/footer.html`，目前仅显示极简版权信息：

```text
© 当前年份 Liwen Zhang (张立文). All rights reserved.
```

## 本地预览

建议使用 Ruby 3.1 或更高版本。

首次安装：

```bash
bundle config set --local path 'vendor/bundle'
bundle install
```

启动预览：

```bash
bundle exec jekyll serve -l -H localhost
```

浏览器访问：

```text
http://localhost:4000
```

修改 `_config.yml` 后需要停止并重新启动 Jekyll。若页面仍显示旧内容，先重新构建，再使用浏览器强制刷新。

严格构建检查：

```bash
bundle exec jekyll build --strict_front_matter
```

## GitHub 更新和发布

推荐流程：

1. 修改 Markdown、YAML、图片或样式；
2. 在本地预览所有受影响页面；
3. 执行严格构建；
4. 检查 `git status`，确认没有缓存、临时文件或私人材料；
5. 提交到新分支；
6. 创建 Pull Request；
7. 合并到 GitHub Pages 的发布分支；
8. 等待部署完成后强制刷新浏览器复查。

上传前需要在 GitHub 仓库的 **Settings → Pages** 中确认发布来源：

- 如果使用 **Deploy from a branch**，确认分支和根目录设置正确；
- 如果使用 **GitHub Actions**，仓库必须存在有效的 Pages 工作流。

当前仓库不跟踪 `_site/`，通常不需要手工上传构建产物。

## 发布前检查清单

### 内容

- [ ] 姓名、职称、单位和邮箱准确；
- [ ] 没有“待补充学期”等占位文字；
- [ ] 论文状态、年份、作者顺序和作者标记准确；
- [ ] 课程、奖项和讲座时间准确；
- [ ] 成员身份、起止时间和毕业去向经过确认；
- [ ] 没有公开私人联系方式或未授权照片。

### 链接与图片

- [ ] 五个顶部内容导航均可打开；
- [ ] 点击站点标题可以返回首页；
- [ ] Paper、Code、Data、Model 和活动链接有效；
- [ ] 所有成员图片能够加载；
- [ ] 手机端没有横向滚动。

### 构建与发布

- [ ] `bundle exec jekyll build --strict_front_matter` 成功；
- [ ] `_site/`、`.bundle/`、`vendor/` 没有加入 Git；
- [ ] 没有 `.env`、密钥、内部名单或私人材料；
- [ ] GitHub Pages 发布来源正确；
- [ ] 正式网站已经显示最新提交。

## 不再使用的模板文件

以下两个脚本来自旧版 Academic Pages JSON CV 功能，当前网站已不再使用：

```text
scripts/cv_markdown_to_json.py
scripts/update_cv_json.sh
```

它们原本依赖已经删除的 `_pages/cv.md` 和 `_data/cv.json`。除非未来恢复 JSON CV，否则可以删除，不要把它们当作当前网站的数据更新工具。

仓库中还可能存在 Academic Pages 的演示页面、示例 PDF、旧 Talk Map 或 Notebook。正式发布前应确认这些文件是否属于网站真实内容；不需要的文件应删除或从 Jekyll 输出中排除。

## 常见问题

### 导航仍然显示 Home

确认 `_data/navigation.yml` 中没有 Home，然后重新启动 Jekyll，并使用浏览器强制刷新：

- macOS：`Command + Shift + R`
- Windows：`Ctrl + F5`

### 修改数据后页面没有变化

检查：

1. YAML 缩进是否正确；
2. 是否修改了正确的数据文件；
3. Jekyll 是否仍在运行；
4. 是否需要重新启动服务；
5. 浏览器是否使用了缓存。

### 新增人员后没有显示

确认成员位于对应分组的 `members:` 下，并保持正确缩进。空分组会自动隐藏。

### 页面构建失败

优先检查：

- YAML 中是否混用了 Tab；
- 冒号后是否缺少空格；
- 包含特殊符号的字符串是否需要引号；
- Markdown Front Matter 是否保留完整；
- Ruby 和依赖版本是否符合要求。

## 许可证

模板相关许可证见 [`LICENSE`](LICENSE)。网站中的个人照片、成员照片、论文、课程资料和其他内容仍应遵循各自的版权与授权要求。
