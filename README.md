# 研究所備審資料生成 Skill

一個供 Codex 使用的繁體中文 Skill，協助申請人依真實背景撰寫與修改研究所備審資料，包括自傳、求學動機、讀書計畫、工作經歷、論文及專題成果。

## 功能特色

- 以繁體中文及申請人第一人稱撰寫。
- 依學校、系所、教授研究方向及字數限制調整內容。
- 區分已有經驗、正在學習及未來規劃，避免誇大或虛構經歷。
- 可撰寫整合版本，也可分別製作自傳、求學動機與讀書計畫。
- 預設可要求 Codex 製作正式的 `.docx` 文件，並進行版面檢查。
- 在資料允許時，查核系所、課程及教授研究資訊。

## 使用平台

主要適用於支援 Agent Skills 的 Codex 環境：

- Codex 桌面版
- Codex CLI
- Windows、macOS 與 Linux

此 Skill 採標準 `SKILL.md` 結構。其他支援 Agent Skills 規格的代理工具也可能使用，但安裝位置與觸發方式請以該工具的文件為準。

## 安裝方法

### 方法一：使用 Git 下載（建議）

將整個倉庫複製到使用者層級的 Codex Skills 目錄。

#### Windows PowerShell

```powershell
New-Item -ItemType Directory -Force "$env:USERPROFILE\.codex\skills" | Out-Null
git clone https://github.com/Linziyan2024/graduate-application-writer.git "$env:USERPROFILE\.codex\skills\graduate-application-writer"
```

#### macOS／Linux

```bash
mkdir -p ~/.codex/skills
git clone https://github.com/Linziyan2024/graduate-application-writer.git ~/.codex/skills/graduate-application-writer
```

安裝後請開啟新的 Codex 對話；若 Codex 已在執行但未顯示此 Skill，請重新啟動 Codex。

### 方法二：下載 ZIP

1. 在本倉庫頁面按下 **Code → Download ZIP**。
2. 解壓縮檔案。
3. 將資料夾重新命名為 `graduate-application-writer`。
4. 把完整資料夾放到下列位置：
   - Windows：`%USERPROFILE%\.codex\skills\graduate-application-writer`
   - macOS／Linux：`~/.codex/skills/graduate-application-writer`
5. 確認資料夾內直接包含 `SKILL.md`，不要多包一層同名資料夾。

### 專案限定安裝

若只希望某個專案使用此 Skill，可將資料夾放在專案內：

```text
<專案根目錄>/.codex/skills/graduate-application-writer/
```

## 資料夾結構

```text
graduate-application-writer/
├── SKILL.md
├── README.md
└── agents/
    └── openai.yaml
```

## 使用方法

在 Codex 對話中直接指定 Skill：

```text
使用 $graduate-application-writer 協助我撰寫研究所備審資料。
```

也可以直接描述需求；當需求符合 Skill 的用途時，Codex 可自動選用它。例如：

```text
請根據我的學經歷，撰寫臺灣某大學資訊管理研究所的求學動機與兩年讀書計畫。
```

第一次使用時，Skill 會先確認字數、頁數及學校格式要求，再蒐集撰寫所需資料。為了提高成品品質，建議事先準備：

- 申請學校、系所、組別及入學年度
- 文件種類與字數或頁數限制
- 學歷、工作經歷及實際技能
- 論文、專題或研究計畫資料
- 求學動機與職涯方向
- 感興趣的教授、研究領域或官方網頁
- 學校提供的備審格式或題目

你也可以直接貼上現有履歷、自傳或草稿，Codex 會先閱讀已有資訊，只追問會影響事實或主軸的缺漏。

## 使用範例

### 撰寫整份備審

```text
使用 $graduate-application-writer 幫我撰寫一份 2,500 字的整合版備審資料，包含自傳、求學動機與兩年讀書計畫。請先向我蒐集必要資料。
```

### 修改既有草稿

```text
使用 $graduate-application-writer 修改下面的求學動機。保留我的真實經歷與語氣，控制在 800 字內，不要虛構成果。
```

### 產出 Word 文件

```text
使用 $graduate-application-writer 根據我提供的資料完成備審，並製作可直接提交的 Word 文件。請遵守學校格式並檢查頁面是否跑版。
```

## 注意事項

- 請只提供真實且可確認的學經歷、論文、專題成果與技能程度。
- 涉及個人資料時，請避免在公開對話、公開倉庫或不受信任的服務中提供身分證號、住址等敏感資訊。
- 若需要查核教授或課程資訊，請提供正確的學校、系所與申請年度。
- 產出內容仍應由申請人本人核對事實、校名、系所名稱、教授姓名與招生規定。

## 更新

使用 Git 安裝者可執行：

```bash
git -C ~/.codex/skills/graduate-application-writer pull
```

Windows PowerShell：

```powershell
git -C "$env:USERPROFILE\.codex\skills\graduate-application-writer" pull
```

## 參考資料

- [OpenAI：Skills 概念](https://developers.openai.com/plugins/concepts/skills)
- [OpenAI：測試 Agent Skills](https://developers.openai.com/blog/eval-skills)

## 授權

本倉庫目前未附開放原始碼授權條款。你可以下載並在自己的 Codex 環境中使用；若要修改後重新散布或整合至其他專案，請先取得作者同意。
