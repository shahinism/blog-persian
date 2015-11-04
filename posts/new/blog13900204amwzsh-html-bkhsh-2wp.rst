.. title: آموزش HTML بخش ۲ .. date: 2011/4/24 00:32:15

.. raw:: html

   <html>

.. raw:: html

   <body>

.. raw:: html

   <p>

خوب‌، در بخش اول با ساختار کلی یک سند HTML آشنا شدیم‌، و نحوهٔ ایجاد آن
را یاد گرفتیم‌. در این بخش می‌خواهیم با امکاناتی که برای تایپوگرافی در
HTML قرار داده شده آشنا شویم‌.

نکته‌: بعضی از تگ‌های استفاده شده در این آموزش در نسخهٔ جدید HTML دیگر
جایی ندارند‌، و آن هم به دلیل استفاده از CSS در کنار HTML است‌. ولی آشنا
شدن با آن‌ها می‌تواند کمک فراوانی به یاد‌گیری سریع‌تر CSS -که در آینده
قصد بر آن داریم- کند‌.

.. raw:: html

   </p>

.. raw:: html

   <h3>

 انواع تیتر‌ها‌:

.. raw:: html

   </h3>

در HTML تگ‌هایی برای شناساندن تیتر‌ها به مرور‌گر و در نتیجه نمایش مناسب
آن‌ها در نظر گرفته شده است که ساختاری برابر <Hn> دارند‌. در این نوع تگ
حرف n برابر با مقداری است که از یک شروع می‌شود‌، و به نسبت بزرگ‌تر شدن
این مقدار‌، اندازهٔ تیتر به کوچک‌تر شدن میل می‌کند‌. برای درک بهتر این
موضوع سعی می‌کنیم‌، در صفحه‌ای که قبلا ساختیم یک تیتر ایجاد کنیم‌:

.. code:: bash


    &lt;html&gt;

    &lt;head&gt;

    &lt;title&gt;First HTML!&lt;/title&gt;

    &lt;/head&gt;

    &lt;body text="yellow" bgcolor="brown"&gt;

    &lt;h1&gt;Hello World&lt;/h1&gt;

    &lt;/body&gt;

    &lt;/html&gt;

نتیجهٔ این کد برابر با تصویر زیر می‌باشد‌. همانطور که می‌بینید عبارت
Hello World به صورت بزرگ نوشته شده است‌.

برای درک بهتر مقدار n در <Hn> از دو مقدار دیگر <h2><h3> به صورت زیر
استفاده می‌کنم‌:

.. code:: bash


    &lt;html&gt;

    &lt;head&gt;

    &lt;title&gt;First HTML!&lt;/title&gt;

    &lt;/head&gt;

    &lt;body text="yellow" bgcolor="brown"&gt;

    &lt;h1&gt;Hello World&lt;/h1&gt;

    &lt;h2&gt;This is an HTML Document&lt;/h2&gt;

    &lt;h3&gt;Season 2&lt;h3&gt;

    &lt;/body&gt;

    &lt;/html&gt;

همانطور که می‌بینید عبارات نوشته شده با اندازه‌های متفاوت به نمایش در
آمده‌اند‌. یکی از مهم‌ترین مزایای استفاده از این تگ‌ها در Seo است که به
موتور‌های جستجو امکان می‌دهد که به راحتی بخش‌های مختلف سند را درک کنند‌.

.. raw:: html

   <h3>

انواع نوشته‌ها‌:

.. raw:: html

   </h3>

.. raw:: html

   <ul>

.. raw:: html

   <li>

Bold : برای نوشتن به صورت تو پر یا همان bold از تگ <b></b> استفاده
می‌شود‌.

.. raw:: html

   </li>

.. raw:: html

   </ul>

.. raw:: html

   <ul>

.. raw:: html

   <li>

Italic : برای نوشتن به صورت مورب نیز از تگ<i></i> استفاده می‌شود‌.

.. raw:: html

   </li>

.. raw:: html

   </ul>

.. raw:: html

   <ul>

.. raw:: html

   <li>

Strike : برای نوستن به صورت رو خط دار از تگ <strike></strike> استفاده
می‌شود‌.

.. raw:: html

   </li>

.. raw:: html

   </ul>

.. raw:: html

   <ul>

.. raw:: html

   <li>

Underline : برای نوشتن به صورت زیر خط دار از تگ <u></u> استفاده می‌شود‌.

.. raw:: html

   </li>

.. raw:: html

   </ul>

خوب می‌خواهیم صفحهٔ ساخته شدمان را اندکی زیبا‌تر کنیم؛ برای این کار از
تگ‌هایی که اخیرا یاد گرفتیم استفاده می‌کنیم‌:

.. code:: bash


    &lt;html&gt;

    &lt;head&gt;

    &lt;title&gt;First HTML!&lt;/title&gt;

    &lt;/head&gt;

    &lt;body text="yellow" bgcolor="brown"&gt;

    &lt;h1&gt;Hello World&lt;/h1&gt;

    &lt;h3&gt;This is an HTML Document &lt;i&gt;season #2&lt;/i&gt;&lt;/h3&gt;

    This is an free tutorial for &lt;b&gt;HTML&lt;/b&gt; from &lt;b&gt;&lt;u&gt;shahinism.com&lt;/u&gt;&lt;/b&gt;

    &lt;/body&gt;

    &lt;/html&gt;

همانطور که می‌بینید توانستیم با تگ‌هایی ساده یک تایپوگرافی معقول ایجاد
کنیم‌. تنها نکته‌ای که در مثال اخیر باید مورد توجه قرار گیرد‌، این قسمت
است‌: <b><u>shahinism.com</u></b>همانطور که می‌بینید از دو تگ زیر خط و
نوشتهٔ تو پر به صورت همزمان استفاده شده‌. ولی تگ‌ها از آخر به اول بسته
شده‌.

.. raw:: html

   <h3>

موقعیت نوشته‌:

.. raw:: html

   </h3>

برای تعیین موقعیت نوشته‌ها نیز در HTML امکاناتی در نظر گرفته شده‌. که به
تعدادی از آن‌ها اشاره می‌کنیم‌:

.. raw:: html

   <ul>

.. raw:: html

   <li>

Center: برای وسط‌چین کردن نوشته استفاده می‌شود‌.

.. raw:: html

   </li>

.. raw:: html

   </ul>

.. raw:: html

   <ul>

.. raw:: html

   <li>

<br> : برای شکستن خط و شروع در خط جدید مورد استفاده قرار می‌گیرد‌.

.. raw:: html

   </li>

.. raw:: html

   </ul>

.. raw:: html

   <ul>

.. raw:: html

   <li>

<sub> و <sub> : که برای نمایش اندیس و توان مورد استفاده قرار می‌گیرد‌.

.. raw:: html

   </li>

.. raw:: html

   </ul>

اکنون می‌خواهیم با کد‌هایی که یاد گرفتیم تغییرات دیگری را نیز در سند
ایجاد کنیم‌:

.. code:: bash


    &lt;html&gt;

    &lt;head&gt;

    &lt;title&gt;First HTML!&lt;/title&gt;

    &lt;/head&gt;

    &lt;body text="yellow" bgcolor="brown"&gt;

    &lt;center&gt;&lt;h1&gt;Hello World&lt;/h1&gt;&lt;/center&gt;

    &lt;h3&gt;This is an HTML Document &lt;i&gt;season &lt;sub&gt;#2&lt;/sub&gt;&lt;/i&gt;&lt;/h3&gt;

    This is an free tutorial for &lt;b&gt;HTML&lt;/b&gt; from: &lt;br&gt;&lt;b&gt;&lt;u&gt;shahinism.com&lt;/u&gt;&lt;/b&gt;

    &lt;/body&gt;

    &lt;/html&gt;

همانطور که در تصویر زیر می‌بینیم #۲مقداری به پایین منتقل شده‌، هم‌چنین
آدرس سایت نیز با توجه به اینکه در ادامهٔ خط نوشته شده‌، ولی پایین‌تر
آمده‌. واضح‌ترین تغییر نیز در این مثال عبارت Hello World است که به وسط
صفحه تغییر مکان داده‌.

.. raw:: html

   <h3>

تغییر قلم‌:

.. raw:: html

   </h3>

برای تغییر قلم نوشته (فونت‌) نیز می‌توانید از تگ فونت استفاده کنید‌.
نمونه‌ای از استفاده از این قلم را در کد زیر ببینید‌:

.. code:: bash


    &lt;html&gt;

    &lt;title&gt;Font Change&lt;/title&gt;

    &lt;/html&gt;

    &lt;body&gt;

    Hi my friends &lt;font face="tahoma" size=24 color=red&gt;in this page we have 2&lt;/font&gt; different font.

    &lt;/body&gt;

    &lt;/html&gt;

نتیجه‌ی مثال زیر را در تصویر زیر می‌بینیم‌:

لازم به ذکر است‌، مرور‌گر‌ها به صورت پیش‌فرض فونتی را برای نمایش نوشته
در نظر می‌گیرند که با مراجعه به بخش تنظیمات هر مرورگر قابل تغییر است‌.
فونت تعیین شده در کد بالا در صورتی که روی سیستم کاربر موجود باشد‌، نمایش
داده می‌شود‌، در غیر این صورت از فونت پیش‌فرض استفاده می‌شود‌. در بخش
آموزش CSS روشی از CSS3 را می‌آموزیم که این نقظه ضعف را پوشش می‌دهد‌.

.. raw:: html

   </body>

.. raw:: html

   </html>
