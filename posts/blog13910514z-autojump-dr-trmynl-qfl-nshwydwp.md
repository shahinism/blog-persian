.. title: از Autojump در ترمینال غافل نشوید‌! .. date: 2012/8/4 9:9:9

[قبلا در مورد Bashmark نوشته
بودم](http://shahinism.com/blog/1391/01/03/%d8%a2%d8%af%d8%b1%d8%b3%e2%80%8c%d9%87%d8%a7-%d8%b1%d8%a7-%d8%af%d8%b1-%d8%ae%d8%b7-%d9%81%d8%b1%d9%85%d8%a7%d9%86-bookmark-%da%a9%d9%86%db%8c%d8%af/ "آدرس‌ها را در خط فرمان Bookmark کنید!")
و دقیقا همین قبلا بود که [فرود](http://cyberrabbits.net/) عزیز گفت که از
[Autojump](https://github.com/joelthelion/autojump "autojump official git channel")
استفاده می‌کند‌. اما آن موقع‌ها بخاطر یک باگ کوچک نادیده گرفته بودمش‌!
امروز که دیگر آن باگ یادم نبود بار دیگر تستش کردم و (آخه دیگه چی بگم؟
این لعنتی خیلی با شعوره‌!) اصلا خودتان این ویدئو را ببینید تا زورش را
درک کنید:

هــاها‌! کدام ابزار را می‌شناسید که سریع‌تر بین دایرکتوری‌ها جابجایتان
کند؟ خوب دیگر پر حرفی بس است‌. برویم سر اصل ماجرا‌. نصب و حل یک مشکل‌!

#### نصب

برای نصب اگر پایتون روی سیستم‌تان بالا‌تر از ۲.۷ است که خیال‌تان راحت و
تنها کافییست که آن را از کانال گیتش دریافت کنید و پس از ورود به پوشه‌اش
اسکریپت install.sh را اجرا کنید‌. اما اگر مثل من با این ترافیک داغان
اینترنت روی اسلکور استیبل گیر کرده‌اید (این یعنی پایتون ۲.۶) پس باید یک
چند‌تا کار اضافه انجام دهید‌ (یا شاید هم بخواهید به ورژن ۱۹ که توی
اسلک‌بیلد‌ها پیدا می‌شود بسنده کنید): \`\`\`bash sbopkg -R -i
"pysetuptools pip" \`\`\` امیدوارم sbopkg را نصب کرده و بی‌خودی زندگی را
برای خود سخت نگیرید ;-) حالا هم کافیست که با pip بستهٔ مورد نیاز
Autojump را نصب کنید‌: \`\`\`bash pip install argparse \`\`\` و سپس:
\`\`\`bash git clone git://github.com/joelthelion/autojump.git cd
autojump ./install.sh --force \`\`\` و حالا خط زیر را به ‎.zshrc اضافه
کنید: \`\`\`bash [[ -s /etc/profile.d/autojump.zsh ]] && source
/etc/profile.d/autojump.zsh \`\`\` و سر‌انجام: \`\`\`bash source
\~/.zshrc \`\`\`

#### مشکل

و خوب کار باید تمام شده باشد اما دستور زیر را امتحان کنید: \`\`\`bash
vim \~/.zsh[TAB] \`\`\` که احتمالا چیزی شبیه خروجی زیر نصیبتان می‌شود:
\`\`\`bash \_arguments:439: \_vim\_files: function definition file not
found \_arguments:439: \_vim\_files: function definition file not found
\_arguments:439: \_vim\_files: function definition file not found \`\`\`
و این یعنی اتوکامپلیشن فوق‌العادهٔ ZSH جلوی دستور vim از کار می‌افتد‌!
خوب چه کنیم؟ تنها یک راه حل در اینترنت جواب این مساله بود و آن هم [از
انجمن
آرچر‌های](https://bbs.archlinux.org/viewtopic.php?id=37245 "Problem on Arch forum")اعظم:
\`\`\`bash \$ echo \$fpath (see the function PATH of zsh)
/usr/share/zsh/site-functions /usr/share/zsh/4.3.11/functions \$ cd
/usr/share/zsh/4.3.11/functions \$ ls \_vi\* \_vim rm \_vim \`\`\` و
حالا لذت ببرید ;-)
