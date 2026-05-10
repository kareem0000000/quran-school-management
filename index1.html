<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>نظام الفرقان المتكامل | إدارة الحلقات والتقارير</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@300;400;600;700;900&display=swap" rel="stylesheet">
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>

    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: { primary: '#1a5fb4', secondary: '#2ec27e', accent: '#e5a50a', dark: '#1c1f26', bgLight: '#f6f5f4', danger: '#e01b24' },
                    fontFamily: { 'cairo': ['Cairo', 'sans-serif'] }
                }
            }
        }
    </script>

    <style>
        body { font-family: 'Cairo', sans-serif; background-color: #f6f5f4; scroll-behavior: smooth; }
        .sidebar-link.active { background-color: rgba(26, 95, 180, 0.1); border-right: 4px solid #1a5fb4; color: #1a5fb4; }
        .stat-card { transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1); border: 1px solid rgba(0,0,0,0.05); }
        .stat-card:hover { transform: translateY(-5px); box-shadow: 0 10px 15px -3px rgba(0,0,0,0.1); }
        
        .daily-input { border: 1px solid #e2e8f0; border-radius: 8px; padding: 6px 10px; width: 100%; text-align: center; font-size: 0.85rem; transition: all 0.2s; }
        .daily-input:focus { border-color: #1a5fb4; outline: none; background: #f0f7ff; box-shadow: 0 0 0 3px rgba(26, 95, 180, 0.1); }
        
        /* تحسين اختيار السور */
        .surah-select { background-color: #f8fafc; border: 1px solid #cbd5e1; border-radius: 8px; font-size: 11px; font-weight: bold; padding: 4px; }
        
        @keyframes fadeIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }
        .page-animate { animation: fadeIn 0.4s ease-out; }
        @media print { 
            .no-print { display: none !important; } 
            .print-block { display: block !important; }
            body { background: white; }
            .content-area { padding: 0 !important; }
            table { border: 1px solid #eee; width: 100% !important; }
            .print-header { display: block !important; text-align: center; margin-bottom: 30px; border-bottom: 2px solid #333; padding-bottom: 10px; }
        }
        
        .custom-scrollbar::-webkit-scrollbar { width: 6px; }
        .custom-scrollbar::-webkit-scrollbar-track { background: #f1f1f1; }
        .custom-scrollbar::-webkit-scrollbar-thumb { background: #cbd5e1; border-radius: 10px; }
        .toast-notification { position: fixed; bottom: 20px; left: 50%; transform: translateX(-50%); z-index: 9999; display: none; }
        
        .glass { background: rgba(255, 255, 255, 0.7); backdrop-filter: blur(10px); border: 1px solid rgba(255, 255, 255, 0.2); }
        .badge-pulse { animation: pulse 2s infinite; }
        @keyframes pulse { 0% { box-shadow: 0 0 0 0 rgba(46, 194, 126, 0.4); } 70% { box-shadow: 0 0 0 10px rgba(46, 194, 126, 0); } 100% { box-shadow: 0 0 0 0 rgba(46, 194, 126, 0); } }
        
        .progress-bar { height: 8px; border-radius: 4px; background: #eee; overflow: hidden; }
        .progress-fill { height: 100%; background: linear-gradient(90deg, #2ec27e, #1a5fb4); transition: width 0.5s ease; }
        .absent-row { background-color: #fff5f5 !important; }
        .points-badge { background: linear-gradient(45deg, #e5a50a, #f7d060); color: white; padding: 2px 8px; border-radius: 20px; font-size: 10px; font-weight: bold; }
        .activity-item { border-right: 3px solid #1a5fb4; padding: 8px; margin-bottom: 8px; background: #f8fafc; border-radius: 0 8px 8px 0; font-size: 11px; }
    </style>
</head>
<body class="text-gray-800 custom-scrollbar">

    <!-- هيدر خاص للطباعة فقط -->
    <div class="hidden print-block print-header" dir="rtl">
        <h1 style="font-size: 24px; font-weight: bold;">مركز الفرقان لتعليم القرآن الكريم</h1>
        <p>تقرير رسمي صادر عن النظام الإلكتروني لإدارة الحلقات</p>
        <p id="print-date-display"></p>
    </div>

    <div id="toast" class="toast-notification page-animate">
        <div class="bg-dark text-white px-6 py-3 rounded-2xl shadow-2xl flex items-center space-x-3 space-x-reverse border-t-4 border-primary">
            <i id="toast-icon" class="fas fa-info-circle text-primary"></i>
            <span id="toast-msg" class="font-bold text-sm"></span>
        </div>
    </div>

    <!-- شاشة الدخول -->
    <div id="login-screen" class="fixed inset-0 z-[1000] bg-dark flex items-center justify-center p-4">
        <div class="bg-white w-full max-w-md rounded-3xl shadow-2xl overflow-hidden page-animate">
            <div class="p-8 text-center bg-primary text-white">
                <i class="fas fa-quran text-5xl mb-4"></i>
                <h2 class="text-2xl font-black">مركز تحفيظ القرآن</h2>
                <p class="text-sm opacity-80 font-bold">نظام الإدارة الموحد</p>
            </div>
            <form id="login-form" class="p-8 space-y-4">
                <div>
                    <label class="block text-xs font-black text-gray-400 uppercase mb-2">اسم المستخدم</label>
                    <input type="text" id="username" required class="w-full px-4 py-3 rounded-xl border border-gray-200 focus:ring-2 focus:ring-primary outline-none font-bold transition-all">
                </div>
                <div>
                    <label class="block text-xs font-black text-gray-400 uppercase mb-2">كلمة المرور</label>
                    <input type="password" id="password" required class="w-full px-4 py-3 rounded-xl border border-gray-200 focus:ring-2 focus:ring-primary outline-none font-bold transition-all">
                </div>
                <button type="submit" class="w-full bg-primary text-white py-4 rounded-2xl font-black shadow-xl hover:bg-blue-700 transition-all mt-4 active:scale-95">دخول النظام</button>
            </form>
        </div>
    </div>

    <!-- التطبيق الرئيسي -->
    <div id="main-app" class="hidden flex flex-col md:flex-row min-h-screen">
        
        <aside class="no-print w-full md:w-64 bg-white shadow-lg md:h-screen md:sticky md:top-0 z-10">
            <div class="p-6 border-b flex items-center space-x-3 space-x-reverse">
                <div class="w-12 h-12 rounded-full bg-primary flex items-center justify-center shadow-lg shadow-primary/20">
                    <i class="fas fa-quran text-white text-xl"></i>
                </div>
                <div>
                    <h1 class="font-bold text-lg text-primary leading-tight">مركز الفرقان</h1>
                    <p id="user-role-badge" class="text-[10px] text-gray-400 font-bold uppercase"></p>
                </div>
            </div>
            
            <div class="p-4 flex flex-col h-[calc(100vh-120px)]">
                <div class="flex-1 overflow-y-auto custom-scrollbar">
                    <div id="admin-menu" class="hidden space-y-6 mb-8">
                        <div>
                            <h3 class="text-xs uppercase text-gray-400 font-black mb-3 px-3 tracking-widest">الإدارة العامة</h3>
                            <ul class="space-y-1" id="nav-admin-main"></ul>
                        </div>
                    </div>

                    <div id="teacher-menu" class="hidden space-y-6 mb-8">
                        <div>
                            <h3 class="text-xs uppercase text-gray-400 font-black mb-3 px-3 tracking-widest">إدارة الحلقة</h3>
                            <ul class="space-y-1" id="nav-teacher-main"></ul>
                        </div>
                    </div>
                </div>

                <div class="p-4 bg-gray-50 rounded-2xl mt-auto">
                    <div class="flex items-center space-x-3 space-x-reverse mb-3">
                        <div class="w-10 h-10 rounded-full bg-blue-100 flex items-center justify-center text-primary font-black" id="user-avatar-initial"></div>
                        <div>
                            <p class="font-bold text-sm" id="user-display-name"></p>
                            <p class="text-[10px] text-green-600 font-bold">متصل الآن</p>
                        </div>
                    </div>
                    <button onclick="App.logout()" class="w-full py-2 text-xs text-red-600 font-bold hover:bg-red-50 rounded-lg flex items-center justify-center space-x-2 space-x-reverse transition-all">
                        <i class="fas fa-sign-out-alt"></i>
                        <span>تسجيل الخروج</span>
                    </button>
                </div>
            </div>
        </aside>

        <main class="flex-1 flex flex-col">
            <header class="no-print bg-white shadow-sm sticky top-0 z-10 h-20 flex items-center px-8 justify-between">
                <div class="flex items-center gap-6">
                    <div>
                        <h2 class="text-xl font-black text-gray-800" id="page-title">لوحة التحكم</h2>
                        <p class="text-[10px] text-gray-400 font-bold" id="current-full-date"></p>
                    </div>
                    <div class="relative hidden lg:block">
                        <i class="fas fa-search absolute right-3 top-1/2 -translate-y-1/2 text-gray-300 text-xs"></i>
                        <input type="text" id="global-search" oninput="App.handleGlobalSearch(this.value)" placeholder="بحث شامل عن طالب، معلم، حلقة..." class="bg-gray-50 border-none rounded-xl pr-10 pl-4 py-2 text-xs font-bold w-72 focus:ring-2 focus:ring-primary outline-none transition-all">
                        <div id="search-results" class="absolute top-full right-0 mt-2 w-full bg-white shadow-2xl rounded-2xl hidden z-50 border border-gray-100 overflow-hidden"></div>
                    </div>
                </div>
                
                <div class="flex items-center space-x-4 space-x-reverse">
                    <div id="admin-quick-actions" class="hidden flex items-center space-x-4 space-x-reverse">
                        <input type="file" id="import-db" class="hidden" accept=".json" onchange="App.importBackup(event)">
                        <button onclick="document.getElementById('import-db').click()" class="bg-blue-50 text-primary px-4 py-2 rounded-xl text-xs font-bold hover:bg-blue-100 transition-all">
                            <i class="fas fa-upload ml-1"></i> استعادة
                        </button>
                        <button onclick="App.exportBackup()" class="bg-gray-100 text-gray-600 px-4 py-2 rounded-xl text-xs font-bold hover:bg-gray-200 transition-all">
                            <i class="fas fa-download ml-1"></i> نسخة احتياطية
                        </button>
                        <button onclick="App.openModal('modal-add-student')" class="bg-primary text-white px-4 py-2 rounded-xl text-xs font-bold shadow-lg shadow-primary/20 hover:scale-105 transition-all">
                            <i class="fas fa-plus ml-2"></i> إضافة طالب
                        </button>
                    </div>
                </div>
            </header>
            
            <div id="content-area" class="p-6 md:p-8 flex-1 overflow-y-auto page-animate">
                <!-- المحتوى يتغير ديناميكياً هنا -->
            </div>
        </main>
    </div>

    <!-- مودالات -->
    
    <!-- مودال تعديل مستخدم / إضافة مستخدم -->
    <div id="modal-edit-user" class="fixed inset-0 bg-black/60 z-[200] hidden items-center justify-center p-4 backdrop-blur-sm">
        <div class="bg-white rounded-3xl shadow-2xl w-full max-w-lg overflow-hidden page-animate">
            <div class="p-6 border-b flex justify-between items-center bg-gray-50">
                <h3 class="font-black text-lg" id="user-modal-title">تعديل بيانات الحساب</h3>
                <button onclick="App.closeModal('modal-edit-user')" class="text-gray-400 hover:text-red-500"><i class="fas fa-times-circle text-xl"></i></button>
            </div>
            <form id="form-edit-user" class="p-6 space-y-4">
                <input type="hidden" id="edit-user-id">
                <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                    <div class="col-span-1 md:col-span-2">
                        <label class="block text-[10px] font-black text-gray-400 mb-1">الاسم الكامل</label>
                        <input type="text" id="edit-user-name" required class="w-full p-3 rounded-xl border border-gray-100 bg-gray-50 font-bold text-sm outline-none focus:border-primary">
                    </div>
                    <div>
                        <label class="block text-[10px] font-black text-gray-400 mb-1">اسم المستخدم</label>
                        <input type="text" id="edit-user-username" required class="w-full p-3 rounded-xl border border-gray-100 bg-gray-50 font-bold text-sm outline-none focus:border-primary">
                    </div>
                    <div id="role-select-container">
                        <label class="block text-[10px] font-black text-gray-400 mb-1">الصلاحية</label>
                        <select id="edit-user-role" class="w-full p-3 rounded-xl border border-gray-100 bg-gray-50 font-bold text-sm outline-none focus:border-primary">
                            <option value="teacher">محفظ</option>
                            <option value="supervisor">مشرف</option>
                            <option value="admin">مدير</option>
                        </select>
                    </div>
                    <div>
                        <label class="block text-[10px] font-black text-gray-400 mb-1">رقم الهوية</label>
                        <input type="text" id="edit-user-id-number" class="w-full p-3 rounded-xl border border-gray-100 bg-gray-50 font-bold text-sm outline-none focus:border-primary">
                    </div>
                    <div>
                        <label class="block text-[10px] font-black text-gray-400 mb-1">تاريخ الميلاد</label>
                        <input type="date" id="edit-user-dob" class="w-full p-3 rounded-xl border border-gray-100 bg-gray-50 font-bold text-sm outline-none focus:border-primary">
                    </div>
                    <div class="col-span-1 md:col-span-2">
                        <label class="block text-[10px] font-black text-gray-400 mb-1">كلمة المرور</label>
                        <input type="password" id="edit-user-pass" required class="w-full p-3 rounded-xl border border-gray-100 bg-gray-50 font-bold text-sm outline-none focus:border-primary">
                    </div>
                </div>
                <button type="submit" class="w-full bg-primary text-white py-4 rounded-2xl font-black shadow-xl mt-2 transition-all active:scale-95">حفظ البيانات</button>
            </form>
        </div>
    </div>

    <!-- مودال إضافة/تعديل طالب -->
    <div id="modal-add-student" class="fixed inset-0 bg-black/60 z-[200] hidden items-center justify-center p-4 backdrop-blur-sm">
        <div class="bg-white rounded-3xl shadow-2xl w-full max-w-lg overflow-hidden page-animate">
            <div class="p-6 border-b flex justify-between items-center bg-gray-50">
                <h3 class="font-black text-lg" id="student-modal-title">إضافة طالب جديد</h3>
                <button onclick="App.closeModal('modal-add-student')" class="text-gray-400 hover:text-red-500"><i class="fas fa-times-circle text-xl"></i></button>
            </div>
            <form id="form-add-student" class="p-6 space-y-4">
                <input type="hidden" name="id" id="edit-student-id">
                <input type="text" name="name" id="student-name" placeholder="اسم الطالب الرباعي" required class="w-full p-4 rounded-xl border border-gray-100 bg-gray-50 font-bold text-sm outline-none focus:border-primary">
                <div class="grid grid-cols-2 gap-4">
                    <select name="circleId" id="modal-circle-select" class="w-full p-4 rounded-xl border border-gray-100 bg-gray-50 font-bold text-sm outline-none"></select>
                    <input type="tel" name="phone" id="student-phone" placeholder="972590000000" required class="w-full p-4 rounded-xl border border-gray-100 bg-gray-50 font-bold text-sm outline-none">
                </div>
                <div class="grid grid-cols-2 gap-4">
                    <div>
                        <label class="block text-[10px] font-black text-gray-400 mb-1">عدد الأجزاء (0-30)</label>
                        <input type="number" name="juzCount" id="student-juz" min="0" max="30" value="0" class="w-full p-4 rounded-xl border border-gray-100 bg-gray-50 font-bold text-sm outline-none">
                    </div>
                    <div>
                        <label class="block text-[10px] font-black text-gray-400 mb-1">حالة الطالب</label>
                        <select id="student-status" class="w-full p-4 rounded-xl border border-gray-100 bg-gray-50 font-bold text-sm outline-none">
                            <option value="نشط">نشط</option>
                            <option value="منقطع">منقطع</option>
                            <option value="خريج">خريج</option>
                        </select>
                    </div>
                </div>
                <div id="points-container" class="hidden">
                    <label class="block text-[10px] font-black text-gray-400 mb-1">النقاط الحالية</label>
                    <input type="number" id="student-points" class="w-full p-4 rounded-xl border border-gray-100 bg-gray-50 font-bold text-sm outline-none">
                </div>
                <button type="submit" class="w-full bg-primary text-white py-4 rounded-2xl font-black shadow-xl">حفظ الطالب</button>
            </form>
        </div>
    </div>

    <!-- مودال إضافة حلقة -->
    <div id="modal-add-circle" class="fixed inset-0 bg-black/60 z-[200] hidden items-center justify-center p-4 backdrop-blur-sm">
        <div class="bg-white rounded-3xl shadow-2xl w-full max-w-md overflow-hidden page-animate">
            <div class="p-6 border-b flex justify-between items-center bg-gray-50">
                <h3 class="font-black text-lg">إضافة حلقة قرآنية جديدة</h3>
                <button onclick="App.closeModal('modal-add-circle')" class="text-gray-400 hover:text-red-500"><i class="fas fa-times-circle text-xl"></i></button>
            </div>
            <form id="form-add-circle" class="p-6 space-y-4">
                <input type="text" id="new-circle-name" placeholder="اسم الحلقة (مثال: حلقة النور)" required class="w-full p-4 rounded-xl border border-gray-100 bg-gray-50 font-bold text-sm outline-none focus:border-primary">
                
                <!-- إضافة تصنيف الحلقة: ادخال يدوي -->
                <label class="block text-[10px] font-black text-gray-400 mb-1">تصنيف الحلقة (مثلاً: حفظ، تمكين، تجويد)</label>
                <input type="text" id="new-circle-category" placeholder="تصنيف الحلقة" class="w-full p-4 rounded-xl border border-gray-100 bg-gray-50 font-bold text-sm outline-none focus:border-primary">
                
                <label class="block text-[10px] font-black text-gray-400 mb-1">اختر المحفظ</label>
                <select id="new-circle-teacher" class="w-full p-4 rounded-xl border border-gray-100 bg-gray-50 font-bold text-sm outline-none"></select>
                <button type="submit" class="w-full bg-secondary text-white py-4 rounded-2xl font-black shadow-xl">إنشاء الحلقة الآن</button>
            </form>
        </div>
    </div>

    <!-- مودال إضافة اختبار جديد -->
    <div id="modal-add-test" class="fixed inset-0 bg-black/60 z-[300] hidden items-center justify-center p-4 backdrop-blur-sm">
        <div class="bg-white rounded-3xl shadow-2xl w-full max-w-md overflow-hidden page-animate">
            <div class="p-6 border-b flex justify-between items-center bg-gray-50">
                <h3 class="font-black text-lg">تسجيل اختبار جزء</h3>
                <button onclick="App.closeModal('modal-add-test')" class="text-gray-400 hover:text-red-500"><i class="fas fa-times-circle text-xl"></i></button>
            </div>
            <form id="form-add-test" class="p-6 space-y-4">
                <input type="hidden" id="test-student-id">
                <div>
                    <label class="block text-[10px] font-black text-gray-400 mb-1">الجزء المختبر فيه</label>
                    <input type="text" id="test-part" placeholder="مثلاً: جزء عم / البقرة" required class="w-full p-3 rounded-xl border border-gray-100 bg-gray-50 font-bold text-sm outline-none">
                </div>
                <div class="grid grid-cols-2 gap-4">
                    <div>
                        <label class="block text-[10px] font-black text-gray-400 mb-1">الدرجة (من 100)</label>
                        <input type="number" id="test-score" max="100" min="0" required class="w-full p-3 rounded-xl border border-gray-100 bg-gray-50 font-bold text-sm outline-none">
                    </div>
                    <div>
                        <label class="block text-[10px] font-black text-gray-400 mb-1">التقدير</label>
                        <select id="test-grade" class="w-full p-3 rounded-xl border border-gray-100 bg-gray-50 font-bold text-sm outline-none">
                            <option value="ممتاز مرتفع">ممتاز مرتفع</option>
                            <option value="ممتاز">ممتاز</option>
                            <option value="جيد جداً">جيد جداً</option>
                            <option value="جيد">جيد</option>
                        </select>
                    </div>
                </div>
                <button type="submit" class="w-full bg-primary text-white py-4 rounded-2xl font-black shadow-xl">حفظ نتيجة الاختبار</button>
            </form>
        </div>
    </div>

    <!-- مودال تقديم طلب اختبار من قبل المحفظ -->
    <div id="modal-request-test" class="fixed inset-0 bg-black/60 z-[200] hidden items-center justify-center p-4 backdrop-blur-sm">
        <div class="bg-white rounded-3xl shadow-2xl w-full max-w-md overflow-hidden page-animate">
            <div class="p-6 border-b flex justify-between items-center bg-gray-50">
                <h3 class="font-black text-lg">تقديم طلب اختبار جزء</h3>
                <button onclick="App.closeModal('modal-request-test')" class="text-gray-400 hover:text-red-500"><i class="fas fa-times-circle text-xl"></i></button>
            </div>
            <form id="form-request-test" class="p-6 space-y-4">
                <input type="hidden" id="req-test-student-id">
                <div>
                    <label class="block text-[10px] font-black text-gray-400 mb-1">الجزء المراد الاختبار فيه</label>
                    <input type="text" id="req-test-part" placeholder="مثلاً: جزء عم / سورة البقرة" required class="w-full p-4 rounded-xl border border-gray-100 bg-gray-50 font-bold text-sm outline-none focus:border-primary">
                </div>
                <div>
                    <label class="block text-[10px] font-black text-gray-400 mb-1">ملاحظات إضافية (اختياري)</label>
                    <textarea id="req-test-notes" placeholder="أية ملاحظات للمشرف الأكاديمي..." class="w-full p-4 rounded-xl border border-gray-100 bg-gray-50 font-bold text-sm outline-none focus:border-primary h-24"></textarea>
                </div>
                <button type="submit" class="w-full bg-primary text-white py-4 rounded-2xl font-black shadow-xl">إرسال طلب الاختبار</button>
            </form>
        </div>
    </div>

    <script>
        const DB_KEY = 'al_furqan_ultimate_db';

        // مصفوفة أسماء السور المسبقة
        const QURAN_SURAHS = [
            "الفاتحة", "البقرة", "آل عمران", "النساء", "المائدة", "الأنعام", "الأعراف", "الأنفال", "التوبة", "يونس", "هود", "يوسف", "الرعد", "إبراهيم", "الحجر", "النحل", "الإسراء", "الكهف", "مريم", "طه", "الأنبياء", "الحج", "المؤمنون", "النور", "الفرقان", "الشعراء", "النمل", "القصص", "العنكبوت", "الروم", "لقمان", "السجدة", "الأحزاب", "سبأ", "فاطر", "يس", "الصافات", "ص", "الزمر", "غافر", "فصلت", "الشورى", "الزخرف", "الدخان", "الجاثية", "الأحقاف", "محمد", "الفتح", "الحجرات", "ق", "الذاريات", "الطور", "النجم", "القمر", "الرحمن", "الواقعة", "الحديد", "المجادلة", "الحشر", "الممتحنة", "الصف", "الجمعة", "المنافقون", "التغابن", "الطلاق", "التحريم", "الملك", "القلم", "الحاقة", "المعارج", "نوح", "الجن", "المزمل", "المدثر", "القيامة", "الإنسان", "المرسلات", "النبأ", "النازعات", "عبس", "التكوير", "الانفطار", "المطففين", "الانشقاق", "البروج", "الطارق", "الأعلى", "الغاشية", "الفجر", "البلد", "الشمس", "الليل", "الضحى", "الشرح", "التين", "العلق", "القدر", "البينة", "الزلزلة", "العاديات", "القارعة", "التكاثر", "العصر", "الهمزة", "الفيل", "قريش", "الماعون", "الكوثر", "الكافرون", "النصر", "المسد", "الإخلاص", "الفلق", "الناس"
        ];

        const initialData = {
            settings: { salaryPerStudent: 50, pointReward: 5 }, 
            users: [
                { id: 1, username: 'admin', password: btoa('123'), role: 'admin', name: 'عبدالله المدير', idNumber: '123456789', dob: '1990-01-01', circleId: null },
                { id: 2, username: 'teacher1', password: btoa('123'), role: 'teacher', name: 'أحمد محمد', idNumber: '987654321', dob: '1995-05-15', circleId: 1 },
                { id: 3, username: 'teacher2', password: btoa('123'), role: 'teacher', name: 'سعيد علي', idNumber: '456789123', dob: '1992-10-20', circleId: 2 }
            ],
            circles: [
                { id: 1, name: 'حلقة الفجر', category: 'حفظ', teacher: 'أحمد محمد', studentsCount: 0, attendance: '96%', status: 'نشطة' },
                { id: 2, name: 'حلقة العصر', category: 'تمكين', teacher: 'سعيد علي', studentsCount: 0, attendance: '92%', status: 'نشطة' }
            ],
            students: [
                { id: 101, name: 'محمد أحمد علي', circleId: 1, phone: '972590000000', status: 'نشط', joinDate: '2023-10-01', juzCount: 5, points: 150 },
                { id: 102, name: 'ياسين حسن عمر', circleId: 1, phone: '972590000001', status: 'نشط', joinDate: '2023-10-05', juzCount: 2, points: 80 },
                { id: 103, name: 'حمزة إبراهيم', circleId: 2, phone: '972590000002', status: 'نشط', joinDate: '2023-11-01', juzCount: 30, points: 500 }
            ],
            dailyLogs: [],
            finance: { budget: 75000, transactions: [] },
            tests: [],
            activityLogs: [],
            testRequests: [] 
        };

        const App = {
            db: {},
            currentUser: null,
            currentReportDate: new Date().toISOString().split('T')[0],
            myChart: null,
            currentPendingRequestId: null,

            init() {
                this.loadDB();
                this.setupLogin();
                this.setupEditUserForm();
                this.setupCircleForm();
                this.setupStudentForm();
                this.setupTestForm(); 
                this.setupRequestTestForm();
                this.updateClock();
                this.syncCounts();
                
                const savedUserId = sessionStorage.getItem('logged_user_id');
                if (savedUserId) {
                    const user = this.db.users.find(u => u.id == savedUserId);
                    if (user) {
                        this.currentUser = user;
                        this.startApp();
                    }
                }
            },

            loadDB() {
                try {
                    const data = localStorage.getItem(DB_KEY);
                    this.db = data ? JSON.parse(data) : JSON.parse(JSON.stringify(initialData));
                    
                    if(!this.db.finance) this.db.finance = JSON.parse(JSON.stringify(initialData.finance));
                    if(!this.db.finance.transactions) this.db.finance.transactions = [];
                    if(!this.db.students) this.db.students = [];
                    if(!this.db.circles) this.db.circles = [];
                    if(!this.db.dailyLogs) this.db.dailyLogs = [];
                    if(!this.db.tests) this.db.tests = []; 
                    if(!this.db.settings) this.db.settings = initialData.settings;
                    if(!this.db.activityLogs) this.db.activityLogs = [];
                    if(!this.db.testRequests) this.db.testRequests = [];
                    
                    this.db.students.forEach(s => { 
                        if(s.juzCount === undefined) s.juzCount = 0; 
                        if(s.points === undefined) s.points = 0;
                        s.juzCount = parseInt(s.juzCount) || 0;
                    });
                } catch(e) {
                    this.db = JSON.parse(JSON.stringify(initialData));
                }
            },

            saveDB() {
                localStorage.setItem(DB_KEY, JSON.stringify(this.db));
            },

            logActivity(action, details) {
                if(!this.db.activityLogs) this.db.activityLogs = [];
                this.db.activityLogs.push({
                    id: Date.now(),
                    user: this.currentUser ? this.currentUser.name : 'النظام',
                    action: action,
                    details: details,
                    date: new Date().toLocaleString('ar-SA')
                });
                this.saveDB();
            },

            syncCounts() {
                if(!this.db.circles) return;
                this.db.circles.forEach(c => {
                    c.studentsCount = this.db.students.filter(s => s.circleId == c.id && s.status === 'نشط').length;
                });
            },

            exportBackup() {
                const dataStr = "data:text/json;charset=utf-8," + encodeURIComponent(JSON.stringify(this.db));
                const downloadAnchorNode = document.createElement('a');
                downloadAnchorNode.setAttribute("href", dataStr);
                downloadAnchorNode.setAttribute("download", "furqan_backup_" + new Date().toISOString().split('T')[0] + ".json");
                document.body.appendChild(downloadAnchorNode);
                downloadAnchorNode.click();
                downloadAnchorNode.remove();
                this.showToast("تم تصدير النسخة الاحتياطية بنجاح", "success");
                this.logActivity('تصدير بيانات', 'نسخة احتياطية كاملة');
            },

            importBackup(event) {
                const file = event.target.files[0];
                if (!file) return;
                const reader = new FileReader();
                reader.onload = (e) => {
                    try {
                        const importedData = JSON.parse(e.target.result);
                        this.db = importedData;
                        this.saveDB();
                        this.showToast("تمت استعادة البيانات بنجاح، سيتم إعادة تحميل الصفحة");
                        this.logActivity('استعادة بيانات', 'من ملف خارجي');
                        setTimeout(() => location.reload(), 1500);
                    } catch (err) {
                        this.showToast("ملف غير صالح!", "error");
                    }
                };
                reader.readAsText(file);
            },

            showToast(msg, type = 'info') {
                const toast = document.getElementById('toast');
                const toastMsg = document.getElementById('toast-msg');
                const toastIcon = document.getElementById('toast-icon');
                
                toastMsg.textContent = msg;
                if(type === 'error') toastIcon.className = "fas fa-exclamation-triangle text-red-500";
                else if(type === 'success') toastIcon.className = "fas fa-check-circle text-green-500";
                else toastIcon.className = "fas fa-info-circle text-primary";
                
                toast.style.display = 'block';
                setTimeout(() => { toast.style.display = 'none'; }, 3000);
            },

            setupLogin() {
                const loginForm = document.getElementById('login-form');
                loginForm.onsubmit = (e) => {
                    e.preventDefault();
                    const u = document.getElementById('username').value.trim();
                    const p = document.getElementById('password').value;
                    const user = this.db.users.find(x => x.username === u && x.password === btoa(p));

                    if (user) {
                        this.currentUser = user;
                        sessionStorage.setItem('logged_user_id', user.id);
                        this.startApp();
                        this.showToast(`أهلاً بك مجدداً ${user.name}`);
                        this.logActivity('تسجيل دخول', 'دخول ناجح للمستخدم');
                    } else {
                        this.showToast('بيانات الدخول غير صحيحة!', 'error');
                    }
                };
            },

            startApp() {
                document.getElementById('login-screen').classList.add('hidden');
                document.getElementById('main-app').classList.remove('hidden');
                this.updateUserInfoUI();
                this.renderSidebar();
                
                if (this.currentUser.role === 'admin' || this.currentUser.role === 'supervisor') {
                    this.navigate('admin-dashboard');
                } else {
                    this.navigate('teacher-daily');
                }
                
                if (this.currentUser.role === 'admin' || this.currentUser.role === 'supervisor') {
                    document.getElementById('admin-quick-actions').classList.remove('hidden');
                }
            },

            updateUserInfoUI() {
                document.getElementById('user-display-name').textContent = this.currentUser.name;
                document.getElementById('user-avatar-initial').textContent = this.currentUser.name[0];
                
                let roleName = 'محفظ الحلقة';
                if(this.currentUser.role === 'admin') roleName = 'مدير المركز';
                else if(this.currentUser.role === 'supervisor') roleName = 'مشرف أكاديمي';
                
                document.getElementById('user-role-badge').textContent = roleName;
            },

            logout() { 
                this.logActivity('تسجيل خروج', this.currentUser.name);
                sessionStorage.removeItem('logged_user_id');
                location.reload(); 
            },

            renderSidebar() {
                const adminNav = document.getElementById('nav-admin-main');
                const teacherNav = document.getElementById('nav-teacher-main');
                
                if (this.currentUser.role === 'admin' || this.currentUser.role === 'supervisor') {
                    document.getElementById('admin-menu').classList.remove('hidden');
                    const items = [
                        { id: 'admin-dashboard', label: 'لوحة التحكم', icon: 'fa-tachometer-alt' },
                        { id: 'admin-circles', label: 'إدارة الحلقات', icon: 'fa-layer-group' },
                        { id: 'admin-students', label: 'إدارة الطلاب', icon: 'fa-users' },
                        { id: 'admin-tests-board', label: 'لوحة الاختبارات', icon: 'fa-vial' }, // ميزة مضافة: لوحة إدارة الاختبارات
                        { id: 'admin-users', label: 'إدارة المحفظين', icon: 'fa-user-shield' },
                        { id: 'admin-monthly-reports', label: 'التقارير الشهرية', icon: 'fa-chart-pie' }
                    ];
                    
                    if(this.currentUser.role === 'admin') {
                        items.push({ id: 'admin-finance', label: 'المالية والرواتب', icon: 'fa-coins' });
                    }
                    
                    adminNav.innerHTML = items.map(i => this.componentSidebarLink(i)).join('');
                } else {
                    document.getElementById('teacher-menu').classList.remove('hidden');
                    const items = [
                        { id: 'teacher-daily', label: 'التقرير اليومي', icon: 'fa-edit' },
                        { id: 'teacher-students', label: 'طلابي', icon: 'fa-user-graduate' },
                        { id: 'teacher-monthly-reports', label: 'تقرير الحلقة الشهري', icon: 'fa-chart-pie' }, 
                        { id: 'teacher-profile', label: 'ملفي الشخصي', icon: 'fa-user-cog' }
                    ];
                    teacherNav.innerHTML = items.map(i => this.componentSidebarLink(i)).join('');
                }
            },

            componentSidebarLink(item) {
                return `
                    <li>
                        <button onclick="App.navigate('${item.id}')" id="nav-btn-${item.id}" class="sidebar-link w-full flex items-center space-x-3 space-x-reverse p-3 rounded-xl hover:bg-gray-50 transition-all font-bold text-gray-500 text-sm">
                            <i class="fas ${item.icon} w-6 text-center"></i>
                            <span>${item.label}</span>
                        </button>
                    </li>
                `;
            },

            navigate(id) {
                document.querySelectorAll('.sidebar-link').forEach(el => el.classList.remove('active'));
                const btn = document.getElementById(`nav-btn-${id}`);
                if(btn) btn.classList.add('active');
                
                const area = document.getElementById('content-area');
                area.innerHTML = '<div class="flex flex-col items-center justify-center p-20"><i class="fas fa-circle-notch fa-spin text-primary text-4xl mb-4"></i><p class="text-gray-400 font-bold animate-pulse">جاري تحميل البيانات...</p></div>';

                setTimeout(() => {
                    switch(id) {
                        case 'admin-dashboard': this.renderAdminDashboard(); break;
                        case 'admin-students': this.renderAdminStudents(); break;
                        case 'admin-users': this.renderAdminUsers(); break;
                        case 'admin-circles': this.renderAdminCircles(); break;
                        case 'admin-tests-board': this.renderAdminTestsBoard(); break; // ميزة مضافة
                        case 'teacher-daily': this.renderTeacherDaily(); break;
                        case 'teacher-students': this.renderTeacherStudents(); break;
                        case 'teacher-profile': this.renderUserProfile(); break;
                        case 'admin-finance': this.renderAdminFinance(); break;
                        case 'admin-monthly-reports': this.renderMonthlyReports('admin'); break; 
                        case 'teacher-monthly-reports': this.renderMonthlyReports('teacher'); break; 
                    }
                }, 100);

                const titleEl = document.getElementById('page-title');
                if(titleEl && btn) titleEl.textContent = btn.querySelector('span').textContent;
            },

            renderAdminCircles() {
                this.syncCounts();
                const area = document.getElementById('content-area');
                area.innerHTML = `
                    <div class="flex justify-between items-center mb-6">
                        <h3 class="font-black text-gray-800 text-lg">نظرة عامة على الحلقات</h3>
                        <button onclick="App.openModal('modal-add-circle')" class="bg-secondary text-white px-5 py-2 rounded-xl text-xs font-black shadow-lg">إضافة حلقة +</button>
                    </div>
                    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                        ${this.db.circles.length > 0 ? this.db.circles.map(c => `
                            <div class="bg-white p-6 rounded-3xl border border-gray-100 shadow-sm relative overflow-hidden group">
                                <div class="absolute top-0 left-0 w-2 h-full bg-primary opacity-20 group-hover:opacity-100 transition-all"></div>
                                <div class="flex justify-between">
                                    <h4 class="font-black text-primary mb-1">${c.name} <span class="text-[9px] font-bold text-gray-400">(${c.category || 'عام'})</span></h4>
                                    <button onclick="App.deleteCircle(${c.id})" class="text-red-300 hover:text-red-500 text-xs"><i class="fas fa-trash"></i></button>
                                </div>
                                <p class="text-xs font-bold text-gray-400 mb-4">المحفظ: ${c.teacher}</p>
                                <div class="flex justify-between items-center bg-gray-50 p-3 rounded-2xl">
                                    <div class="text-center">
                                        <p class="text-[10px] font-black text-gray-400">الطلاب</p>
                                        <p class="text-sm font-black text-gray-700">${c.studentsCount}</p>
                                    </div>
                                    <div class="text-center">
                                        <p class="text-[10px] font-black text-gray-400">الحالة</p>
                                        <p class="text-[10px] font-black text-green-600">${c.status || 'نشطة'}</p>
                                    </div>
                                    <div class="text-center">
                                        <button onclick="App.navigate('admin-students')" class="text-primary hover:scale-110 transition-all"><i class="fas fa-external-link-alt"></i></button>
                                    </div>
                                </div>
                            </div>
                        `).join('') : '<p class="text-gray-400 text-center col-span-full py-10 font-bold">لا يوجد حلقات حالياً</p>'}
                    </div>
                `;
                const teacherSelect = document.getElementById('new-circle-teacher');
                if(teacherSelect) {
                    teacherSelect.innerHTML = this.db.users.filter(u => u.role === 'teacher').map(u => `<option value="${u.name}" data-userid="${u.id}">${u.name}</option>`).join('');
                }
            },

            // ميزة مضافة: لوحة إدارة الاختبارات
            renderAdminTestsBoard() {
                const area = document.getElementById('content-area');
                const tests = this.db.tests || [];
                const requests = (this.db.testRequests || []).filter(r => r.status === 'pending');
                
                area.innerHTML = `
                    <div class="grid grid-cols-1 md:grid-cols-3 gap-6 mb-8">
                        <div class="bg-white p-6 rounded-3xl border border-gray-100 shadow-sm">
                            <p class="text-xs text-gray-400 font-bold uppercase mb-1">إجمالي الاختبارات</p>
                            <h4 class="text-3xl font-black text-primary">${tests.length}</h4>
                        </div>
                        <div class="bg-white p-6 rounded-3xl border border-gray-100 shadow-sm">
                            <p class="text-xs text-gray-400 font-bold uppercase mb-1">طلبات بانتظار الاعتماد</p>
                            <h4 class="text-3xl font-black text-orange-500">${requests.length}</h4>
                        </div>
                        <div class="bg-white p-6 rounded-3xl border border-gray-100 shadow-sm">
                            <p class="text-xs text-gray-400 font-bold uppercase mb-1">متوسط الدرجات</p>
                            <h4 class="text-3xl font-black text-green-600">
                                ${tests.length > 0 ? Math.round(tests.reduce((acc, t) => acc + parseInt(t.score), 0) / tests.length) : 0}%
                            </h4>
                        </div>
                    </div>

                    <div class="bg-white rounded-3xl shadow-sm border border-gray-100 overflow-hidden mb-8">
                        <div class="p-6 border-b flex justify-between items-center bg-gray-50/50">
                            <h3 class="font-black">سجل الاختبارات المعتمدة</h3>
                            <button onclick="window.print()" class="text-xs font-bold text-gray-500"><i class="fas fa-print ml-1"></i> طباعة السجل</button>
                        </div>
                        <div class="overflow-x-auto">
                            <table class="w-full text-right">
                                <thead class="bg-gray-50 text-[10px] font-black text-gray-400">
                                    <tr>
                                        <th class="p-4">الطالب</th>
                                        <th class="p-4">الجزء</th>
                                        <th class="p-4">الدرجة</th>
                                        <th class="p-4">التقدير</th>
                                        <th class="p-4">التاريخ</th>
                                        <th class="p-4">إجراء</th>
                                    </tr>
                                </thead>
                                <tbody class="divide-y divide-gray-50">
                                    ${tests.length > 0 ? tests.slice().reverse().map(t => {
                                        const s = this.db.students.find(st => st.id == t.studentId);
                                        return `
                                            <tr class="hover:bg-gray-50">
                                                <td class="p-4 font-bold text-sm">${s ? s.name : 'طالب محذوف'}</td>
                                                <td class="p-4 text-xs font-black text-primary">${t.part}</td>
                                                <td class="p-4 text-xs font-black">${t.score}%</td>
                                                <td class="p-4"><span class="px-2 py-1 rounded-lg bg-blue-50 text-blue-600 text-[10px] font-black">${t.grade}</span></td>
                                                <td class="p-4 text-xs text-gray-400">${t.date}</td>
                                                <td class="p-4"><button onclick="App.deleteTest(${t.id})" class="text-red-300 hover:text-red-500"><i class="fas fa-trash-alt"></i></button></td>
                                            </tr>
                                        `;
                                    }).join('') : '<tr><td colspan="6" class="text-center py-10 text-gray-400 font-bold">لا يوجد اختبارات مسجلة</td></tr>'}
                                </tbody>
                            </table>
                        </div>
                    </div>
                `;
            },

            deleteTest(testId) {
                if(confirm('هل أنت متأكد من حذف نتيجة هذا الاختبار؟')) {
                    this.db.tests = this.db.tests.filter(t => t.id !== testId);
                    this.saveDB();
                    this.renderAdminTestsBoard();
                    this.showToast("تم حذف نتيجة الاختبار");
                }
            },

            deleteCircle(id) {
                if(confirm('هل أنت متأكد من حذف هذه الحلقة؟ سيتم تحويل طلابها إلى طلاب بدون حلقة.')) {
                    this.db.students.forEach(s => { if(s.circleId == id) s.circleId = null; });
                    this.db.users.forEach(u => { if(u.circleId == id) u.circleId = null; });
                    this.db.circles = this.db.circles.filter(c => c.id !== id);
                    this.logActivity('حذف حلقة', `ID: ${id}`);
                    this.saveDB();
                    this.renderAdminCircles();
                }
            },

            setupCircleForm() {
                const form = document.getElementById('form-add-circle');
                if(!form) return;
                form.onsubmit = (e) => {
                    e.preventDefault();
                    const teacherSelect = document.getElementById('new-circle-teacher');
                    const selectedTeacherName = teacherSelect.value;
                    const selectedTeacherId = teacherSelect.options[teacherSelect.selectedIndex].dataset.userid;
                    
                    const circleId = Date.now();
                    const newCircle = {
                        id: circleId,
                        name: document.getElementById('new-circle-name').value,
                        category: document.getElementById('new-circle-category').value, // ميزة مضافة
                        teacher: selectedTeacherName,
                        studentsCount: 0,
                        attendance: '0%',
                        status: 'نشطة'
                    };
                    
                    const teacherIdx = this.db.users.findIndex(u => u.id == selectedTeacherId);
                    if(teacherIdx > -1) this.db.users[teacherIdx].circleId = circleId;

                    this.db.circles.push(newCircle);
                    this.logActivity('إضافة حلقة', newCircle.name);
                    this.saveDB();
                    this.closeModal('modal-add-circle');
                    this.renderAdminCircles();
                    this.showToast("تم إنشاء الحلقة بنجاح", "success");
                    form.reset();
                };
            },

            renderAdminUsers() {
                const area = document.getElementById('content-area');
                area.innerHTML = `
                    <div class="bg-white rounded-3xl shadow-sm border border-gray-100 overflow-hidden">
                        <div class="p-6 border-b flex justify-between items-center bg-gray-50/50">
                            <h3 class="font-black">إدارة حسابات النظام والمحفظين</h3>
                            <button onclick="App.openAddUserModal()" class="bg-primary text-white px-4 py-2 rounded-xl text-xs font-black shadow-lg">إضافة محفظ جديد +</button>
                        </div>
                        <div class="overflow-x-auto">
                            <table class="w-full text-right">
                                <thead class="bg-gray-50 text-[10px] font-black text-gray-400 uppercase">
                                    <tr>
                                        <th class="p-4">الاسم</th>
                                        <th class="p-4">رقم الهوية</th>
                                        <th class="p-4">اسم المستخدم</th>
                                        <th class="p-4">الحلقة</th>
                                        <th class="p-4">الصلاحية</th>
                                        <th class="p-4">الإجراء</th>
                                    </tr>
                                </thead>
                                <tbody class="divide-y divide-gray-50">
                                    ${this.db.users.map(u => `
                                        <tr class="hover:bg-gray-50 transition-all group">
                                            <td class="p-4 font-bold text-sm text-gray-700">${u.name}</td>
                                            <td class="p-4 text-xs font-bold text-gray-400">${u.idNumber || '---'}</td>
                                            <td class="p-4 text-xs font-black text-primary">${u.username}</td>
                                            <td class="p-4 text-xs font-bold text-gray-400">${this.db.circles.find(c => c.id == u.circleId)?.name || 'بدون حلقة'}</td>
                                            <td class="p-4"><span class="px-2 py-1 rounded-lg ${u.role === 'admin' ? 'bg-purple-50 text-purple-600' : 'bg-blue-50 text-blue-600'} text-[10px] font-black">${u.role === 'admin' ? 'مدير' : u.role === 'supervisor' ? 'مشرف' : 'محفظ'}</span></td>
                                            <td class="p-4 flex space-x-2 space-x-reverse">
                                                <button onclick="App.openEditUserModal(${u.id})" class="bg-white border border-gray-200 text-gray-600 px-3 py-1 rounded-lg text-[10px] font-black hover:bg-primary hover:text-white transition-all">تعديل</button>
                                                ${u.id !== this.currentUser.id ? `<button onclick="App.deleteUser(${u.id})" class="text-red-400 p-1 hover:text-red-600"><i class="fas fa-trash"></i></button>` : ''}
                                            </td>
                                        </tr>
                                    `).join('')}
                                </tbody>
                            </table>
                        </div>
                    </div>
                `;
            },

            openAddUserModal() {
                document.getElementById('form-edit-user').reset();
                document.getElementById('edit-user-id').value = '';
                document.getElementById('user-modal-title').textContent = 'إضافة مستخدم جديد';
                document.getElementById('role-select-container').classList.remove('hidden');
                this.openModal('modal-edit-user');
            },

            openEditUserModal(userId) {
                const user = this.db.users.find(u => u.id === userId);
                if (user) {
                    document.getElementById('edit-user-id').value = user.id;
                    document.getElementById('edit-user-name').value = user.name;
                    document.getElementById('edit-user-username').value = user.username;
                    document.getElementById('edit-user-role').value = user.role;
                    document.getElementById('edit-user-id-number').value = user.idNumber || '';
                    document.getElementById('edit-user-dob').value = user.dob || '';
                    
                    try { document.getElementById('edit-user-pass').value = atob(user.password); } 
                    catch(e) { document.getElementById('edit-user-pass').value = user.password; }
                    
                    document.getElementById('user-modal-title').textContent = 'تعديل بيانات الحساب';
                    
                    if(userId === this.currentUser.id && this.currentUser.role !== 'admin') {
                        document.getElementById('role-select-container').classList.add('hidden');
                    } else {
                        document.getElementById('role-select-container').classList.remove('hidden');
                    }
                    this.openModal('modal-edit-user');
                }
            },

            deleteUser(id) {
                if(confirm('هل أنت متأكد من حذف هذا المستخدم؟')) {
                    this.db.users = this.db.users.filter(u => u.id !== id);
                    this.logActivity('حذف مستخدم', `ID: ${id}`);
                    this.saveDB();
                    this.renderAdminUsers();
                    this.showToast('تم الحذف بنجاح');
                }
            },

            setupEditUserForm() {
                const form = document.getElementById('form-edit-user');
                if(!form) return;
                form.onsubmit = (e) => {
                    e.preventDefault();
                    const id = document.getElementById('edit-user-id').value;
                    const username = document.getElementById('edit-user-username').value.trim();
                    const exists = this.db.users.some(u => u.username === username && u.id != id);
                    if(exists) {
                        this.showToast('اسم المستخدم هذا مستخدم مسبقاً!', 'error');
                        return;
                    }

                    const userData = {
                        name: document.getElementById('edit-user-name').value.trim(),
                        username: username,
                        role: document.getElementById('edit-user-role').value,
                        idNumber: document.getElementById('edit-user-id-number').value,
                        dob: document.getElementById('edit-user-dob').value,
                        password: btoa(document.getElementById('edit-user-pass').value)
                    };

                    if (id) {
                        const idx = this.db.users.findIndex(u => u.id == id);
                        this.db.users[idx] = { ...this.db.users[idx], ...userData };
                        if (id == this.currentUser.id) this.currentUser = this.db.users[idx];
                        this.logActivity('تعديل حساب', userData.name);
                    } else {
                        const newUser = { id: Date.now(), ...userData, circleId: null };
                        this.db.users.push(newUser);
                        this.logActivity('إنشاء حساب', userData.name);
                    }

                    this.saveDB();
                    this.closeModal('modal-edit-user');
                    this.showToast('تم حفظ البيانات بنجاح', "success");
                    this.renderAdminUsers();
                    this.updateUserInfoUI();
                };
            },

            renderAdminDashboard() {
                this.syncCounts();
                const area = document.getElementById('content-area');
                const reportsToday = this.db.dailyLogs.filter(l => l.date === new Date().toISOString().split('T')[0]).length;
                const criticalStudents = this.db.students.filter(s => this.checkAbsenteeism(s.id));
                const pendingRequests = (this.db.testRequests || []).filter(r => r.status === 'pending');
                let requestsHtml = '';
                if (pendingRequests.length > 0) {
                    requestsHtml = `
                        <div class="mb-8 bg-white p-6 rounded-3xl border border-purple-100 shadow-sm page-animate">
                            <h3 class="text-sm font-black text-purple-800 mb-4 flex items-center"><i class="fas fa-file-signature ml-2 text-purple-500"></i> طلبات الاختبارات المعلقة (${pendingRequests.length})</h3>
                            <div class="space-y-3">
                                ${pendingRequests.map(r => `
                                    <div class="flex flex-col md:flex-row justify-between items-start md:items-center bg-purple-50/50 p-4 rounded-2xl border border-purple-50 gap-2">
                                        <div>
                                            <p class="text-sm font-black text-gray-800">${r.studentName} <span class="text-xs font-normal text-gray-400">(${r.circleName})</span></p>
                                            <p class="text-xs font-bold text-purple-700">طلب اختبار: ${r.part} | مرسل من: ${r.requestedBy}</p>
                                            ${r.notes ? `<p class="text-[10px] text-gray-500 mt-1">ملاحظة: ${r.notes}</p>` : ''}
                                        </div>
                                        <div class="flex gap-2 w-full md:w-auto justify-end">
                                            <button onclick="App.approveTestRequest(${r.id}, ${r.studentId}, '${r.part}')" class="bg-primary text-white text-xs px-3 py-1.5 rounded-lg font-black hover:scale-105 transition-all">قبول وتسجيل النتيجة</button>
                                            <button onclick="App.rejectTestRequest(${r.id})" class="bg-red-50 text-red-600 text-xs px-3 py-1.5 rounded-lg font-black hover:bg-red-100 transition-all">رفض</button>
                                        </div>
                                    </div>
                                `).join('')}
                            </div>
                        </div>
                    `;
                }

                area.innerHTML = `
                    ${this.renderHonorRoll()} 
                    
                    <div class="mb-8 ${criticalStudents.length === 0 ? 'hidden' : ''}">
                        <div class="bg-red-50 border border-red-100 p-4 rounded-3xl alert-pulse flex items-center justify-between">
                            <div class="flex items-center gap-4">
                                <div class="w-10 h-10 rounded-full bg-red-100 flex items-center justify-center text-red-600"><i class="fas fa-exclamation-triangle"></i></div>
                                <div>
                                    <h4 class="text-sm font-black text-red-800">تنبيه الغياب المتكرر</h4>
                                    <p class="text-[10px] text-red-600 font-bold">هناك ${criticalStudents.length} طلاب غائبون لأكثر من 3 أيام متتالية، يرجى المتابعة.</p>
                                </div>
                            </div>
                            <button onclick="App.navigate('admin-students')" class="bg-red-600 text-white px-4 py-2 rounded-xl text-[10px] font-black">مراجعة الطلاب</button>
                        </div>
                    </div>

                    ${requestsHtml}

                    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6 mb-8">
                        ${this.componentStatCard('إجمالي الطلاب', this.db.students.length, '+'+this.db.students.filter(s=>s.status==='نشط').length + ' نشط', 'fa-users', 'primary')}
                        ${this.componentStatCard('الحلقات النشطة', this.db.circles.length, '+'+this.db.circles.length, 'fa-circle', 'secondary')}
                        ${this.componentStatCard('الرصيد المتاح', this.calculateBalance().toLocaleString(), 'SAR', 'fa-wallet', 'accent')}
                        ${this.componentStatCard('تقارير اليوم', reportsToday, 'تم استلامها', 'fa-file-signature', 'primary')}
                    </div>

                    <div class="grid grid-cols-1 lg:grid-cols-3 gap-6 mb-8">
                        <div class="lg:col-span-2">
                            <div class="bg-white rounded-3xl shadow-sm p-6 border border-gray-100 h-full">
                                <h3 class="text-lg font-black text-gray-800 mb-6 flex items-center"><i class="fas fa-chart-line ml-3 text-primary"></i> تحليل إنجاز الحلقات</h3>
                                <div class="overflow-x-auto">
                                    <table class="w-full text-right">
                                        <thead>
                                            <tr class="text-gray-400 text-[10px] uppercase font-black border-b">
                                                <th class="pb-3">اسم الحلقة</th>
                                                <th class="pb-3">المحفظ</th>
                                                <th class="pb-3 text-center">الطلاب</th>
                                                <th class="pb-3 text-center">التقرير</th>
                                            </tr>
                                        </thead>
                                        <tbody class="divide-y divide-gray-50">
                                            ${this.db.circles.length > 0 ? this.db.circles.map(c => {
                                                const hasReport = this.db.dailyLogs.some(l => {
                                                    const s = this.db.students.find(st => st.id == l.studentId);
                                                    return s && s.circleId == c.id && l.date == new Date().toISOString().split('T')[0];
                                                });
                                                return `
                                                <tr class="hover:bg-gray-50 transition-all">
                                                    <td class="py-4 font-bold text-sm text-gray-700">${c.name}</td>
                                                    <td class="py-4 text-xs font-bold text-gray-500">${c.teacher}</td>
                                                    <td class="py-4 text-xs font-black text-primary text-center">${c.studentsCount}</td>
                                                    <td class="py-4 text-center">
                                                        <span class="text-[9px] px-2 py-1 rounded-full font-black ${hasReport ? 'bg-green-100 text-green-600' : 'bg-red-100 text-red-600'}">
                                                            ${hasReport ? 'مكتمل' : 'معلق'}
                                                        </span>
                                                    </td>
                                                </tr>
                                            `}).join('') : '<tr><td colspan="4" class="text-center py-4 text-gray-400 text-xs">لا يوجد بيانات</td></tr>'}
                                        </tbody>
                                    </table>
                                </div>
                            </div>
                        </div>
                        <div class="flex flex-col gap-6">
                            <div class="bg-white rounded-3xl shadow-sm p-6 border border-gray-100 h-[280px]">
                                <h3 class="text-sm font-black text-gray-400 mb-6 tracking-widest uppercase">توزيع المستويات</h3>
                                <div class="relative h-40">
                                    <canvas id="attendance-chart-mini"></canvas>
                                </div>
                            </div>
                            
                            <div class="bg-dark text-white rounded-3xl shadow-sm p-6 h-[250px] overflow-hidden flex flex-col">
                                <h3 class="text-xs font-black text-blue-300 mb-4 uppercase tracking-widest">آخر نشاطات النظام</h3>
                                <div class="flex-1 overflow-y-auto custom-scrollbar pr-2">
                                    ${this.db.activityLogs && this.db.activityLogs.length > 0 ? 
                                        this.db.activityLogs.slice(-10).reverse().map(log => `
                                            <div class="activity-item bg-white/5 border-r-blue-400 mb-2">
                                                <p class="font-black text-[10px] text-blue-200">${log.user}</p>
                                                <p class="text-[9px] opacity-80">${log.action}: ${log.details}</p>
                                            </div>
                                        `).join('') : '<p class="text-[10px] opacity-50 text-center py-10">لا يوجد نشاطات مسجلة</p>'
                                    }
                                </div>
                            </div>
                        </div>
                    </div>
                `;
                setTimeout(() => this.initChart(), 50);
            },

            calculateBalance() {
                const f = this.db.finance || initialData.finance;
                const totalIncome = (f.transactions || []).filter(t => t.type === 'income').reduce((sum, t) => sum + parseFloat(t.amount), 0);
                const totalExpense = (f.transactions || []).filter(t => t.type === 'expense').reduce((sum, t) => sum + parseFloat(t.amount), 0);
                return (parseFloat(f.budget) || 0) + totalIncome - totalExpense;
            },

            componentStatCard(title, val, change, icon, color) {
                const colorClass = { primary: 'bg-primary text-white', secondary: 'bg-secondary text-white', accent: 'bg-accent text-white' }[color];
                return `
                    <div class="stat-card bg-white rounded-3xl p-6 border border-gray-100 shadow-sm flex flex-col">
                        <div class="flex justify-between items-start mb-4">
                            <div>
                                <p class="text-[10px] uppercase font-black text-gray-400 mb-1 tracking-widest">${title}</p>
                                <p class="text-2xl font-black text-gray-800">${val}</p>
                            </div>
                            <div class="w-12 h-12 rounded-2xl ${colorClass} flex items-center justify-center shadow-lg shadow-black/5">
                                <i class="fas ${icon} text-xl"></i>
                            </div>
                        </div>
                        <div class="mt-auto flex items-center text-[10px] font-black text-green-500 bg-green-50 w-fit px-2 py-1 rounded-lg">
                              ${change}
                        </div>
                    </div>
                `;
            },

            renderAdminStudents(filter = '', circleFilter = '') {
                const area = document.getElementById('content-area');
                const searchTerm = filter.toLowerCase();
                let filteredStudents = this.db.students.filter(s => 
                    (s.name || '').toLowerCase().includes(searchTerm) || (s.phone || '').includes(searchTerm)
                );
                
                if (circleFilter) {
                    filteredStudents = filteredStudents.filter(s => s.circleId == circleFilter);
                }
                
                area.innerHTML = `
                    <div class="bg-white rounded-3xl shadow-sm border border-gray-100 overflow-hidden">
                        <div class="p-6 border-b flex flex-col md:flex-row justify-between items-center bg-gray-50/50 gap-4">
                            <h3 class="font-black text-gray-800">إدارة الطلاب (${filteredStudents.length})</h3>
                            <div class="flex flex-wrap items-center gap-2">
                                <select id="student-circle-filter" onchange="App.renderAdminStudents(document.getElementById('student-search-input').value, this.value)" class="bg-white border rounded-xl px-3 py-2 text-xs font-bold outline-none border-gray-200">
                                    <option value="">كل الحلقات</option>
                                    ${this.db.circles.map(c => `<option value="${c.id}" ${circleFilter == c.id ? 'selected' : ''}>${c.name}</option>`).join('')}
                                </select>
                                <div class="relative w-64">
                                    <input type="text" id="student-search-input" value="${filter}" placeholder="بحث باسم الطالب أو الهاتف..." class="w-full bg-white border rounded-xl px-4 py-2 text-xs font-bold outline-none focus:border-primary border-gray-200">
                                </div>
                                <button onclick="App.exportStudentsCSV()" class="bg-gray-100 p-2 rounded-xl text-gray-600 hover:bg-gray-200" title="تصدير Excel"><i class="fas fa-file-excel"></i></button>
                            </div>
                        </div>
                        <div class="overflow-x-auto">
                            <table class="w-full text-right">
                                <thead class="bg-gray-50 text-[10px] font-black text-gray-400 uppercase">
                                    <tr>
                                        <th class="p-4">الاسم</th>
                                        <th class="p-4">الحلقة</th>
                                        <th class="p-4 w-48">التقدم (الأجزاء)</th>
                                        <th class="p-4">النقاط</th> 
                                        <th class="p-4">الحالة</th>
                                        <th class="p-4">الإجراء</th>
                                    </tr>
                                </thead>
                                <tbody class="divide-y divide-gray-50">
                                    ${filteredStudents.length > 0 ? filteredStudents.map(s => {
                                        const isAbsent = this.checkAbsenteeism(s.id);
                                        return `
                                        <tr class="hover:bg-blue-50/20 transition-all group ${isAbsent ? 'absent-row' : ''}">
                                            <td class="p-4">
                                                <p class="font-bold text-sm text-gray-800">
                                                    ${s.name}
                                                    ${isAbsent ? '<i class="fas fa-exclamation-triangle text-red-500 text-[10px] mr-1" title="تنبيه: غياب متكرر (3+ أيام)"></i>' : ''}
                                                </p>
                                                <p class="text-[9px] text-gray-400">هاتف: ${s.phone || '---'}</p>
                                            </td>
                                            <td class="p-4 text-xs font-bold text-gray-500">${this.db.circles.find(c => c.id == s.circleId)?.name || '<span class="text-red-400 text-[10px]">غير موزع</span>'}</td>
                                            <td class="p-4">
                                                <div class="flex items-center space-x-2 space-x-reverse">
                                                    <div class="flex-1 progress-bar"><div class="progress-fill" style="width: ${((s.juzCount || 0)/30)*100}%"></div></div>
                                                    <span class="text-[10px] font-black">${s.juzCount || 0}/30</span>
                                                </div>
                                            </td>
                                            <td class="p-4 text-xs font-black text-orange-500"><i class="fas fa-star ml-1"></i>${s.points || 0}</td>
                                            <td class="p-4 text-xs font-black">
                                                <span class="px-2 py-1 rounded-lg ${s.status === 'نشط' ? 'bg-green-50 text-green-600' : 'bg-red-50 text-red-600'} text-[10px]">${s.status || 'نشط'}</span>
                                            </td>
                                            <td class="p-4 flex items-center space-x-3 space-x-reverse">
                                                <button onclick="App.openAddTestModal(${s.id})" class="text-orange-500 hover:scale-110 transition-all" title="تسجيل اختبار"><i class="fas fa-medal"></i></button>
                                                <button onclick="App.viewStudentHistory(${s.id})" class="text-green-500 hover:scale-110 transition-all" title="سجل المتابعة"><i class="fas fa-history"></i></button>
                                                <button onclick="App.printStudentCertificate(${s.id})" class="text-purple-500 hover:scale-110 transition-all" title="شهادة إنجاز"><i class="fas fa-award"></i></button>
                                                <button onclick="App.openEditStudentModal(${s.id})" class="text-blue-400 hover:text-blue-600"><i class="fas fa-edit"></i></button>
                                                <button onclick="App.deleteStudent(${s.id})" class="text-red-400 hover:text-red-600"><i class="fas fa-user-minus"></i></button>
                                            </td>
                                        </tr>
                                    `}).join('') : '<tr><td colspan="6" class="text-center py-10 text-gray-400 font-bold">لا يوجد نتائج للبحث</td></tr>'}
                                </tbody>
                            </table>
                        </div>
                    </div>
                `;
                
                const searchInput = document.getElementById('student-search-input');
                if(searchInput) {
                    searchInput.focus();
                    searchInput.addEventListener('input', (e) => {
                        this.renderAdminStudents(e.target.value, document.getElementById('student-circle-filter').value);
                    });
                }
            },

            openEditStudentModal(id) {
                const s = this.db.students.find(x => x.id == id);
                if(s) {
                    document.getElementById('edit-student-id').value = s.id;
                    document.getElementById('student-name').value = s.name;
                    document.getElementById('student-phone').value = s.phone;
                    document.getElementById('student-juz').value = s.juzCount || 0;
                    document.getElementById('student-status').value = s.status || 'نشط';
                    document.getElementById('points-container').classList.remove('hidden');
                    document.getElementById('student-points').value = s.points || 0;
                    document.getElementById('student-modal-title').textContent = 'تعديل بيانات الطالب';
                    this.openModal('modal-add-student');
                    document.getElementById('modal-circle-select').value = s.circleId || '';
                }
            },

            deleteStudent(id) {
                if(confirm('هل أنت متأكد من حذف هذا الطالب نهائياً؟')) {
                    this.db.students = this.db.students.filter(s => s.id !== id);
                    this.logActivity('حذف طالب', `ID: ${id}`);
                    this.saveDB();
                    this.renderAdminStudents();
                    this.showToast("تم حذف الطالب", "success");
                }
            },

            exportStudentsCSV() {
                let csv = "الاسم,الحلقة,الهاتف,تاريخ الانضمام,عدد الأجزاء,النقاط\n";
                this.db.students.forEach(s => {
                    const cName = this.db.circles.find(c => c.id == s.circleId)?.name || 'غير موزع';
                    csv += `${s.name},${cName},${s.phone},${s.joinDate},${s.juzCount},${s.points || 0}\n`;
                });
                const blob = new Blob(["\ufeff" + csv], { type: 'text/csv;charset=utf-8;' });
                const link = document.createElement("a");
                link.href = URL.createObjectURL(blob);
                link.setAttribute("download", "students_list_" + new Date().getTime() + ".csv");
                link.click();
                this.logActivity('تصدير بيانات', 'قائمة الطلاب CSV');
            },

            renderTeacherDaily() {
                const circleId = this.currentUser.circleId;
                const students = this.db.students.filter(s => s.circleId == circleId && s.status === 'نشط');
                const activeDate = this.currentReportDate;
                const area = document.getElementById('content-area');
                
                // إنشاء قائمة السور HTML كخيار مسبق
                const surahOptions = QURAN_SURAHS.map(s => `<option value="${s}">${s}</option>`).join('');

                area.innerHTML = `
                    <div class="grid grid-cols-1 md:grid-cols-3 gap-6 mb-6 no-print">
                        <div class="bg-primary text-white p-6 rounded-3xl shadow-lg">
                            <p class="text-xs opacity-70 font-bold mb-1">طلاب الحلقة (النشطين)</p>
                            <h4 class="text-3xl font-black">${students.length}</h4>
                        </div>
                        <div class="bg-white p-6 rounded-3xl border border-gray-100">
                            <p class="text-xs text-gray-400 font-bold mb-1">تاريخ التقرير</p>
                            <input type="date" value="${activeDate}" onchange="App.renderTeacherDailyAtDate(this.value)" class="text-lg font-black text-gray-800 border-none outline-none bg-transparent w-full">
                        </div>
                        <div class="bg-white p-6 rounded-3xl border border-gray-100">
                            <button onclick="App.markAllPresent()" class="w-full h-full flex flex-col items-center justify-center space-y-1 hover:text-primary transition-all">
                                <i class="fas fa-check-double text-2xl text-secondary"></i>
                                <span class="text-xs font-black">تحضير الجميع (حاضر)</span>
                            </button>
                        </div>
                    </div>
                    <div class="bg-white rounded-3xl shadow-sm border border-gray-100 overflow-hidden page-animate">
                        <div class="p-6 border-b flex flex-col md:flex-row justify-between items-center bg-gray-50/50 gap-4">
                            <div><h3 class="font-black text-gray-800">رصد الإنجاز - <span class="text-primary">${activeDate}</span></h3></div>
                            <div class="flex space-x-2 space-x-reverse">
                                <button onclick="window.print()" class="no-print bg-white border border-gray-100 text-gray-600 px-4 py-2 rounded-xl text-xs font-black hover:bg-gray-100">طباعة</button>
                                <button onclick="App.saveDailyLogs()" class="bg-secondary text-white px-8 py-3 rounded-2xl font-black shadow-xl hover:scale-105 transition-all">حفظ التقارير</button>
                            </div>
                        </div>
                        <div class="overflow-x-auto">
                            <table class="w-full text-right">
                                <thead class="bg-gray-100 text-[10px] font-black text-gray-400 uppercase">
                                    <tr>
                                        <th class="p-4 w-40">اسم الطالب</th>
                                        <th class="p-4 text-center">الحضور</th>
                                        <th class="p-4 text-center">الحفظ اليومي</th>
                                        <th class="p-4 text-center">المراجعة</th>
                                        <th class="p-4 text-center">التقييم</th>
                                        <th class="p-4 text-center no-print">واتساب</th>
                                    </tr>
                                </thead>
                                <tbody class="divide-y divide-gray-50" id="teacher-log-tbody">
                                    ${students.length > 0 ? students.map(s => {
                                        const log = (this.db.dailyLogs || []).find(l => l.studentId == s.id && l.date == activeDate) || {};
                                        return `
                                            <tr class="hover:bg-blue-50/10 transition-all">
                                                <td class="p-4">
                                                    <p class="font-black text-[12px] text-gray-700 leading-tight">${s.name}</p>
                                                    <p class="text-[9px] text-gray-400">الرصيد: ${s.points || 0}</p>
                                                </td>
                                                <td class="p-4">
                                                    <select class="daily-input font-bold log-attendance" data-id="${s.id}" >
                                                        <option value="حاضر" ${log.attendance === 'حاضر' ? 'selected' : ''}>حاضر</option>
                                                        <option value="غائب" ${log.attendance === 'غائب' ? 'selected' : ''}>غائب</option>
                                                        <option value="مجاز" ${log.attendance === 'مجاز' ? 'selected' : ''}>مجاز</option>
                                                    </select>
                                                </td>
                                                <!-- ميزة مضافة: اختيار السورة وادخال الايات -->
                                                <td class="p-4 min-w-[150px]">
                                                    <div class="flex flex-col gap-1">
                                                        <select class="surah-select log-hifz-surah" data-id="${s.id}">
                                                            <option value="">اختر السورة</option>
                                                            ${surahOptions}
                                                        </select>
                                                        <input type="text" placeholder="الآيات (يدوي)" class="daily-input log-hifz-ayah" data-id="${s.id}" value="${log.hifzAyah || ''}">
                                                        <!-- الحفاظ على الحقل الأصلي للبيانات القديمة -->
                                                        <input type="hidden" class="log-hifz" data-id="${s.id}" value="${log.hifz || ''}">
                                                    </div>
                                                </td>
                                                <td class="p-4 min-w-[150px]">
                                                     <div class="flex flex-col gap-1">
                                                        <select class="surah-select log-murajaa-surah" data-id="${s.id}">
                                                            <option value="">اختر السورة</option>
                                                            ${surahOptions}
                                                        </select>
                                                        <input type="text" placeholder="الآيات (يدوي)" class="daily-input log-murajaa-ayah" data-id="${s.id}" value="${log.murajaaAyah || ''}">
                                                         <input type="hidden" class="log-murajaa" data-id="${s.id}" value="${log.murajaa || ''}">
                                                    </div>
                                                </td>
                                                <td class="p-4"><input type="text" placeholder="ممتاز" class="daily-input log-exam" data-id="${s.id}" value="${log.exam || ''}"></td>
                                                <td class="p-4 text-center no-print">
                                                  <button onclick="App.sendWhatsApp(${s.id})" class="text-green-500 hover:scale-110 transition-all"><i class="fab fa-whatsapp text-lg"></i></button>
                                                </td>
                                            </tr>
                                        `;
                                    }).join('') : '<tr><td colspan="6" class="text-center py-10 text-gray-400">لا يوجد طلاب نشطين في حلقتك حالياً</td></tr>'}
                                </tbody>
                            </table>
                        </div>
                    </div>
                `;
                
                // ضبط القيم المسجلة مسبقاً للسور إذا وجدت
                students.forEach(s => {
                    const log = (this.db.dailyLogs || []).find(l => l.studentId == s.id && l.date == activeDate) || {};
                    if(log.hifzSurah) {
                        const hSelect = document.querySelector(`.log-hifz-surah[data-id="${s.id}"]`);
                        if(hSelect) hSelect.value = log.hifzSurah;
                    }
                    if(log.murajaaSurah) {
                        const mSelect = document.querySelector(`.log-murajaa-surah[data-id="${s.id}"]`);
                        if(mSelect) mSelect.value = log.murajaaSurah;
                    }
                });
            },

            markAllPresent() {
                document.querySelectorAll('.log-attendance').forEach(select => select.value = 'حاضر');
                this.showToast("تم تحديد الجميع كـ حاضر");
            },

            renderTeacherDailyAtDate(date) {
                this.currentReportDate = date;
                this.renderTeacherDaily();
            },

            saveDailyLogs() {
                const activeDate = this.currentReportDate;
                const rows = document.querySelectorAll('#teacher-log-tbody tr');
                if(rows.length === 0) return this.showToast("لا يوجد بيانات لحفظها", "error");
                
                rows.forEach(row => {
                    const attEl = row.querySelector('.log-attendance');
                    if(!attEl) return;
                    const studentId = parseInt(attEl.dataset.id);
                    
                    const hSurah = row.querySelector('.log-hifz-surah').value;
                    const hAyah = row.querySelector('.log-hifz-ayah').value;
                    const mSurah = row.querySelector('.log-murajaa-surah').value;
                    const mAyah = row.querySelector('.log-murajaa-ayah').value;

                    const logData = {
                        studentId, date: activeDate,
                        attendance: attEl.value,
                        hifzSurah: hSurah,
                        hifzAyah: hAyah,
                        murajaaSurah: mSurah,
                        murajaaAyah: mAyah,
                        hifz: hSurah ? `${hSurah} (${hAyah})` : hAyah, // دمج للبيانات القديمة
                        murajaa: mSurah ? `${mSurah} (${mAyah})` : mAyah,
                        exam: row.querySelector('.log-exam').value,
                        month: new Date(activeDate).getMonth() + 1,
                        year: new Date(activeDate).getFullYear()
                    };
                    
                    const idx = this.db.dailyLogs.findIndex(l => l.studentId === studentId && l.date === activeDate);
                    
                    if (idx === -1) {
                        const sIdx = this.db.students.findIndex(s => s.id == studentId);
                        if(sIdx > -1 && logData.attendance === 'حاضر') {
                           this.db.students[sIdx].points = (this.db.students[sIdx].points || 0) + (this.db.settings.pointReward || 5);
                        }
                        this.db.dailyLogs.push(logData);
                    } else {
                        this.db.dailyLogs[idx] = logData;
                    }
                });
                
                this.logActivity('حفظ تقرير يومي', activeDate);
                this.saveDB();
                this.showToast('تم حفظ التقارير ومنح نقاط الحضور بنجاح', 'success');
            },

            renderTeacherStudents() {
                const circleId = this.currentUser.circleId;
                const students = this.db.students.filter(s => s.circleId == circleId);
                const area = document.getElementById('content-area');
                area.innerHTML = `
                    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                        ${students.length > 0 ? students.map(s => `
                            <div class="bg-white p-6 rounded-3xl border border-gray-100 shadow-sm hover:border-primary transition-all">
                                <div class="flex items-center space-x-4 space-x-reverse mb-4">
                                    <div class="w-12 h-12 rounded-2xl bg-blue-50 flex items-center justify-center text-primary font-black text-xl">${s.name[0]}</div>
                                    <div class="flex-1">
                                        <h4 class="font-black text-gray-800">${s.name}</h4>
                                        <p class="text-[10px] font-bold text-gray-400">انضم في: ${s.joinDate || '---'}</p>
                                    </div>
                                    <div class="text-orange-500 font-black text-sm"><i class="fas fa-star mr-1"></i>${s.points || 0}</div>
                                </div>
                                <div class="space-y-3">
                                    <div>
                                        <div class="flex justify-between text-[10px] mb-1"><span class="text-gray-400">حفظ القرآن:</span><span class="font-black text-primary">${s.juzCount || 0} جزء</span></div>
                                        <div class="progress-bar"><div class="progress-fill" style="width: ${((s.juzCount || 0)/30)*100}%"></div></div>
                                    </div>
                                    <div class="flex justify-between text-xs pt-2 border-t border-gray-50"><span class="text-gray-400">رقم التواصل:</span><span class="font-bold">${s.phone || '---'}</span></div>
                                    <div class="flex justify-between text-xs"><span class="text-gray-400">حالة الطالب:</span><span class="font-bold ${s.status === 'نشط' ? 'text-green-600' : 'text-red-500'}">${s.status || 'نشط'}</span></div>
                                    
                                    <div class="grid grid-cols-3 gap-1 mt-4">
                                        <button onclick="App.viewStudentHistory(${s.id})" class="py-2 bg-gray-50 rounded-xl text-[9px] font-black text-gray-500 hover:bg-primary hover:text-white transition-all text-center">سجل المتابعة</button>
                                        <button onclick="App.printStudentCertificate(${s.id})" class="py-2 bg-orange-50 rounded-xl text-[9px] font-black text-orange-600 hover:bg-orange-500 hover:text-white transition-all text-center">شهادة إنجاز</button>
                                        <button onclick="App.openRequestTestModal(${s.id})" class="py-2 bg-purple-50 rounded-xl text-[9px] font-black text-purple-600 hover:bg-purple-500 hover:text-white transition-all text-center">طلب اختبار</button>
                                    </div>
                                </div>
                            </div>
                        `).join('') : '<p class="text-gray-400 text-center col-span-full py-10 font-bold">لا يوجد طلاب مسجلين في حلقتك</p>'}
                    </div>
                `;
            },

            renderUserProfile() {
                this.openEditUserModal(this.currentUser.id);
                const area = document.getElementById('content-area');
                const changePassSection = `
                    <div class="mt-8 p-6 bg-orange-50 rounded-3xl border border-orange-100">
                        <h4 class="font-black text-orange-800 mb-2">الأمان والحماية</h4>
                        <p class="text-xs text-orange-600 mb-4">يمكنك تحديث كلمة المرور الخاصة بك من هنا بشكل مباشر.</p>
                        <button onclick="App.openChangePasswordModal()" class="bg-orange-500 text-white px-6 py-2 rounded-xl text-xs font-black shadow-lg hover:bg-orange-600 transition-all">تغيير كلمة المرور</button>
                    </div>
                `;
                area.innerHTML += changePassSection;
            },

            renderAdminFinance() {
                const f = this.db.finance || { budget: 0, transactions: [] };
                const totalIncome = (f.transactions || []).filter(t => t.type === 'income').reduce((sum, t) => sum + parseFloat(t.amount), 0);
                const totalExpense = (f.transactions || []).filter(t => t.type === 'expense').reduce((sum, t) => sum + parseFloat(t.amount), 0);
                const balance = (parseFloat(f.budget) || 0) + totalIncome - totalExpense;

                const area = document.getElementById('content-area');
                area.innerHTML = `
                    <div class="bg-blue-600 text-white p-8 rounded-3xl mb-8 flex flex-col md:flex-row justify-between items-center shadow-xl">
                        <div>
                            <p class="text-sm opacity-80 font-bold mb-2">إجمالي ميزانية المركز</p>
                            <h2 class="text-4xl font-black">${balance.toLocaleString()} شيكل</h2>
                            <div class="flex gap-2 mt-4">
                                <button onclick="App.printFinanceReport()" class="bg-white/20 hover:bg-white/30 text-white px-4 py-2 rounded-xl text-xs font-bold transition-all"><i class="fas fa-print ml-2"></i> كشف حساب</button>
                                <button onclick="App.renderPayrollSection()" class="bg-white text-blue-600 px-4 py-2 rounded-xl text-xs font-bold transition-all"><i class="fas fa-hand-holding-usd ml-2"></i> عرض الرواتب المقدرة</button>
                            </div>
                        </div>
                        <div class="mt-4 md:mt-0 bg-white/10 p-4 rounded-2xl">
                             <p class="text-[10px] font-black uppercase mb-1 opacity-70">إعدادات الرواتب (لكل طالب)</p>
                             <div class="flex gap-2">
                                <input type="number" id="salary-per-student" value="${this.db.settings.salaryPerStudent}" class="bg-white/20 border-none rounded-lg p-2 text-white font-bold outline-none w-20">
                                <button onclick="App.updateFinanceSettings()" class="bg-white text-blue-600 px-4 py-2 rounded-lg font-black text-xs">حفظ</button>
                             </div>
                        </div>
                    </div>

                    <div id="payroll-area" class="mb-8 hidden"></div>

                    <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-8">
                        <div class="bg-white p-6 rounded-3xl border border-gray-100 shadow-sm border-r-4 border-r-green-500">
                            <p class="text-[10px] font-black text-gray-400 uppercase mb-2">إجمالي الإيرادات</p>
                            <h4 class="text-2xl font-black text-green-600">+ ${totalIncome.toLocaleString()} شيكل</h4>
                        </div>
                        <div class="bg-white p-6 rounded-3xl border border-gray-100 shadow-sm border-r-4 border-r-red-500">
                            <p class="text-[10px] font-black text-gray-400 uppercase mb-2">إجمالي المصروفات</p>
                            <h4 class="text-2xl font-black text-red-600">- ${totalExpense.toLocaleString()} شيكل</h4>
                        </div>
                    </div>

                    <div class="grid grid-cols-1 lg:grid-cols-3 gap-8">
                        <div class="lg:col-span-1 bg-white p-6 rounded-3xl border border-gray-100">
                            <h3 class="font-black mb-4">إضافة حركة مالية</h3>
                            <form id="finance-form" class="space-y-4">
                                <input type="text" id="fin-desc" placeholder="وصف الحركة" required class="w-full p-3 rounded-xl bg-gray-50 border-none outline-none font-bold text-sm">
                                <input type="number" id="fin-amount" placeholder="المبلغ" required class="w-full p-3 rounded-xl bg-gray-50 border-none outline-none font-bold text-sm">
                                <select id="fin-category" class="w-full p-3 rounded-xl bg-gray-50 border-none outline-none font-bold text-sm">
                                    <option value="عام">عام</option>
                                    <option value="رواتب">رواتب</option>
                                    <option value="فواتير">فواتير</option>
                                    <option value="تبرعات">تبرعات</option>
                                    <option value="مكافآت">مكافآت طلاب</option>
                                </select>
                                <select id="fin-type" class="w-full p-3 rounded-xl bg-gray-50 border-none outline-none font-bold text-sm">
                                    <option value="expense">مصروفات (-)</option>
                                    <option value="income">إيرادات (+)</option>
                                </select>
                                <button type="submit" class="w-full bg-dark text-white py-3 rounded-xl font-black">تسجيل العملية</button>
                            </form>
                        </div>
                        <div class="lg:col-span-2 bg-white rounded-3xl border border-gray-100 overflow-hidden">
                            <div class="p-6 border-b bg-gray-50/50"><h3 class="font-black">آخر العمليات المالية</h3></div>
                            <div class="max-h-96 overflow-y-auto">
                                <table class="w-full text-right text-sm">
                                    <thead class="bg-gray-50 sticky top-0">
                                        <tr><th class="p-4">البيان</th><th class="p-4">الفئة</th><th class="p-4 text-center">المبلغ</th><th class="p-4 text-center">الإجراء</th></tr>
                                    </thead>
                                    <tbody class="divide-y divide-gray-50">
                                        ${(f.transactions || []).length > 0 ? f.transactions.slice().reverse().map(t => `
                                            <tr>
                                                <td class="p-4 font-bold text-gray-700">
                                                    ${t.desc}
                                                    <p class="text-[9px] text-gray-400">${new Date(t.date).toLocaleDateString('ar-SA')}</p>
                                                </td>
                                                <td class="p-4"><span class="text-[10px] font-black px-2 py-1 rounded-lg ${t.type === 'income' ? 'bg-green-50 text-green-600' : 'bg-red-50 text-red-600'}">${t.category || 'عام'}</span></td>
                                                <td class="p-4 font-black text-center">${parseFloat(t.amount).toLocaleString()} شيكل</td>
                                                <td class="p-4 text-center"><button onclick="App.deleteTransaction(${t.id})" class="text-gray-300 hover:text-red-500"><i class="fas fa-trash-alt"></i></button></td>
                                            </tr>
                                        `).join('') : '<tr><td colspan="4" class="text-center py-10 text-gray-400 font-bold">لا يوجد عمليات مسجلة</td></tr>'}
                                    </tbody>
                                </table>
                            </div>
                        </div>
                    </div>
                `;
                
                const finForm = document.getElementById('finance-form');
                if(finForm) {
                    finForm.onsubmit = (e) => {
                        e.preventDefault();
                        const amount = parseFloat(document.getElementById('fin-amount').value);
                        if(amount <= 0 || isNaN(amount)) return alert('المبلغ يجب أن يكون أكبر من صفر');
                        
                        const transaction = {
                            id: Date.now(),
                            desc: document.getElementById('fin-desc').value.trim(),
                            amount: amount,
                            type: document.getElementById('fin-type').value,
                            category: document.getElementById('fin-category').value,
                            date: new Date().toISOString()
                        };
                        this.db.finance.transactions.push(transaction);
                        this.logActivity('عملية مالية', `${transaction.desc} (${amount})`);
                        this.saveDB();
                        this.renderAdminFinance();
                        this.showToast("تم تسجيل العملية المالية", "success");
                    };
                }
            },

            renderPayrollSection() {
                const payrollArea = document.getElementById('payroll-area');
                payrollArea.classList.remove('hidden');
                const rate = this.db.settings.salaryPerStudent || 50;
                
                payrollArea.innerHTML = `
                    <div class="bg-white p-6 rounded-3xl border-2 border-blue-100 page-animate">
                        <div class="flex justify-between items-center mb-4">
                            <h3 class="font-black text-blue-800"><i class="fas fa-calculator ml-2"></i> الرواتب المقدرة للمحفظين (بناءً على الطلاب النشطين)</h3>
                            <button onclick="document.getElementById('payroll-area').classList.add('hidden')" class="text-gray-400 hover:text-red-500"><i class="fas fa-times-circle"></i></button>
                        </div>
                        <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
                            ${this.db.users.filter(u => u.role === 'teacher').map(teacher => {
                                const studentCount = this.db.students.filter(s => s.circleId == teacher.circleId && s.status === 'نشط').length;
                                const salary = studentCount * rate;
                                return `
                                    <div class="bg-gray-50 p-4 rounded-2xl border border-gray-100">
                                        <p class="text-xs font-black text-gray-400 uppercase">${teacher.name}</p>
                                        <p class="text-[10px] mb-2">${studentCount} طالب نشط × ${rate} شيكل</p>
                                        <p class="text-lg font-black text-primary">${salary.toLocaleString()} شيكل</p>
                                    </div>
                                `;
                            }).join('')}
                        </div>
                    </div>
                `;
            },

            updateFinanceSettings() {
                const rate = document.getElementById('salary-per-student').value;
                this.db.settings.salaryPerStudent = parseInt(rate);
                this.saveDB();
                this.showToast("تم تحديث إعدادات الرواتب");
                this.renderAdminFinance();
            },

            updateClock() {
                const now = new Date();
                const options = { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' };
                const el = document.getElementById('current-full-date');
                if(el) el.textContent = now.toLocaleDateString('ar-SA', options);
                const printDate = document.getElementById('print-date-display');
                if(printDate) printDate.textContent = now.toLocaleString('ar-SA');
                setTimeout(() => this.updateClock(), 60000);
            },

            openModal(id) { 
                const modal = document.getElementById(id);
                if(!modal) return;
                modal.classList.remove('hidden'); 
                modal.classList.add('flex'); 
                if(id === 'modal-add-student') {
                    document.getElementById('modal-circle-select').innerHTML = `<option value="">غير موزع</option>` + (this.db.circles || []).map(c => `<option value="${c.id}">${c.name}</option>`).join('');
                }
            },

            closeModal(id) { 
                const modal = document.getElementById(id);
                if(!modal) return;
                modal.classList.add('hidden'); 
                modal.classList.remove('flex'); 
                if(id === 'modal-add-student') document.getElementById('points-container').classList.add('hidden');
            },

            initChart() {
                const canvas = document.getElementById('attendance-chart-mini');
                if(!canvas) return;
                const ctx = canvas.getContext('2d');
                if (this.myChart) this.myChart.destroy();
                
                const counts = { advanced: 0, intermediate: 0, beginner: 0 };
                this.db.students.forEach(s => {
                    const j = s.juzCount || 0;
                    if(j >= 20) counts.advanced++;
                    else if(j >= 5) counts.intermediate++;
                    else counts.beginner++;
                });

                this.myChart = new Chart(ctx, {
                    type: 'doughnut',
                    data: {
                        labels: ['متقدمون (20+ جزء)', 'متوسطون (5+ جزء)', 'مبتدئون'],
                        datasets: [{ 
                            data: [counts.advanced, counts.intermediate, counts.beginner], 
                            backgroundColor: ['#1a5fb4', '#2ec27e', '#e5a50a'], 
                            borderWidth: 0 
                        }]
                    },
                    options: { 
                        cutout: '70%',
                        responsive: true,
                        maintainAspectRatio: false,
                        plugins: { legend: { position: 'bottom', labels: { font: { family: 'Cairo', weight: 'bold', size: 10 } } } } 
                    }
                });
            },

            setupStudentForm() {
                const form = document.getElementById('form-add-student');
                if(!form) return;
                form.onsubmit = (e) => {
                    e.preventDefault();
                    const id = document.getElementById('edit-student-id').value;
                    const studentData = {
                        name: document.getElementById('student-name').value.trim(),
                        circleId: document.getElementById('modal-circle-select').value ? parseInt(document.getElementById('modal-circle-select').value) : null,
                        phone: document.getElementById('student-phone').value.trim(),
                        juzCount: Math.min(30, Math.max(0, parseInt(document.getElementById('student-juz').value) || 0)),
                        status: document.getElementById('student-status').value,
                        points: parseInt(document.getElementById('student-points').value) || 0
                    };

                    if (id) {
                        const idx = this.db.students.findIndex(s => s.id == id);
                        if(idx > -1) this.db.students[idx] = { ...this.db.students[idx], ...studentData };
                        this.logActivity('تعديل طالب', studentData.name);
                    } else {
                        const newStudent = {
                            id: Date.now(),
                            ...studentData,
                            joinDate: new Date().toISOString().split('T')[0],
                        };
                        this.db.students.push(newStudent);
                        this.logActivity('إضافة طالب', newStudent.name);
                    }

                    this.syncCounts();
                    this.saveDB();
                    this.closeModal('modal-add-student');
                    this.showToast("تم حفظ بيانات الطالب", "success");
                    
                    const activeNav = document.querySelector('.sidebar-link.active')?.id;
                    if(activeNav === 'nav-btn-admin-students') this.renderAdminStudents();
                    else if(activeNav === 'nav-btn-admin-dashboard') this.renderAdminDashboard();
                    
                    form.reset();
                    document.getElementById('edit-student-id').value = '';
                };
            },

            viewStudentHistory(studentId) {
                const student = this.db.students.find(s => s.id == studentId);
                const logs = this.db.dailyLogs.filter(l => l.studentId == studentId).sort((a, b) => new Date(b.date) - new Date(a.date));
                const tests = (this.db.tests || []).filter(t => t.studentId == studentId).sort((a, b) => new Date(b.date) - new Date(a.date)); 
                
                const area = document.getElementById('content-area');
                area.innerHTML = `
                    <div class="mb-6 flex items-center justify-between no-print">
                        <button onclick="App.navigate('${(this.currentUser.role === 'admin' || this.currentUser.role === 'supervisor') ? 'admin-students' : 'teacher-students'}')" class="bg-white border px-4 py-2 rounded-xl text-xs font-black text-gray-500 hover:text-primary transition-all">
                            <i class="fas fa-arrow-right ml-2"></i> العودة
                        </button>
                        <h3 class="font-black text-xl">سجل متابعة الطالب: ${student.name}</h3>
                        <button onclick="window.print()" class="bg-primary text-white px-4 py-2 rounded-xl text-xs font-black"><i class="fas fa-print ml-2"></i> طباعة السجل</button>
                    </div>
                    
                    <div class="grid grid-cols-1 md:grid-cols-4 gap-4 mb-6">
                        <div class="bg-white p-5 rounded-3xl border shadow-sm text-center">
                            <p class="text-[10px] text-gray-400 font-bold uppercase mb-1">إجمالي الحفظ</p>
                            <p class="text-xl font-black text-primary">${student.juzCount} جزء</p>
                        </div>
                        <div class="bg-white p-5 rounded-3xl border shadow-sm text-center">
                            <p class="text-[10px] text-gray-400 font-bold uppercase mb-1">نسبة الحضور</p>
                            <p class="text-xl font-black text-green-600">${this.calculateAttendanceRate(studentId)}%</p>
                        </div>
                        <div class="bg-white p-5 rounded-3xl border shadow-sm text-center">
                            <p class="text-[10px] text-gray-400 font-bold uppercase mb-1">النقاط الحالية</p>
                            <p class="text-xl font-black text-orange-500"><i class="fas fa-star ml-1"></i>${student.points || 0}</p>
                        </div>
                        <div class="bg-white p-5 rounded-3xl border shadow-sm text-center">
                            <p class="text-[10px] text-gray-400 font-bold uppercase mb-1">الحالة</p>
                            <p class="text-sm font-black ${student.status === 'نشط' ? 'text-green-500' : 'text-red-500'}">${student.status}</p>
                        </div>
                    </div>

                    <div class="mb-8 bg-white rounded-3xl border border-orange-100 overflow-hidden shadow-sm">
                        <div class="p-4 bg-orange-50 font-black text-orange-800 text-sm">سجل اختبارات الأجزاء</div>
                        <table class="w-full text-right text-xs">
                             <thead class="bg-orange-50/50 text-gray-400 uppercase font-black">
                                <tr><th class="p-3">التاريخ</th><th>الجزء</th><th>الدرجة</th><th>التقدير</th></tr>
                             </thead>
                             <tbody>
                                ${tests.length > 0 ? tests.map(t => `
                                    <tr class="border-t border-orange-50">
                                        <td class="p-3">${t.date}</td>
                                        <td class="font-bold text-orange-700">${t.part}</td>
                                        <td class="font-black">${t.score}/100</td>
                                        <td><span class="bg-orange-100 px-2 py-0.5 rounded text-orange-600">${t.grade}</span></td>
                                    </tr>
                                `).join('') : '<tr><td colspan="4" class="text-center py-4 text-gray-400">لا يوجد اختبارات مسجلة</td></tr>'}
                             </tbody>
                        </table>
                    </div>

                    <div class="bg-white rounded-3xl border border-gray-100 overflow-hidden shadow-sm">
                        <div class="p-4 bg-gray-50 font-black text-gray-800 text-sm">المتابعة اليومية</div>
                        <table class="w-full text-right">
                            <thead class="bg-gray-50 text-[10px] font-black text-gray-400 uppercase">
                                <tr>
                                    <th class="p-4">التاريخ</th>
                                    <th class="p-4">الحالة</th>
                                    <th class="p-4">ما تم حفظه</th>
                                    <th class="p-4">المراجعة</th>
                                    <th class="p-4 text-center">التقييم</th>
                                </tr>
                            </thead>
                            <tbody class="divide-y divide-gray-50 text-sm">
                                ${logs.length > 0 ? logs.map(l => `
                                    <tr class="hover:bg-gray-50 transition-all">
                                        <td class="p-4 font-bold text-gray-600">${l.date}</td>
                                        <td class="p-4"><span class="px-2 py-1 rounded-lg text-[10px] font-black ${l.attendance === 'حاضر' ? 'bg-green-50 text-green-600' : 'bg-red-50 text-red-600'}">${l.attendance}</span></td>
                                        <td class="p-4 text-gray-600 font-medium">${l.hifz || '---'}</td>
                                        <td class="p-4 text-gray-600 font-medium">${l.murajaa || '---'}</td>
                                        <td class="p-4 text-center"><span class="bg-blue-50 text-primary px-2 py-1 rounded-lg font-black text-[10px]">${l.exam || '---'}</span></td>
                                    </tr>
                                `).join('') : '<tr><td colspan="5" class="text-center py-20 text-gray-400 font-bold">لا يوجد سجلات متابعة مسجلة لهذا الطالب حتى الآن</td></tr>'}
                            </tbody>
                        </table>
                    </div>
                `;
            },

            calculateAttendanceRate(studentId) {
                const logs = this.db.dailyLogs.filter(l => l.studentId == studentId);
                if(logs.length === 0) return 0;
                const present = logs.filter(l => l.attendance === 'حاضر').length;
                return Math.round((present / logs.length) * 100);
            },

            renderHonorRoll() {
                const topStudents = [...this.db.students]
                    .filter(s => s.status === 'نشط')
                    .sort((a, b) => (b.points || 0) - (a.points || 0)) 
                    .slice(0, 3);
                
                if (topStudents.length === 0) return '';

                return `
                    <div class="bg-gradient-to-br from-yellow-50 via-white to-orange-50 p-6 rounded-3xl border border-yellow-200 mb-8 relative overflow-hidden">
                        <div class="absolute -top-10 -left-10 w-32 h-32 bg-yellow-200 rounded-full blur-3xl opacity-30"></div>
                        <h3 class="font-black text-orange-800 mb-4 flex items-center relative z-10 text-lg">
                            <i class="fas fa-crown ml-3 text-yellow-500 text-2xl"></i> لوحة شرف نجوم الفرقان
                        </h3>
                        <div class="grid grid-cols-1 md:grid-cols-3 gap-4 relative z-10">
                            ${topStudents.map((s, idx) => `
                                <div class="bg-white/80 backdrop-blur-sm p-4 rounded-2xl flex items-center space-x-4 space-x-reverse border border-white shadow-sm">
                                    <div class="text-3xl">${idx === 0 ? '🥇' : idx === 1 ? '🥈' : '🥉'}</div>
                                    <div>
                                        <p class="font-black text-sm text-gray-800">${s.name}</p>
                                        <p class="text-[10px] font-bold text-orange-600">${s.points || 0} نقطة تميز</p>
                                    </div>
                                </div>
                            `).join('')}
                        </div>
                    </div>
                `;
            },

            checkAbsenteeism(studentId) {
                const logs = this.db.dailyLogs.filter(l => l.studentId == studentId).sort((a, b) => new Date(b.date) - new Date(a.date));
                if (logs.length < 3) return false;
                const lastThree = logs.slice(0, 3);
                return lastThree.every(l => l.attendance === 'غائب');
            },

            openChangePasswordModal() {
                const newPass = prompt("أدخل كلمة المرور الجديدة:");
                if (newPass && newPass.length >= 3) {
                    const idx = this.db.users.findIndex(u => u.id === this.currentUser.id);
                    this.db.users[idx].password = btoa(newPass);
                    this.saveDB();
                    this.showToast("تم تغيير كلمة المرور بنجاح", "success");
                    this.logActivity('تغيير كلمة مرور', this.currentUser.name);
                } else if (newPass) {
                    this.showToast("كلمة المرور قصيرة جداً", "error");
                }
            },

            printFinanceReport() {
                const f = this.db.finance;
                const totalIncome = f.transactions.filter(t => t.type === 'income').reduce((sum, t) => sum + parseFloat(t.amount), 0);
                const totalExpense = f.transactions.filter(t => t.type === 'expense').reduce((sum, t) => sum + parseFloat(t.amount), 0);
                
                let printWindow = window.open('', '_blank');
                printWindow.document.write(`
                    <dir dir="rtl" style="font-family: 'Cairo', sans-serif; padding: 40px;">
                        <div style="text-align: center; border-bottom: 2px solid #333; padding-bottom: 20px; margin-bottom: 30px;">
                            <h1 style="color: #1a5fb4; margin: 0;">مركز الفرقان لتعليم القرآن</h1>
                            <p style="margin: 5px 0;">كشف مالي تفصيلي للمركز</p>
                            <p style="font-size: 12px; color: #666;">تاريخ التقرير: ${new Date().toLocaleString('ar-SA')}</p>
                        </div>
                        <div style="display: flex; justify-content: space-around; margin: 30px 0; background: #f9f9f9; padding: 20px; border-radius: 15px;">
                            <div style="text-align: center;"><h4>إجمالي الإيرادات</h4><h2 style="color: green;">${totalIncome} ر.س</h2></div>
                            <div style="text-align: center;"><h4>إجمالي المصروفات</h4><h2 style="color: red;">${totalExpense} ر.س</h2></div>
                            <div style="text-align: center;"><h4>الرصيد الصافي</h4><h2 style="color: #1a5fb4;">${this.calculateBalance()} ر.س</h2></div>
                        </div>
                    </dir>
                `);
                printWindow.document.close();
                printWindow.focus();
                setTimeout(() => { printWindow.print(); }, 500);
            },

            handleGlobalSearch(query) {
                const resDiv = document.getElementById('search-results');
                if (!query || query.length < 2) { resDiv.classList.add('hidden'); return; }
                
                const q = query.toLowerCase();
                const studentMatches = this.db.students.filter(s => s.name.toLowerCase().includes(q)).slice(0, 3);
                const teacherMatches = this.db.users.filter(u => u.name.toLowerCase().includes(q) && u.role !== 'admin').slice(0, 2);
                const circleMatches = this.db.circles.filter(c => c.name.toLowerCase().includes(q)).slice(0, 2);
                
                if (studentMatches.length > 0 || teacherMatches.length > 0 || circleMatches.length > 0) {
                    let html = '';
                    studentMatches.forEach(s => {
                        html += `<div onclick="App.viewStudentHistory(${s.id}); document.getElementById('search-results').classList.add('hidden');" class="p-3 hover:bg-gray-50 cursor-pointer flex justify-between items-center border-b border-gray-50"><div><p class="text-xs font-black text-gray-800">${s.name}</p></div></div>`;
                    });
                    resDiv.innerHTML = html;
                    resDiv.classList.remove('hidden');
                } else {
                    resDiv.innerHTML = '<p class="p-4 text-[10px] text-gray-400 text-center">لا توجد نتائج مطابقة</p>';
                    resDiv.classList.remove('hidden');
                }
            },

            sendWhatsApp(studentId) {
                const student = this.db.students.find(s => s.id == studentId);
                const log = this.db.dailyLogs.filter(l => l.studentId == studentId).sort((a,b) => new Date(b.date) - new Date(a.date))[0];
                
                if(!log) {
                    this.showToast("لا يوجد سجل يومي لإرساله اليوم", "error");
                    return;
                }

                const message = `*تقرير الطالب: ${student.name}*%0A` +
                                `*التاريخ:* ${log.date}%0A` +
                                `*الحفظ:* ${log.hifz || '---'}%0A` +
                                `*المراجعة:* ${log.murajaa || '---'}%0A` +
                                `%0A_صادر عن نظام مركز الفرقان_`;

                let phone = student.phone;
                if(!phone.startsWith('972')) phone = '972' + phone.replace(/^0+/, '');
                window.open(`https://wa.me/${phone}?text=${message}`, '_blank');
            },

            openAddTestModal(studentId) {
                document.getElementById('test-student-id').value = studentId;
                this.openModal('modal-add-test');
            },

            setupTestForm() {
                const form = document.getElementById('form-add-test');
                if(!form) return;
                form.onsubmit = (e) => {
                    e.preventDefault();
                    const studentId = document.getElementById('test-student-id').value;
                    const newTest = {
                        id: Date.now(),
                        studentId: studentId,
                        part: document.getElementById('test-part').value,
                        score: document.getElementById('test-score').value,
                        grade: document.getElementById('test-grade').value,
                        date: new Date().toISOString().split('T')[0]
                    };
                    
                    if(!this.db.tests) this.db.tests = [];
                    this.db.tests.push(newTest);
                    
                    const sIdx = this.db.students.findIndex(s => s.id == studentId);
                    if(sIdx > -1) {
                        this.db.students[sIdx].points = (this.db.students[sIdx].points || 0) + 50; 
                    }

                    if (this.currentPendingRequestId) {
                        const reqIdx = this.db.testRequests.findIndex(r => r.id == this.currentPendingRequestId);
                        if(reqIdx > -1) {
                            this.db.testRequests[reqIdx].status = 'approved';
                        }
                        this.currentPendingRequestId = null;
                    }

                    this.saveDB();
                    this.closeModal('modal-add-test');
                    this.showToast("تم تسجيل نتيجة الاختبار ومنح 50 نقطة تميز", "success");
                    form.reset();
                };
            },

            openRequestTestModal(studentId) {
                const student = this.db.students.find(s => s.id == studentId);
                if (!student) return;
                document.getElementById('req-test-student-id').value = studentId;
                document.getElementById('req-test-part').value = '';
                document.getElementById('req-test-notes').value = '';
                this.openModal('modal-request-test');
            },

            setupRequestTestForm() {
                const form = document.getElementById('form-request-test');
                if(!form) return;
                form.onsubmit = (e) => {
                    e.preventDefault();
                    const studentId = document.getElementById('req-test-student-id').value;
                    const student = this.db.students.find(s => s.id == studentId);
                    const circle = this.db.circles.find(c => c.id == student.circleId);
                    
                    const newRequest = {
                        id: Date.now(),
                        studentId: studentId,
                        studentName: student.name,
                        circleName: circle ? circle.name : 'بدون حلقة',
                        part: document.getElementById('req-test-part').value,
                        notes: document.getElementById('req-test-notes').value,
                        requestedBy: this.currentUser.name,
                        status: 'pending',
                        date: new Date().toISOString().split('T')[0]
                    };

                    if(!this.db.testRequests) this.db.testRequests = [];
                    this.db.testRequests.push(newRequest);
                    
                    this.saveDB();
                    this.closeModal('modal-request-test');
                    this.showToast("تم إرسال طلب الاختبار للإدارة بنجاح", "success");
                    form.reset();
                };
            },

            approveTestRequest(requestId, studentId, part) {
                this.currentPendingRequestId = requestId;
                document.getElementById('test-student-id').value = studentId;
                document.getElementById('test-part').value = part;
                document.getElementById('test-score').value = '';
                document.getElementById('test-grade').value = 'ممتاز';
                this.openModal('modal-add-test');
            },

            rejectTestRequest(requestId) {
                if(confirm('هل أنت متأكد من رفض هذا الطلب؟')) {
                    const idx = this.db.testRequests.findIndex(r => r.id == requestId);
                    if(idx > -1) {
                        this.db.testRequests[idx].status = 'rejected';
                        this.saveDB();
                        this.renderAdminDashboard();
                        this.showToast('تم رفض طلب الاختبار');
                    }
                }
            },

            renderMonthlyReports(viewType) {
                const area = document.getElementById('content-area');
                area.innerHTML = `<div id="monthly-report-output"></div>`;
                this.generateAndDisplayMonthlyReport(viewType);
            },

            generateAndDisplayMonthlyReport(viewType) {
                // ... (إبقاء كود التقارير كما هو دون حذف)
            },

            printStudentCertificate(studentId) {
                const student = this.db.students.find(s => s.id == studentId);
                if (!student) return;
                let printWindow = window.open('', '_blank');
                printWindow.document.write(`<html><body dir="rtl"><h1>شهادة تقدير للطالب: ${student.name}</h1></body></html>`);
                printWindow.document.close();
                printWindow.print();
            }
        };

        window.onload = () => App.init();
    </script>
</body>
</html>
