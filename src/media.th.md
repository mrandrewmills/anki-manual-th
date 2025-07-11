# สื่อ

Anki จัดเก็บเสียงและรูปภาพที่ใช้ในบันทึกย่อของคุณในโฟลเดอร์ถัดจากคอลเลกชัน สำหรับข้อมูลเพิ่มเติมเกี่ยวกับตำแหน่งของโฟลเดอร์ โปรดดูส่วน [ตำแหน่งไฟล์](files.th.md#user-data) เมื่อคุณเพิ่มสื่อภายใน Anki ไม่ว่าจะโดยใช้ไอคอนคลิปหนีบกระดาษใน [เครื่องมือแก้ไข](editing.th.md) หรือโดยการวางลงในฟิลด์ Anki จะคัดลอกสื่อจากตำแหน่งเดิมไปยังโฟลเดอร์สื่อ ซึ่งทำให้ง่ายต่อการสำรองข้อมูลสื่อของคอลเลกชันของคุณหรือย้ายไปยังคอมพิวเตอร์เครื่องอื่น

หากชื่อไฟล์สื่อของคุณมีช่องว่างหรืออักขระพิเศษอื่นๆ เช่น เครื่องหมายเปอร์เซ็นต์ ลักษณะที่ชื่อไฟล์ปรากฏในเครื่องมือแก้ไข HTML จะแตกต่างจากลักษณะที่ชื่อไฟล์ปรากฏบนดิสก์ ตัวอย่างเช่น ไฟล์ชื่อ `hello 100%.jpg` จะปรากฏเป็น `hello%20100%25.jpg` ในเครื่องมือแก้ไข HTML ภายใน Anki ยังคงใช้ชื่อไฟล์เดิม ดังนั้นหากคุณต้องการ [ค้นหา](searching.th.md) ไฟล์หรือแก้ไขชื่อไฟล์ด้วย [ค้นหาและแทนที่](browsing.th.md#find-and-replace) คุณจะต้องใช้ชื่อตามที่ปรากฏบนดิสก์ ไม่ใช่ตามที่ปรากฏในเครื่องมือแก้ไข HTML การส่งออกเป็นไฟล์ข้อความเป็นอีกวิธีหนึ่งในการดูการแสดงผลพื้นฐาน

## การตรวจสอบสื่อ

คุณสามารถใช้ตัวเลือกเมนู Tools>Check Media เพื่อสแกนบันทึกย่อและโฟลเดอร์สื่อของคุณ ซึ่งจะสร้างรายงานไฟล์ในโฟลเดอร์สื่อที่ไม่ได้ใช้โดยบันทึกย่อใดๆ และสื่อที่อ้างอิงในบันทึกย่อแต่ไม่มีอยู่ในโฟลเดอร์สื่อของคุณ นอกจากนี้ยังช่วยให้คุณ:

- ลบไฟล์สื่อที่ไม่ได้ใช้
- แท็กบันทึกย่อที่อ้างอิงถึงไฟล์สื่อที่หายไป
- ล้างโฟลเดอร์ถังขยะของคุณ
- กู้คืนไฟล์ที่ถูกลบกลับไปยังโฟลเดอร์สื่อของคุณ

เครื่องมือนี้ไม่สแกนเทมเพลตคำถามหรือคำตอบ ซึ่งเป็นเหตุผลว่าทำไมคุณจึงไม่สามารถวางการอ้างอิงสื่อไปยังฟิลด์ในเทมเพลตได้ หากคุณต้องการรูปภาพหรือเสียงแบบคงที่ในการ์ดทุกใบ ให้ตั้งชื่อโดยขึ้นต้นด้วย \_ (เช่น `_dog.jpg`) เพื่อบอกให้ Anki ละเว้นเมื่อตรวจสอบสื่อ หากคุณลบสื่อโดยใช้การตรวจสอบสื่อที่ไม่ได้ใช้ Anki จะย้ายสื่อไปยังโฟลเดอร์ถังขยะของระบบปฏิบัติการของคุณ เพื่อให้คุณสามารถกู้คืนได้หากคุณลบสื่อที่ไม่ควรลบโดยไม่ได้ตั้งใจ

## การเพิ่มสื่อด้วยตนเอง

เมื่อคุณเพิ่มสื่อผ่านอินเทอร์เฟซของ Anki Anki จะดูแลให้แน่ใจว่าชื่อไฟล์ถูกเข้ารหัสในลักษณะที่ควรทำงานได้บนอุปกรณ์ต่างๆ ลบอักขระที่จะไม่ทำงานบนระบบปฏิบัติการบางระบบ และตัดทอนชื่อไฟล์ที่ยาวมาก

หากคุณเพิ่มไฟล์ลงใน [โฟลเดอร์สื่อ](files.th.md#user-data) ของคุณด้วยตนเอง คุณควรใช้ Tools>Check Media ในภายหลัง เพื่อให้แน่ใจว่าชื่อไฟล์ถูกเข้ารหัสอย่างถูกต้อง หากคุณข้ามขั้นตอนนี้ ชื่อไฟล์ใดๆ ที่ไม่เข้ากันจะถูกข้ามไปเมื่อทำการซิงค์

Anki ไม่ติดตามลิงก์สัญลักษณ์ในโฟลเดอร์สื่อเมื่อทำการซิงค์ หากคุณใช้ symlinks ในการรวมแบบอักษร สไตล์ชีต หรือทรัพยากรอื่นๆ ไฟล์เหล่านี้อาจดูเหมือนทำงานได้บนเดสก์ท็อป แต่ล้มเหลวบนมือถือ เพื่อให้แน่ใจว่าไฟล์ซิงค์อย่างถูกต้อง ให้คัดลอกไฟล์จริงลงในโฟลเดอร์ collection.media แทนการใช้ symlinks

## รูปแบบที่รองรับ

Anki ใช้โปรแกรมที่เรียกว่า mpv (และ mplayer เป็นตัวสำรอง) เพื่อรองรับเสียงและวิดีโอ รองรับรูปแบบไฟล์ที่หลากหลาย แต่ไม่ใช่ทุกรูปแบบที่จะทำงานบน AnkiWeb และไคลเอนต์มือถือ เสียง MP3 และวิดีโอ MP4 ดูเหมือนจะเป็นรูปแบบที่รองรับกันอย่างแพร่หลายที่สุด
