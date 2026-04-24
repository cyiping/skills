> **注意：** 本存儲庫包含 Anthropic 對 Claude 技能（Skills）的實現。有關 Agent Skills 標準的信息，請參閱 [agentskills.io](http://agentskills.io)。

# 技能 (Skills)
技能（Skills）是包含指令、腳本和資源的資料夾，Claude 會動態載入這些內容，以提高在專門任務上的表現。技能教導 Claude 如何以可重複的方式完成特定任務，無論是根據公司的品牌指南創建文件、使用組織的特定工作流分析數據，還是自動化個人任務。

欲了解更多信息，請查看：
- [什麼是技能？(What are skills?)](https://support.claude.com/en/articles/12512176-what-are-skills)
- [在 Claude 中使用技能 (Using skills in Claude)](https://support.claude.com/en/articles/12512180-using-skills-in-claude)
- [如何創建自定義技能 (How to create custom skills)](https://support.claude.com/en/articles/12512198-creating-custom-skills)
- [透過 Agent Skills 為代理裝備現實世界的能力 (Equipping agents for the real world with Agent Skills)](https://anthropic.com/engineering/equipping-agents-for-the-real-world-with-agent-skills)

# 關於此存儲庫

此存儲庫包含展示 Claude 技能系統可行性的技能案例。這些技能範圍涵蓋創意應用（藝術、音樂、設計）、技術任務（測試 Web 應用程式、MCP 伺服器生成）到企業工作流（溝通、品牌塑造等）。

每個技能都獨立存在於其自身的資料夾中，其中包含一個 `SKILL.md` 文件，記載了 Claude 使用的指令和元數據。瀏覽這些技能以獲取您自己技能的靈感，或了解不同的模式和方法。

本存儲庫中的許多技能都是開源的 (Apache 2.0)。我們還包含了支撐 [Claude 文件處理能力](https://www.anthropic.com/news/create-files) 的文件創建與編輯技能，位於 [`skills/docx`](./skills/docx), [`skills/pdf`](./skills/pdf), [`skills/pptx`](./skills/pptx), 和 [`skills/xlsx`](./skills/xlsx) 子資料夾中。這些是源代碼可用（source-available）而非完全開源的，但我們希望與開發者分享這些內容，作為在生產級 AI 應用程式中主動使用的更複雜技能的參考。

## 免責聲明

**這些技能僅供演示和教育目的。** 雖然 Claude 中可能提供其中一些功能，但您從 Claude 獲得的實現和行為可能與這些技能中顯示的有所不同。這些技能旨在說明模式和可能性。在依賴這些技能執行關鍵任務之前，請務必在您自己的環境中進行徹底測試。

# 技能集 (Skill Sets)
- [./skills](./skills): 創意與設計、開發與技術、企業與溝通、以及文件技能的範例。
- [./spec](./spec): Agent Skills 規範。
- [./template](./template): 技能模板。

# 在 Claude Code、Claude.ai 和 API 中嘗試

## Claude Code
您可以通過在 Claude Code 中執行以下命令，將此存儲庫註冊為 Claude Code Plugin 市場：
```
/plugin marketplace add anthropics/skills
```

接著，安裝特定的一組技能：
1. 選擇 `Browse and install plugins`
2. 選擇 `anthropic-agent-skills`
3. 選擇 `document-skills` 或 `example-skills`
4. 選擇 `Install now`

或者，直接通過以下方式安裝任一插件：
```
/plugin install document-skills@anthropic-agent-skills
/plugin install example-skills@anthropic-agent-skills
```

安裝插件後，您只需提到該技能即可使用。例如，如果您從市場安裝了 `document-skills` 插件，您可以要求 Claude Code 執行類似的操作：「使用 PDF 技能從 `path/to/some-file.pdf` 中提取表單欄位」

## Claude.ai

這些範例技能在 Claude.ai 的付費方案中均已提供。

要使用此存儲庫中的任何技能或上傳自定義技能，請遵循 [在 Claude 中使用技能](https://support.claude.com/en/articles/12512180-using-skills-in-claude#h_a4222fa77b) 中的說明。

## Claude API

您可以通過 Claude API 使用 Anthropic 預建的技能，並上傳自定義技能。更多詳情請參閱 [Skills API Quickstart](https://docs.claude.com/en/api/skills-guide#creating-a-skill)。

# 創建基礎技能

創建技能非常簡單 —— 只需要一個包含 YAML frontmatter 和指令的 `SKILL.md` 文件。您可以將本存儲庫中的 **template-skill** 作為起點：

```markdown
---
name: my-skill-name
description: A clear description of what this skill does and when to use it
---

# My Skill Name

[在此處添加 Claude 在此技能激活時將遵循的指令]

## 範例
- 使用範例 1
- 使用範例 2

## 指南
- 指南 1
- 指南 2
```

Frontmatter 僅需要兩個欄位：
- `name` - 技能的唯一識別碼（小寫，用連字符代替空格）
- `description` - 對技能用途及使用時機的完整描述

下方的 Markdown 內容包含 Claude 將遵循的指令、範例和指南。更多詳情請參閱 [如何創建自定義技能](https://support.claude.com/en/articles/12512198-creating-custom-skills)。

# 合作夥伴技能

技能是教導 Claude 如何更好地使用特定軟體的一種絕佳方式。當我們從合作夥伴那裡看到優秀的技能範例時，我們可能會在此處突出顯示其中的一部分：

- **Notion** - [Notion Skills for Claude](https://www.notion.so/notiondevs/Notion-Skills-for-Claude-28da4445d27180c7af1df7d8615723d0)
