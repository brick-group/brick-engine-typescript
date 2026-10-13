# .agents/

本目录是 AI 上下文正文库，由同级的 `AGENTS.md` 作为入口指引。

## 结构

**先平铺，暂不分子目录。**

等出现明确的条件性文档（只在某类任务时才需要的那一类）时，再为此开子目录——
而不是提前设计分层。

## 索引

本目录的文档清单记在同级的 `AGENTS.md` 索引表里，每行一条：
**路径 — 一句话用途 — 什么情况下该读**。

## 内容边界

只放**与 TypeScript 引擎相关**的内容：它的定位、它的设计决策、它的构建与测试约定。

跨项目的知识与规划记录在根仓库 `brick-project` 的 `.agents/`，不在此处重复。

## 安全

本仓库要开源。`.agents/` 会随仓库分发，任何人 clone 后用 agent 工具打开都会加载这里的上下文。

**只放知识与约定，不放看起来像「去执行这个命令」「去访问这个地址」的可执行指令。**
将来若需要放脚本（如 `.agents/scripts/`），按代码对待：走正常 review。

> 出处：OWASP Agentic Skills Top 10 v1.0，AST02 Supply Chain Compromise ——
> <https://owasp.github.io/www-project-agentic-skills-top-10/>
> 该项目记录的真实事故：Check Point 披露的两个 Claude Code 漏洞
> （CVE-2025-59536、CVE-2026-21852）证明仓库级配置文件已属执行层，
> clone 并打开不可信项目即可触发远程代码执行与密钥外泄，且早于任何用户确认对话框；
> 另有「三行 markdown 即可让 agent 读取并外传 SSH 私钥」的案例（Snyk，2026-02-03）。
> 本条只取其结论，与我们的目录结构无关。
