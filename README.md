# SAP Manual Testing Portfolio — Purchase Requisition (Simulation)

> **Simulation / Test Design Only:** กรณีศึกษาจำลองที่ได้รับแรงบันดาลใจจาก SAP S/4HANA ไม่ได้เข้าถึงหรือทดสอบระบบ SAP จริง และไม่ได้อ้างว่าข้อกำหนดเหล่านี้เป็นมาตรฐานของ SAP ทุกระบบ

## Project Overview
Portfolio การออกแบบ Manual Testing สำหรับการสร้างใบขอซื้อ (Purchase Requisition: PR) แบบหนึ่งรายการสินค้า โดยใช้ Business Rules และข้อมูลจำลอง

## Objectives
- Requirement Analysis และ Test Design
- Positive, Negative, Boundary และ Authorization Testing
- Requirement Traceability
- ตัวอย่าง Bug Reports และ Test Summary ที่แยกสถานการณ์สมมติจากผลจริง

## Scope
**In scope:** Material, Quantity, Required Date, Save PR และสิทธิ์ PR_CREATOR/VIEWER ตามข้อกำหนดจำลอง

**Out of scope:** PR Approval, Purchase Order, Inventory Integration, SAP Configuration, APIs จริง, Performance และ Penetration Testing

## Deliverables
| เอกสาร | รายละเอียด |
|---|---|
| [PR Requirements](requirements/PR-Requirements.md) | 7 Requirements |
| [PR Test Cases](test-cases/PR-Test-Cases.csv) | 10 Test Cases (Not Executed) |
| [BUG-001](bug-reports/BUG-001.md) | Quantity = 0 (Hypothetical) |
| [BUG-002](bug-reports/BUG-002.md) | Unauthorized PR creation (Hypothetical) |
| [Test Summary](test-summary/Test-Summary.md) | Coverage, Traceability และ Execution Status |

## Testing Approach
1. วิเคราะห์ Requirements และกำหนด Test Data จำลอง
2. ออกแบบ Test Scenarios และ Expected Results
3. ตรวจสอบ Requirement-to-Test-Case Traceability
4. เขียนตัวอย่าง Defect Reports โดยไม่อ้างว่าเป็น Bug จริง
5. สรุป Test Design Coverage และข้อจำกัด

## Test Environment
ไม่มี SAP Sandbox หรือ SAP Test Environment; เป็น Desk-based Simulation เท่านั้น จึงไม่มี Actual Result, Screenshot, Log หรือ Pass/Fail จากการ Execute จริง

## Glossary
- **PR:** Purchase Requisition (ใบขอซื้อ)
- **Material:** รหัสสินค้า/วัสดุ
- **Validation:** ตรวจสอบความถูกต้องของข้อมูล
- **Expected Result:** ผลลัพธ์ที่คาดหวัง
- **RBAC:** Role-Based Access Control

## Disclaimer
Business Rules, Role และข้อความ Validation ในเอกสารเป็นสมมติฐานเฉพาะกรณีศึกษา ไม่ใช่ข้อยืนยันพฤติกรรม SAP จริง