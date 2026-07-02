# thai-docx-spellcheck (v1.0)

Source: `agenetic-document-skill/thai-docx-spellcheck/SKILL.md`

## 1. ใช้ทำอะไร
ตรวจคำสะกดผิดภาษาไทยจากไฟล์ `.docx` แบบออฟไลน์และ deterministic (ไม่ใช้ agent) ผ่าน pipeline คงที่ `mammoth` (docx→md) → `mdclean` (ทำความสะอาด markdown) → `pythainlp` (เช็คคำในพจนานุกรม) แล้ว render เป็นรายงาน HTML ไฟล์เดียวสำหรับคน non-tech อ่านเอง เป็น **non-word detector** เท่านั้น — จับ typo ที่กลายเป็นคำจริงไม่ได้ (เช่น เขา vs เข้า) และชื่อคน/คำย่อจะ false positive เสมอ

## 2. วิธีใช้
- Trigger phrases: "ตรวจคำผิดไฟล์ word ทำเป็นรายงาน HTML", "ตรวจคำสะกดภาษาไทยแบบออฟไลน์", "ตรวจคำผิดแบบไม่ใช้ agent"
- รัน `python scripts/run.py "path/to/document.docx"` (หรือไม่ใส่ path เพื่อรันทุกไฟล์ .docx ในโฟลเดอร์)
- Output: `<name>.report.html` ข้างไฟล์ต้นฉบับ (สีแดง = คำต้องสงสัย, "น่าจะเป็น" = คำแนะนำ)
- ถ้าผลลัพธ์ 0 คำ ต้องบอกว่า "ไม่พบคำที่สะกดผิดแบบไม่มีในพจนานุกรม" ไม่ใช่ "ไม่มีคำผิดเลย"
- ใช้แทน `thai-proofread`/`docx-proofread` เมื่อต้องการผลเร็ว ออฟไลน์ ไม่ต้องวิเคราะห์บริบทลึก

## 3. การติดตั้ง
```
pip install mammoth pythainlp
```
รันครั้งแรก `pythainlp` จะดาวน์โหลด corpus ภาษาไทย (ต้องมีอินเทอร์เน็ตครั้งเดียว)
