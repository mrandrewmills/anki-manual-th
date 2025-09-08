# Anki ไม่เลือกธีม GTK บน Gnome/Linux

คุณสามารถแก้ไขปัญหานี้ได้โดยบอก Anki อย่างชัดเจนว่าธีม GTK คืออะไร เรียกใช้คำสั่งต่อไปนี้ในเทอร์มินัล:

```shell
theme=$(gsettings get org.gnome.desktop.interface gtk-theme)
echo "gtk-theme-name=$theme" >> ~/.gtkrc-2.0
echo "export GTK2_RC_FILES=$HOME/.gtkrc-2.0" >> ~/.profile
```

จากนั้นออกจากระบบและกลับเข้าสู่ระบบคอมพิวเตอร์ของคุณอีกครั้ง และ Anki ควรจะเลือกธีม GTK
