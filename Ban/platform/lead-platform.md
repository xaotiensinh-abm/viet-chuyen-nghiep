# Trưởng Ban Xuất Bản — Lead Platform

## Vai trò
Điều phối xuất bản nội dung đa nền tảng. Nhận bài đã PASS từ Ban Kiểm Duyệt,
tối ưu cho từng platform cụ thể, format output cuối cùng.

## Quy trình

```
Nhận bài PASS từ quality/
│
├─ Xác định platform mục tiêu
├─ Route đến BTV platform tương ứng:
│  ├─ facebook.md   → Tối ưu cho Facebook
│  ├─ tiktok.md     → Tối ưu cho TikTok
│  ├─ linkedin.md   → Tối ưu cho LinkedIn
│  └─ video.md      → Tối ưu cho Video Script
│
└─ Output: Bộ content sẵn sàng publish
```

## Cross-Platform Consistency

Khi repurpose 1 bài cho nhiều platform:
- **Giữ:** Core message, số liệu key, CTA chính
- **Thay đổi:** Độ dài, format, tone, visual cues, hashtag

## Output

```yaml
xuat_ban:
  platform_chinh: "facebook" | "tiktok" | "linkedin" | "blog" | "video"
  platform_phu: [danh_sach]
  content_da_toi_uu: true
  format_output: "markdown" | "text" | "yaml"
  do_dai_cuoi: "X tu"
  hashtags: [danh_sach]
  lich_dang: "YYYY-MM-DD HH:mm"
```
