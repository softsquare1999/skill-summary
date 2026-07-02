# Grill-Me

Repo: https://skillsmp.com/creators/activepieces/activepieces/agents-skills-grill-me
(ต้นทาง: https://github.com/activepieces/activepieces)

## 1. ใช้ทำอะไร
Skill ที่ให้ agent "ซัก" ผู้ใช้อย่างเข้มข้นเกี่ยวกับแผนหรือดีไซน์ที่เสนอมา ไล่ถามทุกแขนงของ decision tree จนกว่าจะเข้าใจตรงกัน โดย agent จะสำรวจโค้ดในโปรเจกต์ที่เกี่ยวข้องด้วยเพื่อใช้ประกอบการตั้งคำถาม และเสนอคำตอบแนะนำในแต่ละคำถามให้ด้วย เหมาะกับการ stress-test ข้อเสนอ/ดีไซน์ก่อนลงมือทำจริง

## 2. วิธีใช้
เรียกใช้เมื่อต้องการให้ทดสอบความแน่นของแผน หรือรับฟีดแบ็กเชิงวิจารณ์กับดีไซน์ พูดง่ายๆ ว่า "grill me" ก็ trigger ได้ ใช้ได้กับ Claude Code, Codex CLI, และ ChatGPT

## 3. การติดตั้ง
- **แบบ prompt**: copy skill prompt ไปวางใน Claude/Codex หรือ assistant ที่รองรับ
- **แบบ CLI**:
  ```
  npx skills add https://github.com/activepieces/activepieces --skill grill-me
  ```

ดูแลโดยทีม Activepieces (repo หลักมี ⭐ 22,951 ดาว)
