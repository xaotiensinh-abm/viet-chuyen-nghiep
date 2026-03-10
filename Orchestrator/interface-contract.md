# Interface Contract — Giao thức Giao tiếp Giữa Các Ban

## Mục đích
Chuẩn hóa input/output giữa các Ban để pipeline hoạt động end-to-end.

---

## 1. Content → Style (Gói Nguyên Liệu)

```yaml
# OUTPUT của Ban Thu Thập → INPUT cho Ban Biên Tập
goi_nguyen_lieu:
  brief:
    loai: "ebook" | "blog" | "social" | "email" | "video_script" | "bao_cao"
    audience: "CEO SME" | "Gen Z" | "Kỹ sư" | "..." 
    tone: "..." # từ tone-of-voice-guide.md
    do_dai: "X tu"
    platform: "facebook" | "tiktok" | "linkedin" | "blog" | "all"
  
  research:
    nguon: [{url, tieu_de, do_tin_cay}]
    so_lieu_key: [{gia_tri, nguon, ngay}]
    case_study: [...]
  
  analysis:
    angle: "..."
    outline: [{section, noi_dung}]
    doi_thu_gap: [...]
  
  draft: "..." # Bản thảo thô (nếu có)
```

## 2. Style → Quality (Bản Đã Biên Tập)

```yaml
# OUTPUT của Ban Biên Tập → INPUT cho Ban Kiểm Duyệt
ban_da_bien_tap:
  content: "..." # Nội dung đã biên tập
  diem_phong_cach: X/100
  btv_da_xu_ly: ["storytelling", "rhythm", ...]
  thay_doi:
    - vi_tri: "dong X"
      truoc: "..."
      sau: "..."
      ly_do: "..."
```

## 3. Quality → Platform | Style (Phán Quyết)

```yaml
# OUTPUT của Ban Kiểm Duyệt
phan_quyet:
  ket_qua: "PASS" | "REVISE" | "REJECT"
  diem_tong: X/100
  chi_tiet:
    dau_cau: {ket_qua, loi: [...]}
    viet_hoa: {ket_qua, loi: [...]}
    tu_nhien: {ket_qua, diem, loi: [...]}
    anti_ai: {ket_qua, ty_le_ai, dau_hieu: [...]}
    fact_check: {ket_qua, claims_sai: [...]}
    nhat_quan: {ket_qua, loi: [...]}
  
  # Nếu REVISE:
  ghi_chu_sua: ["..."] # Hướng dẫn cụ thể cho style/ sửa
  lan_revise: 1 | 2
  
  # Nếu REJECT:
  ly_do: "..."
  de_xuat: "..." # Hướng content/ nghiên cứu lại
```

## 4. Platform → Output (Content Sẵn Sàng)

```yaml
# OUTPUT cuối cùng
xuat_ban:
  platform: "facebook" | "tiktok" | "linkedin" | "blog" | "video"
  content: "..." # Đã tối ưu platform
  metadata:
    do_dai: "X tu"
    hashtags: [...]
    format: "text" | "carousel" | "video_script"
    lich_dang: "YYYY-MM-DD HH:mm" # gợi ý (optional)
  
  quality_stamp:
    diem: X/100
    anti_ai: "A" | "B"
    verified: true
```

## 5. Meta → System (Báo Cáo Audit)

```yaml
# OUTPUT của Ban Phát Triển
bao_cao_meta:
  loai: "audit" | "nang_cap" | "patch"
  ngay: "YYYY-MM-DD"
  phat_hien: [{chieu, mo_ta, muc_do}]
  de_xuat: [{agent, hanh_dong, uu_tien}]
  diem_system: X/70
```

---

## Quy tắc Giao tiếp

1. **Mỗi Ban CHỈ đọc input YAML** — không đọc trực tiếp output Ban khác
2. **Mỗi Ban CHỈ viết output YAML** — không sửa output Ban trước
3. **Trưởng Ban chịu trách nhiệm** hợp nhất output từ BTV của mình
4. **Tổng Biên Tập chịu trách nhiệm** chuyển output giữa các Ban
