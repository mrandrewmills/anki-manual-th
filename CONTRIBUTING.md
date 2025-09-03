# การมีส่วนร่วมกับคู่มือ Anki

## การพัฒนาในเครื่อง

anki-manual ถูกสร้างขึ้นโดยใช้ [mdBook](https://rust-lang.github.io/mdBook/), ซึ่งเป็นเครื่องมือจากภาษา Rust สำหรับสร้างเว็บไซต์จาก Markdown

### การติดตั้งโปรแกรมที่จำเป็น

เพื่อใช้งาน mdBook โปรดตรวจสอบให้แน่ใจก่อนว่าคุณได้ติดตั้ง [Rust](https://www.rust-lang.org/tools/install) บนเครื่องของคุณแล้ว

จากนั้นให้ติดตั้ง mdBook และ pre-processor ต่าง ๆ ดังนี้:
```
cargo install mdbook
cargo install mdbook-toc
cargo install mdbook-linkcheck
```

### การพัฒนาและดูตัวอย่าง

หากต้องการให้ anki-manual ทำงานในเครื่อง ให้เริ่มด้วยการ build หนังสือด้วยคำสั่ง:

```
mdbook build
```

จากนั้นให้เรียกใช้งาน anki-manual พร้อมเปิดหน้าแสดงผลด้วยคำสั่ง:

```
mdbook serve --open
```

ตอนนี้คุณสามารถแก้ไขไฟล์ Markdown (`*.md`) ในโฟลเดอร์ `src/` และดูผลลัพธ์การเปลี่ยนแปลงได้แบบเรียลไทม์ผ่านเบราว์เซอร์ของคุณ
