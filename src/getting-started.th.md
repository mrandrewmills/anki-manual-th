# เริ่มต้นใช้งาน

<!-- toc -->

## การติดตั้งและอัปเกรด

ระบบนิเวศของ Anki ประกอบด้วย Anki, AnkiMobile, AnkiDroid และ AnkiWeb ซึ่ง
ทั้งหมดนี้เชื่อมโยงจาก [เว็บไซต์ทางการของเรา](https://apps.ankiweb.net)

สำหรับคำแนะนำเกี่ยวกับวิธีการติดตั้งและอัปเกรด Anki สำหรับคอมพิวเตอร์ของคุณ โปรด
อ่านลิงก์ด้านล่าง:

- [Windows](./platform/windows/installing.md)
- [Mac](./platform/mac/installing.md)
- [Linux](./platform/linux/installing.md)

## วิดีโอ

สำหรับวิธีที่รวดเร็วในการทำความเข้าใจ Anki ลองดูวิดีโอแนะนำเหล่านี้
บางวิดีโอสร้างขึ้นด้วย Anki เวอร์ชันก่อนหน้า แต่แนวคิด
ยังคงเหมือนเดิม

- [Shared Decks and Review Basics](http://www.youtube.com/watch?v=QS2G-k2hQyg&yt:cc=on)

- [Syncing](https://www.youtube.com/watch?v=YkiM4DPzSVc&list=PLGgmaKOIHykFoomqkBJAyGiDQ2kyiuTao&yt:cc=on)

- [Switching Card Order](http://www.youtube.com/watch?v=DnbKwHEQ1mA&yt:cc=on)

- [Styling Cards](http://www.youtube.com/watch?v=F1j1Zx0mXME&yt:cc=on)

- [Typing in the Answer](http://www.youtube.com/watch?v=5tYObQ3ocrw&yt:cc=on)

## แนวคิดหลัก

### การ์ด

คู่คำถามและคำตอบเรียกว่า _การ์ด_ คล้ายกับบัตรคำศัพท์กระดาษ
ที่มีคำถามอยู่ด้านหน้าและคำตอบอยู่ด้านหลัง อย่างไรก็ตาม ใน
Anki การ์ดไม่ได้ดูเหมือนการ์ดจริง และเมื่อคุณ
แสดงคำตอบ คำถามจะยังคงมองเห็นได้ตามค่าเริ่มต้น ตัวอย่างเช่น หาก
คุณกำลังเรียนวิชาเคมีพื้นฐาน คุณอาจเห็นคำถามเช่น:

    Q: สัญลักษณ์ทางเคมีของออกซิเจน?

หลังจากตัดสินใจว่าคำตอบคือ O คุณคลิกปุ่ม
"แสดงคำตอบ" และ Anki จะแสดงให้คุณเห็น:

    Q: สัญลักษณ์ทางเคมีของออกซิเจน?
    A: O

หลังจากยืนยันว่าคุณตอบถูก คุณจะบอก Anki ว่าคุณ
จำคำตอบได้ดีแค่ไหน และ Anki จะเลือกเวลาที่จะแสดงการ์ดให้คุณอีกครั้ง ตัวอย่างเช่น Anki อาจตัดสินใจแสดงการ์ดให้คุณอีกครั้งใน 3 วัน ในกรณีนี้ เรากล่าวว่าการ์ดมีช่วงเวลา 3 วัน

#### สถานะของการ์ด

<div id="types-of-cards" />

- **ใหม่ (New):** การ์ดที่คุณดาวน์โหลดหรือสร้างขึ้นเอง แต่ไม่เคยศึกษามาก่อน

- **กำลังเรียนรู้ (Learning):** การ์ดที่เพิ่งเห็นเป็นครั้งแรกเมื่อไม่นานมานี้ และยังคงอยู่ในระหว่างการเรียนรู้

- **ทบทวน (Review):** การ์ดที่คุณเรียนรู้เสร็จแล้ว การ์ดเหล่านี้จะถูกแสดงอีกครั้งหลังจากที่ระยะเวลา (ช่วงเวลา) ของมันผ่านไป
  มีการ์ดทบทวนสองประเภท:
  - **การ์ดใหม่ (Young):** การ์ดใหม่คือการ์ดที่มีช่วงเวลาน้อยกว่า 21 วัน
  - **การ์ดเก่า (Mature):** การ์ดเก่าคือการ์ดที่มีช่วงเวลา 21 วันขึ้นไป

- **เรียนรู้ใหม่ (Relearn):** การ์ดที่คุณลืมในขั้นตอนการทบทวน การ์ดเหล่านี้จะถูกส่งกลับไปยังสถานะการเรียนรู้ใหม่เพื่อเรียนรู้อีกครั้ง

### สำรับ

_สำรับ_ คือกลุ่มของการ์ด คุณสามารถวางการ์ดในสำรับต่างๆ เพื่อ
ศึกษาบางส่วนของชุดการ์ดของคุณ แทนที่จะศึกษาทั้งหมด
ในคราวเดียว แต่ละสำรับสามารถมีการตั้งค่าที่แตกต่างกันได้ เช่น จำนวนการ์ดใหม่
ที่จะแสดงในแต่ละวัน หรือระยะเวลาที่จะรอจนกว่าการ์ดจะถูกแสดงอีกครั้ง

สำรับสามารถมีสำรับอื่น ๆ อยู่ภายในได้ ซึ่งช่วยให้คุณจัดระเบียบสำรับเป็น
โครงสร้างแบบต้นไม้ Anki ใช้เครื่องหมายทวิภาคคู่ ("::") เพื่อแสดงระดับที่แตกต่างกันภายในโครงสร้างสำรับ ตัวอย่างเช่น สำรับที่ชื่อว่า
"Chinese::Hanzi" หมายถึงสำรับ "Hanzi" ซึ่งเป็นส่วนหนึ่งของสำรับ "Chinese"
หากคุณเลือก "Hanzi" การ์ด Hanzi เท่านั้นที่จะถูกแสดง; หาก
คุณเลือก "Chinese" การ์ด Chinese ทั้งหมดจะถูกแสดง รวมถึงการ์ด Hanzi ด้วย

ในการวางสำรับภายในโครงสร้างต้นไม้ คุณสามารถตั้งชื่อโดยใช้เครื่องหมายทวิภาคคู่คั่น
แต่ละระดับ หรือลากและวางสำรับเหล่านั้นภายในรายการสำรับ สำรับที่
ถูกวางไว้ภายในสำรับอื่นมักเรียกว่า "สำรับย่อย" และสำรับระดับบนสุดเรียกว่า "สำรับหลัก"

Anki เริ่มต้นด้วยสำรับที่ชื่อว่า "Default"; การ์ดใดๆ ที่
แยกออกจากสำรับอื่นจะไปอยู่ที่นี่ Anki จะซ่อน
สำรับเริ่มต้นหากไม่มีการ์ดและคุณได้เพิ่มสำรับอื่น ๆ แล้ว
อีกทางหนึ่ง คุณสามารถเปลี่ยนชื่อสำรับนี้และใช้สำหรับการ์ดอื่น ๆ ได้

สำรับในรายการสำรับจะถูกจัดเรียงตามตัวอักษร ซึ่งอาจส่งผลให้
ลำดับที่น่าประหลาดใจหากชื่อสำรับของคุณมีตัวเลข ตัวอย่างเช่น "My Deck 10"
จะมาก่อน "My Deck 9" เนื่องจาก 1 มาก่อน 9 หากคุณต้องการให้ "My deck 9" ปรากฏก่อน คุณสามารถเปลี่ยนชื่อเป็น "My deck 09" ซึ่งจะปรากฏก่อน "My deck 10"

สำรับเหมาะที่สุดสำหรับการจัดเก็บการ์ดในหมวดหมู่กว้างๆ มากกว่า
หัวข้อเฉพาะเจาะจง เช่น "คำกริยาเกี่ยวกับอาหาร" หรือ "บทเรียนที่ 1" สำหรับข้อมูลเพิ่มเติมเกี่ยวกับ
เรื่องนี้ โปรดดูส่วน [การใช้สำรับอย่างเหมาะสม](editing.md#using-decks-appropriately)

สำหรับข้อมูลเกี่ยวกับลำดับของสำรับที่มีผลต่อลำดับการศึกษาการ์ด
โปรดดูส่วน [ลำดับการแสดงผล](studying.md#display-order)

### โน้ตและฟิลด์

เมื่อสร้างบัตรคำศัพท์ มักจะต้องการสร้างการ์ดมากกว่าหนึ่งใบ
ที่เกี่ยวข้องกับข้อมูลเดียวกัน ตัวอย่างเช่น หากคุณกำลังเรียน
ภาษาฝรั่งเศส และคุณเรียนรู้ว่าคำว่า _bonjour_ หมายถึง สวัสดี คุณอาจ
ต้องการสร้างการ์ดหนึ่งใบที่แสดง "bonjour" และขอให้คุณ
จำ "hello" และการ์ดอีกใบที่แสดง "hello" และขอให้คุณ
จำ "bonjour" การ์ดหนึ่งใบกำลังทดสอบความสามารถในการจดจำ
คำภาษาฝรั่งเศส และการ์ดอีกใบกำลังทดสอบความสามารถในการสร้างคำนั้น

เมื่อใช้บัตรคำศัพท์กระดาษ ทางเลือกเดียวของคุณในกรณีนี้คือการเขียน
ข้อมูลสองครั้ง ครั้งละหนึ่งใบสำหรับแต่ละการ์ด โปรแกรมบัตรคำศัพท์บางโปรแกรม
ทำให้ชีวิตง่ายขึ้นโดยการให้คุณสมบัติในการพลิกด้านหน้าและด้านหลัง
นี่เป็นการปรับปรุงจากสถานการณ์กระดาษ แต่มีข้อเสียหลักสองประการ:

- เนื่องจากโปรแกรมดังกล่าวไม่ได้ติดตามประสิทธิภาพการจดจำ
  และการสร้างของคุณแยกกัน การ์ดจึงมักจะไม่ถูกแสดงให้คุณเห็นใน
  เวลาที่เหมาะสมที่สุด ซึ่งหมายความว่าคุณลืมมากกว่าที่คุณต้องการ หรือคุณ
  ศึกษามากกว่าที่จำเป็น

- การกลับคำถามและคำตอบใช้ได้เฉพาะเมื่อคุณต้องการ
  เนื้อหาเดียวกันทุกประการในแต่ละด้าน ซึ่งหมายความว่าไม่สามารถ
  แสดงข้อมูลเพิ่มเติมที่ด้านหลังของการ์ดแต่ละใบได้ ตัวอย่างเช่น

Anki แก้ปัญหาเหล่านี้โดยอนุญาตให้คุณแบ่งเนื้อหาของการ์ดของคุณ
ออกเป็นข้อมูลแยกส่วน จากนั้นคุณสามารถบอก Anki
ว่าข้อมูลส่วนใดที่คุณต้องการให้แสดงบนด้านหน้าหรือ
ด้านหลังของการ์ดแต่ละใบ และ Anki จะดูแลการสร้างการ์ดให้คุณ และอัปเดตหากคุณทำการแก้ไขใดๆ
ในอนาคต

ลองจินตนาการว่าเราต้องการศึกษาคำศัพท์ภาษาฝรั่งเศส และเราต้องการรวมหมายเลขหน้าหนังสือเรียน
ไว้ที่ด้านหลังของการ์ดแต่ละใบ เราต้องการให้การ์ดของเรามีลักษณะดังนี้:

    Q: Bonjour
    A: Hello
       Page #12

และแบบนี้:

    Q: Hello
    A: Bonjour
       Page #12

ในการ์ดทั้งสองใบ เรามีข้อมูลที่เกี่ยวข้องสามส่วนเหมือนกัน: คำภาษาฝรั่งเศส
ความหมายภาษาอังกฤษ และหมายเลขหน้า หากเรารวมเข้าด้วยกัน
จะมีลักษณะดังนี้:

    French: Bonjour
    English: Hello
    Page: 12

ใน Anki ชุดข้อมูลที่เกี่ยวข้องนี้เรียกว่า _โน้ต_ และข้อมูลแต่ละส่วนจะอยู่ใน _ฟิลด์_ ในตัวอย่างนี้ โน้ต
มีสามฟิลด์: "French", "English" และ "Page"

ในการเพิ่มและแก้ไขฟิลด์ ให้คลิกปุ่ม "Fields…​" ขณะเพิ่มหรือ
แก้ไขโน้ต สำหรับข้อมูลเพิ่มเติมเกี่ยวกับฟิลด์ โปรดดูส่วน
[การปรับแต่งฟิลด์](editing.md#customizing-fields)

### ประเภทการ์ด

เพื่อให้ Anki สร้างการ์ดตามโน้ตของเรา เราจำเป็นต้องให้
พิมพ์เขียวที่ระบุว่าฟิลด์ใดควรแสดงบนด้านหน้าหรือ
ด้านหลังของการ์ดแต่ละใบ พิมพ์เขียวนี้เรียกว่า _ประเภทการ์ด_ โน้ตแต่ละประเภท
สามารถมีประเภทการ์ดได้หนึ่งประเภทขึ้นไป; เมื่อคุณเพิ่มโน้ต Anki จะ
สร้างการ์ดหนึ่งใบสำหรับแต่ละประเภทการ์ด

ประเภทการ์ดทั้งหมดมี _เทมเพลต_ สองแบบ แบบหนึ่งสำหรับคำถามและอีกแบบสำหรับ
คำตอบ ในตัวอย่างภาษาฝรั่งเศสก่อนหน้านี้ เราต้องการให้ด้านหลังของการ์ดจดจำของเรา
มีลักษณะดังนี้:

    Q: Bonjour
    A: Hello
       Page #12

ในการทำเช่นนี้ เราสามารถตั้งค่าเทมเพลตคำตอบเป็น:

    Q: {{French}}
    A: {{English}}<br>
       Page #{{Page}}

ในเทมเพลตการ์ด ชื่อฟิลด์จะถูกครอบด้วยวงเล็บปีกกาคู่ เช่น `{{French}}` หรือ `{{English}}` Anki จะแทนที่สิ่งเหล่านั้นด้วยข้อความจริงที่ฟิลด์มีอยู่ นี่เรียกว่า ["การแทนที่ฟิลด์"](templates/fields.md) ข้อความที่ไม่ได้ครอบด้วยวงเล็บปีกกาคู่จะปรากฏเหมือนเดิมในการ์ดแต่ละใบ ตัวอย่างเช่น เราจะไม่จำเป็นต้องเพิ่ม "Page #" ในทุกโน้ต เพราะเทมเพลตจะเพิ่มให้โดยอัตโนมัติในการ์ดทุกใบ แท็ก `<br>` เป็น
รหัสพิเศษที่บอก Anki ให้ขึ้นบรรทัดใหม่ สำหรับรายละเอียด โปรดดูส่วน [เทมเพลต](templates/intro.md)

เทมเพลตของการ์ดผลิตก็จะทำงานในลักษณะเดียวกัน:

    Q: {{English}}
    A: {{French}}<br>
       Page #{{Page}}

หลังจากสร้างประเภทการ์ดแล้ว ทุกครั้งที่คุณเพิ่มโน้ตใหม่ การ์ด
จะถูกสร้างขึ้นตามประเภทการ์ดนั้น ประเภทการ์ดทำให้ง่ายต่อการรักษา
รูปแบบของการ์ดของคุณให้สอดคล้องกัน และสามารถลด
ความพยายามในการเพิ่มข้อมูลได้อย่างมาก นอกจากนี้ยังหมายความว่า Anki สามารถ
ตรวจสอบให้แน่ใจว่าการ์ดที่เกี่ยวข้องไม่ปรากฏใกล้กันเกินไป และยัง
ช่วยให้คุณแก้ไขข้อผิดพลาดในการพิมพ์หรือข้อเท็จจริงได้ในครั้งเดียว และมีการ์ดที่เกี่ยวข้องทั้งหมดอัปเดตพร้อมกัน

ในการเพิ่มและแก้ไขประเภทการ์ด ให้คลิกปุ่ม "Cards…​" ขณะเพิ่มหรือ
แก้ไขโน้ต สำหรับข้อมูลเพิ่มเติมเกี่ยวกับประเภทการ์ด โปรดดูส่วน [การ์ดและเทมเพลต](templates/intro.md)

### ประเภทโน้ต

Anki อนุญาตให้คุณสร้างประเภทโน้ตที่แตกต่างกันสำหรับ
เนื้อหาที่แตกต่างกัน โน้ตแต่ละประเภทมีชุดฟิลด์และประเภทการ์ดของตัวเอง
เป็นความคิดที่ดีที่จะสร้างประเภทโน้ตแยกต่างหากสำหรับแต่ละหัวข้อกว้างๆ
ที่คุณกำลังศึกษา ในตัวอย่างภาษาฝรั่งเศสก่อนหน้านี้ เราอาจสร้างโน้ต
ประเภทที่เรียกว่า "French" สำหรับสิ่งนั้น หากเราต้องการเรียนรู้เมืองหลวง เรา
สามารถสร้างประเภทโน้ตสำหรับสิ่งนั้นได้เช่นกัน โดยมีฟิลด์เช่น
"Country" และ "Capital City"

Anki มาพร้อมกับประเภทโน้ตมาตรฐานบางประเภท
ประเภทโน้ตเหล่านี้มีไว้เพื่อให้ Anki ใช้งานง่ายขึ้นสำหรับ
ผู้ใช้ใหม่ แต่ในระยะยาว ขอแนะนำให้คุณสร้างประเภทโน้ตของคุณเอง
โดยเฉพาะสำหรับเนื้อหาที่คุณกำลังเรียนรู้ ประเภทโน้ตมาตรฐานคือ:

- **พื้นฐาน (Basic)**\
  มีฟิลด์ "Front" และ "Back" และจะสร้างการ์ดหนึ่งใบ ข้อความที่คุณป้อนใน
  "Front" จะปรากฏที่ด้านหน้าของการ์ด และข้อความที่คุณป้อนใน "Back"
  จะปรากฏที่ด้านหลังของการ์ด

- **พื้นฐาน (และการ์ดกลับด้าน) (Basic (and reversed card))**\
  เหมือน "Basic" แต่สร้างการ์ดสองใบสำหรับข้อความที่คุณป้อน:
  หน้า→หลัง และ หลัง→หน้า

- **พื้นฐาน (การ์ดกลับด้านเสริม) (Basic (optional reversed card))**\
  เหมือน "Basic" แต่มีฟิลด์ที่สามชื่อ "Add Reverse" หากคุณป้อนข้อความใดๆ ลงใน
  ฟิลด์นั้น การ์ดกลับด้าน (หลัง→หน้า) ก็จะถูกสร้างขึ้นด้วย สำหรับรายละเอียด โปรดดูส่วน [การ์ดและเทมเพลต](templates/intro.md)

- **พื้นฐาน (พิมพ์คำตอบ) (Basic (type in the answer))**\
  นี่คือ "Basic" โดยพื้นฐานแล้ว โดยมีช่องข้อความเพิ่มเติมที่ด้านหน้าซึ่งคุณ
  สามารถพิมพ์คำตอบของคุณได้ เมื่อคุณเปิดเผยด้านหลัง Anki จะแสดงความแตกต่างใดๆ ระหว่างอินพุตของคุณกับคำตอบจริง สำหรับรายละเอียด โปรดดูส่วน
  [การตรวจสอบคำตอบของคุณ](templates/fields.md#checking-your-answer)

- **Cloze**\
  ประเภทโน้ตที่ช่วยให้คุณสามารถเลือกข้อความและเปลี่ยนเป็น cloze
  deletion (เช่น "มนุษย์ลงจอดบนดวงจันทร์ในปี \[…\]" → "มนุษย์ลงจอดบน
  ดวงจันทร์ในปี 1969") สำหรับรายละเอียด โปรดดูส่วน [cloze deletion](editing.md#cloze-deletion)

- **Image Occlusion**\
  เหมือนกับประเภทโน้ต cloze แต่ทำงานกับรูปภาพแทนข้อความ
  ซึ่งมีประโยชน์อย่างยิ่งเมื่อศึกษาเนื้อหาที่ต้องใช้รูปภาพเป็นหลัก
  เช่น กายวิภาคศาสตร์และภูมิศาสตร์ สำหรับรายละเอียด โปรดดูส่วน [Image Occlusion](editing.md#image-occlusion)
  ของคู่มือ

ในการเพิ่มประเภทโน้ตของคุณเองและแก้ไขประเภทโน้ตที่มีอยู่ คุณสามารถใช้ Tools →
Manage Note Types จากหน้าต่าง Anki หลัก

โน้ตและประเภทโน้ตเป็นเรื่องทั่วไปสำหรับคอลเลกชันทั้งหมดของคุณมากกว่า
ที่จะจำกัดอยู่แค่สำรับเดียว ซึ่งหมายความว่าคุณสามารถใช้
ประเภทโน้ตที่แตกต่างกันในสำรับเดียว หรือมีการ์ดที่สร้างจาก
โน้ตเดียวกันถูกจัดเก็บไว้ในสำรับที่แตกต่างกัน เมื่อคุณเพิ่มโน้ตโดยใช้
หน้าต่าง Add คุณสามารถเลือกประเภทโน้ตที่จะใช้และสำรับที่จะใช้
และตัวเลือกเหล่านี้เป็นอิสระจากกันโดยสิ้นเชิง คุณยังสามารถ
[เปลี่ยนประเภทโน้ตของโน้ต](browsing.md#notes) หลังจากที่คุณสร้างไปแล้ว

### คอลเลกชัน

_คอลเลกชัน_ ของคุณคือเนื้อหาทั้งหมดที่จัดเก็บใน Anki: การ์ดของคุณ
โน้ต สำรับ ประเภทโน้ต ตัวเลือกสำรับ และอื่นๆ

## สำรับที่แชร์

คุณสามารถดูวิดีโอเกี่ยวกับ [Shared Decks and Review Basics](http://www.youtube.com/watch?v=QS2G-k2hQyg&yt:cc=on) บน YouTube

วิธีที่ง่ายที่สุดในการเริ่มต้นใช้งาน Anki คือการดาวน์โหลดสำรับการ์ด
ที่ผู้อื่นแชร์:

1. คลิกปุ่ม "Get Shared" ที่ด้านล่างของรายการสำรับ

2. เมื่อคุณพบสำรับที่คุณสนใจ ให้คลิกปุ่ม "Download"
   เพื่อดาวน์โหลดแพ็คเกจสำรับ

3. ดับเบิลคลิกแพ็คเกจที่ดาวน์โหลดเพื่อนำเข้าสู่ Anki หรือไปที่
   File → Import

หมายเหตุ: ขณะนี้ยังไม่สามารถเพิ่มสำรับที่แชร์
ไปยังบัญชี AnkiWeb ของคุณได้ คุณต้องนำเข้าสำรับเหล่านั้นไปยัง
แอปเดสก์ท็อป AnkiMobile หรือ AnkiDroid ก่อน จากนั้นจึง [ซิงโครไนซ์](./syncing.md) เพื่ออัปโหลดสำรับไปยัง AnkiWeb

การสร้างสำรับของคุณเองเป็นวิธีที่มีประสิทธิภาพที่สุดในการเรียนรู้เรื่องที่ซับซ้อน
วิชาต่างๆ เช่น ภาษาและวิทยาศาสตร์ไม่สามารถเข้าใจได้
เพียงแค่การท่องจำข้อเท็จจริง — คุณต้องมีคำอธิบายและบริบทเพื่อ
เรียนรู้ได้อย่างมีประสิทธิภาพ นอกจากนี้ การป้อนข้อมูลด้วยตัวคุณเอง
จะบังคับให้คุณตัดสินใจว่าประเด็นสำคัญคืออะไร ซึ่งนำไปสู่ความเข้าใจที่ดีขึ้น

หากคุณเป็นผู้เรียนภาษา คุณอาจถูกล่อลวงให้ดาวน์โหลดรายการคำศัพท์ยาวๆ
และคำแปล แต่สิ่งนี้จะไม่สอนภาษาให้คุณ
มากกว่าการท่องจำสมการทางวิทยาศาสตร์จะสอนดาราศาสตร์ฟิสิกส์
ในการเรียนรู้ที่ถูกต้อง คุณอาจต้องใช้หนังสือเรียน ครู หรือ
การสัมผัสกับประโยคในโลกแห่งความเป็นจริง

    อย่าเรียนรู้หากคุณไม่เข้าใจ
    --SuperMemo

สำรับที่แชร์ส่วนใหญ่สร้างขึ้นโดยผู้ที่กำลังเรียนรู้เนื้อหา
นอก Anki เช่น จากหนังสือเรียน ชั้นเรียน ทีวี ฯลฯ พวกเขาเลือก
ประเด็นที่น่าสนใจจากสิ่งที่เรียนรู้และนำไปใส่ใน Anki. พวกเขา
อาจไม่พยายามเพิ่มข้อมูลพื้นฐานหรือคำอธิบายลงในการ์ด
เพราะพวกเขาเข้าใจเนื้อหาอยู่แล้ว ดังนั้นเมื่อผู้อื่น
ดาวน์โหลดสำรับของพวกเขาและพยายามใช้ พวกเขาอาจพบว่ามันยากมาก
เนื่องจากข้อมูลพื้นฐานและคำอธิบายหายไป

นั่นไม่ได้หมายความว่าสำรับที่แชร์ไม่มีประโยชน์ หากคุณกำลังศึกษาหนังสือเรียน ABC และ
มีคนแชร์สำรับแนวคิดจาก ABC นั่นเป็นวิธีที่ดีในการประหยัด
เวลา และสำหรับเรื่องง่ายๆ ที่เป็นเพียงรายการข้อเท็จจริง
เช่น ชื่อเมืองหลวงหรือธงชาติ คุณอาจไม่ต้องการ
เนื้อหาภายนอกใดๆ อย่างไรก็ตาม สำหรับเรื่องที่ซับซ้อน สำรับที่แชร์ควรใช้เป็น _ส่วนเสริม_ ของเนื้อหาภายนอก ไม่ใช่ _สิ่งทดแทน_
