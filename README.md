<div align="center">

<img src="https://img.shields.io/badge/AI-Writing_Engine-FF6B6B?style=for-the-badge&logo=openai&logoColor=white" /> <img src="https://img.shields.io/badge/Architecture-Tòa_Soạn-7C3AED?style=for-the-badge&logo=buildkite&logoColor=white" /> <img src="https://img.shields.io/badge/Language-Tiếng_Việt-E11D48?style=for-the-badge&logo=googletranslate&logoColor=white" />

# ✍️ VIẾT CHUYÊN NGHIỆP `v3.2`

### Kiến Trúc Tòa Soạn AI — Vietnamese Professional Writing Engine

> *Không phải chatbot. Đây là một **tòa soạn báo** vận hành bên trong AI.*

**6 Ban** · **31 Biên Tập Viên** · **8 Workers** · **16 Pipelines** · **1 Orchestrator**

[![Version](https://img.shields.io/badge/v3.2.0-stable-00C853?style=flat-square&logo=semanticrelease)](.)
[![License](https://img.shields.io/badge/license-MIT-blue?style=flat-square)](LICENSE)
[![Made in](https://img.shields.io/badge/Made_in-Vietnam_🇻🇳-E11D48?style=flat-square)](.)
[![Powered by](https://img.shields.io/badge/Powered_by-Antigravity-7C3AED?style=flat-square&logo=atom&logoColor=white)](.)

</div>

---

## 🆕 What's New in v3.2

> **5 pipeline mới** tích hợp từ `novel-writer.md` — mở rộng năng lực sáng tạo nội dung từ fiction, giáo dục, nghiên cứu đến social đa nền tảng.

| Pipeline mới | Mô tả | Điểm nổi bật |
|:-------------|:-------|:--------------|
| 🎭 `write-fiction` | Viết truyện fiction | 8 thể loại, 7+1 agent, QA **130 điểm** |
| 📖 `write-edu` | Tài liệu học tập | Bloom's Taxonomy, ADDIE model |
| 🎤 `write-slide` | Slide thuyết trình | Narrative arc, ≤7 từ/title, speaker notes |
| 🔬 `write-research` | Tài liệu nghiên cứu | White paper, policy brief, 5-tier source |
| 🌐 `write-social` | Social đa nền tảng | 6 platforms + cross-platform repurposing |

**+4 Workers mới:** `edu-worker` · `slide-worker` · `research-writer-worker` · `social-writer-worker`

---

## 🧬 Tại sao Tòa Soạn, không phải Chatbot?

> *"Một chatbot viết bài — giống một người làm tất cả. Kết quả? Tạm được.*
> *Nhưng tòa soạn — mỗi người một vai — mới tạo ra xuất sắc."*

```mermaid
graph LR
    subgraph OLD["❌ Chatbot Truyền Thống"]
        A["1 prompt → 1 output"] --> B["Chấp nhận kết quả"]
    end
    subgraph NEW["✅ Viết Chuyên Nghiệp"]
        C["Brief"] --> D["Research"]
        D --> E["Viết"]
        E --> F["Biên tập"]
        F --> G["QC 7 Gate"]
        G -->|PASS| H["Xuất bản 10 nền tảng"]
        G -->|REVISE| F
    end

    style OLD fill:#fee2e2,stroke:#ef4444,color:#000
    style NEW fill:#dcfce7,stroke:#22c55e,color:#000
    style A fill:#fecaca,stroke:#ef4444,color:#000
    style B fill:#fecaca,stroke:#ef4444,color:#000
    style C fill:#dbeafe,stroke:#3b82f6,color:#000
    style D fill:#dbeafe,stroke:#3b82f6,color:#000
    style E fill:#dbeafe,stroke:#3b82f6,color:#000
    style F fill:#e9d5ff,stroke:#8b5cf6,color:#000
    style G fill:#bbf7d0,stroke:#22c55e,color:#000
    style H fill:#fef9c3,stroke:#eab308,color:#000
```

| Thế giới thật | Viết Chuyên Nghiệp |
|:---|:---|
| Phóng viên đi thực địa | **Ban Thu Thập** — research trước khi viết |
| Biên tập viên chỉnh sửa | **Ban Biên Tập** — 8 BTV chuyên biệt |
| Tổng biên tập duyệt bài | **Ban Kiểm Duyệt** — 7 gate kiểm tra |
| Trưởng ban phát hành | **Ban Xuất Bản** — tối ưu cho 10 nền tảng |
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

# 🎭 Viết truyện fiction ★ NEW
/viet-pro viết truyện "Đô thị tu tiên — nhân vật chính dân IT"

# 🎤 Tạo slide thuyết trình ★ NEW
/viet-pro tạo slide "AI trong doanh nghiệp — hội nghị VN 2026"

# 🔬 Viết white paper ★ NEW
/viet-pro viết nghiên cứu "Xu hướng ESG tại Việt Nam 2026"

# 🌐 Content đa nền tảng ★ NEW
/viet-pro viết social "Repurpose bài gốc → Facebook, LinkedIn, TikTok, Twitter"

# 📖 Tài liệu học tập ★ NEW
/viet-pro viết tài liệu học tập "Handout quản lý rủi ro"
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
        B1["📰 Thu Thập<br/>3 BTV"]
        B2["✒️ Biên Tập<br/>8 BTV"]
        B3["🔍 Kiểm Duyệt<br/>7 BTV"]
        B4["📡 Xuất Bản<br/>9 BTV"]
        B5["📚 Tư Liệu"]
        B6["🔬 Phát Triển<br/>3 Agents"]
    end

    B1 --> B2 --> B3
    B3 -->|PASS| B4
    B3 -->|REVISE| B2

    BAN --> WKR

    subgraph WKR["⚙️ WORKER LAYER — 8 Specialists ★ v3.2"]
        direction LR
        W1["email"]
        W2["curriculum"]
        W3["guide"]
        W4["merge"]
        W5["edu ★"]
        W6["slide ★"]
        W7["research ★"]
        W8["social ★"]
    end

    WKR --> SE["📊 Scoring Engine<br/>Grade 0-100 / 130"]
    SE --> SM["🔄 State Manager<br/>Max 2 Revisions"]
    SM --> OUTPUT["✅ Final Output"]

    style USER fill:#dbeafe,stroke:#3b82f6,color:#000
    style ORC fill:#ede9fe,stroke:#8b5cf6,color:#000
    style BAN fill:#dcfce7,stroke:#22c55e,color:#000
    style WKR fill:#fef9c3,stroke:#eab308,color:#000
    style OUTPUT fill:#bbf7d0,stroke:#16a34a,color:#000
    style SE fill:#fce7f3,stroke:#ec4899,color:#000
    style SM fill:#fce7f3,stroke:#ec4899,color:#000
```

---

## 🎯 6 Ban — 31 Biên Tập Viên

```mermaid
mindmap
  root((🏛️ Tòa Soạn v3.2))
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

## 🔄 16 Pipelines

```mermaid
flowchart LR
    subgraph CORE["Core Pipelines"]
        P1["✍️ write-new"]
        P2["🔧 edit-draft"]
        P3["📊 grade-content"]
        P4["🎯 critique-content"]
        P5["🔬 deep-research"]
    end

    subgraph SPECIALIZED["Specialized v3.1"]
        P6["📡 publish-ready"]
        P7["♻️ repurpose"]
        P8["📧 write-email"]
        P9["📚 write-curriculum"]
        P10["📖 write-guide"]
        P11["🔗 merge-output"]
    end

    subgraph NEW32["★ NEW v3.2"]
        P12["🎭 write-fiction"]
        P13["📖 write-edu"]
        P14["🎤 write-slide"]
        P15["🔬 write-research"]
        P16["🌐 write-social"]
    end

    P1 --> FLOW1["content → style → quality → platform"]
    P2 --> FLOW2["content → style → quality"]
    P3 --> FLOW3["content → quality"]
    P12 --> FLOW5["content → style → quality 130đ → platform"]
    P16 --> FLOW6["content → social-worker → quality → multi-platform"]

    style CORE fill:#dbeafe,stroke:#3b82f6,color:#000
    style SPECIALIZED fill:#ede9fe,stroke:#8b5cf6,color:#000
    style NEW32 fill:#fef9c3,stroke:#eab308,color:#000
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
| **`write-fiction`** ★ | Viết truyện fiction (8 thể loại) | content → style → quality **130đ** → platform |
| **`write-edu`** ★ | Tài liệu học tập (handout, quiz) | content → style → edu-worker → quality → platform |
| **`write-slide`** ★ | Slide thuyết trình | content → style → slide-worker → quality → platform |
| **`write-research`** ★ | Nghiên cứu (white paper, policy brief) | content → research-worker → quality → platform |
| **`write-social`** ★ | Social đa nền tảng + repurpose | content → social-worker → quality → multi-platform |

---

## ⚙️ 8 Workers — Chuyên Gia Thực Thi

> *Workers bổ sung templates và execution frameworks cho BTV. Workers KHÔNG thay thế BTV — Pipeline gọi BTV trước → Worker bổ sung.*

| Worker | Chức năng | Từ version |
|:-------|:----------|:-----------|
| `email-worker` | Templates email B2B, nurture, cold outreach | v3.1 |
| `curriculum-worker` | Bloom's Taxonomy, ADDIE, module design | v3.1 |
| `guide-worker` | SOP structure, troubleshooting, RACI | v3.1 |
| `merge-worker` | File concatenation, encoding verify | v3.1 |
| **`edu-worker`** ★ | Handout, workbook, quiz, lesson plan | **v3.2** |
| **`slide-worker`** ★ | Narrative arc, visual hierarchy, speaker notes | **v3.2** |
| **`research-writer-worker`** ★ | 5-tier source evaluation, citation check | **v3.2** |
| **`social-writer-worker`** ★ | 6 platforms, cross-platform repurposing | **v3.2** |

---

## 🎭 Spotlight: Fiction Pipeline (v3.2)

> *Pipeline sáng tạo mạnh nhất — 7+1 agent, QA 130 điểm, 8 thể loại.*

```mermaid
graph LR
    BRIEF["📝 Brief"] --> WB["🌍 World Builder"]
    WB --> PLOT["📐 Plot Architect"]
    PLOT --> WRITE["✍️ Prose Writer"]
    WRITE --> HUMAN["🧬 Humanizer<br/>12-layer"]
    HUMAN --> QA["🔍 QA 130đ<br/>8 + 3 trụ"]
    QA -->|PASS| PUB["📡 Publisher"]
    QA -->|REVISE| WRITE
    PUB --> ED["✒️ Continuity Editor"]

    style BRIEF fill:#dbeafe,stroke:#3b82f6,color:#000
    style WB fill:#e9d5ff,stroke:#8b5cf6,color:#000
    style PLOT fill:#e9d5ff,stroke:#8b5cf6,color:#000
    style WRITE fill:#fef9c3,stroke:#eab308,color:#000
    style HUMAN fill:#fce7f3,stroke:#ec4899,color:#000
    style QA fill:#bbf7d0,stroke:#22c55e,color:#000
    style PUB fill:#fef9c3,stroke:#eab308,color:#000
    style ED fill:#e9d5ff,stroke:#8b5cf6,color:#000
```

**8 thể loại:** Tiên hiệp · Đô thị · Ngôn tình · Huyền huyễn · Khoa huyễn · Kinh dị · Trinh thám · Lịch sử

---

## 🧠 Autonomous Core — 4 Engine

```mermaid
graph LR
    TC["🎯 Task Classifier<br/>Auto-detect pipeline"] --> WE["🔀 Workflow Engine<br/>Route to correct Ban"]
    WE --> SE["📊 Scoring Engine<br/>Grade 0-100 / 130"]
    SE --> SM["🔄 State Manager<br/>Track revisions, max 2 loops"]

    style TC fill:#e9d5ff,stroke:#8b5cf6,color:#000
    style WE fill:#dbeafe,stroke:#3b82f6,color:#000
    style SE fill:#fce7f3,stroke:#ec4899,color:#000
    style SM fill:#bbf7d0,stroke:#22c55e,color:#000
```

- **Task Classifier** — Tự nhận diện loại task, không cần user chỉ định pipeline
- **Workflow Engine** — Route đúng Ban theo routing matrix
- **Scoring Engine** — Chấm 6 chiều (100đ) hoặc 11 trụ (130đ cho fiction)
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

    P1 --> FIX["✅ Auto-Fix — Thay bằng văn phong tự nhiên"]
    P2 --> FIX
    P3 --> FIX
    P4 --> FIX
    P5 --> FIX

    style INPUT fill:#fecaca,stroke:#ef4444,color:#000
    style SCAN fill:#e9d5ff,stroke:#8b5cf6,color:#000
    style FIX fill:#bbf7d0,stroke:#22c55e,color:#000
    style P1 fill:#fef9c3,stroke:#eab308,color:#000
    style P2 fill:#fef9c3,stroke:#eab308,color:#000
    style P3 fill:#fef9c3,stroke:#eab308,color:#000
    style P4 fill:#fef9c3,stroke:#eab308,color:#000
    style P5 fill:#fef9c3,stroke:#eab308,color:#000
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
├── ⚙️ Workers/                    # 8 Execution Workers ★ v3.2
│   ├── email-worker.md
│   ├── curriculum-worker.md
│   ├── guide-worker.md
│   ├── merge-worker.md
│   ├── edu-worker.md              # ★ NEW
│   ├── slide-worker.md            # ★ NEW
│   ├── research-writer-worker.md  # ★ NEW
│   └── social-writer-worker.md    # ★ NEW
│
├── 🔄 Team-Orchestration/         # 16 Pipeline definitions
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

### 📊 Chấm Điểm 100 / 130
Rubric 6 chiều cho non-fiction (100đ). Rubric 11 trụ cho fiction (130đ) — bao gồm 8 trụ gốc + 3 trụ anti-AI chuyên biệt.

</td>
</tr>
<tr>
<td width="50%">

### 🔄 Revision Loop
Quality gate → `REVISE` → quay lại Ban Biên Tập → kiểm tra lại. Tối đa 2 vòng. Nếu `REJECT` → escalation lên Orchestrator.

</td>
<td width="50%">

### 📡 Multi-Platform Output
Một nội dung gốc → repurpose cho **10 nền tảng**: Facebook, TikTok, LinkedIn, Twitter/X, Video, Email, Zalo, Threads, Docs, Blog/SEO.

</td>
</tr>
<tr>
<td width="50%">

### 🎭 Fiction Engine ★ NEW
Viết truyện fiction 8 thể loại với QA 130 điểm: World Builder → Plot Architect → Prose Writer → 12-layer Humanizer → Continuity Editor.

</td>
<td width="50%">

### 🌐 Cross-Platform Social ★ NEW
Viết 1 bài gốc, tự động adapt cho 6+ nền tảng. KHÔNG translate — adapt native cho từng platform. Hashtag research trending + niche.

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

## 📊 Scoring Rubric — 6 Dimensions (Non-Fiction)

| Dimension | Weight | Description |
|:----------|:------:|:------------|
| **Content** | 25% | Depth, originality, value |
| **Structure** | 20% | Logic flow, hierarchy |
| **Style** | 15% | Tone, voice, readability |
| **Accuracy** | 20% | Facts, data, citations |
| **Anti-AI** | 10% | Natural language patterns |
| **Format** | 10% | Layout, visual hierarchy |

> **Fiction pipeline** dùng rubric 130 điểm riêng: 8 trụ gốc (storyline, character, world, prose...) + 3 trụ anti-AI.

---

## 📜 Changelog

Xem chi tiết tại [CHANGELOG.md](CHANGELOG.md).

| Version | Highlights |
|:--------|:-----------|
| **v3.2** ★ | +5 Pipelines (fiction/edu/slide/research/social), +4 Workers, Twitter/X support, 130đ Fiction QA |
| **v3.1** | +3 Workers (email/curriculum/guide), +Zalo/Threads BTV, merge-output pipeline |
| **v3.0** | Kiến Trúc Tòa Soạn — 6 Ban, 25→31 BTV, Autonomous Core |
| **v2.0** | Worker-based architecture, SubAgents |
| **v1.0** | Single-agent writing system |

---

## 🤝 Credits & Ecosystem

<div align="center">

```mermaid
graph LR
    VCP["✍️ Viết Chuyên Nghiệp v3.2"] --- AGV["⚛️ Antigravity Ecosystem"]
    AGV --- BMAD["📋 BMAD-METHOD v6"]
    AGV --- JARVIS["🤖 Jarvis Orchestrator"]
    AGV --- GOCLAW["🐺 GoClaw Platform"]

    style VCP fill:#e9d5ff,stroke:#8b5cf6,color:#000
    style AGV fill:#dbeafe,stroke:#3b82f6,color:#000
    style BMAD fill:#bbf7d0,stroke:#22c55e,color:#000
    style JARVIS fill:#fef9c3,stroke:#eab308,color:#000
    style GOCLAW fill:#fce7f3,stroke:#ec4899,color:#000
```

Được xây dựng bởi **[ABM](https://github.com/xaotiensinh-abm)** — AI Business Mastery

Powered by **Antigravity** ecosystem · **BMAD-METHOD** v6 · **Jarvis** Multi-Agent Orchestrator · **GoClaw** AI Gateway

</div>

---

<div align="center">

> *"Viết hay — không phải vì AI giỏi.*
> *Viết hay — vì có tòa soạn giỏi đứng sau AI."*

**Viết Chuyên Nghiệp v3.2** · Made with ❤️ in Vietnam 🇻🇳

</div>
