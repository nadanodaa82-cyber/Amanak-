<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>منصة أمانك | AMANAK Platform</title>
    <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@300;400;500;700;900&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        :root {
            --main-purple: #5c4db1; 
            --light-purple: #a74eb5;
            --blue-gradient: linear-gradient(135deg, #25aae1 0%, #a74eb5 100%);
            --soft-bg: #f8f9ff;
            --text-dark: #2d2d5f;
            --success: #2ecc71;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Tajawal', sans-serif; }
        body { background-color: var(--soft-bg); color: var(--text-dark); scroll-behavior: smooth; overflow-x: hidden; }

        /* Navigation */
        header {
            background: white; padding: 15px 5%; display: flex; justify-content: space-between;
            align-items: center; position: sticky; top: 0; z-index: 1000; box-shadow: 0 4px 20px rgba(0,0,0,0.05);
        }
        .nav-links { display: flex; gap: 15px; }
        .nav-links a { text-decoration: none; color: var(--text-dark); font-weight: 700; cursor: pointer; font-size: 13px; transition: 0.3s; padding: 8px 12px; border-radius: 8px; }
        .nav-links a:hover, .nav-links a.active { color: var(--main-purple); background: #f0eeff; }

        .logo-container { display: flex; align-items: center; gap: 10px; cursor: pointer; }
        .logo-text { display: flex; flex-direction: column; text-align: left; }
        .logo-text span:first-child { font-size: 22px; font-weight: 900; background: var(--blue-gradient); -webkit-background-clip: text; -webkit-text-fill-color: transparent; line-height: 1; }
        .logo-text span:last-child { font-size: 10px; font-weight: bold; color: var(--light-purple); letter-spacing: 1px; }

        .container { max-width: 1150px; margin: 0 auto; padding: 20px; min-height: 80vh; }

        /* Pages System */
        .page { display: none; animation: fadeIn 0.5s ease-out; }
        .page.active { display: block; }
        @keyframes fadeIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }

        /* Hero Section */
        .hero-section { display: grid; grid-template-columns: 1.2fr 0.8fr; gap: 40px; padding: 60px 0; align-items: center; }
        .hero-text h1 { font-size: 40px; font-weight: 900; line-height: 1.3; color: #1a1a4b; }
        .hero-text h1 span { color: var(--main-purple); background: var(--blue-gradient); -webkit-background-clip: text; -webkit-text-fill-color: transparent; }
        .hero-text p { font-size: 18px; color: #555; margin: 20px 0 35px; line-height: 1.8; }
        
        .btn-primary { background: var(--blue-gradient); color: white; padding: 12px 25px; border-radius: 12px; border: none; font-weight: 700; cursor: pointer; transition: 0.3s; display: inline-flex; align-items: center; gap: 8px; justify-content: center; }
        .btn-primary:hover { opacity: 0.9; transform: translateY(-2px); }
        .btn-outline { background: white; border: 2px solid var(--main-purple); color: var(--main-purple); padding: 12px 25px; border-radius: 12px; font-weight: 700; cursor: pointer; transition: 0.3s; }

        .hero-visual { position: relative; text-align: center; }
        .main-circle { width: 250px; height: 250px; background: var(--blue-gradient); border-radius: 50%; display: inline-flex; align-items: center; justify-content: center; position: relative; box-shadow: 0 20px 40px rgba(92, 77, 177, 0.2); }
        .main-circle i { font-size: 100px; color: white; }

        /* Shared Components */
        .card { background: white; border-radius: 20px; padding: 25px; box-shadow: 0 10px 30px rgba(0,0,0,0.03); margin-bottom: 25px; border: 1px solid #f0f0f0; }
        .section-title { font-size: 22px; font-weight: 900; margin-bottom: 25px; border-right: 5px solid var(--main-purple); padding-right: 15px; display: flex; align-items: center; gap: 10px; color: var(--text-dark); }
        
        .features-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 20px; margin: 30px 0; }
        .f-card { background: white; padding: 25px; border-radius: 20px; text-align: center; transition: 0.3s; border: 1px solid #eee; cursor: pointer; }
        .f-card:hover { transform: translateY(-5px); border-color: var(--main-purple); box-shadow: 0 15px 30px rgba(0,0,0,0.05); }

        .stats-container { display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 20px; margin-bottom: 30px; }
        .stat-box { padding: 20px; border-radius: 15px; color: white; text-align: center; }

        /* Tables & Forms */
        table { width: 100%; border-collapse: collapse; margin-top: 15px; }
        th { background: #f8f9ff; padding: 15px; text-align: right; font-size: 14px; color: var(--main-purple); }
        td { padding: 15px; border-bottom: 1px solid #eee; font-size: 14px; }
        
        .form-group { text-align: right; margin-bottom: 15px; }
        label { display: block; margin-bottom: 8px; font-weight: 700; font-size: 13px; }
        input, select, textarea { width: 100%; padding: 12px; border-radius: 10px; border: 1px solid #eee; background: #fafafa; outline: none; font-family: 'Tajawal'; }

        .status-badge { padding: 4px 10px; border-radius: 15px; font-size: 11px; font-weight: bold; background: #eef2ff; color: var(--main-purple); }

        footer { text-align: center; padding: 30px; color: #888; font-size: 12px; border-top: 1px solid #eee; margin-top: 50px; }

        @media (max-width: 992px) {
            .hero-section, .features-grid { grid-template-columns: 1fr; text-align: center; }
            .hero-text h1 { font-size: 30px; }
            header { flex-direction: column; gap: 15px; }
            .nav-links { flex-wrap: wrap; justify-content: center; }
        }
    </style>
</head>
<body>

    <header>
        <div class="auth-btns">
            <button class="btn-outline" style="padding: 5px 15px; font-size: 12px;" onclick="showPage('login-page')">تسجيل الدخول</button>
        </div>
        <nav class="nav-links">
            <a onclick="showPage('home-page')" id="nav-home" class="active">الرئيسية</a>
            <a onclick="showPage('booking-page')" id="nav-booking">حجز استشارة</a>
            <a onclick="showPage('dashboard-page')" id="nav-dashboard">لوحة التحكم</a>
            <a onclick="showPage('inquiries-page')" id="nav-inquiries">الاستعلامات</a>
            <a onclick="showPage('reports-page')" id="nav-reports">التقارير</a>
        </nav>
        <div class="logo-container" onclick="showPage('home-page')">
            <div class="logo-text">
                <span>أمانك</span>
                <span>AMANAK</span>
            </div>
            <i class="fas fa-hands-helping" style="font-size: 28px; color: var(--main-purple);"></i>
        </div>
    </header>

    <div class="container">

        <div id="home-page" class="page active">
            <section class="hero-section">
                <div class="hero-text">
                    <div style="color: var(--light-purple); font-weight: 800; margin-bottom: 10px;">📍 جامعة طيبة - عمادة شؤون الطلاب</div>
                    <h1>مساحتكِ الآمنة لـ <span>حياة جامعية</span> هادئة</h1>
                    <p>منصة أمانكِ توفر لكِ الدعم النفسي والاجتماعي بخصوصية تامة. احجزي استشارتكِ، وطوري مهاراتكِ في بيئة داعمة ومحفزة للنجاح.</p>
                    <div style="display:flex; gap:12px;">
                        <button class="btn-primary" onclick="showPage('booking-page')">ابدئي حجز استشارة</button>
                        <button class="btn-outline" onclick="showPage('inquiries-page')">لديكِ استفسار؟</button>
                    </div>
                </div>
                <div class="hero-visual">
                    <div class="main-circle"><i class="fas fa-heartbeat"></i></div>
                </div>
            </section>

            <div class="features-grid">
                <div class="f-card" onclick="showPage('booking-page')">
                    <i class="fas fa-calendar-alt" style="font-size: 30px; color: var(--main-purple); margin-bottom: 15px;"></i>
                    <h3>حجز مواعيد</h3>
                    <p>اختاري الوقت المناسب لكِ بكل مرونة.</p>
                </div>
                <div class="f-card" onclick="showPage('inquiries-page')">
                    <i class="fas fa-comment-dots" style="font-size: 30px; color: #d63384; margin-bottom: 15px;"></i>
                    <h3>استعلامات سريعة</h3>
                    <p>تواصل مباشر مع فريق الدعم الفني.</p>
                </div>
                <div class="f-card" onclick="showPage('reports-page')">
                    <i class="fas fa-chart-line" style="font-size: 30px; color: #00b894; margin-bottom: 15px;"></i>
                    <h3>تقارير التقدم</h3>
                    <p>تابعي مستوى تحسنكِ بشكل دوري.</p>
                </div>
            </div>
        </div>

        <div id="booking-page" class="page">
            <div style="max-width: 600px; margin: 0 auto;" class="card">
                <span class="section-title"><i class="fas fa-pen-fancy"></i> طلب موعد جديد</span>
                <div class="form-group">
                    <label>نوع الاستشارة</label>
                    <select id="cons-type">
                        <option>نفسية</option>
                        <option>اجتماعية</option>
                        <option>أكاديمية</option>
                    </select>
                </div>
                <div style="display:grid; grid-template-columns: 1fr 1fr; gap:15px;">
                    <div class="form-group"><label>التاريخ</label><input type="date" id="cons-date"></div>
                    <div class="form-group"><label>الوقت</label><input type="time" id="cons-time"></div>
                </div>
                <div class="form-group">
                    <label>ملاحظات إضافية</label>
                    <textarea rows="3" placeholder="اشرحي باختصار سبب الطلب..."></textarea>
                </div>
                <button class="btn-primary" style="width:100%;" onclick="confirmBooking()">تأكيد وإرسال الطلب</button>
            </div>
        </div>

        <div id="dashboard-page" class="page">
            <div class="stats-container">
                <div class="stat-box" style="background:var(--main-purple);"><h3>05</h3><p>جلسات سابقة</p></div>
                <div class="stat-box" style="background:#25aae1;"><h3>01</h3><p>موعد قادم</p></div>
                <div class="stat-box" style="background:var(--light-purple);"><h3>ممتاز</h3><p>تقييم الحالة</p></div>
            </div>
            <div class="card">
                <span class="section-title"><i class="fas fa-history"></i> الجلسات القادمة</span>
                <table id="sessions-table">
                    <thead>
                        <tr>
                            <th>نوع الجلسة</th>
                            <th>التاريخ والوقت</th>
                            <th>الحالة</th>
                        </tr>
                    </thead>
                    <tbody id="sessions-list">
                        <tr>
                            <td>استشارة نفسية</td>
                            <td>12 مايو 2026 | 09:00 ص</td>
                            <td><span class="status-badge">مؤكد</span></td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>

        <div id="inquiries-page" class="page">
            <span class="section-title"><i class="fas fa-question-circle"></i> إدارة الاستعلامات</span>
            <div class="card">
                <div style="display: flex; gap: 10px; margin-bottom: 20px;">
                    <input type="text" placeholder="بحث برقم التذكرة أو الموضوع..." style="flex: 2;">
                    <button class="btn-primary">بحث</button>
                </div>
                <table>
                    <thead>
                        <tr>
                            <th>رقم التذكرة</th>
                            <th>الموضوع</th>
                            <th>التاريخ</th>
                            <th>الحالة</th>
                            <th>الإجراء</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>#INQ-990</td>
                            <td>استفسار عن دورة الثقة بالنفس</td>
                            <td>01 مايو 2026</td>
                            <td><span class="status-badge" style="background:#fff3cd; color:#856404;">قيد المعالجة</span></td>
                            <td><button class="btn-outline" style="padding: 5px 10px; font-size: 12px;">عرض</button></td>
                        </tr>
                        <tr>
                            <td>#INQ-985</td>
                            <td>تغيير الأخصائية المسؤولة</td>
                            <td>28 أبريل 2026</td>
                            <td><span class="status-badge" style="background:#d1e7dd; color:#0f5132;">مكتمل</span></td>
                            <td><button class="btn-outline" style="padding: 5px 10px; font-size: 12px;">عرض</button></td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>

        <div id="reports-page" class="page">
            <span class="section-title"><i class="fas fa-file-signature"></i> إدارة التقارير</span>
            <div class="stats-container">
                <div class="stat-box" style="background: linear-gradient(135deg, #6a11cb 0%, #2575fc 100%);">
                    <h3>08</h3>
                    <p>تقارير تم إصدارها</p>
                </div>
                <div class="stat-box" style="background: linear-gradient(135deg, #11998e 0%, #38ef7d 100%);">
                    <h3>92%</h3>
                    <p>نسبة التحسن العام</p>
                </div>
            </div>
            <div class="card">
                <h3>تصدير تقرير مفصل</h3>
                <p style="color: #666; margin-bottom: 20px; font-size: 14px;">اختاري الفترة الزمنية لتوليد تقرير شامل عن النشاط والحالة النفسية.</p>
                <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 15px; margin-bottom: 20px;">
                    <div class="form-group">
                        <label>من تاريخ</label>
                        <input type="date">
                    </div>
                    <div class="form-group">
                        <label>إلى تاريخ</label>
                        <input type="date">
                    </div>
                </div>
                <button class="btn-primary" style="width: 100%;"><i class="fas fa-file-pdf"></i> تحميل التقرير بصيغة PDF</button>
            </div>
        </div>

        <div id="login-page" class="page">
            <div style="max-width: 400px; margin: 40px auto;" class="card">
                <h2 style="text-align:center; margin-bottom:20px; color: var(--main-purple);">تسجيل الدخول</h2>
                <div class="form-group"><label>البريد الجامعي</label><input type="email" placeholder="example@taibahu.edu.sa"></div>
                <div class="form-group"><label>كلمة المرور</label><input type="password" placeholder="********"></div>
                <button class="btn-primary" style="width:100%;" onclick="showPage('home-page')">دخول للمنصة</button>
                <p style="text-align: center; margin-top: 15px; font-size: 13px; color: #777;">نسيتِ كلمة المرور؟</p>
            </div>
        </div>

    </div>

    <footer>
        <p>مشروع تخرج - منصة أمانك - جامعة طيبة &copy; 2026</p>
        <p style="margin-top: 5px;">جميع الحقوق محفوظة لصالح عمادة شؤون الطلاب</p>
    </footer>

    <script>
        function showPage(pageId) {
            // إخفاء كل الصفحات
            document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
            // إزالة نشاط الروابط
            document.querySelectorAll('.nav-links a').forEach(a => a.classList.remove('active'));
            
            // إظهار الصفحة المطلوبة
            document.getElementById(pageId).classList.add('active');
            
            // تمييز الرابط النشط في القائمة
            const navId = 'nav-' + pageId.split('-')[0];
            const navElement = document.getElementById(navId);
            if(navElement) navElement.classList.add('active');

            window.scrollTo(0,0);
        }

        function confirmBooking() {
            const date = document.getElementById('cons-date').value;
            const time = document.getElementById('cons-time').value;
            const type = document.getElementById('cons-type').value;

            if(!date || !time) { 
                alert("يرجى اختيار التاريخ والوقت أولاً."); 
                return; 
            }
            
            // إضافة الطلب للجدول برمجياً للتمثيل
            const list = document.getElementById('sessions-list');
            const row = `<tr>
                <td>استشارة ${type}</td>
                <td>${date} | ${time}</td>
                <td><span class="status-badge" style="background:#fff3cd; color:#856404;">جديد</span></td>
            </tr>`;
            list.innerHTML = row + list.innerHTML;

            alert("تم إرسال طلب الموعد بنجاح! يمكنك متابعته من لوحة التحكم.");
            showPage('dashboard-page');
        }
    </script>
</body>
</html>
