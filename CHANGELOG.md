# Changelog — Viết Chuyên Nghiệp

## [v3.0.2] — 2026-03-10

### Added
- Đóng gói global skill: directory junction `skills/viet-chuyen-nghiep`
- Workflow `/viet-pro` tại `global_workflows/viet-pro.md`
- Auto-activate triggers mới: "viết blog", "viết báo cáo", "viết đề án", "viết email marketing"
- `base_path` directive trong SKILL.md cho global skill resolution

### Changed
- SKILL.md: Examples + Constraints cập nhật 100% v3.0 Ban terminology

## [v3.0.1] — 2026-03-10

### Fixed (Audit fix — 54→100/100)
- `Orchestrator/routing-matrix.md` → pipeline v3.0 Ban/
- `Orchestrator/editor-in-chief.md` → 6 Ban (thay 8 phòng ban)
- `Orchestrator/delegation-protocol.md` → Ban/BTV terminology
- `Orchestrator/escalation-rules.md` → escalation đến đúng Ban
- 6 files `Team-Orchestration/*.md` → tham chiếu Ban/
- `workforce-config.json` → v3.0 Ban/ + legacy markers
- `HUONG-DAN-SU-DUNG.md` → v3.0 kiến trúc Tòa Soạn
- `README.md` → v3.0 architecture

### Added
- `Orchestrator/interface-contract.md` — YAML schema giữa 6 Ban
- `Team-Orchestration/golden-test.md` — 2 test cases end-to-end
- `Workers/DEPRECATED.md` + `SubAgents/DEPRECATED.md` — legacy markers

## [v3.0.0] — 2026-03-10

### Added (Kiến Trúc Tòa Soạn)
- `Ban/content/` (3 files): lead-content, research, analysis
- `Ban/style/` (6 files): lead-style, storytelling, rhythm, narrative, presentation, technical
- `Ban/quality/` (7 files): lead-quality, punctuation, capitalization, natural, anti-ai, fact-check, consistency
- `Ban/platform/` (5 files): lead-platform, facebook, tiktok, linkedin, video
- `Ban/examples/` (1 file): lead-examples
- `Ban/meta/` (3 files): lead-meta, upgrade, style-audit

### Changed
- SKILL.md: v3.0 Tổng Biên Tập, sơ đồ Tòa Soạn, routing table

### Deprecated
- `Workers/` (8 files) → thay thế bởi `Ban/`
- `SubAgents/` (32 files) → thay thế bởi `Ban/`

## [v2.0.0] — 2026-03-08

### Added
- Autonomous-Core: 4 engines (task-classifier, workflow, scoring, state)
- Context-Layer: CoreModules, Knowledge-Base, Second-Brain, Memory
- Team-Orchestration: 6 pipeline definitions
- Orchestrator: editor-in-chief, routing-matrix, delegation, escalation

## [v1.0.0] — 2026-02

### Added
- Initial release: 8 Workers + 32 SubAgents
- Basic pipeline: intake → research → strategy → output → quality
