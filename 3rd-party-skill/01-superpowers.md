# Superpowers

Repo: https://github.com/obra/superpowers

## 1. ใช้ทำอะไร
เฟรมเวิร์ก/methodology สำหรับ coding agent ให้ทำงานอย่างเป็นระบบแทนที่จะกระโดดเขียนโค้ดทันที มี workflow 6 ขั้น:

1. **Brainstorming** — refine ไอเดียผ่านคำถาม นำเสนอดีไซน์ให้ validate ก่อน
2. **Git Worktrees** — แยก branch ทำงานให้ isolate
3. **Planning** — ย่อยงานเป็น task ละ 2-5 นาที ระบุ spec ชัดเจน
4. **Subagent-Driven Development** — ส่ง subagent ใหม่ทำแต่ละ task พร้อม review 2 ชั้น
5. **Test-Driven Development** — บังคับ RED-GREEN-REFACTOR
6. **Code Review & Finishing** — รีวิวงานและตัดสินใจเรื่อง merge

มี skill ย่อยกว่า 15 ตัว ครอบคลุม testing, debugging, การวางแผน/รีวิว, และ meta-skill ทำให้ agent ทำงานต่อเนื่องได้หลายชั่วโมงโดยไม่หลุดจากแผน

## 2. วิธีใช้
Skill ทั้งหมด trigger อัตโนมัติเมื่อเกี่ยวข้อง ไม่ต้องเรียกเอง เช่น:
- เจอบั๊ก → `systematic-debugging` เด้งเอง
- จะสร้างฟีเจอร์ใหม่ → `brainstorming` เด้งเอง

## 3. การติดตั้ง
- Claude Code: `/plugin install superpowers@claude-plugins-official`
- Cursor: `/add-plugin superpowers`
- GitHub Copilot CLI: register marketplace แล้ว install plugin
- Antigravity/Pi: ติดตั้งจาก GitHub repo โดยตรง
