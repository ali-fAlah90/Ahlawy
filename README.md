<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>أهلاوي - صوت الـ 100 مليون</title>
    <style>
        body {
            font-family: 'Cairo', sans-serif; /* خط عربي أكثر حداثة وجمالية */
            background-color: #f0f2f5;
            color: #333;
            margin: 0;
            padding: 0;
            line-height: 1.8; /* زيادة تباعد الأسطر لتحسين القراءة */
        }
        .header {
            background-color: #a00000; /* أحمر الأهلي الأصلي */
            color: white;
            padding: 25px 0; /* زيادة حجم الهيدر */
            text-align: center;
            font-size: 3em; /* تكبير حجم الخط */
            font-weight: bold;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3); /* ظل أوضح */
            letter-spacing: 2px; /* تباعد الحروف */
        }
        .navbar {
            background-color: #8b0000; /* أحمر أغمق قليلاً */
            overflow: hidden;
            box-shadow: 0 3px 8px rgba(0, 0, 0, 0.15);
            display: flex;
            justify-content: center;
            padding: 5px 0; /* padding أقل للناف بار */
        }
        .navbar a {
            display: block;
            color: white;
            text-align: center;
            padding: 16px 25px; /* padding أكبر للروابط */
            text-decoration: none;
            font-size: 1.2em; /* تكبير حجم الخط */
            transition: background-color 0.3s ease, transform 0.2s ease; /* إضافة ترانزيشن للحركة */
            cursor: pointer;
        }
        .navbar a:hover {
            background-color: #b30000;
            transform: translateY(-2px); /* تأثير رفع بسيط عند المرور */
        }
        .container {
            width: 90%; /* عرض أكبر للمحتوى */
            max-width: 1100px; /* تحديد أقصى عرض */
            margin: 35px auto; /* زيادة الهامش العلوي والسفلي */
            background-color: white;
            padding: 40px; /* زيادة padding داخلي */
            border-radius: 12px; /* حواف أكثر دائرية */
            box-shadow: 0 0 20px rgba(0, 0, 0, 0.15); /* ظل أوضح */
            display: none;
        }
        .container.active {
            display: block;
        }
        .section-title {
            color: #a00000;
            text-align: center;
            margin-bottom: 30px; /* زيادة المسافة تحت العنوان */
            font-size: 2.5em; /* تكبير حجم العنوان */
            border-bottom: 4px solid #a00000; /* خط سميك */
            padding-bottom: 15px;
            display: inline-block;
            width: 100%;
            font-weight: bold;
        }
        /* Style for Home section news */
        .news-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); /* تخطيط شبكي للأخبار */
            gap: 30px; /* مسافة بين الأخبار */
        }
        .news-item {
            background-color: #fefefe;
            border: 1px solid #eee;
            border-radius: 10px;
            padding: 20px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.08);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        .news-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 6px 15px rgba(0, 0, 0, 0.12);
        }
        .news-item h3 {
            color: #a00000;
            margin-bottom: 12px;
            font-size: 1.6em;
            border-bottom: 2px dashed #f0f0f0;
            padding-bottom: 10px;
        }
        .news-item p {
            color: #444;
            font-size: 1.1em;
        }
        .news-item a {
            display: inline-block;
            margin-top: 15px;
            color: #007bff; /* لون أزرق للرابط */
            text-decoration: none;
            font-weight: bold;
            transition: color 0.3s ease;
        }
        .news-item a:hover {
            color: #0056b3;
        }

        /* Style for Matches section */
        .match-list {
            list-style: none;
            padding: 0;
        }
        .match-item {
            background-color: #f9f9f9;
            border: 1px solid #ddd;
            border-radius: 10px;
            padding: 20px 25px;
            margin-bottom: 20px;
            display: flex;
            flex-direction: column; /* جعل العناصر تتكدس رأسيا */
            align-items: flex-start; /* محاذاة لليسار */
            box-shadow: 0 3px 8px rgba(0, 0, 0, 0.08);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        .match-item:hover {
            transform: scale(1.02); /* تكبير بسيط عند المرور */
            box-shadow: 0 5px 12px rgba(0, 0, 0, 0.1);
        }
        .match-item strong {
            color: #a00000;
            font-size: 1.5em;
            margin-bottom: 8px; /* مسافة تحت اسم المباراة */
        }
        .match-item span {
            font-size: 1.1em;
            color: #555;
            margin-bottom: 5px; /* مسافة بين تفاصيل المباراة */
        }
        .match-item .details {
            font-size: 1em;
            color: #777;
        }

        /* Style for Tickets section */
        .no-tickets-message {
            font-size: 2.2em; /* تكبير حجم الرسالة */
            color: #e60000;
            margin-top: 60px;
            margin-bottom: 40px;
            font-weight: bold;
            text-shadow: 1px 1px 2px rgba(0,0,0,0.1);
        }
        .info-text {
            font-size: 1.3em; /* تكبير حجم النص */
            color: #555;
            margin-bottom: 25px;
        }

        /* Style for Contact section */
        .contact-form {
            max-width: 700px; /* عرض أكبر للنموذج */
            margin: 0 auto;
            padding: 30px;
            border: 1px solid #ddd;
            border-radius: 12px;
            background-color: #f9f9f9;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        .form-group {
            margin-bottom: 20px; /* مسافة أكبر بين حقول النموذج */
        }
        .form-group label {
            display: block;
            margin-bottom: 10px;
            font-weight: bold;
            color: #555;
            font-size: 1.1em;
        }
        .form-group input[type="text"],
        .form-group input[type="email"],
        .form-group textarea {
            width: calc(100% - 24px); /* خصم padding من العرض الكلي */
            padding: 14px; /* padding أكبر */
            border: 1px solid #ccc;
            border-radius: 7px; /* حواف أكثر دائرية */
            box-sizing: border-box;
            font-size: 1.1em;
        }
        .form-group textarea {
            resize: vertical;
            min-height: 150px; /* ارتفاع أكبر لمربع النص */
        }
        .form-group input[type="submit"] {
            background-color: #a00000;
            color: white;
            padding: 15px 30px; /* padding أكبر للزر */
            border: none;
            border-radius: 7px;
            cursor: pointer;
            font-size: 1.2em; /* تكبير حجم خط الزر */
            font-weight: bold;
            transition: background-color 0.3s ease, transform 0.2s ease;
        }
        .form-group input[type="submit"]:hover {
            background-color: #8b0000;
            transform: translateY(-2px);
        }

        .footer {
            background-color: #333;
            color: white;
            text-align: center;
            padding: 25px 0; /* padding أكبر للفوتر */
            margin-top: 40px; /* مسافة أكبر فوق الفوتر */
            font-size: 1em;
        }
    </style>
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;700&display=swap" rel="stylesheet">
</head>
<body>
    <div class="header">
        أهلاوي - صوت الـ 100 مليون
    </div>

    <div class="navbar">
        <a onclick="showSection('home')">الرئيسية</a>
        <a onclick="showSection('matches')">مواعيد مباريات الأهلي</a>
        <a onclick="showSection('tickets')">تذاكر مباريات الأهلي</a>
        <a onclick="showSection('contact')">تواصل معنا</a>
    </div>

    <div id="home" class="container active">
        <h2 class="section-title">آخر أخبار الأهلي</h2>

        <div class="news-grid">
            <div class="news-item">
                <h3>الأهلي ينهي معسكره الخارجي بنجاح ويستعد للدوري الممتاز</h3>
                <p>اختتم الفريق الأول بالنادي الأهلي معسكره الإعدادي الخارجي في النمسا والذي استمر لأكثر من 10 أيام، وشهد تدريبات مكثفة ومباريات ودية قوية استعداداً لانطلاق الموسم الجديد من الدوري الممتاز وكأس السوبر الإفريقي. أبدى الجهاز الفني ارتياحاً كبيراً لمستوى اللياقة البدنية للاعبين والانسجام داخل الفريق.</p>
                <p style="font-size: 0.9em; color: #888;">المصدر: الموقع الرسمي للنادي الأهلي | 7 سبتمبر 2024</p>
                <a href="https://www.alahlyegypt.com/ar/news/8128" target="_blank">اقرأ المزيد</a>
            </div>

            <div class="news-item">
                <h3>الأهلي يواجه الرجاء المغربي في السوبر الأفريقي</h3>
                <p>تأكدت مواجهة الأهلي المرتقبة أمام الرجاء المغربي في بطولة كأس السوبر الأفريقي، بعد تتويج الأهلي بدوري أبطال أفريقيا والرجاء بكأس الكونفدرالية. يستعد الأهلي بقوة لهذه المواجهة الهامة التي يسعى من خلالها لإضافة لقب قاري جديد لخزائنه، وتعد المباراة اختباراً حقيقياً لقوة الفريق مع بداية الموسم.</p>
                <p style="font-size: 0.9em; color: #888;">المصدر: كووورة | 5 سبتمبر 2024</p>
                <a href="https://www.kooora.com/" target="_blank">اقرأ المزيد</a>
            </div>

            <div class="news-item">
                <h3>حلم كأس العالم للأندية 2025: الأهلي يتأهل رسميًا</h3>
                <p>تأكد تأهل النادي الأهلي رسميًا لبطولة كأس العالم للأندية الموسعة التي ستقام في الولايات المتحدة الأمريكية عام 2025. جاء التأهل بعد المستويات المتميزة التي قدمها الفريق في البطولات القارية الأخيرة وتصنيفه ضمن أفضل الأندية الأفريقية. يمثل هذا التأهل إنجازًا كبيرًا وفرصة فريدة للأهلي لمواجهة كبار الأندية العالمية.</p>
                <p style="font-size: 0.9em; color: #888;">المصدر: فيفا | 1 سبتمبر 2024</p>
                <a href="https://www.fifa.com/ar/club-world-cup" target="_blank">اقرأ المزيد</a>
            </div>
        </div>
        <p style="text-align: center; color: #777; font-size: 1em; margin-top: 30px;">
            تابعونا لمزيد من الأخبار والتحديثات الحصرية عن نادي القرن.
        </p>
    </div>

    <div id="matches" class="container">
        <h2 class="section-title">مواعيد مباريات الأهلي القادمة</h2>

        <ul class="match-list">
            <li class="match-item">
                <strong>بطولة: كأس السوبر الإفريقي</strong>
                <span>المباراة: الأهلي vs الرجاء الرياضي المغربي</span>
                <span>الموعد: 15 سبتمبر 2024</span>
                <span>التوقيت: 09:00 مساءً بتوقيت القاهرة</span>
                <span>الملعب: استاد القاهرة الدولي</span>
            </li>
            <li class="match-item">
                <strong>بطولة: الدوري المصري الممتاز (الجولة الأولى)</strong>
                <span>المباراة: الأهلي vs فريق X</span>
                <span>الموعد: 22 سبتمبر 2024</span>
                <span>التوقيت: 07:00 مساءً بتوقيت القاهرة</span>
                <span>الملعب: استاد السلام</span>
            </li>
            <li class="match-item">
                <strong>بطولة: الدوري المصري الممتاز (الجولة الثانية)</strong>
                <span>المباراة: الأهلي vs فريق Y</span>
                <span>الموعد: 28 سبتمبر 2024</span>
                <span>التوقيت: 04:00 مساءً بتوقيت القاهرة</span>
                <span>الملعب: استاد برج العرب</span>
            </li>
        </ul>
        <p style="text-align: center; color: #777; font-size: 1.1em; margin-top: 20px;">
            **ملاحظة:** هذه المواعيد هي الأقرب للواقع بناءً على المعلومات المتاحة حاليًا وقد تتغير بقرار من الجهات المنظمة.
        </p>
    </div>

    <div id="tickets" class="container">
        <h2 class="section-title">تذاكر مباريات الأهلي</h2>

        <div style="text-align: center;">
            <div class="no-tickets-message">
                عفوًا، لا توجد تذاكر متاحة حاليًا.
            </div>
            <p class="info-text">
                جمهور الأهلي العظيم، نعتذر عن عدم توفر التذاكر في الوقت الحالي.
                <br>
                يرجى متابعة قنواتنا الرسمية وموقعنا بانتظام للحصول على آخر التحديثات بخصوص توفر التذاكر.
                <br>
                دعمكم هو وقودنا!
            </p>
        </div>
    </div>

    <div id="contact" class="container">
        <h2 class="section-title">تواصل معنا</h2>

        <div class="contact-form">
            <form action="#" method="post">
                <div class="form-group">
                    <label for="name">الاسم الكامل:</label>
                    <input type="text" id="name" name="name" required>
                </div>
                <div class="form-group">
                    <label for="email">البريد الإلكتروني:</label>
                    <input type="email" id="email" name="email" required>
                </div>
                <div class="form-group">
                    <label for="subject">الموضوع:</label>
                    <input type="text" id="subject" name="subject" required>
                </div>
                <div class="form-group">
                    <label for="message">رسالتك:</label>
                    <textarea id="message" name="message" required></textarea>
                </div>
                <div class="form-group" style="text-align: center;">
                    <input type="submit" value="إرسال الرسالة">
                </div>
            </form>
            <p style="text-align: center; margin-top: 20px; color: #777;">
                صوت جمهور الأهلي مسموع دائمًا! سنتواصل معك في أقرب وقت ممكن.
            </p>
        </div>
    </div>

    <div class="footer">
        &copy; 2025 أهلاوي - صوت الـ 100 مليون. كل الحقوق محفوظة.
    </div>

    <script>
        function showSection(sectionId) {
            var containers = document.querySelectorAll('.container');
            containers.forEach(function(container) {
                container.classList.remove('active');
            });
            document.getElementById(sectionId).classList.add('active');
        }

        document.addEventListener('DOMContentLoaded', function() {
            showSection('home');
        });
    </script>
</body>
</html>
