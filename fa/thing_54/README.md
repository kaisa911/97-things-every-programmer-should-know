# چه‌موقع و چگونه از راه‌کارهای موقتی در کدنویسی استفاده کنیم؟

در پاسخ به این سؤال که چرا برخی دولوپرها دست به استفاده از سولوشن‌های (راه‌کارهای) موقتی می‌زنند بایستی گفت که علت اصلی مشکلات غیرمنتظره‌ای هستند که پیش می‌آیند و بایستی در کوتاه‌ترین زمان ممکن رفع شوند.

در بسیاری از تیم‌های توسعه‌ٔ نرم‌افزار همواره بخش‌‌هایی وجود دارند که هرگز از استانداردهای کدنویسی تبعیت نکرده و با سایر بخش‌های سورس‌کد هم‌خوانی ندارند و بالاخره روزی می‌بایست ریفکتور شده و با سایر بخش‌های سیستم هارمونی پیدا کنند.

نیاز به توضیح هم نیست که اکثر دولوپرها همواره از این موضوع شاکی هستند؛ گرچه دلایل بسیاری برای وجود این دست «راه‌کارهای موقتی» بسیارند اما کلید موفقیت این دست راه‌کارها کاربردی بودنشان است!

باتوجه به این که Interim Solutions (راه‌کارهای موقتی) به‌نوعی مفید واقع شده و مورد قبول برخی دولوپرها قرار گرفته‌اند، کمتر کسی را می‌توان یافت که برای رفع آن‌ها گامی بردارد چراکه مفید، کاربردی و مشکل‌گشا بوده و تنها نقطه‌ضعفی که دارند این است که استانداردهای کدنویسی را فالو نمی‌کنند (البته این درحالی است که چنین چیزی در بسیاری از شرکت‌های نرم‌افزاری و تیم‌های توسعه اصلاً مشکل خاصی محسوب نمی‌شود).

حال ممکن است زمان‌هایی پیش آید که پس از پیاده‌سازی راه‌کارهای موقتی به‌منظور رفع یک باگ و یا افزودن یک فیچر جدید، نرم‌افزار پس از مدتی به مشکل می‌خورد و از آنجا که استانداردهای کدنویسی در پیاده‌سازی این دست راه‌کارها اعمال نشده، طبق روال هم به‌سادگی نمی‌توان دست به رفع مشکلات پیش آمده زد.

در پاسخ به این سؤال که در چنین مواقعی چه باید کرد؟ بایستی گفت که معمولاً آپدیت‌های موقعی روی باگ‌های موجود در راه‌کارهای موقتی جواب می‌دهند و از لحاظ ماهیت، آپدیت‌های موقتی دقیقاً شبیه راه‌کارهای موقتی هستند با این تفاوت که کمی به‌روزشده‌تر می‌باشند.

همواره این نکته را به‌خاطر داشته باشیم زمانی‌که پروژه‌ای حاوی راه‌کارهای موقتی بسیاری باشد، از یک سو پیچیدگی سورس‌کد افزایش یافته و از سوی دیگر نگهداری، آپدیت و دیباگینگ نرم‌افزار هم به‌مراتب دشوارتر خواهد شد. به‌عنوان یک Best Practice کلی، وقتی در فرایند توسعه‌ٔ نرم‌افزار با مشکلی روبه‌رو شدید، ابتدا مراحل زیر را به ترتیب اولویت انجام دهید:

۱- تا حد ممکن از ارائهٔ راه‌کارهای موقتی خودداری کنید. خودداری‌هایی از این دست در بسیاری از موارد چارهٔ کار نیست چراکه ممکن است مشکلی جدی بوجود آمده باشد که نیاز است تا در اسرع وقت رفع گردد و اگر دولوپر پروژه بخواهد استانداردهایی که تا پیش از این به‌کار می‌‌بسته را در رفع مشکل فعلی مدنظر گیرد، این استانداردها دست‌وپاگیر خواهند بود اما به‌هرحال به‌عنوان اولین تلاش چنین چیزی توصیه می‌شود.

۲- تا حد ممکن مقابل اصرارهای مدیر پروژه به‌منظور اعمال یک فیچر خاص در کمترین زمان ممکن مقابله نمایید. در برخی موارد، اصرارهای مدیر پروژه آنقدرها هم که وی وانمود می‌کند لازم‌الاجرا نیست و از همین روی ضرری ندارد که تا حدی در مقابل اصرارهای وی مقاومت کرد.

۳- اگر هم مجبور به این کار شدید، تا حد ممکن حداقل‌ استانداردهای کدنویسی را رعایت نمایید. به‌عبارت دیگر، اگر گایدلاین‌ها و استانداردهای کدنویسی را گروه‌بندی کنید، می‌توانید در اعمال چنین راه‌کارهایی آن‌دسته از استانداردهایی که به‌مراتب مهم‌تر از بقیه هستند را رعایت نموده و الباقی را نادیده بگیرید.