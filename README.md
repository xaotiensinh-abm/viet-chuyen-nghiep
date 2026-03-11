<div align="center">

<img src="https://img.shields.io/badge/AI-Writing_Engine-FF6B6B?style=for-the-badge&logo=openai&logoColor=white" /> <img src="https://img.shields.io/badge/Architecture-Tòa_Soạn-7C3AED?style=for-the-badge&logo=buildkite&logoColor=white" /> <img src="https://img.shields.io/badge/Language-Tiếng_Việt-E11D48?style=for-the-badge&logo=googletranslate&logoColor=white" />

# ✍️ VIẾT CHUYÊN NGHIỆP `v3.1`

### Kiến Trúc Tòa Soạn AI — Vietnamese Professional Writing Engine

> *Không phải chatbot. Đây là một **tòa soạn báo** vận hành bên trong AI.*

**6 Ban** · **31 Biên Tập Viên** · **13 Workers** · **11 Pipelines** · **1 Orchestrator**

[![Version](https://img.shields.io/badge/v3.1.0-stable-00C853?style=flat-square&logo=semanticrelease)](.)
[![License](https://img.shields.io/badge/license-MIT-blue?style=flat-square)](LICENSE)
[![Made in](https://img.shields.io/badge/Made_in-Vietnam_🇻🇳-E11D48?style=flat-square)](.)
[![Powered by](https://img.shields.io/badge/Powered_by-Antigravity-7C3AED?style=flat-square&logo=atom&logoColor=white)](.)

</div>

---

## 🧬 Tại sao Tòa Soạn, không phải Chatbot?

> *"Một chatbot viết bài — giống một người làm tất cả. Kết quả? Tạm được.*
> *Nhưng tòa soạn — mỗi người một vai — mới tạo ra xuất sắc."*

```mermaid
graph LR
    subgraph "❌ Chatbot Truyền Thống"
        A["1 prompt → 1 output"] --> B["Chấp nhận kết quả"]
    end
    subgraph "✅ Viết Chuyên Nghiệp"
        C["Brief"] --> D["Research"]
        D --> E["Viết"]
        E --> F["Biên tập"]
        F --> G["QC 7 Gate"]
        G -->|"PASS"| H["Xuất bản 9 nền tảng"]
        G -->|"REVISE"| F
    end

    style A fill:#1a1a2e,stroke:#e94560,color:#fff
    style B fill:#1a1a2e,stroke:#e94560,color:#fff
    style C fill:#0f3460,stroke:#00d2ff,color:#fff
    style D fill:#0f3460,stroke:#00d2ff,color:#fff
    style E fill:#0f3460,stroke:#00d2ff,color:#fff
    style F fill:#16213e,stroke:#7C3AED,color:#fff
    style G fill:#16213e,stroke:#00C853,color:#fff
    style H fill:#1a1a2e,stroke:#FFD700,color:#fff
```

| Thế giới thật | Viết Chuyên Nghiệp |
|:---|:---|
| Phóng viên đi thực địa | **Ban Thu Thập** — research trước khi viết |
| Biên tập viên chỉnh sửa | **Ban Biên Tập** — 8 BTV chuyên biệt |
| Tổng biên tập duyệt bài | **Ban Kiểm Duyệt** — 7 gate kiểm tra |
| Trưởng ban phát hành | **Ban Xuất Bản** — tối ưu cho 9 nền tảng |
| Phòng tư liệu | **Ban Tư Liệu** — thư viện bài mẫu |
| Ban phát triển | **Ban Phát Triển** — tự nâng cấp |

---

## ⚡ Quick Start — 30 Giây

```bash
# 🚀 Kích hoạt
/viet-pro

# ✍️ Viết mới
/viet-pro viết ebook "Hướng dẫn AI cho doanh nghiệp Việt Nam"

# 📊 Chấm bài (thang 100 điểm, rubric 6 chiều)
/viet-pro chấm bài article.md

# 🔧 Sửa bản nháp
/viet-pro sửa bài draft.md

# 🎯 Phản biện đa chiều
/viet-pro phản biện report.md

# 📚 Viết giáo trình E-learning
/viet-pro viết giáo trình "Module 3: Prompt Engineering"

# 📧 Viết email
/viet-pro viết email "Cold outreach cho CEO ngành F&B"
```

---

## 🏗️ Kiến Trúc Hệ Thống

```mermaid
graph TB
    USER["👤 User Input"] --> ORC

    subgraph ORC["🧠 ORCHESTRATOR LAYER"]
        TC["Task Classifier"] --> WE["Workflow Engine"]
        WE --> RM["Routing Matrix"]
    end

    RM --> BAN

    subgraph BAN["🏛️ BAN LAYER — 6 Ban · 31 BTV"]
        direction LR
        B1["📰 Thu Thập\n3 BTV"]
        B2["✒️ Biên Tập\n8 BTV"]
        B3["🔍 Kiểm Duyệt\n7 BTV"]
        B4["📡 Xuất Bản\n9 BTV"]
        B5["📚 Tư Liệu"]
        B6["🔬 Phát Triển\n3 Agents"]
    end

    B1 --> B2 --> B3
    B3 -->|"PASS"| B4
    B3 -->|"REVISE"| B2

    BAN --> WKR

    subgraph WKR["⚙️ WORKER LAYER — 13 Specialists"]
        direction LR
        W1["email"]
        W2["curriculum"]
        W3["guide"]
        W4["social"]
        W5["video"]
        W6["research"]
        W7["longform"]
        W8["merge"]
    end

    WKR --> SE["📊 Scoring Engine\nGrade 0-100"]
    SE --> SM["🔄 State Manager\nMax 2 Revisions"]
    SM --> OUTPUT["✅ Final Output"]

    style USER fill:#1a1a2e,stroke:#00d2ff,color:#fff
    style ORC fill:#0f3460,stroke:#7C3AED,color:#fff
    style BAN fill:#16213e,stroke:#00C853,color:#fff
    style WKR fill:#1a1a2e,stroke:#FFD700,color:#fff
    style OUTPUT fill:#0f3460,stroke:#00C853,color:#fff
    style SE fill:#16213e,stroke:#FF6B6B,color:#fff
    style SM fill:#16213e,stroke:#FF6B6B,color:#fff
```

---

## 🎯 6 Ban — 31 Biên Tập Viên

```mermaid
mindmap
  root((🏛️ Tòa Soạn))
    📰 Thu Thập
      lead-content
      research
      analysis
    ✒️ Biên Tập
      lead-style
      storytelling
      rhythm
      narrative
      presentation
      technical
      email
      curriculum
    🔍 Kiểm Duyệt
      lead-quality
      punctuation
      capitalization
      natural
      anti-ai
      fact-check
      consistency
    📡 Xuất Bản
      lead-platform
      facebook
      tiktok
      linkedin
      video
      email-platform
      zalo
      threads
      docs
    📚 Tư Liệu
      example library
    🔬 Phát Triển
      lead-meta
      upgrade
      style-audit
```

<details>
<summary><b>📰 Ban Thu Thập (Content)</b> — 3 BTV</summary>

| BTV | Chức năng |
|:----|:----------|
| `lead-content` | Trưởng ban — Bóc brief, xác định scope |
| `research` | Nghiên cứu sâu, thu thập nguồn |
| `analysis` | Phân tích dữ liệu, tổng hợp insight |

</details>

<details>
<summary><b>✒️ Ban Biên Tập (Style)</b> — 8 BTV</summary>

| BTV | Chức năng |
|:----|:----------|
| `lead-style` | Trưởng ban — Chọn tone, phân bổ BTV |
| `storytelling` | Kể chuyện, narrative arc |
| `rhythm` | Nhịp văn, câu ngắn/dài, tiết tấu |
| `narrative` | Cấu trúc bài viết dạng tường thuật |
| `presentation` | Format slide, bullets, visual hierarchy |
| `technical` | Văn phong kỹ thuật, chuyên ngành |
| `email` | Tone email: formal / casual / sales |
| `curriculum` | Cấu trúc bài giảng, module hóa |

</details>

<details>
<summary><b>🔍 Ban Kiểm Duyệt (Quality)</b> — 7 BTV</summary>

| BTV | Chức năng |
|:----|:----------|
| `lead-quality` | Trưởng ban — Tổng hợp 6 gate, ra quyết định |
| `punctuation` | Dấu câu, chính tả |
| `capitalization` | Viết hoa, viết thường chuẩn Việt |
| `natural` | Văn phong tự nhiên, tránh sáo rỗng |
| `anti-ai` | Phát hiện & loại bỏ dấu vết AI |
| `fact-check` | Kiểm chứng sự kiện, số liệu |
| `consistency` | Nhất quán thuật ngữ xuyên suốt |

**Quyết định:** `PASS` · `REVISE` (max 2 vòng) · `REJECT`

</details>

<details>
<summary><b>📡 Ban Xuất Bản (Platform)</b> — 9 BTV</summary>

| BTV | Nền tảng |
|:----|:---------|
| `lead-platform` | Trưởng ban — Chọn kênh, phân bổ |
| `facebook` | Facebook — hook, engagement, CTA |
| `tiktok` | TikTok — script ngắn, trending |
| `linkedin` | LinkedIn — thought leadership |
| `video` | Kịch bản video dạng dài |
| `email-platform` | Email marketing / B2B / nurture |
| `zalo` | Zalo OA — tone gần gũi, locale VN |
| `threads` | Threads — conversational |
| `docs` | User Guide / SOP / FAQ / Giáo trình |

</details>

<details>
<summary><b>📚 Ban Tư Liệu (Examples)</b></summary>

Thư viện bài mẫu đã qua quality gate — dùng làm reference cho các BTV.

</details>

<details>
<summary><b>🔬 Ban Phát Triển (Meta)</b> — 3 Agents</summary>

| Agent | Chức năng |
|:------|:----------|
| `lead-meta` | Trưởng ban — Điều phối nâng cấp |
| `upgrade` | Phân tích feedback, đề xuất cải tiến |
| `style-audit` | Audit style consistency toàn hệ thống |

</details>

---

## 🔄 11 Pipelines

```mermaid
flowchart LR
    subgraph CORE["Core Pipelines"]
        P1["✍️ write-new"]
        P2["🔧 edit-draft"]
        P3["📊 grade-content"]
        P4["🎯 critique-content"]
        P5["🔬 deep-research"]
    end

    subgraph SPECIALIZED["Specialized"]
        P6["📡 publish-ready"]
        P7["♻️ repurpose"]
        P8["📧 write-email"]
        P9["📚 write-curriculum"]
        P10["📖 write-guide"]
        P11["🔗 merge-output"]
    end

    P1 --> FLOW1["content → style → quality → platform"]
    P2 --> FLOW2["content → style → quality"]
    P3 --> FLOW3["content → quality"]
    P7 --> FLOW1
    P8 --> FLOW1
    P9 --> FLOW1
    P10 --> FLOW1
    P11 --> FLOW4["merge-worker → quality"]

    style CORE fill:#0f3460,stroke:#00d2ff,color:#fff
    style SPECIALIZED fill:#16213e,stroke:#7C3AED,color:#fff
```

| Pipeline | Mô tả | Luồng Ban |
|:---------|:-------|:----------|
| `write-new` | Viết mới từ đầu | content → style → quality → platform |
| `edit-draft` | Sửa bản nháp | content → style → quality |
| `grade-content` | Chấm bài thang 100 | content → quality |
| `critique-content` | Phản biện nội dung | content → quality |
| `deep-research` | Nghiên cứu chuyên sâu | content → quality |
| `publish-ready` | Chuẩn bị xuất bản | quality → platform |
| `repurpose` | Tái sử dụng nội dung | content → style → quality → platform |
| `write-email` | Viết email chuyên nghiệp | content → style → quality → platform |
| `write-curriculum` | Viết giáo trình | content → style → quality → platform |
| `write-guide` | Viết guide/SOP/FAQ | content → style → quality → platform |
| `merge-output` | Ghép file, verify encoding | merge-worker → quality |

---

## 🧠 Autonomous Core — 4 Engine

```mermaid
graph LR
    TC["🎯 Task Classifier\nAuto-detect pipeline"] --> WE["🔀 Workflow Engine\nRoute to correct Ban"]
    WE --> SE["📊 Scoring Engine\nGrade 0-100, 6 dimensions"]
    SE --> SM["🔄 State Manager\nTrack revisions, max 2 loops"]

    style TC fill:#7C3AED,stroke:#fff,color:#fff
    style WE fill:#0f3460,stroke:#00d2ff,color:#fff
    style SE fill:#E11D48,stroke:#fff,color:#fff
    style SM fill:#00C853,stroke:#fff,color:#fff
```

- **Task Classifier** — Tự nhận diện loại task, không cần user chỉ định pipeline
- **Workflow Engine** — Route đúng Ban theo routing matrix
- **Scoring Engine** — Chấm 6 chiều: `Content` · `Structure` · `Style` · `Accuracy` · `Anti-AI` · `Format`
- **State Manager** — Quản lý revision loop (max 2 vòng), escalation rules

---

## 🛡️ Anti-AI Detection Engine

> *Vấn đề lớn nhất của AI writing: đọc là biết AI viết.*

```mermaid
graph TD
    INPUT["📝 AI Draft"] --> SCAN["🔍 Anti-AI Scanner"]

    SCAN --> P1["Pattern: Mở đầu sáo rỗng"]
    SCAN --> P2["Pattern: Listing cân đối"]
    SCAN --> P3["Pattern: Kết bài template"]
    SCAN --> P4["Pattern: Zero opinion"]
    SCAN --> P5["Pattern: Lặp đại từ"]

    P1 --> FIX["✅ Auto-Fix\nThay bằng văn phong tự nhiên"]
    P2 --> FIX
    P3 --> FIX
    P4 --> FIX
    P5 --> FIX

    style INPUT fill:#1a1a2e,stroke:#e94560,color:#fff
    style SCAN fill:#7C3AED,stroke:#fff,color:#fff
    style FIX fill:#00C853,stroke:#fff,color:#fff
```

---

## 📂 Cấu Trúc Dự Án

```
viet-chuyen-nghiep/
│
├── 📄 SKILL.md                    # Skill definition (core brain)
├── 📄 viet-pro.md                 # Workflow trigger file
├── 📄 workforce-config.json       # Cấu hình toàn workforce
├── 📄 CHANGELOG.md                # Version history
│
├── 🏛️ Ban/                        # ══ 6 Ban chuyên môn ══
│   ├── content/                   #   📰 Thu Thập (3 BTV)
│   ├── style/                     #   ✒️ Biên Tập (8 BTV)
│   ├── quality/                   #   🔍 Kiểm Duyệt (7 BTV)
│   ├── platform/                  #   📡 Xuất Bản (9 BTV)
│   ├── examples/                  #   📚 Tư Liệu
│   └── meta/                      #   🔬 Phát Triển (3 Agents)
│
├── ⚙️ Workers/                    # 13 Execution Workers
├── 🔄 Team-Orchestration/         # 11 Pipeline definitions
├── 🧠 Autonomous-Core/            # 4 Engine files
├── 📖 Context-Layer/              # Knowledge Base
├── 🎯 Orchestrator/               # Routing matrix
├── 📝 Memory/                     # Session memory
├── 📚 docs/                       # Documentation
├── 🎬 output/                     # Generated content
└── 🔧 scripts/                    # Utility scripts
```

---

## 🎓 Tính Năng Nổi Bật

<table>
<tr>
<td width="50%">

### 🔬 Deep Research First
Mọi bài viết bắt đầu bằng nghiên cứu — không bao giờ viết "từ không khí." Ban Thu Thập research trước, phân tích insight, rồi mới chuyển sang Ban Biên Tập.

</td>
<td width="50%">

### 📊 Chấm Điểm 100
Rubric 6 chiều, trọng số rõ ràng. Không phải "bài này tốt" — mà **"bài này 87/100, mất điểm ở Anti-AI (82) và Structure (85)."**

</td>
</tr>
<tr>
<td width="50%">

### 🔄 Revision Loop
Quality gate → `REVISE` → quay lại Ban Biên Tập → kiểm tra lại. Tối đa 2 vòng. Nếu `REJECT` → escalation lên Orchestrator.

</td>
<td width="50%">

### 📡 Multi-Platform Output
Một nội dung gốc → repurpose cho **9 nền tảng**: Facebook, TikTok, LinkedIn, Video, Email, Zalo, Threads, Docs, Guide.

</td>
</tr>
<tr>
<td width="50%">

### 🧩 Modular & Extensible
Thêm Ban mới? Tạo folder + config. Thêm BTV? Drop file `.md`. Thêm pipeline? Tạo file trong `Team-Orchestration/`.

</td>
<td width="50%">

### 🛡️ Anti-AI Detection
BTV chuyên trách phát hiện & loại bỏ dấu vết AI. Bài viết đầu ra đọc như **con người viết** — không phải máy.

</td>
</tr>
</table>

---

## 📊 Scoring Rubric — 6 Dimensions

| Dimension | Weight | Description |
|:----------|:------:|:------------|
| **Content** | 25% | Depth, originality, value |
| **Structure** | 20% | Logic flow, hierarchy |
| **Style** | 15% | Tone, voice, readability |
| **Accuracy** | 20% | Facts, data, citations |
| **Anti-AI** | 10% | Natural language patterns |
| **Format** | 10% | Layout, visual hierarchy |

---

## 📜 Changelog

Xem chi tiết tại [CHANGELOG.md](CHANGELOG.md).

| Version | Highlights |
|:--------|:-----------|
| **v3.1** | +3 Workers (email/curriculum/guide), +Zalo/Threads BTV, merge-output pipeline |
| **v3.0** | Kiến Trúc Tòa Soạn — 6 Ban, 25→31 BTV, Autonomous Core |
| **v2.0** | Worker-based architecture, SubAgents |
| **v1.0** | Single-agent writing system |

---

## 🤝 Credits & Ecosystem

<div align="center">

```mermaid
graph LR
    VCP["✍️ Viết Chuyên Nghiệp\nv3.1"] --- AGV["⚛️ Antigravity\nEcosystem"]
    AGV --- BMAD["📋 BMAD-METHOD\nv6"]
    AGV --- JARVIS["🤖 Jarvis\nOrchestrator"]

    style VCP fill:#7C3AED,stroke:#fff,color:#fff
    style AGV fill:#0f3460,stroke:#00d2ff,color:#fff
    style BMAD fill:#00C853,stroke:#fff,color:#fff
    style JARVIS fill:#FFD700,stroke:#1a1a2e,color:#1a1a2e
```

Được xây dựng bởi **[ABM](https://github.com/xaotiensinh-abm)** — AI Business Mastery

Powered by **Antigravity** ecosystem · **BMAD-METHOD** v6 · **Jarvis** Multi-Agent Orchestrator

</div>

---

<div align="center">

> *"Viết hay — không phải vì AI giỏi.*
> *Viết hay — vì có tòa soạn giỏi đứng sau AI."*

**Viết Chuyên Nghiệp v3.1** · Made with ❤️ in Vietnam 🇻🇳

</div>
