![SolidWorks](https://img.shields.io/badge/SolidWorks-API-blue)
![MCP](https://img.shields.io/badge/MCP-Compatible-green)
![AI Automation](https://img.shields.io/badge/AI-Automation-orange)
# swapi-pilot

### swapi-pilot MCP - 你的 SolidWorks API 領航員

swapi-pilot 為 AI agents提供準確、最新的 SolidWorks API 文件庫
減少錯誤並提高自動化精度，可以說是SolidWorks Codeing專用的上下文關係(Context)。

你還在網路上跟找VBA Macro？求助網路上的Solidworks大神幫你寫Macro？你只要安裝swapi-pilot MCP，想要什麼Macro自已作，再也不用求人了！

## 示範影片

### 影片 1：批次轉檔 — SLDPRT 轉 .XT 格式
[![Watch the Video | SolidWorks AI Automation Demo](https://img.youtube.com/vi/Nc2ZtKBUyDE/maxresdefault.jpg)](https://youtu.be/Nc2ZtKBUyDE)
> 示範情境：資料夾內有多個 SolidWorks 零件檔（.SLDPRT），需要批次轉成 Parasolid（.XT）格式供其他 CAD 系統使用。

只需一句指令，Claude Code 搭配 swapi-pilot MCP 自動查詢正確的 SolidWorks API、產生 C# 自動化腳本、執行後完成批次轉檔。**全程不需要手動查文件、不需要寫程式。**

**關鍵字**：SolidWorks 批次轉檔、SLDPRT to XT、Parasolid 匯出、SolidWorks 自動化、AI 輔助 SolidWorks、Claude Code MCP

---

### 影片 2：智慧操作 FeatureManager — 拉桿移到 Parting Line 上方
[![Watch the Video | SolidWorks AI Automation Demo](https://img.youtube.com/vi/qIYzhO-rA10/maxresdefault.jpg)](https://youtu.be/qIYzhO-rA10)
> 示範情境：正在編輯 SolidWorks 模具零件，需要把 FeatureManager 歷程拉桿（Rollback Bar）移到第一個 Parting Line 特徵的正上方，以便修改之前的特徵。

一句指令，Claude Code 搭配 swapi-pilot MCP 即時搜尋 API、辨識出正確的方法與參數，自動執行完成——**完全不需要手動拖曳，也不需要翻閱 SolidWorks API 文件。**

**關鍵字**：SolidWorks FeatureManager、Rollback Bar 自動化、Parting Line 特徵、模具設計自動化、SolidWorks API Claude、AI 輔助工程設計

---

### 影片 3：免費 LLM 也能做到 — Kimi 2.5 搭配 swapi-pilot
[![Watch the Video | SolidWorks AI Automation Demo](https://img.youtube.com/vi/FiM7A_966BU/maxresdefault.jpg)](https://youtu.be/FiM7A_966BU)
> 示範情境：同樣是將 FeatureManager 歷程拉桿移到第一個（最早出現的）Parting Line 特徵上方，這次改用免費的 Kimi 2.5 來執行。

沒有 swapi-pilot，這類任務對任何 LLM 來說都極度困難——SolidWorks API 文件龐大，光靠 LLM 的訓練資料幾乎不可能找到正確的方法與參數。**swapi-pilot 補上了這個缺口**：它在呼叫 API 時即時提供精確的文件上下文，讓免費的 LLM 也能完成原本做不到的任務。

**swapi-pilot 不綁定任何 AI 平台。** 只要支援 MCP 的工具，都能用。

**關鍵字**：Kimi 2.5、免費 LLM SolidWorks、MCP 通用、SolidWorks API 自動化、AI 輔助 CAD、swapi-pilot MCP

---

## 安裝說明

Claude Code：

```bash
claude mcp add swapi-pilot --transport http https://swapi-pilot.com/mcp
```
#### or 在 C:\Users\ "user"\ .claude.json 新增
```json
  "mcpServers": {
    "swapi-pilot": {
      "type": "http",
      "url": "https://swapi-pilot.com/mcp"
    }
  }
```
Codex CLI：
##### 在\.codex\config.toml 新增
```bash
[mcp_servers.swapi-pilot]
url = "https://swapi-pilot.com/mcp"
```
Opencode：
##### 在\.config\opencode\opencode.json新增
```json
{
  "$schema": "https://opencode.ai/config.json",
  "mcp": {
    "swapi-pilot": {
      "type": "remote",
      "url": "https://swapi-pilot.com/mcp",
      "enabled": true
    }
  }
}
```
## 第一次使用強烈建議：放入 AI 工作範本

安裝完 MCP 後，建議將以下檔案放到你的**工作資料夾根目錄**，讓 AI 知道如何正確使用 swapi-pilot：

| 檔案 | 適用工具 |
|------|---------|
| `CLAUDE.md` | Claude Code |
| `AGENTS.md` | Codex CLI、Opencode |

放入後，AI 會自動讀取範本，在撰寫 SolidWorks 程式前先查詢 API 文件，大幅減少錯誤。

> 兩個檔案內容相同，依你使用的工具放入對應檔案即可。這份檔案只是**參考範本**，你可以依照自己的需求修改內容。就算不放，swapi-pilot MCP 一樣能正常運作——只是 AI 每次都需要你手動提醒它查詢 API 文件的步驟。

## 使用自動執行C#(generate_project)前置需求(非必備想自動執行再安裝)

使用 `generate_project` 工具產生並執行 C# 專案，需要先安裝 **.NET SDK 8.0**：

- 下載：https://dotnet.microsoft.com/download/dotnet/8.0

安裝後即可直接使用 `dotnet run`。

## 可用工具

| Tool | 說明 |
|------|------|
| `search_solidworks_api` | 用關鍵字、介面名稱或方法名稱搜尋 API |
| `get_api_detail` | 取得特定 API 的完整資訊（語法、說明、範例） |
| `list_interface_members` | 列出某介面的所有成員 |
| `get_example_code` | 搜尋並取得範例程式碼 |
| `get_enum` | 查詢列舉/常數值 |
| `generate_project` | 產生 C# console 專案範本 |


