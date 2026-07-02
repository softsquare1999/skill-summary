# msteams-transcript-to-draft (v1.0)

Source: `agenetic-document-skill/msteams-transcript-to-draft/SKILL.md`

## 1. ใช้ทำอะไร
อ่าน transcript การประชุม MS Teams (ไทย/อังกฤษ/ผสม, รองรับ `.md`/`.txt`/`.docx`) แล้วสกัดข้อมูลผู้เข้าร่วม วาระ มติ และ action items ด้วย subagent เดียว ส่ง output เป็น JSON ตาม schema ที่กำหนด แล้วประกอบเป็นร่างรายงานการประชุมภาษาไทย บันทึกที่ `context/meeting_draft.md` เพื่อให้ user ตรวจก่อนนำไปใส่ Word template จริง

## 2. วิธีใช้
- Trigger phrases: "อ่าน transcript", "ถอดเสียงการประชุม", "เขียน meeting draft", "transcript to draft", "สร้าง draft รายงานประชุม"
- ถ้า transcript เป็น `.docx` จะ delegate ไปที่ `extract-msword-to-markdown` ก่อนแปลงเป็น `.md`
- ตัวอย่าง: "อ่าน transcript การประชุมที่ context/meeting_transcript.md แล้วเขียนสรุปลง context/meeting_draft.md"
- Output: `context/meeting_draft.md` (มีรายชื่อผู้เข้าร่วม, ตารางสาระสำคัญ/มติ, ตาราง action items) พร้อมรายงานจำนวนวาระ/action item และ flag ข้อมูลที่ไม่ชัดเจน

## 3. การติดตั้ง
```
pip install python-docx
```
(จำเป็นเฉพาะกรณี input เป็น `.docx`)
