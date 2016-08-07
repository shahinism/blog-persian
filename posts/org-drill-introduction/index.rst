.. link:
.. description:
.. tags: org, org-drill, Emacs, flashcard
.. date: 2014/03/22 13:11:34
.. title: org-drill ایکمس‌، رفیق حافظهٔ شما!
.. slug: org-drill-introduction

خوب اگر از پست‌های وبلاگم‌، مرا بشناسید می‌دانید که علاقهٔ زیادی به فلش‌کارت‌ها دارم! و این علاقه دلیلی جز عادت بدم در سریع خواندن مطالب مورد نیازم در هر لحظه و فراموشی سریع راه حل‌ها ندارد! خوب اگر مدتی مثل من کار کنید‌، می‌فهمید که در اکثر اوقات دنبال مسایل تکراری هستید که خیلی زود فراموش کرده‌اید و حالا دوباره باید وقت‌تان را به پایشان تلف کنید.

با وجود علاقهٔ زیادم به `فلش کارت‌ها <http://http://fa.wikipedia.org/wiki/%D8%AC%D8%B9%D8%A8%D9%87_%D9%84%D8%A7%DB%8C%D8%AA%D9%86%D8%B1>`_ هرگز به طور جدی ازشان استفاده نکردم. جدای از این که علاقه‌ای به نوشتن روی کاغذ هر مطلب جدیدی که می‌خواهم به خاطر بسپارم ندارم‌، نمونهٔ کامپیوتری سریعی هم برای ذخیرهٔ فلش کارت‌هایم نمی‌شناختم. در واقع Anki_ عالی بود‌، ولی آن هم پروسهٔ ذخیرهٔ فلش کارتش‌، زیادی آدم را از موضوع اصلی کار دور می‌کرد. اما الان ایمکس_ هست‌، قابلیت Capture‌ و org-mode دوست داشتنی‌اش که در ارسال_ قبلی‌ام بهشان اشاره کردم هستند و فقط جای خالی org-drill_ برای کامل کردن حلقه خالی است.

نصب org-mode به همراه org-drill
=======================================
org-drill_ را می‌توان در پوشهٔ contrib از پروژهٔ org پیدا کرد و از آن‌جایی که orgای که همراه خود ایمکس نصب می‌شود‌، از این پوشه فاکتور گرفته‌، باید org را از مخزن اصلی‌اش و به همراه این پوشه نصب کنید. اول لیست مخازن‌تان را به صورت زیر ویرایش کنید تا مخزن رسمی org هم به بسته‌های‌تان اضافه شود:

.. code:: cl

  (setq package-archives '(("org" . "http://orgmode.org/elpa/")
	  ("gnu" . "http://elpa.gnu.org/packages/")
	  ("marmalade" . "http://marmalade-repo.org/packages/")
	  ("melpa" . "http://melpa.milkbox.net/packages/")
	  ("SC" . "http://joseito.republika.pl/sunrise-commander/")))

حالا دستور زیر را وارد کنید:

.. code:: cl

   M-x package-install org-plus-contrib

حالا هم این خطوط را به ‎.emacs اضافه کنید تا org-drill فعال شود:

.. code:: cl

   (require 'org-drill)

تا این‌جای کار موفق به نصب org-drill_ شدیم. حالا کافیست که یک Capture هم برایش تعریف کنیم تا بتوان بدون دغدغهٔ زیادی اقدام به ایجاد یک فلش کارت کرد. برای مثال‌، کپچر من به شکل زیر است:

.. code:: cl

   (setq org-capture-templates
      '(("f" "Flashcard" plain (file (concat org-dir "flashcard.org"))
	 "* %^{Topic}\t\t\t\t:drill:\n%^{Question}\n** Answer\n%^{Answer}")))

با این کد ایمکس فلش‌کارت‌هایم را در فایل flashcard.org موجود در پوشهٔ فایل‌های orgام ذخیره می‌کند.

نحوهٔ کار
===========
برای کار با این بسته هم کافیست درون فایل مربوطه فلش کارتی به شکل زیر داشته باشیم:

.. code::

   * Topic          :drill:
   Question
   ** Hide
   Answer

اگر با org-mode کار کرده باشید کل قضیه برای‌تان روشن خواهد بود. اول فایل flashcard.org را باز می‌کنیم و سپس دستور زیر را وارد می‌کنیم:

.. code:: cl

   M-x org-drill

org-drill به دنبال شاخه‌هایی با تگ :drill: می‌گردد و از آن‌ها به عنوان فلش کارت استفاده می‌کند. در هر نمایش هم به طور پیشفرض بخش جواب نمایش داده نمی‌شود و منتظر فشار یک کلید می‌ماند. پس از نمایش جواب هم می‌توانید به خودتان نمره دهید که بر اساس همین نمره‌ها زمان نمایش دوباره به صورت یک properties زیر Topic تعیین می‌شود که خود org-drill می‌داند چطور باید از آن استفاده کند.

**پی‌نوشت‌ها:** در حین کار با این بسته به مشکلی برخوردم که ممکن است برای شما هم اتفاق بیافتد. این قضیه را در `bug‌های <https://bitbucket.org/eeeickythump/org-drill/issue/20/mapcar-wrong-type-argument-listp>`_ org-drill مطرح کردم و پس از حل شدن راه حلش را هم آن‌جا نوشتم که ممکن است به درد‌تان بخورد.

.. _org-drill: http://orgmode.org/worg/org-contrib/org-drill.html
.. _ارسال: http://shahinism.github.io/posts/bookmark_links_from_firefox_to_emacs_orgmode.html
.. _ایمکس: http://shahinism.github.io/categories/emacs.html
.. _Anki: http://ankisrs.net/docs/manual.html
