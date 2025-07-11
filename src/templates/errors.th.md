# ข้อผิดพลาด

<!-- toc -->

เมื่อแก้ไขเทมเพลตใน Anki คุณอาจพบข้อผิดพลาดต่างๆ ที่เกิดขึ้นระหว่างการแสดงบัตร ข้อผิดพลาดเหล่านี้มักเกิดจากโค้ด HTML, CSS หรือการใช้งานฟิลด์ในเทมเพลตไม่ถูกต้อง

## ข้อผิดพลาดที่พบบ่อย

- **ฟิลด์ไม่แสดงผล:** ตรวจสอบว่าชื่อฟิลด์ในเทมเพลตตรงกับชื่อฟิลด์ในประเภทโน้ต เช่น `{{Front}}` ต้องมีฟิลด์ชื่อ "Front" จริง
- **HTML ผิดพลาด:** หากมีแท็ก HTML ไม่สมบูรณ์หรือปิดแท็กไม่ถูกต้อง อาจทำให้การแสดงผลผิดปกติ
- **CSS ไม่ทำงาน:** ตรวจสอบไวยากรณ์ CSS และชื่อ class หรือ id ให้ถูกต้อง

## การแก้ไขข้อผิดพลาด

1. ตรวจสอบข้อความแจ้งเตือนหรือข้อผิดพลาดที่ Anki แสดงขณะบันทึกหรือแสดงตัวอย่างบัตร
2. ตรวจสอบชื่อฟิลด์และโครงสร้าง HTML/CSS ในเทมเพลต
3. หากใช้ JavaScript ให้ตรวจสอบว่าโค้ดไม่มีข้อผิดพลาดทางไวยากรณ์

## ตัวอย่างข้อผิดพลาด

- พิมพ์ชื่อฟิลด์ผิด: `{{Frnot}}` แทนที่จะเป็น `{{Front}}`
- ลืมปิดแท็ก HTML: `<div>{{Front}}</div` (ควรเป็น `<div>{{Front}}</div>`)
- CSS ไม่ถูกต้อง: `.card { font-size 20px; }` (ควรเป็น `.card { font-size: 20px; }`)

สำหรับข้อมูลเพิ่มเติมเกี่ยวกับการแก้ไขข้อผิดพลาดในเทมเพลต ดู [คู่มือ Anki](https://docs.ankiweb.net/templates/errors.html)
