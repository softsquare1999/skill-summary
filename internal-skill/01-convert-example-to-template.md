# convert-example-to-template (v1.4)

Source: `agenetic-document-skill/convert-example-to-template/SKILL.md`

## 1. ใช้ทำอะไร
แปลงไฟล์ `.docx` ที่กรอกข้อมูลแล้วให้กลายเป็น template เปล่า (คงสไตล์/header-footer/โลโก้/table structure ไว้ แทนที่เนื้อหาจริงด้วย `[กรอก...]`) โดยแก้ไข XML ของ `.docx` โดยตรง ไม่ต้องใช้ Word นอกจากนี้ยังใช้แก้ header/footer ที่หายไป และจัดหน้า portrait/landscape ผสมกันในเอกสารเดียวได้

## 2. วิธีใช้
- Trigger phrases: "ทำเป็น template", "แปลงเป็น template", "convert to template", "header ไม่แสดง", "footer หาย", ขอปรับหน้าเป็น landscape
- Task 1 — แก้ header/footer หาย: `unpack.py` → `fix_header_footer.py` → `repack.py`
- Task 2 — แปลงเป็น template: `analyze_doc.py` (ดู style/table ก่อนเสมอ) → `convert_to_template.py <src> <out> [options]` (มี flag เช่น `--keep-styles`, `--keep-patterns`, `--table-header-rows`, `--lang en`)
- Task 3 — mixed orientation: `unpack.py` → `set_orientation.py ... split --before "TEXT"` → `repack.py`
- Task 4 — มี rule เฉพาะสำหรับเอกสาร Minutes of Meeting (MOM) โปรเจกต์ AP-005

## 3. การติดตั้ง
ไม่ต้องติดตั้ง dependency เพิ่ม — ใช้ Python stdlib เท่านั้น (`zipfile`/`xml`) วางไฟล์ SKILL.md พร้อม `scripts/` ตามโครงสร้าง repo แล้วอ้างอิง path ใน `.claude/settings.json`
