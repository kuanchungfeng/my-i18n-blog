---
title: "10個實用的Github Copilot用法"
date: 2024-12-14T11:43:39+08:00
draft: false
categories:
  - "GithubCopilot"
tags:
  - "Productivity"
  - "GithubCopilot"
authors: [Arthur]
toc: true
---

工程師的日常總是有永無止境的 task，因此開發效率是工程師的一大追求目標。Github Copilot 做為一個開發 AI 工具，能做的事很多，包含程式碼的生成與解釋、修正具體的錯誤、優化程式碼、撰寫測試和文件等等。

本篇將分享 10 個很實用的 Github Copilot 用法，幫助你最大化利用 Github Copilot，快速的完成專案和提升開發體驗。

{{< admonition type=note title="vscode版本" open=false >}}
本篇操作的畫面是使用 vscode 版本：**1.95.3**
{{< /admonition >}}

## 一鍵產生 commit message

每次 commit 的時候，總是需要稍微思考一下 commit message 要寫什麼。雖然思考加上輸入大約只要 1 分左右，但如果可以一鍵就輸入完 commit message，長遠下來可以省下很多時間。

{{< vimeo 1039221086 >}}

## Fix using copilot

寫 code 的過程中，不定時會遇到 vscode 出現紅線，這時候只要將滑鼠移到紅線上，透過 Fix using copilot，copilot 就會幫你修正你寫錯的 code。

{{< vimeo 1039223764 >}}

## Optimize or review Code

工程師除了自己開發外，也經常需要 review 同事的 code，有時候會遇到某個方法雖然可以運行，卻覺得實作起來不太簡潔或是有 bad code 的味道，這時候可以考慮用 copilot 優化這段 code。步驟如下：

- 選取想要優化的程式片段
- 利用**cmd+i**(Windows：Ctrl+i)打開 Ask Copilot 輸入框
- 輸入**Help me optimize the following code**
- **_檢查優化的程式是否有比較好_**

{{< vimeo 1039222557 >}}

### Review and Comment

上面這個方法雖然步驟不多，但每次都要自己輸入優化指令，其實也蠻不直覺的。

為了解決這個問題，Vscode 把這功能整合在右鍵裡面。

{{< vimeo 1039230973 >}}

> [!Warning]
> 兩種用法可能得到的答案會不太一樣，建議**兩種混著使用**，可以得到不同的優化建議

## 詢問 Vscode 相關問題

開發中有時會遇到一些 Vscode 環境相關問題，遇到時總是要上網查耗費一些時間，這時候可以透過在 Chat 中使用 **@vscode** 來詢問 Vscode 問題。例如：

- 詢問 Vscode **複製這行到下一行**的快捷鍵是什麼：

{{< vimeo 1039240404 >}}

- 更改字體大小

{{< vimeo 1039243095 >}}

從上面的影片我們可以輕鬆找到設定字體的地方，然後再自己修改設定，但有沒有可能直接透過 Chat 幫我們更改字體呢？

### Commander

為了讓更改設定更簡單快速，Vscode 在 2024-10 的版本出了一個 Extension:[Commander](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-commander)

![vscode-commander](/images/github-copilot/vscode-commander.png)

安裝好以後，透過 Chat 的 @commander 直接調整 Vscode 環境

{{< vimeo 1039320346 >}}

### @commander 比較好用？

從更改字體的 Use case 來看，使用 @commander 看起來更方便快速，那@vscode 就不需要使用了嗎？

讓我們再回到詢問快捷鍵的問題：

![vscode-vs-commander](/images/github-copilot/vscode-vs-commander.png)

會發現兩者的答案不一樣，這邊因為我有自訂過 Copy line down 的快捷鍵，所以看起來 **@vscode** 在一些客製化調整的問題，回答的比較準。

### @vscode vs @commander

|            |            @vscode             |         @commander          |
| :--------: | :----------------------------: | :-------------------------: |
|  使用情境  | 需要問一些已經客製化的設定問題 | 想要直接透過 Chat 快速更改  |
|    內建    |  內建於 Vscode，無需額外安裝   | 需要安裝 Extension 才能使用 |
| 操作便捷性 |     需要手動查找設定並修改     | 可以直接在 Chat 中完成修改  |
|  支援範圍  |   廣泛，涵蓋所有 Vscode 功能   | 主要針對設定調整和環境配置  |

## 開發中的尋寶之旅

有時候你知道某個功能存在，但不知道它的實作位置。這可能是同事開發的功能，也可能是你很久以前寫的，已經忘記了具體位置。

以前只能在專案中逐個檔案搜尋，或者嘗試搜尋關鍵字，現在可以透過 chat 中的 **@workspace** 快速找到相關程式碼。

### 詢問某個功能的實作位置及細節

這邊使用一個 Todo list 專案來示範，在其 [README](https://github.com/kuanchungfeng/todo-list-app/blob/master/README.md) 中可以看到有 sort 功能的介紹。

![todo-list-demo](/images/github-copilot/todo-list-demo.png)

假設我想要更了解 sort 怎麼實作，以及目前有支援哪些欄位排序，這時候我就可以直接問 Copilot

{{< vimeo 1039387860 >}}

### 詢問專案的高層級問題

有時候你可能會想了解專案的結構或一些更大範圍的問題。例如，假設你是第一次接觸這個專案，不知道如何啟動它，這時可以透過 **@workspace** 詢問，快速獲得啟動專案的指引，如下圖所示：

![how-to-start-project](/images/github-copilot/how-to-start-project.png)

更多@workspace 的用法，可以參考這篇：[Making Copilot Chat an expert in your workspace](https://code.visualstudio.com/docs/copilot/workspace-context)

## 快速找到 terminal 錯誤的原因

工程師常常會在 terminal 看到各種錯誤，這時候你可能會把錯誤訊息複製到網站或給 ChatGPT，這時候其實可以直接透過 **#terminalSelection** 來找出原因

{{< vimeo 1039391427 >}}

## 利用 vscode 上網找資料

因為 Github Copilot 預設不會直接去上網搜尋資料，如果想要上網查資料，可以透過在 chat 使用 @github 達成。

### 上網找 css 對應的 tailwind class

在有導入 tailwind 的專案中，有時候你知道某個 css 的用法，但你不熟 tailwind 對應的 class，這時候你可以這樣做：

{{< vimeo 1039399674 >}}

### @github 的限制

@github 的能上網功能雖然強大，但使用上也有一些限制：

- 無法查詢跟無關的內容
  ![copilot-not-support-non-programming-related](/images/github-copilot/copilot-not-support-non-programming-related.png)
- 無法同時根據 @workspace 和上網的資料(@github)問問題
  ![use-workspace-and-github](/images/github-copilot/use-workspace-and-github.png)

### Web Search for Copilot

為了可以解決上述問題，Vscode 在 2024-10 的版本出了一個 Extension:[Web Search for Copilot](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-websearchforcopilot)

![vscode web search](/images/github-copilot/vscode-web-search.png)

> [!IMPORTANT]
> 使用 Web search 這個 Extension，需要設定 API key 才能運行，目前支援介接[Tavily](https://tavily.com/)和[Bing](https://www.bing.com/)的搜尋引擎 API，詳細請參考[這邊](https://code.visualstudio.com/updates/v1_95#_web-search-for-copilot)

設定好之後，試試看剛剛的做不到的需求：

#### 查詢與程式無關的內容

{{< vimeo 1039420447 >}}

#### 同時使用@workspace 和上網查詢

{{< vimeo 1039421538 >}}

### @github vs @websearch

|                       |           @github           |           @websearch           |
| :-------------------: | :-------------------------: | :----------------------------: |
|       使用情境        |   需要查詢程式相關的資料    |     可以查詢程式無關的內容     |
|         內建          | 內建於 Vscode，無需額外安裝 |  需要安裝 Extension 才能使用   |
|         費用          |            免費             | 需要設定 API key，可能產生費用 |
| 與@workspace 同時使用 |           不支援            |              支援              |
|       查詢速度        |            快速             |  取決於所使用的搜尋引擎和 API  |

## 利用 AI 產出視覺化文件

清楚易懂是寫文件的關鍵。一張圖往往能直觀地傳達所有信息，勝過千言萬語。

### Mermaid

Mermaid 是一個強大圖表生成工具，可以生成流程圖、序列圖、甘特圖等。使用 Mermaid，可以輕鬆地在你的文件中添加各種視覺化圖表，讓你的文件更加生動和易於理解。

### 安裝 vscode-mermAId

要在 vscode 上使用 Mermaid，要先安裝 Extension:[vscode-mermAId](https://marketplace.visualstudio.com/items?itemName=ms-vscode.copilot-mermaid-diagram)

![vscode-mermAId](/images/github-copilot/vscode-mermAId.png)

### 產生元件關係圖

通常一個 module 裡面會有多個元件，這時候可以透過 mermaid 產出相關元件的序列圖

{{< vimeo 1039705296 >}}

### 用流程圖解釋方法

{{< vimeo 1039708945 >}}

{{< admonition type=info title="Info " open=true >}}
更多圖的類型可參考[Mermaid 官方文檔](https://mermaid.js.org/syntax/flowchart.html)。
{{< /admonition >}}

## 利用圖片與 AI 互動並產出對應的程式碼

工程師常常需要依照設計稿產出對應的程式，這時候如果可以透過將設計稿的截圖給 AI，請他幫你產出對應的 html 和 CSS

### Vision for Copilot Preview

要讓 Copilot 看得懂圖，首先要安裝這個 Extension:[Vision for Copilot Preview]
(https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-copilot-vision)

> [!IMPORTANT]
> 使用 Vision for Copilot Preview 這個 Extension，需要設定對應的 AI 才能運行，目前支援介接 OpenAI、Azure OpenAI、Anthropic 或 Gemini，詳細請參考[Extension 說明](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-copilot-vision#overview)

### 使用截圖來產出 html 和 css

這邊用 Thread 出現的 Progress design 來嘗試

![progress-bar-demo](/images/github-copilot/progress-bar.png)

首先先將照片複製到解貼版，然後再使用 @vision 請他依照圖片產出 html 和 CSS

{{< vimeo 1040091027 >}}

> [!Warning]
> 從影片中可以看出，目前只能完成一個大致的 HTML，但可以根據這個 HTML 結構進一步調整，從而節省設計完整 DOM 結構的時間。

## 在每次 Chat 之前加入指令

使用 ChatGPT 一段時間後，你會發現，為了讓指令更加精確，可以在每次對話開始時，透過預設指令讓 ChatGPT 扮演特定角色，或在回答前先執行特定操作。

### 如何在 github copilot 設定預設指令

1. 先到設定搜尋`Use Instruction Files`，將該選項打勾
   ![use-instruction-files](/images/github-copilot/use-instruction-files.png)
2. 建立一個.github 目錄，並新增一個檔案取名為`copilot-instruction.md`
   ![create-copilot-instruction](/images/github-copilot/create-copilot-instruction.png)

> [!Warning]
> 如果是公司的專案，記得把這個檔案加進.gitignore

3. 依照自己的需求設定預設指令
4. 回到 Chat 繼續跟 Copilot 聊天

### 用中文輸入，但請 Copilot 翻譯成英文查詢

使用生成式 AI 的人常說，使用英文提問通常會更精確。

#### 在聊天之前先做翻譯的動作在做查詢

![add-instruction](/images/github-copilot/add-instruction.png)

用中文跟 Copilot 對話

{{< vimeo 1040111056 >}}

更多關於 instructions 相關的介紹，可參考[這篇](https://docs.github.com/en/copilot/customizing-copilot/adding-custom-instructions-for-github-copilot)

## 總結

這篇介紹了 10 個 Copilot 使用技巧，讓我們快速回顧一下:

1. 一鍵生成 commit message
2. 快速修正 vscode 錯誤
3. 高效優化程式碼
4. 詢問 Vscode 相關問題
5. 尋找專案功能
6. 快速找到 terminal 錯誤原因
7. 利用 vscode 上網找資料
8. 生成視覺化文件
9. 透過圖片與 AI 互動生成程式碼
10. 在每次 Chat 之前加入指令

希望這些技巧能幫助你更高效地運用 GitHub Copilot，進一步提升開發體驗與工作效率。
