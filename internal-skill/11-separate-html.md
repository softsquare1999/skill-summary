# separate-html (v1.2.0)

Source: `agenetic-document-skill/separate-html/SKILL.md`

## 1. ใช้ทำอะไร
แยกไฟล์ `BMA ERP Components.html` (bundled single-page app ที่มี `__bundler/manifest`) ออกเป็น standalone HTML ทีละ section (เมนู) เพื่อนำเข้า Figma ผ่าน plugin **html.to.design** แต่ละไฟล์ output ฝัง font/icon เป็น data URI ทั้งหมด ไม่มี external dependency ใช้ Python 3-stage workflow: build asset cache → extract shared parts → generate files (รายละเอียดเต็มอยู่ใน `references/figma-html-split.md`)

## 2. วิธีใช้
- Trigger phrases: "แยก html", "แยกไฟล์ตามเมนู", "ส่งเข้า Figma", "standalone HTML per section" หรืออัปโหลดไฟล์ `BMA ERP Components.html`
- ตัวอย่าง: "แยก BMA ERP Components.html ออกเป็นไฟล์ HTML แยกทีละเมนู เพื่อส่งเข้า Figma" หรือระบุ output directory เพิ่มเติม
- Output: ไฟล์ HTML แยกทีละ section เช่น `01_Page_Header.html`, `02_Buttons.html` แต่ละไฟล์มี sidebar/header/banner/scripts ครบพร้อม active state

## 3. การติดตั้ง
ต้องมี Cowork หรือ Claude Code ที่มีสิทธิ์ Bash + Python 3 (stdlib เท่านั้น: `json`, `re`, `base64`, `gzip`, `pickle`) — ไม่ต้องติดตั้ง dependency เพิ่ม
