.. title: نصب و اجرای Anki در اسلکور .. date: 2011/9/12 15:4:34

این بار نرم‌افزاری بسیار کوچکتر از قبل‌، دغدغه‌ی نصب و اجرای یک
نرم‌افزار در محیط اسلکور را برایم فراهم کرد‌!
[Anki](http://ankisrs.net/ "Anki Official website") نرم‌افزار شبیه ساز
محیط [فلش
کارت](http://fa.wikipedia.org/wiki/%D8%AC%D8%B9%D8%A8%D9%87_%D9%84%D8%A7%DB%8C%D8%AA%D9%86%D8%B1 "جعبه لایتنر در ویکی پدیا")
را به دلیل خاصیتش‌، قبل از این می‌شناختم‌. ولی با شکست در اجرایش و
همچنین نبود فلش کارت مناسب زیاد توجهی بهش نکردم‌. اما اینبار با ورود
[فلش کارت‌های
ایمان‌](http://flashcard.linuxreview.ir/ "4K English words by Flashcard")،
وضع فرق کرد‌. می‌دانستم که کاملترین نمونه‌ی این نرم‌افزار‌ها همین Anki
است‌. از همه جالبتر هم بخش آمار و نمودار‌هایش بود که بسیار وسوسه‌ام
می‌کرد این نرم‌افزار را نصب کنم‌. در ادامه مراحل نصب را مرور می‌کنیم‌!
قبل از هر کاری pysetuptools را از
[اینجا](http://slackbuilds.org/repository/13.37/python/pysetuptools/ "pysetuptools")
دریافت و نصب کنید‌. دیگر پیش نیاز‌های اولیه‌تان برای نصب این‌ها هستند‌:
\`\`\`bash sqlalchemy 0.4.3 simplejson 1.7.3 \`\`\` بسته‌ی دوم
‌(‌simplejason‌) را می‌توانید با استفاده از Slackbuild‌ موجود در [این
آدرس‌](http://slackbuilds.org/repository/13.37/python/simplejson/ "simplejson Slackbuild")
نصب کنید‌. برای SQLAlchamy هم من آخرین نسخه‌ی موجود را نصب کردم‌! برای
این کار کافیست آخرین نسخه را از
[این‌جا](http://www.sqlalchemy.org/ "sqlalchemy official website")
دریافت کنید‌، و Slackbuild نسخه قدیمی را نیز از
[این‌جا](http://slackbuilds.org/repository/13.37/development/SQLAlchemy/ "sqlalchamy slackbuild")
بگیرید‌، حالا فایل Slackbuild را با یک ویرایشگر متن باز کنید‌، همان
اوایل متن مقدار جلوی VERSION را به مقدار دلخواهتان تغییر دهید‌ ‌(برای من
چنین چیزی از آب در آمد VERSION=0.7.2 )‌ حالا اگر می‌خواهید این نرم‌افزار
قدرت گراف کشیدن داشته باشد به ترتیب باید از پس بسته‌های زیر هم بر
بیایید‌. ‌(‌لینک Slackbuild‌های مربوطه از این شماره‌ها قابل دسترسی است‌:
[۱](http://slackbuilds.org/repository/13.37/development/numpy/ "numpy slackbuild")‌،
[۲](http://slackbuilds.org/repository/13.37/python/pytz/ "pytz slackbuild")‌،
[۳‌](http://slackbuilds.org/repository/13.37/python/python-dateutil/ "python-dateutil")،
[۴](http://slackbuilds.org/repository/13.37/libraries/matplotlib/ "matplotlib slackuild")‌‌)
\`\`\`bash - python-numpy (numpy) - python-matplotlib (matplotlib)
\`\`\` برای داشتن چند قابلیت دیگر نظیر ضبط صدا و یا وارد کردن فایل XML
هم نیاز به چند پیش‌نیاز دارید که با استفاده از فایل README موجود در
پوشه‌ی Anki می‌توانید با آن‌ها آشنا شوید‌. ‌(‌من اون‌ها رو تست نکردم‌، و
برای نصب هم نیازی به اون‌ها نداریم‌)‌. پس از نصب پیش‌نیاز‌ها آخرین
نسخه‌ی Anki را از [این‌جا](http://ankisrs.net/ "Anki Official website")
دریافت کنید‌. آن را از حالت فشرده خارج کرده و سپس به مسیر زیر بروید‌:
\`\`\`bash cd anki-YOUR-VERSION/libanki \`\`\` لطفا توجه داشته باشید که
فایلی با نام setup.py در پوشه‌ی اول Anki هم موجود هست‌، ولی ما به آن کار
نداریم‌، و عملیات نصب را با setup.py موجود در پوشه libanki انجام
می‌دهیم‌. برای شروع عملیات نصب دستور زیر را اجرا کنید‌: \`\`\`bash
python setup.py install \`\`\` دستور فوق را یا با کاربر root و یا با
استفاده از sudo اجرا کنید‌. پس از پایان عملیات نصب می‌توانید برنامه را
با دستور anki اجرا کنید‌. متاسفانه نصاب این برنامه برای anki در منوی KDE
هیچ گزینه‌ای اضافه نمی‌کند‌، پس باید زحمت این را شما بکشید‌. ظاهرا الان
برنامه درست کار می‌کند‌، اما برای دیدن روی بد سکه‌، سعی کنید فلش کارت
جدیدی ایجاد کنید و یا یک فلش کارت به آن اضافه کنید‌. متاسفانه با اخطار
زیر روبرو می‌شوید‌: \`\`\`bash Traceback (most recent call last): File
"/usr/lib/python2.6/site-packages/ankiqt/ui/main.py", line 953, in onNew
self.deck.initUndo() File
"/usr/lib/python2.6/site-packages/anki/deck.py", line 3415, in initUndo
(null, 'delete from %(t)s where rowid = ' || new.rowid); end""" % {'t':
table}) File "/usr/lib/python2.6/site-packages/anki/db.py", line 114, in
statement return self.execute(text(sql), kwargs) File
"/usr/lib/python2.6/site-packages/anki/db.py", line 90, in execute x =
self.\_session.execute(\*a, \*\*ka) File
"/usr/lib/python2.6/site-packages/SQLAlchemy-0.6.7-py2.6.egg/sqlalchemy/orm/session.py",
line 724, in execute clause, params or {}) File
"/usr/lib/python2.6/site-packages/SQLAlchemy-0.6.7-py2.6.egg/sqlalchemy/engine/base.py",
line 1191, in execute params) File
"/usr/lib/python2.6/site-packages/SQLAlchemy-0.6.7-py2.6.egg/sqlalchemy/engine/base.py",
line 1271, in \_execute\_clauseelement return
self.\_\_execute\_context(context) File
"/usr/lib/python2.6/site-packages/SQLAlchemy-0.6.7-py2.6.egg/sqlalchemy/engine/base.py",
line 1302, in \_\_execute\_context context.parameters[0],
context=context) File
"/usr/lib/python2.6/site-packages/SQLAlchemy-0.6.7-py2.6.egg/sqlalchemy/engine/base.py",
line 1401, in \_cursor\_execute context) File
"/usr/lib/python2.6/site-packages/SQLAlchemy-0.6.7-py2.6.egg/sqlalchemy/engine/base.py",
line 1394, in \_cursor\_execute context) File
"/usr/lib/python2.6/site-packages/SQLAlchemy-0.6.7-py2.6.egg/sqlalchemy/engine/default.py",
line 299, in do\_execute cursor.execute(statement, parameters)
sqlalchemy.exc.OperationalError: (OperationalError) cannot create
trigger on system table u"ncreate temp trigger
\_undo\_sqlite\_stat2\_itnafter insert on sqlite\_stat2 beginninsert
into undoLog valuesn(null, 'delete from sqlite\_stat2 where rowid = ' ||
new.rowid); end" () \`\`\` خوب برنامه به دلایلی ‌(‌که هنوز هم نفهمیدم
چیه‌!‌) این اخطار رو از قرار فقط برای جماعت اسلکور کار بر می‌گرداند‌!
برای حل این مشکل نیز کافیست‌، برنامه را دوباره استارت کنید و با استفاده
از کلید Download موجود در صفحه اصلی‌، اقدام به بارگذاری یکی از
فلش‌کارت‌های مربوط کنید‌. به طرز عجیبی برنامه پس از آن کاملا درست کار
می‌کند و شما هم می‌توانید با استفاده از آن‌، بر دانستنی‌های دائمتان
بیافزایید‌ :-P
