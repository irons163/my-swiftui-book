# SwiftUI 中文書專案

這個目錄現在不只是一本書的寫作骨架，而是已經長成一套完整的書稿工作區。主題是一本以「習慣養成 App」為主線的 SwiftUI 中文實戰書，重點不只放在畫面怎麼做出來，也放在狀態、資料流、架構、測試與產品整合怎麼一起長成同一個 App。

## 目前狀態

- `book/chapters/01` 到 `14` 都已經整理成正式初稿。
- `book/appendices/` 已補上 Swift、Xcode 與速查型附錄骨架。
- `book/figures/` 已補上各章對應的 Mermaid 圖解草稿。
- `docs/` 已整理出 GitBook 發布用結構，並可搭配 `.gitbook.yaml` 直接做 GitHub Sync。
- `BOOK_BLUEPRINT.md`、`WRITING_GUIDE.md`、前言、目錄頁、書封文案、封底文案與出版社提案摘要已和正文方向對齊。
- 目前最適合往下做的工作，會是作者語氣再個人化、試讀者回饋輪，以及對外提案版型整理。

## 這個專案想完成什麼

這本書想解決的不是「讀者會不會幾個 SwiftUI 元件」，而是另一個更核心的問題：

`讀完之後，讀者能不能用現代 SwiftUI 思維做出一個可維護、可測、可繼續長大的中型 App。`

因此，全書刻意用一個主線專案貫穿，讓每一章都不只是教局部技巧，而是回到同一個產品脈絡裡回答：

- 這個觀念是為了解決什麼問題？
- 它在真實 App 中會落在哪裡？
- 初學者最容易在哪裡寫出能跑、卻不穩的版本？

## 核心文件

- `BOOK_BLUEPRINT.md`
  整本書的定位、目標讀者、章節藍圖與差異化設計。

- `WRITING_GUIDE.md`
  全書語氣、章節骨架、術語統一與交稿前檢查規則。

- `GITHUB_UPLOAD_CHECKLIST.md`
  從 `git init`、第一個 commit 到第一次 `git push` 的完整操作清單，適合把這個專案正式推上 GitHub。

- `book/frontmatter/preface.md`
  前言草稿，目前已收成接近正式出版語氣，可再按作者個人背景微調。

- `book/frontmatter/table-of-contents.md`
  出版提案版本的目錄頁，已按 Part 與章節定位整理完成。

- `book/frontmatter/cover-copy.md`
  書封主標、副標、短文案與封面設計方向。

- `book/frontmatter/back-cover-copy.md`
  封底長短版文案、適讀對象、能力承諾與通路簡介版。

- `book/frontmatter/publisher-proposal-summary.md`
  1 到 2 頁版本的出版社提案摘要，可直接用來說明市場缺口、讀者定位、差異化與目前完成度。

- `book/chapters/`
  全書 14 章正文初稿。

- `book/appendices/`
  用來接住還不夠熟悉 Swift 與 Xcode 的讀者，採「補票上車」定位，不打斷正文主線。

- `book/figures/`
  對應各章的圖解草稿、圖說與建議放置位置。

- `docs/`
  提供 GitBook 發布用的乾淨內容根目錄，只保留前言、正文章節與附錄，不把提案文案與工作檔一起公開。
  另外也補上 `docsify` 本機預覽所需的 `index.html` 與 `_sidebar.md`，可先在本機看近似文件站效果。

- `templates/chapter-template.md`
  後續若要新增附錄、番外章或延伸章節，可沿用的模板。

## 章節結構

全書目前分成四個部分：

1. 建立 SwiftUI 思維
   第 01 到 03 章

2. 做出可操作的介面
   第 04 到 07 章

3. 讓 App 開始有生命
   第 08 到 12 章

4. 從作品走向產品
   第 13 到 14 章

這樣的安排，是為了讓讀者先理解 SwiftUI 的思維與版面，再往狀態、互動、資料生命週期與專案結構一路推進，最後回到產品整合、版本演進與下一步。

## 專案結構

```text
my-swiftui-book/
├── README.md
├── .gitbook.yaml
├── BOOK_BLUEPRINT.md
├── WRITING_GUIDE.md
├── templates/
│   └── chapter-template.md
└── book/
    ├── frontmatter/
    │   ├── preface.md
    │   ├── table-of-contents.md
    │   ├── cover-copy.md
    │   ├── back-cover-copy.md
    │   └── publisher-proposal-summary.md
    ├── chapters/
    │   ├── 01-declarative-thinking.md
    │   ├── 02-layout-and-composition.md
    │   ├── 03-state-and-data-flow.md
    │   ├── 04-navigation-and-lists.md
    │   ├── 05-forms-and-input.md
    │   ├── 06-reusable-components.md
    │   ├── 07-animation-and-gestures.md
    │   ├── 08-async-and-networking.md
    │   ├── 09-persistence-and-local-data.md
    │   ├── 10-app-architecture.md
    │   ├── 11-testing-and-previews.md
    │   ├── 12-performance-and-debugging.md
    │   ├── 13-build-a-real-app.md
    │   └── 14-publish-and-grow.md
    ├── appendices/
    │   ├── appendix-a-swift-basics.md
    │   ├── appendix-b-xcode-and-project-basics.md
    │   └── appendix-c-swift-and-swiftui-cheatsheet.md
    └── figures/
        ├── 01-declarative-thinking-figures.md
        ├── 02-layout-and-composition-figures.md
        ├── 03-state-and-data-flow-figures.md
        ├── 04-navigation-and-lists-figures.md
        ├── 05-forms-and-input-figures.md
        ├── 06-reusable-components-figures.md
        ├── 07-animation-and-gestures-figures.md
        ├── 08-async-and-networking-figures.md
        ├── 09-persistence-and-local-data-figures.md
        ├── 10-app-architecture-figures.md
        ├── 11-testing-and-previews-figures.md
        ├── 12-performance-and-debugging-figures.md
        ├── 13-build-a-real-app-figures.md
        └── 14-publish-and-grow-figures.md
└── docs/
    ├── README.md
    ├── 00-preface.md
    ├── chapters/
    └── appendices/
```

## 如果你現在要繼續往下做

最推薦的順序是：

1. 回頭把附錄 A、B、C 再收成和正文一樣成熟的正式書稿語氣。
2. 在前言或第 1 章前補一段「閱讀前準備」，把附錄使用方式說清楚。
3. 找 2 到 3 位試讀者，優先驗證前言、第 01 章、第 03 章、第 13 章與附錄 A。
4. 先用本機文件站或 GitBook Preview 檢查側欄、頁面順序與閱讀流。
5. 依出版社或提案需求，把 frontmatter、appendices 與 Mermaid 圖整理成對外版型。
6. 最後再做一輪全書細修，準備進入正式交稿或提案。

## 一句話定位

這不是一本只教你把 SwiftUI 畫面做出來的書，而是一本帶你用正確思維把 App 做對、做穩，最後做成產品原型的中文實戰書。
