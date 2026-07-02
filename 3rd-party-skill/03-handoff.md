# Handoff

Repo: https://github.com/robertguss/claude-code-toolkit/tree/main/skills/handoff

## 1. ใช้ทำอะไร
สร้างเอกสาร handoff แบบมีโครงสร้าง (markdown) เพื่อส่งต่อบริบทงานระหว่าง session ของ Claude เก็บ decision, ความคืบหน้า, การเปลี่ยนแปลงโค้ด, blocker และสิ่งที่ต้องทำต่อ ทำให้ session ถัดไปทำงานต่อได้โดยไม่ต้องอธิบายซ้ำ

## 2. วิธีใช้
1. ประเมิน phase ปัจจุบันของงาน (exploration / implementation / debugging ฯลฯ)
2. ถามผู้ใช้ว่ารายละเอียดไหนสำคัญที่สุดที่ต้องเก็บ
3. สร้างเอกสาร handoff ที่มี decision พร้อมเหตุผล ("why"), code change, blocker, next steps
4. บันทึกที่ `.claude/handoffs/[date]-[description].md`

**Trigger เมื่อ**: จบ session งาน, พักงานกลางคัน, สลับไปทำโปรเจกต์อื่นชั่วคราว, หรือคาดว่า context จะถูก reset

## 3. การติดตั้ง
เป็น skill แบบ process/instruction ไม่ใช่โค้ดที่ต้อง build วางไฟล์ SKILL.md ไว้ในโฟลเดอร์ skills ของโปรเจกต์/plugin ตามโครงสร้าง toolkit นี้ก็ใช้งานได้เลย
