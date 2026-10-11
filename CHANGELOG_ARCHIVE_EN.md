# Release archive: 1.0.1–1.0.6

[Back to 1.0.7](./README_EN.md)

> Preserved from the official historical README, including original images. Refer to the 1.0.7 main page for current editions, installation and behavior.

## 13. 1.0.1 Changelog

> The v1.0.1–v1.0.5 sections record their original releases. For current behavior and edition boundaries, use the v1.0.6 (0930) guidance on this page.

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

The AI Task module records execution, evidence, key payloads, Flag hits, and final reports; while **running**, use toolbar **Supplementary hints** to **queue** context for later turns **without replacing** the pre-launch brief. The underlying **multi-stage adaptive orchestration** is continuously hardened (tool chain, budgets, readability). See in-product User Manual §10.

### 3. Interception Mode Is Now Available in the Community Edition

Interception Mode is now officially available for Community Edition users (**HTTP** and **WebSocket frames** when rules match).

Community Edition users can now pause, inspect, modify, and forward requests through Interception Mode, making manual testing, parameter debugging, and request verification much more convenient.

<img width="1956" height="1035" alt="image" src="https://github.com/user-attachments/assets/6154a019-fbbe-45d6-bbbf-3b68227db08b" />

### 4. WebSocket Capture, Replay, Micro Fuzz, and Intercept

Enable **WebSocket** under capture types, then filter by type in the sidebar; handshakes often show as `GET 101`, frames as **`WS`** (**`OUT`** / **`IN`**). **Frame replay** shares the HTTP workbench and needs an **`OPEN`** page socket; **`§...§` + Micro Fuzz** uses the next inbound frame as the response. **Intercept** supports **per-frame** edit/forward/drop. Scope is page-created WebSockets inside the browser—not a system MITM. Details: User Manual §5.

<img width="1548" height="942" alt="image" src="https://github.com/user-attachments/assets/d7a6f0fa-4894-4e30-a729-2c962aad194a" />

### 5. AI Tasks: In-Task Supplementary Hints

While a task **runs**, expand **Supplementary hints**, enter newly noticed parameters, reflections, paths, or CTF hints, and **Submit**; entries are **queued** with timestamps and appended as **runtime user supplementary hints** for later model turns, with per-turn and queue size caps. **Do not** paste real secrets; redaction and authorization rules match the full AI workflow.

<img width="1548" height="942" alt="image" src="https://github.com/user-attachments/assets/6634413a-4d35-4e2f-b286-5c7a88c29c84" />
<img width="1548" height="942" alt="image" src="https://github.com/user-attachments/assets/c40d4f83-6d44-46a6-b8e3-d170f274c2f7" />

### 6. AI Tasks: Orchestration and Execution Improvements

The **AI Task Console** multi-stage adaptive pipeline is tightened: **multi-turn agent** loops with real HTTP evidence, **structured runtime memory** (including failure memory aligned with sidebar metrics), and **protocol checks / replanning** for steadier stages and CTF early-finalize paths.

---

## 15. 1.0.3 Changelog

This `v1.0.3` release brings three main updates:

### 1. AI Tasks Support Skills Loading (Pro)

The **AI Task Console** can inject built-in **penetration / CTF knowledge bases**, or **import external SKILL.md files and skill folders** from Advanced Settings. Pick libraries and submodules in the task panel—they are injected as context to support multi-stage automated testing and triage.

<img width="438" height="575" alt="image" src="https://github.com/user-attachments/assets/82d7170f-cd6b-4e38-9b78-49a788af2b3a" />

<img width="1956" height="1040" alt="image" src="https://github.com/user-attachments/assets/9f970717-f7df-4dc6-910f-74c70b989cad" />


### 2. Capture & Intercept Experience Improvements

Smoother **capture / intercept** workflows in the sidebar: cleaner filtering and scope switching, easier list browsing, and more fluid edit/forward actions for day-to-day debugging and manual testing.

### 3. Online Activation Added

**Single-click** the popup **status badge** to open Software activation with a new **Online** tab for subscription or lifetime membership. Benefits sync online and are **cached locally**, so Pro features continue offline while the cache/subscription remains valid—alongside the existing **offline activation code** path for easier checkout and renewal.

<img width="438" height="575" alt="image" src="https://github.com/user-attachments/assets/e2a80834-6d66-4ffa-bcf3-8151b322de59" />

---

## 16. 1.0.4 Changelog

This `v1.0.4` release brings four main updates:

### 1. Tampermonkey Scripts + Page Script Workspace (Pro)

Import `.user.js` userscripts and manage them in the sidebar with one-click inject. AI can create or optimize scripts from traffic and tie them into capture, replay, and sensitive scanning. Human-written scripts, AI-written scripts, and AI-orchestrated scripts share one workflow.

<img width="3046" height="1688" alt="041bc1f31c42a9d53fedf9c92b972b9a" src="https://github.com/user-attachments/assets/067a5dab-9e00-4cd9-a964-012d5733f8d5" />

<img width="3096" height="1882" alt="f48bb626b893c2efe11b0cdf9c8e69b9" src="https://github.com/user-attachments/assets/1e805ed7-b7ab-4fc8-a6b3-a9e779ce5507" />


### 2. AI Task Smart Script Dispatch (Pro)

Enable **Smart Script Dispatch** so AI tasks can list, run, or create page scripts during pentest / CTF—pull page-side intelligence back, then continue replay verification and reporting.

### 3. Capture / Intercept Reliability

More stable intercept for local labs and self-signed HTTPS; fixes regressions such as empty intercept queues; packet editor now accepts Chinese input correctly.

### 4. Firefox Stability and Cross-Browser Alignment

Fixes Firefox capture, sidebar, intercept, replay, and script injection; daily experience is further aligned across Chrome and Firefox.

> See `1.0.4更新说明` in the repo for the full release notes.

---

## 17. 1.0.5 Changelog

This `v1.0.5` release brings four main updates:

### 1. AI Task Console Overhaul (Core Release)

Execution log redesigned as a **timeline card stream** (color-coded stage / AI / test / tool-call cards; expandable tool JSON); **draggable split** between log and report; **task background AI understanding** before launch; reports include **vulnerability inventory + request/response evidence**; built-in `crypto.logic.analyze` and `codec.transform` for advanced crypto workflows.

<img width="1526" height="891" alt="image" src="https://github.com/user-attachments/assets/a1e25ad7-7aa1-4b01-a42f-adec0a4dbcc6" />

### 2. Thicker Skills Library + AI Generate Skill

Built-in sub-modules expanded to **19 pentest + 28 CTF**; **Smart Enable** toggle per main Skill; **AI Generate Skill** in Advanced Settings—create a single skill or collection and save as standalone Skill, built-in sub-module, or append to an imported skill.

<img width="2084" height="1700" alt="ac1eb01ce372ddf86b80d79ce4ac610b" src="https://github.com/user-attachments/assets/889cea2a-0751-434b-bab7-d2ff84bf4a0e" />

<img width="450" height="570" alt="a9c5841467cee3adc1a220001c27b2b5" src="https://github.com/user-attachments/assets/15b6d6a5-8718-4442-a8d1-6a4a71be5a6a" />

<img width="450" height="570" alt="image" src="https://github.com/user-attachments/assets/68b436cd-5b20-466a-b425-dd7bb22750ed" />


### 3. Codec Capabilities Completed

Replay workbench adds **AES / DES / RSA / SM** and smart nested decode; built-in **Smart Decode Assistant** (enabled by default): select text on any page for common decode and hash hints; advanced AES / nested chains still go through replay or inline packet codec.

<img width="1024" height="523" alt="image" src="https://github.com/user-attachments/assets/c0ffab9d-2de8-4e67-8d24-2f24dc5250e9" />


### 4. UX Improvements and Bug Fixes

Fixed various Chrome / Firefox system issues; better coordination among intercept / debug mode / passive listening toggles; improved sidebar and settings copy; user manual updated to **v1.0.5**.

---

## 18. v1.0.6 changelog

### 1. HawkEye Browser Automation MCP (PRO)

HawkEye now exposes a security-oriented browser MCP, positioned like a security-specialized Playwright MCP. MCP-capable Agent Hosts such as Codex, Cursor, and LM Studio connect to `hx0-hawkeye`; the Host model can then autonomously call `browser_navigate`, `browser_type`, `browser_snapshot`, and HawkEye capture, replay, mutation, codec, TLS, sensitive-data, and evidence tools in the real browser. The loopback-only server supports stdio, Streamable HTTP, and legacy SSE and requires the user to enable the extension bridge. This capability is separate from the in-extension AI Task Console.

<img width="1800" height="1382" alt="Codex, Cursor, or LM Studio controlling the browser through HawkEye MCP" src="https://github.com/user-attachments/assets/ff0c2671-6559-4f38-b6f5-2a6a50c5375a" />

### 2. Browser-level Agent (PRO)

Agent Mode requires an active trial or Professional license. It starts from the user's real current HTTP(S) tab and supports multi-turn planning, approval modes, complex controls / iframe / Shadow DOM interaction, visual screenshots, attachments, traffic analysis, replay, codecs, autonomous public-web research, native downloads, durable long-context memory, and expandable tool evidence.

<img width="1500" height="900" alt="v1.0.6 Browser-level Agent" src="https://github.com/user-attachments/assets/b9491db0-727c-4a09-8020-0f87abd97efe" />

### 3. Extreme performance and low resource use

Firefox no longer keeps passive capture listeners alive unnecessarily: `webRequest` listeners exist only while their feature state requires them. DOM snapshots, ref assignment, list rows, capture notifications, MutationObserver reuse, Agent transport, and MCP transport now use one-pass traversal, caches, batching, compact envelopes, and bounded pagination. Large results remain resumable through `next_cursor`, preserving evidence while reducing transfer and memory cost.

### 4. Default-off Skills and a strict allowlist

The 19 pentest and 28 CTF built-in sub-modules now include the v1.0.6 runtime contract. Skills are off in new Agent conversations. Both Advanced Settings enablement and the current conversation's Skills control must be on; otherwise Skill bodies never enter model context and Agent cannot bypass the user's selection.

### 5. Community capabilities opened since v1.0.5

Smart Proxy Router, Full Deep Search, and Sensitive Information Matching (built-in rules, custom regex, keyword libraries, and batch import/export) are available in Community starting with v1.0.6. AI Tasks, AI Skills, browser-level Agent, and HawkEye MCP remain Professional features.

### 6. 0930 capture and interaction improvements

- Capture history distinguishes current domain, current tab, and all records. Cross-subdomain requests remain visible under the originating tab. Intercept queues refresh automatically, and missing original request or response bodies show diagnostics.
- Replay opens in Pretty by default; edits in Pretty or Raw are sent. WebSocket frames, batch replay, AI analysis, and dark-link results have clearer feedback.
- Settings delete confirmations use in-extension dialogs. Firefox shortcut buttons match Chrome; English persona content updates when switching language, and dark-link settings remain scrollable in short popups and rule names wrap. Pending Agent approvals can be reopened from the waiting indicator, while backdrop and Escape no longer dismiss the approval dialog.
- Local MCP Server 1.0.13 improves setup and connection diagnostics. Extension scripts in the official Chrome and Firefox ZIPs are obfuscated.
