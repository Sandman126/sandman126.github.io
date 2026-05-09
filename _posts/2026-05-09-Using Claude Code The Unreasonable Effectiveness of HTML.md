---
title: "Using Claude Code: The Unreasonable Effectiveness of HTML使用 Claude 代码：HTML 的非合理有效性"
source: https://x.com/trq212/status/2052809885763747935
author:
  - "[[@trq212]]"
published: 2026-05-09
created: 2026-05-09
description: Markdown has become the dominant file format used by agents to communicate with us. It’s simple, portable, has some rich text capability and...
tags:
  - clippings
category:
  - 网络
  - AI
pin: false
math: false
mermaid: false
image: assets/img/bannel.jpg
---
![图像](https://pbs.twimg.com/media/HHz_ftzaIAAwkQs?format=jpg&name=large)


Markdown has become the dominant file format used by agents to communicate with us. It’s simple, portable, has some rich text capability and is easy for you to edit. Claude has even gotten surprisingly good at using ASCII to make diagrams inside of markdown files.Markdown 已成为代理们与我们沟通的主流文件格式。它简单、便携，具备丰富的文本功能，且编辑起来很方便。Claude 甚至在使用 ASCII 在 Markdown 文件中绘制图表方面变得惊人地擅长。

But as agents have become more and more powerful, I have felt that markdown has become a restricting format. I find it difficult to read a markdown file of more than a hundred lines. I want richer visualizations, color and diagrams and I want to be able to share them easily.但随着代理权力的提升，我觉得折扣已经变成了一种限制性的格式。我发现很难读懂超过一百行的 markdown 文件。我想要更丰富的可视化、色彩和图表，并且能够轻松分享。

I'm also increasingly not editing these files myself, but using them as specs, reference files, brainstorming outputs, etc. When I do make edits, I’m usually prompting Claude to edit them, which removes one of markdown’s largest benefits.我也越来越少自己编辑这些文件，而是把它们当作规格、参考文件、头脑风暴输出等使用。当我做编辑时，通常是提示 Claude 去编辑，这削弱了 Markdown 最大的好处之一。

I’ve started preferring HTML as an output format instead of Markdown and increasingly see this being used by others on the Claude Code team, this is why.我开始更喜欢用 HTML 作为输出格式，而不是 Markdown，而且越来越多地看到 Claude Code 团队的其他人也在用它，这就是原因。

(if you want to start with some examples, you can see a bunch here: [https://thariqs.github.io/html-effectiveness](https://thariqs.github.io/html-effectiveness/), just be sure to come back and read more about why)（如果你想先举一些例子，可以在这里看到很多：[https://thariqs.github.io/html-effectiveness](https://thariqs.github.io/html-effectiveness/)，记得回来了解更多原因）

# Why HTML?为什么选择 HTML？

## Information Density信息密度

![图像](https://pbs.twimg.com/media/HHz_q48aAAAaCfW?format=jpg&name=large)

HTML can convey much richer information compared to markdown. It can of course do simple document structure like headers and formatting, but it can also represent all sorts of other information such as:HTML 比 markdown 能传达更丰富的信息。它当然可以做简单的文档结构，比如头部和格式化，但它也可以表示各种其他信息，比如：

- Tabular data using tables使用表格的表格数据
- Design data with CSS用 CSS 设计数据
- Illustrations with SVG使用 SVG 的插图
- Code snippets with script tags带脚本标签的代码片段
- Interactions using HTML elements with javascript + CSS使用 HTML 元素与 JavaScript + CSS 的交互
- Workflows using SVG and HTML使用 SVG 和 HTML 的工作流程
- Spatial data using absolute positions and canvases使用绝对位置和画布的空间数据
- Images using image tags使用图像标签的图片

I would go so far as to say that there is almost no set of information that Claude can read that you cannot fairly efficiently represent with HTML. This makes it a highly efficient way for the model to communicate in-depth information to you and for you to revie wit.我甚至会说，几乎没有 Claude 能读取的信息是你用 HTML 无法高效表现的。这使得模型能够高效地向你传达深入信息，并让你轻松表达机智。

I’ve found that in the absence of being able to do this, the model may do more inefficient things in markdown like ASCII diagrams or, my favorite, estimating colors with unicode characters like in this screenshot from Claude Code.我发现如果不能做到这一点，模型在 markdown 中可能会做一些效率较低的事情，比如 ASCII 图表，或者我最喜欢的用 Unicode 字符估计颜色，就像这张 Claude Code 截图里的那样。

![图像](https://pbs.twimg.com/media/HH0CDc6a8AAy1bv?format=png&name=large)

Claude Code trying to show color in markdownClaude 代码试图在 Markdown 中显示颜色

## Visual Clarity & Ease of Reading视觉清晰度与阅读便利性

![图像](https://pbs.twimg.com/media/HH0AgqJbcAAaEcZ?format=jpg&name=large)

As Claude is able to do more complex work, it is also writing larger and larger specs and plans. In practice, I've found I tend to not actually read more than a 100-line markdown file, and I certainly am not able to get anyone else in my organization to read it.随着 Claude 能够处理更复杂的工作，它也在编写越来越大的规格和设计图。实际上，我发现自己通常不会真正阅读超过 100 行的 markdown 文件，而且我当然也无法让组织里的其他人去读它。

But HTML documents are much easier to read, Claude can organize the structure visually to be ideal to navigate with tabs, illustrations, links, etc. It can even be mobile responsive so you can read it differently based on your form factor.但 HTML 文档更容易阅读，Claude 可以直观地组织结构，方便通过标签、插图、链接等导航。它甚至可以是移动响应式的，所以你可以根据你的机型不同来阅读。

## Ease of Sharing分享便利性

Markdown files are fairly hard to share since most browsers do not render them natively well. You often have to add them as attachments to emails or messages.Markdown 文件比较难分享，因为大多数浏览器原生渲染不好。你通常需要把它们作为附件添加到邮件或消息中。

With HTML, as long as you upload the file (for example to S3), you can share the link easily. Your colleagues can open it wherever they wish and easily reference it.用 HTML 时，只要上传文件（比如上传到 S3），就能轻松分享链接。你的同事们可以随意打开并轻松查阅。

The chance of someone actually reading your spec, report or PR writeup is much much higher if it’s in HTML.如果是 HTML 格式，别人真的会看到你的规格、报告或公关报告，几率会高得多。

## Two-way Interaction双向交互

![图像](https://pbs.twimg.com/media/HH0Ao0tbYAAOF9e?format=jpg&name=large)

HTML can allow you to interact with the document, for example you might want to ask it to add sliders or knobs to adjust a design or allow you to tweak different options in the algorithm to see what happens. You can also ask it to let you copy these changes into a prompt to paste back into Claude Code. Read more about my playgrounds post to see examples of this two way interaction: [https://x.com/trq212/status/2017024445244924382](https://x.com/trq212/status/2017024445244924382)HTML 可以让你与文档互动，比如你可能想让它添加滑块或旋钮来调整设计，或者允许你调整算法中的不同选项，看看会发生什么。你也可以请求它允许你把这些更改复制到提示中，再粘贴回 Claude 代码。 阅读我关于游乐场的帖子，了解这种双向互动的示例：[https://x.com/trq212/status/2017024445244924382](https://x.com/trq212/status/2017024445244924382)

**Data Ingestion数据摄取**

Why use Claude Code to make HTML files instead of ClaudeAI or Claude Design for example? One of the biggest reasons is all the context Claude Code can ingest. For example, when writing this article, I asked Claude Code to read through my code folder and find all the HTML files I’ve generated, group and categorize them and then make an HTML file with all diagrams representing each type. The diagrams you see in this article are a direct result of that.为什么用 Claude 代码来制作 HTML 文件，而不是用 ClaudeAI 或 Claude Design 之类的？其中一个最大原因是 Claude 代码可以吸收大量上下文。 例如，写这篇文章时，我让 Claude Code 翻阅我的代码文件夹，找到我生成的所有 HTML 文件，将它们分组和分类，然后制作一个包含每种类型的图表的 HTML 文件。你在这篇文章中看到的图表就是这个过程的直接结果。

Besides the file system, Claude Code can find additional context using your MCPs (like Slack, Linear, etc.), your web browser (with Claude in Chrome), your git history, etc.除了文件系统，Claude Code 还可以通过你的 MCP（如 Slack、线性线性等）、浏览器（在 Chrome 中使用 Claude）、git 历史记录等来查找额外的上下文。

## It’s Joyful这很快乐

Making HTML documents with Claude is just more fun and makes me feel more involved and invested in the creation, and that by itself is enough.用 Claude 制作 HTML 文档更有趣，也让我对创作更有投入感，这本身就足够了。

## How to Get Started如何开始

I’m a little bit afraid that people will read this article and turn it into a /html skill or something. While there might be some value in that, I want to emphasize that you don’t need to do much to get Claude to do this. You can just ask it to “make a HTML file” or “make a HTML artifact”.我有点担心有人读了这篇文章后，会把它变成 /html 技能之类的。虽然这可能有一定价值，但我想强调，你不需要做太多事情就能让克劳德这么做。你可以直接让它“制作一个 HTML 文件”或“创建一个 HTML 伪造品”。

The trick is knowing what you want the artifact to do and how you might use it. You may over time make a skill, but for now I’d suggest just prompting from scratch to get a hang of how to use it in different cases.关键是你知道你想让神器做什么，以及你可能如何使用它。你可能会随着时间积累技能，但目前我建议你从零开始提示，熟悉如何在不同情况下使用它。

# Use Cases使用场景

To make this more concrete, I’ve made many different HTML files for different use cases. You can view all of them here: [https://thariqs.github.io/html-effectiveness/](https://thariqs.github.io/html-effectiveness/) but here’s an overview.为了更具体一点，我为不同的用例制作了许多不同的 HTML 文件。你可以在这里查看所有内容：[https://thariqs.github.io/html-effectiveness/](https://thariqs.github.io/html-effectiveness/)，但这里有一个概览。

## Specs, Planning & Exploration规格、规划与探索

HTML is a rich canvas for Claude to dive into a problem. When I start working on a problem instead of a simple markdown plan I expect to make a web of HTML files. For example, I might start with asking Claude Code to brainstorm and create some explorations of different options. I would then ask it to expand more into one, maybe make mockups or code snippets. Finally, when I feel good I’ll ask it to write an implementation plan. When I’m happy with the plan I’ll create a new session and pass in all of these files for it to implement.HTML 是 Claude 深入解决问题的丰富画布。当我开始做一个问题时，我期望自己不是简单的标记计划，而是建立一个 HTML 文件的网络。比如，我可能会先让 Claude Code 一起头脑风暴，探索不同的选项。然后我会让它扩展成一个，可能做样图或代码片段。最后，当我感觉好了，我会让它写一份实施计划。当我对计划满意时，我会创建一个新会话，把所有这些文件交给它实现。

When verifying I’ll also ask the verification agent to read in the files and it will have much broader context on what is needed.验证时我也会让验证人员查看文件，里面会有更广泛的背景信息。

![图像](https://pbs.twimg.com/media/HH0BFWLbMAEk_7T?format=jpg&name=large)

**Example Prompts:示例提示：**

- I'm not sure what direction to take the onboarding screen. Generate 6 distinctly different approaches — vary layout, tone, and density — and lay them out as a single HTML file in a grid so I can compare them side by side. Label each with the tradeoff it's making.我不确定该把入职流程往哪个方向走。生成 6 种截然不同的方法——不同的布局、语气和密度——并将它们排成一个 HTML 文件，形成网格，方便我并排比较。给每一个标签标注它所做的权衡。
- Create a thorough implementation plan in a HTML file, be sure to make some mockups, show data flow and add important code snippets I might want to review. Make it easy to read and digest.在 HTML 文件中制定详尽的实现计划，确保制作一些模型，展示数据流，并添加我可能想审查的重要代码片段。让它易于阅读和消化。

**Use Cases:使用场景：**

- Exploring other ways to implement something in code探索用代码实现某些东西的其他方法
- Exploring multiple visual designs探索多种视觉设计

## Code Review & Understanding代码审查与理解

Code can be difficult to read in a Markdown file. But with HTML we can render diffs, annotations, flowcharts, modules, etc. Use this to understand code that the agent has written, to get code review or to explain a PR to someone reviewing your code. I find this often works better than the default Github diff view, and I attach a HTML code explainer to every PR I make now. Markdown 文件中的代码可能难以阅读。 但用 HTML 我们可以渲染差异、注释、流程图、模块等。 利用这些来理解经纪人写的代码，进行代码审查，或者向审核你的代码的人解释永久居民。我发现这样通常比默认的 Github 差异视图效果更好，我现在每个 PR 都会附带 HTML 代码解释。

![图像](https://pbs.twimg.com/media/HH0BRSQbMAAuuof?format=png&name=large)

**Example prompt:示例提示：**

Help me review this PR by creating an HTML artifact that describes it. I'm not very familiar with the streaming/backpressure logic so focus on that. Render the actual diff with inline margin annotations, color-code findings by severity and whatever else might be needed to convey the concept well.帮我通过创建一个描述它的 HTML 文稿来复习这个 PR。我对流式/背压逻辑不太熟悉，所以重点关注这个。用内联边距注释、按严重程度的颜色编码以及其他必要的方法来渲染实际的差异，以便更好地传达概念。

**Use Cases:使用场景：**

- Creating a PR创建 PR
- Reviewing a PR审核 PR 时
- Understanding a topic in Code理解代码中的主题

## Design & Prototypes设计与原型

Claude Design is based on HTML because HTML is incredibly expressive at design, even if your end surface is not HTML. Claude can sketch out a design in HTML and then write it in your language of choice, be it React, Swift, etc.Claude Design 基于 HTML，因为 HTML 在设计上极具表现力，即使你的终端表面不是 HTML。Claude 可以用 HTML 草拟设计，然后用你喜欢的语言写成，比如 React、Swift 等。

You can also prototype interactions, such as animations, actions, etc. Consider asking Claude to make sliders, knobs, etc. to tune in exactly what you’re looking for.你还可以原型制作交互，比如动画、动作等。可以考虑让 Claude 做滑块、旋钮等，调到你想要的音色。

![图像](https://pbs.twimg.com/media/HH0BXqjboAAHGsw?format=jpg&name=large)

**Example prompt:示例提示：**

I want to prototype a new checkout button, when clicked it does a play animation and then turns purple quickly. Create a HTML file with several sliders and options for me to try different options on this animation, give me a copy button to copy the parameters that worked well.我想做一个新的结账按钮的原型，点击后会播放播放动画，然后很快变成紫色。创建一个包含多个滑块和选项的 HTML 文件，让我可以在这个动画中尝试不同的选项，给我一个复制按钮来复制那些效果好的参数。

**Use this for:它用于：**

- Creating design system artifacts创建设计系统产物
- Adjusting components调整组件
- Visualizing component libraries组件库可视化
- Prototyping Joyful Animations制作快乐动画原型

## Reports, Research & Learning报告、研究与学习

Claude Code is incredibly good at synthesizing information across multiple data sources and converting it into a report for readability. You can prompt Claude to search your Slack, your codebase, git history, the internet, etc. and use it to generate extremely readable reports for yourself, for leadership, for your team, etc. Claude Code 非常擅长将多个数据源的信息综合并转化为报告，便于阅读。你可以提示 Claude 搜索你的 Slack、代码库、git 历史记录、互联网等，并用它生成极易读的报告，供自己、领导层、团队等使用。

You could assemble this in the form of a long HTML document, an interactive explainer or even a slideshow/deck. Ask Claude to use SVG for diagrams to help visualize it. For example, for my posts on prompt caching, I asked Claude to prepare an in-depth research file in HTML for me to read on all of our changes to prompt caching after reading the git history.你可以把它整理成一份长的 HTML 文档、互动解说，甚至幻灯片/演示文稿。让 Claude 用 SVG 做图表，帮助可视化。 例如，针对我关于提示缓存的帖子，我请 Claude 准备一个深入的 HTML 研究文件，让我在阅读 git 历史后阅读我们所有提示缓存的变更。

![图像](https://pbs.twimg.com/media/HH0Bp86bUAAJDyZ?format=jpg&name=large)

**Example prompt:** I don't understand how our rate limiter actually works. Read the relevant code and produce a single HTML explainer page: a diagram of the token-bucket flow, the 3–4 key code snippets annotated, and a "gotchas" section at the bottom. Optimize it for someone reading it once.示例提示： 我不太明白我们的速率限制器到底是怎么工作的。阅读相关代码，制作一个 HTML 解释页面：标记桶流程图、注释的 3–4 个关键代码片段，以及底部的“陷阱”部分。优化一下，让有人只读一次。

**Use this for:它用于：**

- Summarize how a feature works总结一个功能的工作原理
- Explain a concept to me给我解释一个概念
- Weekly status reports to your boss每周向老板汇报状态
- Incident reports to your leadership向领导提交事件报告
- SVG illustrations, flowcharts, technical diagrams, etcSVG 插图、流程图、技术图等

# Custom Editing Interfaces自定义编辑接口

Sometimes it’s hard to describe what you want purely in a text box. In this case, I'll ask Claude to build me a throwaway editor for the exact thing I'm working on. Not a product, or a reusable tool, but a single HTML file, purpose-built for this one piece of data.有时候，单纯用文本框描述你想要什么很难。在这种情况下，我会请 Claude 帮我做一个一次性编辑器，专门针对我正在做的项目。这不是一个产品，也不是一个可复用的工具，而是一个专门为这条数据而设计的单一 HTML 文件。

The trick is always to end with an export: a "copy as JSON" or "copy as prompt" button that turns whatever I did in the UI back into something I can paste into Claude Code.诀窍总是以导出结束：一个“复制为 JSON”或“复制为提示”按钮，把我在 UI 里做的事转回我可以粘贴到 Claude 代码里的东西。

![图像](https://pbs.twimg.com/media/HH0FbKebUAAsRPr?format=jpg&name=large)

**Example prompts:示例提示：**

- I need to reprioritize these 30 Linear tickets. Make me an HTML file with each ticket as a draggable card across Now / Next / Later / Cut columns. Pre-sort them by your best guess. Add a "copy as markdown" button that exports the final ordering with a one-line rationale per bucket.我需要重新优先处理这 30 张线性工单。给我做一个 HTML 文件，每个工单作为可拖拽的卡片，横跨现在/下一/稍后/切割列。按你的最佳猜测预先排序。添加一个“复制为 markdown”按钮，导出最终订单，每个桶有一行说明。
- Here's our feature flag config. Build a form-based editor for it, group flags by area, show dependencies between them, warn me if I enable a flag whose prerequisite is off. Add a "copy diff" button that gives me just the changed keys.这是我们的功能标志配置。为它搭建一个基于表单的编辑器，按区域分组旗帜，显示它们之间的依赖关系，如果我启用了先决条件不符的旗帜，会提醒我。加一个“复制差别”按钮，只显示更改后的按键。
- I'm tuning this system prompt. Make a side-by-side editor: editable prompt on the left with the variable slots highlighted, three sample inputs on the right that re-render the filled template live. Add a character/token counter and a copy button.我正在调整这个系统提示。做一个并排编辑器：左边是可编辑提示，变量插槽高亮，右边有三个样本输入，实时重新渲染填充模板。添加角色/标记计数器和复制按钮。

**Use this for:它用于：**

- Reordering, triaging, or bucketing anything (tickets, test cases, feedback)重新排序、分流或分桶处理任何内容（工单、测试用例、反馈）
- Editing structured config (feature flags, env vars, JSON/YAML with constraints)编辑结构化配置（功能标志、env vars、带约束的 JSON/YAML）
- Tuning prompts, templates, or copy with live preview调校提示、模板或带有实时预览的文案
- Curating datasets, approve/reject rows, tag examples, export the selection策划数据集，批准/拒绝行，标签示例，导出所选内容
- Annotating a document, transcript, or diff and exporting the annotations注释文档、文字记录或差异文并导出注释
- Picking values that are painful to express in text: colors, easing curves, crop regions, cron schedules, regexes.选择那些难以用文字表达的值：颜色、缓曲线、裁切区域、cron 计划、正则表达。

## Frequently Asked Questions常见问题解答

I’ve been telling many people about how I’ve switched to HTML and I’ve seen a few repeated questions.我跟很多人说我已经转向 HTML，也看到过一些反复出现的问题。

**Isn’t it less token efficient?** While markdown often uses fewer tokens, I’ve found that the added expressiveness of HTML and the much higher likelihood of me reading it means I get overall better output. With the 1MM context window in Opus 4.7, the increased token usage is not really noticeable in the context window.它不是更低的代币效率吗？ 虽然 markdown 通常用的标记更少，但我发现 HTML 的表现力和我阅读的可能性大大提高，整体输出更好。在 Opus 4.7 的 1MM 上下文窗口中，令牌使用增加在上下文窗口中并不明显。

**When do you use markdown for now?** I have honestly stopped using markdown altogether for almost everything, but I’m probably far on the HTML maximalist side of things.你现在什么时候用 Markdown？ 说实话，我几乎已经完全不使用 Markdown 了，但我可能已经偏向 HTML 极致主义了。

**How do I view the HTML file?** I tend just open it in a browser locally (you can ask Claude to open it), or upload to S3 if you want a shareable link.我该如何查看 HTML 文件？ 我通常在本地浏览器打开（你可以让 Claude 帮我打开），或者上传到 S3，如果你想要一个可分享的链接。

**Doesn't this take longer to generate than markdown?** This does take longer! HTML can take 2-4x longer than Markdown, but I've found the results are worth it.这不是比降价更花时间生成吗？ 这确实需要更长时间！HTML 可能比 Markdown 慢 2 到 4 倍，但我发现效果很值得。

**What about version control?** This is honestly one of the biggest downsides of HTML, HTML diffs are noisy and hard to review compared to Markdown.版本控制怎么办？ 说实话，这也是 HTML 最大的缺点之一，HTML 差异比 Markdown 更吵，也很难复习。

**How do I get Claude to match my taste / not make it ugly?** The frontend design plugin helps Claude make good HTML files. But to match your own companies style, you can create a single design system HTML file by pointing Claude at your codebase. You can then use that design system file as a reference for other html files.**我该如何让 Claude 符合我的品味/不让它变得难看？** 前端设计插件帮助 Claude 制作优质的 HTML 文件。但为了符合你公司的风格，你可以通过指向代码库的 Claude 创建一个单一的设计系统 HTML 文件。你可以用这个设计系统文件作为其他 HTML 文件的参考。

## Stay in the Loop

All of the above is to say that I think the real reason I use HTML is that I feel much more in the loop with Claude. I had begun to fear that because I had stopped reading plans in depth I would simply have to leave Claude to make its choices.

But I am happy to say instead that I feel more in the loop than ever before when using HTML. I hope you do too.