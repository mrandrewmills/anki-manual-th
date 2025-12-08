# ग्नोम/लिनक्स पर Anki GTK थीम नहीं उठा रहा है

आप इस समस्या को स्पष्ट रूप से Anki को बताकर हल कर सकते हैं कि GTK थीम क्या है। एक टर्मिनल में निम्नलिखित कमांड चलाएँ:

```shell
theme=$(gsettings get org.gnome.desktop.interface gtk-theme)
echo "gtk-theme-name=$theme" >> ~/.gtkrc-2.0
echo "export GTK2_RC_FILES=$HOME/.gtkrc-2.0" >> ~/.profile
```

फिर अपने कंप्यूटर से लॉग आउट करें और वापस लॉग इन करें, और Anki को GTK थीम उठा लेना चाहिए।