# docx-proofread (v1.0)

Source: `agenetic-document-skill/docx-proofread/SKILL.md`

## 1. ใช้ทำอะไร
Pipeline ครบวงจร: extract `.docx` → markdown (ใช้ logic เดียวกับ `extract-msword-to-markdown`) แล้ว proofread เนื้อหาภาษาไทยด้วย Opus agent แบบ parallel (ใช้ logic เดียวกับ `thai-proofread`) รวมสองสกิลเป็นคำสั่งเดียว มี timestamp logic เพื่อข้ามไฟล์ที่ทำล่าสุดแล้ว

## 2. วิธีใช้
- Trigger phrases: "ตรวจเอกสาร word", "proofread .docx", "ตรวจสอบเอกสาร Word ภาษาไทย", "/docx-proofread"
- ระบุไฟล์/โฟลเดอร์ หรือไม่ระบุก็ได้ (glob `*.docx` ในโฟลเดอร์ปัจจุบัน)
- Flag `--fresh` — บังคับ extract/proofread ใหม่ทั้งหมด ไม่สนใจ timestamp
- Output: `context/<NN>-<title>.md` (extract), `proofread/<filename>-proofread.md` (report), พร้อมตารางสรุปสถานะต่อไฟล์

## 3. การติดตั้ง
ไม่ต้องติดตั้ง Python เพิ่ม — รันผ่าน Claude agent + PowerShell ทั้งหมด
