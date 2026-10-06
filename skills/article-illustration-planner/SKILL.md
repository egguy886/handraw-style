---
name: article-illustration-planner
description: 深度分析文章脉络，精准规划插图点位与视觉意象。对知识类/教程类文章默认启动“认知降负与视觉替换机制”，将复杂抽象概念/流程/决策树提炼为高信息量图示并精炼替换冗长文字；对非知识类文章保持叙事氛围与意境。严格防止开篇扎堆，生成协同 324 种手绘风格与 36 种色彩画廊的高质量生图提示词，支持自主生图或全自动插图回填排版。
---

# Article Illustration Planner (文章配图规划与插图回填)

Turn an article into a coherent visual-illustration plan and deliver the final illustrated article.

The user provides:

* An article text or local file path (e.g. `d:\path\to\article.md`);
* (Optional) A hand-drawn style number (`001`–`324`) and/or theme color (`C-01`–`C-36`). If omitted, the Skill automatically analyzes the article's mood, domain, and audience to recommend an optimal cohesive style and theme color combination;
* (Optional) Whitespace preference (`留白`: `正常` / `适中` / `多`). Default is `正常`;
* (Optional) Aspect ratio. Default is `4:3` (editorial reading standard). Note: Poster layout selection is strictly disabled for article illustrations.

The Skill decides:

* whether the article actually benefits from illustrations;
* where illustrations add the most value;
* how many illustrations are appropriate;
* what each image should communicate;
* whether an image should supplement, explain, replace, or reorganize part of the text;
* how to express each illustration in the selected or recommended visual style and theme color;
* how to guide the user seamlessly through image generation and automatic insertion into the article.

Do not mechanically illustrate every paragraph.

Do not distribute images at fixed intervals.

Do not force a predetermined number of illustrations.

The primary task is **visual editorial judgment**, not filling empty spaces with pictures.

---

# Core Principle

First determine:

> What does this article need visually?

Only then determine:

> What should each image contain?

The selected style number controls **how the image is drawn**.

It must not determine **what the image is about**.

Separate these two decisions:

1. visual communication strategy;
2. visual style and color palette.

---

# Default Behavior & Article-Type Adaptation (分类自适应工作模式)

Skill 必须首先判断文章类型，并自动适配两套截然不同的工作模式：

## 模式 A：知识/干货/教程/实操类文章 (Knowledge & Explanatory Articles)
> **核心使命：认知降负与文字替换机制（Cognitive Load Reduction & Text Replacement）**

1. **配图的核心价值在于“降低认知负荷，辅助理解”**：
   - 知识类文章的最大痛点是枯燥复杂的机制推导、层级漏斗与多分支规则。配图决不能是与业务无关的童话装饰小品；
   - 重点识别文章中**用文字表达相对复杂、抽象、嵌套、读者理解成本极高**的概念（例如：多维加权算法公式、阶梯流量池跃迁漏斗、长篇 ASCII 字符图表、爆款封面反差模型、多分支数据诊断决策树、多 SKU 价格锚定矩阵等）。
2. **文字替换原则（强制替换与精炼，对文章做必要修改）**：
   - 必须将上述复杂概念提炼设计为高信息密度的**概念图、流程图或对比图（conceptual / process / comparison diagram）**；
   - **记住是替换，对文章必须进行修改精简**：在最终回填排版时，将原先繁琐冗长的文字推导或复杂图表直接替换为**“配图 + 极简核心提要/行动清单”**，真正做到“一图胜千言”，大幅为读者减轻认知负担。
3. **点位排布与防堆叠红线（Anti-Clustering Pacing Rules）**：
   - **严禁开篇堆叠**：严禁在目录后、前言后、第一章首段前连续插入多张图（相邻两张图之间严禁少于 300~500 字，必须有完整的实质性正文承载）；
   - **严禁中后段断档**：配图必须均匀分布在全篇真正具有高认知负荷的章节节点（如核心 SOP、诊断决策），杜绝“前密后空/头重脚轻”；
   - **严禁图意倒挂**：插图必须紧跟在所阐述的具象概念/子标题之后，紧密承接上文。

## 模式 B：非知识类文章（抒情散文、叙事故事、随笔、小说等） (Non-Knowledge Articles)
> **核心原则：意境烘托与保全模式（Preserve Mode & Atmospheric Resonance）**

1. **保留原文不删改**：保持 Preserve mode，不强求替换或删改原文文字；
2. **风格可保持现有艺术探索**：可自由使用手绘隐喻、叙事微距、跨媒介微缩摄影等视觉风格，重点在于烘托情绪、营造意境与提供阅读视觉停顿。

---

# Inputs & Parameters

### 1. Article Content or File Path
- Direct text pasted in chat, or a local file path (e.g., `d:\path\to\article.md`).
- Always support absolute Windows paths cleanly.

### 2. Style & Color
- Style range: `#001`–`#324` from the local hand-drawn style library.
- Color palette: `C-01`–`C-36` from the 36 classic theme color gallery.
- Dynamic aesthetic reasoning: If user doesn't specify, analyze domain, mood, and tone to recommend the most expressive style and color palette.

### 3. Aspect Ratio (画幅比例)
- **Default: 4:3**. Editorial article illustrations naturally fit widescreen horizontal reading flow across Web, WeChat, Zhihu, and Markdown readers.
- Other supported ratios if user requests: `16:9`, `1:1`, `3:4`.
- **Layout Selection Disabled**: Poster layout selection (`SC-*`, `IG-*`, etc.) is disabled for article illustrations. Article illustrations are standalone editorial visuals integrated into prose.

### 4. Whitespace Control (留白控制)
- **正常 (Normal, Default)**: Standard compositional density. No additional whitespace keywords are appended.
- **适中 (Moderate)**: Appends `【大量留白】` / `[generous whitespace]` to the visual prompt.
- **多 (High)**: Appends `【大量留白，场景只显示必要部分，不要显示全】` / `[generous whitespace, show only essential elements of the scene, do not display the full context]` to the visual prompt.

---

---

# Article Understanding

Before selecting images, understand the article as a whole.

Internally identify:

* central idea;
* article type;
* major sections;
* argument or narrative progression;
* information-density changes;
* emotional changes;
* conceptual difficulty;
* places where prose becomes repetitive;
* places where a visual could communicate something words are currently carrying inefficiently.

Do not expose lengthy internal analysis unless the user asks for it.

The visible output should focus on useful editorial decisions.

---

# Article Types

Infer dominant visual needs:

### Reflective / philosophical
* Metaphor, symbolic scenes, emotional transitions, visual pauses, restrained narrative moments.
* Avoid merely drawing a literal person who is "thinking", "sad", or "happy" when a stronger visual metaphor is possible.

### Narrative / personal essay
* Key moments, environmental storytelling, objects with narrative meaning, shifts in relationship, place, time, or emotional state.

### Explanatory / educational
* Concept visualization, analogy, causal relationships, processes, systems, hierarchy, comparison, transformation over time.
* Hand-drawn explanatory illustration may combine objects, characters, spatial relationships, labels, and diagrams.

### Argumentative / analytical
* Contrasts, competing forces, cause and effect, hidden relationships, structural models, before-and-after states.

---

# Illustration Functions

For every proposed image, decide its primary purpose:

* `opening-visual` — establishes the article's visual premise;
* `metaphor` — translates an abstract idea into a visual situation;
* `narrative-scene` — depicts a meaningful moment or situation;
* `concept-explanation` — makes a difficult concept easier to understand;
* `relationship` — visualizes relationships among ideas or entities;
* `process` — visualizes sequence, causality, or transformation;
* `comparison` — contrasts two or more states or ideas;
* `visual-pause` — creates rhythm and emotional breathing room;
* `transition` — bridges two sections;
* `summary` — condenses a section or conclusion visually;
* `text-replacement` — carries information that would otherwise require substantial prose.

---

# Image Type

For every proposed image, choose one concise image-type keyword:

* `editorial illustration` — a broad, article-led visual that establishes or reinforces an argument;
* `conceptual diagram` — an explanatory relationship, system, or abstraction;
* `process diagram` — a sequence, causal chain, cycle, or transformation;
* `comparison diagram` — a contrast between states, groups, or outcomes;
* `narrative scene` — a concrete, meaningful moment or situation;
* `metaphorical illustration` — a symbolic visual situation for an abstract or emotional idea.

Use the same selected value in the illustration plan and both copyable prompts.

---

# Selecting Illustration Positions

Choose illustration positions according to editorial value:

* where the article introduces its central idea;
* where an abstract idea becomes important;
* where the reader must understand a relationship;
* where explanation becomes text-heavy;
* where a major emotional or argumentative turn occurs;
* where the article shifts from one conceptual section to another;
* where a concrete scene makes an idea memorable;
* where the ending benefits from visual resonance.

Do not choose positions merely because a paragraph is long.

Do not insert an image when it would interrupt a strong reading rhythm.

The number of images should emerge naturally from the article (typically 2 to 5 for standard articles, 1 to 2 for short essays).

---

# Prompt Writing

Each image prompt should be concise enough to leave meaningful creative freedom to the image model.

The prompt structure:
1. **图片类型 / Image type**: `图片类型：{image_type}。` / `Image type: {image_type}.`
2. **主题与核心视觉意象**: Dominant visual idea, key subjects, environmental storytelling.
3. **留白修饰**: If `适中`, append `【大量留白】` / `[generous whitespace]`. If `多`, append `【大量留白，场景只显示必要部分，不要显示全】` / `[generous whitespace, show only essential elements of the scene, do not display the full context]`.
4. **画风与色彩基调**: Hand-drawn style definition from `#001`–`#324` and theme color from `C-01`–`C-36`.

---

# Output Format

Start with a concise overall recommendation:
* Inferred article type;
* Visual strategy;
* Recommended number of illustrations;
* Recommended style number & name, theme color & name, aspect ratio (`4:3`), and whitespace setting.

Then provide each illustration in reading order:

```markdown
### Illustration N

**插入位置 / Insert after:**
`[引用目标小标题或紧邻的上文段落前/后 10-20 个字]`

**配图定位 / Purpose:**
解释该图在阅读流中的作用。

**图片类型 / Image Type:**
editorial illustration / metaphorical illustration / conceptual diagram ...

**视觉构思 / Visual Concept:**
描述核心视觉隐喻、主体与画面情绪。

**图文关系 / Relationship to Text:**
supplements text / explains text / visually summarizes text / replaces part of text

**（知识类文章必填）被图片替换/精简的复杂文字 / Text to Replace:**
`[直接标明原文中被该图片替代/精简掉的冗长推演、复杂层级或长篇ASCII字符图表]`

**（知识类文章必填）精简后的轻量导读 / Simplified Replacement Text:**
`[文字替换后在正文中保留的极简核心要点/行动清单，大幅减轻认知负担]`

**画风与配色 / Style & Color:**
`#{style_number} · {style_name}` + `{color_id} · {color_name}`

**生图提示词 (Prompt):**
- **中文提示词**:
```text
图片类型：{image_type}。{visual_concept}。{whitespace_clause}画风：{style_prompt}。色彩：{color_prompt}。画幅比例 4:3。
```
- **English Prompt**:
```text
Image type: {image_type}. {visual_concept_en}. {whitespace_clause_en} Style: {style_prompt_en}. Color palette: {color_prompt_en}. Aspect ratio: 4:3.
```
```

---

# Post-Planning Call-to-Action (CTA)

Immediately following the illustration plan, the Skill **MUST** output the standardized dual-track delivery CTA block:

```markdown
---

💡 **插图方案已规划完成！接下来您可以选择以下两种交付方式：**

1. **【方式 A · 自主生图回填】**：
   复制上方提示词，前往您常用的生图工具出图。生成完成后，将图片文件直接拖入对话，或发送本地图片路径（如 `D:\path\to\illus1.png`），我会帮您将配图精准插入到文章对应位置中！

2. **【方式 B · 全自动生图插入】**：
   直接对我说 **“全自动生图”** 或 **“帮我生成所有配图并插入”**，我将全自动调用生图工具批量绘制配图，并自动排版回填到文章对应锚点中，输出完整的图文定稿！
```

---

# Dual-Track Delivery Workflow (双轨交付流程)

## Track A · 自主生图回填 (Manual Generation & Back-fill)

When the user chooses Track A and provides images:
1. **Image Receipt**: User pastes images into chat, or supplies local image file paths / URLs.
2. **Anchor Matching**: The Skill matches each received image to the corresponding Illustration N (`Illustration 1`, `Illustration 2`, etc.) based on visual content or user specification.
3. **Local File Management**:
   - If the user provided a local article path (e.g. `D:\path\to\my_article.md`):
     - Create an assets folder: `D:\path\to\images\` (relative `images/`).
     - Save/copy the received image into `D:\path\to\images\illus_01.webp` (or `.png`/`.jpg`).
     - Use relative path `images/illus_01.webp` in Markdown.
   - If the article was provided as chat text:
     - Store images in the conversation artifact directory or working directory, using clean markdown syntax.
4. **Markdown Insertion Standard**:
   Insert the image block immediately after the designated anchor point:
   ```markdown
   ![插图N: 说明](images/illus_0N.webp)
   *▲ 图N：说明*
   ```
5. **Output**:
   - For local file: Write the illustrated article to `D:\path\to\my_article_illustrated.md` (or update original if requested by user).
   - For chat text: Output the full illustrated article Markdown ready to copy.

---

## Track B · 全自动生图插入 (Fully Automated Generation & Insertion)

When the user triggers Track B (e.g. "全自动生图", "帮我生成并插入", "自动完成"):
1. **Execution Verification**: Confirm the target article location (file path `d:\path\to\article.md` or in-memory draft).
2. **Automated Image Generation**:
   - For each planned Illustration N in sequential order:
     - Call the image generation tool (`generate_image`) using the finalized prompt.
     - Specify aspect ratio `4:3` (unless customized by user).
     - Maintain strict style `#001`–`#324` and color consistency.
3. **Asset Organization**:
   - Save each generated image to `<article_dir>/images/illus_01.webp`, `illus_02.webp`, etc.
4. **Automatic Insertion & Assembly**:
   - Read the original article markdown.
   - Accurately locate each anchor point (`Insert after:` heading or sentence excerpt).
   - Insert the formatted image link and caption:
     ```markdown
     ![插图N: 说明](images/illus_0N.webp)
     *▲ 图N：说明*
     ```
   - **知识类文章执行文字替换与精炼**：若规划中指定了“被图片替换的复杂文字”，自动将该段繁琐文字修剪替换为规划中的极简说明/清单，确保图文排版真正实现认知减负。
   - Save the finalized document as `[article_name]_illustrated.md` (or write in-place if requested).
5. **Final Presentation**:
   - Provide a brief summary table of generated illustrations.
   - Present the path to the newly created illustrated article, or display the illustrated article directly.

---

# Automation Helper Script

The Skill provides a deterministic Python helper script located at:
`skills/article-illustration-planner/scripts/insert_illustrations.py`

Usage:
```bash
python -X utf8 skills/article-illustration-planner/scripts/insert_illustrations.py \
  --article "D:\path\to\article.md" \
  --manifest "D:\path\to\illustrations_manifest.json" \
  --output "D:\path\to\article_illustrated.md"
```

The manifest format:
```json
[
  {
    "index": 1,
    "anchor": "### 1. 概念起源",
    "position": "after",
    "image_path": "images/illus_01.webp",
    "caption": "图1：概念起源与核心意象"
  }
]
```

The script cleanly preserves indentation, headings, code blocks, and math formulas without touching unintended text.

---

# Design Philosophy

This Skill should remain intentionally lightweight and high-taste.

Prefer:
* visual editorial judgment over rules;
* meaning over generic templates;
* article-specific visual thinking over clichés;
* clean dual-track execution over tedious back-and-forth;
* seamless integration from prompt planning to final illustrated Markdown delivery.
