.. title: Syntax-highlighting برای خط فرمان ZSH .. date: 2012/3/21
4:21:43

قبلا که خط فرمان ZSH را [معرفی
کردم‌](http://shahinism.com/blog/1390/11/27/zsh-%d8%af%d9%88%d8%b3%d8%aa-%d8%b4%d9%85%d8%a7%d8%b3%d8%aa%e2%80%8c/ "Zsh دوست شماست‌!")،
در مورد مزایا و امکاناتش نسبت به بش نیز توضیح دادم. ولی حالا وقتی که کمی
درگیر این دستور نوشتن‌ها و ترکیبات مختلفشان شده باشید‌، مطمئنا می‌دانید
که رنگ شدن هوشمند دستورات یا همان Syntax-highlighting چقدر می‌تواند در
میان انبوه دستورات مفید باشد‌. خوب این‌جا دنیاییست که همه چیز در آن ممکن
است و حالا یک آدم خوش ذوق پیدا شده و همچین امکانی را برای ZSH محیا کرده.
برای دریافت آن می‌توانید به [این‌
لینک](https://github.com/zsh-users/zsh-syntax-highlighting "zsh-syntax-highlighting")
مراجعه کنید‌. و اگر به نصیحت قبلی‌ام گوش کرده‌اید و از oh-my-zsh استفاده
می‌کنید‌، به طریق زیر می‌توانید از این افزونه استفاده کنید‌. \`\`\`bash
cd \~/.oh-my-zsh/plugins git clone
https://github.com/zsh-users/zsh-syntax-highlighting \`\`\` و حالا برای
فعال کردن آن خط زیر را به ‎.zshrc موجود در پوشه خانگی اضافه می‌کنیم‌:
\`\`\`bash plugins=(zsh-syntax-highlighting) \`\`\` و برای اعمال
تغییرات: \`\`\`bash source \~/.zshrc \`\`\` حال با تایپ دستورات نتیجه‌ای
مانند
عک[![](/wp-content/uploads/highlight.png "highlight")](/wp-content/uploads/highlight.png)
زیر خواهید داشت:  
