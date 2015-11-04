.. title: آموزش HTML بخش 4 .. date: 2011/5/14 18:25:28

تا این‌جای کار یاد گرفتیم‌، که چطور یک ساختار HTML را پیاده سازی کنیم و
چطور به نوشته‌ها ظاهری متناسب با کاربرد و مکانشان در صفحه بدهیم‌. حال در
این بخش قصد داریم نحوه‌ی ایجاد پیوند‌ها را بررسی کنیم‌. پیوند یا لینک‌،
امکان دسترسی و ارجاع آسان کاربر را به صفحات مختلف در سرتاسر وب و یا حتی
در یک صفحه فراهم می‌کند. لذا نحوه‌ی استفاده‌ی درست از تگ‌های پیوند و
ایجاد میانبر‌های مناسب می‌تواند، به کاربری آسان صفحه‌ی وب کمک زیادی کند!
عموما یک لینک در صفحه‌ی HTML ساختاری برابر با چیزی که در زیر می‌بینید
دارد‌: \`\`\`html \<a href="http://shahinism.com"\>Shahin's personal
weblog\</a\> \`\`\` همانطور که می‌بینید تگ A مختص ایجاد پیوند می‌باشد‌.
همچنین برای تعیین مقصد لینک‌، از پارامتر href استفاده می‌شود. در اینجا
لینکی به صورت [Shahin's personal weblog](http://shahinism.com) ایجاد
کردیم‌! حال فرض کنید که می‌خواهیم، این لینک بر روی یک عکس اعمال شود‌، به
طوری که پس از کلیک بر روی عکس‌، کاربر به سمت این وبلاگ راهنمایی شود‌.
برای این کار از تگ a و image به صورت زیر استفاده می‌کنیم‌. \`\`\`html
\<a href="http://shahinism.com"\>\<img src="1.jpg" alt="Shahin's Blog"
/\>\</a\> \`\`\` همانطور که می‌بینید‌، با مخلوط کردن این دو تگ به سادگی
توانستیم بر روی یک عکس مقدار لینک مورد نظر را اعمال کنیم‌. شاید تا کنون
دیده‌اید که بعد از کلید بر روی یک لینک به بخش خاصی از صفحه مثلا به وسط
صفحه‌ی حاضر و یا حتی صفحه‌ی دیگر منتقل می‌شوید‌. این‌جاست که با مفهومی
به نام Anchor یا لنگر آشنا می‌شویم‌. برای درک بهتر موضوع می‌توانید به
[این پست](http://www.midinternet.com/5969 "راهنمای مصور لنگر") خوب در
وبلاگ «‌با اینترنت‌» مراجعه کنید‌، که به صورت عملی در محیط وردپرس این
مفهوم را آموزش داده‌. و حالا ما قصد داریم‌، که آن را از نظر کد بررسی
کنیم‌: برای این‌کار ابتدا باید مقصد را معین کنیم‌. لذا به صورت زیر عمل
می‌کنیم‌: \`\`\`html \<a name="middle"\>\</a\> \`\`\` همانطور که
می‌بینید برای تعیین کردن مقصد به تنهایی از تگ name استفاده کردیم‌.
بدیهیست که می‌توانید با دیگر پارامتر‌هایی که تا کنون یاد گرفتید‌، خواص
دیگری را به این بخش از صفحه بیافزایید‌! و حالا برای لینک کردن به این بخش
از صفحه نیز‌، کافیست به صورت زیر عمل کنیم‌: \`\`\`html \<a
href="\#middle"\>\</a\> \`\`\` همانطور که دیدید کافیست که جلوی آدرس
مقصد‌، اسم مقصد را بعد از یک \# قرار دهیم‌. همچنین‌، در صورتی که بخواهید
از صفحه‌ی دیگری به این لنگر در صفحه‌ لینک کنید‌، کافیست بعد از نوشتن
آدرس صفحه‌، اسم لنگر را بعد از یک \# وارد کنید‌. حتما تا کنون متوجه
شده‌اید که لینک‌ها در صفحه‌های مختلف رنگ‌های مختلفی دارند‌. و در برابر
عمل‌های مختلف با تغییر رنگ واکنش نشان می‌دهند‌. برای تعیین این رنگ‌ها
می‌توانید از پارمتر‌های Alink, Vlink در تگ body استفاده کنید‌، که به
ترتیب تعیین کننده‌ی رنگ لینک‌های رویت شده‌، رنگ لینک‌های رویت نشده
می‌باشند‌. نمونه‌ای از استفاده از این پارامتر‌ها را در نمونه‌ی زیر
می‌بینید‌: \`\`\`html \<body alink=yellow vlink=Red\> \</body\> \`\`\`
رنگ‌لینک‌ها در این صفحه زرد تعیین شده و رنگ لینک‌هایی که قبلا رویت شده‌،
قرمز می‌شود‌. حال اگر بخواهیم‌ که کاربر این توانایی را داشته باشد که با
کلید Tab بین لینک‌ها پیمایش کند‌، می‌توانیم با اختصاص پارامتر tabindex
به تگ A و تعیین یک شماره‌، ترتیب پیمایش را معین کنیم‌: \`\`\`html \<a
href="http://shahinism.com" tabindex=1\>Shahinism\</a\> \<a
href="http://google.com" tabindex=2\>Google\</a\> \`\`\` و اگر بخواهیم
این قابلیت را به کاربر بدهیم که بتواند با کلید‌های کیبورد لینک مورد نظر
را انتخاب کند‌، یا به عبارتی میانبری برای کیبورد تعیین کنیم به صورت زیر
از تگ Accesskey استفاده می‌کنیم‌: \`\`\`html \<a
href="http://shahinism.com" tabindex=1 accesskey=s\>Shahinism\</a\> \<a
href="http://google.com" tabindex=2 accesskey=g\>Google\</a\> \`\`\` در
این کد کاربر می‌تواند با زدن کلید S به سایت شاهینیسم و کلید G به سابت
گوگل برود‌. لازم به ذکر است که در مرورگر IE باید برای استفاده از این
کلید‌ها از آن‌ها به صورت ترکیبی با کلید Alt استفاده شود‌. نکته‌ی آخر این
که اگر می‌خواهید برای لینک خود یک لیبل تعیین کنید می‌توانید از تگ title
همانطور که برای عکس‌ها در دروس قبل استفاده می‌شد‌، استفاده کنید‌.