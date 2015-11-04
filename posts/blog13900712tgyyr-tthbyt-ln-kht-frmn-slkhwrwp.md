.. title: تغییر (تثبیت‌) اعلان خط فرمان اسلکور .. date: 2011/10/4
6:19:13

اعلان خط فرمان لینوکس در عین سادگی‌اش می‌تواند شدیدا کاربردی باشد‌! در
توزیع‌های مختلف دیده بودم که این اعلان خط فرمان فقط در علائم کاربری \$ و
ریشه \# متفاوت از هم بود‌، اما در اسلکور‌، یک نکته عجیب در این مورد
برایم وجود داشت‌! آن هم این که در حالت عادی اعلان فرمان به صورت‌:
\`\`\`bash user@hostname \$ \`\`\` نشان داده می‌شد‌، اما وقتی مثلا در
کنسول KDE یک Tab جدید باز می‌کردم‌، اعلان به صورت زیر تغییر می‌کرد که
متاسفانه‌، هیچ قابلیت به درد بخوری در خود نداشت‌: \`\`\`bash bash.4.?:
\$ \`\`\` این مشکل از وقتی که از برنامه
[Yakuake](http://yakuake.kde.org/ "yakuake official webpage") برای
دسترسی راحت‌تر به ترمینال استفاده می‌کردم‌، بیشتر به چشم می‌آمد‌، و عملا
تمامی اعلان فرمان‌هایش به همین شکل بود‌. پس تصمیم گرفتم یک بار برای
همیشه‌، بی‌سوادی را کنار بگذارم و حلش کنم‌. مشکل به دو فایل زیر مربوط
می‌شد‌: \`\`\`bash /etc/bashrc \~/.bashrc \`\`\` که متاسفانه هیچ‌کدامشان
در اسلکور به صورت پیش‌فرض وجود نداشتند‌، و از قرار آن اعلان سالم اول کار
هم از فایل HOSTNAME موجود در شاخه etc ‏استفاده می‌کرد‌. خوب پس کافی بود
یکی از این فایل‌ها را بسازم‌، و از آن‌جایی که ساختن فایل دوم‌، به نظرم
آسان‌تر آمد‌، با دستور vim \~/.bashrc اقدام به ساختنش کردم‌، و خط زیر را
به آن اضافه کردم‌: \`\`\`bash PS1="[u@hw]\$ " \`\`\` ترمینال را یک بار
بستم و باز کردم‌، و همه‌چیز خوب بود‌. حالا می‌ماند توضیحات این خط دوم‌:

-   ! : شماره فعلی تاریخچه فرمان را نشان میدهد.
-   \# : شماره دستور آخرین دستور را نشان میدهد.
-   \$ : اعلان فرمان استاندارد را نشان میدهد.
-   W : فقط دایرکتوری کاری جاری را نشان میدهد.
-   \\ : فقط یک بک اسلش نشان داده میشود.
-   d : روز، ماه و شماره روز را نمایش میدهد. مثلا : Sat Jan 23
-   h : نام کامپیوتر میزبان را نشان میدهد.
-   n : یک خط جدید باز میکند.
-   s : نام پوسته فرمان را نشان میدهد. مثلا bash
-   t : زمان را بصورت ساعت، دقیقه و ثانیه نمایش میدهد. برای مثال :
    10:14:40
-   u : نام کاربر را نمایش میدهد.
-   w : مسیر کامل دایرکتوری جاری را نمایش میدهد.

من این تنظیمات را از مطلب «‌آموزش کامل خط فرمان‌» که در سایت
[تکنوتاکس](http://www.technotux.org/index.php/%D8%B5%D9%81%D8%AD%D9%87%D9%94_%D8%A7%D8%B5%D9%84%DB%8C "Technotux homepage")
قرار داشت‌، بدست آورده بودم‌، ولی الان هر چه گشتم لینک پیدا نکردم‌، که
اضافه کنم‌! برای این که نتیجه‌ی اعلانتان را ببینید و یا این که اگر لازم
شد در موقعیت خاصی وضعیت اعلانتان را عوض کنید (‌البته نه برای همیشه‌، فقط
برای نشست حاظر‌) کافیست از دستور زیر در ترمینال استفاده کنید‌:
\`\`\`bash export PS1="[u@hw]\$ " \`\`\` فکر کنم به عنوان یک نکته کوچک‌،
دیگر همین‌قدر توضیح دادن کافی باشد. ;-)