.. title: افزودن قابلیت تکمیل خودکار به Emacs .. date: 2012/2/8 5:34:54

یکی از مهم‌ترین قابلیت‌های مورد علاقه‌ی افراد تنبلی هم‌چون من‌، داشتن
قابلیت تکمیل خودکار در هر فرآیند تایپی است‌. مدتی است که تصمیم به دوستی
با ایمکس گرفته‌ام‌، و در همین راستا‌، قصد افزودن این قابلیت را به ایمکس
نیز داشتم‌. حالا هم محض به خاطر سپردن‌، مراحل ساده‌ی کار را در این‌جا
درج می‌کنم‌: آخرین نسخه بسته Auto-complete را از این صفحه
[دانلود](http://cx4a.org/software/auto-complete/index.html#Downloads "emacs auto-complete Downlad page")
کنید‌. و داخل یک پوشه تخلیه‌اش کنید‌. ایمکس را باز کنید‌، و دستور زیر را
وارد کنید‌: \`\`\`bashM-x load-file RET\`\`\` آدرس فایل ‎/etc/install.el
موجود در پوشه‌ی دانلود شده را به ایمکس بدهید‌. برای نمونه من چیزی شبیه
به این را وارد کردم‌:
\`\`\`bash\~/home/shahin/auto-complete/etc/install.el\`\`\` باقی مراحل
را تایید کنید و تمام‌. پیغام زیر را مشاهده می‌کنید‌:
\`\`\`bashSuccessfully installed! Add the following code to your .emacs:
(add-to-list 'load-path "\~/.emacs.d") ; This may not be appeared if you
have already added. (add-to-list 'ac-dictionary-directories
"\~/.emacs.d/ac-dict") (require 'auto-complete-config)
(ac-config-default) \`\`\` همانطور که در توضیحات داده شده زیر تبریک
آمده‌، خط‌های مربوطه را به فایل ‎.emacs موجود در پوشه‌ی خانگی‌تان (‌اگه
نیست بسازید‌) وارد کنید‌. به همین سادگی‌. حالا یک فایل باز کنید و شروع
به تایپ کنید و از قابلیت تکمیل خودکارش لذت ببرید‌. **پی‌نوشت:** جالبیتش
این است که حتی در محیط متنی هم به خوبی عمل می‌کند و نیازتان را بر طرف
می‌سازد ;-) =-=-=-=-= *Powered by
**[Blogilo](http://blogilo.gnufolks.org/)***