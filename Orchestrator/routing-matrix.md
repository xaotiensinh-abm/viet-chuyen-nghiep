# Ma trận Điều hướng — v3.0 Kiến Trúc Tòa Soạn

## Sơ đồ Pipeline v3.0

```
USER → Tổng Biên Tập (SKILL.md)
         │
         ├─ BAN THU THẬP (content/)  → Bóc brief, nghiên cứu, phân tích
         │
         ├─ BAN BIÊN TẬP (style/)   → Biên tập phong cách (6 BTV)
         │
         ├─ BAN KIỂM DUYỆT (quality/) → 6 kiểm tra song song → PASS/REVISE/REJECT
         │
         ├─ BAN XUẤT BẢN (platform/) → Tối ưu đa nền tảng
         │
         └─ OUTPUT → User
```

## Bảng Routing Chính

| Loại task | Tín hiệu nhận dạng | Pipeline | Các Ban (theo thứ tự) |
|-----------|--------------------|---------|-----------------------|
| Viết ebook/tài liệu/handbook | "viết ebook", "viết sách", "viết tài liệu", "handbook" | `write-new` | content → style → quality → platform |
| Viết content social | "viết bài facebook", "content social", "TikTok", "LinkedIn" | `write-new` | content → style → quality → platform |
| Viết kịch bản video | "kịch bản video", "video script", "short video" | `write-new` | content → style → quality → platform (video) |
| Sửa bản nháp | "sửa bài", "edit", "viết lại", "rewrite" | `edit-draft` | content (light) → style → quality |
| Chấm bài | "chấm bài", "grade", "đánh giá", "thang 100" | `grade-content` | content (light) → quality (rubric) |
| Phản biện | "phản biện", "critique", "review logic" | `critique-content` | content → quality (logic + fact-check) |
| Research thuần | "nghiên cứu", "tìm hiểu", "deep research" | `deep-research` | content (research only) → quality |
| Repurpose | "chuyển thể", "repurpose", "viết lại cho [platform]" | `write-new` | content (light) → style → quality → platform |
| Xuất bản | "publish", "kiểm duyệt cuối", "ready to publish" | `publish-ready` | quality (full 6 kiểm tra) → platform |

## Quy tắc Routing

### 1. Ưu tiên Intent rõ ràng
Nếu user nói rõ loại task → route trực tiếp theo bảng trên.

### 2. Xử lý Mơ hồ
Nếu không rõ loại task:
- Hỏi user: "Anh/chị muốn em viết mới, sửa bài, hay đánh giá bài viết?"
- KHÔNG đoán — hỏi rõ rồi mới route

### 3. Multi-output
Khi user yêu cầu nhiều loại (VD: "viết ebook rồi tạo 3 bài social"):
1. Chạy pipeline `write-new` → content → style → quality (tạo bài gốc)
2. Rồi chạy pipeline `write-new` → content (light) → style → quality → platform (repurpose)
3. Cả 2 đều qua quality gate

### 4. Research LUÔN bắt buộc
Ban Thu Thập (content/) tham gia **mọi pipeline** (trừ `publish-ready`).

### 5. Quality LUÔN cuối pipeline
Ban Kiểm Duyệt (quality/) **luôn là Ban cuối** trước xuất bản.

### 6. Vòng lặp REVISE
Khi quality/ trả REVISE:
```
quality/ REVISE → style/ sửa theo ghi chú → quality/ chạy lại
Tối đa 2 vòng. Nếu vẫn fail → REJECT → content/ nghiên cứu lại.
```

## Routing Nội bộ Mỗi Ban

Mỗi Trưởng Ban tự phân công BTV nào xử lý:
- `Ban/content/lead-content.md` → phân công research.md, analysis.md
- `Ban/style/lead-style.md` → phân công 5 BTV theo tín hiệu bài
- `Ban/quality/lead-quality.md` → chạy 6 BTV song song, quyết định PASS/REVISE/REJECT
- `Ban/platform/lead-platform.md` → route đến BTV platform tương ứng
- `Ban/meta/lead-meta.md` → kích hoạt khi cần audit/nâng cấp system
