# Viết Chuyên Nghiệp v3.0 — Kiến Trúc Tòa Soạn

> Multi-Agent Content Production System cho AI  
> Version: 3.0 | Date: 2026-03-10 | Architecture: Tòa Soạn

---

## 🎯 Tổng Quan

**Viết Chuyên Nghiệp** là skill AI sản xuất nội dung tiếng Việt chuyên nghiệp, 
hoạt động theo mô hình **Tòa Soạn** — Tổng Biên Tập điều phối **6 Ban** 
với **25 biên tập viên (BTV)** chuyên biệt + 4 engines tự động + 45+ knowledge files.

```
AI viết tiếng Việt thường → "Trong thế giới ngày nay..." + "Hơn nữa..." 
Skill này fix → viết tự nhiên, có data, anti-AI score ≤ 40
```

---

## 🏗️ Kiến Trúc v3.0

```
TỔNG BIÊN TẬP (SKILL.md)
│
├─ 📝 Ban Thu Thập (content/)     — 3 BTV
│  Bóc brief, nghiên cứu 5 lớp, phân tích audience/angle
│
├─ ✍️ Ban Biên Tập (style/)       — 6 BTV
│  Cốt truyện, nhịp văn, tường thuật, trình bày, học thuật
│
├─ 🔍 Ban Kiểm Duyệt (quality/)  — 7 BTV
│  Dấu câu, viết hoa, tự nhiên, anti-AI, fact-check, nhất quán
│  → PASS / REVISE / REJECT
│
├─ 📱 Ban Xuất Bản (platform/)    — 5 BTV
│  Facebook VN, TikTok Gen Z, LinkedIn B2B, Video Script
│
├─ 📚 Ban Tư Liệu (examples/)    — Thư viện bài mẫu
│
└─ 🔧 Ban Phát Triển (meta/)      — 3 agents
   Self-improve, audit, nâng cấp hệ thống
```

### Pipeline Chính

```
content/ → style/ → quality/ → platform/ → User
                       │
                       ├─ PASS → tiếp tục
                       ├─ REVISE → quay lại style/ (tối đa 2 lần)
                       └─ REJECT → quay lại content/
```

---

## 📋 Capabilities

| Pipeline | Input | Output | Các Ban |
|----------|-------|--------|---------|
| **write-new** | Brief/topic | Blog, ebook, social, video script | content → style → quality → platform |
| **edit-draft** | Draft text | Polished version | content → style → quality |
| **deep-research** | Topic/question | Research report | content → quality |
| **critique-content** | Content to review | Critique report | content → quality |
| **grade-content** | Content to score | Rubric scorecard | content → quality |
| **publish-ready** | Final draft | Verified output | quality → platform |

---

## 🚀 Cách Sử Dụng

```
# Viết bài blog mới
"Viết bài blog 1200 từ về xu hướng AI cho CEO doanh nghiệp VN"

# Chấm điểm bài viết
"Chấm bài này theo thang 100 điểm: [paste bài]"

# Phản biện nội dung
"Phân tích logic + evidence của bài viết này: [paste bài]"

# Viết kịch bản video
"Viết script TikTok 60s về 3 sai lầm khi dùng ChatGPT"

# Chuyển thể → social
"Chuyển bài blog này thành 3 post Facebook + 2 LinkedIn"
```

---

## 📁 Cấu Trúc Thư mục

```
Viet-chuyen-nghiep/
├── SKILL.md                    # Entry point — Tổng Biên Tập
├── workforce-config.json       # Config v3.0
├── README.md                   # ← File này
│
├── Ban/                        # 6 BAN CHUYÊN MÔN (v3.0)
│   ├── content/   (3 files)    # Thu thập & nghiên cứu
│   ├── style/     (6 files)    # Biên tập phong cách
│   ├── quality/   (7 files)    # Kiểm duyệt
│   ├── platform/  (5 files)    # Xuất bản đa nền tảng
│   ├── examples/  (1 file)     # Thư viện bài mẫu
│   └── meta/      (3 files)    # Phát triển & audit
│
├── Orchestrator/               # Điều phối trung tâm
│   ├── editor-in-chief.md      # Vai trò Tổng BT
│   ├── routing-matrix.md       # Ma trận routing
│   ├── interface-contract.md   # YAML schema giữa Ban
│   ├── delegation-protocol.md  
│   └── escalation-rules.md     
│
├── Team-Orchestration/         # 6 pipeline definitions
│
├── Autonomous-Core/            # 4 engines tự động
│
├── Context-Layer/              # 45+ knowledge files
│   ├── CoreModules/            # Quy tắc lõi
│   ├── Knowledge-Base/         # Kiến thức chuyên sâu
│   ├── Second-Brain/           # Kinh nghiệm tích lũy
│   └── Memory/                 # Session memory
│
├── Workers/   ⚠️ LEGACY        # v2.0 — xem DEPRECATED.md
└── SubAgents/ ⚠️ LEGACY        # v2.0 — xem DEPRECATED.md
```

---

## 🔑 Điểm Khác Biệt

1. **Kiến Trúc Tòa Soạn** → 6 Ban chuyên biệt thay vì workers chung
2. **Ban Biên Tập** → 6 BTV phong cách (storytelling, rhythm, narrative...)
3. **Ban Kiểm Duyệt** → 7 BTV granular (dấu câu, viết hoa, anti-AI...)
4. **Anti-AI Engine** → 15 dấu hiệu, thang A-D, target ≤ 30%
5. **100-point Rubric** → chấm điểm 6 tiêu chí weighted
6. **Self-Improve** → Ban Phát Triển tự audit, nâng cấp hệ thống
7. **Interface Contract** → YAML schema chuẩn giữa các Ban

---

## 📖 Tham khảo

- Entry point: [`SKILL.md`](./SKILL.md)
- Hướng dẫn: [`HUONG-DAN-SU-DUNG.md`](./HUONG-DAN-SU-DUNG.md)
- Config: [`workforce-config.json`](./workforce-config.json)
