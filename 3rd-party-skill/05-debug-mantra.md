# Debug Mantra

Repo: https://github.com/thananon/9arm-skills/tree/main/skills/engineering/debug-mantra

## 1. ใช้ทำอะไร
บังคับวินัยการ debug แบบ 4 ขั้นตอน: reproduce ปัญหาให้ได้ก่อน → trace เส้นทางที่ fail → ตั้งสมมติฐานแล้วพยายาม "หักล้าง" มันก่อนเชื่อ → cross-reference กับหลักฐานทั้งหมดที่เจอมา เปลี่ยนการแก้บั๊กแบบสุ่มลองผิดลองถูกให้เป็นกระบวนการที่มีหลักฐานรองรับ

## 2. วิธีใช้
1. ท่องบล็อก mantra ให้ตรงคำเป๊ะๆ ตอนเริ่ม debug session
2. ทำตาม 4 ขั้นตอนตามลำดับ ห้ามข้าม ห้ามเสนอ fix ก่อนจะ reproduce ได้
3. จดบันทึก (ledger) ทุกการทดลอง สิ่งที่เปลี่ยน และผลที่ตัดออก/ยืนยัน
4. เมื่อมีสมมติฐาน ต้องออกแบบวิธี "หักล้าง" มันก่อนเริ่มทดสอบ

**Trigger**: `/debug-mantra` หรืออัตโนมัติเมื่อผู้ใช้รายงานบั๊ก, สิ่งพัง/throw error, ขอให้ debug/วินิจฉัย, หรือแปะ stack trace/error log มา

## 3. การติดตั้ง
เป็น skill instruction ที่โหลดผ่านกลไก skill ของ Claude Code (ไฟล์ SKILL.md ในโฟลเดอร์ skills ของ repo) ไม่ต้องติดตั้งแยก
