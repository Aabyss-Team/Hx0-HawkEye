# 历史更新日志：1.0.1–1.0.6

[返回 1.0.7 首页](./README.md)

> 这里按版本介绍 1.0.1–1.0.6 的主要功能与更新，截图对应当时界面。当前操作、安装方式与版本权益请参阅 [1.0.7 首页](./README.md)。

## 十三、1.0.1 更新日志

> 以下条目记录各版本当时的更新；当前使用方法请参阅 [1.0.7 首页](./README.md)。

本次 `V1.0.1` 主要围绕两项专业版能力完善：

- **智能代理分流器（1.0.1 首发时为专业版，1.0.6 起社区版开放）**：在基础设置页 `抓包类型/后缀` 下方新增代理分流入口，可按站点规则把命中的浏览器请求转发到 Burp、Yakit 或其他上游代理，未命中的请求继续保持原有网络路径。适合把“浏览器原生会话抓包”与“代理深度调试”串成一个工作流，减少频繁切换系统代理的成本。

  <img width="430" height="573" alt="image" src="https://github.com/user-attachments/assets/db12989b-7d10-4b11-9859-a9da61a79d03" />

- **加密逻辑智能分析（专业版）**：功能在AI分析按钮右侧，模型会结合当前请求的 URL、参数、请求头、Body、响应线索，以及同页 JS / HTML 中的函数名、字段名和提交流程，辅助判断前端是否做了编码、摘要、签名或混合加密，适合复核改包前后的签名链路变化。（一句话总结：让AI帮你猜加密/编码/签名逻辑，省去人肉逆向的时间。）

  <img width="780" height="151" alt="image" src="https://github.com/user-attachments/assets/727c7ad7-c5e8-438f-a9e7-cc7f7afe5697" />

  <img width="1548" height="940" alt="image" src="https://github.com/user-attachments/assets/2c431003-88c4-4b1f-90b3-07c749de443c" />

  <img width="1548" height="940" alt="image" src="https://github.com/user-attachments/assets/ea538cdc-b9ce-4bfa-be6f-c762edb54f91" />

  <img width="1548" height="940" alt="image" src="https://github.com/user-attachments/assets/1c145765-ab5e-41e5-b905-455964b64190" />
  
- **稳定性补充**：改善请求头显示，以及普通抓包、拦截和代理切换时的稳定性。
- **侧栏和批量页面优化**：侧栏报文展示与交互优化（双端一致），批量页面整体布局优化。
- **页面内重放和页面内Fuzz功能优化**：更新后支持表单 POST（请求头 Content-Type: application/x-www-form-urlencoded）。
- **重放工作台优化**：编解码功能现支持响应体处理，新增作用域区分，并统一了请求与响应的撤销/重做记录。
- **「全部域名」筛选**：修复域名筛选为「全部域名」时与工作台范围（当前页 / 全部数据包）联动不当导致的列表或筛选状态异常。
- **抓包 / 拦截列表**：表头各列右侧竖条可拖拽调节列宽，宽度本地持久化，下次打开仍生效。
- **302 / 重定向抓包**：改善重定向（如 302）请求的记录，减少遗漏和重复显示。
- **表头三态排序**：抓包 / 拦截列表表头支持「默认 → 升序 → 降序 → 回默认」；Fuzz 结果表同样三态，取消排序后按原始序号恢复顺序；点击列宽拖条不会触发排序。



## 十四、1.0.2 更新日志

本次 `V1.0.2` 围绕 **HTTP 重放增强**、**WebSocket 工作台**、**AI 任务台（含运行中补充线索）** 及 **社区版拦截开放** 等重点升级，进一步提升 Web 安全测试、CTF 与日常抓包分析效率。

<img width="1055" height="1491" alt="v1 0 2海报" src="https://github.com/user-attachments/assets/853169b7-01bb-4f13-8d44-81fa68567e78" />

## 主要更新

### 1. 重放数据包支持关键请求头覆盖

重放工作台现已增强对特殊请求头的处理能力，支持在 Raw 请求中编辑并生效以下字段：

- `Referer: https://xxx.com`
- `User-Agent: xxx`
- `Origin: https://xxx.com`
- `X-Forwarded-For: x.x.x.x`

该能力适用于常见的来源校验、UA 校验、伪造来源、CTF Referer 绕过等场景。用户可以直接在 Raw 请求中修改请求头后重放，工具会尽量保持与 Burp Suite 类似的重放行为。

### 2. 新增 AI 任务模块

新增独立的 AI 任务模块，用于将抓包、请求分析、漏洞测试和报告生成串联成自动化流程。

当前 AI 任务支持两种模式：

- **智能渗透模式**  
  面向常规 Web 安全测试场景，AI 会基于目标站点、历史流量和页面上下文，自动进行信息收集、入口分析、攻击建模、漏洞探测和结果研判。

  <img width="3912" height="2070" alt="909110ca03be628642c272a91c8c7cc6" src="https://github.com/user-attachments/assets/e42f8720-613a-429b-952d-dd93fbb24a22" />


  <img width="3912" height="2070" alt="91bcbb07d5a3bd6db6ef5f9baea3563e" src="https://github.com/user-attachments/assets/fdaee4df-15b7-489d-8ecd-0462d7e9619d" />


- **CTF 夺旗模式**  
  面向 CTF Web 题目，AI 会围绕题目入口、提示、响应特征和可疑参数自动规划解题路径，尝试构造利用请求，并在命中 Flag 后生成复盘报告。

  <img width="3912" height="2070" alt="31c644c1426fc64801d7d1caac178e13" src="https://github.com/user-attachments/assets/c100544b-7ca3-4616-bb1a-7a45ddbeb64c" />

  <img width="3912" height="2070" alt="89ef599acf45a623a3dcd065a48c9119" src="https://github.com/user-attachments/assets/cd57e1c5-1a77-4d93-b3ea-5e124937b06e" />


AI 任务会记录执行过程、请求证据、关键 payload、Flag 命中结果和最终报告。运行中可使用工具栏 **「补充线索」** 提交新信息，帮助任务调整后续步骤。详见用户手册 §10。

### 3. 拦截模式开放给社区版

拦截模式现已开放给社区版用户使用（含命中规则时的 **HTTP 与 WebSocket 帧** 侧栏队列）。

社区版用户可以使用拦截模式完成请求暂停、查看、修改、放行等基础操作，更方便地进行手工测试、参数调试和请求验证。

<img width="1956" height="1035" alt="image" src="https://github.com/user-attachments/assets/0f4cb847-e564-40c1-84f3-b6bc2b7a73c5" />

### 4. WebSocket 抓包、重放、微型 Fuzz 与拦截改包

弹窗勾选 **WebSocket** 后，侧栏可按类型筛选；握手多为 `GET 101`，数据帧为 **`WS`**（**`OUT`** / **`IN`**）。**帧重放** 与 HTTP 共用重放工作台，依赖页内 **`OPEN`** 连接；**`§...§` + 微型 Fuzz** 以下一条入站帧为响应。**拦截** 下支持 **帧级** 编辑/放行/丢弃。定位为浏览器内页面 JS 创建的 WebSocket，非系统级 MITM；细节见用户手册 §5。

<img width="1548" height="942" alt="image" src="https://github.com/user-attachments/assets/392bcbfd-4356-459d-a6eb-0c2d58ff8bcd" />

### 5. AI 任务：运行中「补充线索」

任务执行中展开 **「补充线索」**，输入新发现的参数、回显、入口或 CTF 提示，点击 **「提交」**。任务会在后续步骤参考这些信息；单次提交和队列均有长度限制，请按界面提示填写。不要粘贴真实口令。
<img width="1548" height="942" alt="image" src="https://github.com/user-attachments/assets/a81e5507-1561-413e-971d-db82ae7fbf0e" />
<img width="1548" height="942" alt="image" src="https://github.com/user-attachments/assets/e6ddb672-c912-4099-9ad7-fdd82fe6efc9" />

### 6. AI 任务：执行体验改进

AI 任务会参考已有请求证据和失败步骤，调整后续计划；达到目标或找到 Flag 后，及时整理结果与报告。

---

## 十五、1.0.3 更新日志

本次 `V1.0.3` 主要带来三项更新：

### 1. AI 任务支持加载 Skills（专业版）

AI 任务台可注入内置 **渗透 / CTF 知识库**，也支持在高级设置 **导入外部 SKILL.md 或技能目录**；任务面板可按需勾选库与子模块，启动后作为上下文辅助多阶段自动化测试与研判。

<img width="1956" height="1040" alt="image" src="https://github.com/user-attachments/assets/63206722-eef8-4e76-ab67-64d631c17644" />


<img width="438" height="563" alt="image" src="https://github.com/user-attachments/assets/6d56a214-5d1c-4181-b421-fc1783f03c40" />


### 2. 抓包与拦截体验优化

优化侧栏 **抓包 / 拦截** 列表的浏览与操作：筛选与范围切换更连贯，列表展示与改包、放行等日常动作更顺手，减少高频调试时的来回切换。

### 3. 新增在线激活

单击弹窗 **状态徽章** 打开「软件激活」，新增 **在线激活** Tab，支持订阅或永久会员；权益联网同步并 **缓存到本机**，断网后可在有效期内继续使用专业版。与原有 **离线激活码** 并行，开通与续费更方便。

<img width="438" height="563" alt="image" src="https://github.com/user-attachments/assets/71313a25-a59d-4c02-80cf-9ee6ef6a75e2" />

---

## 十六、1.0.4 更新日志

本次 `V1.0.4` 主要带来四项更新：

### 1. 油猴脚本 + 页面脚本工作台（专业版）

支持导入 `.user.js` 油猴脚本，侧栏统一管理、一键注入；可用 AI 从流量创建或优化脚本，并与抓包、重放、敏感扫描等能力联动。人写脚本、AI 写脚本、AI 任务调度脚本三条路径打通。

<img width="1548" height="941" alt="image" src="https://github.com/user-attachments/assets/152c24a6-cf8e-41dd-a41e-641b11da5fb7" />

<img width="3080" height="1716" alt="e327bce7470c8582ba612072f9e9019b" src="https://github.com/user-attachments/assets/943ef6ca-0fb7-4047-9abf-789482b149c4" />



### 2. AI 任务智能脚本调用（专业版）

勾选 **智能脚本调用** 后，AI 任务在渗透 / CTF 过程中可自动列出、执行或创建页面脚本，把页面侧情报采回来，再继续重放验证与报告生成。

### 3. 拦截 / 抓包可靠性增强

本地靶场与自签名 HTTPS 拦截更稳定；修复拦截队列为空等回归问题；改包编辑器支持正常输入中文。

### 4. Firefox 稳定性与双端对齐

修复 Firefox 抓包、侧栏、拦截、重放、脚本注入等主链路问题，双端日常体验进一步对齐。


---

## 十七、1.0.5 更新日志

本次 `V1.0.5` 主要带来四项更新：

### 1. AI 任务台全面升级（本版核心）

执行记录按时间轴展示，可展开查看工具结果；日志与报告之间可拖动调整宽度。启动前可让 AI 帮助理解任务背景，报告包含 **漏洞清单与请求 / 响应证据**，并支持加密逻辑分析和高级编解码。

<img width="3080" height="1788" alt="7adc70c64d50d5272a58d6aec4db0c55" src="https://github.com/user-attachments/assets/83e16c37-e808-438b-8b01-c9be189381e1" />


### 2. Skills 知识库加厚 + AI 生成技能

内置子模块扩容至 **渗透 19 + CTF 28**；主 Skill 新增 **「智能启用」** 开关；高级设置新增 **AI 生成技能**，可生成单个 Skill 或技能集合并保存为独立 Skill、内置库子模块或追加到已有导入 Skill。

<img width="1038" height="816" alt="image" src="https://github.com/user-attachments/assets/559350c7-dcbe-4552-9936-88cb0ea9b066" />

<img  height="740" alt="3b62bafea675b0fe0e2b790e8e4e689e" src="https://github.com/user-attachments/assets/b00e9183-4e18-4bb1-9561-042afe4494ab" />

<img  height="740" alt="cc4666c5f38a35d7174ebe3c357c2ef4" src="https://github.com/user-attachments/assets/e377d19c-b6c8-404c-9eb3-56e7b2c006d5" />


### 3. 编解码能力补齐

重放台补齐 **AES / DES / RSA / SM** 与智能套娃解码；内置页面脚本 **「智能解码助手」**（默认启用）：选中文本即尝试常见解码与哈希识别；高级 AES / 套娃仍走重放台或详情内联「加密&编码」。

<img width="1600" height="1164" alt="e958884a06b31b7830f092368ce2931f" src="https://github.com/user-attachments/assets/41721abe-97fd-4eeb-a2c0-95b8bf7b20a1" />

### 4. 体验优化与问题修复

修复 Chrome / Firefox 双端若干系统问题；优化拦截 / 调试模式 / 被动监听等开关联动；改进侧栏与设置交互提示。


---

## 十八、1.0.6 更新日志

### 1. 鹰眼浏览器自动化 MCP（PRO）

新增面向安全工作流的 HawkEye MCP，定位类似安全专版 Playwright MCP：Codex、Cursor、LM Studio 等支持 MCP 的 Agent Host 接入 `hx0-hawkeye` 后，可由 Host 中的模型自动调用 `browser_navigate`、`browser_type`、`browser_snapshot` 以及鹰眼抓包、重放、变异、编解码、TLS、敏感信息和证据工具控制真实浏览器。本地 Server 仅监听回环地址，支持 stdio、Streamable HTTP 与 legacy SSE；用户需主动开启扩展桥接。该能力独立于扩展内 AI 任务台。

<img width="1800" height="1382" alt="Codex、Cursor、LM Studio 等 Agent Host 通过 HawkEye MCP 自动控制浏览器" src="https://github.com/user-attachments/assets/ff0c2671-6559-4f38-b6f5-2a6a50c5375a" />

### 2. 浏览器级 Agent（PRO）

Agent 模式仅对有效试用或专业版授权开放。它以用户当前真实 HTTP(S) 标签页为任务起点，支持多轮计划、安全批准模式、复杂控件 / iframe / Shadow DOM 交互、视觉截图、附件、抓包研判、重放、编解码、自主联网研究、原生下载、长上下文记忆与可展开的工具证据。

<img width="1500" height="900" alt="v1.0.6 浏览器级 Agent" src="https://github.com/user-attachments/assets/26994329-4e55-42c4-b48d-9a60153ae146" />

<img width="3096" height="1882" alt="ee4d555e47df0404083987143a76c727" src="https://github.com/user-attachments/assets/cb8d9460-bb90-4bc8-be5f-5ea635b95bfb" />

<img width="3096" height="1882" alt="1570653742b0ce10142f775ebe5171af" src="https://github.com/user-attachments/assets/ed512839-09b8-4307-a8f0-bb620fc305fb" />


### 3. 性能与资源占用改进

降低 Firefox 的后台资源占用，改善大型页面的读取、抓包列表刷新与 Agent / MCP 响应。大量结果可分页继续查看，兼顾操作流畅度与证据完整性。

### 4. 自主选择 Agent 使用的 Skills

内置知识库包含 19 个渗透子模块和 28 个 CTF 子模块。新 Agent 聊天默认关闭 Skills；需要使用时，先在高级设置选择可用技能，再在当前聊天中开启 **Skills**。

### 5. 相比 1.0.5 的社区版能力开放

智能代理分流器、全量深度搜索，以及敏感信息匹配（内置规则、自定义正则、关键词库与批量导入导出）在 1.0.6 起向社区版开放；AI 任务、AI Skills、浏览器级 Agent 与 HawkEye MCP 仍为专业版能力。

### 6. 0930 抓包与交互改进

- 抓包历史增加当前域名、当前标签页和全部记录范围；跨子域名请求仍归属发起请求的标签页。拦截队列自动刷新，原始请求体/响应体无法取得时显示原因。
- 重放台默认使用 Pretty；在 Pretty 或 Raw 中编辑都能重放。WebSocket 帧、批量重放、AI 分析及暗链检测的反馈得到改进。
- 设置中的删除确认改用内置弹窗，Firefox 快捷键按钮样式与 Chrome 一致；中英文设置可随界面语言切换，暗链设置卡片在低弹窗高度下可完整滚动，规则标题也可换行。Agent 待批准操作可从等待状态重新打开，遮罩和 Esc 不再误关批准弹窗。
- 本地 MCP Server 1.0.13 改善安装示例及连接诊断。
