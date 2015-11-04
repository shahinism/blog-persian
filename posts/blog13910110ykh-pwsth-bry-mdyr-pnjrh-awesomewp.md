.. title: یک پوسته برای مدیر پنجره Awesome .. date: 2012/3/29 21:44:1

قبلا در مورد[نصب مدیر پنجره
Awesome](http://shahinism.com/blog/1391/01/06/%d9%86%d8%b5%d8%a8-awesome-wm-%d8%b1%d9%88%db%8c-%d8%a7%d8%b3%d9%84%da%a9%d9%88%d8%b1/ "نصب Awesome WM روی اسلکور")صحبت
کردیم‌. اما متاسفانه پوسته پیش‌فرض این مدیر پنجره چندان چنگی به دل
نمی‌زند. از طرفی چون عمده کسانی که احتمالا این مدیرپنجره رو امتحان
می‌کنند مهاجران از KDE یا Gnome هستند‌، انتظار بالایی هم از این مدیر
پنجره جدید دارند. خودم اولین پوسته‌ای که استفاده کردم و کلا درکم رو نسبت
به ویرایش پوسته Awesome بیشتر کرد‌، ویرایش علی موسوی (tuxitop) عزیز از
پوسته‌ی zenburn پیش‌فرض Awesome بود‌. (‌~~الان هر چی گشتم لینکش رو پیدا
کنم نشد :-(~~ خودش لطف کرد[لینک
جدید](https://gitorious.org/awesome-configs)رو داد ;-)) پوسته‌ی فعلی من
روی Awesome از اسکرین شات زیر قابل مشاهده است:

![](https://github.com/shahinism/.configs/raw/master/Awesome-wm-theme/snapshot.png)

امکاناتش هم به شرح زیر:

-   یک ترمینال مثل yakuake در KDE که با Mod+F12 باز می‌شود. که البته از
    terminator به عنوان ترمینال استفاده می‌کند که در صورت موجود نبودنش
    روی سیستم‌تان باید نصبش کنید.
-   یک سری ویجت در نوار ابزار که اطلاعات سخت‌افزاری سیستم و شبکه را به
    نمایش می‌گذارند.
-   میانبر پیش‌فرض Alt+Shift برای تغییر کیبرد بین فارسی و انگلیسی.

برای نصب هم باید به صورت زیر عمل کرد([لینک پوسته روی
Git](https://github.com/shahinism/.configs/tree/master/Awesome-wm-theme)):
\`\`\`bash \$ git clone https://github.com/shahinism/Awesome-wm-theme \$
mv \~/.config/awesome \~/.config/awesome.back \$ mv Awesome-wm-theme
\~/.config/awesome \$ cd \~/.config/awesome \$ git clone
http://git.sysphere.org/vicious \$ git clone
https://github.com/cedlemo/blingbling.git Restart Awesome \`\`\` همانطور
که می‌بینید برای این پوسته دو افزونه vicious و blingblind (کشته‌ی اسمشم)
را نیز نصب کردیم‌. **ویرایش یک:** به یاد‌آوری Hamed عزیز نرم‌افزار‌های
کانفیگ شده روی این پوسته را در زیر ذکر می‌کنم‌. البته تمامی این
نرم‌افزار‌ها قابل جایگزینی هستند و تنها کافیست فایل rc.lua ویرایش شود‌.
همچنین جدای از لیست نرم‌افزار‌های اختیاری زیر مطمئن شوید که بسته
setxkbmap هم روی سیستم نصب است‌. این بسته برای تغییر لایوت کیبورد مورد
استفاده قرار می‌گیرد‌.

-   terminator به عنوان شبیه ساز ترمینال.
-   dolphin به عنوان فایل منیجر
-   conky برای ویجت روی دسکتاپ

