# thai-proofread (v1.0)

Source: `agenetic-document-skill/thai-proofread/SKILL.md`

## 1. ใช้ทำอะไร
ตรวจสอบไฟล์ markdown ภาษาไทยหาข้อผิดพลาด 3 ด้าน: คำสะกดผิด, บริบทภาษาที่ไม่ปกติ (เลือกคำผิด, polarity กลับด้าน, table header ผิด), เครื่องหมายวรรคตอน โดย spawn Claude Opus agent แบบ parallel ทีละไฟล์ (หรือ batch ไฟล์เล็ก) แล้วบันทึกรายงานแยกไฟล์

## 2. วิธีใช้
- Trigger phrases: "ตรวจสอบเอกสารภาษาไทย", "เช็คคำสะกดผิด", "proofread Thai documents", "ตรวจเครื่องหมายวรรคตอน" หรือชี้ไปที่ folder markdown แล้วขอ quality check
- ตัวอย่าง: "ตรวจสอบไฟล์ markdown ภาษาไทยทั้งหมดใน context/" หรือ "proofread context/01-วัตถุประสงค์.md"
- Batching: ไฟล์ <30 บรรทัด batch 2 ต่อ agent, 30-100 บรรทัด 1 agent/ไฟล์, >100 บรรทัด 1 agent/ไฟล์ (แตกเป็น section ถ้า >200 บรรทัด) สูงสุด 6 agent ต่อรอบ
- Output: `proofread/<filename>-proofread.md` ต่อไฟล์ พร้อมตารางสรุปจำนวน issue

## 3. การติดตั้ง
ไม่ต้องติดตั้งอะไร รันผ่าน Claude Opus agent ทั้งหมด
