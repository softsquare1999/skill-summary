# extract-msword-to-markdown (v2.0)

Source: `agenetic-document-skill/extract-msword-to-markdown/SKILL.md`

## 1. ใช้ทำอะไร
แปลงไฟล์ `.docx` หนึ่งไฟล์หรือหลายไฟล์เป็น markdown มี 2 mode:
- **plain-text** (default) — ข้อความล้วน ไม่มี style markup แต่สร้าง auto-numbering จาก `numbering.xml`/`styles.xml` (เช่น "บทที่ 1", "1.2", bullet) ให้อัตโนมัติ
- **keep-format** — เก็บ heading (`#`/`##`/`###`), bold, list ไว้เป็น markdown

ใช้ PowerShell `System.IO.Compression.ZipFile` API อ่าน `word/document.xml` โดยตรง ไม่ต้องพึ่ง pandoc/LibreOffice/COM

## 2. วิธีใช้
- Trigger phrases: "อ่านไฟล์ word แล้วเก็บไว้ที่ context", "แปลง word เป็น markdown", "extract .docx", "convert Word to markdown"
- บอก user ว่าใช้ mode ไหนก่อนเริ่มเสมอ (default plain-text) ถ้า user บอก "keep format"/"เก็บ format"/"เก็บ heading" ให้สลับเป็น keep-format
- ตัวอย่าง: "อ่านไฟล์ references/xxx.docx แล้วเก็บเป็น markdown ใน context/" หรือ "อ่านไฟล์ word ทุกไฟล์ใน references/ แล้ว convert เป็น markdown"
- Output: `context/<NN>-<ThaiTitle>.md` (keep-format มี frontmatter อ้างอิงชื่อไฟล์ต้นฉบับ)

## 3. การติดตั้ง
ไม่ต้องติดตั้งอะไรเพิ่ม (PowerShell stdlib เท่านั้น)
