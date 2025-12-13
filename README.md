<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>جمعية الخير والإحسان - نظام العضوية والدفع المتكامل</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/toastify-js/src/toastify.min.css">
    <style>
        :root {
            --primary-color: #2E7D32;
            --secondary-color: #4CAF50;
            --accent-color: #FF9800;
            --light-color: #F1F8E9;
            --dark-color: #1B5E20;
            --text-color: #333;
            --raghidi-color: #00A79D;
            --ahli-color: #E30613;
            --success-color: #28a745;
            --warning-color: #ffc107;
            --info-color: #17a2b8;
            --danger-color: #dc3545;
            --sidebar-width: 250px;
            --header-height: 70px;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: #f9f9f9;
            color: var(--text-color);
            line-height: 1.6;
            overflow-x: hidden;
        }
        
        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }
        
        /* رأس الموقع */
        header {
            background-color: white;
            box-shadow: 0 2px 15px rgba(0, 0, 0, 0.1);
            position: sticky;
            top: 0;
            z-index: 1000;
            height: var(--header-height);
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 0;
            height: 100%;
        }
        
        .logo {
            display: flex;
            align-items: center;
        }
        
        .logo img {
            height: 50px;
            margin-left: 10px;
        }
        
        .logo-text h1 {
            color: var(--primary-color);
            font-size: 1.6rem;
        }
        
        .logo-text p {
            color: var(--dark-color);
            font-size: 0.85rem;
        }
        
        .user-menu {
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .user-info {
            text-align: left;
            margin-left: 10px;
        }
        
        .user-name {
            font-weight: 600;
            color: var(--primary-color);
        }
        
        .user-role {
            font-size: 0.8rem;
            color: #666;
        }
        
        .user-avatar {
            width: 45px;
            height: 45px;
            border-radius: 50%;
            background-color: var(--primary-color);
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            font-size: 1.2rem;
        }
        
        .notifications {
            position: relative;
        }
        
        .notification-badge {
            position: absolute;
            top: -5px;
            left: -5px;
            background-color: var(--danger-color);
            color: white;
            border-radius: 50%;
            width: 20px;
            height: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 0.7rem;
        }
        
        nav ul {
            display: flex;
            list-style: none;
        }
        
        nav ul li {
            margin-right: 20px;
        }
        
        nav ul li a {
            text-decoration: none;
            color: var(--text-color);
            font-weight: 600;
            padding: 8px 15px;
            border-radius: 4px;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            gap: 8px;
        }
        
        nav ul li a:hover, nav ul li a.active {
            background-color: var(--primary-color);
            color: white;
        }
        
        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            font-size: 1.5rem;
            color: var(--primary-color);
            cursor: pointer;
        }
        
        /* لوحة التحكم */
        .dashboard-container {
            display: flex;
            min-height: calc(100vh - var(--header-height));
        }
        
        .sidebar {
            width: var(--sidebar-width);
            background-color: var(--dark-color);
            color: white;
            transition: all 0.3s ease;
            position: fixed;
            height: calc(100vh - var(--header-height));
            overflow-y: auto;
            padding-top: 20px;
        }
        
        .sidebar.collapsed {
            margin-right: calc(-1 * var(--sidebar-width));
        }
        
        .main-content {
            flex: 1;
            margin-right: var(--sidebar-width);
            padding: 25px;
            transition: all 0.3s ease;
        }
        
        .main-content.expanded {
            margin-right: 0;
        }
        
        .sidebar-toggle {
            background-color: var(--primary-color);
            color: white;
            border: none;
            border-radius: 5px;
            padding: 8px 12px;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 8px;
            margin-bottom: 20px;
            margin-right: 20px;
        }
        
        .sidebar-menu {
            list-style: none;
        }
        
        .sidebar-menu li {
            margin-bottom: 5px;
        }
        
        .sidebar-menu a {
            color: white;
            text-decoration: none;
            padding: 15px 25px;
            display: flex;
            align-items: center;
            gap: 12px;
            transition: all 0.3s ease;
            border-right: 3px solid transparent;
        }
        
        .sidebar-menu a:hover, .sidebar-menu a.active {
            background-color: rgba(255, 255, 255, 0.1);
            border-right-color: var(--accent-color);
        }
        
        /* إحصائيات لوحة التحكم */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
            gap: 25px;
            margin-bottom: 40px;
        }
        
        .stat-card {
            background-color: white;
            border-radius: 10px;
            padding: 25px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            border-top: 4px solid var(--primary-color);
            transition: transform 0.3s;
        }
        
        .stat-card:hover {
            transform: translateY(-5px);
        }
        
        .stat-card.green {
            border-top-color: var(--success-color);
        }
        
        .stat-card.blue {
            border-top-color: var(--info-color);
        }
        
        .stat-card.orange {
            border-top-color: var(--accent-color);
        }
        
        .stat-card.red {
            border-top-color: var(--danger-color);
        }
        
        .stat-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
        }
        
        .stat-icon {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            color: white;
        }
        
        .stat-icon.green {
            background-color: var(--success-color);
        }
        
        .stat-icon.blue {
            background-color: var(--info-color);
        }
        
        .stat-icon.orange {
            background-color: var(--accent-color);
        }
        
        .stat-icon.red {
            background-color: var(--danger-color);
        }
        
        .stat-value {
            font-size: 2rem;
            font-weight: bold;
            color: var(--dark-color);
            margin-bottom: 5px;
        }
        
        .stat-label {
            color: #666;
            font-size: 0.9rem;
        }
        
        .stat-change {
            font-size: 0.8rem;
            margin-top: 5px;
        }
        
        .stat-change.positive {
            color: var(--success-color);
        }
        
        .stat-change.negative {
            color: var(--danger-color);
        }
        
        /* الرسوم البيانية */
        .charts-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
            gap: 25px;
            margin-bottom: 40px;
        }
        
        .chart-card {
            background-color: white;
            border-radius: 10px;
            padding: 25px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
        }
        
        .chart-header {
            margin-bottom: 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .chart-title {
            color: var(--primary-color);
            font-size: 1.2rem;
        }
        
        .chart-container {
            height: 300px;
            position: relative;
        }
        
        /* الجداول */
        .data-table {
            width: 100%;
            border-collapse: collapse;
            background-color: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
        }
        
        .data-table th {
            background-color: var(--light-color);
            color: var(--primary-color);
            padding: 15px;
            text-align: right;
            font-weight: 600;
        }
        
        .data-table td {
            padding: 15px;
            border-bottom: 1px solid #eee;
        }
        
        .data-table tr:last-child td {
            border-bottom: none;
        }
        
        .data-table tr:hover {
            background-color: rgba(0, 0, 0, 0.02);
        }
        
        .status-badge {
            padding: 5px 12px;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 600;
        }
        
        .status-badge.active {
            background-color: rgba(40, 167, 69, 0.1);
            color: var(--success-color);
        }
        
        .status-badge.pending {
            background-color: rgba(255, 193, 7, 0.1);
            color: var(--warning-color);
        }
        
        .status-badge.inactive {
            background-color: rgba(220, 53, 69, 0.1);
            color: var(--danger-color);
        }
        
        /* أقسام الموقع */
        section {
            padding: 60px 0;
        }
        
        .section-title {
            margin-bottom: 30px;
        }
        
        .section-title h2 {
            color: var(--primary-color);
            font-size: 2rem;
            position: relative;
            display: inline-block;
            padding-bottom: 15px;
        }
        
        .section-title h2::after {
            content: '';
            position: absolute;
            bottom: 0;
            right: 0;
            width: 80px;
            height: 3px;
            background-color: var(--accent-color);
        }
        
        .section-title.centered {
            text-align: center;
        }
        
        .section-title.centered h2::after {
            right: 50%;
            transform: translateX(50%);
        }
        
        /* قسم البطل */
        .hero {
            background: linear-gradient(rgba(0, 0, 0, 0.8), rgba(0, 0, 0, 0.8)), url('https://images.unsplash.com/photo-1532629345422-7515f3d16bb6?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80');
            background-size: cover;
            background-position: center;
            color: white;
            text-align: center;
            padding: 100px 0;
            margin-bottom: 40px;
        }
        
        .hero h2 {
            font-size: 2.8rem;
            margin-bottom: 20px;
        }
        
        .hero p {
            font-size: 1.2rem;
            max-width: 800px;
            margin: 0 auto 30px;
        }
        
        /* الأزرار */
        .btn {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            background-color: var(--accent-color);
            color: white;
            padding: 12px 30px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: bold;
            font-size: 1.1rem;
            transition: all 0.3s ease;
            border: none;
            cursor: pointer;
            gap: 8px;
        }
        
        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        .btn-primary {
            background-color: var(--primary-color);
        }
        
        .btn-primary:hover {
            background-color: var(--dark-color);
        }
        
        .btn-success {
            background-color: var(--success-color);
        }
        
        .btn-warning {
            background-color: var(--warning-color);
            color: #212529;
        }
        
        .btn-danger {
            background-color: var(--danger-color);
        }
        
        .btn-info {
            background-color: var(--info-color);
        }
        
        .btn-sm {
            padding: 8px 16px;
            font-size: 0.9rem;
        }
        
        /* نموذج تسجيل الدخول */
        .auth-container {
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 80vh;
            padding: 40px 0;
        }
        
        .auth-card {
            background-color: white;
            border-radius: 15px;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.1);
            padding: 40px;
            width: 100%;
            max-width: 500px;
        }
        
        .auth-header {
            text-align: center;
            margin-bottom: 40px;
        }
        
        .auth-header h2 {
            color: var(--primary-color);
            margin-bottom: 10px;
        }
        
        .form-group {
            margin-bottom: 25px;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            color: var(--primary-color);
        }
        
        .form-control {
            width: 100%;
            padding: 12px 15px;
            border: 1px solid #ddd;
            border-radius: 8px;
            font-size: 1rem;
            transition: all 0.3s;
        }
        
        .form-control:focus {
            border-color: var(--primary-color);
            outline: none;
            box-shadow: 0 0 0 3px rgba(46, 125, 50, 0.1);
        }
        
        /* إشعارات */
        .notifications-dropdown {
            position: absolute;
            top: 40px;
            left: -200px;
            width: 350px;
            background-color: white;
            border-radius: 10px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.15);
            z-index: 1001;
            display: none;
        }
        
        .notifications-dropdown.show {
            display: block;
            animation: slideDown 0.3s;
        }
        
        @keyframes slideDown {
            from { opacity: 0; transform: translateY(-10px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .notification-header {
            padding: 15px;
            border-bottom: 1px solid #eee;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .notification-item {
            padding: 15px;
            border-bottom: 1px solid #f5f5f5;
            display: flex;
            gap: 12px;
            cursor: pointer;
            transition: background-color 0.2s;
        }
        
        .notification-item:hover {
            background-color: #f9f9f9;
        }
        
        .notification-item.unread {
            background-color: rgba(46, 125, 50, 0.05);
        }
        
        .notification-icon {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            flex-shrink: 0;
        }
        
        .notification-icon.info {
            background-color: rgba(23, 162, 184, 0.1);
            color: var(--info-color);
        }
        
        .notification-icon.success {
            background-color: rgba(40, 167, 69, 0.1);
            color: var(--success-color);
        }
        
        .notification-icon.warning {
            background-color: rgba(255, 193, 7, 0.1);
            color: var(--warning-color);
        }
        
        .notification-content {
            flex: 1;
        }
        
        .notification-title {
            font-weight: 600;
            margin-bottom: 5px;
        }
        
        .notification-time {
            font-size: 0.8rem;
            color: #999;
        }
        
        /* نظام التبويبات */
        .tabs {
            display: flex;
            border-bottom: 1px solid #ddd;
            margin-bottom: 30px;
        }
        
        .tab {
            padding: 15px 30px;
            cursor: pointer;
            font-weight: 600;
            color: #666;
            border-bottom: 3px solid transparent;
            transition: all 0.3s;
        }
        
        .tab:hover {
            color: var(--primary-color);
        }
        
        .tab.active {
            color: var(--primary-color);
            border-bottom-color: var(--primary-color);
        }
        
        .tab-content {
            display: none;
        }
        
        .tab-content.active {
            display: block;
            animation: fadeIn 0.5s;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        
        /* تحسينات التجاوب */
        @media (max-width: 1200px) {
            .charts-container {
                grid-template-columns: 1fr;
            }
        }
        
        @media (max-width: 992px) {
            .sidebar {
                margin-right: calc(-1 * var(--sidebar-width));
                z-index: 1001;
            }
            
            .sidebar.show {
                margin-right: 0;
            }
            
            .main-content {
                margin-right: 0;
            }
            
            .mobile-menu-btn {
                display: block;
            }
            
            nav ul {
                display: none;
                position: absolute;
                top: 100%;
                right: 0;
                background-color: white;
                width: 100%;
                box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
                flex-direction: column;
                padding: 20px 0;
            }
            
            nav ul.show {
                display: flex;
            }
            
            nav ul li {
                margin: 0;
            }
            
            nav ul li a {
                padding: 15px 25px;
                border-radius: 0;
            }
            
            .stats-grid {
                grid-template-columns: repeat(2, 1fr);
            }
        }
        
        @media (max-width: 768px) {
            .stats-grid {
                grid-template-columns: 1fr;
            }
            
            .hero h2 {
                font-size: 2.2rem;
            }
            
            .hero p {
                font-size: 1rem;
            }
            
            .auth-card {
                padding: 30px 20px;
            }
            
            .notifications-dropdown {
                left: -250px;
                width: 300px;
            }
        }
        
        @media (max-width: 576px) {
            .header-content {
                flex-direction: column;
                align-items: flex-start;
                height: auto;
            }
            
            .logo {
                margin-bottom: 15px;
            }
            
            .user-menu {
                width: 100%;
                justify-content: space-between;
            }
        }
    </style>
</head>
<body>
    <!-- رأس الموقع -->
    <header>
        <div class="container">
            <div class="header-content">
                <button class="mobile-menu-btn" id="mobileMenuBtn">
                    <i class="fas fa-bars"></i>
                </button>
                
                <div class="logo">
                    <img src="https://cdn-icons-png.flaticon.com/512/3208/3208720.png" alt="شعار الجمعية">
                    <div class="logo-text">
                        <h1>جمعية الخير والإحسان</h1>
                        <p>يداً بيد نحو مجتمع أفضل</p>
                    </div>
                </div>
                
                <nav id="mainNav">
                    <ul id="navMenu">
                        <!-- سيتم تعبئة القائمة ديناميكياً -->
                    </ul>
                </nav>
                
                <div class="user-menu">
                    <div id="userAuthSection">
                        <!-- سيتم تعبئة قسم تسجيل الدخول ديناميكياً -->
                    </div>
                </div>
            </div>
        </div>
    </header>

    <!-- لوحة التحكم -->
    <div class="dashboard-container" id="dashboardContainer" style="display: none;">
        <div class="sidebar" id="sidebar">
            <button class="sidebar-toggle" id="sidebarToggle">
                <i class="fas fa-bars"></i> القائمة
            </button>
            
            <ul class="sidebar-menu" id="sidebarMenu">
                <!-- سيتم تعبئة القائمة الجانبية ديناميكياً -->
            </ul>
        </div>
        
        <div class="main-content" id="mainContent">
            <!-- محتوى لوحة التحكم الرئيسي -->
            <div id="dashboardContent">
                <!-- سيتم تعبئة المحتوى ديناميكياً -->
            </div>
        </div>
    </div>

    <!-- المحتوى الرئيسي للزوار -->
    <div id="mainContentArea">
        <!-- قسم البطل -->
        <section class="hero" id="home">
            <div class="container">
                <h2>جمعية الخير والإحسان</h2>
                <p>جمعية خيرية مرخصة تهدف إلى تقديم الدعم والمساعدات للمحتاجين والأسر المتعففة في مختلف مناطق المملكة. نعمل من خلال برامج متنوعة لتحقيق التنمية المستدامة والتكافل الاجتماعي.</p>
                <div id="heroButtons">
                    <!-- سيتم تعبئة الأزرار ديناميكياً -->
                </div>
            </div>
        </section>

        <!-- الأقسام الأخرى -->
        <section id="about" style="display: none;">
            <div class="container">
                <div class="section-title centered">
                    <h2>عن الجمعية</h2>
                </div>
                
                <div class="about-content" id="aboutContent">
                    <!-- سيتم تعبئة محتوى "عن الجمعية" ديناميكياً -->
                </div>
            </div>
        </section>

        <section id="registration" class="registration-section" style="display: none;">
            <div class="container">
                <div class="section-title centered">
                    <h2>تسجيل عضوية جديدة</h2>
                </div>
                
                <div class="registration-form" id="registrationFormContainer">
                    <!-- سيتم تعبئة نموذج التسجيل ديناميكياً -->
                </div>
            </div>
        </section>

        <section id="plans" style="display: none;">
            <div class="container">
                <div class="section-title centered">
                    <h2>خطط الاشتراك</h2>
                    <p>اختر الخطة المناسبة لك وشارك معنا في أعمال الخير</p>
                </div>
                
                <div class="plans" id="plansContainer">
                    <!-- سيتم تعبئة خطط الاشتراك ديناميكياً -->
                </div>
            </div>
        </section>

        <section id="payment" class="payment-section" style="display: none;">
            <div class="container">
                <div class="section-title centered">
                    <h2>الدفع الإلكتروني</h2>
                    <p>اختر طريقة الدفع المناسبة وأكمل عملية الدفع بسهولة</p>
                </div>
                
                <div class="payment-options" id="paymentOptionsContainer">
                    <!-- سيتم تعبئة خيارات الدفع ديناميكياً -->
                </div>
            </div>
        </section>

        <section id="tracking" class="tracking-section" style="display: none;">
            <div class="container">
                <div class="section-title centered">
                    <h2>متابعة العضوية</h2>
                    <p>تابع حالة اشتراكك والمبلغ المتبقي وأيام الاستلام</p>
                </div>
                
                <div class="tracking-card" id="trackingContainer">
                    <!-- سيتم تعبئة متابعة العضوية ديناميكياً -->
                </div>
            </div>
        </section>

        <section id="license" class="license-section" style="display: none;">
            <div class="container">
                <div class="license-content">
                    <h2>تصريح الجمعية</h2>
                    <p>تعمل جمعية الخير والإحسان تحت إشراف وزارة الموارد البشرية والتنمية الاجتماعية بترخيص رسمي</p>
                    <div class="license-number">ترخيص رقم: 12345</div>
                    <p>تم منح الترخيص في تاريخ 10/5/2010 ويتم تجديده سنوياً وفقاً لللوائح والأنظمة المعمول بها</p>
                    <p>جميع تبرعاتكم محفوظة في حسابات بنكية مرخصة وتصرف وفقاً للأنظمة والضوابط الشرعية والقانونية</p>
                    <a href="#" class="btn" style="margin-top: 20px;">
                        <i class="fas fa-file-certificate"></i> عرض الترخيص الرسمي
                    </a>
                </div>
            </div>
        </section>

        <section id="contact" style="display: none;">
            <div class="container">
                <div class="section-title centered">
                    <h2>اتصل بنا</h2>
                </div>
                
                <div class="contact-content" id="contactContent">
                    <!-- سيتم تعبئة محتوى "اتصل بنا" ديناميكياً -->
                </div>
            </div>
        </section>

        <!-- تذييل الصفحة -->
        <footer style="display: none;" id="footer">
            <div class="container">
                <div class="footer-content" id="footerContent">
                    <!-- سيتم تعبئة التذييل ديناميكياً -->
                </div>
                
                <div class="copyright">
                    <p>جميع الحقوق محفوظة &copy; 2023 جمعية الخير والإحسان</p>
                    <p style="margin-top: 5px; font-size: 0.8rem;">رقم السجل التجاري: 1012345678 | الرقم الضريبي: 310123456789</p>
                </div>
            </div>
        </footer>
    </div>

    <!-- نموذج تسجيل الدخول -->
    <div class="modal" id="loginModal" style="display: none;">
        <div class="auth-container">
            <div class="auth-card">
                <div class="auth-header">
                    <h2>تسجيل الدخول</h2>
                    <p>أدخل بيانات حسابك للدخول إلى النظام</p>
                </div>
                
                <form id="loginForm">
                    <div class="form-group">
                        <label for="loginEmail">البريد الإلكتروني</label>
                        <input type="email" id="loginEmail" class="form-control" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="loginPassword">كلمة المرور</label>
                        <input type="password" id="loginPassword" class="form-control" required>
                    </div>
                    
                    <div class="form-group" style="display: flex; justify-content: space-between; align-items: center;">
                        <div>
                            <input type="checkbox" id="rememberMe">
                            <label for="rememberMe" style="display: inline; margin-right: 5px;">تذكرني</label>
                        </div>
                        <a href="#" id="forgotPassword" style="font-size: 0.9rem;">نسيت كلمة المرور؟</a>
                    </div>
                    
                    <button type="submit" class="btn btn-primary" style="width: 100%;">
                        <i class="fas fa-sign-in-alt"></i> تسجيل الدخول
                    </button>
                    
                    <div style="text-align: center; margin-top: 20px;">
                        <p>ليس لديك حساب؟ <a href="#" id="showRegister">سجل الآن</a></p>
                    </div>
                </form>
            </div>
        </div>
    </div>

    <!-- نموذج التسجيل -->
    <div class="modal" id="registerModal" style="display: none;">
        <div class="auth-container">
            <div class="auth-card">
                <div class="auth-header">
                    <h2>إنشاء حساب جديد</h2>
                    <p>املأ النموذج لإنشاء حساب في الجمعية</p>
                </div>
                
                <form id="registerForm">
                    <div class="form-group">
                        <label for="registerName">الاسم الكامل</label>
                        <input type="text" id="registerName" class="form-control" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="registerEmail">البريد الإلكتروني</label>
                        <input type="email" id="registerEmail" class="form-control" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="registerPhone">رقم الجوال</label>
                        <input type="tel" id="registerPhone" class="form-control" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="registerPassword">كلمة المرور</label>
                        <input type="password" id="registerPassword" class="form-control" required minlength="6">
                    </div>
                    
                    <div class="form-group">
                        <label for="registerConfirmPassword">تأكيد كلمة المرور</label>
                        <input type="password" id="registerConfirmPassword" class="form-control" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="registerRole">نوع العضوية</label>
                        <select id="registerRole" class="form-control" required>
                            <option value="">اختر نوع العضوية</option>
                            <option value="member">عضو عادي</option>
                            <option value="donor">متبرع</option>
                            <option value="volunteer">متطوع</option>
                        </select>
                    </div>
                    
                    <button type="submit" class="btn btn-primary" style="width: 100%;">
                        <i class="fas fa-user-plus"></i> إنشاء حساب
                    </button>
                    
                    <div style="text-align: center; margin-top: 20px;">
                        <p>لديك حساب بالفعل؟ <a href="#" id="showLogin">تسجيل الدخول</a></p>
                    </div>
                </form>
            </div>
        </div>
    </div>

    <!-- نموذج تأكيد الدفع -->
    <div class="modal" id="paymentConfirmationModal" style="display: none;">
        <div class="modal-content">
            <div class="modal-header">
                <h3>تأكيد عملية الدفع</h3>
                <button class="close-modal" id="closePaymentModal">&times;</button>
            </div>
            
            <div class="payment-confirmation">
                <i class="fas fa-check-circle"></i>
                <h3>تم استلام إيصال الدفع بنجاح</h3>
                <p>شكراً لك على دعمك لجمعية الخير والإحسان</p>
                
                <div class="confirmation-details">
                    <div class="confirmation-row">
                        <span class="confirmation-label">رقم المرجع:</span>
                        <span id="confirmationRef">PAY-2023-08542</span>
                    </div>
                    <div class="confirmation-row">
                        <span class="confirmation-label">المبلغ المدفوع:</span>
                        <span id="confirmationAmount">500 ريال</span>
                    </div>
                    <div class="confirmation-row">
                        <span class="confirmation-label">طريقة الدفع:</span>
                        <span id="confirmationMethod">مصرف الراجحي</span>
                    </div>
                    <div class="confirmation-row">
                        <span class="confirmation-label">تاريخ الدفع:</span>
                        <span id="confirmationDate">15 سبتمبر 2023</span>
                    </div>
                    <div class="confirmation-row">
                        <span class="confirmation-label">حالة المعاملة:</span>
                        <span style="color: var(--success-color); font-weight: bold;" id="confirmationStatus">قيد المراجعة</span>
                    </div>
                </div>
                
                <p>سيتم تفعيل عضويتك خلال 24-48 ساعة عمل بعد التحقق من الدفع</p>
                <p>للاستفسارات يرجى الاتصال على 0112345678</p>
                
                <div style="margin-top: 30px;">
                    <button class="btn" id="printConfirmation">
                        <i class="fas fa-print"></i> طباعة التأكيد
                    </button>
                    <button class="btn btn-primary" id="closeConfirmation" style="margin-right: 15px;">
                        <i class="fas fa-check"></i> موافق
                    </button>
                </div>
            </div>
        </div>
    </div>

    <!-- نموذج محاكاة التحويل -->
    <div class="modal" id="simulationModal" style="display: none;">
        <div class="modal-content">
            <div class="modal-header">
                <h3>محاكاة التحويل البنكي</h3>
                <button class="close-modal" id="closeSimulationModal">&times;</button>
            </div>
            
            <div class="payment-confirmation">
                <i class="fas fa-mobile-alt" style="color: var(--info-color);"></i>
                <h3>محاكاة عملية التحويل</h3>
                <p>هذه محاكاة لعملية التحويل البنكي لأغراض التوضيح</p>
                
                <div class="confirmation-details">
                    <div class="confirmation-row">
                        <span class="confirmation-label">البنك:</span>
                        <span id="simulationBank">مصرف الراجحي</span>
                    </div>
                    <div class="confirmation-row">
                        <span class="confirmation-label">رقم الحساب:</span>
                        <span id="simulationAccount">SA58800000733333385959</span>
                    </div>
                    <div class="confirmation-row">
                        <span class="confirmation-label">المبلغ:</span>
                        <span id="simulationAmount">500 ريال</span>
                    </div>
                    <div class="confirmation-row">
                        <span class="confirmation-label">الاسم:</span>
                        <span>جمعية الخير والإحسان</span>
                    </div>
                </div>
                
                <div style="margin: 25px 0; padding: 20px; background-color: #e8f5e9; border-radius: 10px;">
                    <h4><i class="fas fa-info-circle"></i> في التطبيق الحقيقي:</h4>
                    <p>1. سجل الدخول إلى تطبيق البنك</p>
                    <p>2. اذهب إلى قسم التحويلات</p>
                    <p>3. أدخل رقم الحساب أعلاه</p>
                    <p>4. أدخل المبلغ وأكد العملية</p>
                    <p>5. احفظ إيصال التحويل</p>
                </div>
                
                <p>بعد إكمال التحويل الفعلي، ارجع إلى الموقع لرفع إيصال التحويل</p>
                
                <div style="margin-top: 30px;">
                    <button class="btn btn-primary" id="simulateSuccess">
                        <i class="fas fa-check"></i> محاكاة تحويل ناجح
                    </button>
                    <button class="btn" id="closeSimulation" style="margin-right: 15px;">
                        <i class="fas fa-times"></i> إلغاء
                    </button>
                </div>
            </div>
        </div>
    </div>

    <!-- نموذج إدارة المستخدمين (للمسؤولين) -->
    <div class="modal" id="userManagementModal" style="display: none;">
        <div class="modal-content" style="max-width: 900px;">
            <div class="modal-header">
                <h3>إدارة المستخدمين</h3>
                <button class="close-modal" id="closeUserManagementModal">&times;</button>
            </div>
            
            <div class="tabs">
                <div class="tab active" data-tab="usersList">قائمة المستخدمين</div>
                <div class="tab" data-tab="addUser">إضافة مستخدم جديد</div>
                <div class="tab" data-tab="rolesPermissions">الأدوار والصلاحيات</div>
            </div>
            
            <div class="tab-content active" id="usersListTab">
                <div style="margin-bottom: 20px;">
                    <div class="form-group" style="display: flex; gap: 10px;">
                        <input type="text" id="userSearch" class="form-control" placeholder="بحث عن مستخدم...">
                        <select id="userFilter" class="form-control" style="width: 200px;">
                            <option value="">جميع المستخدمين</option>
                            <option value="admin">مسؤول</option>
                            <option value="member">عضو</option>
                            <option value="donor">متبرع</option>
                            <option value="volunteer">متطوع</option>
                        </select>
                    </div>
                </div>
                
                <div class="table-responsive">
                    <table class="data-table" id="usersTable">
                        <thead>
                            <tr>
                                <th>الاسم</th>
                                <th>البريد الإلكتروني</th>
                                <th>الدور</th>
                                <th>الحالة</th>
                                <th>تاريخ التسجيل</th>
                                <th>الإجراءات</th>
                            </tr>
                        </thead>
                        <tbody id="usersTableBody">
                            <!-- سيتم تعبئة الجدول ديناميكياً -->
                        </tbody>
                    </table>
                </div>
            </div>
            
            <div class="tab-content" id="addUserTab">
                <form id="addUserForm">
                    <div class="form-row" style="display: flex; gap: 20px; margin-bottom: 20px;">
                        <div class="form-group" style="flex: 1;">
                            <label for="newUserName">الاسم الكامل</label>
                            <input type="text" id="newUserName" class="form-control" required>
                        </div>
                        <div class="form-group" style="flex: 1;">
                            <label for="newUserEmail">البريد الإلكتروني</label>
                            <input type="email" id="newUserEmail" class="form-control" required>
                        </div>
                    </div>
                    
                    <div class="form-row" style="display: flex; gap: 20px; margin-bottom: 20px;">
                        <div class="form-group" style="flex: 1;">
                            <label for="newUserPhone">رقم الجوال</label>
                            <input type="tel" id="newUserPhone" class="form-control" required>
                        </div>
                        <div class="form-group" style="flex: 1;">
                            <label for="newUserRole">الدور</label>
                            <select id="newUserRole" class="form-control" required>
                                <option value="member">عضو</option>
                                <option value="donor">متبرع</option>
                                <option value="volunteer">متطوع</option>
                                <option value="admin">مسؤول</option>
                            </select>
                        </div>
                    </div>
                    
                    <div class="form-group">
                        <label for="newUserPassword">كلمة المرور</label>
                        <input type="password" id="newUserPassword" class="form-control" required minlength="6">
                    </div>
                    
                    <button type="submit" class="btn btn-primary">
                        <i class="fas fa-user-plus"></i> إضافة مستخدم
                    </button>
                </form>
            </div>
            
            <div class="tab-content" id="rolesPermissionsTab">
                <div style="margin-bottom: 20px;">
                    <h4>إدارة الأدوار والصلاحيات</h4>
                    <p>قم بتعيين الصلاحيات المناسبة لكل دور في النظام</p>
                </div>
                
                <div class="table-responsive">
                    <table class="data-table">
                        <thead>
                            <tr>
                                <th>الدور</th>
                                <th>الوصف</th>
                                <th>عدد المستخدمين</th>
                                <th>الإجراءات</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr>
                                <td><strong>مسؤول</strong></td>
                                <td>صلاحيات كاملة على النظام</td>
                                <td id="adminCount">1</td>
                                <td><button class="btn btn-sm btn-info">تعديل الصلاحيات</button></td>
                            </tr>
                            <tr>
                                <td><strong>عضو</strong></td>
                                <td>الوصول إلى الملف الشخصي والاشتراكات</td>
                                <td id="memberCount">0</td>
                                <td><button class="btn btn-sm btn-info">تعديل الصلاحيات</button></td>
                            </tr>
                            <tr>
                                <td><strong>متبرع</strong></td>
                                <td>الوصول إلى التبرعات والتقارير</td>
                                <td id="donorCount">0</td>
                                <td><button class="btn btn-sm btn-info">تعديل الصلاحيات</button></td>
                            </tr>
                            <tr>
                                <td><strong>متطوع</strong></td>
                                <td>الوصول إلى الأنشطة والتطوع</td>
                                <td id="volunteerCount">0</td>
                                <td><button class="btn btn-sm btn-info">تعديل الصلاحيات</button></td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>
        </div>
    </div>

    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/toastify-js"></script>
    <script>
        // ========================================
        // نظام إدارة الحالة والتطبيق
        // ========================================
        const AppState = {
            currentUser: null,
            isLoggedIn: false,
            currentPage: 'home',
            sidebarCollapsed: false,
            notifications: [],
            users: [],
            memberships: [],
            payments: []
        };
        
        // ========================================
        // قاعدة بيانات محلية باستخدام IndexedDB
        // ========================================
        class Database {
            constructor() {
                this.db = null;
                this.init();
            }
            
            async init() {
                return new Promise((resolve, reject) => {
                    const request = indexedDB.open('CharityAppDB', 1);
                    
                    request.onerror = () => {
                        console.error('فشل فتح قاعدة البيانات');
                        reject(request.error);
                    };
                    
                    request.onsuccess = () => {
                        this.db = request.result;
                        console.log('تم فتح قاعدة البيانات بنجاح');
                        resolve(this.db);
                    };
                    
                    request.onupgradeneeded = (event) => {
                        const db = event.target.result;
                        
                        // إنشاء جداول المخزن
                        if (!db.objectStoreNames.contains('users')) {
                            const usersStore = db.createObjectStore('users', { keyPath: 'id', autoIncrement: true });
                            usersStore.createIndex('email', 'email', { unique: true });
                            usersStore.createIndex('role', 'role', { unique: false });
                        }
                        
                        if (!db.objectStoreNames.contains('memberships')) {
                            const membershipsStore = db.createObjectStore('memberships', { keyPath: 'id', autoIncrement: true });
                            membershipsStore.createIndex('userId', 'userId', { unique: false });
                            membershipsStore.createIndex('status', 'status', { unique: false });
                        }
                        
                        if (!db.objectStoreNames.contains('payments')) {
                            const paymentsStore = db.createObjectStore('payments', { keyPath: 'id', autoIncrement: true });
                            paymentsStore.createIndex('userId', 'userId', { unique: false });
                            paymentsStore.createIndex('membershipId', 'membershipId', { unique: false });
                            paymentsStore.createIndex('status', 'status', { unique: false });
                        }
                        
                        if (!db.objectStoreNames.contains('notifications')) {
                            const notificationsStore = db.createObjectStore('notifications', { keyPath: 'id', autoIncrement: true });
                            notificationsStore.createIndex('userId', 'userId', { unique: false });
                            notificationsStore.createIndex('read', 'read', { unique: false });
                        }
                        
                        console.log('تم إنشاء هياكل قاعدة البيانات');
                    };
                });
            }
            
            // إضافة مستخدم جديد
            async addUser(user) {
                return new Promise((resolve, reject) => {
                    const transaction = this.db.transaction(['users'], 'readwrite');
                    const store = transaction.objectStore('users');
                    const request = store.add(user);
                    
                    request.onsuccess = () => resolve(request.result);
                    request.onerror = () => reject(request.error);
                });
            }
            
            // الحصول على جميع المستخدمين
            async getUsers() {
                return new Promise((resolve, reject) => {
                    const transaction = this.db.transaction(['users'], 'readonly');
                    const store = transaction.objectStore('users');
                    const request = store.getAll();
                    
                    request.onsuccess = () => resolve(request.result);
                    request.onerror = () => reject(request.error);
                });
            }
            
            // البحث عن مستخدم بالبريد الإلكتروني
            async getUserByEmail(email) {
                return new Promise((resolve, reject) => {
                    const transaction = this.db.transaction(['users'], 'readonly');
                    const store = transaction.objectStore('users');
                    const index = store.index('email');
                    const request = index.get(email);
                    
                    request.onsuccess = () => resolve(request.result);
                    request.onerror = () => reject(request.error);
                });
            }
            
            // تحديث مستخدم
            async updateUser(id, updates) {
                return new Promise((resolve, reject) => {
                    const transaction = this.db.transaction(['users'], 'readwrite');
                    const store = transaction.objectStore('users');
                    const getRequest = store.get(id);
                    
                    getRequest.onsuccess = () => {
                        const user = getRequest.result;
                        Object.assign(user, updates);
                        const updateRequest = store.put(user);
                        
                        updateRequest.onsuccess = () => resolve(updateRequest.result);
                        updateRequest.onerror = () => reject(updateRequest.error);
                    };
                    
                    getRequest.onerror = () => reject(getRequest.error);
                });
            }
            
            // حذف مستخدم
            async deleteUser(id) {
                return new Promise((resolve, reject) => {
                    const transaction = this.db.transaction(['users'], 'readwrite');
                    const store = transaction.objectStore('users');
                    const request = store.delete(id);
                    
                    request.onsuccess = () => resolve(true);
                    request.onerror = () => reject(request.error);
                });
            }
            
            // إضافة اشتراك جديد
            async addMembership(membership) {
                return new Promise((resolve, reject) => {
                    const transaction = this.db.transaction(['memberships'], 'readwrite');
                    const store = transaction.objectStore('memberships');
                    const request = store.add(membership);
                    
                    request.onsuccess = () => resolve(request.result);
                    request.onerror = () => reject(request.error);
                });
            }
            
            // الحصول على اشتراكات مستخدم
            async getUserMemberships(userId) {
                return new Promise((resolve, reject) => {
                    const transaction = this.db.transaction(['memberships'], 'readonly');
                    const store = transaction.objectStore('memberships');
                    const index = store.index('userId');
                    const request = index.getAll(userId);
                    
                    request.onsuccess = () => resolve(request.result);
                    request.onerror = () => reject(request.error);
                });
            }
            
            // إضافة إشعار جديد
            async addNotification(notification) {
                return new Promise((resolve, reject) => {
                    const transaction = this.db.transaction(['notifications'], 'readwrite');
                    const store = transaction.objectStore('notifications');
                    const request = store.add(notification);
                    
                    request.onsuccess = () => resolve(request.result);
                    request.onerror = () => reject(request.error);
                });
            }
            
            // الحصول على إشعارات مستخدم
            async getUserNotifications(userId) {
                return new Promise((resolve, reject) => {
                    const transaction = this.db.transaction(['notifications'], 'readonly');
                    const store = transaction.objectStore('notifications');
                    const index = store.index('userId');
                    const request = index.getAll(userId);
                    
                    request.onsuccess = () => resolve(request.result);
                    request.onerror = () => reject(request.error);
                });
            }
        }
        
        // ========================================
        // تهيئة التطبيق
        // ========================================
        const db = new Database();
        let charts = {};
        
        // تهيئة قاعدة البيانات والمستخدم الافتراضي
        async function initializeApp() {
            try {
                await db.init();
                
                // تحميل المستخدمين من قاعدة البيانات
                const users = await db.getUsers();
                if (users.length === 0) {
                    // إنشاء مستخدم مسؤول افتراضي
                    const adminUser = {
                        name: 'المسؤول',
                        email: 'admin@example.com',
                        password: 'admin123', // في التطبيق الحقيقي يجب تشفير كلمة المرور
                        phone: '0501234567',
                        role: 'admin',
                        status: 'active',
                        createdAt: new Date().toISOString(),
                        avatarColor: '#2E7D32'
                    };
                    
                    await db.addUser(adminUser);
                    console.log('تم إنشاء المستخدم المسؤول الافتراضي');
                }
                
                // تحميل البيانات إلى حالة التطبيق
                AppState.users = await db.getUsers();
                
                // التحقق من وجود جلسة مستخدم مسجلة
                const savedUser = localStorage.getItem('currentUser');
                if (savedUser) {
                    const user = JSON.parse(savedUser);
                    const dbUser = await db.getUserByEmail(user.email);
                    
                    if (dbUser && dbUser.password === user.password) {
                        AppState.currentUser = dbUser;
                        AppState.isLoggedIn = true;
                    } else {
                        localStorage.removeItem('currentUser');
                    }
                }
                
                // تهيئة واجهة المستخدم
                initializeUI();
                
            } catch (error) {
                console.error('خطأ في تهيئة التطبيق:', error);
                showToast('حدث خطأ في تهيئة النظام. يرجى تحديث الصفحة.', 'error');
            }
        }
        
        // ========================================
        // تهيئة واجهة المستخدم
        // ========================================
        function initializeUI() {
            // تحديث واجهة المستخدم بناءً على حالة تسجيل الدخول
            updateUIForAuthState();
            
            // تعيين معالج الأحداث
            setupEventListeners();
            
            // عرض الصفحة الرئيسية
            showPage('home');
        }
        
        // تحديث واجهة المستخدم بناءً على حالة تسجيل الدخول
        async function updateUIForAuthState() {
            const userAuthSection = document.getElementById('userAuthSection');
            
            if (AppState.isLoggedIn && AppState.currentUser) {
                // عرض معلومات المستخدم
                const user = AppState.currentUser;
                const firstName = user.name.split(' ')[0];
                const avatarInitial = firstName.charAt(0);
                
                // تحميل إشعارات المستخدم
                AppState.notifications = await db.getUserNotifications(user.id) || [];
                const unreadCount = AppState.notifications.filter(n => !n.read).length;
                
                userAuthSection.innerHTML = `
                    <div class="notifications">
                        <button class="btn btn-sm" id="notificationsBtn">
                            <i class="fas fa-bell"></i>
                            ${unreadCount > 0 ? `<span class="notification-badge">${unreadCount}</span>` : ''}
                        </button>
                        <div class="notifications-dropdown" id="notificationsDropdown">
                            <div class="notification-header">
                                <h4 style="margin: 0;">الإشعارات</h4>
                                <button class="btn btn-sm btn-primary" id="markAllRead">تعيين الكل كمقروء</button>
                            </div>
                            <div id="notificationsList">
                                ${AppState.notifications.slice(0, 5).map(notification => `
                                    <div class="notification-item ${notification.read ? '' : 'unread'}" data-id="${notification.id}">
                                        <div class="notification-icon ${notification.type || 'info'}">
                                            <i class="fas ${notification.icon || 'fa-info-circle'}"></i>
                                        </div>
                                        <div class="notification-content">
                                            <div class="notification-title">${notification.title}</div>
                                            <p style="font-size: 0.9rem; margin: 5px 0;">${notification.message}</p>
                                            <div class="notification-time">${formatTime(notification.createdAt)}</div>
                                        </div>
                                    </div>
                                `).join('')}
                                ${AppState.notifications.length === 0 ? '<p style="text-align: center; padding: 20px; color: #999;">لا توجد إشعارات</p>' : ''}
                            </div>
                            <div style="padding: 15px; border-top: 1px solid #eee; text-align: center;">
                                <a href="#" id="viewAllNotifications">عرض جميع الإشعارات</a>
                            </div>
                        </div>
                    </div>
                    <div class="user-info">
                        <div class="user-name">${firstName}</div>
                        <div class="user-role">${getRoleName(user.role)}</div>
                    </div>
                    <div class="user-avatar" style="background-color: ${user.avatarColor || '#2E7D32'}">
                        ${avatarInitial}
                    </div>
                    <button class="btn btn-sm btn-danger" id="logoutBtn">
                        <i class="fas fa-sign-out-alt"></i> خروج
                    </button>
                `;
                
                // إظهار لوحة التحكم وإخفاء المحتوى الرئيسي
                document.getElementById('dashboardContainer').style.display = 'flex';
                document.getElementById('mainContentArea').style.display = 'none';
                
                // تحديث القائمة الجانبية
                updateSidebarMenu();
                
                // تحميل لوحة التحكم
                loadDashboard();
                
            } else {
                // عرض أزرار تسجيل الدخول والتسجيل
                userAuthSection.innerHTML = `
                    <button class="btn btn-sm btn-primary" id="loginBtn">
                        <i class="fas fa-sign-in-alt"></i> تسجيل الدخول
                    </button>
                    <button class="btn btn-sm" id="registerBtn">
                        <i class="fas fa-user-plus"></i> تسجيل جديد
                    </button>
                `;
                
                // إخفاء لوحة التحكم وإظهار المحتوى الرئيسي
                document.getElementById('dashboardContainer').style.display = 'none';
                document.getElementById('mainContentArea').style.display = 'block';
                
                // تحديث قائمة التنقل للزوار
                updateNavigationMenu();
            }
        }
        
        // تحديث قائمة التنقل
        function updateNavigationMenu() {
            const navMenu = document.getElementById('navMenu');
            
            if (AppState.isLoggedIn) {
                navMenu.innerHTML = `
                    <li><a href="#" data-page="dashboard"><i class="fas fa-tachometer-alt"></i> لوحة التحكم</a></li>
                    <li><a href="#" data-page="profile"><i class="fas fa-user"></i> الملف الشخصي</a></li>
                    <li><a href="#" data-page="payments"><i class="fas fa-credit-card"></i> المدفوعات</a></li>
                    <li><a href="#" data-page="reports"><i class="fas fa-chart-bar"></i> التقارير</a></li>
                `;
            } else {
                navMenu.innerHTML = `
                    <li><a href="#" data-page="home" class="active"><i class="fas fa-home"></i> الرئيسية</a></li>
                    <li><a href="#" data-page="about"><i class="fas fa-info-circle"></i> عن الجمعية</a></li>
                    <li><a href="#" data-page="registration"><i class="fas fa-user-plus"></i> التسجيل</a></li>
                    <li><a href="#" data-page="plans"><i class="fas fa-tags"></i> خطط الاشتراك</a></li>
                    <li><a href="#" data-page="payment"><i class="fas fa-credit-card"></i> الدفع</a></li>
                    <li><a href="#" data-page="tracking"><i class="fas fa-chart-line"></i> المتابعة</a></li>
                    <li><a href="#" data-page="license"><i class="fas fa-certificate"></i> التصريح</a></li>
                    <li><a href="#" data-page="contact"><i class="fas fa-envelope"></i> اتصل بنا</a></li>
                `;
            }
        }
        
        // تحديث القائمة الجانبية
        function updateSidebarMenu() {
            const sidebarMenu = document.getElementById('sidebarMenu');
            const user = AppState.currentUser;
            
            let menuItems = '';
            
            // عناصر القائمة العامة
            menuItems += `
                <li><a href="#" data-page="dashboard" class="active"><i class="fas fa-tachometer-alt"></i> لوحة التحكم</a></li>
                <li><a href="#" data-page="profile"><i class="fas fa-user"></i> الملف الشخصي</a></li>
                <li><a href="#" data-page="memberships"><i class="fas fa-id-card"></i> الاشتراكات</a></li>
                <li><a href="#" data-page="payments"><i class="fas fa-credit-card"></i> المدفوعات</a></li>
                <li><a href="#" data-page="reports"><i class="fas fa-chart-bar"></i> التقارير</a></li>
            `;
            
            // عناصر القائمة للمسؤولين فقط
            if (user.role === 'admin') {
                menuItems += `
                    <li><a href="#" data-page="users"><i class="fas fa-users"></i> إدارة المستخدمين</a></li>
                    <li><a href="#" data-page="finance"><i class="fas fa-money-bill-wave"></i> الإدارة المالية</a></li>
                    <li><a href="#" data-page="settings"><i class="fas fa-cog"></i> الإعدادات</a></li>
                `;
            }
            
            sidebarMenu.innerHTML = menuItems;
        }
        
        // ========================================
        // معالجة الصفحات والتنقل
        // ========================================
        function showPage(pageId) {
            AppState.currentPage = pageId;
            
            // تحديث حالة الروابط النشطة
            document.querySelectorAll('nav a, .sidebar-menu a').forEach(link => {
                link.classList.remove('active');
                if (link.getAttribute('data-page') === pageId) {
                    link.classList.add('active');
                }
            });
            
            // إخفاء جميع الأقسام
            const sections = ['home', 'about', 'registration', 'plans', 'payment', 'tracking', 'license', 'contact'];
            sections.forEach(section => {
                const element = document.getElementById(section);
                if (element) element.style.display = 'none';
            });
            
            // إخفاء لوحة التحكم إذا لم تكن صفحة لوحة التحكم
            if (!AppState.isLoggedIn || pageId !== 'dashboard') {
                document.getElementById('dashboardContainer').style.display = 'none';
                document.getElementById('mainContentArea').style.display = 'block';
                
                // إظهار القسم المطلوب
                const targetSection = document.getElementById(pageId);
                if (targetSection) {
                    targetSection.style.display = 'block';
                    
                    // تحميل محتوى الصفحة
                    loadPageContent(pageId);
                }
                
                // إظهار التذييل للزوار
                document.getElementById('footer').style.display = 'block';
            } else {
                // إظهار لوحة التحكم
                document.getElementById('dashboardContainer').style.display = 'flex';
                document.getElementById('mainContentArea').style.display = 'none';
                document.getElementById('footer').style.display = 'none';
                
                // تحميل محتوى لوحة التحكم
                loadDashboardContent(pageId);
            }
            
            // إغلاق القائمة المتنقلة على الأجهزة الصغيرة
            if (window.innerWidth <= 992) {
                document.getElementById('mainNav').classList.remove('show');
            }
        }
        
        // تحميل محتوى الصفحة
        function loadPageContent(pageId) {
            switch(pageId) {
                case 'home':
                    loadHomePage();
                    break;
                case 'about':
                    loadAboutPage();
                    break;
                case 'registration':
                    loadRegistrationPage();
                    break;
                case 'plans':
                    loadPlansPage();
                    break;
                case 'payment':
                    loadPaymentPage();
                    break;
                case 'tracking':
                    loadTrackingPage();
                    break;
                case 'contact':
                    loadContactPage();
                    break;
            }
        }
        
        // تحميل محتوى لوحة التحكم
        function loadDashboardContent(pageId) {
            const dashboardContent = document.getElementById('dashboardContent');
            
            switch(pageId) {
                case 'dashboard':
                    loadDashboard();
                    break;
                case 'profile':
                    loadProfilePage();
                    break;
                case 'memberships':
                    loadMembershipsPage();
                    break;
                case 'payments':
                    loadPaymentsPage();
                    break;
                case 'reports':
                    loadReportsPage();
                    break;
                case 'users':
                    loadUsersPage();
                    break;
                case 'finance':
                    loadFinancePage();
                    break;
                case 'settings':
                    loadSettingsPage();
                    break;
            }
        }
        
        // ========================================
        // تحميل صفحات الموقع
        // ========================================
        function loadHomePage() {
            const heroButtons = document.getElementById('heroButtons');
            
            if (AppState.isLoggedIn) {
                heroButtons.innerHTML = `
                    <a href="#" data-page="dashboard" class="btn btn-primary" style="margin-left: 15px;">
                        <i class="fas fa-tachometer-alt"></i> الانتقال إلى لوحة التحكم
                    </a>
                    <a href="#" data-page="profile" class="btn">
                        <i class="fas fa-user"></i> الملف الشخصي
                    </a>
                `;
            } else {
                heroButtons.innerHTML = `
                    <a href="#" data-page="registration" class="btn">سجل الآن</a>
                    <a href="#" data-page="payment" class="btn btn-primary" style="margin-right: 15px;">
                        <i class="fas fa-credit-card"></i> ادفع الآن
                    </a>
                `;
            }
        }
        
        function loadAboutPage() {
            const aboutContent = document.getElementById('aboutContent');
            aboutContent.innerHTML = `
                <div style="display: flex; gap: 40px; align-items: center; margin-bottom: 50px;">
                    <div style="flex: 1;">
                        <h3 style="color: var(--primary-color); margin-bottom: 20px;">رسالتنا وأهدافنا</h3>
                        <p>تأسست جمعية الخير والإحسان عام 2010 بهدف تقديم المساعدات العاجلة والمستدامة للمحتاجين في المجتمع. نحن نعمل تحت إشراف وزارة الموارد البشرية والتنمية الاجتماعية برقم ترخيص 12345.</p>
                        <p>تهدف الجمعية إلى تحقيق التكافل الاجتماعي من خلال برامج متنوعة تشمل:</p>
                        <ul style="list-style: none; margin: 20px 0; padding-right: 20px;">
                            <li style="margin-bottom: 10px; padding-right: 25px; position: relative;">
                                <i class="fas fa-check-circle" style="color: var(--secondary-color); position: absolute; right: 0;"></i>
                                تقديم المساعدات المالية والعينية للأسر المتعففة
                            </li>
                            <li style="margin-bottom: 10px; padding-right: 25px; position: relative;">
                                <i class="fas fa-check-circle" style="color: var(--secondary-color); position: absolute; right: 0;"></i>
                                تنفيذ مشاريع تنموية مستدامة
                            </li>
                            <li style="margin-bottom: 10px; padding-right: 25px; position: relative;">
                                <i class="fas fa-check-circle" style="color: var(--secondary-color); position: absolute; right: 0;"></i>
                                برامج كفالة الأيتام والأرامل
                            </li>
                            <li style="margin-bottom: 10px; padding-right: 25px; position: relative;">
                                <i class="fas fa-check-circle" style="color: var(--secondary-color); position: absolute; right: 0;"></i>
                                توزيع السلال الغذائية في المناسبات
                            </li>
                            <li style="margin-bottom: 10px; padding-right: 25px; position: relative;">
                                <i class="fas fa-check-circle" style="color: var(--secondary-color); position: absolute; right: 0;"></i>
                                برامج التوعية الصحية والتعليمية
                            </li>
                        </ul>
                        <p>نحن نؤمن بأن العمل الخيري المنظم قادر على إحداث تغيير إيجابي في حياة الأفراد والمجتمعات.</p>
                    </div>
                    <div style="flex: 1; border-radius: 10px; overflow: hidden; box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);">
                        <img src="https://images.unsplash.com/photo-1551836026-d5c2c5af78e4?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80" alt="نشاطات الجمعية" style="width: 100%; height: auto; display: block;">
                    </div>
                </div>
                
                <div style="background-color: var(--light-color); border-radius: 10px; padding: 40px; margin-top: 40px;">
                    <h3 style="color: var(--primary-color); margin-bottom: 30px; text-align: center;">إحصائيات الجمعية</h3>
                    <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 20px;">
                        <div style="text-align: center;">
                            <div style="font-size: 2.5rem; font-weight: bold; color: var(--primary-color);">2,500+</div>
                            <div style="color: #666;">عضو مسجل</div>
                        </div>
                        <div style="text-align: center;">
                            <div style="font-size: 2.5rem; font-weight: bold; color: var(--primary-color);">1,200+</div>
                            <div style="color: #666;">أسرة مستفيدة</div>
                        </div>
                        <div style="text-align: center;">
                            <div style="font-size: 2.5rem; font-weight: bold; color: var(--primary-color);">5M+</div>
                            <div style="color: #666;">ريال تبرعات</div>
                        </div>
                        <div style="text-align: center;">
                            <div style="font-size: 2.5rem; font-weight: bold; color: var(--primary-color);">50+</div>
                            <div style="color: #666;">مشروع منفذ</div>
                        </div>
                    </div>
                </div>
            `;
        }
        
        function loadRegistrationPage() {
            const registrationFormContainer = document.getElementById('registrationFormContainer');
            registrationFormContainer.innerHTML = `
                <form id="membershipRegistrationForm">
                    <div style="display: flex; gap: 20px; margin-bottom: 20px;">
                        <div style="flex: 1;">
                            <label for="fullName">الاسم الكامل *</label>
                            <input type="text" id="fullName" class="form-control" required>
                        </div>
                        <div style="flex: 1;">
                            <label for="nationalId">رقم الهوية *</label>
                            <input type="text" id="nationalId" class="form-control" required>
                        </div>
                    </div>
                    
                    <div style="display: flex; gap: 20px; margin-bottom: 20px;">
                        <div style="flex: 1;">
                            <label for="phone">رقم الجوال *</label>
                            <input type="tel" id="phone" class="form-control" required>
                        </div>
                        <div style="flex: 1;">
                            <label for="email">البريد الإلكتروني</label>
                            <input type="email" id="email" class="form-control">
                        </div>
                    </div>
                    
                    <div style="display: flex; gap: 20px; margin-bottom: 20px;">
                        <div style="flex: 1;">
                            <label for="city">المدينة *</label>
                            <select id="city" class="form-control" required>
                                <option value="">اختر المدينة</option>
                                <option value="الرياض">الرياض</option>
                                <option value="جدة">جدة</option>
                                <option value="مكة">مكة</option>
                                <option value="المدينة">المدينة</option>
                                <option value="الدمام">الدمام</option>
                                <option value="أبها">أبها</option>
                                <option value="حائل">حائل</option>
                            </select>
                        </div>
                        <div style="flex: 1;">
                            <label for="birthDate">تاريخ الميلاد</label>
                            <input type="date" id="birthDate" class="form-control">
                        </div>
                    </div>
                    
                    <div style="margin-bottom: 20px;">
                        <label for="address">العنوان التفصيلي</label>
                        <textarea id="address" class="form-control" rows="3"></textarea>
                    </div>
                    
                    <div style="margin-bottom: 30px;">
                        <label for="plan">اختر خطة العضوية *</label>
                        <select id="plan" class="form-control" required>
                            <option value="">اختر خطة الاشتراك</option>
                            <option value="basic">العضوية الأساسية (100 ريال/شهرياً)</option>
                            <option value="silver">العضوية الفضية (250 ريال/شهرياً)</option>
                            <option value="gold">العضوية الذهبية (500 ريال/شهرياً)</option>
                            <option value="platinum">العضوية البلاتينية (1000 ريال/شهرياً)</option>
                        </select>
                    </div>
                    
                    <button type="submit" class="btn btn-primary" style="width: 100%;">
                        <i class="fas fa-user-plus"></i> تسجيل العضوية
                    </button>
                </form>
            `;
            
            // إضافة معالج للنموذج
            document.getElementById('membershipRegistrationForm').addEventListener('submit', async function(e) {
                e.preventDefault();
                
                // جمع بيانات النموذج
                const formData = {
                    fullName: document.getElementById('fullName').value,
                    nationalId: document.getElementById('nationalId').value,
                    phone: document.getElementById('phone').value,
                    email: document.getElementById('email').value,
                    city: document.getElementById('city').value,
                    birthDate: document.getElementById('birthDate').value,
                    address: document.getElementById('address').value,
                    plan: document.getElementById('plan').value,
                    submittedAt: new Date().toISOString()
                };
                
                // حفظ في التخزين المحلي
                localStorage.setItem('membershipApplication', JSON.stringify(formData));
                
                // إرسال إشعار
                if (AppState.isLoggedIn) {
                    await db.addNotification({
                        userId: AppState.currentUser.id,
                        title: 'طلب عضوية جديد',
                        message: `تم تقديم طلب عضوية لخطة ${formData.plan}`,
                        type: 'info',
                        icon: 'fa-user-plus',
                        read: false,
                        createdAt: new Date().toISOString()
                    });
                }
                
                showToast('تم تقديم طلب العضوية بنجاح! سنقوم بالتواصل معك قريباً.', 'success');
                
                // إعادة تعيين النموذج
                this.reset();
                
                // الانتقال إلى صفحة الدفع
                showPage('payment');
            });
        }
        
        function loadPlansPage() {
            const plansContainer = document.getElementById('plansContainer');
            plansContainer.innerHTML = `
                <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 30px;">
                    <div style="background-color: white; border-radius: 10px; overflow: hidden; box-shadow: 0 5px 20px rgba(0, 0, 0, 0.08); transition: transform 0.3s;">
                        <div style="background-color: var(--primary-color); color: white; padding: 25px; text-align: center;">
                            <h3 style="margin-bottom: 10px;">العضوية الأساسية</h3>
                            <div style="font-size: 2.2rem; font-weight: bold; margin-bottom: 5px;">100 ريال</div>
                            <div>شهرياً</div>
                        </div>
                        <div style="padding: 25px;">
                            <ul style="list-style: none; margin-bottom: 25px; padding-right: 0;">
                                <li style="padding: 8px 0; border-bottom: 1px solid #eee; position: relative; padding-right: 25px;">
                                    <i class="fas fa-check" style="color: var(--secondary-color); position: absolute; right: 0;"></i>
                                    بطاقة عضوية أساسية
                                </li>
                                <li style="padding: 8px 0; border-bottom: 1px solid #eee; position: relative; padding-right: 25px;">
                                    <i class="fas fa-check" style="color: var(--secondary-color); position: absolute; right: 0;"></i>
                                    تقرير سنوي عن أنشطة الجمعية
                                </li>
                                <li style="padding: 8px 0; border-bottom: 1px solid #eee; position: relative; padding-right: 25px;">
                                    <i class="fas fa-check" style="color: var(--secondary-color); position: absolute; right: 0;"></i>
                                    دعوات للفعاليات الخيرية
                                </li>
                                <li style="padding: 8px 0; position: relative; padding-right: 25px;">
                                    <i class="fas fa-check" style="color: var(--secondary-color); position: absolute; right: 0;"></i>
                                    مشاركة في توزيع السلال الغذائية
                                </li>
                            </ul>
                            <button class="btn select-plan-btn" data-plan="basic" data-amount="100" style="width: 100%;">
                                <i class="fas fa-check"></i> اختر هذه الخطة
                            </button>
                        </div>
                    </div>
                    
                    <div style="background-color: white; border-radius: 10px; overflow: hidden; box-shadow: 0 5px 20px rgba(0, 0, 0, 0.08); transition: transform 0.3s;">
                        <div style="background-color: #6c757d; color: white; padding: 25px; text-align: center;">
                            <h3 style="margin-bottom: 10px;">العضوية الفضية</h3>
                            <div style="font-size: 2.2rem; font-weight: bold; margin-bottom: 5px;">250 ريال</div>
                            <div>شهرياً</div>
                        </div>
                        <div style="padding: 25px;">
                            <ul style="list-style: none; margin-bottom: 25px; padding-right: 0;">
                                <li style="padding: 8px 0; border-bottom: 1px solid #eee; position: relative; padding-right: 25px;">
                                    <i class="fas fa-check" style="color: var(--secondary-color); position: absolute; right: 0;"></i>
                                    جميع مزايا العضوية الأساسية
                                </li>
                                <li style="padding: 8px 0; border-bottom: 1px solid #eee; position: relative; padding-right: 25px;">
                                    <i class="fas fa-check" style="color: var(--secondary-color); position: absolute; right: 0;"></i>
                                    اسمك في قائمة الداعمين على الموقع
                                </li>
                                <li style="padding: 8px 0; border-bottom: 1px solid #eee; position: relative; padding-right: 25px;">
                                    <i class="fas fa-check" style="color: var(--secondary-color); position: absolute; right: 0;"></i>
                                    مشاركة في تحديد أولويات المشاريع
                                </li>
                                <li style="padding: 8px 0; position: relative; padding-right: 25px;">
                                    <i class="fas fa-check" style="color: var(--secondary-color); position: absolute; right: 0;"></i>
                                    تقرير ربع سنوي مفصل
                                </li>
                            </ul>
                            <button class="btn select-plan-btn" data-plan="silver" data-amount="250" style="width: 100%;">
                                <i class="fas fa-check"></i> اختر هذه الخطة
                            </button>
                        </div>
                    </div>
                    
                    <div style="background-color: white; border-radius: 10px; overflow: hidden; box-shadow: 0 5px 20px rgba(0, 0, 0, 0.08); transition: transform 0.3s; position: relative;">
                        <div style="position: absolute; top: 20px; left: -30px; background-color: var(--accent-color); color: white; padding: 5px 30px; transform: rotate(-45deg); font-size: 0.8rem; font-weight: bold; z-index: 1;">
                            الأكثر اختياراً
                        </div>
                        <div style="background-color: #ffc107; color: #212529; padding: 25px; text-align: center;">
                            <h3 style="margin-bottom: 10px;">العضوية الذهبية</h3>
                            <div style="font-size: 2.2rem; font-weight: bold; margin-bottom: 5px;">500 ريال</div>
                            <div>شهرياً</div>
                        </div>
                        <div style="padding: 25px;">
                            <ul style="list-style: none; margin-bottom: 25px; padding-right: 0;">
                                <li style="padding: 8px 0; border-bottom: 1px solid #eee; position: relative; padding-right: 25px;">
                                    <i class="fas fa-check" style="color: var(--secondary-color); position: absolute; right: 0;"></i>
                                    جميع مزايا العضوية الفضية
                                </li>
                                <li style="padding: 8px 0; border-bottom: 1px solid #eee; position: relative; padding-right: 25px;">
                                    <i class="fas fa-check" style="color: var(--secondary-color); position: absolute; right: 0;"></i>
                                    زيارات ميدانية للمشاريع
                                </li>
                                <li style="padding: 8px 0; border-bottom: 1px solid #eee; position: relative; padding-right: 25px;">
                                    <i class="fas fa-check" style="color: var(--secondary-color); position: absolute; right: 0;"></i>
                                    شهادة داعم ذهبي
                                </li>
                                <li style="padding: 8px 0; border-bottom: 1px solid #eee; position: relative; padding-right: 25px;">
                                    <i class="fas fa-check" style="color: var(--secondary-color); position: absolute; right: 0;"></i>
                                    دعوات حصرية للفعاليات
                                </li>
                                <li style="padding: 8px 0; position: relative; padding-right: 25px;">
                                    <i class="fas fa-check" style="color: var(--secondary-color); position: absolute; right: 0;"></i>
                                    تسمية مشروع باسمك
                                </li>
                            </ul>
                            <button class="btn btn-primary select-plan-btn" data-plan="gold" data-amount="500" style="width: 100%;">
                                <i class="fas fa-crown"></i> اختر هذه الخطة
                            </button>
                        </div>
                    </div>
                    
                    <div style="background-color: white; border-radius: 10px; overflow: hidden; box-shadow: 0 5px 20px rgba(0, 0, 0, 0.08); transition: transform 0.3s;">
                        <div style="background-color: #17a2b8; color: white; padding: 25px; text-align: center;">
                            <h3 style="margin-bottom: 10px;">العضوية البلاتينية</h3>
                            <div style="font-size: 2.2rem; font-weight: bold; margin-bottom: 5px;">1000 ريال</div>
                            <div>شهرياً</div>
                        </div>
                        <div style="padding: 25px;">
                            <ul style="list-style: none; margin-bottom: 25px; padding-right: 0;">
                                <li style="padding: 8px 0; border-bottom: 1px solid #eee; position: relative; padding-right: 25px;">
                                    <i class="fas fa-check" style="color: var(--secondary-color); position: absolute; right: 0;"></i>
                                    جميع مزايا العضوية الذهبية
                                </li>
                                <li style="padding: 8px 0; border-bottom: 1px solid #eee; position: relative; padding-right: 25px;">
                                    <i class="fas fa-check" style="color: var(--secondary-color); position: absolute; right: 0;"></i>
                                    عضوية في المجلس الاستشاري
                                </li>
                                <li style="padding: 8px 0; border-bottom: 1px solid #eee; position: relative; padding-right: 25px;">
                                    <i class="fas fa-check" style="color: var(--secondary-color); position: absolute; right: 0;"></i>
                                    زيارات شخصية من رئيس الجمعية
                                </li>
                                <li style="padding: 8px 0; border-bottom: 1px solid #eee; position: relative; padding-right: 25px;">
                                    <i class="fas fa-check" style="color: var(--secondary-color); position: absolute; right: 0;"></i>
                                    تقارير شهرية مفصلة
                                </li>
                                <li style="padding: 8px 0; position: relative; padding-right: 25px;">
                                    <i class="fas fa-check" style="color: var(--secondary-color); position: absolute; right: 0;"></i>
                                    لوحة شكر في مقر الجمعية
                                </li>
                            </ul>
                            <button class="btn select-plan-btn" data-plan="platinum" data-amount="1000" style="width: 100%;">
                                <i class="fas fa-gem"></i> اختر هذه الخطة
                            </button>
                        </div>
                    </div>
                </div>
            `;
            
            // إضافة معالج لأزرار اختيار الخطط
            document.querySelectorAll('.select-plan-btn').forEach(button => {
                button.addEventListener('click', function() {
                    const plan = this.getAttribute('data-plan');
                    const amount = this.getAttribute('data-amount');
                    
                    // حفظ الخطة المختارة
                    localStorage.setItem('selectedPlan', plan);
                    localStorage.setItem('selectedAmount', amount);
                    
                    showToast(`تم اختيار خطة ${plan} بقيمة ${amount} ريال شهرياً`, 'success');
                    
                    // الانتقال إلى صفحة التسجيل
                    showPage('registration');
                });
            });
        }
        
        // ========================================
        // تحميل لوحة التحكم
        // ========================================
        async function loadDashboard() {
            const dashboardContent = document.getElementById('dashboardContent');
            const user = AppState.currentUser;
            
            // إحصائيات لوحة التحكم
            const stats = await calculateDashboardStats();
            
            dashboardContent.innerHTML = `
                <div class="section-title">
                    <h2>مرحباً ${user.name.split(' ')[0]} 👋</h2>
                    <p>لوحة تحكم جمعية الخير والإحسان - آخر تحديث: ${formatDate(new Date())}</p>
                </div>
                
                <div class="stats-grid">
                    <div class="stat-card green">
                        <div class="stat-header">
                            <div>
                                <div class="stat-value">${stats.totalMembers}</div>
                                <div class="stat-label">إجمالي الأعضاء</div>
                            </div>
                            <div class="stat-icon green">
                                <i class="fas fa-users"></i>
                            </div>
                        </div>
                        <div class="stat-change positive">
                            <i class="fas fa-arrow-up"></i> 12% زيادة هذا الشهر
                        </div>
                    </div>
                    
                    <div class="stat-card blue">
                        <div class="stat-header">
                            <div>
                                <div class="stat-value">${stats.activeMemberships}</div>
                                <div class="stat-label">اشتراكات نشطة</div>
                            </div>
                            <div class="stat-icon blue">
                                <i class="fas fa-id-card"></i>
                            </div>
                        </div>
                        <div class="stat-change positive">
                            <i class="fas fa-arrow-up"></i> 8% زيادة هذا الشهر
                        </div>
                    </div>
                    
                    <div class="stat-card orange">
                        <div class="stat-header">
                            <div>
                                <div class="stat-value">${stats.totalRevenue} ريال</div>
                                <div class="stat-label">إجمالي الإيرادات</div>
                            </div>
                            <div class="stat-icon orange">
                                <i class="fas fa-money-bill-wave"></i>
                            </div>
                        </div>
                        <div class="stat-change positive">
                            <i class="fas fa-arrow-up"></i> 15% زيادة هذا الشهر
                        </div>
                    </div>
                    
                    <div class="stat-card red">
                        <div class="stat-header">
                            <div>
                                <div class="stat-value">${stats.pendingPayments}</div>
                                <div class="stat-label">مدفوعات معلقة</div>
                            </div>
                            <div class="stat-icon red">
                                <i class="fas fa-clock"></i>
                            </div>
                        </div>
                        <div class="stat-change negative">
                            <i class="fas fa-arrow-down"></i> 5% زيادة هذا الشهر
                        </div>
                    </div>
                </div>
                
                <div class="charts-container">
                    <div class="chart-card">
                        <div class="chart-header">
                            <h3 class="chart-title">إحصائيات الاشتراكات</h3>
                            <select id="chartPeriod" class="form-control" style="width: 150px;">
                                <option value="monthly">شهري</option>
                                <option value="quarterly">ربع سنوي</option>
                                <option value="yearly">سنوي</option>
                            </select>
                        </div>
                        <div class="chart-container">
                            <canvas id="membershipsChart"></canvas>
                        </div>
                    </div>
                    
                    <div class="chart-card">
                        <div class="chart-header">
                            <h3 class="chart-title">توزيع المدفوعات</h3>
                            <div>
                                <button class="btn btn-sm btn-primary" id="refreshCharts">
                                    <i class="fas fa-sync-alt"></i> تحديث
                                </button>
                            </div>
                        </div>
                        <div class="chart-container">
                            <canvas id="paymentsChart"></canvas>
                        </div>
                    </div>
                </div>
                
                <div style="margin-top: 40px;">
                    <div class="section-title">
                        <h3>آخر المدفوعات</h3>
                    </div>
                    <div class="table-responsive">
                        <table class="data-table">
                            <thead>
                                <tr>
                                    <th>رقم المرجع</th>
                                    <th>العضو</th>
                                    <th>المبلغ</th>
                                    <th>طريقة الدفع</th>
                                    <th>التاريخ</th>
                                    <th>الحالة</th>
                                </tr>
                            </thead>
                            <tbody id="recentPaymentsTable">
                                <!-- سيتم تعبئة الجدول ديناميكياً -->
                            </tbody>
                        </table>
                    </div>
                </div>
            `;
            
            // تحميل الرسوم البيانية
            loadCharts();
            
            // تحميل المدفوعات الأخيرة
            loadRecentPayments();
        }
        
        async function calculateDashboardStats() {
            // في التطبيق الحقيقي، سيتم حساب هذه الإحصائيات من قاعدة البيانات
            // هنا نستخدم بيانات وهمية للعرض التوضيحي
            return {
                totalMembers: AppState.users.length,
                activeMemberships: 45,
                totalRevenue: '125,000',
                pendingPayments: 12
            };
        }
        
        function loadCharts() {
            // تدمير الرسوم البيانية السابقة إذا كانت موجودة
            if (charts.membershipsChart) {
                charts.membershipsChart.destroy();
            }
            if (charts.paymentsChart) {
                charts.paymentsChart.destroy();
            }
            
            // رسم بياني للاشتراكات
            const membershipsCtx = document.getElementById('membershipsChart').getContext('2d');
            charts.membershipsChart = new Chart(membershipsCtx, {
                type: 'line',
                data: {
                    labels: ['يناير', 'فبراير', 'مارس', 'أبريل', 'مايو', 'يونيو'],
                    datasets: [{
                        label: 'اشتراكات جديدة',
                        data: [12, 19, 15, 25, 22, 30],
                        borderColor: 'rgb(75, 192, 192)',
                        backgroundColor: 'rgba(75, 192, 192, 0.2)',
                        tension: 0.4
                    }, {
                        label: 'تجديد اشتراكات',
                        data: [8, 12, 10, 18, 15, 22],
                        borderColor: 'rgb(255, 159, 64)',
                        backgroundColor: 'rgba(255, 159, 64, 0.2)',
                        tension: 0.4
                    }]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    plugins: {
                        legend: {
                            position: 'top',
                            rtl: true
                        }
                    },
                    scales: {
                        y: {
                            beginAtZero: true,
                            ticks: {
                                stepSize: 5
                            }
                        }
                    }
                }
            });
            
            // رسم بياني دائري للمدفوعات
            const paymentsCtx = document.getElementById('paymentsChart').getContext('2d');
            charts.paymentsChart = new Chart(paymentsCtx, {
                type: 'doughnut',
                data: {
                    labels: ['الراجحي', 'الأهلي', 'بطاقات ائتمان', 'نقدي'],
                    datasets: [{
                        data: [45, 30, 15, 10],
                        backgroundColor: [
                            'rgba(0, 167, 157, 0.8)',
                            'rgba(227, 6, 19, 0.8)',
                            'rgba(54, 162, 235, 0.8)',
                            'rgba(255, 206, 86, 0.8)'
                        ],
                        borderWidth: 1
                    }]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    plugins: {
                        legend: {
                            position: 'left',
                            rtl: true
                        }
                    }
                }
            });
        }
        
        function loadRecentPayments() {
            const tableBody = document.getElementById('recentPaymentsTable');
            
            // بيانات وهمية للمدفوعات الأخيرة
            const recentPayments = [
                { id: 'PAY-001', member: 'أحمد محمد', amount: '500 ريال', method: 'الراجحي', date: '2023-09-15', status: 'مكتمل' },
                { id: 'PAY-002', member: 'سالم عبدالله', amount: '250 ريال', method: 'الأهلي', date: '2023-09-14', status: 'مكتمل' },
                { id: 'PAY-003', member: 'فاطمة خالد', amount: '1000 ريال', method: 'الراجحي', date: '2023-09-13', status: 'معلق' },
                { id: 'PAY-004', member: 'خالد سعود', amount: '500 ريال', method: 'بطاقة ائتمان', date: '2023-09-12', status: 'مكتمل' },
                { id: 'PAY-005', member: 'نورة أحمد', amount: '100 ريال', method: 'نقدي', date: '2023-09-11', status: 'ملغى' }
            ];
            
            tableBody.innerHTML = recentPayments.map(payment => `
                <tr>
                    <td>${payment.id}</td>
                    <td>${payment.member}</td>
                    <td>${payment.amount}</td>
                    <td>${payment.method}</td>
                    <td>${payment.date}</td>
                    <td>
                        <span class="status-badge ${payment.status === 'مكتمل' ? 'active' : payment.status === 'معلق' ? 'pending' : 'inactive'}">
                            ${payment.status}
                        </span>
                    </td>
                </tr>
            `).join('');
        }
        
        // ========================================
        // وظائف المساعدة
        // ========================================
        function formatDate(date) {
            return new Date(date).toLocaleDateString('ar-SA', {
                year: 'numeric',
                month: 'long',
                day: 'numeric'
            });
        }
        
        function formatTime(date) {
            const now = new Date();
            const inputDate = new Date(date);
            const diffMs = now - inputDate;
            const diffMins = Math.floor(diffMs / 60000);
            const diffHours = Math.floor(diffMs / 3600000);
            const diffDays = Math.floor(diffMs / 86400000);
            
            if (diffMins < 60) {
                return `قبل ${diffMins} دقيقة`;
            } else if (diffHours < 24) {
                return `قبل ${diffHours} ساعة`;
            } else if (diffDays < 7) {
                return `قبل ${diffDays} يوم`;
            } else {
                return formatDate(date);
            }
        }
        
        function getRoleName(role) {
            const roles = {
                'admin': 'مسؤول',
                'member': 'عضو',
                'donor': 'متبرع',
                'volunteer': 'متطوع'
            };
            return roles[role] || role;
        }
        
        function showToast(message, type = 'info') {
            const backgroundColor = type === 'success' ? '#28a745' : 
                                  type === 'warning' ? '#ffc107' : 
                                  type === 'error' ? '#dc3545' : '#17a2b8';
            
            Toastify({
                text: message,
                duration: 4000,
                gravity: "top",
                position: "left",
                backgroundColor: backgroundColor,
                stopOnFocus: true,
                className: "toastify-ar",
                rtl: true
            }).showToast();
        }
        
        // ========================================
        // معالجة تسجيل الدخول والتسجيل
        // ========================================
        async function handleLogin(email, password) {
            try {
                const user = await db.getUserByEmail(email);
                
                if (!user) {
                    showToast('البريد الإلكتروني أو كلمة المرور غير صحيحة', 'error');
                    return false;
                }
                
                if (user.password !== password) {
                    showToast('البريد الإلكتروني أو كلمة المرور غير صحيحة', 'error');
                    return false;
                }
                
                if (user.status !== 'active') {
                    showToast('حسابك غير نشط. يرجى التواصل مع الإدارة.', 'warning');
                    return false;
                }
                
                // تحديث حالة التطبيق
                AppState.currentUser = user;
                AppState.isLoggedIn = true;
                
                // حفظ جلسة المستخدم
                localStorage.setItem('currentUser', JSON.stringify({
                    id: user.id,
                    email: user.email,
                    password: user.password
                }));
                
                // تحديث واجهة المستخدم
                updateUIForAuthState();
                
                // إضافة إشعار تسجيل دخول
                await db.addNotification({
                    userId: user.id,
                    title: 'تسجيل دخول ناجح',
                    message: `تم تسجيل دخولك إلى النظام في ${formatDate(new Date())}`,
                    type: 'success',
                    icon: 'fa-sign-in-alt',
                    read: false,
                    createdAt: new Date().toISOString()
                });
                
                showToast(`مرحباً بعودتك ${user.name.split(' ')[0]}!`, 'success');
                
                // الانتقال إلى لوحة التحكم
                showPage('dashboard');
                
                return true;
                
            } catch (error) {
                console.error('خطأ في تسجيل الدخول:', error);
                showToast('حدث خطأ أثناء تسجيل الدخول. يرجى المحاولة مرة أخرى.', 'error');
                return false;
            }
        }
        
        async function handleRegister(userData) {
            try {
                // التحقق من وجود مستخدم بنفس البريد الإلكتروني
                const existingUser = await db.getUserByEmail(userData.email);
                
                if (existingUser) {
                    showToast('هذا البريد الإلكتروني مستخدم بالفعل', 'warning');
                    return false;
                }
                
                // إنشاء لون افتراضي للصورة الرمزية
                const colors = ['#2E7D32', '#4CAF50', '#FF9800', '#2196F3', '#9C27B0'];
                const randomColor = colors[Math.floor(Math.random() * colors.length)];
                
                // إنشاء المستخدم الجديد
                const newUser = {
                    name: userData.name,
                    email: userData.email,
                    password: userData.password,
                    phone: userData.phone,
                    role: userData.role,
                    status: 'active',
                    createdAt: new Date().toISOString(),
                    avatarColor: randomColor
                };
                
                // حفظ المستخدم في قاعدة البيانات
                const userId = await db.addUser(newUser);
                newUser.id = userId;
                
                // تحديث حالة التطبيق
                AppState.users.push(newUser);
                
                showToast(`تم إنشاء حسابك بنجاح! مرحباً ${newUser.name.split(' ')[0]}`, 'success');
                
                // تسجيل الدخول تلقائياً
                await handleLogin(newUser.email, newUser.password);
                
                return true;
                
            } catch (error) {
                console.error('خطأ في التسجيل:', error);
                showToast('حدث خطأ أثناء إنشاء الحساب. يرجى المحاولة مرة أخرى.', 'error');
                return false;
            }
        }
        
        async function handleLogout() {
            // إضافة إشعار تسجيل خروج
            if (AppState.currentUser) {
                await db.addNotification({
                    userId: AppState.currentUser.id,
                    title: 'تسجيل خروج',
                    message: 'تم تسجيل خروجك من النظام',
                    type: 'info',
                    icon: 'fa-sign-out-alt',
                    read: false,
                    createdAt: new Date().toISOString()
                });
            }
            
            // تحديث حالة التطبيق
            AppState.currentUser = null;
            AppState.isLoggedIn = false;
            
            // حذف جلسة المستخدم
            localStorage.removeItem('currentUser');
            
            // تحديث واجهة المستخدم
            updateUIForAuthState();
            
            // الانتقال إلى الصفحة الرئيسية
            showPage('home');
            
            showToast('تم تسجيل الخروج بنجاح', 'info');
        }
        
        // ========================================
        // تعيين معالجي الأحداث
        // ========================================
        function setupEventListeners() {
            // القائمة المتنقلة
            document.getElementById('mobileMenuBtn').addEventListener('click', function() {
                document.getElementById('mainNav').classList.toggle('show');
            });
            
            // التنقل بين الصفحات
            document.addEventListener('click', function(e) {
                // التنقل عبر الروابط
                if (e.target.matches('[data-page]') || e.target.closest('[data-page]')) {
                    e.preventDefault();
                    const link = e.target.matches('[data-page]') ? e.target : e.target.closest('[data-page]');
                    const pageId = link.getAttribute('data-page');
                    showPage(pageId);
                }
                
                // فتح/إغلاق القائمة الجانبية
                if (e.target.id === 'sidebarToggle' || e.target.closest('#sidebarToggle')) {
                    document.getElementById('sidebar').classList.toggle('collapsed');
                    document.getElementById('mainContent').classList.toggle('expanded');
                }
            });
            
            // تسجيل الدخول
            document.addEventListener('click', function(e) {
                if (e.target.id === 'loginBtn' || e.target.closest('#loginBtn')) {
                    e.preventDefault();
                    document.getElementById('loginModal').style.display = 'block';
                }
                
                if (e.target.id === 'showRegister' || e.target.closest('#showRegister')) {
                    e.preventDefault();
                    document.getElementById('loginModal').style.display = 'none';
                    document.getElementById('registerModal').style.display = 'block';
                }
            });
            
            // التسجيل
            document.addEventListener('click', function(e) {
                if (e.target.id === 'registerBtn' || e.target.closest('#registerBtn')) {
                    e.preventDefault();
                    document.getElementById('registerModal').style.display = 'block';
                }
                
                if (e.target.id === 'showLogin' || e.target.closest('#showLogin')) {
                    e.preventDefault();
                    document.getElementById('registerModal').style.display = 'none';
                    document.getElementById('loginModal').style.display = 'block';
                }
            });
            
            // إغلاق النماذج
            document.addEventListener('click', function(e) {
                if (e.target.classList.contains('modal') || 
                    e.target.id === 'closePaymentModal' || 
                    e.target.id === 'closeConfirmation' ||
                    e.target.id === 'closeSimulationModal' ||
                    e.target.id === 'closeSimulation' ||
                    e.target.id === 'closeUserManagementModal') {
                    
                    e.target.closest('.modal').style.display = 'none';
                }
            });
            
            // إغلاق النماذج بالزر ESC
            document.addEventListener('keydown', function(e) {
                if (e.key === 'Escape') {
                    document.querySelectorAll('.modal').forEach(modal => {
                        modal.style.display = 'none';
                    });
                }
            });
            
            // نموذج تسجيل الدخول
            document.getElementById('loginForm').addEventListener('submit', async function(e) {
                e.preventDefault();
                
                const email = document.getElementById('loginEmail').value;
                const password = document.getElementById('loginPassword').value;
                
                await handleLogin(email, password);
                
                if (AppState.isLoggedIn) {
                    document.getElementById('loginModal').style.display = 'none';
                    this.reset();
                }
            });
            
            // نموذج التسجيل
            document.getElementById('registerForm').addEventListener('submit', async function(e) {
                e.preventDefault();
                
                const name = document.getElementById('registerName').value;
                const email = document.getElementById('registerEmail').value;
                const phone = document.getElementById('registerPhone').value;
                const password = document.getElementById('registerPassword').value;
                const confirmPassword = document.getElementById('registerConfirmPassword').value;
                const role = document.getElementById('registerRole').value;
                
                if (password !== confirmPassword) {
                    showToast('كلمتا المرور غير متطابقتين', 'error');
                    return;
                }
                
                const userData = { name, email, phone, password, role };
                
                await handleRegister(userData);
                
                if (AppState.isLoggedIn) {
                    document.getElementById('registerModal').style.display = 'none';
                    this.reset();
                }
            });
            
            // تسجيل الخروج
            document.addEventListener('click', function(e) {
                if (e.target.id === 'logoutBtn' || e.target.closest('#logoutBtn')) {
                    e.preventDefault();
                    handleLogout();
                }
            });
            
            // الإشعارات
            document.addEventListener('click', function(e) {
                if (e.target.id === 'notificationsBtn' || e.target.closest('#notificationsBtn')) {
                    e.preventDefault();
                    document.getElementById('notificationsDropdown').classList.toggle('show');
                }
                
                // إغلاق قائمة الإشعارات عند النقر خارجها
                window.addEventListener('click', function(event) {
                    const notificationsDropdown = document.getElementById('notificationsDropdown');
                    const notificationsBtn = document.getElementById('notificationsBtn');
                    
                    if (notificationsDropdown && notificationsBtn && 
                        !notificationsDropdown.contains(event.target) && 
                        !notificationsBtn.contains(event.target)) {
                        
                        notificationsDropdown.classList.remove('show');
                    }
                });
            });
        }
        
        // ========================================
        // بدء تشغيل التطبيق
        // ========================================
        window.addEventListener('DOMContentLoaded', initializeApp);
    </script>
</body>
</html>
