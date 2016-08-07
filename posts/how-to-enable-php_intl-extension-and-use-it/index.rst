.. link: 
.. description: نحوه فعال‌سازی افزونه intl php 
.. tags: intl, PHP, NumberFormatter, Gentoo
.. date: 2014/09/28 13:19:47
.. title: افزونه INTL PHP و کلاس NumberFormatter
.. slug: how-to-enable-php_intl-extension-and-use-it

ممکن است مثل امروز من بخواهید یک مقدار عددی را به واحد پولی کشوری و به صورت درست در PHP_ نمایش بدهید. در این صورت کلاس NumberFormatter_ می‌تواند کارتان را راه بیاندازد. برای مثال به تکه کد زیر نگاه کنید:

.. code:: php

	  <?php
	  $number = 1234.56;

	  $iran = new NumberFormatter("fa-IR", NumberFormatter::CURRENCY);
	  $formatted3 = $iran->format($number);
   
	  print "IRAN: ".$formatted3.'<br>';
	  ?>

خروجی این خطوط به این صورت خواهد بود:

.. code:: html

    IRAN: ‎ریال۱٬۲۳۵

ولی ممکن است مثل من با این اخطار روبرو شوید:

.. code::

   Fatal error: Class 'NumberFormatter' not found

و این به این معناست که احتمالا افزونه intl در در نصب PHP‌تان فعال نیست. برای تست این که آیا نیاز به نصب دارید یا نه‌، دستور زیر را اجرا کنید:

.. code:: bash

	  php -m | grep intl

اگر خروجی‌ای نداشتید یعنی این افزونه نصب نیست. بسته به توزیع مورد استفاده‌تان باید به دنبال روش نصبش باشید. مثلا در Gentoo_:

.. code:: bash

	  use="intl" emerge --oneshot -a php

یا در بعضی از توزیع‌های محبوب دیگر

.. code:: bash

	  // Debian 
	  apt-get install php5-intl
	  // Centos
	  yum install php-intl

حالا که کار نصب تمام شد کافیست در فایل php.ini‌تان این خط را وارد کنید:

.. code::

   extension=php_intl.dll

و تمام‌، حالا این افزونه و کلاس NumberFormatter_ در دسترس‌تان است.

.. _Gentoo: http://gentoo.org
.. _PHP: http://php.net
.. _NumberFormatter: http://php.net/manual/en/class.numberformatter.php
