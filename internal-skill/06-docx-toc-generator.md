# docx-toc-generator (v1.0)

Source: `agenetic-document-skill/docx-toc-generator/SKILL.md`

## 1. ใช้ทำอะไร
สร้างสารบัญ (Table of Contents) แบบตาราง Markdown จากไฟล์ `.docx` หนึ่งไฟล์หรือหลายไฟล์ พร้อมเลขหน้าและระดับ heading แบบย่อหน้า วิธีทำ: แปลงเป็น PDF ผ่าน LibreOffice แล้วดึงเลขหน้าจาก PDF bookmark (PyMuPDF); ถ้าไม่มี bookmark จะ fallback ไปใช้ python-docx (ไม่มีเลขหน้า) รองรับทั้งไฟล์เดี่ยวและทั้งโฟลเดอร์ (auto-detect เลขบทจากชื่อไฟล์)

## 2. วิธีใช้
- Trigger phrases: "สร้างสารบัญ", "สารบัญ", "รายการหัวข้อ", "generate TOC", "table of contents", "TOC"
- ระบุจำนวนระดับ heading ได้ (default 2 ระดับ)
- ตัวอย่าง: "สร้างสารบัญจากไฟล์ Word นี้: references/แผนการดำเนินงาน.docx แสดง 2 ระดับ heading"
- Output: ไฟล์เดี่ยว → `{basename}-สารบัญ.md`, โฟลเดอร์ → `{folder}/สารบัญ.md`
- ข้อควรระวัง: บน Windows ต้องใช้ PowerShell `Start-Process` เรียก LibreOffice เพื่อรองรับชื่อไฟล์ภาษาไทย

## 3. การติดตั้ง
```
pip install pymupdf python-docx
```
ต้องติดตั้ง LibreOffice (path เริ่มต้น `C:\Program Files\LibreOffice\program\soffice.exe` บน Windows)
