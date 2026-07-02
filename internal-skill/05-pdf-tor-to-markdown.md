# pdf-tor-to-markdown (v1.0)

Source: `agenetic-document-skill/pdf-tor-to-markdown/SKILL.md`

## 1. ใช้ทำอะไร
แปลง PDF ที่ scan มา (TOR หรือเอกสารราชการไทย) เป็น markdown ไฟล์เดียว โดยถอดข้อความตรงตัว ไม่สรุป/ไม่แปล ใช้ `pymupdf` render แต่ละหน้าเป็น PNG 200 DPI แล้ว spawn subagent แยกทีละหน้า (batch ละ 5-6 หน้า, รันแบบ parallel ใน batch) ให้ถอดข้อความทีละหน้า จากนั้นรวมเป็นไฟล์เดียวพร้อม `<!-- page N -->` anchor แล้วลบไฟล์ temp ทิ้ง

## 2. วิธีใช้
- Trigger phrases: "แปลง PDF scanned", "แปลง TOR เป็น markdown", "ขอบเขตงาน PDF แปลงเป็น markdown", "/pdf-tor-to-markdown"
- ต้องระบุ `<pdf_path>` และ `<output_path>` (default `context/<filename>.md`)
- กฎสำคัญ: ห้าม paraphrase, คัดลอกทุกบรรทัดแม้ซ้ำ, คำที่อ่านไม่ชัดใส่ `[?]` ต่อท้าย, ลายเซ็นให้ใช้ `______`

## 3. การติดตั้ง
```
pip install pymupdf
```
ไม่ต้องใช้ Anthropic API key เพิ่ม (ใช้ Claude Code vision ผ่าน Read tool)
