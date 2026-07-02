# pdf-flow-to-description (v1.2)

Source: `agenetic-document-skill/pdf-flow-to-description/SKILL.md`

## 1. ใช้ทำอะไร
อ่าน flowchart/business process diagram จาก PDF (รองรับภาษาไทย) แล้วเขียนคำอธิบายขั้นตอนแบบเลข 1-2-3-4 เป็นทางการสำหรับผู้อ่านที่ไม่ใช่สาย IT หรือผู้อ่านที่คุ้นเคย ERP โดย render PDF เป็น PNG ก่อนเสมอ (กันปัญหาภาษาไทย encode ผิด) crop แยก section/swimlane หากซับซ้อน แล้วเรียก `/advisor` (Opus) เพิ่มเมื่อ flow ซับซ้อนจริงๆ เท่านั้น

## 2. วิธีใช้
- Trigger phrases: "อธิบาย flow", "เขียนบรรยายขั้นตอน", "แปล diagram เป็นข้อความ", "สรุป process"
- ต้องถามก่อนเริ่ม (ถ้ายังไม่ระบุ): PDF/หน้าที่ต้องการ, กลุ่มผู้อ่าน (รู้จัก ERP หรือ non-IT), output path
- กฎการเขียน: ห้ามใช้ลูกศร/em dash, สลับประธานประโยคตามผู้กระทำจริง, ทางแยกใช้เลข+อักษร (3ก./3ข.), ซ่อน technical term (module code, API, database) สำหรับกลุ่ม non-IT
- Output: markdown เช่น `references/flow_descriptions/CF_flow_descriptions.md`

## 3. การติดตั้ง
```
pip install pymupdf
```
