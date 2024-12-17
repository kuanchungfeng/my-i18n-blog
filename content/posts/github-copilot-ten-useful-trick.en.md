---
title: "10 Useful GitHub Copilot Tricks"
date: 2024-12-14T11:43:39+08:00
draft: false
categories:
  - "GitHubCopilot"
tags:
  - "Productivity"
  - "GitHubCopilot"
authors: [Arthur]
toc: true
---

Engineers often have endless tasks, so development efficiency is a major goal. GitHub Copilot, as an AI development tool, can do many things, including code generation and explanation, fixing specific errors, optimizing code, writing tests and documentation, and more.

This article will share 10 very useful GitHub Copilot tricks to help you maximize the use of GitHub Copilot, quickly complete projects, and enhance the development experience.

{{< admonition type=note title="VSCode Version" open=false >}}
The operations in this article use VSCode version: **1.95.3**
{{< /admonition >}}

## One-click commit message generation

Every time you commit, you need to think about what to write for the commit message. Although thinking and typing only takes about 1 minute, if you can enter the commit message with one click, it can save a lot of time in the long run.

{{< vimeo 1039221086 >}}

## Fix using Copilot

During coding, you may encounter red lines in VSCode from time to time. At this time, just move the mouse to the red line, and use Fix using Copilot, and Copilot will help you fix the code you wrote incorrectly.

{{< vimeo 1039223764 >}}

## Optimize or review code

In addition to developing their own code, engineers often need to review colleagues' code. Sometimes you may encounter a method that works but feels not very concise or has bad code smells. At this time, you can consider using Copilot to optimize this code. The steps are as follows:

- Select the code snippet you want to optimize
- Use **cmd+i** (Windows: Ctrl+i) to open the Ask Copilot input box
- Enter **Help me optimize the following code**
- **_Check if the optimized code is better_**

{{< vimeo 1039222557 >}}

### Review and Comment

Although the above method has few steps, you have to enter the optimization command yourself each time, which is not very intuitive.

To solve this problem, VSCode integrates this function into the right-click menu.

{{< vimeo 1039230973 >}}

> [!Warning]
> The answers obtained by the two methods may be different. It is recommended to **use both mixed**, to get different optimization suggestions.

## Ask VSCode related questions

During development, you may encounter some VSCode environment-related issues. When you encounter them, you always need to search online, which takes some time. At this time, you can use **@vscode** in the Chat to ask VSCode questions. For example:

- Ask what the shortcut key for **copying this line to the next line** in VSCode is:

{{< vimeo 1039240404 >}}

- Change the font size

{{< vimeo 1039243095 >}}

From the above videos, we can easily find the place to set the font and then modify the settings ourselves. But is it possible to directly change the font through Chat?

### Commander

To make setting changes simpler and faster, VSCode released an extension in the 2024-10 version: [Commander](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-commander)

![vscode-commander](/images/github-copilot/vscode-commander.png)

After installation, you can directly adjust the VSCode environment through Chat's @commander.

{{< vimeo 1039320346 >}}

### Is @commander better?

From the use case of changing the font, using @commander seems more convenient and faster. So, is @vscode no longer needed?

Let's go back to the question of asking for shortcut keys:

![vscode-vs-commander](/images/github-copilot/vscode-vs-commander.png)

You will find that the answers are different. Here, because I have customized the shortcut key for Copy line down, it seems that **@vscode** is more accurate in answering some customized settings questions.

### @vscode vs @commander

|            |            @vscode             |         @commander          |
| :--------: | :----------------------------: | :-------------------------: |
|  Usage Scenario  | Need to ask questions about customized settings | Want to quickly change settings through Chat  |
|    Built-in    |  Built into VSCode, no additional installation required   | Requires installation of the extension to use |
| Ease of Operation |     Need to manually find and modify settings     | Can complete modifications directly in Chat  |
|  Support Range  |   Extensive, covering all VSCode features   | Mainly for setting adjustments and environment configuration  |

## Treasure hunt during development

Sometimes you know a feature exists but don't know its implementation location. This could be a feature developed by a colleague or something you wrote a long time ago and have forgotten the exact location.

Previously, you could only search through files in the project one by one or try to search for keywords. Now you can quickly find related code through **@workspace** in the chat.

### Ask about the implementation location and details of a feature

Here, we use a Todo list project as an example. In its [README](https://github.com/kuanchungfeng/todo-list-app/blob/master/README.md), you can see the introduction of the sort feature.

![todo-list-demo](/images/github-copilot/todo-list-demo.png)

Suppose I want to know more about how sort is implemented and which fields are currently supported for sorting. At this time, I can directly ask Copilot.

{{< vimeo 1039387860 >}}

### Ask high-level questions about the project

Sometimes you may want to understand the structure of the project or some broader questions. For example, if you are new to the project and don't know how to start it, you can ask **@workspace** to quickly get guidance on starting the project, as shown below:

![how-to-start-project](/images/github-copilot/how-to-start-project.png)

For more uses of @workspace, you can refer to this article: [Making Copilot Chat an expert in your workspace](https://code.visualstudio.com/docs/copilot/workspace-context)

## Quickly find the cause of terminal errors

Engineers often see various errors in the terminal. At this time, you may copy the error message to a website or ChatGPT. Actually, you can directly find the cause through **#terminalSelection**.

{{< vimeo 1039391427 >}}

## Use VSCode to search for information online

Because GitHub Copilot does not search for information online by default, if you want to search for information online, you can do so through @github in the chat.

### Search for the corresponding Tailwind class for CSS online

In a project with Tailwind, sometimes you know the usage of a certain CSS but are not familiar with the corresponding Tailwind class. At this time, you can do this:

{{< vimeo 1039399674 >}}

### Limitations of @github

Although the online search function of @github is powerful, there are some limitations in its use:

- Cannot query unrelated content
  ![copilot-not-support-non-programming-related](/images/github-copilot/copilot-not-support-non-programming-related.png)
- Cannot ask questions based on both @workspace and online data (@github) at the same time
  ![use-workspace-and-github](/images/github-copilot/use-workspace-and-github.png)

### Web Search for Copilot

To solve the above problems, VSCode released an extension in the 2024-10 version: [Web Search for Copilot](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-websearchforcopilot)

![vscode web search](/images/github-copilot/vscode-web-search.png)

> [!IMPORTANT]
> To use the Web Search extension, you need to set up an API key. Currently, it supports integrating with search engine APIs from [Tavily](https://tavily.com/) and [Bing](https://www.bing.com/). For details, please refer to [here](https://code.visualstudio.com/updates/v1_95#_web-search-for-copilot).

After setting it up, try the previously unmet needs:

#### Query unrelated content

{{< vimeo 1039420447 >}}

#### Use @workspace and online search simultaneously

{{< vimeo 1039421538 >}}

### @github vs @websearch

|                       |           @github           |           @websearch           |
| :-------------------: | :-------------------------: | :----------------------------: |
|       Usage Scenario        |   Need to search for programming-related information    |     Can search for unrelated content     |
|         Built-in          | Built into VSCode, no additional installation required |  Requires installation of the extension to use   |
|         Cost          |            Free             | Requires setting up an API key, which may incur costs |
| Use with @workspace simultaneously |           Not supported            |              Supported              |
|       Search Speed        |            Fast             |  Depends on the search engine and API used  |

## Use AI to generate visual documentation

Clear and understandable documentation is key. A picture often conveys all the information intuitively, better than a thousand words.

### Mermaid

Mermaid is a powerful chart generation tool that can generate flowcharts, sequence diagrams, Gantt charts, etc. Using Mermaid, you can easily add various visual charts to your documentation, making it more vivid and easy to understand.

### Install vscode-mermAId

To use Mermaid in VSCode, you need to install the extension: [vscode-mermAId](https://marketplace.visualstudio.com/items?itemName=ms-vscode.copilot-mermaid-diagram)

![vscode-mermAId](/images/github-copilot/vscode-mermAId.png)

### Generate component relationship diagrams

Usually, a module contains multiple components. At this time, you can use Mermaid to generate sequence diagrams of related components.

{{< vimeo 1039705296 >}}

### Explain methods with flowcharts

{{< vimeo 1039708945 >}}

{{< admonition type=info title="Info " open=true >}}
For more types of diagrams, refer to the [Mermaid official documentation](https://mermaid.js.org/syntax/flowchart.html).
{{< /admonition >}}

## Interact with AI using images and generate corresponding code

Engineers often need to produce corresponding code based on design drafts. At this time, if you can generate the corresponding HTML and CSS by giving the AI a screenshot of the design draft, it will be very helpful.

### Vision for Copilot Preview

To make Copilot understand images, you need to install this extension: [Vision for Copilot Preview](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-copilot-vision)

> [!IMPORTANT]
> To use the Vision for Copilot Preview extension, you need to set up the corresponding AI. Currently, it supports integrating with OpenAI, Azure OpenAI, Anthropic, or Gemini. For details, please refer to the [extension description](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-copilot-vision#overview).

### Use screenshots to generate HTML and CSS

Here, we use the Progress design that appears in Thread as an example.

![progress-bar-demo](/images/github-copilot/progress-bar.png)

First, copy the photo to the clipboard, and then use @vision to ask it to generate HTML and CSS based on the image.

{{< vimeo 1040091027 >}}

> [!Warning]
> From the video, you can see that it can currently only complete a rough HTML, but you can further adjust based on this HTML structure, saving time in designing the complete DOM structure.

## Add instructions before each Chat

After using ChatGPT for a while, you will find that to make instructions more precise, you can add preset instructions before each conversation to let ChatGPT play a specific role or perform specific operations before answering.

### How to set preset instructions in GitHub Copilot

1. First, go to settings and search for `Use Instruction Files`, and check the option.
   ![use-instruction-files](/images/github-copilot/use-instruction-files.png)
2. Create a .github directory and add a file named `copilot-instruction.md`.
   ![create-copilot-instruction](/images/github-copilot/create-copilot-instruction.png)

> [!Warning]
> If it is a company project, remember to add this file to .gitignore.

3. Set preset instructions according to your needs.
4. Go back to Chat and continue chatting with Copilot.

### Input in Chinese but ask Copilot to translate into English for queries

People who use generative AI often say that asking questions in English is usually more precise.

#### Translate before querying

![add-instruction](/images/github-copilot/add-instruction.png)

Chat with Copilot in Chinese.

{{< vimeo 1040111056 >}}

For more information about instructions, refer to [this article](https://docs.github.com/en/copilot/customizing-copilot/adding-custom-instructions-for-github-copilot).

## Summary

This article introduced 10 Copilot usage tips. Let's quickly review:

1. One-click commit message generation
2. Quickly fix VSCode errors
3. Efficiently optimize code
4. Ask VSCode related questions
5. Find project features
6. Quickly find the cause of terminal errors
7. Use VSCode to search for information online
8. Generate visual documentation
9. Interact with AI using images and generate corresponding code
10. Add instructions before each Chat

I hope these tips help you get the most out of GitHub Copilot, making your development smoother and more efficient.

