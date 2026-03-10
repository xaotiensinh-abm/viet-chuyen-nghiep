# Hướng Dẫn Sử Dụng — Viết Chuyên Nghiệp v3.0 Kiến Trúc Tòa Soạn

## Giới thiệu

**Viết Chuyên Nghiệp** là skill AI viết nội dung tiếng Việt chuyên nghiệp, 
hoạt động theo mô hình **Tòa Soạn** — Tổng Biên Tập điều phối 6 Ban 
với 25 biên tập viên (BTV) chuyên biệt.

## Kiến trúc Tòa Soạn v3.0

```
TỔNG BIÊN TẬP (SKILL.md)
│
├─ 📝 BAN THU THẬP (content/)     — 3 BTV
│  Bóc brief, nghiên cứu 5 lớp, phân tích audience/angle
│
├─ ✍️ BAN BIÊN TẬP (style/)       — 6 BTV
│  Cốt truyện, nhịp văn, tường thuật, trình bày, học thuật
│
├─ 🔍 BAN KIỂM DUYỆT (quality/)  — 7 BTV
│  Dấu câu, viết hoa, tự nhiên, anti-AI, fact-check, nhất quán
│  → PASS / REVISE / REJECT
│
├─ 📱 BAN XUẤT BẢN (platform/)    — 5 BTV
│  Facebook VN, TikTok Gen Z, LinkedIn B2B, Video Script
│
├─ 📚 BAN TƯ LIỆU (examples/)    — Thư viện bài mẫu
│
└─ 🔧 BAN PHÁT TRIỂN (meta/)      — 3 agents
   Self-improve, audit, nâng cấp hệ thống
```

## Cách sử dụng

### Viết mới (ebook, tài liệu, content social, video script)
```
"Viết ebook về AI cho CEO, 5 chương"
"Viết 3 bài social (FB + TikTok + LinkedIn) về remote work"
"Viết kịch bản video 60s giới thiệu sản phẩm"
```
Pipeline: `content → style → quality → platform`

### Sửa bản nháp
```
"Sửa lại bài viết này cho tự nhiên hơn"
"Viết lại đoạn mở bài cho hấp dẫn"
```
Pipeline: `content (light) → style → quality`

### Chấm bài (thang 100 điểm)
```
"Chấm bài marketing này thang 100"
"Đánh giá bài viết của em"
```
Pipeline: `content (light) → quality (rubric)`

### Phản biện
```
"Phản biện bài phân tích thị trường này"
"Kiểm tra logic bài viết"
```
Pipeline: `content → quality (critique mode)`

### Xuất bản
```
"Kiểm duyệt bài này, sẵn sàng publish chưa?"
```
Pipeline: `quality (full) → platform`

## Pipelines

| Lệnh | Pipeline v3.0 |
|-------|--------------|
| Viết mới | content → style → quality → platform |
| Sửa bài | content → style → quality |
| Chấm bài | content → quality (rubric) |
| Phản biện | content → quality (critique) |
| Research | content → quality (verify) |
| Xuất bản | quality → platform |

## Vòng lặp Chất lượng

```
              ┌──── REVISE (tối đa 2 lần) ────┐
              ▼                                │
content → style → quality ──── PASS ──→ platform → User
                     │
                     └── REJECT ──→ content (nghiên cứu lại)
```

## Cấu trúc Thư mục

```
Viet-chuyen-nghiep/
├─ SKILL.md                    ← Tổng Biên Tập (entry point)
├─ HUONG-DAN-SU-DUNG.md        ← File này
├─ workforce-config.json       ← Config v3.0
│
├─ Ban/                        ← 6 BAN CHUYÊN MÔN (v3.0)
│  ├─ content/   (3 files)     ← Thu thập & nghiên cứu
│  ├─ style/     (6 files)     ← Biên tập phong cách
│  ├─ quality/   (7 files)     ← Kiểm duyệt
│  ├─ platform/  (5 files)     ← Xuất bản đa nền tảng
│  ├─ examples/  (1 file)      ← Thư viện bài mẫu
│  └─ meta/      (3 files)     ← Phát triển & audit
│
├─ Orchestrator/               ← Điều phối trung tâm
│  ├─ editor-in-chief.md       ← Vai trò Tổng BT
│  ├─ routing-matrix.md        ← Ma trận routing
│  ├─ delegation-protocol.md   ← Quy trình giao việc
│  └─ escalation-rules.md      ← Quy tắc báo cáo
│
├─ Team-Orchestration/         ← Pipeline chi tiết
│  ├─ write-new.md
│  ├─ edit-draft.md
│  ├─ grade-content.md
│  ├─ critique-content.md
│  ├─ deep-research.md
│  └─ publish-ready.md
│
├─ Autonomous-Core/            ← 4 Engine tự động
│  ├─ task-classifier.md
│  ├─ workflow-engine.md
│  ├─ scoring-engine.md
│  └─ state-manager.md
│
├─ Context-Layer/              ← Knowledge Base (45+ files)
│  ├─ CoreModules/             ← Quy tắc lõi
│  ├─ Knowledge-Base/          ← Kiến thức chuyên sâu
│  ├─ Second-Brain/            ← Kinh nghiệm tích lũy
│  └─ Memory/                  ← Session memory
│
├─ Workers/                    ← ⚠️ LEGACY v2.0 (xem DEPRECATED.md)
├─ SubAgents/                  ← ⚠️ LEGACY v2.0 (xem DEPRECATED.md)
└─ assets/examples/            ← Ví dụ mẫu
```

## Xử lý Sự cố

| Vấn đề | Giải pháp |
|--------|----------|
| Bài viết bị reject nhiều lần | Kiểm tra brief rõ ràng chưa, yêu cầu cụ thể hơn |
| Anti-AI score cao (>30%) | Yêu cầu "viết lại cho tự nhiên, thêm ví dụ cá nhân" |
| Thiếu nguồn/số liệu | Yêu cầu "research kỹ hơn" hoặc cung cấp nguồn |
| Format không đúng platform | Chỉ rõ platform: "viết cho Facebook" hoặc "format LinkedIn" |

## Câu hỏi Thường gặp

**Q: Skill này có viết được tiếng Anh không?**
A: Mặc định tiếng Việt. Nếu cần tiếng Anh, hãy nói rõ trong yêu cầu.

**Q: Có giới hạn độ dài không?**
A: Không. Skill xử lý từ caption 50 từ đến ebook nhiều chương.

**Q: Workers/ và SubAgents/ còn dùng không?**
A: Không — đã được thay thế bởi Ban/ từ v3.0. Giữ lại để tham khảo.
