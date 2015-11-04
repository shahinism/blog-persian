.. title: چ‌چ‌چ (۱۱)‌: چگونه می‌توانم بفهمم کارت اترنتم (NIC) شناخته شده
یا نه‌؟ .. date: 2012/1/3 22:12:43

کارت اترنت شیشهٔ زندگی یک سرور لینوکسی به حساب می‌آید‌. پس اگر نیاز
دارید که بفهمید کارت اترنت سرورتان شناخته شده از دستور dmesg، ifconfig
یا netstat استفاده کنید‌. دستور ifconfig می‌تواند برای تنظیم یک کارت
رابط شبکه (Network interface card) به‌‌ همان خوبی که برای کشف اطلاعات
دربارهٔ کارت اترنت عمل می‌کند‌، مورد استفاده قرار گیرد‌. اگر می‌خواهید
چیپ کارت شبکه‌تان را بشناسید هم می‌توانید از دستور lspci استفاده کنید
(‌پایین‌تر نمونه‌ای از خروجی این دستور را با هم می‌بینیم‌) ‌. \`\`\`bash
\# /sbin/ifconfig \`\`\` خروجی‌: \`\`\`bash eth۰ Link encap: Ethernet
HWaddr ۰۰: ۲۴: ۱d: d۱: ۰۴: d۰ inet addr: ۱۹۲. ۱۶۸. ۱. ۲ Bcast: ۱۹۲. ۱۶۸.
۱. ۲۵۵ Mask: ۲۵۵. ۲۵۵. ۲۵۵. ۰ inet۶ addr: fe۸۰:: ۲۲۴: ۱dff: fed۱: ۴d۰/۶۴
Scope: Link UP BROADCAST RUNNING MULTICAST MTU: ۱۵۰۰ Metric: ۱ RX
packets: ۱۸۰۷۸ errors: ۰ dropped: ۰ overruns: ۰ frame: ۰ TX packets:
۲۰۱۰۸ errors: ۰ dropped: ۰ overruns: ۰ carrier: ۰ collisions: ۰
txqueuelen: ۱۰۰۰ RX bytes: ۱۰۱۹۴۷۸۶ (۹. ۷ MiB) TX bytes: ۳۴۵۳۳۵۳ (۳. ۲
MiB) Interrupt: ۴۰ Base address: ۰x۸۰۰۰ \`\`\` توجه کنید که اگر در خروجی
eth۰ را دیدید‌، پس کارت شما شناخته شده‌. نکته دیگر اینکه در سرور‌های
مجازی با عبارات دیگری نظیر venet روبرو هستید‌، که پس از تجربه کردنشان‌،
می‌توانید بهتر درکشان کنید ;-) برنامه dmesg به کاربران کمک می‌کند
پیغام‌های هنگام بوت را مشاهده کنند‌. این پیغام‌ها در فایل
‎/var/log/dmesg (‌لینوکس دبیان‌) ذخیره می‌شوند‌: \`\`\`bash cat
/var/log/dmesg | grep -i eth۰ \`\`\` خروجی‌: \`\`\`bash [۴. ۷۰۹۳۴۷]
r۸۱۶۹ ۰۰۰۰: ۰۲: ۰۰. ۰: eth۰: RTL۸۱۶۸c/۸۱۱۱c at ۰xffffc۹۰۰۱۰۹c۸۰۰۰، ۰۰:
۲۴: ۱d: d۱: ۰۴: d۰، XID ۱c۴۰۰۰c۰ IRQ ۴۰ \`\`\` و یا: \`\`\`bash \# dmesg
| grep -i eth۰ \`\`\` نمایش جدول تمام رابط‌های شبکه‌: \`\`\`bash \#
netstat -i \`\`\` خروجی‌: \`\`\`bash Kernel Interface table Iface MTU
Met RX-OK RX-ERR RX-DRP RX-OVR TX-OK TX-ERR TX-DRP TX-OVR Flg eth۰ ۱۵۰۰
۰ ۱۸۴۰۸ ۰ ۰ ۰ ۲۰۵۲۴ ۰ ۰ ۰ BMRU lo ۱۶۴۳۶ ۰ ۹۸۲۲ ۰ ۰ ۰ ۹۸۲۲ ۰ ۰ ۰ LRU
\`\`\` پیدا کردن چیپ NIC برای رفع نقض کردن کارت ارتنت (NIC) من پیشنهاد
می‌کنم که از دستور lspci استفاده کنید‌. Lspci ابزاری برای نمایش اطلاعات
تمام درگاه‌های PCI موجود در سیستم که ابزار‌ی به‌شان متصل شده می‌باشد‌.
\`\`\`bash lspci | less \`\`\` یا \`\`\`bash `lspci | grep Ethernet`
\`\`\` خروجی‌: \`\`\`bash ۰۲: ۰۰. ۰ Ethernet controller: Realtek
Semiconductor Co.، Ltd. RTL۸۱۱۱/۸۱۶۸B PCI Express Gigabit Ethernet
controller (rev ۰۲) \`\`\` در مثال بالا من یک کارت «Realtec
Semiconductor» با چیپ RTL-۸۱۱۱/۸۱۶۸B دارم‌.

[**منبع**](http://www.cyberciti.biz/faq/how-can-i-find-out-if-my-ethernet-card-nic-is-being-recognized-or-not/ "NIC on cyberciti")