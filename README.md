# ahmad-maryam-platform
منصة مأساة أحمد ومريم — قصة تفاعلية عربية
```html
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>مأساة أحمد ومريم - المنصة التفاعلية والتحليل الأدبي</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Chart.js CDN -->
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Amiri:ital,wght@0,400;0,700;1,400&family=Tajawal:wght@300;400;500;700&display=swap" rel="stylesheet">
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        sand: {
                            50: '#FAF8F5',
                            100: '#F4EFE6',
                            200: '#E8DEC9',
                            800: '#4A3E31',
                            900: '#2C231A',
                        },
                        maroon: {
                            100: '#F8E8E8',
                            600: '#9B2C2C',
                            800: '#631717',
                            900: '#420D0D',
                        },
                        amberCustom: '#C05621'
                    },
                    fontFamily: {
                        amiri: ['Amiri', 'serif'],
                        tajawal: ['Tajawal', 'sans-serif'],
                    }
                }
            }
        }
    </script>
    <style>
        body {
            background-color: #FAF8F5;
            color: #2C231A;
            font-family: 'Tajawal', sans-serif;
        }
        .chart-container {
            position: relative;
            width: 100%;
            max-width: 650px;
            margin-left: auto;
            margin-right: auto;
            height: 320px;
            max-height: 400px;
        }
        @media (min-width: 768px) {
            .chart-container {
                height: 360px;
            }
        }
        .custom-scroll::-webkit-scrollbar {
            width: 6px;
        }
        .custom-scroll::-webkit-scrollbar-track {
            background: #F4EFE6;
        }
        .custom-scroll::-webkit-scrollbar-thumb {
            background: #C05621;
            border-radius: 3px;
        }
    </style>
</head>
<body class="bg-sand-50 text-sand-900 min-h-screen flex flex-col antialiased">

    <!-- Header Navigation -->
    <header class="sticky top-0 z-50 bg-sand-100/90 backdrop-blur border-b border-sand-200 shadow-sm">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-16">
                <div class="flex items-center space-x-4 space-x-reverse">
                    <span class="text-2xl font-bold font-amiri text-maroon-800">مأساة أحمد ومريم</span>
                    <span class="hidden md:inline-block text-xs bg-maroon-100 text-maroon-800 px-2.5 py-1 rounded-full font-medium">دراسة سردية وتحليلية</span>
                </div>
                <nav class="hidden md:flex space-x-1 space-x-reverse text-sm font-medium">
                    <button onclick="switchTab('dashboard')" id="tab-btn-dashboard" class="nav-tab px-3 py-2 rounded-md transition text-maroon-800 bg-sand-200 font-bold">لوحة العرض</button>
                    <button onclick="switchTab('reader')" id="tab-btn-reader" class="nav-tab px-3 py-2 rounded-md transition text-sand-800 hover:bg-sand-200">النص الكامل</button>
                    <button onclick="switchTab('analysis')" id="tab-btn-analysis" class="nav-tab px-3 py-2 rounded-md transition text-sand-800 hover:bg-sand-200">الدليل الأدبي</button>
                    <button onclick="switchTab('medical')" id="tab-btn-medical" class="nav-tab px-3 py-2 rounded-md transition text-sand-800 hover:bg-sand-200">التحليل الطبي</button>
                </nav>
                <div class="md:hidden">
                    <select onchange="switchTab(this.value)" class="bg-sand-200 text-sand-900 text-sm rounded-md p-2 border border-sand-200">
                        <option value="dashboard">لوحة العرض العامة</option>
                        <option value="reader">النص الكامل للقصة</option>
                        <option value="analysis">دليل التحسين الأدبي</option>
                        <option value="medical">التحليل الطبي (تاكوتسوبو)</option>
                    </select>
                </div>
            </div>
        </div>
    </header>

    <!-- Main Content Area -->
    <main class="flex-grow max-w-7xl w-full mx-auto px-4 sm:px-6 lg:px-8 py-8">

        <!-- SECTION 1: DASHBOARD -->
        <section id="sec-dashboard" class="space-y-8">
            <!-- Intro Paragraph -->
            <div class="bg-white p-6 rounded-xl shadow-sm border border-sand-200">
                <h1 class="text-2xl font-bold font-amiri text-maroon-900 mb-2">مرحباً بك في المنصة التحليلية السردية</h1>
                <p class="text-sand-800 leading-relaxed">
                    تقدم هذه المنصة التفاعلية تحليلاً شاملاً ومكاملاً لرواية <strong>«مأساة أحمد ومريم: سيرة القهر الصامت والقصاص الأبدي»</strong>. يستعرض هذا القسم المتكامل مؤشرات الحالة النفسية للشخصيات الرئيسية، والمسار الزمني للحُب والانكسار، والتأثير الدرامي لعوامل التحريض الخارجي مقارنة بالجلد الذاتي.
                </p>
            </div>

            <!-- Stats Grid -->
            <div class="grid grid-cols-1 md:grid-cols-4 gap-4">
                <div class="bg-white p-5 rounded-xl border border-sand-200 shadow-sm text-center">
                    <div class="text-3xl font-bold text-maroon-800 font-amiri">10</div>
                    <div class="text-sm text-sand-800 mt-1">فصول درامية محكمة</div>
                </div>
                <div class="bg-white p-5 rounded-xl border border-sand-200 shadow-sm text-center">
                    <div class="text-3xl font-bold text-amberCustom font-amiri">15 يوماً</div>
                    <div class="text-sm text-sand-800 mt-1">فترة حصار التحريض المفصلية</div>
                </div>
                <div class="bg-white p-5 rounded-xl border border-sand-200 shadow-sm text-center">
                    <div class="text-3xl font-bold text-maroon-600 font-amiri">Takotsubo</div>
                    <div class="text-sm text-sand-800 mt-1">المسبب الطبي للوفاة (القلب المنكسر)</div>
                </div>
                <div class="bg-white p-5 rounded-xl border border-sand-200 shadow-sm text-center">
                    <div class="text-3xl font-bold text-sand-800 font-amiri">مطلق</div>
                    <div class="text-sm text-sand-800 mt-1">مستوى القصاص المعنوي (الفصل 10)</div>
                </div>
            </div>

            <!-- Dynamic Interactive Visuals Grid -->
            <div class="grid grid-cols-1 lg:grid-cols-2 gap-8">
                <!-- Dynamic Chart 1: Emotional Trajectory -->
                <div class="bg-white p-6 rounded-xl shadow-sm border border-sand-200 flex flex-col justify-between">
                    <div>
                        <h2 class="text-lg font-bold text-maroon-900 mb-1">مسار الاستقرار النفسي عبر الفصول</h2>
                        <p class="text-xs text-sand-800 mb-4">تتبع المنحنى البياني للحالة النفسية لكل من أحمد ومريم من الفصل الأول حتى العاشر.</p>
                        <div class="chart-container">
                            <canvas id="chartEmotionalJourney"></canvas>
                        </div>
                    </div>
                    <div class="mt-4 pt-3 border-t border-sand-100 text-xs text-sand-800">
                        💡 **ملاحظة تفاعلية:** انقر على أسماء الشخصيات في المفتاح أعلى الرسم البياني لعزل منحنى شخصية واحدة.
                    </div>
                </div>

                <!-- Dynamic Chart 2: External vs Internal Drivers -->
                <div class="bg-white p-6 rounded-xl shadow-sm border border-sand-200 flex flex-col justify-between">
                    <div>
                        <h2 class="text-lg font-bold text-maroon-900 mb-1">مسببات المأساة وتوزيع المؤثرات</h2>
                        <p class="text-xs text-sand-800 mb-4">نسبة التأثير الدرامي للتحريض الخارجي، مقابل صمت أحمد وتدميره الذاتي.</p>
                        <div class="chart-container">
                            <canvas id="chartDrivers"></canvas>
                        </div>
                    </div>
                    <div class="mt-4 pt-3 border-t border-sand-100 text-xs text-sand-800">
                        💡 **الخلاصة:** التحريض الخارجي (أم محسن) وجلد الذات المستمر شنا هجوماً مزدوجاً أدى لتوقف البطين الأيسر.
                    </div>
                </div>
            </div>

            <!-- Character Dynamics Interactive Cards -->
            <div class="bg-white p-6 rounded-xl shadow-sm border border-sand-200">
                <h2 class="text-lg font-bold text-maroon-900 mb-4">شخصيات المأساة والديناميكية الدرامية</h2>
                <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
                    <div class="p-4 rounded-lg bg-sand-50 border border-sand-200 hover:border-maroon-600 transition cursor-pointer" onclick="jumpToChapter(4)">
                        <div class="flex items-center justify-between mb-2">
                            <span class="font-bold text-maroon-900">أحمد</span>
                            <span class="text-xs bg-maroon-100 text-maroon-800 px-2 py-0.5 rounded">الضحية والسجان</span>
                        </div>
                        <p class="text-xs text-sand-800 leading-relaxed">
                            عاش 4 سنوات كفاح لأجل مريم، لكنه رفض اتهامها ومارس شيطنة الذات حمايةً لملاكها المزيف حتى انكسر قلبه طبيّاً.
                        </p>
                    </div>
                    <div class="p-4 rounded-lg bg-sand-50 border border-sand-200 hover:border-maroon-600 transition cursor-pointer" onclick="jumpToChapter(9)">
                        <div class="flex items-center justify-between mb-2">
                            <span class="font-bold text-maroon-900">مريم</span>
                            <span class="text-xs bg-amberCustom/10 text-amberCustom px-2 py-0.5 rounded">الانقلاب والألم</span>
                        </div>
                        <p class="text-xs text-sand-800 leading-relaxed">
                            وقعت تحت تأثير شحن أمها، وعادت لبيتها بقلب جاف من أجل طفلتها "رقية"، لتصحو متأخرة على خشبة المغتسل.
                        </p>
                    </div>
                    <div class="p-4 rounded-lg bg-sand-50 border border-sand-200 hover:border-maroon-600 transition cursor-pointer" onclick="jumpToChapter(8)">
                        <div class="flex items-center justify-between mb-2">
                            <span class="font-bold text-maroon-900">أم محسن</span>
                            <span class="text-xs bg-sand-200 text-sand-800 px-2 py-0.5 rounded">محرك التحريض</span>
                        </div>
                        <p class="text-xs text-sand-800 leading-relaxed">
                            مارست إعادة تأويل مستمرة لكل أفعال أحمد النبيلة وتأليب ابنته، ثم تبرأت بذعر عند الصدمة الأولى.
                        </p>
                    </div>
                </div>
            </div>
        </section>

        <!-- SECTION 2: READER MODE -->
        <section id="sec-reader" class="hidden space-y-6">
            <!-- Intro Paragraph -->
            <div class="bg-white p-6 rounded-xl shadow-sm border border-sand-200">
                <h1 class="text-2xl font-bold font-amiri text-maroon-900 mb-2">النص الأدبي الكامل ومستعرض الفصول</h1>
                <p class="text-sand-800 leading-relaxed">
                    يتيح لك هذا القسم قراءة النص المكتمل لـ <strong>«مأساة أحمد ومريم»</strong> مع أدوات التحكم في القراءة والتنقل السريع بين الفصول العشرة. تم ضبط النص بتشكيل دقيق ومحكم والتعديلات النحوية والحسية الموصى بها.
                </p>
            </div>

            <!-- Controls bar -->
            <div class="bg-white p-4 rounded-xl border border-sand-200 shadow-sm flex flex-wrap items-center justify-between gap-4">
                <div class="flex items-center space-x-3 space-x-reverse">
                    <label class="text-xs font-bold text-sand-800">اختر الفصل:</label>
                    <select id="chapterSelect" onchange="jumpToChapter(this.value)" class="bg-sand-50 border border-sand-200 text-sm rounded-md p-1.5 focus:outline-none focus:ring-1 focus:ring-maroon-600">
                        <option value="0">المطلع (توطئة سردية)</option>
                        <option value="1">الفصل الأول: غبار الطريق ونور المرفأ</option>
                        <option value="2">الفصل الثاني: الغربة الأولى وسحابة الجفاء</option>
                        <option value="3">الفصل الثالث: الخمسة عشر يوماً وحصار التحريض</option>
                        <option value="4">الفصل الرابع: شيطنة الذات وحماية الملاك</option>
                        <option value="5">الفصل الخامس: الرجاء المر والانحناء المزيف</option>
                        <option value="6">الفصل السادس: صدمة الاعتراف والحسم القاسي</option>
                        <option value="7">الفصل السابع: جحيم الزواج الأخوي واعتلال القلب</option>
                        <option value="8">الفصل الثامن: احتضار الصمت والتخبط الأخير</option>
                        <option value="9">الفصل التاسع: صدمة المغتسل وعقاب الذاكرة</option>
                        <option value="10">الفصل العاشر: القصاص الأبدي والحسرة الخالدة</option>
                    </select>
                </div>
                <div class="flex items-center space-x-2 space-x-reverse">
                    <span class="text-xs font-bold text-sand-800">حجم الخط:</span>
                    <button onclick="changeFontSize(-1)" class="px-2 py-1 bg-sand-200 rounded hover:bg-sand-800 hover:text-white transition text-xs font-bold">-</button>
                    <button onclick="changeFontSize(1)" class="px-2 py-1 bg-sand-200 rounded hover:bg-sand-800 hover:text-white transition text-xs font-bold">+</button>
                </div>
            </div>

            <!-- Reader Box -->
            <div class="bg-white p-6 sm:p-10 rounded-xl shadow-sm border border-sand-200 font-amiri text-lg leading-loose text-sand-900 space-y-8" id="storyContainer">
                <!-- Chapters will be rendered dynamically by JS -->
            </div>
        </section>

        <!-- SECTION 3: LITERARY ANALYSIS -->
        <section id="sec-analysis" class="hidden space-y-8">
            <!-- Intro Paragraph -->
            <div class="bg-white p-6 rounded-xl shadow-sm border border-sand-200">
                <h1 class="text-2xl font-bold font-amiri text-maroon-900 mb-2">دليل التحسين والنصائح الأدبية التطبيقية</h1>
                <p class="text-sand-800 leading-relaxed">
                    يعرض هذا القسم تقييماً شاملاً للمستوى الأدبي للنص، مع مقارنة تفاعلية حية بين الصياغات التقريرية السابقة والتعديلات الحوارية والحسية المقترحة لرفع القيمة الدرامية والتشويق الوجداني للنص.
                </p>
            </div>

            <!-- Critique Summary Cards -->
            <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                <div class="bg-white p-5 rounded-xl border border-sand-200 shadow-sm">
                    <div class="text-maroon-800 font-bold mb-2 flex items-center space-x-2 space-x-reverse">
                        <span>✦</span>
                        <span>1. الحوارات النفسية (ف 4)</span>
                    </div>
                    <p class="text-xs text-sand-800 leading-relaxed">
                        استبدال المونولوجات التقريرية البليغة بـ "التلعثم" والأنفاس المتقطعة لتعكس حالة الانهيار الفيزيائي والمفهوم الحقيقي لجلد الذات.
                    </p>
                </div>
                <div class="bg-white p-5 rounded-xl border border-sand-200 shadow-sm">
                    <div class="text-maroon-800 font-bold mb-2 flex items-center space-x-2 space-x-reverse">
                        <span>✦</span>
                        <span>2. الذعر الباطني (ف 8)</span>
                    </div>
                    <p class="text-xs text-sand-800 leading-relaxed">
                        جعل حوار "أم محسن" عند اكتشاف الموت ناطقاً بالهروب والذعر التلقائي دون إعلان مباشر صريح لخوفها من المعرة.
                    </p>
                </div>
                <div class="bg-white p-5 rounded-xl border border-sand-200 shadow-sm">
                    <div class="text-maroon-800 font-bold mb-2 flex items-center space-x-2 space-x-reverse">
                        <span>✦</span>
                        <span>3. المشهد الحسي (ف 9)</span>
                    </div>
                    <p class="text-xs text-sand-800 leading-relaxed">
                        ربط الذكريات في مشهد المغتسل بتفاصيل مادية جليلة (انسكاب الماء، برودة الكتفين، انكسار الضوء) بدلاً من سرد قائمة جافة.
                    </p>
                </div>
            </div>

            <!-- Interactive Applied Edits Table -->
            <div class="bg-white p-6 rounded-xl shadow-sm border border-sand-200">
                <h2 class="text-lg font-bold text-maroon-900 mb-4">نماذج المقارنة التطبيقية (قبل وبعد التحسين)</h2>
                <div class="space-y-6">
                    <!-- Example 1 -->
                    <div class="border border-sand-200 rounded-lg p-4 bg-sand-50 space-y-3">
                        <div class="text-xs font-bold text-maroon-800 bg-maroon-100 inline-block px-2 py-0.5 rounded">الفصل الرابع: حوار انكسار أحمد</div>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4 text-sm">
                            <div class="p-3 bg-white border border-red-200 rounded">
                                <span class="text-xs text-red-600 font-bold block mb-1">قبل (صياغة تقريرية زائدة):</span>
                                «لاَ تَتَحَدَّثِي عَنْ مَرْيَمَ بِسُوءٍ! مَرْيَمُ مَلاَكٌ نَقِيٌّ لاَ يُخْطِئُ.. أَنَا الظَّالِمُ، أَنَا الشَّيْطَانُ...»
                            </div>
                            <div class="p-3 bg-white border border-green-200 rounded">
                                <span class="text-xs text-green-700 font-bold block mb-1">بعد (صياغة حسية متقطعة):</span>
                                «دَعِيهَا يَا أُمِّي.. لاَ... لاَ تَقُولِي عَنْهَا هَكَذَا! مَرْيَمُ... مَرْيَمُ لَمْ تَظْلِمْنِي، أَنَا... أَنَا الَّذِي لَمْ أَعْرِفْ كَيْفَ أُصُونُهَا... الذَّنْبُ ذَنْبِي أَنَا!»
                            </div>
                        </div>
                    </div>

                    <!-- Example 2 -->
                    <div class="border border-sand-200 rounded-lg p-4 bg-sand-50 space-y-3">
                        <div class="text-xs font-bold text-maroon-800 bg-maroon-100 inline-block px-2 py-0.5 rounded">الفصل الثامن: مكالمة أم محسن الذعورة</div>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4 text-sm">
                            <div class="p-3 bg-white border border-red-200 rounded">
                                <span class="text-xs text-red-600 font-bold block mb-1">قبل (اعتراف مباشر بالجريمة):</span>
                                «لاَ تُوَرِّطِينَا يَا مَرْيَمُ! لاَ أَدْرِي، اتَّصِلِي بِأَهْلِهِ... لاَ تَجْعَلِي المَعَرَّةَ تَسْقُطُ عَلَيْنَا!»
                            </div>
                            <div class="p-3 bg-white border border-green-200 rounded">
                                <span class="text-xs text-green-700 font-bold block mb-1">بعد (ذعر وتملص باطني مبكر):</span>
                                «مَاذَا تَقُولِينَ؟! بَارِدٌ؟! اتَّصِلِي بِأَهْلِهِ فَوْراً يَا مَرْيَمُ! أَنَا لاَ علاَقَةَ لِي، اتَّصِلِي بِأَصْدِقَائِهِ... أَنْتِ مَنْ كُنْتِ مَعَهُ فِي البَيْتِ، أَقْلِقِي الدُّنْيَا عِنْدَهُمْ لاَ عِنْدِي!»
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Review Matrix Table -->
            <div class="bg-white p-6 rounded-xl shadow-sm border border-sand-200">
                <h2 class="text-lg font-bold text-maroon-900 mb-4">جدول مراجعة الضبط والنحو (عينات سريعة)</h2>
                <div class="overflow-x-auto">
                    <table class="w-full text-sm text-right text-sand-800">
                        <thead class="bg-sand-100 text-maroon-900 text-xs font-bold uppercase">
                            <tr>
                                <th class="p-3">الفصل</th>
                                <th class="p-3">التركيب السابق</th>
                                <th class="p-3">التعديل الموصى به</th>
                                <th class="p-3">السبب والتعليل الأدبي</th>
                            </tr>
                        </thead>
                        <tbody class="divide-y divide-sand-200">
                            <tr>
                                <td class="p-3 font-bold">الفصل الثالث</td>
                                <td class="p-3 text-red-600">«وَفِي المَقَابِلِ، وَفِي مُنْتَصَفِ...»</td>
                                <td class="p-3 text-green-700 font-bold">«وَفِي هَذِهِ الأَثْنَاءِ...»</td>
                                <td class="p-3 text-xs">لتفادي تكرار حروف الجر وتقوية الإيقاع السردي.</td>
                            </tr>
                            <tr>
                                <td class="p-3 font-bold">الفصل السابع</td>
                                <td class="p-3 text-red-600">«وَتَضَخُّمٍ حَادَّ»</td>
                                <td class="p-3 text-green-700 font-bold">«وَتَضَخُّمٍ حَادٍّ»</td>
                                <td class="p-3 text-xs">ضبط التنوين بالإضافة والكسر المقدر على الياء المحذوفة.</td>
                            </tr>
                            <tr>
                                <td class="p-3 font-bold">الفصل الثامن</td>
                                <td class="p-3 text-red-600">«مُسْتَلْقِياً بِالنَّفْسِ الوَضْعِيَّةِ»</td>
                                <td class="p-3 text-green-700 font-bold">«مُسْتَلْقِياً بِالوَضْعِيَّةِ نَفْسِهَا»</td>
                                <td class="p-3 text-xs">استخدام التوكيد المعنوي الفصيح بدلاً من الصياغة الركيكة.</td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>
        </section>

        <!-- SECTION 4: MEDICAL BREAKDOWN -->
        <section id="sec-medical" class="hidden space-y-8">
            <!-- Intro Paragraph -->
            <div class="bg-white p-6 rounded-xl shadow-sm border border-sand-200">
                <h1 class="text-2xl font-bold font-amiri text-maroon-900 mb-2">التحليل الطبي - متلازمة القلب المنكسر (Takotsubo)</h1>
                <p class="text-sand-800 leading-relaxed">
                    من أبرز نقاط القوة في النص الأدبي ربط المأساة النفسية بعارض طبي واقعي شديد التأثير وهو <strong>«متلازمة القلب المنكسر»</strong>. يوضح هذا القسم الآلية الفيزيولوجية الهرمونية التي قادت لتوقف البطين الأيسر والصدمة القلبية إثر القهر المكتوم.
                </p>
            </div>

            <!-- Medical Chart Grid -->
            <div class="grid grid-cols-1 lg:grid-cols-2 gap-8">
                <!-- Hormone Chart -->
                <div class="bg-white p-6 rounded-xl shadow-sm border border-sand-200">
                    <h2 class="text-lg font-bold text-maroon-900 mb-1">ارتفاع هرمونات الإجهاد (الأدرينالين)</h2>
                    <p class="text-xs text-sand-800 mb-4">تصاعد ضخ هرمونات التوتر من الصدمة العاطفية حتى توقف العضلة.</p>
                    <div class="chart-container">
                        <canvas id="chartMedicalHormones"></canvas>
                    </div>
                </div>

                <!-- Symptoms Matrix -->
                <div class="bg-white p-6 rounded-xl shadow-sm border border-sand-200 space-y-4">
                    <h2 class="text-lg font-bold text-maroon-900">الأعراض النفسجسمية الظاهرة على أحمد</h2>
                    <div class="space-y-3 text-sm">
                        <div class="p-3 rounded-lg bg-red-50 border border-red-100 flex items-start space-x-3 space-x-reverse">
                            <span class="text-red-700 font-bold text-base">1</span>
                            <div>
                                <div class="font-bold text-red-900">خفقان ورعشة متكررة في القلب</div>
                                <div class="text-xs text-red-700 mt-0.5">التجسد الفيزيائي لإفراز الأدرينالين السام بتركيز مرتفع.</div>
                            </div>
                        </div>
                        <div class="p-3 rounded-lg bg-amber-50 border border-amber-100 flex items-start space-x-3 space-x-reverse">
                            <span class="text-amber-800 font-bold text-base">2</span>
                            <div>
                                <div class="font-bold text-amber-900">تضخم قمة البطين الأيسر</div>
                                <div class="text-xs text-amber-800 mt-0.5">اتساع قمة البطين الأيسر ليشبه جرة الأخطبوط اليدوية اليابانية (Takotsubo).</div>
                            </div>
                        </div>
                        <div class="p-3 rounded-lg bg-sand-100 border border-sand-200 flex items-start space-x-3 space-x-reverse">
                            <span class="text-sand-800 font-bold text-base">3</span>
                            <div>
                                <div class="font-bold text-sand-900">خمول شديد وبرودة الأطراف</div>
                                <div class="text-xs text-sand-800 mt-0.5">هبوط نتاج القلب الدموي المباشر مما يسبب غياب الأوكسجين عن الأطراف.</div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

    </main>

    <!-- Footer -->
    <footer class="bg-sand-100 border-t border-sand-200 py-6 mt-12">
        <div class="max-w-7xl mx-auto px-4 text-center text-xs text-sand-800">
            تم التطوير للعرض الأدبي والتحليلي التفاعلي • جميع الحقوق محفوظة لقصة «مأساة أحمد ومريم»
        </div>
    </footer>

    <!-- Application Scripting -->
    <script>
        // Story Data Object
        const storyData = [
            {
                title: "المطلع (توطئة سردية)",
                content: `«وَمَا القَهْرُ الصَّامِتُ إِلا سُمٌّ يَسْرِي فِي أَوْرِدَةِ القَلْبِ بَطِيئاً، حَتَّى إِذَا بَلَغَ المُنْتَهَى، انْكَسَرَ العَضُدُ وَتَوَقَّفَ النَّبْضُ بِلَا ضَجِيجٍ.»`
            },
            {
                title: "الفصل الأول: غبار الطريق ونور المرفأ",
                content: `لَمْ يَكُنِ الحُبُّ بِالنِّسْبَةِ لِـ "أَحْمَدَ" مَجَرَّدَ عَاطِفَةٍ عَابِرَةٍ، بَلْ كَانَ عَقِيدَةً وَعَرَقاً يُسْكَبُ فِي ظُلُمَاتِ الأَيَّامِ. أَرْبَعَ سَنَوَاتٍ طِوَالاً وَهُوَ يُصَارِعُ التَّعَبَ، يَصِلُ اللَّيْلَ بِالنَّهَارِ، وَيَسْتَقْطِعُ مِنْ قُوتِهِ وَنَوْمِهِ لِيَصْنَعَ صَرْحاً يَجْمَعُهُ بِـ "مَرْيَمَ". كَانَتْ مَرْيَمُ هِيَ المَرْفَأَ الَّذِي يَنْشُدُ الوُصُولَ إِلَيْهِ وَسَطَ تَلَاطُمِ أَمْوَاجِ الحَيَاةِ الجَافِيَةِ.\nوَحِينَ اكْتَمَلَ البِنَاءُ، وَاجْتَمَعَتِ الأَيْدِي فِي بَيْتٍ وَاحِدٍ، بَدَتِ الحَيَاةُ وَكَأَنَّهَا تَعْتَذِرُ لأَحْمَدَ عَنْ كُلِّ مَرَارَتِهَا. عَاشَا أَيَّاماً مِنَ الشَّغَفِ الصَّافِي، حُبٌّ مُتَبَادَلٌ يَمْلأُ أَرْكَانَ البَيْتِ الدَّافِئِ، وَحَنَانٌ يَتَفَجَّرُ مِنْ قَلْبِ شَابٍّ كَانَ يَرَى فِي زَوْجَتِهِ كُلَّ أَهْلِهِ وَدُنْيَاهُ؛ كَانَتْ مَرْيَمُ بِالنِّسْبَةِ لَهُ الجَوْهَرَةَ الَّتِي صَانَهَا بِدَمِ قَلْبِهِ.`
            },
            {
                title: "الفصل الثاني: الغربة الأولى وسحابة الجفاء",
                content: `مَعَ مُرُورِ الأَيَّامِ وَالتَّرَاكُمَاتِ الصَّغِيرَةِ الَّتِي لا يَخْلُو مِنْهَا بَيْتٌ، بَدَأَتْ مَرْيَمُ تَشْعُرُ بِثِقَلِ المَسْؤُولِيَّةِ. لَمْ تَكُنْ هُنَاك مُشْكِلاَتٌ كَبِيرَةٌ، لَكِنَّ الصَّمْتَ بَدَأَ يَحُلُّ مَحَلَّ الكَلِمَاتِ الدَّافِئَةِ، وَأَخَذَتِ الرِّيبَةُ تَتَسَلَّلُ إِلَى قَلْبِهَا تُجَاعَ أَبْسَطِ تَصَرُّفَاتِ أَحْمَدَ؛ فَكَرَمُهُ بَاتَ يُقْرَأُ كَاسْتِعْرَاضٍ، وَحِلْمُهُ وَسُكُوتُهُ عِنْدَ الخِلاَفِ بَاتَا يُفَسَّرَانِ عَلَى أَنَّهُمَا تَجَاهُلٌ وَاسْتِخْفَافٌ.\nوَفِي لَحْظَةِ غَضَبٍ وَتَرَاكُمٍ مَكْتُومٍ، جَمَعَتْ مَرْيَمُ أَمْتِعَتَهَا وَغَادَرَتِ البَيْتَ مُتَّجِهَةً إِلَى بَيْتِ أَهْلِهَا، مُطَاوِعَةً رَغْبَةً دَاخِلِيَّةً بِالاِبْتِعَادِ وَمُطَالِبَةً بِالطَّلاَقِ، لِتَتْرُكَ أَحْمَدَ وَحِيداً فِي بَيْتٍ صَارَ يَضِيقُ بِجُدْرَانِهِ.`
            },
            {
                title: "الفصل الثالث: الخمسة عشر يوماً وحصار التحريض",
                content: `خِلاَلَ الخَمْسَةَ عَشَرَ يَوْماً الَّتِي قَضَتْهَا مَرْيَمُ فِي بَيْتِ أَهْلِهَا، ظَهَرَتْ أُمُّهَا "أُمُّ مُحْسِنٍ" فِي المَشْهَدِ بِشَكْلٍ حَادٍّ وَمُبَاشِرٍ؛ لَمْ تَكُنْ تَرْغَبُ فِي التَّهْدِئَةِ، بَلْ وَجَدَتْ فِي هَذَا الخُرُوجِ فُرْصَةً لِفَرْضِ السَّيْطَرَةِ، وَبَدَأَتْ تُعِيدُ تَأْوِيلَ كُلِّ مَوَاقِفِ أَحْمَدَ السَّابِقَةِ وَتَصُبُّ السُّمُومَ فِي أُذُنِ مَرْيَمَ:\n * «إِنْ أَهْدَاكِ شَيْئاً فَهُوَ يُحَاوِلُ شِرَاءَ سُكُوتِكِ عَنْ تَقْصِيرِهِ.»\n * «إِنْ تَأَخَّرَ فِي عَمَلِهِ فَهُوَ لا يُقِيمُ لَكِ وَزْناً وَيُحِبُّ كَدْحَهُ أَكْثَرَ مِنْكِ.»\n * «إِنْ صَمَتَ عِنْدَ غَضَبِكِ فَهُوَ يَسْتَخِفُّ بِعَقْلِكِ وَلا يَرَاكِ شَيْئاً.»\nوَفِي هَذِهِ الأَثْنَاءِ، لَمْ تَكُنْ "أُمُّ أَحْمَدَ" مَلاَكاً مُطْلَقاً أَوْ شَاهِدَةً زُوراً عَلَى انْكِسَارِ ابْنِهَا، بَلْ كَانَتْ امْرَأَةً مُمَزَّقَةً تَغْلِي أُمُومَتُهَا غَضَباً لِكَرَامَةِ ابْنِهَا المُهْدَرَةِ؛ حَاوَلَتْ أَنْ تُجَارِيَ صَنِيعَ "أُمِّ مُحْسِنٍ"، فَدَخَلَتْ عَلَيْهِ لِتَفْتَحَ بَابَ العَتَبِ، وَتَصُبَّ فِي صَدْرِهِ شَيْئاً مِنَ الحِقْدِ أَوْ الرَّغْبَةِ فِي الاِنْتِقَامِ لِذَاتِهِ المَجْرُوحَةِ.\nلَكِنَّ مُحَاوَلاَتِهَا اصْطَدَمَتْ بِحَائِطِ صَدٍّ مَنِيعٍ بَنَاهُ أَحْمَدُ حَوْلَ نَفْسِهِ؛ فَكُلَّمَا هَمَّتْ أُمُّهُ بِكَلِمَةِ تَحْرِيضٍ أَوْ لَوْمٍ لِمَرْيَمَ، كَانَ يُقَاطِعُهَا بِدُمُوعِهِ وَانْهِيَارِهِ، مُلْقِياً بِكُلِّ أَوْزَارِ الدُّنْيَا عَلَى كَتِفَيْهِ، وَمُصِرّاً عَلَى أَنَّ مَرْيَمَ نَقِيَّةٌ لاَ تُخْطِئُ وَمَا هُوَ إِلاَّ الجَانِي الأَوْحَدُ.`
            },
            {
                title: "الفصل الرابع: شيطنة الذات وحماية الملاك",
                content: `فِي المَقَابِلِ، كَانَ أَحْمَدُ يَعِيشُ جَحِيماً مِنْ نَوْعٍ آخَرَ. وَرَغْمَ فَدَاحَةِ جَفَاءِ مَرْيَمَ، رَفَضَ قَلْبُهُ الأَعْمَى بِالحُبِّ أَنْ يَتَّهِمَهَا أَوْ يُحَمِّلَهَا الذَّنْبَ، وَمَارَسَ أَقْصَى دَرَجَاتِ جَلْدِ الذَّاتِ.\nحِينَ كَانَ مَنْ حَوْلَهُ يُلاَحِظُونَ شُحُوبَ وَجْهِهِ وَانْكِسَارَ عَيْنَيْهِ، كَانَ أَحْمَدُ يَثُورُ بِغَضَبٍ حَارِقٍ لِحِمَايَتِهَا:\n> «دَعِيهَا يَا أُمِّي.. لاَ... لاَ تَقُولِي عَنْهَا هَكَذَا! مَرْيَمُ... مَرْيَمُ لَمْ تَظْلِمْنِي، أَنَا... أَنَا الَّذِي لَمْ أَعْرِفْ كَيْفَ أُصُونُهَا... الذَّنْبُ ذَنْبِي أَنَا!»\nوَحِينَ كَانَ يَجْلِسُ مَعَ صَدِيقِهِ الوَفِيِّ "أَبِي مَيَارَ"، كَانَ يَنْحَنِي بَاكِياً:\n> «يَا أَبَا مَيَارَ.. لَقَدْ ظَلَمْتُهَا.. أَنَا رَجُلٌ سَيِّئٌ لاَ أَسْتَحِقُّهَا.. مَرْيَمُ مَظْلُومَةٌ مَعِي».`
            },
            {
                title: "الفصل الخامس: الرجاء المر والانحناء المزيف",
                content: `فِي نِهَايَةِ الأَيَّامِ الخَمْسَةَ عَشَرَ، لَمْ يَذْهَبْ أَحْمَدُ إِلَى بَيْتِ أَهْلِ مَرْيَمَ لِيُدَافِعَ عَنْ نَفْسِهِ، بَلْ ذَهَبَ مُحْنِيَ الرَّأْسِ كَأَنَّهُ الجَانِي الَّذِي يَطْلُبُ العَفْوَ. التَمَسَ رِضَاهَا بِدُمُوعٍ مَكْتُومَةٍ، وَرَجَاهَا أَنْ تَعُودَ؛ لاَ كِبْرِيَاءً، بَلْ عِشْقاً وَتَشَبُّثاً بِآخِرِ أَمَلٍ.\nعَادَتْ مَرْيَمُ مُحَمَّلَةً بِكَلاَمِ أُمِّهَا وَسُّمُومِهَا، فَقَطْ كَيْ لاَ تُحْرَمَ طِفْلَتُهَا الصَّغِيرَةُ "رُقَيَّةُ" مِنْ بَيْتِهَا. عَادَتْ جَسَداً بِلاَ رُوحٍ.`
            },
            {
                title: "الفصل السادس: صدمة الاعتراف والحسم القاسي",
                content: `فِي لَيْلَةٍ بَارِدَةٍ، كَانَ أَحْمَدُ يُحَاوِلُ أَنْ يُرَمِّمَ الجِدَارَ المُتَهَدِّمَ؛ اقْتَرَبَ مِنْهَا بِكَلِمَةٍ طَيِّبَةٍ وَيَدٍ تَرْتَجِفُ.\nنَظَرَتْ إِلَيْهِ مَرْيَمُ بِبُرُودٍ قَاطِعٍ، وَقَالَتْ:\n> «أَنَا أَكْرَهُكَ يَا أَحْمَدُ.. لَقَدِ اتَّخَذْتُ قَرَاراً نِهَائِيّاً بِمَشَاعِرِي، وَلَنْ تَتَغَيَّرَ تُجَاهَكَ مَهْمَا فَعَلْتَ. وُجُودِي مَعَكَ لاَ يَعْنِي شَيْئاً سِوَى أَنَّنِي هُنَا لأَجْلِ رُقَيَّةَ فَقَطْ.»`
            },
            {
                title: "الفصل السابع: جحيم الزواج الأخوي واعتلال القلب",
                content: `بَدَأَتِ المَرْحَلَةُ الأَخِيرَةُ: "الزَّوَاجُ الأَخَوِيُّ القَسْرِيُّ". عَيْشٌ تَحْتَ سَقْفٍ وَاحِدٍ بِتَبَاعُدٍ كَامِلٍ.\nبَدَأَ جَسَدُ أَحْمَدَ يَنَهَارُ تَحْتَ وَطْأَةِ هَذَا القَهْرِ المَكْتُومِ. ظَهَرَتْ عَلَيْهِ أَعْرَاضٌ نَفْسِجِسْمِيَّةٌ حَادَّةٌ: خَفَقَانٌ وَرَعْشَةٌ مُتَكَرِّرَةٌ فِي القَلْبِ، وَتَضَخُّمٌ حَادٍّ فِي قِمَّةِ البُطَيْنِ، وَشُحُوبٌ كَأَنَّهُ مَيِّتٌ. كَانَتْ هَذِهِ العَلاَمَاتُ هِيَ التَّجَسُّدَ الفِزْيَائِيَّ لِـ "سَنَدْرُومِ القَلْبِ المَنْكَسِرِ" (Takotsubo cardiomyopathy).\nوَحِينَ كَانَ يَئِنُّ، كَانَ الجَمِيعُ يَتَعَامَلُونَ مَعَ أَلَمِهِ عَلَى أَنَّهُ "مَجَرَّدُ دِرَامَا أَوْ مَزْحَةٍ".`
            },
            {
                title: "الفصل الثامن: احتضار الصمت والتخبط الأخير",
                content: `فِي تِلْكَ اللَّيْلَةِ الأَخِيرَةِ، كَانَ الهَوَاءُ ثَقِيلاً. جَلَسَ أَحْمَدُ مُسْتَلْقِياً بِالوَضْعِيَّةِ نَفْسِهَا، وَيَدُهُ عَلَى صَدْرِهِ الَّذِي يَرْتَجِفُ. نَظَرَ نَحْوَ مَرْيَمَ نَظْرَةَ تَوْدِيعٍ، لَكِنَّهَا زَمْجَرَتْ بِضَجَرٍ:\n> «كَفَاكَ تَمْثِيلاً يَا أَحْمَدُ، أَزِلْ هَذِهِ المَسْرَحِيَّةَ وَنَمْ!»\nوَفِي هَزِيعِ اللَّيْلِ الأَخِيرِ، بَلَغَ اعْتِلاَلُ عَضَلَةِ القَلْبِ ذُرْوَتَهُ؛ تَوَقَّفَ البُطَيْنُ الأَيْسَرُ عَنِ النَّبْضِ تَمَاماً، وَفَاضَتْ رُوحُهُ.\nمَعَ طُلُوعِ الفَجْرِ، حَاوَلَتْ إِيقَاظَهُ فَوَجَدَتْهُ بَارِداً. اتَّصَلَتْ بِأُمِّهَا أُمِّ مُحْسِنٍ، فَقَالَتْ لَهَا الأُمُّ بِذُعْرٍ:\n> «مَاذَا تَقُولِينَ؟! بَارِدٌ؟! اتَّصِلِي بِأَهْلِهِ فَوْراً يَا مَرْيَمُ! أَنَا لاَ علاَقَةَ لِي، اتَّصِلِي بِأَصْدِقَائِهِ... أَنْتِ مَنْ كُنْتِ مَعَهُ فِي البَيْتِ!»`
            },
            {
                title: "الفصل التاسع: صدمة المغتسل وعقاب الذاكرة",
                content: `حِينَ انْسَكَبَ المَاءُ البَارِدُ عَلَى صَدْرِهِ السَّاكِنِ، وَرَأَتْ مَرْيَمُ انْكِشَافَ كَتِفَيْهِ اللَّتَيْنِ حَمَلَتَا هَمَّ السِّنِينِ لأَجْلِهَا، وَمَسَّتْ أصَابِعَهُ البَارِدَةَ وَانْكِسَارَ الضَّوْءِ عَلَى جَسَدِهِ.. تَذَكَّرَتْ كَيْفَ كَانَتْ تِلْكَ الأَصَابِعُ تَرْتَجِفُ وَهُوَ يَمْدُّ يَدَهُ لِيَبْدَأَ صَفْحَةً جَدِيدَةً.\nتَدَاعَتْ سُدُودُ القَسْوَةِ، وَحَلَّ مَحَلَّهَا نَدَمٌ كَالسَّكَاكِينِ يُمَزِّقُ أَحْشَاءَهَا. انْهَارَتْ تَبْكِي بِدُمُوعٍ حَارِقَةٍ، لَكِنَّهُ كَانَ قَدْ أَبْحَرَ بَعِيداً.`
            },
            {
                title: "الفصل العاشر: القصاص الأبدي والحسرة الخالدة",
                content: `لَمْ تَعُدْ مَرْيَمُ تَنَامُ. كَانَ أَحْمَدُ يَأْتِيهَا فِي الأَحْلاَمِ بِمَلاَمِحِهِ التَّعِبَةِ وَعَيْنَيْهِ البَاكِيَتَيْنِ اللَّتَيْنِ غَطَّاهُمَا التُّرَابُ، وَيُعَاتِبُهَا بِصَمْتٍ قَاتِلٍ.\nوَالأَشَدُّ إِيلاَماً كَانَ رُؤْيَةَ طِفْلَتِهَا "رُقَيَّةَ" الَّتِي كَبِرَتْ لِتُعَامِلَ أُمَّهَا بِبُرُودٍ وَجَفَاءٍ شَبِيهَيْنِ تَمَاماً بِذَاكَ الَّذِي عَامَلَتْ بِهِ مَرْيَمُ أَحْمَدَ. عَاشَتْ مَرْيَمُ مَا تَبَقَّى مِنْ عُمْرِهَا تَتَحَسَّرُ عَلَى قَلْبٍ نَقِيٍّ لَمْ تَعْرِفْ قِيمَتَهُ إِلاَّ بَعْدَ أَنْ تَحَوَّلَ إِلَى رَمَادٍ.`
            }
        ];

        // Global font size tracking
        let currentFontSize = 18;

        // Switch Tabs Function
        function switchTab(tabId) {
            const tabs = ['dashboard', 'reader', 'analysis', 'medical'];
            tabs.forEach(t => {
                document.getElementById(`sec-${t}`).classList.add('hidden');
                const btn = document.getElementById(`tab-btn-${t}`);
                if(btn) {
                    btn.classList.remove('bg-sand-200', 'font-bold', 'text-maroon-800');
                    btn.classList.add('text-sand-800');
                }
            });

            document.getElementById(`sec-${tabId}`).classList.remove('hidden');
            const activeBtn = document.getElementById(`tab-btn-${tabId}`);
            if(activeBtn) {
                activeBtn.classList.add('bg-sand-200', 'font-bold', 'text-maroon-800');
            }
        }

        // Render Reader Story
        function renderStory() {
            const container = document.getElementById('storyContainer');
            container.innerHTML = '';
            storyData.forEach((chap, idx) => {
                const chapDiv = document.createElement('div');
                chapDiv.id = `chapter-block-${idx}`;
                chapDiv.className = "pb-8 border-b border-sand-200 last:border-b-0 space-y-3";
                
                const title = document.createElement('h2');
                title.className = "text-xl font-bold text-maroon-800 font-amiri mb-2";
                title.innerText = chap.title;

                const text = document.createElement('div');
                text.className = "whitespace-pre-line leading-relaxed text-sand-900";
                text.style.fontSize = `${currentFontSize}px`;
                text.innerText = chap.content;

                chapDiv.appendChild(title);
                chapDiv.appendChild(text);
                container.appendChild(chapDiv);
            });
        }

        // Jump to chapter
        function jumpToChapter(index) {
            switchTab('reader');
            setTimeout(() => {
                const el = document.getElementById(`chapter-block-${index}`);
                if(el) {
                    el.scrollIntoView({ behavior: 'smooth' });
                }
            }, 100);
        }

        // Change font size
        function changeFontSize(delta) {
            currentFontSize = Math.max(14, Math.min(26, currentFontSize + delta));
            renderStory();
        }

        // Initialize Charts via Chart.js
        function initCharts() {
            // Chart 1: Emotional Trajectory
            const ctx1 = document.getElementById('chartEmotionalJourney').getContext('2d');
            new Chart(ctx1, {
                type: 'line',
                data: {
                    labels: ['ف1', 'ف2', 'ف3', 'ف4', 'ف5', 'ف6', 'ف7', 'ف8', 'ف9', 'ف10'],
                    datasets: [
                        {
                            label: 'استقرار أحمد النفسي',
                            data: [90, 60, 40, 20, 35, 15, 10, 0, 0, 0],
                            borderColor: '#631717',
                            backgroundColor: 'rgba(99, 23, 23, 0.1)',
                            fill: true,
                            tension: 0.3
                        },
                        {
                            label: 'استقرار مريم النفسي',
                            data: [85, 50, 30, 25, 30, 40, 35, 20, 5, 2],
                            borderColor: '#C05621',
                            backgroundColor: 'rgba(192, 86, 33, 0.1)',
                            fill: true,
                            tension: 0.3
                        }
                    ]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    plugins: {
                        legend: { position: 'top', labels: { font: { family: 'Tajawal' } } }
                    },
                    scales: {
                        y: { min: 0, max: 100, title: { display: true, text: 'مستوى الاستقرار (%)' } }
                    }
                }
            });

            // Chart 2: Drivers
            const ctx2 = document.getElementById('chartDrivers').getContext('2d');
            new Chart(ctx2, {
                type: 'doughnut',
                data: {
                    labels: ['جلد الذات والصمت (أحمد)', 'تحريض أم محسن', 'جفاء مريم والقرار القاسي', 'تدخلات سلبية أخرى'],
                    datasets: [{
                        data: [40, 30, 20, 10],
                        backgroundColor: ['#631717', '#C05621', '#E8DEC9', '#4A3E31']
                    }]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    plugins: {
                        legend: { position: 'bottom', labels: { font: { family: 'Tajawal', size: 11 } } }
                    }
                }
            });

            // Chart 3: Medical Hormones
            const ctx3 = document.getElementById('chartMedicalHormones').getContext('2d');
            new Chart(ctx3, {
                type: 'bar',
                data: {
                    labels: ['الحياة الطبيعية', 'الخلاف الأول', 'حصار التحريض', 'صدمة الكره (ف6)', 'الاحتضار (ف8)'],
                    datasets: [{
                        label: 'تركيز الكاتيكولامينات/الأدرينالين (pg/mL)',
                        data: [150, 350, 600, 1200, 2800],
                        backgroundColor: '#9B2C2C'
                    }]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    plugins: {
                        legend: { position: 'top', labels: { font: { family: 'Tajawal' } } }
                    }
                }
            });
        }

        // On DOM Load
        document.addEventListener('DOMContentLoaded', () => {
            renderStory();
            initCharts();
        });
    </script>
</body>
</html>
```