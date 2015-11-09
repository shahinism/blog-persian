.. date: 2013/09/12 11:31:45
.. title: py3status ابزار مناسب برای گرفتن اطلاعات در نوار ابزار i3
.. description: 
.. link: 
.. slug: py3status
.. tags: i3, i3status, python, py3status, i3bar

قبلا در مورد i3_ `حرف زده‌ام <http://shahinism.github.io/posts/blog13910415tjrbh-khr-b-i3-ykh-rgyb-qdr.html>`_ و نوشته‌ام که چطور با شل اسکریپت، و برای جلوگیری از مصرف زیاد رم (که Conky قاتلش بود) اطلاعات وضعیت سیستمم را در i3bar `نمایش می‌دهم <http://shahinism.github.io/posts/blog13910904dryft-tlt-systm-bdwn-stfdh-z-conky.html>`_. خوب، حقیقتش بعد از مدتی فهمیدم که شل اسکریپتم در ازای اجرای طولانی مدت، رم زیادی می‌خورد و از طرفی، خیلی ساده است. خوب یکی از مزیت‌های i3status_ این است که اطلاعات را به صورت رنگی نمایش می‌دهد که جدای از زیبایی بصری، به درک سریع اطلاعات کمک می‌کند. ولی بدبختی این i3status_ هم این است که به قدر کافی قابل گسترش نیست و ابزارهایی هم که خودش در اختیارتان می‌گذارد فوق‌العاده محدود است!

این وضعیت از قرار تنها مرا آزار نمی‌داده. ultrabug روی github پروژهٔ پایتونی‌ای را `شروع کرده <https://github.com/ultrabug/py3status>`_ که در واقع حکم یک پوشش برای i3status_ را دارد. وظیفهٔ این پروژه این است که اسکریپت پایتونی شما را تحویل گرفته و آن را با کمک i3status_ در i3bar به نمایش در آورد. خوبی ویژه‌اش این است که شما هم می‌توانید خودتان اسکریپت بنویسید و هم از ابزارهای آمادهٔ i3status_ استفاده کنید و در آخر هم از فایل تنظیمات i3status_ برای تنظیم هر دو ابزار بهره بگیرید.

نصب و ساخت اسکریپت
========================

برای شروع کافیست آن را نصب کرده و دستور زیر را در فایل تنظیمات i3‌تان قرار دهید (مسیر ‎ ~/‌.‌i3/config):

.. code:: bash

      bar {
        status_command py3status -i ~/.i3/py3status -c ~/.i3/i3status.conf
      }

با این دستور ما به i3_ می‌فهمانیم که باید از py3status_ برای نمایش داده‌های i3bar استفاده کند. همینطور به py3status_ می‌گوییم که فایل تنظیمات i3status_ در کدام مسیر واقع شده و در کدام مسیر باید به دنبال اسکریپت‌های پایتونی ما بگردد (‎‌~/‌.‌i3/py3status که یک دایرکتوری برای اسکریپت‌های ماست).

لازمهٔ اسکریپتی که می‌نویسید این است که حتما کلاسی به اسم Py3status_ داشته باشد که اطلاعات نهایی را در آن پردازش کرده و نمایش دهد. همچنین این کلاس باید در پاسخ فراخوانی‌اش موقعیتی که می‌خواهیم نتیجهٔ اسکریپت در آن نمایش داده شود (به عدد) و کل رشتهٔ خروجی را بازگرداند. چیزی مثل return(0, response)‎‌. برای نمونه به این کلاس توجه کنید:

.. code:: python

  class Py3status:
    """
    System status in i3bar
    """
    def ramInfo(self, json, i3status_config):
        """calculate the memory (RAM) status and return it.

        """
        data = GetData()
        response = {'full_text': '', 'name': 'ram_info'}
        total_mem, used_mem, used_mem_percent = data.memory()

        if used_mem_percent <= 40:
            response['color'] = i3status_config['color_good']
        elif used_mem_percent <= 75:
            response['color'] = i3status_config['color_degraded']
        else:
            response['color'] = i3status_config['color_bad']

        response['full_text'] = "RAM: %.2f/%.2f GB (%d%%)" % \
                                (used_mem, total_mem, used_mem_percent)
        response['cached_until'] = time()

        return (0, response)


پوشهٔ نمونه‌ها
==============

.. image:: https://dl.dropboxusercontent.com/u/25017694/Blog-photos/py3status_in_use.png

کاربران py3status_ ابزارهای مختلفی در این زمینه نوشته‌اند که در پوشهٔ Examples پروژه می‌توانید نمونه‌هایی از آن‌ها را ببینید. برای مثال دو اسکریپت netdata (که وظیفهٔ بررسی سرعت اینترنت و حجم دریافتی یا ارسالی داده را بر عهده دارد) و sysdata (که میزان مصرفی رم را محاسبه می‌کند) را من نوشته‌ام و در پروژه اصلی به اشتراک گذاشته‌ام. همینطور یک اسکریپت قابل کنترل با کیبورد برای `pomodoro <http://shahinism.github.io/posts/blog13900424ashnyy-b-tkhnykh-mdyryt-zmn-pmwdwr-.html>`_ هم ساخته شده که می‌توانید مدیریت زمان فعالیتتان را با آن انجام دهید.

.. _i3: http://i3wm.org/
.. _py3status: https://github.com/ultrabug/py3status 
.. _i3status: http://i3wm.org/i3status/
