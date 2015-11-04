.. title: نصب Awesome WM روی اسلکور .. date: 2012/3/25 22:12:34

در چند ماه گذشته یکی از عذاب‌آور‌ترین کار‌هایی که انجام دادم‌، نصب مدیر
پنجره‌ی [Awesome](http://awesome.naquadah.org/ "Awesome wm main page")
روی اسلکور بود‌! بماند که چند باری هم وسوسه شدم که به یکی از توزیع‌های
مخزن دار (اسمو D:) کوچ کنم‌. ولی ارزش اسلکور برایم این‌قدر بالا بود که
دست به این کار نزنم. بعد از چند بار آزمایش و خطا‌، شکست و ... روشی که در
زیر می‌بینید تمیز‌ترین روش نصب مدیر پنجره‌ی Awesome روی اسلکور است‌:
اولین کاری که باید انجام دهیم‌، کامپایل دوباره‌ی بسته‌ی Cairo با قابلیت
پشتیبانی از xcb است‌. برای این کار در شاخه ‎/source/l/cairo در DVD
اسلکور فایل cairo.SlackBuild را با یک ویرایشگر باز کرده و به دنبال عبارت
‎‎‏‎--enable-xcb بگردید‌. پس از یافتنش علامت \# را از اول آن بردارید‌.
یا آن بخش را به صورت زیر ویرایش کنید‌: \`\`\`bash CFLAGS="\$SLKCFLAGS"
\\ ./configure \\ --prefix=/usr \\ --libdir=/usr/lib\${LIBDIRSUFFIX}
\\ --mandir=/usr/man \\ --sysconfdir=/etc \\ --disable-gtk-doc
\\ --disable-glitz \\ --disable-quartz \\ --disable-static
\\ --enable-xcb \\ --disable-win32 \`\`\` فایل را ذخیره کرده و مثل یک
SlackBuild عادی نصبش کنید‌. حالا به شاخه‌ی
‎/source/l/startup-notification بروید و به ترتیب دستورات زیر را اجرا
کنید‌: \`\`\`bash rm startup-notification\*.tar.bz2 wget -c
http://www.freedesktop.org/software/startup-notification/releases/startup-notification-0.12.tar.gz
gunzip startup-notification-0.12.tar.gz bzip2
startup-notification-0.12.tar VERSION=0.12
./startup-notification.SlackBuild upgradepkg
/tmp/startup-notification-\*.txz \`\`\` حالا به شاخه
‎/source/x/x11/src/xcb در DVD بروید و دستورات زیر را اجرا کنید‌:
\`\`\`bash rm xcb-util-\* wget -c
http://xcb.freedesktop.org/dist/xcb-util-0.3.8.tar.bz2
http://xcb.freedesktop.org/dist/xcb-util-image-0.3.8.tar.bz2
http://xcb.freedesktop.org/dist/xcb-util-renderutil-0.3.8.tar.bz2
http://xcb.freedesktop.org/dist/xcb-util-wm-0.3.8.tar.bz2
http://xcb.freedesktop.org/dist/xcb-util-keysyms-0.3.8.tar.bz2 cd
\$SLACKWARE\_TREE/source/x/x11 for i in xcb-util xcb-util-keysyms
xcb-util-renderutil xcb-util-wm xcb-util-image; do ./x11.SlackBuild xcb
\$i; done upgradepkg --install-new /tmp/x11-build/xcb-util-\*.txz \`\`\`
حال نوبت به نصب چند پیش‌نیاز می‌رسد‌. برای راحتی کار پیشنهاد می‌کنم
[sbopkg](http://sbopkg.org "sbopkg official page") و
[src2pkg](http://src2pkg.net "src2pkg official page") را دریافت و نصب
کنید‌. باقی مراحل را با استفاده از این دو ابزار ادامه می‌دهیم‌. برای نصب
libev, lua, imlib2, giblib, feh به ترتیب دستورات زیر را وارد می‌کنیم‌:
\`\`\`bash sbopkg -i imlib2 sbopkg -i lua sbopkg -i libev sbopkg -i
giblib sbopkg -i feh \`\`\` و حالا آخرین نسخه libxdg را از[این
آدرس](http://n.ethz.ch/~nevillm/download/libxdg-basedir/) دریافت کرده و
به صورت زیر کامپایل می‌کنیم‌: \`\`\`bash src2pkg
libxdg-basedir-\*.tar.gz installpkg /tmp/libxdg\*.txz \`\`\` برای نصب
oocairo و oopango نیز از دو اسکریپت به صورت زیر استفاده می‌کنیم‌:
\`\`\`bash mkdir oocairo cd oocairo wget -c
https://raw.github.com/cycojesus/slackbuilds/master/l/oocairo/oocairo.SlackBuild
chmod +x oocairo.SlackBuild ./oocairo.SlackBuild
upgradepkg --install-new /tmp/oocairo-\*.txz cd .. mkdir oopango cd
oopango wget -c
https://raw.github.com/cycojesus/slackbuilds/master/l/oopango/oopango.SlackBuild
chmod +x oopango.SlackBuild ./oopango.SlackBuild
upgradepkg --install-new /tmp/oopango-\*.txz \`\`\` و سرانجام نوبت به
کامپایل خود Awesome می‌رسد‌. آن را از[این
صفحه](http://awesome.naquadah.org/download/ "Awesome wm download page")
دانلود و استخراج کنید. سپس فایل awesomeConfig.cmake را با یک ویرایشگر
باز کرده و عبارت زیر را: \`\`\`bash if(DEFINED SYSCONFDIR)
set(SYSCONFDIR \${SYSCONFDIR} CACHE PATH "config directory") else()
set(SYSCONFDIR \${PREFIX}/etc CACHE PATH "config directory") endif()
\`\`\` به صورت زیر ویرایش کنید‌: \`\`\`bash if(DEFINED SYSCONFDIR)
set(SYSCONFDIR /etc CACHE PATH "config directory") else() set(SYSCONFDIR
/etc CACHE PATH "config directory") endif() \`\`\` فایل را ذخیره کرده و
دستور make را اجرا کنید‌. پس از به پایان رسیدن این دستور به صورت زیر عمل
می‌کنیم‌: \`\`\`bash mkdir /tmp/awesome-version make install
DESTDIR=/tmp/awesome-version cd /tmp/awesome-version makepkg -l y -c n
/tmp/awesome-version.tgz installpkg /tmp/awesome-version.tgz \`\`\` و
سرانجام پس از نصب Awesome برای این که بتوانیم آن را با xwmconfig انتخاب
کنیم‌، دستور زیر را وارد کرده‌: \`\`\`bash vim
/etc/X11/xinit/awesome.xinit \`\`\` و متن زیر را در آن وارد کنید:
\`\`\`bash\#!/bin/sh \# \$Xorg: xinitrc.cpp,v 1.3 2000/08/17 19:54:30
cpqbld Exp \$ userresources=\$HOME/.Xresources
usermodmap=\$HOME/.Xmodmap sysresources=/etc/X11/xinit/.Xresources
sysmodmap=/etc/X11/xinit/.Xmodmap \# merge in defaults and keymaps if
[ -f \$sysresources ]; then /usr/bin/xrdb -merge \$sysresources fi if
[ -f \$sysmodmap ]; then /usr/bin/xmodmap \$sysmodmap fi if [ -f
\$userresources ]; then /usr/bin/xrdb -merge \$userresources fi if [ -f
\$usermodmap ]; then /usr/bin/xmodmap \$usermodmap fi exec awesome
\`\`\` و سرانجام با دستور زیر به آن امکان اجرا می‌دهیم‌: \`\`\`bash
chmod +x /etc/X11/xinit/awesome.xinit \`\`\`. در آینده‌ای نزدیک در مورد
این مدیر پنجره و نحوه‌ی کار با آن بیشتر صحبت خواهم کرد ;-)
