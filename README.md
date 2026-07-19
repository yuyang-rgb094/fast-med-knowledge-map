# Fast Medical Knowledge Map (scholarly-research-kb)

> 一套经过实战验证的循证医学知识库构建元规则Skill，可平移到任何需要系统性文献检索、学者发现、知识图谱构建的领域。

## 概述

本Skill源自iPaw项目（AI兽医辅助诊断系统）三个模块（眼科M1、皮肤科M2、体况管理M3）的实战经验总结，提供了一套完整的**5阶段知识工程工作流**，从需求规划到质量审计全覆盖。

## 核心理念

- **学者优先于关键词**：先锚定领域核心学者，再通过合作网络展开，避免关键词检索遗漏
- **证据金字塔分层**：T0教科书/指南 → P0多中心队列 → P1单中心 → P2病例报告
- **质量先于数量**：严格执行期刊守门和排除标准，宁缺毋滥
- **图结构优先**：基于Obsidian wikilink构建双层知识图谱，天然支持Graph-augmented RAG

## 5阶段工作流

```
Phase 1: 需求规划 → 定义范围、主题分类树、知识缺口矩阵
Phase 2: 学者发现 → Tier 1/2/3 三层分级 + 合作网络图谱
Phase 3: 双轨检索 → Track A(学者追踪) + Track B(主题关键词) + Track C(嵌入召回)
Phase 4: 知识转化 → 全文获取 → GRADE评估 → 结构化笔记 → 图谱连接
Phase 5: 质量审计 → 断链检测 + GRADE一致性 + 孤立节点 + 文献完整性
```

## 目录结构

```
.trae/skills/scholarly-research-kb/
├── SKILL.md                              # 主Skill文件，包含完整元规则
└── templates/
    ├── requirements_document_template.md  # Phase 1需求文档模板
    ├── knowledge_node_template.md         # Obsidian知识节点模板
    └── quality_audit_template.md          # Phase 5质量审计报告模板
```

## 核心元规则一览

| 维度 | 元规则 |
|------|--------|
| **学者搜寻** | Tier 1(≥10篇)/Tier 2(3-9篇)/Tier 3(1-2篇)三层分级模型 |
| **文献检索** | 三轨并行：学者追踪 + MeSH+自由词关键词 + 嵌入语义召回 |
| **证据分级** | GRADE体系动态升降级；editorial/comment不得冒充指南 |
| **质量守门** | 期刊Tier S/A/B/C/排除五层；MDPI等水刊直接排除 |
| **知识图谱** | 双层图：L1文档级(wikilink) + L2实体级(多跳推理) |
| **语料分层** | A类结构化规则(YAML) + B类半结构化知识(MD) + C类原始文献(PDF/XML) |
| **质量审计** | 6大检查项：断链、GRADE一致性、文献完整性、孤立节点、Frontmatter、跨模块链接 |

## 使用方法

### 在TRAE中安装

将本仓库clone到你的项目目录，或将 `.trae/skills/scholarly-research-kb/` 目录复制到你的项目的 `.trae/skills/` 下。TRAE会自动识别该Skill。

### 触发条件

当你需要执行以下任务时，TRAE会自动调用此Skill：
- 开始一个新领域的知识库构建
- 系统性文献综述
- 循证医学知识图谱搭建
- 学者网络分析
- 文献质量评估

## 领域适配

平移到新领域时需要调整：
- 期刊分层表（根据目标领域期刊声誉）
- 证据金字塔研究类型定义
- MeSH术语表/关键词
- Frontmatter字段
- 安全规则/合规红线

**不需要调整的核心元规则**：5阶段工作流顺序、学者三层分级、三轨检索策略、GRADE升降级方法、双层图结构、六大审计项。

## 反模式（请勿这样做）

1. ❌ 从关键词检索开始而不先锚定学者
2. ❌ 按IF一刀切筛选期刊（会误杀专业领域权威期刊）
3. ❌ 先收集文献再评估质量
4. ❌ 扁平存储文档而不建立wikilink
5. ❌ 作者权威凌驾于期刊质量
6. ❌ P2病例报告用来支撑临床建议
7. ❌ editorial/comment当指南用
8. ❌ 跳过质量审计直接交付

## 实战验证

本方法论已在iPaw项目中成功应用于三个模块：
- **M1眼科**：25篇PDF、499个wikilink、0断链
- **M2皮肤科**：涵盖CAD、脓皮症、蠕形螨等7大皮肤病
- **M3体况**：German AJ(76篇)、Raffan E(Cell Metab)等核心学者完整追踪

## License

MIT
