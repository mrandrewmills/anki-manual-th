# জিনোম/লিনাক্সে অ্যাঙ্কি GTK থিম শনাক্ত করতে পারছে না

আপনি অ্যাঙ্কিকে স্পষ্টভাবে GTK থিম কোনটি তা জানিয়ে দিয়ে এই সমস্যাটি সমাধান করতে পারেন। একটি টার্মিনালে নিম্নলিখিত কমান্ডগুলো চালান:

```shell
theme=$(gsettings get org.gnome.desktop.interface gtk-theme)
echo "gtk-theme-name=$theme" >> ~/.gtkrc-2.0
echo "export GTK2_RC_FILES=$HOME/.gtkrc-2.0" >> ~/.profile
```

এরপর আপনার কম্পিউটার থেকে লগ আউট করে আবার লগ ইন করুন, এবং অ্যাঙ্কি GTK থিমটি শনাক্ত করতে পারবে।
