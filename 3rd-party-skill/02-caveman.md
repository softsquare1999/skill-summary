# Caveman

Repo: https://github.com/JuliusBrussee/caveman

## 1. ใช้ทำอะไร
Skill สำหรับบีบอัด output ของ AI ให้สั้นลง ~65-75% โดยยังคงความถูกต้องทางเทคนิคเต็ม 100% ตัดคำฟุ่มเฟือย เขียนเป็นประโยคสั้น/fragment แทน รองรับ 30+ agent (Claude Code, Cursor, Windsurf, Copilot ฯลฯ)

ความสามารถหลัก:
- มีระดับความเข้ม (lite / full / ultra / wenyan-จีนโบราณ)
- ย่อ commit message ตาม character limit ที่กำหนด
- ย่อ PR review
- บีบอัดไฟล์ memory ลด input token ~46%
- มีสถิติ token/cost ที่ประหยัดได้

## 2. วิธีใช้
- `/caveman [level]` — เปิดโหมดบีบอัดสำหรับ session นั้น (หรือพูดว่า "talk like caveman")
- `/caveman-stats` — ดูสถิติ token/เงินที่ประหยัดได้สะสม
- `/caveman-compress <file>` — บีบอัดไฟล์ memory ให้เล็กลง

## 3. การติดตั้ง
- macOS/Linux/WSL:
  ```
  curl -fsSL https://raw.githubusercontent.com/JuliusBrussee/caveman/main/install.sh | bash
  ```
- Windows PowerShell:
  ```
  irm https://raw.githubusercontent.com/JuliusBrussee/caveman/main/install.ps1 | iex
  ```
- ต้องมี Node ≥18 ติดตั้งใช้เวลา ~30 วินาที
