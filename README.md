# Fast Medical Knowledge Map

> A battle-tested TRAE skill for systematic scholarly knowledge base construction — literature retrieval, scholar discovery, knowledge graph building, and evidence grading.
>
> 经过实战验证的TRAE Skill，用于系统性构建循证知识库——文献检索、学者发现、知识图谱搭建与证据分级。

---

## What Is This? / 这是什么？

**EN:** A domain-agnostic meta-skill distilled from three production modules of the iPaw project (an AI veterinary diagnostic system). It encodes a complete **5-phase knowledge engineering workflow** — from requirements planning through quality auditing — into a reusable TRAE skill that can be ported to medicine, engineering, social sciences, or any field requiring rigorous evidence-based knowledge systems.

**CN:** 一套领域无关的元规则Skill，源自iPaw项目（AI兽医辅助诊断系统）三个生产模块的实战经验。将完整的**5阶段知识工程工作流**——从需求规划到质量审计——封装为可复用的TRAE Skill，可平移到医学、工程学、社会科学等任何需要严格循证知识体系的领域。

---

## Core Principles / 核心理念

| EN | CN |
|----|----|
| **Scholars before keywords** — Anchor domain core scholars first, then expand via collaboration networks. | **学者优先于关键词** — 先锚定领域核心学者，再通过合作网络展开。 |
| **Evidence pyramid layering** — T0 Textbooks/Guidelines → P0 Multi-center → P1 Single-center → P2 Case reports. | **证据金字塔分层** — T0教科书/指南 → P0多中心 → P1单中心 → P2病例报告。 |
| **Quality over quantity** — Strict journal gatekeeping and exclusion criteria. | **质量先于数量** — 严格执行期刊守门和排除标准。 |
| **Graph structure over flat docs** — Obsidian wikilinks form a dual-layer knowledge graph for Graph-augmented RAG. | **图结构优先于扁平文档** — 基于Obsidian wikilink构建双层知识图谱，支持Graph-augmented RAG。 |

---

## 5-Phase Workflow / 5阶段工作流

```
Phase 1: Requirements Planning    → Define scope, topic taxonomy, knowledge gap matrix
         需求规划                   → 定义范围、主题分类树、知识缺口矩阵
Phase 2: Scholar Discovery        → Tier 1/2/3 stratified anchoring + collaboration network
         学者发现                   → Tier 1/2/3 分层锚定 + 合作网络图谱
Phase 3: Dual-Track Retrieval     → Track A (scholars) + Track B (keywords) + Track C (embedding recall)
         双轨检索                   → Track A(学者) + Track B(关键词) + Track C(嵌入召回)
Phase 4: Knowledge Transformation → Full-text → GRADE assessment → Structured notes → Graph linking
         知识转化                   → 全文获取 → GRADE评估 → 结构化笔记 → 图谱连接
Phase 5: Quality Audit            → Broken links + GRADE consistency + Orphan nodes + Literature completeness
         质量审计                   → 断链检测 + GRADE一致性 + 孤立节点 + 文献完整性
```

---

## Meta-Rules at a Glance / 核心元规则一览

| Dimension / 维度 | EN: Meta-Rule | CN: 元规则 |
|---|---|---|
| **Scholar Search / 学者搜寻** | 3-tier ranking: Tier 1 (≥10 papers) / Tier 2 (3-9) / Tier 3 (1-2) | 三层分级：Tier 1(≥10篇) / Tier 2(3-9篇) / Tier 3(1-2篇) |
| **Retrieval / 文献检索** | 3 parallel tracks: scholar tracking + MeSH/keyword + embedding semantic recall | 三轨并行：学者追踪 + MeSH+自由词 + 嵌入语义召回 |
| **Evidence / 证据分级** | GRADE with dynamic upgrade/downgrade; editorial ≠ guideline | GRADE动态升降级；editorial ≠ 指南 |
| **Quality Gate / 质量守门** | 5-tier journal classification (S/A/B/C/Exclude); MDPI excluded | 期刊五层分类(S/A/B/C/排除)；MDPI直接排除 |
| **Knowledge Graph / 知识图谱** | Dual-layer: L1 document-level (wikilinks) + L2 entity-level (multi-hop) | 双层图：L1文档级(wikilink) + L2实体级(多跳推理) |
| **Corpus / 语料分层** | A: Structured rules (YAML) + B: Knowledge notes (MD) + C: Raw literature (PDF/XML) | A类结构化规则 + B类半结构化知识 + C类原始文献 |
| **Audit / 质量审计** | 6 mandatory checkpoints: broken links, GRADE, completeness, orphans, frontmatter, cross-module | 6大检查项：断链、GRADE、完整性、孤立节点、Frontmatter、跨模块链接 |

---

## File Structure / 文件结构

```
.trae/skills/scholarly-research-kb/
├── SKILL.md                                        # Complete meta-rules (554 lines)
│                                                   # 完整元规则（554行）
└── templates/
    ├── requirements_document_template.md            # Phase 1 requirements doc template
    │                                               # Phase 1 需求文档模板
    ├── knowledge_node_template.md                   # Obsidian knowledge node template
    │                                               # Obsidian 知识节点模板
    └── quality_audit_template.md                    # Phase 5 quality audit report template
                                                    # Phase 5 质量审计报告模板

DOCUMENTATION.md                                    # Full bilingual (EN/CN) reference documentation
                                                    # 完整英中对照参考文档
```

---

## Quick Start / 快速开始

### Installation / 安装

```bash
# Clone and copy the skill into your TRAE project
git clone https://github.com/yuyang-rgb094/fast-med-knowledge-map.git
cp -r fast-med-knowledge-map/.trae/skills/scholarly-research-kb your-project/.trae/skills/
```

**EN:** TRAE will auto-detect the skill. It triggers when you start a new domain knowledge base, conduct systematic literature reviews, or build evidence-based knowledge graphs.

**CN:** TRAE会自动识别该Skill。当你开始新领域知识库构建、系统性文献综述或搭建循证知识图谱时自动触发。

---

## Domain Adaptation / 领域适配

### Adapt these per domain / 需要调整

- Journal tier table / 期刊分层表
- Evidence pyramid definitions / 证据金字塔研究类型定义
- MeSH terms / keywords / MeSH术语表
- Frontmatter fields / Frontmatter字段
- Safety rules / 安全规则

### Keep these fixed / 不需要调整

- 5-phase workflow sequence / 5阶段工作流顺序
- 3-tier scholar ranking / 学者三层分级
- 3-track retrieval / 三轨检索策略
- GRADE methodology / GRADE升降级方法
- Dual-layer graph / 双层图结构
- 6 audit checkpoints / 六大审计项

---

## Anti-Patterns / 反模式

| # | EN | CN |
|---|----|----|
| 1 | ❌ Keyword search before scholar anchoring | ❌ 不锚定学者就从关键词开始 |
| 2 | ❌ IF-based journal filtering (kills domain-authoritative journals) | ❌ 按IF一刀切（会误杀领域权威期刊） |
| 3 | ❌ Collect first, evaluate quality later | ❌ 先收集再评估质量 |
| 4 | ❌ Flat docs without wikilinks | ❌ 扁平文档无wikilink |
| 5 | ❌ Author authority > journal quality | ❌ 作者权威凌驾于期刊质量 |
| 6 | ❌ P2 case reports for clinical recommendations | ❌ P2病例报告支撑临床建议 |
| 7 | ❌ Editorial/comment as guideline | ❌ editorial/comment当指南 |
| 8 | ❌ Skip quality audit | ❌ 跳过质量审计 |

---

## Battle-Tested / 实战验证

Validated across three production modules of the iPaw project / 在iPaw项目三个生产模块中验证：

| Module | EN | CN |
|---|---|---|
| **M1 Ophthalmology** | 25 PDFs, 499 wikilinks, 0 broken links | 25篇PDF、499个wikilink、0断链 |
| **M2 Dermatology** | 7 skin conditions, 49 papers across 6 sub-categories | 7大皮肤病，6个子类别共49篇论文 |
| **M3 Body Condition** | German AJ (76 papers, RVC), Raffan E (Cell Metab), Churchill J (WSAVA) | German AJ(76篇)、Raffan E(Cell Metab)、Churchill J(WSAVA) |

---

## Documentation / 详细文档

For the complete bilingual (EN/CN) reference with all templates, GRADE rules, and search string examples, see [**DOCUMENTATION.md**](./DOCUMENTATION.md).

完整英中对照参考文档（含全部模板、GRADE规则、检索式示例）请参阅 [**DOCUMENTATION.md**](./DOCUMENTATION.md)。

---

## License

MIT