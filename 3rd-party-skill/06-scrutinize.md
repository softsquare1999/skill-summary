# Scrutinize

Repo: https://github.com/thananon/9arm-skills/tree/main/skills/engineering/scrutinize

## 1. ใช้ทำอะไร
รีวิวโค้ด/PR/แผนงานแบบมุมมอง "คนนอก" (outsider) เริ่มจากตั้งคำถามว่างานนี้ควรมีอยู่จริงไหม มีทางที่ง่ายกว่านี้หรือไม่ ก่อนจะไล่ trace เส้นทาง execution จริงเพื่อยืนยันว่าโค้ดทำในสิ่งที่มันอ้างว่าทำจริง

## 2. วิธีใช้ (4 ขั้นตอน)
1. **Intent** — สรุปเป้าหมายใหม่ หาทางเลือกที่เรียบง่ายกว่า
2. **Trace** — ไล่เส้นทางโค้ดจริงแบบ end-to-end
3. **Verify** — ตรวจทุกข้ออ้างกับ edge case และผลข้างเคียงที่ซ่อนอยู่
4. **Report** — รายงานผลเรียงตามความรุนแรง อ้างอิง file:line ชัดเจนทุกจุด (หลักการ "cite or it didn't happen")

**Trigger**: `/scrutinize` หรืออัตโนมัติเมื่อผู้ใช้ขอ review/audit/sanity-check/second opinion บนแผน, PR, diff, design doc, หรือโค้ดที่เสนอ

## 3. การติดตั้ง
เป็น skill instruction ที่โหลดผ่านกลไก skill ของ Claude Code (ไฟล์ SKILL.md ในโฟลเดอร์ skills ของ repo) ไม่ต้องติดตั้งแยก
