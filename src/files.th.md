# การจัดการไฟล์และคอลเลกชันของคุณ

<!-- toc -->

## การตรวจสอบคอลเลกชันของคุณ

เป็นความคิดที่ดีที่จะตรวจสอบไฟล์คอลเลกชันของคุณเป็นครั้งคราวเพื่อหาปัญหา คุณสามารถทำได้ผ่านรายการเมนู Tools>Check Database (เครื่องมือ>ตรวจสอบฐานข้อมูล) การตรวจสอบฐานข้อมูลทำให้แน่ใจว่าไฟล์ไม่ได้รับความเสียหาย สร้างโครงสร้างภายในบางอย่างขึ้นมาใหม่ และปรับให้ไฟล์มีประสิทธิภาพสูงสุด

เมื่อคุณตรวจสอบฐานข้อมูล รายการแท็กของคุณจะถูกสร้างขึ้นใหม่ด้วย เมื่อคุณลบสำรับไพ่หรือการ์ดแต่ละใบ Anki จะไม่อัปเดตรายการแท็กที่ใช้แล้ว เนื่องจากไม่มีประสิทธิภาพ หากคุณต้องการล้างแท็กเก่าที่ไม่ได้ใช้งานออกจากรายการ การตรวจสอบฐานข้อมูลของคุณคือวิธีที่จะทำ

โปรดทราบว่า Anki จะปรับคอลเลกชันของคุณให้เหมาะสมโดยอัตโนมัติทุกๆ 2 สัปดาห์ การปรับให้เหมาะสมนี้ช่วยให้แน่ใจว่าคอลเลกชันทำงานได้ดี แต่จะไม่ตรวจสอบข้อผิดพลาดหรือสร้างรายการแท็กใหม่เมื่อปรับให้เหมาะสมโดยอัตโนมัติ

<a id="file-locations"></a>

## ข้อมูลผู้ใช้

บน **Windows** Anki เวอร์ชันล่าสุดจะจัดเก็บไฟล์คอลเลกชันของคุณในโฟลเดอร์ appdata ของคุณ คุณสามารถเข้าถึงได้โดยเปิดตัวจัดการไฟล์และพิมพ์ `%APPDATA%\Anki2` ในช่องตำแหน่งที่ตั้ง Anki เวอร์ชันเก่าจะจัดเก็บไฟล์ Anki ของคุณในโฟลเดอร์ชื่อ `Anki` ในโฟลเดอร์ `Documents` ของคุณ

บนคอมพิวเตอร์ **Mac** Anki เวอร์ชันล่าสุดจะจัดเก็บข้อมูลผู้ใช้ทั้งหมดในโฟลเดอร์ `~/Library/Application Support/Anki2` โฟลเดอร์ Library จะถูกซ่อนไว้โดยค่าเริ่มต้น แต่สามารถเปิดเผยได้ใน Finder โดยกดปุ่ม option ค้างไว้ขณะคลิกที่เมนู Go หากคุณใช้ Anki เวอร์ชันเก่า ไฟล์ Anki ของคุณจะอยู่ในโฟลเดอร์ `Documents/Anki`

บน **Linux** Anki เวอร์ชันล่าสุดจะจัดเก็บข้อมูลผู้ใช้ของคุณใน `~/.local/share/Anki2` หรือ `$XDG_DATA_HOME/Anki2` หากคุณได้ตั้งค่าเส้นทางข้อมูลที่กำหนดเอง หากคุณใช้ **Flatpak** build ของบุคคลที่สาม ไฟล์ของคุณจะอยู่ใน `~/.var/app/net.ankiweb.Anki/data/Anki2/` Anki เวอร์ชันเก่าจะจัดเก็บไฟล์ของคุณใน `~/Documents/Anki` หรือ `~/Anki`

ภายในโฟลเดอร์ Anki การตั้งค่าระดับโปรแกรมและระดับโปรไฟล์จะถูกจัดเก็บไว้ในไฟล์ชื่อ `prefs.db`

นอกจากนี้ยังมีโฟลเดอร์แยกต่างหากสำหรับแต่ละโปรไฟล์ โฟลเดอร์ประกอบด้วย:

- บันทึกย่อ สำรับไพ่ การ์ด และอื่นๆ ของคุณในไฟล์ชื่อ `collection.anki2`
- เสียงและรูปภาพของคุณในโฟลเดอร์ `collection.media`
- โฟลเดอร์สำรองข้อมูล
- ไฟล์ระบบบางไฟล์

คุณไม่ควรคัดลอกหรือย้ายคอลเลกชันของคุณในขณะที่ Anki เปิดอยู่ การทำเช่นนั้นอาจทำให้คอลเลกชันของคุณเสียหายได้ โปรดอย่าย้ายหรือแก้ไขไฟล์อื่นๆ ในโฟลเดอร์ด้วย

## ไฟล์โปรแกรม

ตัวเรียกใช้งานของ Anki ได้รับการติดตั้งในตำแหน่งต่อไปนี้โดยค่าเริ่มต้น:

- Windows: `%LOCALAPPDATA%\Programs\Anki`
- macOS: `/Applications/Anki.app`
- Linux: `/usr/local/share/anki`

เมื่อคุณติดตั้ง/อัปเดต Anki ด้วยตัวเรียกใช้งาน มันจะดาวน์โหลดไฟล์สนับสนุนและวางไว้ในตำแหน่งต่อไปนี้:

- Windows: `%LOCALAPPDATA%\AnkiProgramFiles`
- macOS: `~/Library/Application Support/AnkiProgramFiles`
- Linux: `~/.local/share/AnkiProgramFiles`

การลบโฟลเดอร์นั้นจะทำให้ตัวเรียกใช้งานทำงานเหมือนกับการติดตั้งใหม่

`AnkiProgramFiles` มีไฟล์ทั้งหมดที่จำเป็นในการรัน Anki นอกเหนือจากตัวเรียกใช้งาน คุณสามารถคัดลอกไปยังโฟลเดอร์หรือระบบอื่น และเริ่ม Anki จากตำแหน่งใหม่โดยเปิด `AnkiProgramFiles/.venv/bin/anki` (หรือ `AnkiProgramFiles\.venv\scripts\anki` บน Windows) หากวางไว้ในตำแหน่งมาตรฐานบนคอมพิวเตอร์เครื่องใหม่ ตัวเรียกใช้งานจะสามารถใช้ไฟล์ที่มีอยู่ซ้ำได้เช่นกัน โดยมีเงื่อนไขว่าไฟล์ถูกคัดลอกโดยรักษาวันที่แก้ไขไว้

ดูส่วนแฟลชไดรฟ์ด้านล่างสำหรับข้อมูลเพิ่มเติม

## ตัวเลือกการเริ่มต้น

หากคุณได้ทำการเปลี่ยนแปลงที่ทำลายล้างบนคอมพิวเตอร์เครื่องหนึ่งและมีสำเนาที่ไม่เสียหายบนคอมพิวเตอร์เครื่องอื่น คุณอาจต้องการเริ่ม Anki โดยไม่ต้องซิงค์เพื่อใช้ตัวเลือกการซิงค์แบบเต็มโดยไม่ต้องดาวน์โหลดการเปลี่ยนแปลงก่อน ในทำนองเดียวกัน หากคุณประสบปัญหากับ Anki คุณอาจต้อง (หรืออาจได้รับคำแนะนำให้) ปิดใช้งานส่วนเสริมชั่วคราวเพื่อดูว่ามีส่วนเสริมใดที่อาจเป็นสาเหตุของปัญหาหรือไม่ ในการทำทั้งสองอย่างนี้พร้อมกัน คุณสามารถเปิด Anki ในเซฟโหมดได้โดยกดปุ่ม <kbd>Shift</kbd> ค้างไว้ขณะเริ่ม Anki กด <kbd>Shift</kbd> ค้างไว้จนกว่าข้อความบนหน้าจอจะแจ้งให้คุณทราบว่า Anki ได้เริ่มทำงานในเซฟโหมดแล้ว

เป็นไปได้ที่จะระบุตำแหน่งโฟลเดอร์ที่กำหนดเองระหว่างการเริ่มต้น นี่เป็นคุณสมบัติขั้นสูงที่มีไว้เพื่อใช้กับการติดตั้งแบบพกพาเป็นหลัก และเราขอแนะนำให้คุณใช้ตำแหน่งเริ่มต้นในสถานการณ์ส่วนใหญ่

ไวยากรณ์ในการระบุโฟลเดอร์อื่นมีดังนี้:

    anki -b /path/to/anki/folder

- หากคุณมีหลายโปรไฟล์ คุณสามารถส่ง -p <name> เพื่อโหลดโปรไฟล์เฉพาะได้
- หากคุณส่ง -p some-fake-name Anki จะแสดงหน้าจอโปรไฟล์เมื่อเริ่มต้น หากไม่มีโปรไฟล์ให้ไว้ โปรไฟล์ที่ใช้ล่าสุดจะถูกโหลด
- ในการเปลี่ยนภาษาของอินเทอร์เฟซ ให้ใช้ -l <รหัสภาษา iso 639-1> เช่น "-l ja" สำหรับภาษาญี่ปุ่น

หากคุณต้องการใช้ตำแหน่งโฟลเดอร์ที่กำหนดเองเสมอ คุณสามารถแก้ไขทางลัดไปยัง Anki ของคุณได้ บน Windows ให้คลิกขวาที่ทางลัด เลือก Properties เลือกแท็บ Shortcut และเพิ่ม "-b \\path\\to\\data\\folder" หลังเส้นทางไปยังโปรแกรม ซึ่งควรจะทำให้คุณได้บางอย่างเช่น

    "C:\Program Files\Anki\anki.exe" -b "C:\AnkiDataFolder"

คุณยังสามารถใช้เทคนิคนี้กับตัวเลือก -l เพื่อใช้ Anki ในภาษาต่างๆ ได้อย่างง่ายดาย

บน Windows คุณควรใช้เครื่องหมายแบ็กสแลช (\\) ไม่ใช่เครื่องหมายทับ (/)

บน Mac ไม่มีวิธีง่ายๆ ในการเปลี่ยนพฤติกรรมเมื่อคลิกที่ไอคอน Anki แต่เป็นไปได้ที่จะเริ่ม Anki ด้วยโฟลเดอร์ฐานที่กำหนดเองจากเทอร์มินัล:

    open /Applications/Anki.app --args -b ~/myankifolder

อีกทางหนึ่ง คุณสามารถกำหนดตัวแปรสภาพแวดล้อม "ANKI_BASE" ได้ บน Windows คุณสามารถกำหนดตัวแปรสภาพแวดล้อมด้วย:

    set "ANKI_BASE=C:/path/to/AnkiDataFolder"

บน Linux และ macOS คุณสามารถใช้:

    export ANKI_BASE="/path/to/AnkiDataFolder"

## DropBox และการซิงค์ไฟล์

เราไม่แนะนำให้คุณซิงค์โฟลเดอร์ Anki ของคุณโดยตรงกับบริการซิงโครไนซ์ของบุคคลที่สาม เนื่องจากอาจทำให้ฐานข้อมูลเสียหายได้เมื่อไฟล์ถูกซิงค์ขณะใช้งาน

หากคุณเพียงต้องการซิงโครไนซ์สื่อของคุณ คุณสามารถเชื่อมโยงโฟลเดอร์ภายนอกเข้ากับบริการต่างๆ เช่น DropBox ได้ โปรดดู [DropboxWiki: Sync Folders Outside Dropbox (archive.org)][dropboxwiki-sync-other] สำหรับข้อมูลเพิ่มเติม

[dropboxwiki-sync-other]: http://web.archive.org/web/20180919153730/http://www.dropboxwiki.com/tips-and-tricks/sync-other-folders

หากคุณต้องการให้คอลเลกชันของคุณซิงค์อยู่เสมอ ขอแนะนำอย่างยิ่งให้คุณสร้างสคริปต์ที่คัดลอกไฟล์ของคุณจากโฟลเดอร์ที่ซิงค์ไปยังโฟลเดอร์ในเครื่อง เปิด Anki แล้วคัดลอกไฟล์กลับเมื่อ Anki ปิดลง ซึ่งจะช่วยให้แน่ใจว่าไฟล์จะไม่ถูกซิงโครไนซ์ในขณะที่เปิดอยู่

## ระบบไฟล์เครือข่าย

เราขอแนะนำอย่างยิ่งให้คุณให้ Anki จัดเก็บไฟล์ของคุณบนฮาร์ดดิสก์ในเครื่อง เนื่องจากระบบไฟล์เครือข่ายอาจทำให้ฐานข้อมูลเสียหายได้ หากระบบไฟล์เครือข่ายเป็นทางเลือกเดียวของคุณ ขอแนะนำให้ใช้ Tools>Check Database เป็นประจำเพื่อตรวจหาความเสียหาย

## การทำงานจากแฟลชไดรฟ์

บน Windows สามารถติดตั้ง Anki บนไดรฟ์ USB / แฟลชและทำงานเป็นแอปพลิเคชันแบบพกพาได้ ตัวอย่างต่อไปนี้สมมติว่าไดรฟ์ USB ของคุณคือไดรฟ์ G โปรดตรวจสอบให้แน่ใจว่าคุณได้อ่านส่วนไฟล์โปรแกรมด้านบนแล้ว

- คัดลอกโฟลเดอร์ `AnkiProgramFiles` ไปยังแฟลชไดรฟ์ เพื่อให้คุณมีโฟลเดอร์เช่น `G:\Anki`
- สร้างไฟล์ข้อความชื่อ `G:\anki.bat` ด้วยข้อความต่อไปนี้:

  `g:\anki\.venv\scripts\pythonw -c '''import aqt; aqt.run()''' -b g:\ankidata`

- การดับเบิลคลิกที่ `anki.bat` ควรจะเริ่ม Anki โดยมีข้อมูลผู้ใช้จัดเก็บไว้ใน `G:\\ankidata`

การซิงค์สื่อกับ AnkiWeb อาจไม่ทำงานหากแฟลชไดรฟ์ของคุณฟอร์แมตเป็น FAT32 โปรดฟอร์แมตไดรฟ์เป็น NTFS เพื่อให้แน่ใจว่าสื่อซิงค์อย่างถูกต้อง

## การสำรองข้อมูล

โปรดดู [ส่วนนี้](./backups.th.md)

## ฮาร์ดดิสก์ที่ไม่สามารถเข้าถึงได้

หาก Anki ไม่สามารถเขียนไฟล์ใน [โฟลเดอร์ Anki](#user-data) ได้ ข้อความจะแสดงขึ้นเมื่อเริ่มต้นโดยระบุว่า Anki ไม่สามารถเขียนไปยังฮาร์ดดิสก์ได้ และ Anki จะปิดลง หากคุณไม่แน่ใจว่าจะแก้ไขสิทธิ์ได้อย่างไร โปรดติดต่อผู้ที่มีความรู้เกี่ยวกับคอมพิวเตอร์ใกล้ตัวคุณและสามารถช่วยเหลือคุณได้

## สิทธิ์ของโฟลเดอร์ชั่วคราว

Anki ใช้โฟลเดอร์ชั่วคราวของระบบเพื่อจัดเก็บข้อมูลชั่วคราว หากสิทธิ์ของโฟลเดอร์นี้ถูกเปลี่ยนแปลงจากการตั้งค่าเริ่มต้นโดยแอปที่ไม่ประสงค์ดีหรือแอปป้องกันไวรัสที่มีข้อบกพร่อง Anki จะทำงานไม่ถูกต้อง

หากคุณใช้เครื่อง Windows 7 ขั้นตอนทั่วไปในการแก้ไขปัญหามีดังต่อไปนี้ เนื่องจากค่อนข้างซับซ้อน โปรดสอบถามผู้ที่มีความรู้เกี่ยวกับ Windows หากคุณไม่แน่ใจ

1. คลิกที่แถบเริ่มต้นและพิมพ์ %temp% (รวมเครื่องหมายเปอร์เซ็นต์) แล้วกด <kbd>Enter</kbd>
2. ไปที่โฟลเดอร์ด้านบนหนึ่งโฟลเดอร์และค้นหาโฟลเดอร์ temp คลิกขวาที่โฟลเดอร์แล้วเลือก Properties
3. ในแท็บ security คลิกที่ Advanced
4. คลิกที่แท็บ Owner หากคุณไม่ได้ระบุว่าเป็นเจ้าของ ให้คลิกปุ่มเพื่อรับสิทธิ์ความเป็นเจ้าของ
5. ในแท็บ permissions ตรวจสอบให้แน่ใจว่าคุณมีการควบคุมเต็มรูปแบบ ในการติดตั้ง W7 เริ่มต้น การควบคุมจะถูกสืบทอดมาจาก c:\\users\\your-username

## คอลเลกชันที่เสียหาย

Anki ใช้รูปแบบไฟล์ที่ทนทานต่อการขัดข้องของโปรแกรมและคอมพิวเตอร์ แต่ก็ยังเป็นไปได้ที่คอลเลกชันของคุณจะเสียหายได้หากไฟล์ถูกแก้ไขในขณะที่ Anki เปิดอยู่ จัดเก็บไว้ในไดรฟ์เครือข่าย หรือเสียหายจากข้อบกพร่อง

เมื่อคุณเรียกใช้ Tools>Check Database คุณจะได้รับข้อความหาก Anki ตรวจพบว่าไฟล์ได้รับความเสียหาย **วิธีที่ดีที่สุดในการกู้คืนจากปัญหานี้คือการกู้คืนจาก [การสำรองข้อมูลอัตโนมัติล่าสุด](#backups)** แต่ถ้าการสำรองข้อมูลของคุณเก่าเกินไป คุณสามารถพยายามซ่อมแซมความเสียหายแทนได้

บน Linux ตรวจสอบให้แน่ใจว่าได้ติดตั้ง sqlite3 แล้ว บน Mac ควรจะติดตั้งไว้แล้ว บน Windows ให้ดาวน์โหลด <http://www.sqlite.org/sqlite-3_6_23.zip>

ถัดไป สร้างการสำรองข้อมูลของไฟล์ collection.anki2 ของคุณ ในกรณีที่เกิดข้อผิดพลาดกับขั้นตอนด้านล่าง

### Linux/macOS

เปิดเทอร์มินัล เปลี่ยนไปยังโฟลเดอร์ที่คอลเลกชันของคุณตั้งอยู่ และพิมพ์:

    sqlite3 collection.anki2 .dump > dump.txt

เปิดไฟล์ dump.txt ที่ได้ในโปรแกรมแก้ไขข้อความ และดูที่บรรทัดสุดท้าย หากอ่านว่า "rollback;" ให้เปลี่ยนเป็น "commit;"

จากนั้นรันคำสั่งต่อไปนี้ในเทอร์มินัล:

    cat dump.txt | sqlite3 temp.file

ตรวจสอบให้แน่ใจว่าคุณใช้ temp.file - อย่าใส่ collection.anki2 ทางด้านขวา มิฉะนั้นคุณจะล้างไฟล์ เมื่อคุณทำเสร็จแล้ว ให้ไปยังขั้นตอนสุดท้าย

### Windows

คัดลอกโปรแกรม `sqlite3.exe` และสำรับไพ่ของคุณไปยังเดสก์ท็อปของคุณ จากนั้นไปที่ **Start>Run** และพิมพ์ `cmd.exe`

หากคุณใช้ Windows เวอร์ชันล่าสุด พรอมต์คำสั่งอาจไม่เริ่มทำงานบนเดสก์ท็อปของคุณ หากคุณไม่เห็นเดสก์ท็อปแสดงในพรอมต์คำสั่ง ให้พิมพ์บางอย่างเช่นต่อไปนี้ โดยแทนที่ "administrator" ด้วยชื่อล็อกอินของคุณ

    cd C:\Users\Administrator\Desktop

จากนั้นพิมพ์:

    sqlite3 collection.anki2 .dump > dump.txt

เปิดไฟล์ dump.txt ที่ได้ในโปรแกรมแก้ไขข้อความ และดูที่บรรทัดสุดท้าย หากอ่านว่า "rollback;" ให้เปลี่ยนเป็น "commit;"

จากนั้นรันคำสั่งต่อไปนี้ในเทอร์มินัล:

    type dump.txt | sqlite3 temp.file

ตรวจสอบให้แน่ใจว่าคุณใช้ temp.file - อย่าใส่ collection.anki2 ทางด้านขวา มิฉะนั้นคุณจะล้างไฟล์ เมื่อคุณทำเสร็จแล้ว ให้ไปยังขั้นตอนสุดท้าย

### ขั้นตอนสุดท้าย

ตรวจสอบว่าคุณไม่ได้รับข้อความแสดงข้อผิดพลาด และ temp.file ไม่ว่างเปล่า กระบวนการนี้จะปรับคอลเลกชันให้เหมาะสมในกระบวนการ ดังนั้นจึงเป็นเรื่องปกติที่ไฟล์ใหม่จะมีขนาดเล็กกว่าไฟล์เก่าเล็กน้อย

เมื่อคุณยืนยันแล้วว่าไฟล์ไม่ว่างเปล่า:

- เปลี่ยนชื่อไฟล์ collection.anki2 เดิมเป็นอย่างอื่น
- เปลี่ยนชื่อ temp.file เป็น collection.anki2
- ย้าย collection.anki2 กลับเข้าไปในโฟลเดอร์คอลเลกชันของคุณ โดยเขียนทับเวอร์ชันเก่า
- เริ่ม Anki และไปที่ Tools>Check Database เพื่อให้แน่ใจว่าคอลเลกชันได้รับการกู้คืนเรียบร้อยแล้ว
