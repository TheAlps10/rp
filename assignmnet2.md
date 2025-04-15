# 团队分工说明

- **廖乾钦**：舆情报告撰写，查找文献，进度汇总，上台讲解
- **吴诚毅**：coze技术使用，具体展开内容汇总，主题稿子
- **陈景灿**：可视化数据， markdown 源代码，提交作业latex脚本代码

---

# Assignment2.md 的具体展开内容（三部分）

## 一、使用的智能体工具 -- coze

### 创建的智能体提示：

!()[a.png]

### 创建相关舆情分析照片数据集：

（此处留空，根据实际情况填写）

## 二、所用的脚本（LaTeX）：文章内容

（此处留空，根据实际情况填写）

## 三、每个步骤的提示词

### 任务描述

**主题**：江西高校食品安全事件（“指鼠为鸭”）  
**背景**：2023年江西某高校食品安全事件引发热议，校方与相关部门起初坚称饭菜中的异物是鸭脖，而公众普遍认为是老鼠头，这一事件引发了广泛的社会关注和讨论。  
**任务**：进行舆情分析研判报告的撰写，确保信息的真实准确性，按照既定主题进行报告搜集工作。不限于图文等，可以展示视频发布后引起的反响，增添优秀评论来支撑论点，对于观点分析可以多生成一点分析内容。

### 相关文献探讨

结合相关文献探讨“指鼠为鸭”事件的舆情发展对社会信任的影响。

### 政府应对策略

政府部门应如何应对类似食品安全事件以维护社会信任？

### 深入分析舆情发展过程

请你现在根据插入的（食品安全——指鼠为鸭）的数据集，进行进一步的深入分析舆情发展过程，融合上述生成的文章再叙述一遍。

### 成功引发广泛关注的原因

请你接着分析一下这个案例能够成功引发广泛关注和讨论的原因有哪些？

### 文献探讨与总结

现在增加相关话题的文献探讨，请你进行总结并结合文章内容再重新增添叙述内容。

### 整合完整舆情报告

请你将上述所有提到的内容进行整合，叙述生成一篇完整的舆情报告的文章。

---

## 代码示例

### Python 代码（环形图）

```python
import matplotlib.pyplot as plt
import numpy as np

# 数据
labels = ['微博', 'APP', '问答', '视频', '头条号', '微信', '网页', '其他类型', '论坛', '搜狐号', '报刊', '评论']
sizes = [72.34, 7.18, 6.29, 4.32, 2.43, 0.02, 0.02, 0.02, 0.02, 0.02, 0.02, 0.02]
colors = ['#66c2a5', '#fc8d62', '#8da0cb', '#e78ac3', '#a6d854', '#ffd92f', '#e5c494', '#b3b3b3', '#ff9999', '#66c2a5', '#fc8d62', '#8da0cb']

# 创建环形图
fig, ax = plt.subplots(figsize=(10, 10))
wedges, texts, autotexts = ax.pie(sizes, colors=colors, startangle=90, wedgeprops=dict(width=0.3), autopct='%1.2f%%')

# 设置图例
plt.legend(wedges, labels, loc="center left", bbox_to_anchor=(1, 0, 0.5, 1))

# 显示图表
plt.axis('equal')
plt.tight_layout()
plt.show()

import matplotlib.pyplot as plt
from wordcloud import WordCloud

# 数据
words = {
    "江西": 126490, "食堂": 10000, "异物": 15000, "学生": 12000, "调查组": 11000, "事件": 13000,
    "食品安全": 8000, "微博": 7000, "学校": 6000, "当事人": 5000, "市场": 4000, "责任": 3000,
    "安全事件": 2000, "视频": 1800, "食品": 1700, "通报": 1600, "工作人员": 1500, "事发": 1400,
    "问题": 1300, "权威": 1200, "中午": 1100, "大山": 1000, "江西省": 900, "头部": 800,
    "如今": 700, "技术": 600, "老鼠": 500, "管理局": 400, "同学": 300, "现场": 200,
    "职业": 100, "窗口": 90, "事情": 80, "一楼": 70, "笑柄": 60, "许可": 50,
    "校方": 40, "企业": 30, "部门": 20, "负责人": 10, "情况": 5, "工职": 4,
    "高校学生": 3, "如今": 2, "技术": 1
}

# 创建词云
wordcloud = WordCloud(
    width=800, height=600, background_color='white', font_path='simhei.ttf',
    max_words=150, max_font_size=60, min_font_size=8, random_state=42,
    prefer_horizontal=0.95
).generate_from_frequencies(words)

# 显示词云
plt.figure(figsize=(10, 8))
plt.imshow(wordcloud, interpolation='bilinear')
plt.axis('off')
plt.show()

# 保存词云图
wordcloud.to_file("wordcloud.png")



import matplotlib.pyplot as plt
from matplotlib.colors import to_rgba
import numpy as np

# 数据
labels = ['江西', '食堂', '异物', '学生', '调查组', '事件', '视频', '饭菜', '现场', '老鼠']
sizes = [13.05, 12.26, 11.74, 11.53, 11.15, 10.32, 8.17, 7.81, 7.05, 6.92]
original_colors = ['#77DD77', '#FFA500', '#FF6347', '#4682B4', '#3CB371', '#FFD700', '#D3D3D3', '#808080', '#4B0082', '#9400D3']
alpha = 0.8
colors = [to_rgba(c, alpha) for c in original_colors]
explode = (0, 0, 0, 0, 0, 0, 0, 0, 0, 0)

# 设置字体属性
plt.rcParams['font.sans-serif'] = ['SimHei']
plt.rcParams['font.size'] = 10

# 绘制环形图
fig, ax = plt.subplots()
wedges, texts, autotexts = ax.pie(sizes, explode=explode, labels=labels, colors=colors,
                                  autopct='%1.2f%%', startangle=90, wedgeprops={'width': 0.4},
                                  shadow=True)

# 优化百分比标签显示
for autotext in autotexts:
    autotext.set_color('white')
    autotext.set_weight('bold')
    bbox = autotext.get_bbox_patch()
    if bbox is not None:
        bbox.set_facecolor('black')
        bbox.set_alpha(0.6)

# 优化扇形标签显示
for text in texts:
    text.set_bbox(dict(facecolor='white', edgecolor='black', alpha=0.7))

# 调整图形布局
ax.axis('equal')
plt.subplots_adjust(left=0.15, right=0.85, top=0.9, bottom=0.1)
plt.show()



import matplotlib.pyplot as plt
import numpy as np
from scipy.interpolate import UnivariateSpline

# 数据
dates = ['06-14', '06-15', '06-16', '06-17', '06-18', '06-19', '06-20']
categories = {
    '网页': [1000, 3000, 10000, 30000, 20000, 10000, 5000],
    '微博': [500, 1500, 5000, 15000, 10000, 5000, 2500],
    'APP': [300, 900, 3000, 9000, 6000, 3000, 1500],
    '论坛': [200, 600, 2000, 6000, 4000, 2000, 1000],
    '报刊': [100, 300, 1000, 3000, 2000, 1000, 500],
    '搜狐号': [50, 150, 500, 1500, 1000, 500, 250],
    '问题': [30, 90, 300, 900, 600, 300, 150],
    '评论': [20, 60, 200, 600, 400, 200, 100],
    '其他类型': [10, 30, 100, 300, 200, 100, 50]
}

# 将日期转换为数值
x = np.arange(len(dates))

# 创建图表
plt.figure(figsize=(12, 6))

# 为每个类别绘制平滑的折线图
for category, values in categories.items():
    y = np.array(values)
    try:
        spline = UnivariateSpline(x, y, s=10000)  # 增大s值
        xs = np.linspace(0, len(x) - 1, 1000)
        ys = spline(xs)
        line, = plt.plot(xs, ys, label=category, alpha=0.7)
        plt.fill_between(xs, ys - 1000, ys + 1000, color=line.get_color(), alpha=0.1)
    except Exception as e:
        print(f"Error processing category {category}: {e}")

# 设置图表属性
plt.xticks(x, dates)
plt.xlabel('日期')
plt.ylabel('数值')
plt.title('各类别随时间变化的趋势')
plt.legend(loc='lower right', bbox_to_anchor=(1, 0, 0.5, 1))
plt.grid(True, alpha=0.3)

# 显示图表
plt.tight_layout()
plt.show()






% 导言区增强
\documentclass[UTF8]{ctexart}
\usepackage{geometry}
\usepackage{hyperref}
\usepackage{graphicx}
\usepackage{float}  % <<<<<< 新增1：固定图片位置
\usepackage{booktabs}
\usepackage{enumitem}
\usepackage{amsmath,amssymb}
\usepackage{titlesec}
\usepackage{fontspec}
\usepackage{emptypage}
\usepackage{afterpage}
\usepackage[backend=biber,style=gb7714-2015]{biblatex}

% 图片路径设置 <<<<<< 新增2：指定图片搜索路径
\graphicspath{{./}{./images/}}  % 允许从当前目录和images子目录加载图片

\addbibresource{ref.bib}

% 列表格式设置
\setlistdepth{9}
\setlist[itemize,1]{label=$\bullet$}
\setlist[itemize,2]{label=$\circ$}
\setlist[itemize,3]{label=$\triangleright$}

% 章节格式设置
\titleformat{\section}
  {\LARGE\bfseries\heiti\centering}
  {\thesection、}
  {0.5em}
  {}
  [\vspace{-0.5ex}]

\titleformat{\subsection}
  {\Large\bfseries\heiti}
  {\thesubsection.}
  {0.5em}
  {}

\titleformat{\subsubsection}
  {\large\bfseries\heiti}
  {\thesubsubsection.}
  {0.5em}
  {}

% 章节间距
\titlespacing*{\section}{0pt}{3ex}{2ex}
\titlespacing*{\subsection}{0pt}{2.5ex}{1.5ex}
\titlespacing*{\subsubsection}{0pt}{2ex}{1ex}

% 封面信息
\title{“指鼠为鸭”事件大数据舆情分析报告\\——基于2023-2025年全网数据的深度研究}
\author{第五组全体成员}

\begin{document}
\maketitle

% 摘要与关键词
\begin{abstract}
2023年江西"指鼠为鸭"事件暴露基层治理中公信力危机的制度性根源\cite{liang2023}。学生食堂发现异物后，校方与市场监管部门未充分取证便坚称其为"鸭脖"，引发全网质疑\cite{tuyaju2023}。尽管省级联合调查组最终确认异物为鼠头并追责涉事方，但涉事官员仅被调岗且未公开处分细节\cite{dawan2025}，引发公众对"护短文化"的质疑。事件推动《校园食品安全应急处置指南》出台\cite{zhonggong2023}，引入"四维检测法"等技术标准，并强化AI监控与区块链溯源体系，但执行成本与地方监管惯性仍制约制度效能。网民通过"鼠鼠我鸭"等亚文化解构官方叙事\cite{niandu2025}，倒逼政务透明化。制度刚性（公务员处分公示）及社会共治（第三方监督）重塑"技术赋能+情感修复"的双轨治理范式\cite{fengmian2025}，防范公信力危机重演。
\end{abstract}

\noindent\textbf{关键词：}网络舆情应对；公信力危机；食品安全监管；指鼠为鸭

% 正文各章节
\input{introduction.tex}  % 确保这些子文件中也有\cite{}引用
\section{事件演进与舆情特征}
\input{event_evolution.tex}
\section{官方应对的决策逻辑分析}
\input{decision_logic.tex}
\section{理论框架下的深度解构}
\input{theoretical_framework.tex}
\section{制度变革与社会影响}
\input{institutional_change.tex}
\section{结论与展望}
\input{conclusion.tex}

% 强制显示所有参考文献（即使未被引用）
\nocite{*}  % 关键新增！确保所有文献条目显示
\printbibliography[title=参考文献]

% 附录
\appendix
\input{appendix.tex}
\end{document}
