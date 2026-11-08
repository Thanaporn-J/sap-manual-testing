# PR Requirements — ข้อกำหนดจำลอง

**ระบบสมมติ:** สร้าง Purchase Requisition แบบหนึ่งรายการสินค้า มี Role `PR_CREATOR` และ `VIEWER` ตามนิยามของกรณีศึกษานี้

| ID | Requirement / Business Rule (สมมติ) | Acceptance Criteria |
|---|---|---|
| REQ-001 | `PR_CREATOR` สร้าง PR ได้ | กรอกข้อมูลถูกต้องแล้ว Save จะได้รับ PR ID |
| REQ-002 | Material เป็น Required Field | หากว่าง Save ไม่สำเร็จและมีข้อความแจ้งเตือน |
| REQ-003 | Quantity ต้องมากกว่า 0 | 0 และค่าติดลบไม่ผ่าน; 1 ผ่าน |
| REQ-004 | Required Date ต้องระบุและไม่ย้อนหลัง | ว่างหรือก่อนวันที่อ้างอิงไม่ผ่าน; วันปัจจุบันผ่าน |
| REQ-005 | บันทึกข้อมูลตรงตามที่ระบุ | PR ID และ Material, Quantity, Required Date ถูกต้อง |
| REQ-006 | `VIEWER` ไม่มีสิทธิ์สร้าง PR | ปฏิเสธการสร้าง PR และไม่มีข้อมูลใหม่ |
| REQ-007 | Material ต้องอยู่ใน Master Data จำลอง | รหัสที่ไม่มีอยู่ไม่ผ่าน Validation |

## Assumptions / Test Data
- วันที่อ้างอิงจำลอง: **2026-11-08** (ไม่ใช่วันที่ Execute จริง)
- Valid Materials: `MAT-1001` (ปากกา), `MAT-1002` (กระดาษ)
- Invalid Material: `MAT-9999`
- `PR_CREATOR` = สร้าง PR ได้; `VIEWER` = ดูข้อมูลอย่างเดียว
- Quantity เป็นจำนวนเต็มบวก; Required Date รูปแบบ YYYY-MM-DD
- ข้อความ Error เป็นตัวอย่าง ไม่ใช่ข้อความมาตรฐาน SAP

## Out of Scope
PR Approval, PO, Unit of Measure หลายประเภท, Cost Center, SAP Customizing, Integration และ SAP Authorization Objects จริง