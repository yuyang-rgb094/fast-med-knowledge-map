# Fast Medical Knowledge Map — Documentation

> A battle-tested meta-skill for systematic scholarly knowledge base construction.
> 经过实战验证的系统性循证知识库构建元规则Skill。

---

## Table of Contents / 目录

1. [Overview / 概述](#overview--概述)
2. [Core Principles / 核心理念](#core-principles--核心理念)
3. [5-Phase Workflow / 5阶段工作流](#5-phase-workflow--5阶段工作流)
4. [Phase 1: Requirements Planning / 需求规划](#phase-1-requirements-planning--需求规划)
5. [Phase 2: Scholar Discovery / 学者发现](#phase-2-scholar-discovery--学者发现)
6. [Phase 3: Dual-Track Retrieval / 双轨检索](#phase-3-dual-track-retrieval--双轨检索)
7. [Phase 4: Knowledge Transformation / 知识转化](#phase-4-knowledge-transformation--知识转化)
8. [Phase 5: Quality Audit / 质量审计](#phase-5-quality-audit--质量审计)
9. [Knowledge Graph Architecture / 知识图谱架构](#knowledge-graph-architecture--知识图谱架构)
10. [Meta-Rules Reference / 核心元规则一览](#meta-rules-reference--核心元规则一览)
11. [Domain Adaptation Guide / 领域适配指南](#domain-adaptation-guide--领域适配指南)
12. [Anti-Patterns / 反模式](#anti-patterns--反模式)
13. [File Structure / 文件结构](#file-structure--文件结构)
14. [Battle-Tested Validation / 实战验证](#battle-tested-validation--实战验证)
15. [Installation / 安装方法](#installation--安装方法)

---

## Overview / 概述

**EN:** This skill provides a complete meta-rules system for building evidence-based knowledge bases, distilled from three production modules (Ophthalmology M1, Dermatology M2, Body Condition M3) of the iPaw project — an AI-assisted veterinary diagnostic system. It covers the full lifecycle from literature retrieval and scholar discovery through knowledge graph construction to quality auditing. The methodology is domain-agnostic and can be ported to medicine, veterinary science, engineering, social sciences, or any field requiring rigorous evidence-based knowledge systems.

**CN:** 本Skill提供一套完整的循证知识库构建元规则体系，源自iPaw项目（AI兽医辅助诊断系统）三个生产模块（眼科M1、皮肤科M2、体况管理M3）的实战经验总结。涵盖从文献检索、学者发现、知识图谱构建到质量审计的完整生命周期。该方法论与领域无关，可平移到医学、兽医学、工程学、社会科学等任何需要严格循证知识体系的领域。

---

## Core Principles / 核心理念

**Dual-track retrieval + Scholar-first anchoring + Evidence quality gating + Graph-augmented RAG**
**双轨并行检索 + 学者锚定优先 + 证据质量守门 + 图增强RAG**

| # | EN: Principle | CN: 原则 |
|---|---------------|----------|
| 1 | **Scholars before keywords**: Anchor domain core scholars first, then expand through collaboration and citation networks. Keyword-only searches miss high-value literature clusters. | **学者优先于关键词**：先锚定领域核心学者，再通过合作网络和引用网络展开。纯关键词检索会遗漏高价值文献集群。 |
| 2 | **Evidence pyramid layering**: T0 Textbooks/Guidelines → P0 Multi-center cohorts → P1 Single-center → P2 Case reports. Higher tiers carry greater clinical weight. | **证据金字塔分层**：T0教科书/指南 → P0多中心队列 → P1单中心 → P2病例报告。层级越高，临床权重越大。 |
| 3 | **Quality over quantity**: Strictly enforce journal gatekeeping and exclusion criteria. A small curated corpus beats a large noisy one. | **质量先于数量**：严格执行期刊守门和排除标准。小而精的语料库优于大而杂的文献堆。 |
| 4 | **Graph structure over flat documents**: Obsidian wikilinks form a natural knowledge graph that enables multi-hop reasoning. | **图结构优先于扁平文档**：基于Obsidian wikilink构建天然知识图谱，支持多跳推理和关联发现。 |

---

## 5-Phase Workflow / 5阶段工作流

```
Phase 1: Requirements Planning ──→ Define scope, topic taxonomy, knowledge gap matrix
         │                         定义范围、主题分类树、知识缺口矩阵
         │
Phase 2: Scholar Discovery ────→ Tier 1/2/3 stratified anchoring + collaboration network map
         │                         Tier 1/2/3 分层锚定 + 合作网络图谱
         │
Phase 3: Dual-Track Retrieval ─→ Track A (scholar tracking) + Track B (topic keywords) + Track C (embedding recall)
         │                         Track A(学者追踪) + Track B(主题关键词) + Track C(嵌入召回)
         │
Phase 4: Knowledge Transform ─→ Full-text acquisition → GRADE assessment → Structured notes → Graph linking
         │                         全文获取 → GRADE评估 → 结构化笔记 → 图谱连接
         │
Phase 5: Quality Audit ──────→ Broken-link detection + GRADE consistency + Orphan nodes + Literature completeness
                                   断链检测 + GRADE一致性 + 孤立节点 + 文献完整性
```

---

## Phase 1: Requirements Planning / 需求规划

### 1.1 Module Scope Definition / 模块范围定义

**EN:** Define the knowledge domain boundary, module ID, positioning (diagnostic/preventive/therapeutic/assessment), cross-module comorbidity links, and product-driven knowledge requirements.

**CN:** 定义知识领域边界、模块编号、定位（诊断/预防/治疗/评估）、跨模块共病关联，以及产品需求驱动的知识需求矩阵。

**Required outputs / 必须输出：**

| EN | CN |
|----|----|
| Module name and ID (e.g., M3 Body Condition) | 模块名称与编号（如M3体况管理） |
| Core positioning | 核心定位 |
| Cross-module comorbidity map (Mermaid) | 跨模块共病关联图（Mermaid） |
| Product-requirement matrix: scenario → knowledge need → evidence depth | 产品需求驱动矩阵：场景 → 知识需求 → 证据深度 |

### 1.2 Knowledge Gap Matrix / 知识缺口矩阵

**EN:** Audit existing knowledge base nodes, identify gaps, and prioritize by P0 (product-critical) / P1 (mechanism deepening) / P2 (long-term reserve). Each gap gets a target literature count.

**CN:** 审计现有知识库节点，识别缺口，按P0（产品核心依赖）/ P1（机制深化）/ P2（长期储备）分级。每个缺口标注目标文献数量。

### 1.3 Topic Taxonomy / 主题分类树

**EN:** Build a hierarchical topic tree (depth 3-4 levels). Each leaf node gets a unique ID (e.g., T1.1, T4.3), a priority tag (P0/P1/P2), and a target literature count.

**CN:** 构建层级式主题分类树（深度3-4层）。每个叶子节点分配唯一ID（如T1.1、T4.3）、优先级标签（P0/P1/P2）和目标文献量。

**Template / 模板：**
```
Module Root
├── T1 Assessment Tools
│   ├── T1.1 Scoring Systems
│   ├── T1.2 Validation Studies
│   └── T1.3 AI/Remote Assessment
├── T2 Epidemiology
├── T3 Pathophysiology
├── T4 Comorbidities
├── T5 Interventions
└── T6 Population-Specific
```

---

## Phase 2: Scholar Discovery / 学者发现

### 2.1 Three-Tier Scholar Ranking Model / 学者三层分级模型

| Tier | EN: Definition | CN: 定义 | Tracking Strategy / 追踪策略 |
|------|---------------|----------|---------------------------|
| **Tier 1 (P0 Core)** | ≥10 relevant publications; domain founders or guideline authors | ≥10篇相关文献；领域奠基者或指南制定者 | Full bibliography + collaboration network + mentees. Track ALL relevant papers. 全量追踪文献 + 合作网络 + 指导团队 |
| **Tier 2 (P1 Important)** | 3-9 relevant publications; key contributors | 3-9篇相关文献；关键贡献者 | Representative papers + recent 3 years. 代表性论文 + 近3年新作 |
| **Tier 3 (P2 Supplementary)** | 1-2 high-impact publications | 1-2篇高影响力文献 | Key single papers only. 仅追踪关键单篇 |

### 2.2 Scholar Anchoring Methods / 学者锚定方法

**EN — Discovery paths (in priority order):**

1. **Guideline/consensus author rosters** — First and corresponding authors of clinical guidelines are natural Tier 1 candidates.
2. **Textbook chapter authors** — Authors of authoritative textbook chapters in the target domain.
3. **Highly-cited paper first/corresponding authors** — Sort by citation count on PubMed/Google Scholar.
4. **Academic organization committee members** — E.g., WSAVA, ICADA, ISCAID steering committees.
5. **Citation snowballing** — Expand from Tier 1 scholars' references and "Cited by" lists.

**CN — 发现路径（按优先级）：**

1. **指南/共识作者名单**：临床指南的执笔人和通讯作者 → 天然Tier 1
2. **教科书章节作者**：权威教材对应章节的作者
3. **高被引论文第一/通讯作者**：在PubMed/Google Scholar上按被引排序
4. **学术组织委员会成员**：如WSAVA、ICADA、ISCAID等专业委员
5. **引用网络滚雪球**：从Tier 1学者的参考文献和被引文献中扩展

**EN — Required fields for each Tier 1 scholar:**
- Full name, current institution, country
- Research direction keywords
- PubMed publication count (estimated H-index)
- Representative paper list (year, title, journal, PMID, corresponding topic ID)
- Key collaborator list

**CN — 每位Tier 1学者必须记录：**
- 姓名、当前机构、国家
- 研究方向关键词
- PubMed相关文献数（估算H-index）
- 代表性论文清单（年份、标题、期刊、PMID、对应主题ID）
- 主要合作者名单

### 2.3 Collaboration Network Graph / 合作网络图谱

**EN:** Render scholar collaboration networks using Mermaid diagrams. Annotate node types (Tier 1 = bold/large), relationship types (mentor-student, long-term collaboration, cross-institution), institution prestige tiers, and network topology (star vs. mesh).

**CN:** 使用Mermaid绘制学者合作网络图谱。标注节点类型（Tier 1 = 加粗/大节点）、合作关系类型（导师-学生、长期合作、跨机构）、机构声望层级和网络拓扑类型（星型 vs. 网状）。

---

## Phase 3: Dual-Track Retrieval / 双轨检索

### 3.1 Track A: Scholar-Anchored Retrieval / 学者锚定检索

**EN:** Execute in order: Tier 1 → Tier 2 → Tier 3. Use PubMed author search with domain keywords. Sort by date descending; prioritize last 5 years. Expand via "Similar articles" and "Cited by". Check author name variants (e.g., Bjørnvad vs. Bjornvad). Confirm identity via institution to avoid homograph confusion.

**CN:** 按Tier 1 → Tier 2 → Tier 3顺序执行。使用PubMed作者检索 + 领域关键词。按时间倒序，优先近5年。通过"Similar articles"和"Cited by"扩展。注意学者姓名变体（如Bjørnvad vs. Bjornvad）。通过机构信息确认身份以避免同名混淆。

### 3.2 Track B: Topic Keyword Retrieval / 主题关键词检索

**EN:** Design PubMed search strings per topic sub-tree. Combine MeSH terms with [tiab] free-text terms. Include species/population filters and optional study-type filters.

**CN:** 为每个主题子树设计PubMed检索式。组合MeSH术语与[tiab]自由词。包含物种/人群限定和可选的研究类型限定。

**Search string template / 检索式模板：**
```pubmed
# [Topic ID] [Topic Name]
(MeSH_term[MeSH Terms] OR free_text_1[tiab] OR free_text_2[tiab] OR abbreviation[tiab])
AND (disease/phenomenon_keyword[tiab])
AND (species/population_filter[tiab])
AND (study_type_filter[tiab] — optional)
```

#### Journal Quality Gatekeeping / 期刊质量守门

**EN:** Apply journal tier filtering at retrieval stage — do NOT defer quality assessment to post-download.

**CN:** 在检索阶段即执行期刊分层筛选——不要把质量评估推迟到下载之后。

| Tier | EN: Strategy | CN: 策略 |
|------|-------------|----------|
| **Tier S (Top)** | Directly include as P0 candidates. Journals like Science, Nature, Cell Metab. | 直接纳入P0候选 |
| **Tier A (Domain Authority)** | Include as P1 candidates. | 纳入P1候选 |
| **Tier B (Acceptable)** | Evaluate per-paper; assign to P1 or P2. | 逐篇评估后纳入P1或P2 |
| **Tier C (Caution)** | Only if highly-cited AND methodologically rigorous. | 仅限高被引且方法学严谨者 |
| **⚠️ Watch List** | Only if truly innovative methods AND cited above threshold; otherwise discard. | 仅限方法学确实创新且被引>阈值者，否则舍弃 |
| **❌ Exclude List** | Discard immediately. Never enter screening pool. | 直接舍弃，不进入初筛池 |

**EN — Universal exclusion list (extendable per domain):**
- MDPI portfolio journals (high self-citation, extremely short review cycles)
- Unpeer-reviewed preprint platforms (TechRxiv, etc.)
- Conference abstracts without DOI
- Theses/dissertations (when content is covered by journal papers)
- Predatory journals

**CN — 通用排除名单（可按领域扩展）：**
- MDPI旗下多数期刊（高自引、审稿周期极短）
- 未经同行评审的预印本平台（TechRxiv等）
- 无DOI的会议论文摘要
- 学位论文（内容已被期刊论文覆盖时）
- 掠夺性期刊（predatory journals）

**EN — Quality Red Flags checklist:**
- ⚠️ Extremely short review cycle (<30 days from submission to acceptance)
- ⚠️ Suspiciously perfect accuracy (AUC >0.99 suggests data leakage or overfitting)
- ⚠️ Opaque external validation
- ⚠️ Input modality mismatch with product scenario
- ⚠️ Extremely small sample size (n<5 case reports, unless unique presentation)
- ⚠️ Undeclared conflicts of interest (industry-funded studies must be flagged)

**CN — 质量红旗检查清单：**
- ⚠️ 审稿周期极短（投稿到接受<30天）
- ⚠️ 准确率过于完美（AUC>0.99需警惕数据泄露或过拟合）
- ⚠️ 外部验证不透明
- ⚠️ 输入模态与产品场景不匹配
- ⚠️ 样本量极小（n<5的病例报告，除非表现独特）
- ⚠️ 未声明的利益冲突（企业资助研究必须标注）

### 3.3 Track C: Embedding-Based Semantic Recall / 嵌入数据库语义召回

**EN:** Build a semantic keyword matrix organized by dimension (core entity, disease association, intervention, population). Each P0 topic needs 2-3 natural-language query templates with full research context — not isolated keywords.

**CN:** 按语义维度（核心实体、疾病关联、干预方法、人群/品种）组织关键词矩阵。每个P0主题需准备2-3个自然语言查询模板，包含完整的研究语境而非孤立关键词。

| Semantic Dimension / 语义维度 | Core Keywords / 核心词 | Extended Synonyms / 扩展同义词 | Semantic Approximations / 语义近似词 |
|------|------|------|------|
| Core Entity / 核心实体 | ... | ... | ... |
| Disease Association / 疾病关联 | ... | ... | ... |
| Intervention / 干预方法 | ... | ... | ... |
| Population / 人群 | ... | ... | ... |

### 3.4 Result Fusion & Deduplication / 检索结果融合与去重

**EN:**
1. Merge all three tracks into a unified candidate pool.
2. Deduplicate by PMID/DOI.
3. Title/abstract screening: remove irrelevant, clearly low-quality, or off-topic papers.
4. Classify by topic ID; check if each topic meets its target count.
5. Generate download manifest annotated with priority (T0/P0/P1/P2).

**CN:**
1. 三轨结果合并到统一候选池
2. 按PMID/DOI去重
3. 标题/摘要初筛：剔除与主题无关、明显低质量、不符合纳入标准的文献
4. 按主题ID分类，检查每个主题的文献量是否达标
5. 生成下载清单，标注优先级（T0/P0/P1/P2）

---

## Phase 4: Knowledge Transformation / 知识转化

### 4.1 Full-Text Acquisition / 全文获取策略

| Literature Type / 文献类型 | EN: Method | CN: 获取方式 | Format Priority / 格式优先级 |
|---|---|---|---|
| Open Access | Europe PMC REST API (`/rest/{pmcid}/fullTextXML`) | Europe PMC REST API | JATS XML > PDF |
| Subscription-based | DOI lookup → institutional access / interlibrary loan → manual download | DOI定位 → 机构订阅/馆际互借 → 手动下载 | PDF |
| Clinical Guidelines | Official society website direct download | 官方学会网站直接下载 | PDF |
| Textbooks | Commercial purchase / library loan | 商业购买/图书馆借阅 | PDF (extract relevant chapters) |

### 4.2 Evidence Grading (GRADE) / 证据分级评估

#### Four-Level Evidence Pyramid / 四级证据金字塔

| Level / 层级 | EN: Evidence Type | CN: 证据类型 | GRADE | Clinical Weight / 临床权重 | Acquisition Priority / 获取优先级 |
|---|---|---|---|---|---|
| **T0** | Textbooks / Authoritative clinical guidelines | 教科书 / 权威机构临床指南 | ⊕⊕⊕⊕ High / 高 | Directly adoptable / 可直接采纳 | Highest / 最高 |
| **P0** | Multi-center cohorts / High-quality diagnostic studies / Top-journal papers | 多中心队列 / 高质量诊断研究 / 顶刊论文 | ⊕⊕⊕◯ Moderate / 中 | Highly credible / 高度可信 | High / 高 |
| **P1** | Single-center cohorts / Case-control / Domain reviews | 单中心队列 / 病例对照 / 领域综述 | ⊕⊕◯◯ Low / 低 | Interpret with caution / 需谨慎解读 | Medium / 中 |
| **P2** | Case reports / Preprints / In-vitro experiments | 病例报告 / 预印本 / 体外实验 | ⊕◯◯◯ Very Low / 极低 | Reference only / 仅作参考 | Low / 低 |

#### GRADE Upgrade/Downgrade Rules / GRADE升降级规则

**Downgrade factors (-1 level each / 每项降1级):**

| EN | CN |
|----|----|
| Risk of bias (study design flaws) | 偏倚风险（研究设计缺陷） |
| Inconsistency (high inter-study heterogeneity, I²>50%) | 不一致性（研究间异质性大） |
| Indirectness (population/intervention/outcome differs from target) | 间接性（人群/干预/结局与目标场景不同） |
| Imprecision (overly wide confidence intervals) | 不精确性（置信区间过宽） |
| Publication bias | 发表偏倚 |

**Upgrade factors (+1 level each / 每项升1级):**

| EN | CN |
|----|----|
| Large effect size (RR>2 or <0.5) | 大效应量（RR>2或<0.5） |
| Dose-response relationship | 剂量-反应关系 |
| Residual confounding likely biases toward null | 残余混杂因素反向效应 |

**Critical principles / 重要原则:**

| EN | CN |
|----|----|
| Editorial/Comment/Letter is NOT a formal guideline — must be downgraded. | Editorial/Comment/Letter不是正式指南，必须降级。 |
| Author authority does NOT override journal quality — a famous author in a low-tier journal gets downgraded, not upgraded. | 作者权威不凌驾于期刊质量——知名作者发在水刊上按期刊质量降级，而非按作者权威升级。 |
| In-vitro / animal experiments cannot be directly extrapolated to clinical recommendations. | 体外实验/动物实验不能直接外推为临床建议。 |
| Papers published before the latest textbook were likely already subsumed — only retain those with unique datasets. | 比最新教科书发表早的论文，其核心发现大概率已被涵盖——仅保留有独特数据集的。 |

### 4.3 Obsidian Knowledge Base Structure / Obsidian知识库结构

#### Directory Layout / 目录组织规范

```
vault/
├── 01_Knowledge_Framework/    # Framework layer: MOCs, evidence standards, methodology
│   │                           # 框架层：知识地图、证据标准、方法论
│   ├── Evidence_Grading.md
│   ├── Evidence_Pyramid.md
│   ├── MOC_*.md               # Map of Content
│   └── ...
├── 0X_[Module_Name]/           # Module-specific knowledge nodes
│   │                           # 各模块知识节点
│   ├── _[Guideline_Name].md    # Guideline source notes (_prefix = reference material)
│   │                           # 指南原文笔记（_前缀 = 参考资料）
│   ├── [Topic_Name].md         # Structured knowledge nodes
│   │                           # 结构化知识节点
│   └── _raw/                   # Raw text extractions (optional)
│                               # 原始文本提取（可选）
├── 07_References/             # Reference layer
│   │                           # 参考层
│   ├── Literature_Index.md    # Complete literature index with GRADE
│   │                           # 完整文献索引（含GRADE分级）
│   └── Scholar_Network.md     # Scholar collaboration network
│                               # 学者合作网络
└── 00_INDEX.md                # Entry point
```

#### Node Types & Frontmatter / 节点类型与Frontmatter规范

| Node Type / 节点类型 | Naming / 命名规范 | Required Frontmatter / 必需字段 |
|---|---|---|
| MOC Map / 地图节点 | `MOC_*.md` | title, tags: [MOC] |
| Disease/Topic / 疾病/主题节点 | `[Topic_Name].md` (snake_case) | title, tags, module, [domain-specific] |
| Guideline Source / 指南原文节点 | `_[Guideline_Name].md` (_prefix) | title, tags: [reference, guideline], source, year |
| Population Profile / 人群档案 | `[Profile_Name].md` | title, tags: [population], predispositions |
| Assessment Tool / 评估工具 | `[Tool_Name].md` | title, tags: [assessment], validation |

#### Wikilink Rules / Wikilink建立规范

| EN | CN |
|----|----|
| Every knowledge node MUST link to at least 1 MOC node + 1 related node. | 每个知识节点必须至少连接1个MOC节点 + 1个相关节点。 |
| Cross-module links MUST be established for all comorbidity associations. | 共病关联的跨模块链接必须建立。 |
| Check bidirectionality: if A links B, consider whether B should link back to A. | 双向链接检查：A链接B时，考虑B是否需要回链A。 |
| Link granularity: link to specific notes; use `[[Note#Section]]` for section-level links. | 链接粒度：链接到具体笔记；必要时使用 `[[笔记名#章节名]]` 定位到章节。 |

### 4.4 Structured Knowledge Output (YAML) / 结构化知识库产物

**EN:** For knowledge consumed by code/rule engines, output as YAML with standardized fields: `what_it_is`, `predisposed_individuals`, `defining_characteristics` (with `image_recognition_labels`), `clinical_significance` (with `key_know_why` and `complications`), `diagnosis` (with `differential_diagnosis` and `grading`), `treatment` (with `contraindications`), `prognosis`, `referral_criteria`.

**CN:** 需被代码/规则引擎直接消费的知识，输出为YAML格式，包含标准化字段：`what_it_is`(定义)、`predisposed_individuals`(易感人群)、`defining_characteristics`(定义性特征，含`image_recognition_labels`)、`clinical_significance`(临床意义，含`key_know_why`和`complications`)、`diagnosis`(诊断，含`differential_diagnosis`和`grading`)、`treatment`(处置，含`contraindications`)、`prognosis`(预后)、`referral_criteria`(转诊标准)。

**Safety rules engine (deterministic, NOT LLM-dependent) / 安全规则引擎（确定性硬约束，不依赖LLM）:**
```yaml
safety_rules:
  - id: SR001
    description: "Corticosteroids contraindicated in corneal ulcer"
    condition: "diagnosis contains 'corneal ulcer'"
    contraindication: "corticosteroids"
    severity: critical
```

---

## Phase 5: Quality Audit / 质量审计

### Six Audit Checkpoints / 六大审计检查项

| # | EN: Checkpoint | CN: 检查内容 | Pass Criteria / 通过标准 |
|---|---------------|-------------|----------------------|
| 5.1 | **Broken-link detection**: Scan all wikilinks, verify target files exist. | **断链检测**：扫描所有wikilink，验证目标文件存在 | 0 broken links / 0断链 |
| 5.2 | **GRADE consistency**: Every literature citation must have a GRADE rating with upgrade/downgrade rationale. No editorial masquerading as guideline. | **GRADE一致性**：每条文献引用标注GRADE等级及升降级理由；无editorial冒充指南 | All literature graded; no misclassification / 全部已分级；无误分类 |
| 5.3 | **Literature completeness**: Cross-reference vault citations against actual PDF/XML files. | **文献完整性**：vault引用文献与实际PDF/XML交叉比对 | 100% traceability / 引用文献100%可追溯 |
| 5.4 | **Orphan node detection**: Analyze wikilink network connectivity. | **孤立节点检测**：分析wikilink网络连接度 | Each node links to ≥1 MOC + ≥1 related node; 0 orphans / 每节点至少连1个MOC+1个相关节点；0孤立 |
| 5.5 | **Frontmatter consistency**: Verify all required fields exist and are correctly formatted. | **Frontmatter一致性**：验证所有节点必填字段存在且格式正确 | 100% template compliance / 100%符合模板规范 |
| 5.6 | **Cross-module links**: Verify all comorbidity associations have cross-module wikilinks established. | **跨模块链接**：验证共病关联的跨模块wikilink已建立 | All comorbidity matrix links exist / 共病矩阵中所有关联已建立链接 |

---

## Knowledge Graph Architecture / 知识图谱架构

### Three-Tier Corpus Classification / 语料三层分类

| Type / 类型 | EN: Format & Role | CN: 格式与用途 |
|---|---|---|
| **A: Structured Rules** | YAML/JSON — Parsed into code/config, NOT fed to RAG. Used for safety rules, disease associations, classification labels → deterministic tools. | YAML/JSON — 解析为代码/配置，不进RAG。用于安全规则、疾病关联、分类标签 → 确定性工具 |
| **B: Semi-structured Knowledge** | Obsidian .md — **Core Graph RAG retrieval source**. Wiki links form the L1 graph layer. The "know-why" fuel for Agent reasoning. | Obsidian .md — **Graph RAG核心检索源**。Wiki links构成L1层图。Agent推理的"know-why"燃料 |
| **C: Raw Literature** | PDF/JATS XML — Parse abstracts into RAG; full-text processing deferred. Used for evidence traceability. | PDF/JATS XML — 解析摘要进RAG；全文后置。用于原始证据溯源 |

### Dual-Layer Graph / 双层图结构

| Layer / 层 | EN | CN |
|---|---|---|
| **L1 (Document-level)** | Built from Obsidian wiki links. Nodes = notes, edges = wikilinks. Human-curated, high quality, coarse granularity. | 基于Obsidian wiki links构建。节点=笔记，边=wikilink。人工策展，质量高，粒度粗。 |
| **L2 (Entity-level)** | Extract medical entities (diseases, symptoms, drugs, pathogens, breeds) and relations from note text. Incrementally built for fine-grained associations. | 从笔记正文中抽取医学实体（疾病、症状、药物、病原体、品种）及关系。增量构建细粒度关联。 |

### Retrieval Strategy / 检索策略

**EN:**
1. Query enters → vector retrieval returns semantically matching chunks (split by header section).
2. Simultaneously, perform 1-2 hop multi-hop reasoning on L1+L2 graph, returning associated entity chunks.
3. Merge both paths and feed into Agent's ReAct loop.

**CN:**
1. 查询进入 → 向量检索返回语义匹配的chunk（按header section切分）
2. 同时在L1+L2图上进行1-2跳多跳推理，返回关联实体的chunk
3. 两路结果合并后送入Agent的ReAct循环

### Chunking Strategy / Chunking策略

**EN:** Split by Markdown header section. Each chunk carries: frontmatter metadata (disease name, module, urgency), section title, section content, and preserved wiki links as L1 edges.

**CN:** 按Markdown header section切分。每个chunk携带：frontmatter元数据（疾病名/模块/紧急度）、section标题、section内容，以及保留的wiki links作为L1层边。

---

## Meta-Rules Reference / 核心元规则一览

| Dimension / 维度 | EN: Meta-Rule | CN: 元规则 |
|---|---|---|
| **Scholar Search / 学者搜寻** | 3-tier ranking: Tier 1 (≥10 papers) / Tier 2 (3-9) / Tier 3 (1-2). Scholar-first, not keyword-first. | 三层分级：Tier 1(≥10篇) / Tier 2(3-9篇) / Tier 3(1-2篇)。学者优先于关键词。 |
| **Literature Retrieval / 文献检索** | 3 parallel tracks: scholar tracking + MeSH/free-text keywords + embedding semantic recall. | 三轨并行：学者追踪 + MeSH+自由词关键词 + 嵌入语义召回。 |
| **Evidence Grading / 证据分级** | GRADE with dynamic upgrade/downgrade. Editorial/comment MUST NOT be treated as guideline. Author authority does NOT override journal quality. | GRADE体系动态升降级。editorial/comment不得冒充指南。作者权威不凌驾于期刊质量。 |
| **Quality Gatekeeping / 质量守门** | 5-tier journal classification (S/A/B/C/Exclude). MDPI and predatory journals excluded outright. Red flag checklist for suspicious papers. | 期刊五层分类(S/A/B/C/排除)。MDPI和掠夺性期刊直接排除。可疑文献红旗检查清单。 |
| **Knowledge Graph / 知识图谱** | Dual-layer: L1 document-level (wikilinks) + L2 entity-level (multi-hop reasoning). Graph-augmented RAG. | 双层图：L1文档级(wikilink) + L2实体级(多跳推理)。Graph-augmented RAG。 |
| **Corpus Layering / 语料分层** | A: Structured rules (YAML→code) + B: Semi-structured knowledge (MD→Graph RAG) + C: Raw literature (PDF/XML→evidence traceability). | A类结构化规则(YAML→代码) + B类半结构化知识(MD→Graph RAG) + C类原始文献(PDF/XML→证据溯源)。 |
| **Quality Audit / 质量审计** | 6 mandatory checkpoints: broken links, GRADE consistency, literature completeness, orphan nodes, frontmatter compliance, cross-module links. | 6大强制检查项：断链、GRADE一致性、文献完整性、孤立节点、Frontmatter规范、跨模块链接。 |

---

## Domain Adaptation Guide / 领域适配指南

### What to Adapt / 需要调整的部分

| EN | CN |
|----|----|
| Journal tier table — reclassify based on target domain's journal reputation. | 期刊分层表 — 根据目标领域的期刊声誉重新划分。 |
| Evidence pyramid — adjust research type definitions per tier (e.g., human medicine weights RCTs higher; engineering may prioritize benchmarks). | 证据金字塔 — 根据领域特点调整各层级的研究类型定义。 |
| MeSH terms / keywords — replace with target domain's controlled vocabulary. | MeSH词/关键词 — 替换为目标领域的规范术语。 |
| Frontmatter fields — customize for domain-specific node types (disease → technology, product, etc.). | Frontmatter字段 — 根据领域需求定制节点类型。 |
| Safety rules — define domain-specific hard constraints and compliance red lines. | 安全规则 — 定义领域特定的硬约束和合规红线。 |
| Academic organizations — replace with target domain's authoritative bodies. | 学术组织名单 — 替换为目标领域的权威学术组织。 |

### What Stays Fixed / 不需要调整的核心元规则

| EN | CN |
|----|----|
| 5-phase workflow sequence | 5阶段工作流顺序 |
| 3-tier scholar ranking model | 学者三层分级模型 |
| 3-track retrieval strategy (scholar + keyword + embedding) | 三轨检索策略（学者 + 关键词 + 嵌入） |
| GRADE upgrade/downgrade methodology | GRADE升降级方法论 |
| Dual-layer graph structure | 双层图结构 |
| 6 quality audit checkpoints | 六大质量审计检查项 |

---

## Anti-Patterns / 反模式

| # | EN: Don't Do This | CN: 请勿这样做 | Why / 原因 |
|---|---|---|---|
| 1 | Start with keyword searches without anchoring scholars first. | 从关键词检索开始而不先锚定学者。 | Misses entire high-value literature clusters anchored around core scholars. / 会遗漏围绕核心学者的高价值文献集群。 |
| 2 | Filter journals by impact factor with a single cutoff. | 按IF一刀切筛选期刊。 | Kills domain-authoritative journals with modest IFs (e.g., Vet Ophthalmology). / 会误杀IF不高但领域权威的专业期刊。 |
| 3 | Collect literature first, evaluate quality later. | 先收集文献再评估质量。 | Wastes time acquiring and reading low-quality papers. / 浪费时间在低质量文献的获取和阅读上。 |
| 4 | Store documents flat without wikilinks. | 扁平存储文档而不建立wikilink。 | Loses multi-hop reasoning capability; degrades to vanilla RAG. / 丧失多跳推理能力，退化为普通RAG。 |
| 5 | Trust famous authors publishing in low-quality journals. | 信任知名作者发在水刊上的文章。 | Author authority ≠ journal quality. A Nature-published unknown > MDPI-published luminary. / 作者权威≠期刊质量。 |
| 6 | Use P2 case reports to support clinical recommendations. | 用P2病例报告支撑临床建议。 | Very-low-quality evidence is reference only, never directive. | 极低质量证据只能参考，不可指导临床。 |
| 7 | Treat editorials/comments as formal guidelines. | 将editorial/comment当指南用。 | Must be downgraded to P1. / 必须降级为P1。 |
| 8 | Create orphan nodes with no wikilink connections. | 创建无wikilink连接的孤立节点。 | Knowledge graph becomes a collection of information silos. | 知识图谱沦为信息孤岛集合。 |
| 9 | Skip quality audit before delivery. | 跳过质量审计直接交付。 | Broken links and inconsistencies cause severe errors in Agent reasoning. | 断链和不一致会在Agent推理时造成严重错误。 |

---

## File Structure / 文件结构

```
.trae/skills/scholarly-research-kb/
├── SKILL.md                                        # EN: Main skill file — complete meta-rules (554 lines)
│                                                   # CN: 主Skill文件 — 完整元规则（554行）
└── templates/
    ├── requirements_document_template.md            # EN: Phase 1 requirements doc template
    │                                               # CN: Phase 1需求文档模板
    ├── knowledge_node_template.md                   # EN: Obsidian knowledge node template
    │                                               # CN: Obsidian知识节点模板
    └── quality_audit_template.md                    # EN: Phase 5 quality audit report template
                                                    # CN: Phase 5质量审计报告模板
```

---

## Battle-Tested Validation / 实战验证

**EN:** This methodology has been production-validated across three modules of the iPaw project:

| Module / 模块 | EN | CN |
|---|---|---|
| **M1 Ophthalmology** | 25 PDFs, 499 wikilinks, 0 broken links. Covered KCS, corneal ulcer, cataract, conjunctivitis, cherry eye, uveitis, feline conjunctivitis. | 25篇PDF、499个wikilink、0断链。覆盖KCS、角膜溃疡、白内障、结膜炎、樱桃眼、葡萄膜炎、猫结膜炎。 |
| **M2 Dermatology** | Covered 7 major skin conditions across 6 sub-categories: CAD (13 papers), pyoderma/MRSP (13 papers), other infections (5 papers), AI/computer vision (5 papers), epidemiology/breeds (8 papers), feline allergy (5 papers). | 涵盖6个子类别的7大皮肤病：CAD异位性皮炎(13篇)、脓皮症/MRSP(13篇)、其他感染(5篇)、AI/计算机视觉(5篇)、流行病学/品种(8篇)、猫过敏(5篇)。 |
| **M3 Body Condition** | Complete scholar tracking: German AJ (RVC, 76 papers), Raffan E (Cambridge, POMC gene discoverer, Cell Metab), Churchill J (WSAVA nutrition guidelines core). | 核心学者完整追踪：German AJ(RVC, 76篇)、Raffan E(剑桥, POMC基因发现者, Cell Metab)、Churchill J(WSAVA营养指南核心)。 |

---

## Installation / 安装方法

### In TRAE / 在TRAE中安装

**EN:** Clone this repository into your project directory, or copy the `.trae/skills/scholarly-research-kb/` folder into your project's `.trae/skills/` directory. TRAE will automatically recognize it as an available skill.

**CN:** 将本仓库clone到你的项目目录，或将 `.trae/skills/scholarly-research-kb/` 目录复制到你的项目的 `.trae/skills/` 下。TRAE会自动识别该Skill。

```bash
git clone https://github.com/yuyang-rgb094/fast-med-knowledge-map.git
cp -r fast-med-knowledge-map/.trae/skills/scholarly-research-kb your-project/.trae/skills/
```

### Trigger Conditions / 触发条件

**EN:** TRAE will automatically invoke this skill when you:
- Start building a new domain knowledge base
- Conduct a systematic literature review
- Build an evidence-based knowledge graph
- Analyze scholarly networks
- Assess literature quality

**CN:** 当你执行以下任务时，TRAE会自动调用此Skill：
- 开始一个新领域的知识库构建
- 系统性文献综述
- 循证知识图谱搭建
- 学者网络分析
- 文献质量评估

---

## License

MIT