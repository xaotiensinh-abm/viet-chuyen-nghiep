# Golden End-to-End Test — Pipeline write-new

## Mục đích
Kiểm tra toàn bộ pipeline v3.0 hoạt động đúng end-to-end.

---

## Test Case 1: Viết Blog 1200 từ

### Input (Brief từ User)
```
"Viết bài blog 1200 từ về 5 sai lầm phổ biến khi CEO ứng dụng AI vào doanh nghiệp.
Audience: CEO SME Việt Nam. 
Tone: Chuyên gia tư vấn, gần gũi.
Platform: LinkedIn."
```

### Bước 1: Ban Thu Thập (content/) ✅

**Expected output:**
```yaml
goi_nguyen_lieu:
  brief:
    loai: "blog"
    audience: "CEO SME Việt Nam"
    tone: "chuyên-gia-gần-gũi"
    do_dai: "1200 từ"
    platform: "linkedin"
  research:
    nguon:
      - {url: "...", tieu_de: "McKinsey AI Report 2025", do_tin_cay: "tier-1"}
      - {url: "...", tieu_de: "VnExpress AI Survey VN", do_tin_cay: "tier-2"}
    so_lieu_key:
      - {gia_tri: "70% dự án AI thất bại", nguon: "McKinsey", ngay: "2025"}
      - {gia_tri: "23% SME VN dùng AI", nguon: "VCCI", ngay: "2025"}
  analysis:
    angle: "Chia sẻ kinh nghiệm thực chiến, không lý thuyết suông"
    outline:
      - {section: "Hook", noi_dung: "Câu hỏi gây sốc + số liệu"}
      - {section: "Sai lầm 1-5", noi_dung: "Mỗi sai lầm = tình huống + giải pháp"}
      - {section: "Kết", noi_dung: "CTA tải checklist"}
```

**Checklist verify:**
- [ ] Có ít nhất 3 nguồn tier-1 hoặc tier-2
- [ ] Angle rõ ràng, không generic
- [ ] Outline có hook + body + CTA

### Bước 2: Ban Biên Tập (style/) ✅

**BTV cần kích hoạt:**
- `storytelling.md` → hook mở đầu bằng tình huống thực
- `rhythm.md` → biến tấu câu ngắn/dài, punch line cuối mỗi sai lầm
- `technical.md` → thuật ngữ AI giải thích đúng cho CEO
- `presentation.md` → heading H2 cho mỗi sai lầm, bold key insight

**Checklist verify:**
- [ ] Hook 2 dòng đầu gây tò mò
- [ ] Mỗi sai lầm có ví dụ cụ thể (show, don't tell)
- [ ] Biến tấu câu: không quá 3 câu liên tiếp cùng độ dài
- [ ] Thuật ngữ AI không dùng jargon mà CEO không hiểu

### Bước 3: Ban Kiểm Duyệt (quality/) ✅

**6 kiểm tra chạy song song:**

| BTV | Expected Result |
|-----|----------------|
| punctuation.md | 0 lỗi dấu câu |
| capitalization.md | Viết hoa đúng tên riêng, đầu câu |
| natural.md | ≤ 2 tín hiệu "mùi dịch" |
| anti-ai.md | Score ≤ 30% (grade A hoặc B) |
| fact-check.md | 100% claims có nguồn tier-1/2 |
| consistency.md | Tone nhất quán, xưng hô "bạn" suốt bài |

**Expected phán quyết:**
```yaml
phan_quyet:
  ket_qua: "PASS"
  diem_tong: 82
```

**Nếu REVISE:**
- Ghi chú cụ thể: "Đoạn 3 anti-AI 45%, cần thay 'hơn nữa' → ví dụ cụ thể"
- Chuyển style/ → sửa → quality/ chạy lại

### Bước 4: Ban Xuất Bản (platform/) ✅

**BTV linkedin.md tối ưu:**
```yaml
xuat_ban:
  platform: "linkedin"
  content: "..." # Đã tối ưu: hook 2 dòng, 1300 ký tự max, CTA rõ
  metadata:
    do_dai: "1180 từ"
    hashtags: ["#AIforBusiness", "#CEOInsights", "#DigitalTransformation"]
    format: "text"
  quality_stamp:
    diem: 82
    anti_ai: "B"
    verified: true
```

**Checklist verify:**
- [ ] Hook 2 dòng đầu xuất hiện trước "see more"
- [ ] Có hashtag liên quan
- [ ] CTA cuối bài rõ ràng

---

## Test Case 2: Chấm Bài (grade-content)

### Input
```
"Chấm bài marketing 800 từ về cloud computing theo thang 100"
```

### Expected Pipeline
```
content/ (light) → quality/ (rubric mode)
```

### Expected Output
```yaml
phan_quyet:
  ket_qua: "GRADED"
  diem_tong: 67
  chi_tiet:
    noi_dung_do_sau: 15/25
    cau_truc_logic: 16/20
    phong_cach: 12/20
    chinh_xac: 12/15
    anti_ai: 5/10
    format: 7/10
  nhan_xet: "Bài viết có nội dung tốt nhưng thiếu ví dụ cụ thể..."
  de_xuat: ["Thêm case study VN", "Giảm cụm từ AI-generated"]
```

---

## Regression Checklist

Sau mỗi thay đổi hệ thống, chạy lại:

- [ ] Test Case 1 (write-new → blog LinkedIn) — pipeline 4 Ban
- [ ] Test Case 2 (grade-content → rubric 100) — pipeline 2 Ban
- [ ] REVISE loop: cố ý tạo bài anti-AI > 60% → verify quality/ reject → style/ sửa
- [ ] Escalation: cố ý brief mơ hồ → verify hệ thống hỏi user
