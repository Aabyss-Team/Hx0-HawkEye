# 🦅 Hx0 HawkEye: Full-stack lightweight capture & AI security auditing extension


【[中文](./README.md) / English】


![](https://img.shields.io/badge/Network-No_system_proxy-success)  ![](https://img.shields.io/badge/UI-Sidebar_integrated-5865F2)  ![](https://img.shields.io/badge/Session-Same_origin_XHR_Fetch_WS-00A86B)  ![](https://img.shields.io/badge/Capture-Intercept-4285F4)  ![](https://img.shields.io/badge/Capability-Traffic_replay-blue)  ![](https://img.shields.io/badge/Capability-Micro_Fuzz-8B5CF6)  ![](https://img.shields.io/badge/Capability-Sensitive_data-FF69B4)  ![](https://img.shields.io/badge/Capability-Dark_link_scan-333333)  ![](https://img.shields.io/badge/AI-BYOK_optional-orange)

## 1. What it is
**Skip the proxy hassle—truly ready out of the box.** Hx0 HawkEye is a native browser extension (Chrome / Firefox and mainstream Chromium) that gives you a full **capture, intercept (HTTP + WebSocket frames), replay, micro-Fuzz, and AI-assisted auditing** loop directly in the sidebar.

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774276035508-0a9af8e0-4a11-4c83-9fe7-8ea82484d093.png)

#### ⚡ Core advantage: why not a classic proxy?
+ **Zero environment overhead**: no Burp Suite required, no system proxy, no root trust or Java setup.
+ **Session fidelity**: sees real page **XHR / Fetch / WebSocket** traffic with the **same origin login state** as the active tab—no more “proxy ate my cookies” or constant re-auth pain.
+ **Works immediately after install**: ideal for day-to-day dev/debug, API triage, and **authorized** first-pass security review.

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774275081238-a9d3306e-b723-4e0f-846b-38ef9a50ca02.png)

#### 🤖 Differentiator: end-to-end AI (BYOK)
Bring your own model API (BYOK) and embed AI into the sidebar workflow:

+ **Smart cases & payload generation**: structured test ideas in the replay workbench; context-aware mutated payloads in micro Fuzz—without bloated static wordlists.

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774275467560-2fe55566-6241-4482-b932-f1bd41dcd726.png)

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774275500332-6fb4554b-861f-4e98-81ee-dbe1bf42d005.png)

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774276635896-103172aa-4680-4c76-b96a-d31a1dfce8b0.png)

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774276656535-f6f1c42d-6fdf-499e-a7eb-2122ef98d4d6.png)

+ **Deep single-request analysis**: semantic AI read-through of full Request / Response for risk triage.

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774275567642-5018496d-2b53-4674-bd7a-3d65d0806658.png)

+ **Batch synthesis**: select multiple packets in a dedicated workbench; AI extracts patterns across APIs and third-party calls to support supply-chain / dependency-surface **first-pass** review.

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774275663993-07154b5a-c440-4b22-820c-c3645a284671.png)

+ **Dual-engine static hunting**: **built-in dark-link rules + AI contextual interpretation** for batch replay across pages and broad static coverage.



<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774275800441-dc18805d-35b8-46a5-a983-afef8e05450a.png)

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774275958382-e5751509-132f-4ebc-8736-0f6e642048ec.png)

---

## 2. Why we built it
With **SPAs, heavy XHR/Fetch, and WebSocket**, engineers constantly switch between “real browser session” and “capture / tamper / replay.” Classic proxies (e.g. Burp) are powerful but need system proxy and trust, and **cookies / login state** can diverge from the tab; lightweight toolbar extensions often lack **durable history, structured detail, and a closed-loop workbench**.

**Hx0 HawkEye** aims to keep **no mandatory system proxy** while folding **capture (HTTP / WebSocket) → filter → detail audit → intercept → replay → micro Fuzz → sensitive & dark-link checks → optional AI** into **one sidebar hub**, cutting context-switch cost for dev triage and **authorized** API review.

---

## 3. Features
Core flow: **Capture** (optional **WebSocket**) → **Filter** → **Detail** → **Replay** (HTTP / **WebSocket frames**; optional **AI test cases**) → **Micro Fuzz** (HTTP / **WS**; optional **AI payloads**) → **Dark-link / AI packet analysis** (including **batch AI / dark-link workbenches** after multi-select) → **AI Task Console** (Pro, multi-stage automation).

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774276082646-8aad5093-4c32-4595-9c6b-a5378a0f564d.png)

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774276530139-e52d8423-756d-4ad1-83f2-7ceb512d6508.png)

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774276559659-94bcce01-2393-4383-84db-91ba9453bb99.png)

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774276602069-b749ad60-8ba6-49a1-8129-acca2f9b1aaf.png)

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774276735904-99b04e61-1646-479c-85bf-92b9998bece0.png)

| Module | Description |
| --- | --- |
| **Capture** | Hooks `fetch` / XHR in the page world; records requests and responses (including bodies, with size guards). Noise control via **host/IP wildcards**, **resource types** (XHR/Fetch, **WebSocket**, JSON, HTML, JS, binary, etc.), and **custom suffixes**. With **WebSocket** enabled, records handshakes (e.g. `GET 101`) and frames (`WS`, `OUT` / `IN`). |
| **History** | **IndexedDB** persistence; filters by type, host, method, status, **sensitive hits**, search; default scope **current page** or **all packets**. |
| **Intercept** | Queued hold for **HTTP**; **WebSocket** outbound/inbound **frames** can enter a **frame** queue when rules match; **edit, forward, drop** in the sidebar; bulk actions; shares target rules with capture. |
| **Detail audit** | **Pretty / Raw / Hex**; response **Render** (sandbox); **sensitive** aggregation & highlights; copy full URL from title; download split raw **.txt**; **Burp-style** export. |
| **Replay** | Edit raw traffic and replay; **WebSocket frame replay** shares the same workbench and sends via a still-**OPEN** page socket (not a fresh handshake); **in-page replay** (some WAF challenge pages); undo/redo; host switch; **AI test cases** from current request/options (requires AI config). |
| **Encode / hash** | MD5, SM3, SHA, ROT13, Base64, URL, Hex, etc.; scope: **selection / param values only / full URL line**. |
| **Micro Fuzz** | `§...§` injection points; **Start Fuzz** and **in-page Fuzz** (HTTP/DOM); **WebSocket micro Fuzz** sends serially and uses the **next inbound frame** as the response (needs an active page socket); baseline diff; **AI payloads** from model context; pair with Render, sensitive, and **AI result** views. |
| **Dark link & static threats** | Rule scan on static HTML, etc.; **high-trust TLD** allowlist; downloadable reports; **AI packet/semantic** interpretation; **batch dark-link** workbench for **horizontal compare** and **third-party script clues** (supply-chain first pass). |
| **AI (optional)** | **Single packet**: interpret **request + response**, anomalies and risk notes. **Batch**: multi-select history, dedicated tab with **per-row highlights + summary** for multi-endpoint evidence. **AI Task Console**: multi-stage automation (penetration / CTF) in the sidebar, with **in-task supplementary hints** queued into later turns. Models: OpenAI, DeepSeek, local LM Studio, **custom base URL**; **OpenAI-compatible** and paths such as **Baidu Qianfan coding plans**; traffic goes **only to your configured endpoint** (BYOK). |
| **Sensitive matching** | Built-in rules (IDs, phones, cards, email, Shiro/JWT/Swagger/UEditor/Druid fingerprints, IP, domain, CTF flags, etc.) plus **custom regex** and **keyword lists**; import/export, clear-all. |
| **Batch** | Bulk export/delete, **batch AI**, **batch dark-link** (separate tab), batch replay, etc. |
| **i18n** | UI **中文 / English**. |


**Chrome vs Firefox** differ in sidebar hosting, intranet/self-signed HTTPS helpers, and intercept prompts; **core features align**. See in-extension help after install for details.

---

## 4. Editions (Community / Pro)

Hx0 HawkEye currently uses a three-state model: **Community**, **Pro**, and a **30-minute first-install Pro trial**.

- **Community** keeps the essential loop: **capture (including WebSocket) → inspect → standard replay (including WebSocket frames) → basic encode/decode**, plus **intercept** (**HTTP** and matching **WebSocket frames**).
- **Pro** unlocks **in-page replay / fuzzing, HTTP/WS micro Fuzz, AI, AI Task Console, dark-link review, batch workbenches, and advanced encode/decode tools**.
- **First-install trial** grants **full Pro capability for 30 minutes**. If no activation code is applied after the trial, the product **automatically falls back to Community**.

### Feature Comparison Table

| Feature                                                                                                           | Community Edition | Professional Edition | Description                                                                                                                                                                                                                                                                                                            |
| ----------------------------------------------------------------------------------------------------------------- | ----------------- | -------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Packet Capture Toggle, Target Domain / IP, Capture Type / Suffix Filters                                          | ✅                 | ✅                    | The Community Edition is sufficient for basic traffic capture and noise reduction                                                                                                                                                                                                                                      |
| History List, Current Page / All Packets Switch, Host / Method / Status Code Filters                              | ✅                 | ✅                    | Quickly locate and filter requests                                                                                                                                                                                                                                                                                     |
| Pretty / Raw / Hex / Render Views, Copy / Single Export / Copy URL by Title                                       | ✅                 | ✅                    | Full packet detail auditing is available in the Community Edition                                                                                                                                                                                                                                                      |
| Built-in Sensitive Information Detection & Aggregated Display                                                     | ✅                 | ✅                    | Supports built-in rule-based detection                                                                                                                                                                                                                                                                                 |
| Standard Replay                                                                                                   | ✅                 | ✅                    | Full basic replay workflow; includes **WebSocket frame replay** via the shared workbench (requires an `OPEN` socket in the page)                                                                                                                                                                                                                                                      |
| **Interception Toggle, Modify / Forward / Forward All / Drop All (Community since v1.0.2)**                      | ✅                 | ✅                    | Queue-based intercept for **HTTP** and **WebSocket frames** when host rules match                                                                                                                                                                                                                                                                                                   |
| Floating Action Button, Open as New Tab, Language Switching                                                       | ✅                 | ✅                    | Daily productivity features remain available in the Community Edition                                                                                                                                                                                                                                                  |
| **Basic Encoding & Decoding**: MD5, SM3, SHA-1, SHA-256, ROT13, Base32 / Base64 / URL / Hex                       | ✅                 | ✅                    | Directly available in the Community Edition                                                                                                                                                                                                                                                                            |
| **Advanced Encoding & Decoding**: SHA-512, HMAC-SHA256, Base64URL, Unicode, HTML, JSON, JWT, Timestamp Conversion | ❌                 | ✅                    | Designed for advanced verification, signing, and analysis workflows                                                                                                                                                                                                                                                    |
| **Intelligent Encryption Logic Analysis (Added in v1.0.1)**                                                       | ❌                 | ✅                    | Combines request context with related JS / HTML clues to help identify encoding, hashing, signatures, or hybrid encryption workflows                                                                                                                                                                                   |
| In-Page Replay, In-Page Fuzzing, **HTTP / WebSocket Micro Fuzz**, Injection Point Marking                                           | ❌                 | ✅                    | Suitable for dynamic pages, WAF testing, real-time channels, and high-frequency parameter probing                                                                                                                                                                                                                                   |
| Switch HTTP Method, Switch Target Domain                                                                          | ❌                 | ✅                    | Useful for multi-environment debugging and verification                                                                                                                                                                                                                                                                |
| **Intelligent Proxy Router (Added in v1.0.1)**                                                                    | ❌                 | ✅                    | Located below “Capture Type / Suffix” in Settings. Requests matching site rules can be automatically forwarded to upstream proxies such as Burp Suite or Yakit, while unmatched traffic continues using the original network path. The Firefox version additionally supports “Compatibility Mode” and “Takeover Mode”. |
| AI Analysis Settings, AI Result Analysis, AI Analysis, AI Test Case Generation                                    | ❌                 | ✅                    | All AI-related capabilities are included in the Professional Edition                                                                                                                                                                                                                                                   |
| **AI Task Console (v1.0.2)**                                                                                    | ❌                 | ✅                    | Multi-stage automation: Intelligent Penetration and CTF modes; **in-task supplementary hints**; tighter orchestration and tool chains; ties history, replay, and evidence into reports                                                                                                                                |
| Hidden Link & Static Threat Detection, Report Export, High-Reputation Top-Level Domains                           | ❌                 | ✅                    | Rule scanning, reporting, and advanced noise-reduction capabilities                                                                                                                                                                                                                                                    |
| Full Deep Search, Custom Regex / Keyword Libraries                                                                | ❌                 | ✅                    | Advanced search and rule extension capabilities                                                                                                                                                                                                                                                                        |
| Batch Export, Batch Delete, Batch Replay, Batch AI Analysis, Batch Hidden-Link Detection                          | ❌                 | ✅                    | Unified batch-processing workflow exclusive to the Professional Edition                                                                                                                                                                                                                                                |

> Version `1.0.1` mainly introduced two Professional Edition features: `Intelligent Proxy Router` and `Intelligent Encryption Logic Analysis`.  
> Version `1.0.2` adds **WebSocket** (capture / frame replay / **WS micro Fuzz** / frame intercept), the **AI Task Console** (including **in-task hints** and multi-stage orchestration improvements), and moves **intercept** capabilities to the Community Edition.

### Understanding the Edition Boundaries in One Sentence

- **Community Edition focuses on:** packet inspection (**HTTP / WebSocket**), understanding, basic verification, essential encoding/decoding, and **intercept/tamper**.
- **Professional Edition focuses on:** page-context validation, mutation testing, AI analysis, AI tasks, hidden-link scanning, and large-scale batch workflows.
- If you simply want to evaluate the product’s core value first, the Community Edition is already sufficient for the most important primary workflow.

---

## 5. Product strengths
1. **No proxy wall**: extension form factor—**no separate JVM, no dedicated proxy port**; configure targets and capture.  
2. **Session match**: same **same-origin session** as the active tab; fewer **random logouts** on replay.  
3. **One workbench**: history, intercept, replay, encoders, micro Fuzz, **WebSocket**, sensitive, dark-link, AI—**same sidebar**.  
4. **Modern frontends**: **XHR/Fetch, WebSocket, FormData, multipart**; **Raw / Hex** within extension limits.  
5. **Dynamic-page forensics**: **in-page replay / in-page Fuzz** runs in real DOM—helps with some **WAF / challenge** pages.  
6. **Sensitive & dark-link built-in**: list badges, detail rollups, exportable reports for **dev self-check and authorized first pass**.  
7. **AI in the loop**: **AI Task Console** (multi-stage + **in-task hints**), **AI test cases**, **AI Fuzz payloads**, **single-packet AI**, **batch AI** (multi-packet summary for **supply-chain / dependency** hints), **dark-link rules + AI**—same sidebar, fewer tools.  
8. **AI under your control (BYOK)**: you choose model and endpoint; **data only goes to your API**—cloud (DeepSeek, SiliconFlow, Qianfan, etc.) or **on-prem**.  
9. **Light footprint**: runs with the browser vs heavy standalone proxy stacks.

---

## 6. Comparison with common tools
Compared across shape, session, workflow, and specialties: **Hx0 HawkEye**, **Burp Suite**, **Yakit**, **HackBar / simple extensions**. **Enterprise deep scanning, complex Intruder, non-browser traffic** still belong on dedicated platforms—use **alongside** this product.

| Dimension | **Hx0 HawkEye** | **Burp Suite** | **Yakit** | **HackBar / simple extensions** |
| --- | --- | --- | --- | --- |
| **Shape & deploy** | Browser extension; **sidebar = main hub**; optional floating ball; **no JVM, no proxy port** | Java proxy + browser trust; suite, heavy | Desktop + engine/plugin ecosystem; security platform | Often toolbar mini-panel or single-request helpers |
| **Day-to-day cost** | **Install and go**; no forced system proxy; EN/ZH UI, flow in sidebar | Proxy, root trust, Proxy/Repeater learning curve | Install + pipeline/workflow learning | Fast start, scattered features, weak “project” workspace |
| **Browser session** | **Same tab origin**; fewer login gaps on replay | Via proxy; cookie juggling into Repeater common | Via proxy/engine; different from pure extension | Manual headers/cookies |
| **Modern APIs (XHR/Fetch/SPA + WS)** | Page-world fetch/XHR hooks; optional **WebSocket** capture / frame replay / frame tamper; **multipart Raw/Hex** (within limits) | Full proxy visibility, very capable | Plugins cover complex cases | Often no history, no Hex/sensitive rollups |
| **History & workbench** | **IndexedDB**; rich filters (including **WebSocket** type); detail/replay/fuzz/AI **in sidebar** | Proxy History very strong; more app switching | Platform records & collaboration | Usually **no or weak history** |
| **System proxy / non-browser** | **In-browser** HTTP(S) and **page WebSocket** | Strong | Strong | Weak |
| **Intercept** | **HTTP + WebSocket frames**; queued; per-item or bulk in sidebar | Proxy intercept, industry standard | MITM / workflows | Rare or URL-only |
| **Replay / fuzz** | Replay + **HTTP/WS micro Fuzz** + **in-page replay/fuzz** (e.g. form POST) | Repeater / Intruder mature | Web Fuzzer, etc. | Rarely concurrent fuzz or structured diff |
| **Sensitive / dark-link / reports** | **Built-in rules + badges + rollups**; export | Scanner, BApps; licensing/config | Rich PoC/plugins | Rarely built-in |
| **AI assist** | **BYO API**, **you control data path** | Often third-party or DIY | Growing | Uncommon |
| **Active scan / heavy automation** | Not the focus; **manual tight loop** | Scanner, macros, plugins | PoC, batch, collaboration | Minimal |
| **Resource use** | With browser, **light** | Proxy + JVM, usually higher | Varies | Tiny but narrow |


**Suggested combo**: HawkEye as daily **in-browser hub**; add **Burp / Yakit** for full-site scanning, huge wordlists, or non-browser clients—“fast sidebar loop + deep platform.”

---

## 7. Offline install (release build)
This extension uses low-level network capture and security APIs and is **not listed on the Chrome or Firefox add-on stores**. Download the **release** package from this repo’s **Releases** page (or mirrors/attachments noted in the release notes), then follow your browser below for **offline install**.

> Actual archive names follow each release. Examples: `Hx0-HawkEye-Chrome-V1.0.2-Official.Release` (folder / `.crx`) and `Hx0-HawkEye-Firefox-V1.0.2.Official.Release` (folder / `.xpi`). Version numbers update per release.
>

### Browser compatibility & recommended methods
| **Browser** | **Recommended method** | **Pros** | **Cons / notes** |
| --- | --- | --- | --- |
| **⭐⭐⭐⭐⭐** **Microsoft Edge** | **Drag-drop** `.crx` | Simplest, persists, few security nag dialogs | Turn on **Developer mode** on the extensions page first |
| **⭐⭐⭐⭐⭐** **360 Speed / QQ / Sogou** | **Drag-drop** `.crx` | Easiest in China desktop browsers; few blocks | Generally smooth for third-party extensions |
| **⭐⭐⭐⭐** **Google Chrome** | Load **unpacked folder** | Persists across restarts | **Do not delete** the unpacked folder; some builds show “disable dev-mode extensions” at startup—dismiss to continue |
| **⭐⭐⭐** **Firefox Developer / ESR** | Install `.xpi` | Persistent, store-like experience | Specific Firefox builds + `about:config` tweak |
| **⭐⭐** **Firefox (release)** | **Temporary load** (folder) | Any Firefox version, no advanced prefs | **Extension disappears after browser quit**—reload each session; good for one-off testing |


### Step-by-step
#### 1. ⭐⭐⭐⭐⭐ Recommended · Edge / 360 Speed / QQ / Sogou
These browsers are friendly to local extensions; `.crx` usually **survives restart** with fewer prompts.

1. Open extensions:  
    - **Edge**: `edge://extensions/`  
    - **360 Speed**: `chrome://extensions/`  
    - **QQ Browser**: `qqbrowser://extensions/`  
    - **Sogou**: `se://extensions/`
2. Enable **Developer mode** (Edge: “Developer mode”; often bottom-left or top-right).
3. **Drag** `Hx0-HawkEye-Chrome-V1.0.2-Official.Release.crx` onto the page.
4. Confirm **Add extension**.

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774270129480-cf1a6ea4-5466-4179-98b8-0d3a0770ac96.png)

#### 2. ⭐⭐⭐⭐ · Google Chrome
Chrome tightly restricts non-store `.crx`; prefer **unpacked folder**.

1. Unzip to a **fixed path** (e.g. `D:\Tools\Hx0-Extension\`); **do not delete** `Hx0-HawkEye-Chrome-V1.0.2-Official.Release`.
2. Open `chrome://extensions/`.
3. Enable **Developer mode** (top right).
4. **Load unpacked** → select that folder.
5. Pin the extension. If you see “Disable extensions in developer mode,” **close the banner**—capture usually still works.

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774270197440-8104787e-3b2f-4c85-ad78-d7c00d8bffa2.png)

#### 3. ⭐⭐⭐ / ⭐⭐ · Mozilla Firefox
Unsigned extensions are restricted; for **permanent** install use **Firefox Developer Edition** or **ESR**.

**Option A: ****⭐⭐⭐**** Permanent (Developer / ESR)**

1. Open `about:config`, accept risk.
2. Find `xpinstall.signatures.required`, set to `false`.

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774270335728-56339724-4b13-4e5d-aa3d-4537b31e2c22.png)

3. Open `about:addons` → Extensions.
4. Gear **⚙** → **Install Add-on From File…**
5. Choose `Hx0-HawkEye-Firefox-V1.0.2.Official.Release.xpi`.

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774270404338-e04bc8ac-19af-42ba-b952-5dc0852b4902.png)

**Option B: ****⭐⭐**** Temporary (any Firefox; lost on quit)**

1. After each Firefox start, open `about:debugging`.
2. **This Firefox** → **Load Temporary Add-on…**
3. In the unpacked `Hx0-HawkEye-Firefox-V1.0.2.Official.Release` folder, select `manifest.json`.
4. Repeat after **every** browser restart.

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774270459374-5be17f95-c8c4-4155-99a2-e17831e76862.png)

### After install
+ **Toolbar popup**: capture/intercept toggles, targets & types, open capture UI (sidebar)
+ **Sidebar**: history, intercept, replay workbench
+ **Options**: language, AI, payload encoding, sensitive rules, dark-link, etc. (Chrome: `chrome://extensions` → Details → Extension options)

---

## 8. User manual
After install, open the **in-product User Manual** for full tutorials, **Chrome / Firefox differences**, **FAQ**, and **licensing** (exact entry depends on build).

---

## 9. Security & compliance
+ Use capture, intercept, replay, and Fuzz **only on systems you are authorized to test**.  
+ **AI analysis** may send traffic to third-party or internal model endpoints—**redact** and assess cross-border / compliance rules.  
+ Use **Render** and similar features in trusted environments; sandboxing reduces but does not remove risk from malicious responses.  
+ Commercial use: follow **license** terms in the product.

---

## 10. How to Obtain the Activation Code

New users can first use the **full Pro trial for 30 minutes**. When the trial ends without activation, the product automatically falls back to **Community**. If the experience fits your workflow, you can obtain a Pro activation code through the following methods:

**Visit [the activation code tutorial](https://www.yuque.com/u12459488/bzqpay/udkx5qy1x6guinz0?singleDoc) to get your activation code for free for a limited time.**

---

## 11. Contact & feedback
**Hx0 Team (Hx0战队)**

+ WeChat official account / knowledge planet: **Hx0战队**
+ Email: [hx0studio@foxmail.com](mailto:hx0studio@foxmail.com)

Please include browser + version, extension version, repro steps, and screenshots when reporting issues.

---

## 12. Disclaimer
This project and extension are for **security research, development debugging, and authorized testing** only. Obey applicable laws and scope of authorization.  
The authors and contributors **assume no liability** for **unauthorized testing** or its consequences.

---

## 13. 1.0.1 Changelog

This `1.0.1` update primarily focuses on the enhancement of two professional edition capabilities:

- **Smart Proxy Dispatcher (Professional Edition)**: Added a proxy dispatch entry below the `Capture Type / Suffix`on the basic settings page. It can forward browser requests matching site rules to Burp, Yakit, or other upstream proxies, while unmatched requests continue on their original network path. This is suitable for integrating "native browser session capture" and "in-depth proxy debugging" into a single workflow, reducing the overhead of frequently switching system proxies.
  

<img width="430" height="599" alt="image" src="https://github.com/user-attachments/assets/64221294-63da-4aff-aeec-69250f0b6650" />


- **Encryption Logic Intelligent Analysis (Professional Edition)**: Located to the right of the AI Analysis button. The model combines clues from the current request's URL, parameters, headers, body, and response, along with function names, field names, and submission flows from JS/HTML on the same page, to help determine if encoding, hashing, signing, or hybrid encryption is implemented on the front-end. It is suitable for reviewing changes in signature chains before and after packet modification.（In a nutshell: Let AI help you guess encryption, encoding, or signature logic, saving you the time of manual reverse engineering.）

  <img width="1548" height="940" alt="image" src="https://github.com/user-attachments/assets/f6a6e38e-21c2-4531-b6a9-56234e43e043" />

  <img width="1531" height="929" alt="image" src="https://github.com/user-attachments/assets/718d6ad7-1f99-4c99-b3c7-108afdd48ac0" />

  <img width="1548" height="940" alt="image" src="https://github.com/user-attachments/assets/213b5822-bcf7-404c-baa7-69111dd1116b" />

  <img width="1548" height="940" alt="image" src="https://github.com/user-attachments/assets/b762a1cc-6054-4d17-9fa1-0adec61f35b8" />

  <img width="1548" height="940" alt="image" src="https://github.com/user-attachments/assets/e255ea62-6817-4ad3-815e-c1f7b40c77e2" />

  
- **Stability Improvements**: Concurrently strengthened details related to request header completion and proxy release in the standard capture mode, reducing display discrepancies and the probability of conflicts when switching between standard mode, intercept mode, and proxy settings.
- **Sidebar and Batch Page Optimization**: Sidebar message display and interaction optimization (consistent across both ends), overall layout optimization of batch pages.  
- **Enhanced In-Page Replay and In-Page Fuzz Functions**: Updated to support form POST (Request Header Content-Type: application/x-www-form-urlencoded).
- **Replay Workspace Optimized**:  Encoding/decoding functions now support response body processing, added scope differentiation, and unified undo/redo records for both requests and responses.
- **“All domains” filter**: Fixed incorrect list or filter behavior when the host filter is set to “All domains” and it interacts with the workbench scope (current tab vs all traffic).
- **Capture / intercept list**: Column widths can be adjusted by dragging the vertical handles on the right side of each header cell; widths are saved locally and restored the next time you open the panel.
- **302 / redirect capture**: Improved how redirects (e.g. 302) are recorded and deduplicated across webRequest and passive CDP paths, reducing duplicate entries and missed captures caused by inconsistent typing.
- **Three-state header sorting**: The capture / intercept table headers cycle default → ascending → descending → default. The Fuzz results table uses the same pattern; clearing sort restores the original row order by sequence; clicking a column-width handle does not trigger sorting.

## 14. 1.0.2 Changelog

This `v1.0.2` release strengthens **HTTP replay headers**, adds a **WebSocket workbench**, expands the **AI Task Console** (**in-task hints** + **orchestration improvements**), and brings **intercept** to the Community Edition—boosting Web assessments, CTF workflows, and daily capture analysis.

<img width="1055" height="1491" alt="v1 0 2海报-en" src="https://github.com/user-attachments/assets/98ec2d5e-e410-40c3-92fd-088a87f2d467" />


## Main Updates

### 1. Replay Requests Now Support Critical Header Overrides

The Replay Workbench has been enhanced to better handle special request headers. You can now edit and apply the following fields directly inside Raw requests:

- `Referer: https://xxx.com`
- `User-Agent: xxx`
- `Origin: https://xxx.com`
- `X-Forwarded-For: x.x.x.x`

This feature is useful for common scenarios such as referer validation bypass, User-Agent verification, forged origins, and CTF Referer bypass techniques. Users can directly modify request headers in Raw mode and replay them, with behavior designed to closely resemble the replay experience of Burp Suite.

### 2. Added AI Task Module

A brand-new standalone AI Task Module has been introduced to automate the workflow of traffic capture, request analysis, vulnerability testing, and report generation.

The AI Task Module currently supports two modes:

- **Intelligent Penetration Mode**
  Designed for standard Web security testing scenarios. Based on the target site, historical traffic, and page context, the AI can automatically perform information gathering, entry-point analysis, attack modeling, vulnerability probing, and result evaluation.
  
<img width="3912" height="2070" alt="a7d48640ee2e4fed8032b4cf48229b23" src="https://github.com/user-attachments/assets/707007d2-7dc9-48c2-8981-8e7732219690" />

- **CTF Capture-the-Flag Mode**
  Designed for Web-based CTF challenges. The AI automatically plans solving strategies around challenge entry points, hints, response behaviors, and suspicious parameters. It attempts to construct exploitation requests and generates a post-analysis report after successfully capturing the Flag.

  <img width="3912" height="2070" alt="27e66bc42b733225d16ceccd9e78eed7" src="https://github.com/user-attachments/assets/a00c9dc2-8203-4a2a-aadd-ee32971d0138" />

The AI Task module records execution, evidence, key payloads, Flag hits, and final reports; while **running**, use toolbar **Supplementary hints** to **queue** context for later turns **without replacing** the pre-launch brief. The underlying **multi-stage adaptive orchestration** is continuously hardened (tool chain, budgets, readability). See in-product User Manual §8.

### 3. Interception Mode Is Now Available in the Community Edition

Interception Mode is now officially available for Community Edition users (**HTTP** and **WebSocket frames** when rules match).

Community Edition users can now pause, inspect, modify, and forward requests through Interception Mode, making manual testing, parameter debugging, and request verification much more convenient.

<img width="1956" height="1035" alt="image" src="https://github.com/user-attachments/assets/6154a019-fbbe-45d6-bbbf-3b68227db08b" />

### 4. WebSocket Capture, Replay, Micro Fuzz, and Intercept

Enable **WebSocket** under capture types, then filter by type in the sidebar; handshakes often show as `GET 101`, frames as **`WS`** (**`OUT`** / **`IN`**). **Frame replay** shares the HTTP workbench and needs an **`OPEN`** page socket; **`§...§` + Micro Fuzz** uses the next inbound frame as the response. **Intercept** supports **per-frame** edit/forward/drop. Scope is page-created WebSockets inside the browser—not a system MITM. Details: User Manual §5.

<img width="1548" height="942" alt="image" src="https://github.com/user-attachments/assets/28b7a2de-26cc-41b5-9f58-9a9b262ff45c" />

### 5. AI Tasks: In-Task Supplementary Hints

While a task **runs**, expand **Supplementary hints**, enter newly noticed parameters, reflections, paths, or CTF hints, and **Submit**; entries are **queued** with timestamps and appended as **runtime user supplementary hints** for later model turns, with per-turn and queue size caps. **Do not** paste real secrets; redaction and authorization rules match the full AI workflow.

<img width="1548" height="942" alt="image" src="https://github.com/user-attachments/assets/6634413a-4d35-4e2f-b286-5c7a88c29c84" />
<img width="1548" height="942" alt="image" src="https://github.com/user-attachments/assets/c40d4f83-6d44-46a6-b8e3-d170f274c2f7" />

### 6. AI Tasks: Orchestration and Execution Improvements

The **AI Task Console** multi-stage adaptive pipeline is tightened: **multi-turn agent** loops with real HTTP evidence, **structured runtime memory** (including failure memory aligned with sidebar metrics), and **protocol checks / replanning** for steadier stages and CTF early-finalize paths.

