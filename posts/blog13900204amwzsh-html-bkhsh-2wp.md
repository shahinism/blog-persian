.. title: آموزش HTML بخش ۲ .. date: 2011/4/24 00:32:15

خوب‌، در [بخش
اول](http://shahinism.com/1390/02/%d8%a2%d9%85%d9%88%d8%b2%d8%b4-html-%d8%a8%d8%ae%d8%b4-%db%b1/ "آموزش HTML بخش ۱")
با ساختار کلی یک سند HTML آشنا شدیم‌، و نحوهٔ ایجاد آن را یاد گرفتیم‌.
در این بخش می‌خواهیم با امکاناتی که برای **تایپوگرافی** در HTML قرار
داده شده آشنا شویم‌. **نکته‌:** بعضی از تگ‌های استفاده شده در این آموزش
در نسخهٔ جدید HTML دیگر جایی ندارند‌، و آن هم به دلیل استفاده از CSS در
کنار HTML است‌. ولی آشنا شدن با آن‌ها می‌تواند کمک فراوانی به یاد‌گیری
سریع‌تر CSS -که در آینده قصد بر آن داریم- کند‌.

### **انواع تیتر‌ها‌:**

در HTML تگ‌هایی برای شناساندن <span style="color: #800080;">**تیتر‌ها**
به مرور‌گر و در نتیجه نمایش مناسب آن‌ها در نظر گرفته شده است که ساختاری
برابر <span style="color: #99cc00;">**\<Hn\>** دارند‌. در این نوع تگ حرف
<span style="color: #ff0000;">**n** برابر با مقداری است که از یک شروع
می‌شود‌، و به نسبت بزرگ‌تر شدن این مقدار‌، اندازهٔ تیتر به کوچک‌تر شدن
میل می‌کند‌. برای درک بهتر این موضوع سعی می‌کنیم‌، در صفحه‌ای که قبلا
ساختیم یک تیتر ایجاد کنیم‌: \`\`\`bash \<html\> \<head\> \<title\>First
HTML!\</title\> \</head\> \<body text="yellow" bgcolor="brown"\>
\<h1\>Hello World\</h1\> \</body\> \</html\> \`\`\` نتیجهٔ این کد برابر
با تصویر زیر می‌باشد‌. همانطور که می‌بینید عبارت Hello World به صورت
بزرگ نوشته شده است‌.
[![](http://shahinism.com/wp-content/uploads/2011/04/html1-7-300x74.png "html1-7")](http://shahinism.com/wp-content/uploads/2011/04/html1-7.png)
برای درک بهتر مقدار n در \<Hn\> از دو مقدار دیگر <span
style="color: #cc99ff;">**\<h2\>\<h3\>** به صورت زیر استفاده می‌کنم‌:
\`\`\`bash \<html\> \<head\> \<title\>First HTML!\</title\> \</head\>
\<body text="yellow" bgcolor="brown"\> \<h1\>Hello World\</h1\>
\<h2\>This is an HTML Document\</h2\> \<h3\>Season 2\<h3\> \</body\>
\</html\> \`\`\`
[![](http://shahinism.com/wp-content/uploads/2011/04/html1-6-300x96.png "html1-6")](http://shahinism.com/wp-content/uploads/2011/04/html1-6.png)همانطور
که می‌بینید عبارات نوشته شده با اندازه‌های متفاوت به نمایش در آمده‌اند‌.
یکی از مهم‌ترین مزایای استفاده از این تگ‌ها در **<span
style="color: #3366ff;">Seo است که به موتور‌های جستجو امکان می‌دهد که به
راحتی بخش‌های مختلف سند را <span style="color: #ffcc00;">**درک** کنند‌.
</span></span>**</span></span></span></span>

### انواع نوشته‌ها‌:

-   **Bold :** برای نوشتن به صورت تو پر یا همان bold از تگ
    **\<b\>\</b\>** استفاده می‌شود‌.

<!-- -->

-   *Italic :* برای نوشتن به صورت مورب نیز از تگ**\<i\>\</i\>** استفاده
    می‌شود‌.

<!-- -->

-   ~~Strike :~~ برای نوستن به صورت رو خط دار از تگ
    **\<strike\>\</strike\>** استفاده می‌شود‌.

<!-- -->

-   Underline : برای نوشتن به صورت زیر خط دار از تگ **\<u\>\</u\>**
    استفاده می‌شود‌.

خوب می‌خواهیم صفحهٔ ساخته شدمان را اندکی <span
style="color: #ff9900;">**زیبا‌تر** کنیم؛ برای این کار از تگ‌هایی که
اخیرا یاد گرفتیم استفاده می‌کنیم‌: \`\`\`bash \<html\> \<head\>
\<title\>First HTML!\</title\> \</head\> \<body text="yellow"
bgcolor="brown"\> \<h1\>Hello World\</h1\> \<h3\>This is an HTML
Document \<i\>season \#2\</i\>\</h3\> This is an free tutorial for
\<b\>HTML\</b\> from \<b\>\<u\>shahinism.com\</u\>\</b\> \</body\>
\</html\> \`\`\`
[![](http://shahinism.com/wp-content/uploads/2011/04/html1-5-300x81.png "html1-5")](http://shahinism.com/wp-content/uploads/2011/04/html1-5.png)همانطور
که می‌بینید توانستیم با تگ‌هایی ساده یک تایپوگرافی معقول ایجاد کنیم‌.
تنها نکته‌ای که در مثال اخیر باید مورد <span
style="color: #ff0000;">**توجه** قرار گیرد‌، این قسمت است‌:
\<b\>\<u\>shahinism.com\</u\>\</b\>همانطور که می‌بینید از دو تگ زیر خط و
نوشتهٔ تو پر به صورت همزمان استفاده شده‌. ولی تگ‌ها از <span
style="color: #999999;">**آخر به اول بسته شده‌**. </span></span></span>

### موقعیت نوشته‌:

برای تعیین موقعیت نوشته‌ها نیز در HTML امکاناتی در نظر گرفته شده‌. که به
تعدادی از آن‌ها اشاره می‌کنیم‌:

-   Center: برای **وسط‌چین** کردن نوشته استفاده می‌شود‌.

<!-- -->

-   \<br\> : برای **شکستن** خط و شروع در خط جدید مورد استفاده قرار
    می‌گیرد‌.

<!-- -->

-   \<sub\> و \<sub\> : که برای نمایش **اندیس و توان** مورد استفاده قرار
    می‌گیرد‌.

اکنون می‌خواهیم با کد‌هایی که یاد گرفتیم تغییرات دیگری را نیز در سند
ایجاد کنیم‌: \`\`\`bash \<html\> \<head\> \<title\>First HTML!\</title\>
\</head\> \<body text="yellow" bgcolor="brown"\> \<center\>\<h1\>Hello
World\</h1\>\</center\> \<h3\>This is an HTML Document \<i\>season
\<sub\>\#2\</sub\>\</i\>\</h3\> This is an free tutorial for
\<b\>HTML\</b\> from: \<br\>\<b\>\<u\>shahinism.com\</u\>\</b\>
\</body\> \</html\> \`\`\`
[![](http://shahinism.com/wp-content/uploads/2011/04/html1-4-300x62.png "html1-4")](http://shahinism.com/wp-content/uploads/2011/04/html1-4.png)
همانطور که در تصویر زیر می‌بینیم <span
style="color: #0d96f1;">**\#**<span style="color: #00ccff;">**۲**مقداری
به پایین منتقل شده‌، هم‌چنین آدرس سایت نیز با توجه به اینکه در ادامهٔ خط
نوشته شده‌، ولی پایین‌تر آمده‌. واضح‌ترین تغییر نیز در این مثال عبارت
Hello World است که به وسط صفحه تغییر مکان داده‌. </span></span>

### تغییر قلم‌:

برای تغییر قلم نوشته **(فونت‌)** نیز می‌توانید از تگ فونت استفاده کنید‌.
نمونه‌ای از استفاده از این قلم را در کد زیر ببینید‌: \`\`\`bash \<html\>
\<title\>Font Change\</title\> \</html\> \<body\> Hi my friends \<font
face="tahoma" size=24 color=red\>in this page we have 2\</font\>
different font. \</body\> \</html\> \`\`\` نتیجه‌ی مثال زیر را در تصویر
زیر می‌بینیم‌:
[![](../wp-content/uploads/2011/04/html1-3-300x39.png "html1-3")](../wp-content/uploads/2011/04/html1-3.png)
لازم به **ذکر** است‌، مرور‌گر‌ها به صورت **پیش‌فرض** فونتی را برای نمایش
نوشته در نظر می‌گیرند که با مراجعه به بخش تنظیمات هر مرورگر قابل تغییر
است‌. فونت تعیین شده در کد بالا در صورتی که روی سیستم کاربر موجود باشد‌،
نمایش داده می‌شود‌، در غیر این صورت از فونت پیش‌فرض استفاده می‌شود‌. در
بخش آموزش CSS روشی از CSS3 را می‌آموزیم که این **نقظه ضعف** را پوشش
می‌دهد‌.