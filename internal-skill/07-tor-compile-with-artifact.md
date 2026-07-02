# tor-compile-with-artifact (v1.0)

Source: `agenetic-document-skill/tor-compile-with-artifact/SKILL.md`

## 1. ใช้ทำอะไร
วิเคราะห์ข้อกำหนดในขอบเขตงาน (TOR) เปรียบเทียบกับเอกสารส่งมอบ (Deliverables) ของโครงการ รองรับไฟล์ input หลายแบบ (`.md`, `.docx`, `.pdf` ทั้ง text/scanned, `.xlsx`) แล้ววิเคราะห์เป็นตาราง Gap Analysis พร้อมสถานะ (✅ มีแล้ว / ⚠️ ไม่ครบ / ❌ ขาดหาย / ⏭️ ข้าม) และข้อเสนอแนะ ส่งออกได้เป็น Markdown (ลงทะเบียนเป็น Artifact), Excel, หรือ Word

## 2. วิธีใช้
- Trigger phrases: "วิเคราะห์ TOR", "ตรวจสอบสิ่งส่งมอบ", "ตรวจสอบความครบถ้วนตาม TOR", "ทำ checklist จาก TOR", "/tor-compile-with-artifact"
- ระบุไฟล์ TOR และโฟลเดอร์เอกสารส่งมอบ ระบบจะเลือกวิธี parse ตามนามสกุลไฟล์อัตโนมัติ (delegate ไปที่ `extract-msword-to-markdown` สำหรับ .docx, `pdf-tor-to-markdown` สำหรับ scanned PDF)
- Output: `context/TOR_Deliverables_Checklist.md` (+Artifact), `context/TOR_Checklist.xlsx`, หรือ `context/TOR_Checklist.docx`
- เสนอเรียก `/advisor` เพิ่มถ้าต้องการวิเคราะห์เชิงลึก

## 3. การติดตั้ง
```
pip install pymupdf pandas openpyxl tabulate
```
(สำหรับ Word output ต้องมี `python-docx` ด้วย)
