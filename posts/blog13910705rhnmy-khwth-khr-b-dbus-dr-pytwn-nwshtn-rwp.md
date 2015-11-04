.. title: راهنمای کوتاه کار با DBus در پایتون (نوشتن روبات پاسخگو برای
Pidgin) .. date: 2012/9/26 15:52:57

مساله این‌جاست که وقتی پای کامپیوتر می‌نشینم‌، حتی اگر کاری نداشته
باشم‌، یادم نمی‌ماند که مسنجرم را روشن کنم‌. و خوب از طرفی دوست دارم که
در صورت امکان‌، با رفقای اینترنتی و غیر اینترنتی‌ام در ارتباط باشم‌. خوب
حل این مشکل ساده است‌. کافی است میز‌کارت را تنظیم کنی که با روشن شدنش‌،
Pidgin را هم اجرا کند‌. ولی خوب این بالقوه مشکل دیگری را می‌آفریند. کدام
مشکل؟ همین که گاها موقع کار کردن‌، یکی از دوستانت می‌پرد وسط و چیزی
می‌گوید که کوچکترین پیامدش حواس پرتی است و این اصلا نمی‌تواند کمک خوبی
برای بالا بردن بهره‌وری شود. راه حل کوتاه در این زمینه استفاده از
Status‌های مسنجر است‌. جدای از این که Status‌ها در همهٔ مسنجر‌ها همانطور
که باید نشان داده نمی‌شوند‌، چه تضمینی وجود دارد که من حواس‌پرت و البته
تنبل (gsh سابق D:)، یادم بماند و حالش را داشته باشم که در هر وضعیتی
Status مناسب را انتخاب کنم‌؟ بعد از کمی جستجو‌، با
[DBus](http://dbus.freedesktop.org/ "dbus official webpage") آشنا شدم و
البته یادم آمد که خیلی وقت پیش‌،[جادی
عزیز‌](http://jadi.net/2011/07/linux-chera-command-line/ "jadi dbus")،
کاری تقریبا در همین مایه‌ها با DBus و Pidgin انجام داده بود‌. توضیحات
تکمیلی در مورد DBus را می‌توانید در وبلاگ جادی بخوانید‌، خصوصا این که
اسکریپت نوشته شده توسط جادی در آن پست‌، پیش در آمد خوبی برای این کار
است‌، و حقیقتش تنها منبع به درد بخورم در این زمینه بود‌! (منظورم در
زمینهٔ عملی کار با DBus است‌، در زمینهٔ تئوری و به عنوان یک راهنما
می‌توان به
[راهنمای](http://dbus.freedesktop.org/doc/dbus-python/doc/tutorial.html "dbus-python turorila")
Freedesktop بسنده کرد‌.) مساله این‌جاست که می‌خواهیم اسکریپتی بنویسیم که
پس از اجرا‌، منتظر Pidgin بماند‌. اگر Pidgin پیغامی دریافت کرد‌، اسکریپت
به صورت خود‌کار و بلافاصله‌، جوابی را که از قبل بهش خورانده‌ایم رو به
مخاطب آن‌ور خط بدهد‌. با این وصف‌، اسکریپت‌مان دو مرحله خواهد داشت‌.
اول‌، منتظر ماندن برای یک علامت که از طرف Pidgin‌، پس از دریافت پیام
ارسال می‌شود‌. دوم‌، ارسال جواب برای مخاطبی که پیغام را ارسال کرده‌.
برای انجام این کار اول از همه‌، ابزار‌های مورد نیازمان را وارد می‌کنیم‌:
[python] import sys import dbus from PyQt4.QtGui import QApplication
from dbus.mainloop.qt import DBusQtMainLoop [/python] قرار بر این بود که
اسکریپت پس از اجرا منتظر بماند‌، درست؟ خوب همان‌طور که می‌دانید
برنامه‌ها منطقا جوری نوشته می‌شوند که یک کاری را شروع کنند‌، انجام
دهند‌، و پایان یابند‌. این روند زیاد برای کار ما مناسب نیست‌. از طرفی
استفاده از حلقه‌های بی‌نهایت مرسوم‌‌، جز پیچیده کردن کار‌، نتیجه‌ای به
همراه ندارد‌. این است که برای سازگاری بیشتر اسکریپت با برنامه‌های Qt (در
ادامه دلیلش را می‌گویم) از QApplication و DBusQtMainLoop برای مدیریت
حلقهٔ اصلی استفاده می‌کنیم‌. در ادامه اضافه می‌کنیم: [python] bus\_loop
= DBusQtMainLoop(set\_as\_default=True) [/python] کار با حلقهٔ اصلی هنوز
تمام نشده‌، باقی کار را آخر انجام می‌دهیم‌. و اما حالا نوبت به انجام
مرحلهٔ اول کارمان می‌رسد. تابع گیرندهٔ سیگنال (همان علامتی که Pidgin پس
از دریافت پیغام ارسال می‌کند) را می‌نویسیم‌. [python] def
connect\_dbus(text): global answer answer = text bus = dbus.SessionBus()
bus.add\_signal\_receiver(pidgin\_control\_func,
dbus\_interface="im.pidgin.purple.PurpleInterface",
signal\_name="ReceivedImMsg") [/python] اولین سوال در این تابع‌، این است
که به کدام DBus وصل شویم؟ به طور معمول دو DBus داریم‌، SystemBus که به
صورت سراسری (System wide) است‌‌. و دومی SessionBus که محدود به یوزر اجرا
کنندهٔ برنامه می‌شود‌. برای کار ما‌، دومی‌، انتخاب معقول‌تری است‌. پس از
اتصال‌، نوبت به نصب یک پیغام‌گیر می‌شود‌. تابع مورد استفاده به صورت
bus.add\_signal\_receiver است که سه آرگومان می‌گیرد‌. که هر کدام به
سوالی پاسخ می‌دهند‌: ۱- پس از دریافت سیگنال کدام تابع را صدا کنم؟ پاسخ:
pidgin\_control\_func (تابعی که در مرحلهٔ دوم خواهیم ساخت) ۲- روی DBus
به حرف کدام برنامه گوش کنم؟ پاسخ: Pidign که خوب ما از آدرس DBusاش برای
معرفی استفاده می‌کنیم‌. ۳- منتظر چه نوع علامتی باشم؟ پاسخ: ReceivedImMsg
که با کمی جستجو در مستندات Pidgin به عنوان علامت دریافت پیغام توسط
Pidgin شناسایی کردیم ;-) در این تابع ما از فراخوان می‌خواهیم که آرگومانی
را به عنوان text برایمان ارسال کند و آن را به متغیر سراسری answer نسبت
می‌دهیم‌. دلیل این کار ساده است‌. چون می‌خواهیم کلا در برنامهٔ اصلی فقط
همین تابع را صدا کنیم و خودش باقی کار‌ها را انجام دهد. نوبت به نوشتن
تابع دوم می‌رسد‌: [python] def pidgin\_control\_func(account, sender,
message, conversation, flags): bus = dbus.SessionBus() obj =
bus.get\_object("im.pidgin.purple.PurpleService",
"/im/pidgin/purple/PurpleObject") purple = dbus.Interface(obj,
"im.pidgin.purple.PurpleInterface") if
purple.PurpleAccountGetUsername(account) != sender:
purple.PurpleConvImSend(purple.PurpleConvIm(conversation), answer)
[/python] خوب اول از همه این که ما در نوشتن این تابع ۶ آرگومان
می‌گیریم‌. و البته این شش آرگومان چیز‌هایی هستند که همان سیگنال
ReceivedImMsg برای‌مان می‌فرستد‌. که البته اطلاعات خیلی به درد
بخوری‌اند‌. طبق روال قبلی به SessionBus وصل می‌شویم (این کار را می‌شد یک
بار انجام داد‌، ولی موقع استفاده به صورت ماژول کمی جفتک می‌انداخت). در
ادامه به سه سوال دیگر جواب می‌دهیم: ۱- روی DBus به کدام برنامه گوش کنم؟
پاسخ im.pigin.purple.PurpleService ۲- آدرسش کجاست؟ پاسخ:
‎/im/pidgin/purple/PurpleObject در واقع با پاسخ به این دو سوال‌، سعی به
ساخت یک شیع ارتباطی با برنامهٔ مورد نظر داریم‌. حال با این شیع می‌توانیم
یک رابط برای مکاتبهٔ تابع‌مان با Pidgin بسازیم‌. ۳- کدام رابط از آبجکت
ساخته شده؟ پاسخ: im.pidgin.purple.PurpleInterface و خوب حالا تنها برای
ارسال پیام کافی است تابع PurpleConvImSend را از شیع ساخته شده صدا کنیم‌
و به دو سوال پاسخ دهیم: ۱- به چه کسی پیغام بفرستم؟ پاسخ: کسی که برای‌مان
پیغام فرستاده‌. برای به دست آوردنش کافی است که از تابع PurpleConvIm از
شیع‌مان بخواهم که آدرسش را پیدا کند ;-) ۲- چه بگویم؟ پاسخ answer‌‌، همان
متغیر سراسری که که در تابع اول‌، مقدار دهی‌اش کردیم‌. البته من در تابع
یک قفل کودک هم گذاشته‌ام‌. چطور؟ ماجرا این‌جاست که با نوشتن هم‌چین
تابعی‌، وقتی وسوسه می‌شوید که خود‌تان امتحانش کنید‌، به یک لوپ بی‌نهایت
تبدیلش می‌کنید! کافیسیت برای دیدن این لوپ شرط if موجود در تابع را پاک
کرده و تابع را امتحان کنید‌. یک بار به خود‌تان پیغام بدهید‌، Pidgin
علامت می‌دهد‌، روبات پاسخ می‌دهد و دوباره پس از دریافت پیغام روبات روی
Pidgin‌، این برنامه دوباره سیگنال ارسال می‌کند و این کار اگر ولش کنید تا
عبد ادامه خواهد داشت ;-) دیگر وقت اجرای تابع اصلی رسیده‌، و کافیست که:
[python] app = QApplication([]) connect\_dbus(message) app.exec\_()
[/python] برنامه الان به راحتی اجرا می‌شود و کاری را هم که می‌خواهیم
دقیقا انجام می‌دهد(البته طبیعی است که چیز‌های ساده‌ای باید به آن اضافه
کنید‌.)‌. ولی هنوز یک مشکل دارد‌، آن هم این که نمی‌توان آن را بست‌! حتی
Ctrl+c هم در ترمینال آن را نمی‌کشد‌. این است که از دو خط زیر و دقیقا قبل
از ساختن شیع app کمک می‌گیریم: [python] import signal
signal.signal(signal.SIGINT, signal.SIG\_DFL) [/python] کار این تابع این
است که وقتی SIGINT یا همان Ctrl+c ما را گرفت (توجه کنید که این کلید در
رابط گرافیکی Qt برای کپی متن استفاده می‌شود) آن را به SIG\_DFL ترجمه
کند‌! یعنی بزند بترکاند برنامه‌مان را ;-) می‌توانید نسخهٔ کامل اسکریپت
را از[این
لینک](https://github.com/shahinism/PyPomo/raw/master/src/answering_machine.py "Download answering machine")دانلود
کنید و به صورت زیر اجرایش کنید: \`\`\`bash python answering\_machine.py
ANSWER\_MESSAGE \`\`\` اما خوب درست است که این اسکریپت تقریبا مشکل‌مان
را حل می‌کند‌، اما هنوز یک جای کارش می‌لنگد‌! باز هم من کم حواس باید
یادم باشد که اجرایش کنم‌! و از آن بد‌تر در وقت آزادم خاموشش کنم‌! و این
اصلا حال نمی‌دهد‌. این است که آن را با
[PyPomo](http://shahinism.github.com/PyPomo/ "PyPomo Official webpage")
قاطی می‌کنم‌ (آخرین نسخهٔ روی گیت). جوری که وقتی در حال انجام یک پامودور
هستم‌، این اسکریپت را روشن کند‌، و وقتی که موقع استراحت است یا interrupt
داده‌ام‌، آن را خاموش کند‌. حالا دیگر تقریبا همه چیز حل شده است ;-)
**پی‌نوشت۱:** متاسفانه هر کاری کردم نتوانستم این دندانه گذاری کد‌ها را
درست کنم‌. مشکل از پلاگین وردپرس‌ام است‌، یا همچین چیزی‌، باید به فکر
جایگزینی برایش باشم‌! **پی‌نوشت۲:** می‌دانم برنامه به بهترین شکل ممکن
نوشته نشده‌، زیاده کاری دارد و حتی در ترکیبش با PyPomo باگ‌هایی هست که
به چشمم نیامده‌، ولی خوب حداقل تلاشم را کرده‌ام دیگر‌. اگر برنامه نظرتان
را جلب کرده‌، و راه بهتری بلدید‌، روی گیت فورکش کنید و تغییرات‌تان را
اعمال کنید‌. مطمئنم چیز‌های بهتری می‌توان ازش ساخت‌!