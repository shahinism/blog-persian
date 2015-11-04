.. title: از Autojump در ترمینال غافل نشوید‌! .. date: 2012/8/4 9:9:9

.. raw:: html

   <html>

.. raw:: html

   <body>

قبلا در مورد Bashmark نوشته بودم و دقیقا همین قبلا بود که فرود عزیز گفت
که از Autojump استفاده می‌کند‌. اما آن موقع‌ها بخاطر یک باگ کوچک نادیده
گرفته بودمش‌! امروز که دیگر آن باگ یادم نبود بار دیگر تستش کردم و (آخه
دیگه چی بگم؟ این لعنتی خیلی با شعوره‌!) اصلا خودتان این ویدئو را ببینید
تا زورش را درک کنید:

.. raw:: html

   <p class="aligncenter">

.. raw:: html

   <iframe src="http://www.youtube.com/embed/tnNyoMGnbKg" frameborder="0" width="420" height="315">

.. raw:: html

   </iframe>

.. raw:: html

   </p>

هــاها‌! کدام ابزار را می‌شناسید که سریع‌تر بین دایرکتوری‌ها جابجایتان
کند؟ خوب دیگر پر حرفی بس است‌. برویم سر اصل ماجرا‌. نصب و حل یک مشکل‌!

.. raw:: html

   <h4>

نصب

.. raw:: html

   </h4>

برای نصب اگر پایتون روی سیستم‌تان بالا‌تر از ۲.۷ است که خیال‌تان راحت و
تنها کافییست که آن را از کانال گیتش دریافت کنید و پس از ورود به پوشه‌اش
اسکریپت install.sh را اجرا کنید‌. اما اگر مثل من با این ترافیک داغان
اینترنت روی اسلکور استیبل گیر کرده‌اید (این یعنی پایتون ۲.۶) پس باید یک
چند‌تا کار اضافه انجام دهید‌ (یا شاید هم بخواهید به ورژن ۱۹ که توی
اسلک‌بیلد‌ها پیدا می‌شود بسنده کنید):

.. code:: bash


    sbopkg -R -i "pysetuptools pip"

امیدوارم sbopkg را نصب کرده و بی‌خودی زندگی را برای خود سخت نگیرید ;-)
حالا هم کافیست که با pip بستهٔ مورد نیاز Autojump را نصب کنید‌:

.. code:: bash


    pip install argparse

و سپس:

.. code:: bash


    git clone git://github.com/joelthelion/autojump.git

    cd autojump

    ./install.sh --force

و حالا خط زیر را به ‎.zshrc اضافه کنید:

.. code:: bash


    [[ -s /etc/profile.d/autojump.zsh ]] &amp;&amp; source /etc/profile.d/autojump.zsh

و سر‌انجام:

.. code:: bash


    source ~/.zshrc

.. raw:: html

   <h4>

مشکل

.. raw:: html

   </h4>

و خوب کار باید تمام شده باشد اما دستور زیر را امتحان کنید:

.. code:: bash


    vim ~/.zsh[TAB]

که احتمالا چیزی شبیه خروجی زیر نصیبتان می‌شود:

.. code:: bash


    _arguments:439: _vim_files: function definition file not found

    _arguments:439: _vim_files: function definition file not found

    _arguments:439: _vim_files: function definition file not found

و این یعنی اتوکامپلیشن فوق‌العادهٔ ZSH جلوی دستور vim از کار می‌افتد‌!
خوب چه کنیم؟ تنها یک راه حل در اینترنت جواب این مساله بود و آن هم از
انجمن آرچر‌های اعظم:

.. code:: bash


    $ echo $fpath (see the function PATH of zsh)

    /usr/share/zsh/site-functions /usr/share/zsh/4.3.11/functions

    $ cd /usr/share/zsh/4.3.11/functions

    $ ls _vi*

    _vim

    rm _vim

و حالا لذت ببرید ;-)

.. raw:: html

   </body>

.. raw:: html

   </html>
