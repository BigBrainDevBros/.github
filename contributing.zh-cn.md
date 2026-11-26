# 参与 BigBrainDevBros 协作指南

[English](contributing.md) · [规范文档](template.md) · [检查清单](check.md) · [安全策略](security.md)

所有 **BigBrainDevBros** 仓库的贡献者与 AI 助手均需遵守 [规范文档](template.md) 与 [检查清单](check.md) 中的核心约定。

## 权限与协作方式

- 所有组织成员默认拥有仓库 **Write** 权限。
- 遵循以 `main` 为主干的开发模式，也可为跨模块或大型改动创建分支（`<type>/<issue>-<slug>`）并发起 Pull Request。
- 禁止对 `main` 执行 force-push 或重写共享提交历史。

## 双语协作规则（English / 简体中文）

1. **统一英文技术标识**：提交信息、分支名、SemVer 标签（`v1.0.0`）、Issue 标签、`[PREFIX]` 前缀、文件路径及 CI 工作流名称统一使用英文。
2. **双语文档**：长篇文档使用 `readme.md` + `readme.zh-cn.md` 互相链接，保持版本徽章同步。
3. **日常议题与讨论**：Issue、PR 与 Discussions 可自由使用英文或简体中文撰写正文；主史诗（Master Epic）与里程碑标题建议同时保留中英文以便检索。

## 提交前必查五项

1. **禁止直接二进制链接**：Markdown 中不得出现 `.dmg`、`.zip`、`.exe` 等直链，安装包统一走 GitHub Releases。
2. **三词提交格式**：严格匹配 `^[a-z]+: [a-z0-9]+ [a-z0-9]+ [a-z0-9]+$`（例如 `fix: sync mode state`）。
3. **全小写路径**：Git 跟踪的所有文件名与目录名必须为小写（`CNAME` 与 `TornTools` 例外）。
4. **标题格式与零表情**：Markdown 标题使用规范格式，文档与模板中禁止使用 emoji。
5. **发布审批**：未经维护者明确同意，不得私自打 tag 或发布 GitHub Release。

## 双语文档检查

只读的 `bilingual-docs.yml` 可复用工作流检查项目说明、贡献指南及 Wiki 首页的英中双向链接。项目可在工作流的 `jobs.<job>.uses` 中引用 `BigBrainDevBros/.github/.github/workflows/bilingual-docs.yml` 并固定到已审核的提交 SHA。翻译内容与发布版本仍须由审阅者核对。
