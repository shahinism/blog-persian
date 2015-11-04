.. title: مشکل رزولوشن پایین در اوبونتو پس از نصب درایور NVIDIA .. date:
2010/6/19 9:16:2

مدت‌ها بود که پس از نصب اوبنتو و نصب درایور NVIDIA مشکل مسخره‌ای داشتم‌،
آن هم این بود که Nvidia Settings رزولوشن‌های پایینی را برای تنظیم در
اختیار داشت‌، مانند 800x600 که واقعا عذاب آور بود‌. آن هم در یک توالت
فرنگی 15 اینچی‌. جستجو در بین انجمن‌های لینوکسی فارسی هم نتیجه‌ای جز
وارد کردن دستی رزولوشن در بر نداشت‌. اما این کار اصلا تغییری در تنظیمات
Nvidia Settings ایجاد نمی‌کرد‌. سر انجام کاشف جور دیگری به عمل آمد‌.
یعنی اصلا مشکل سر این قسمت زیری نبود‌: \`\`\`bash Section "Screen"
DefaultDepth 24 SubSection "Display" Depth 15 Modes "1152x864"
"1024x768" "1024x600" "800x600" "768x576" "640x480" EndSubSection \`\`\`
که دوستان می‌گفتند باید دستی رزولوشن‌های جدید را وارد کنم‌. مشکل اینجا
بود که NVIDIA در هنگام نصب مانیتور مرا شناسایی نکرده بود در نتیجه
VertRefresh و HorizSync ای که برای مانیتور Unknown نشان می‌داد اصلا قدرت
نمایش رزولوشنی بالاتر از 800x600 را نداشت‌. پس باید به صورت دستی این
قسمت را تغییر می‌دادم‌. در زیر نمایی از کد را می‌بینید‌: \`\`\`bash
Section "Monitor" Option "CalcAlgorithm" "XServerPool" DisplaySize 331
207 HorizSync 30-62 VertRefresh 43-60 UseModes "Modes[0]" EndSection
\`\`\` کد های بالا از فایل کانفیگ سیستم من نیست‌، ولی چند نکته هست که
باید بهش توجه داشته باشید‌: یک اینکه باید HorizSync و VertRefresh رو در
بخش Section "Monitor" تغییر بدید‌. نکته مهم بعدی اینه که این مقادیری که
برای این دو متغیر در اینجا قرار داده شده رزولوشن مانیتور شما رو در حالت
عادی برای 1152x864 آماده می‌کنه ولی تا چند رزولوشن بالاتر هم پشتیبانی
می‌کنه‌. و سه این‌که خیلی مراقب تغییر این اعداد باشید‌. اول از فایل
کانفیگتون یه بک آپ بگیرید‌، بعد این‌ها رو تغییز بدید‌. اگر دیدید که
مانیتور Out Of Range شد کافیه که اون فایل بک آپ رو برگردونید‌. در کل کار
آسونیه فقط یکم باس قلق سیستم دستتون باشه‌. برای این‌که بیشتر موضوع رو
درک کنید‌، به لینک‌های زیر یه نگاه بندازید‌:

[Linux find out monitor VertRefresh values and HorizSync rate with
ddcprobe](http://www.cyberciti.biz/faq/howto-use-linux-ddcprobe-command/)

[Resolution 1152x864 not
possible](http://forums.opensuse.org/get-help-here/laptop/432735-resolution-1152x864-not-possible.html)