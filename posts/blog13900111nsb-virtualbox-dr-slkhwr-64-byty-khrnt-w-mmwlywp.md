.. title: نصب VirtualBox در اسلکور 64 بیتی کارنت و معمولی‌! .. date:
2011/3/31 8:31:47

نصب ماشین مجازی ساز ویرچوال باکس حداقل برای دانشجو‌هایی مثل من که دوست
دارند با لینوکس کار کنن و استادایی دارن که کار با نرم‌افزار‌های کرک شده
رو قراره ازشون امتحان بگیرن‌، یه امر حیاتیه‌‌! نصب ویرچوال باکس روی
اسلکور چند‌تا تکنیک کوچولو لازم داره که می‌خوام توی این پست بنویسم که در
آینده اگه بهشون نیاز پیدا کردم‌، در دسترس باشن‌! اول از همه به قابلیت
چند کتاب‌خانه‌ای توی اسلکور نیاز دارید که می‌تونید از سه تا لینک روبرو
کمک بگیرین‌:
[+](http://slackware.com/%7Ealien/multilib/ "Alien Multilib"),
[+](http://shahinism.com/1389/12/%d9%85%d8%b3%d8%a7%d9%84%d9%87%e2%80%8c-%d8%a7%d8%b3%da%a9%d8%a7%db%8c%d9%be-%d8%af%d8%b1-%d8%a7%d8%b3%d9%84%da%a9%d9%88%d8%b1-64-%d8%a8%db%8c%d8%aa%db%8c/ "مساله‌: اسکایپ در اسلکور ۶۴ بیتی"),
[+](http://slack-world.com/index.php/articles/43-general-system/85-multilib-slackware64 "اضافه کردن چند کتاب‌خانه‌ای در اسلکور 64 بیتی").
و دوم بسته‌ی Acpci رو از
[این‌جا](http://shahinism.com/wp-admin/post-new.php "Acpica Slackbuild")
دریافت و نصب کنین‌. برای نصب مثل آدمی‌زاد این نرم افزار کافیه اول با
دستور زیر یه گروه برای ویرچوال باکس بسازین‌: \`\`\`bash groupadd -g 215
vboxusers \`\`\` و بعد هم با استفاده از این دو Slackbuild
[+](http://slackbuilds.org/repository/13.1/system/virtualbox-ose/ "Virtualbox-ose"),
[+](http://slackbuilds.org/repository/13.1/system/virtualbox-kernel/ "Virtualbox-kernel")
بسته‌های Virtualbox-ose و Virtualbox-kernel رو نصب کنید‌. ( اگه برای
دانلود بسته‌های Virtualbox-ose مشکلی داشتین تا مدتی می‌تونین اون رو از
روی سرور من یعنی
[اینجا](http://188.40.173.20/pack/virtualbox-3.2.10-ose.tar "Virtualbox-3.2.10-ose.tar")
دانلود کنید‌.) ولی می‌مونه یه نکته که برای موقعیه که شما از نسخه‌ی کارنت
اسلکور استفاده می‌کنین‌. بنا به دلایلی که برام آخرش هم روشن نشد که چرا
توی 13.1 این اتفاق نیافتاد‌، ممکنه با این اخطار روبرو بشین‌: \`\`\`bash
\<code\>kmk[2]: \*\*\* Waiting for unfinished jobs.... kmk[2]: Leaving
directory \`/tmp/VirtualBox-3.2.0\_OSE' kmk[2]: Entering directory
\`/tmp/VirtualBox-3.2.0\_OSE' kmk[2]: \*\*\* Exiting with status 2
kmk[1]: \*\*\* [pass\_binaries\_this] Error 2 kmk[1]: Leaving directory
\`/tmp/VirtualBox-3.2.0\_OSE' kmk: \*\*\* [pass\_binaries\_order] Error
2\</code\> \`\`\` خوب من چون علاقه‌ای به این نداشتم که از بسته کامپایلش
کنم‌، یه روش آرتیستی بهتون می‌گم که برای خودم تا الانش که جواب داده‌.
وقتی که Slackbuild شروع به کار کرد‌، خوب کد‌های خروجی رو نگاه کنین‌، تا
برسین به جایی که Enjoy رو ببینین‌. می‌شه تقریبا بعد از کامپایل و شروع
make . به عبارت دیگه جایی که از پروسه‌ی چک کردن بسته‌های پیش‌نیاز فارغ
شده‌. همین‌جا یه Ctrl+z بزنین دستور زیر رو بزنین‌: **به روز رسانی‌:**
آموزشی که این‌جا نوشتم مربوط به 3.2.10 هست ولی توی Virtualbox 4.0.4 هم
همین مشکل پا بر‌جاست و با همین روش حل می‌شه‌! **به روز رسانی‌:** از قرار
اگه یه کم توجه می‌کردم نیازی به این آرتیست بازی هم نیست! توی بسته‌ی
Slackbuild‌ی که می‌گیریم یه فایل به اسم localConfig.kmk هست که تغییراتی
که در ادامه ذکر کردم رو توی همون اعمال کنید حله‌! \`\`\`bash vim
/tmp/SBo/VirtualBox-3.2.10\_OSE/LocalConfig.kmk \`\`\` اگه احیانا دیدین
که این فایل موجود نبود‌، با fg 1 بزارین یکم دیگه Slackbuild کارش رو
بکونه و بعد Ctrl+z رو بزنین و ادامه بدین‌: توی آخر فایل اضافه کنین‌:
\`\`\`bash VBOX\_WITH\_WARNINGS\_AS\_ERRORS := \`\`\` و حالا با fg 1
پروسه‌ی Slackbuild‌مون رو که استاپ کرده بودیم‌، بر می‌گردونیم که کارش رو
بکنه‌. اگه همه‌چی درست انجام شده باشه دیگه مشکلی نداریم‌. حالا که نصب رو
انجام دادیم‌، می‌ریم که VirtualBox رو باز کنیم‌، و ماشین مجازیمون رو از
توش اجرا کنیم‌. ولی از اون‌جایی که کور خوندیم‌، اجرا نمی‌شه‌. چرا‌؟
بخاطر این که Vboxdrv اجرا نشده‌. چی‌کار کنیم‌؟ می‌زنیم‌: \`\`\`bash
/etc/rc.d/rc.vboxdrv start \`\`\` حالا اجرا می‌شه‌. ولی مشکل این‌جاست که
بعد از یه خاموش روشن باس دوباره این کار رو انجام بدیم‌. برای این که از
این تکرار ملالت‌بار خلاص بشیم‌، کافیه بزنیم‌: \`\`\`bash vim
/etc/rc.d/rc.local \`\`\` و خط‌های زیر رو بهش اضافه کنیم‌: \`\`\`bash
\#start vboxdrv if [ -x /etc/rc.d/rc.vboxdrv ]; then
/etc/rc.d/rc.vboxdrv start fi \# Start vboxnet if [ -x
/etc/rc.d/rc.vboxnet ]; then /etc/rc.d/rc.vboxnet start fi \`\`\` به
فاصله‌ها حتما دقت کنین‌. و برای این که تغییراتی که تو روشن شدن سیستم
دادیم‌، موقع خاموش شدن به حالت قبل برگردونیم بزنین‌: \`\`\`bash vim
/etc/rc.d/rc.local\_shutdown \`\`\` و توش کد‌های زیر رو وارد کنید‌:
\`\`\`bash top vboxdrv if [ -x /etc/rc.d/rc.vboxdrv ]; then
/etc/rc.d/rc.vboxdrv stop fi \# Stop vboxnet if [ -x
/etc/rc.d/rc.vboxnet ]; then /etc/rc.d/rc.vboxnet stop fi \`\`\` همین‌.
از مجازی سازی با VirtualBox لذت ببرین‌!