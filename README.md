<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portofolio Profesional - Developer & Researcher</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&family=Raleway:wght@400;500;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary-color: #2c3e50;
            --secondary-color: #3498db;
            --accent-color: #e74c3c;
            --light-color: #ecf0f1;
            --dark-color: #1a1a2e;
            --success-color: #27ae60;
            --shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            --transition: all 0.3s ease;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Poppins', sans-serif;
            line-height: 1.6;
            color: #333;
            background-color: #f9f9f9;
            overflow-x: hidden;
        }

        h1, h2, h3, h4 {
            font-family: 'Raleway', sans-serif;
            font-weight: 700;
            margin-bottom: 1rem;
            color: var(--primary-color);
        }

        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }

        /* Header & Navigation */
        header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            background-color: rgba(255, 255, 255, 0.95);
            box-shadow: var(--shadow);
            z-index: 1000;
            transition: var(--transition);
        }

        header.scrolled {
            padding: 5px 0;
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 0;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--primary-color);
            text-decoration: none;
        }

        .logo span {
            color: var(--secondary-color);
        }

        .nav-links {
            display: flex;
            list-style: none;
        }

        .nav-links li {
            margin-left: 2rem;
        }

        .nav-links a {
            text-decoration: none;
            color: var(--primary-color);
            font-weight: 500;
            transition: var(--transition);
            position: relative;
        }

        .nav-links a:hover {
            color: var(--secondary-color);
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background-color: var(--secondary-color);
            transition: var(--transition);
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .menu-toggle {
            display: none;
            font-size: 1.5rem;
            cursor: pointer;
        }

        /* Hero Section */
        .hero {
            padding: 150px 0 80px;
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            width: 300px;
            height: 300px;
            border-radius: 50%;
            background: rgba(52, 152, 219, 0.1);
            top: -150px;
            right: -100px;
        }

        .hero::after {
            content: '';
            position: absolute;
            width: 200px;
            height: 200px;
            border-radius: 50%;
            background: rgba(231, 76, 60, 0.1);
            bottom: -100px;
            left: -50px;
        }

        .hero-content {
            display: flex;
            align-items: center;
            justify-content: space-between;
            position: relative;
            z-index: 1;
        }

        .hero-text {
            flex: 1;
            padding-right: 2rem;
        }

        .hero-text h1 {
            font-size: 3.5rem;
            line-height: 1.2;
            margin-bottom: 1.5rem;
            animation: fadeInUp 1s ease;
        }

        .hero-text h1 span {
            color: var(--secondary-color);
        }

        .hero-text p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            color: #555;
            animation: fadeInUp 1s ease 0.2s both;
        }

        .btn {
            display: inline-block;
            padding: 12px 30px;
            background-color: var(--secondary-color);
            color: white;
            text-decoration: none;
            border-radius: 5px;
            font-weight: 500;
            transition: var(--transition);
            border: none;
            cursor: pointer;
            animation: fadeInUp 1s ease 0.4s both;
        }

        .btn:hover {
            background-color: var(--primary-color);
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
        }

        .hero-image {
            flex: 1;
            text-align: center;
            animation: fadeInRight 1s ease;
        }

        .profile-img {
            width: 300px;
            height: 300px;
            border-radius: 50%;
            object-fit: cover;
            border: 10px solid white;
            box-shadow: var(--shadow);
            animation: float 3s ease-in-out infinite;
        }

        /* Section Styling */
        section {
            padding: 80px 0;
        }

        .section-title {
            text-align: center;
            margin-bottom: 3rem;
            position: relative;
        }

        .section-title h2 {
            font-size: 2.5rem;
            display: inline-block;
            position: relative;
            padding-bottom: 10px;
        }

        .section-title h2::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background-color: var(--secondary-color);
            border-radius: 2px;
        }

        /* Portfolio Section */
        .portfolio-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 30px;
        }

        .portfolio-item {
            background-color: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
            opacity: 0;
            transform: translateY(30px);
        }

        .portfolio-item.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .portfolio-item:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.15);
        }

        .portfolio-img {
            width: 100%;
            height: 200px;
            object-fit: cover;
            transition: var(--transition);
        }

        .portfolio-item:hover .portfolio-img {
            transform: scale(1.05);
        }

        .portfolio-info {
            padding: 20px;
        }

        .portfolio-info h3 {
            margin-bottom: 10px;
            font-size: 1.3rem;
        }

        .portfolio-info p {
            color: #666;
            margin-bottom: 15px;
        }

        /* Articles Section */
        .articles-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 30px;
        }

        .article-card {
            background-color: white;
            border-radius: 10px;
            padding: 25px;
            box-shadow: var(--shadow);
            transition: var(--transition);
            opacity: 0;
            transform: translateY(30px);
        }

        .article-card.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .article-card:hover {
            transform: translateY(-5px);
        }

        .article-category {
            display: inline-block;
            padding: 5px 15px;
            background-color: var(--light-color);
            color: var(--primary-color);
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 500;
            margin-bottom: 15px;
        }

        .research { background-color: #e8f4fc; color: var(--secondary-color); }
        .tutorial { background-color: #f0f7e9; color: var(--success-color); }
        .opinion { background-color: #fef5e7; color: #e67e22; }

        .article-card h3 {
            margin-bottom: 10px;
        }

        .article-card p {
            color: #666;
            margin-bottom: 20px;
        }

        .article-link {
            display: inline-flex;
            align-items: center;
            color: var(--secondary-color);
            text-decoration: none;
            font-weight: 500;
        }

        .article-link i {
            margin-left: 5px;
            transition: var(--transition);
        }

        .article-link:hover i {
            transform: translateX(5px);
        }

        /* Activities Section */
        .timeline {
            position: relative;
            max-width: 800px;
            margin: 0 auto;
        }

        .timeline::before {
            content: '';
            position: absolute;
            left: 50%;
            transform: translateX(-50%);
            width: 4px;
            height: 100%;
            background-color: var(--secondary-color);
        }

        .timeline-item {
            margin-bottom: 40px;
            position: relative;
            width: 45%;
            opacity: 0;
            transform: translateY(30px);
        }

        .timeline-item.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .timeline-item:nth-child(odd) {
            left: 0;
        }

        .timeline-item:nth-child(even) {
            left: 55%;
        }

        .timeline-content {
            background-color: white;
            padding: 20px;
            border-radius: 10px;
            box-shadow: var(--shadow);
            position: relative;
        }

        .timeline-item:nth-child(odd) .timeline-content::after {
            content: '';
            position: absolute;
            right: -10px;
            top: 20px;
            width: 0;
            height: 0;
            border-top: 10px solid transparent;
            border-bottom: 10px solid transparent;
            border-left: 10px solid white;
        }

        .timeline-item:nth-child(even) .timeline-content::after {
            content: '';
            position: absolute;
            left: -10px;
            top: 20px;
            width: 0;
            height: 0;
            border-top: 10px solid transparent;
            border-bottom: 10px solid transparent;
            border-right: 10px solid white;
        }

        .timeline-icon {
            position: absolute;
            left: 50%;
            transform: translateX(-50%);
            width: 40px;
            height: 40px;
            background-color: var(--secondary-color);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 1.2rem;
            z-index: 1;
        }

        /* Skills Section */
        .skills-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 30px;
        }

        .skill-category {
            background-color: white;
            padding: 25px;
            border-radius: 10px;
            box-shadow: var(--shadow);
            transition: var(--transition);
            opacity: 0;
            transform: translateY(30px);
        }

        .skill-category.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .skill-category:hover {
            transform: translateY(-5px);
        }

        .skill-category h3 {
            display: flex;
            align-items: center;
            margin-bottom: 20px;
        }

        .skill-category h3 i {
            margin-right: 10px;
            color: var(--secondary-color);
        }

        .skill-list {
            list-style: none;
        }

        .skill-list li {
            margin-bottom: 15px;
            display: flex;
            justify-content: space-between;
        }

        .skill-bar {
            height: 8px;
            background-color: #eee;
            border-radius: 4px;
            margin-top: 5px;
            overflow: hidden;
        }

        .skill-level {
            height: 100%;
            border-radius: 4px;
            background-color: var(--secondary-color);
            transition: width 1.5s ease;
        }

        /* Contact Section */
        .contact-container {
            display: flex;
            flex-wrap: wrap;
            gap: 50px;
        }

        .contact-info {
            flex: 1;
            min-width: 300px;
        }

        .contact-card {
            background-color: white;
            padding: 25px;
            border-radius: 10px;
            box-shadow: var(--shadow);
            margin-bottom: 30px;
            transition: var(--transition);
        }

        .contact-card:hover {
            transform: translateY(-5px);
        }

        .contact-card h3 {
            display: flex;
            align-items: center;
            margin-bottom: 20px;
        }

        .contact-card h3 i {
            margin-right: 10px;
            color: var(--secondary-color);
        }

        .social-links {
            display: flex;
            gap: 15px;
            margin-top: 20px;
        }

        .social-links a {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background-color: var(--primary-color);
            color: white;
            border-radius: 50%;
            text-decoration: none;
            transition: var(--transition);
        }

        .social-links a:hover {
            background-color: var(--secondary-color);
            transform: translateY(-3px);
        }

        .download-cv {
            margin-top: 20px;
        }

        /* Footer */
        footer {
            background-color: var(--dark-color);
            color: white;
            padding: 40px 0;
            text-align: center;
        }

        .footer-content {
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .footer-logo {
            font-size: 2rem;
            font-weight: 700;
            margin-bottom: 20px;
        }

        .footer-logo span {
            color: var(--secondary-color);
        }

        .copyright {
            margin-top: 20px;
            color: #aaa;
            font-size: 0.9rem;
        }

        /* Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fadeInRight {
            from {
                opacity: 0;
                transform: translateX(30px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        @keyframes float {
            0%, 100% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(-15px);
            }
        }

        /* Responsive Design */
        @media (max-width: 992px) {
            .hero-content {
                flex-direction: column;
                text-align: center;
            }
            
            .hero-text {
                padding-right: 0;
                margin-bottom: 40px;
            }
            
            .hero-text h1 {
                font-size: 2.8rem;
            }
            
            .timeline::before {
                left: 30px;
            }
            
            .timeline-item {
                width: 100%;
                left: 0 !important;
                padding-left: 70px;
            }
            
            .timeline-icon {
                left: 30px;
            }
            
            .timeline-item:nth-child(odd) .timeline-content::after,
            .timeline-item:nth-child(even) .timeline-content::after {
                left: -10px;
                border-right: 10px solid white;
                border-left: none;
            }
        }

        @media (max-width: 768px) {
            .menu-toggle {
                display: block;
            }
            
            .nav-links {
                position: fixed;
                top: 70px;
                left: -100%;
                width: 100%;
                height: calc(100vh - 70px);
                background-color: white;
                flex-direction: column;
                align-items: center;
                justify-content: flex-start;
                padding-top: 50px;
                transition: var(--transition);
                box-shadow: var(--shadow);
            }
            
            .nav-links.active {
                left: 0;
            }
            
            .nav-links li {
                margin: 15px 0;
            }
            
            .hero-text h1 {
                font-size: 2.2rem;
            }
            
            .section-title h2 {
                font-size: 2rem;
            }
        }
    </style>
</head>
<body>
    <!-- Header & Navigation -->
    <header id="header">
        <div class="container">
            <nav>
                <a href="#" class="logo">Porto<span>folio</span></a>
                <div class="menu-toggle" id="menuToggle">
                    <i class="fas fa-bars"></i>
                </div>
                <ul class="nav-links">
                    <li><a href="#home">Beranda</a></li>
                    <li><a href="#portfolio">Portofolio</a></li>
                    <li><a href="#articles">Artikel</a></li>
                    <li><a href="#activities">Kegiatan</a></li>
                    <li><a href="#skills">Skill</a></li>
                    <li><a href="#contact">Kontak</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="container">
            <div class="hero-content">
                <div class="hero-text">
                    <h1>Halo, Saya <span>Alex Chandra</span></h1>
                    <p>Full Stack Developer & AI Researcher dengan pengalaman 5+ tahun dalam pengembangan web dan penelitian kecerdasan buatan. Saya bersemangat menciptakan solusi inovatif yang menggabungkan teknologi terbaru dengan desain yang menarik.</p>
                    <a href="#portfolio" class="btn">Lihat Proyek Saya</a>
                </div>
                <div class="hero-image">
                    <img src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=774&q=80" alt="Foto Profil" class="profile-img">
                </div>
            </div>
        </div>
    </section>

    <!-- Portfolio Section -->
    <section id="portfolio">
        <div class="container">
            <div class="section-title">
                <h2>Portofolio Proyek</h2>
                <p>Beberapa proyek terbaik yang telah saya kembangkan</p>
            </div>
            <div class="portfolio-grid">
                <div class="portfolio-item">
                    <img src="https://images.unsplash.com/photo-1551650975-87deedd944c3?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1674&q=80" alt="Proyek E-Commerce" class="portfolio-img">
                    <div class="portfolio-info">
                        <h3>Sistem E-Commerce Modern</h3>
                        <p>Aplikasi e-commerce lengkap dengan React, Node.js, dan MongoDB. Fitur keranjang belanja, pembayaran online, dan dashboard admin.</p>
                        <a href="#" class="btn">Lihat di GitHub</a>
                    </div>
                </div>
                <div class="portfolio-item">
                    <img src="https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1770&q=80" alt="Analisis Data" class="portfolio-img">
                    <div class="portfolio-info">
                        <h3>Dashboard Analisis Data</h3>
                        <p>Dashboard interaktif untuk visualisasi data menggunakan Python, D3.js, dan Flask. Menampilkan insight bisnis secara real-time.</p>
                        <a href="#" class="btn">Lihat di GitHub</a>
                    </div>
                </div>
                <div class="portfolio-item">
                    <img src="https://images.unsplash.com/photo-1531746790731-6c087fecd65a?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1818&q=80" alt="Aplikasi Mobile" class="portfolio-img">
                    <div class="portfolio-info">
                        <h3>Aplikasi Mobile Kesehatan</h3>
                        <p>Aplikasi React Native untuk monitoring kesehatan dengan fitur pelacakan aktivitas, kalori, dan koneksi ke wearable devices.</p>
                        <a href="#" class="btn">Lihat di GitHub</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Articles Section -->
    <section id="articles" style="background-color: #f5f7fa;">
        <div class="container">
            <div class="section-title">
                <h2>Artikel & Jurnal</h2>
                <p>Publikasi dan tulisan tentang teknologi dan penelitian</p>
            </div>
            <div class="articles-container">
                <div class="article-card">
                    <span class="article-category research">Penelitian</span>
                    <h3>Implementasi Machine Learning untuk Deteksi Dini Penyakit Jantung</h3>
                    <p>Studi tentang penggunaan algoritma Random Forest dan SVM dalam menganalisis data medis untuk prediksi penyakit kardiovaskular dengan akurasi 94%.</p>
                    <a href="#" class="article-link">Baca PDF <i class="fas fa-arrow-right"></i></a>
                </div>
                <div class="article-card">
                    <span class="article-category tutorial">Tutorial</span>
                    <h3>Membangun REST API dengan Node.js dan Express</h3>
                    <p>Panduan lengkap untuk mengembangkan RESTful API yang scalable dengan autentikasi JWT, validasi data, dan dokumentasi Swagger.</p>
                    <a href="#" class="article-link">Baca Artikel <i class="fas fa-arrow-right"></i></a>
                </div>
                <div class="article-card">
                    <span class="article-category opinion">Opini</span>
                    <h3>Masa Depan Web Development di Era AI</h3>
                    <p>Analisis tentang bagaimana kecerdasan buatan akan mengubah landscape pengembangan web dalam 5-10 tahun ke depan.</p>
                    <a href="#" class="article-link">Baca Artikel <i class="fas fa-arrow-right"></i></a>
                </div>
            </div>
        </div>
    </section>

    <!-- Activities Section -->
    <section id="activities">
        <div class="container">
            <div class="section-title">
                <h2>Kegiatan Personal</h2>
                <p>Pengalaman, volunteering, dan sertifikasi</p>
            </div>
            <div class="timeline">
                <div class="timeline-item">
                    <div class="timeline-icon">
                        <i class="fas fa-hands-helping"></i>
                    </div>
                    <div class="timeline-content">
                        <h3>Volunteer Tech Mentor</h3>
                        <p>Code For Indonesia (2022 - Sekarang)</p>
                        <p>Membimbing siswa SMA/SMK dalam belajar pemrograman dasar dan pengembangan web.</p>
                    </div>
                </div>
                <div class="timeline-item">
                    <div class="timeline-icon">
                        <i class="fas fa-certificate"></i>
                    </div>
                    <div class="timeline-content">
                        <h3>AWS Certified Developer</h3>
                        <p>Amazon Web Services (2023)</p>
                        <p>Sertifikasi profesional untuk pengembangan aplikasi di platform AWS.</p>
                    </div>
                </div>
                <div class="timeline-item">
                    <div class="timeline-icon">
                        <i class="fas fa-camera"></i>
                    </div>
                    <div class="timeline-content">
                        <h3>Fotografi Landscape</h3>
                        <p>Hobi (2018 - Sekarang)</p>
                        <p>Eksplorasi fotografi alam dan perkotaan. Beberapa karya dipamerkan di pameran lokal.</p>
                    </div>
                </div>
                <div class="timeline-item">
                    <div class="timeline-icon">
                        <i class="fas fa-chalkboard-teacher"></i>
                    </div>
                    <div class="timeline-content">
                        <h3>Workshop Full-Stack Development</h3>
                        <p>Universitas Teknologi Digital (2023)</p>
                        <p>Menyelenggarakan workshop 2 hari tentang pengembangan aplikasi web modern.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Skills Section -->
    <section id="skills" style="background-color: #f5f7fa;">
        <div class="container">
            <div class="section-title">
                <h2>Keterampilan Teknis</h2>
                <p>Kompetensi dan teknologi yang saya kuasai</p>
            </div>
            <div class="skills-container">
                <div class="skill-category">
                    <h3><i class="fas fa-code"></i> Frontend</h3>
                    <ul class="skill-list">
                        <li>React.js <span>95%</span>
                            <div class="skill-bar"><div class="skill-level" style="width: 95%"></div></div>
                        </li>
                        <li>Vue.js <span>85%</span>
                            <div class="skill-bar"><div class="skill-level" style="width: 85%"></div></div>
                        </li>
                        <li>JavaScript/ES6+ <span>98%</span>
                            <div class="skill-bar"><div class="skill-level" style="width: 98%"></div></div>
                        </li>
                        <li>HTML/CSS <span>99%</span>
                            <div class="skill-bar"><div class="skill-level" style="width: 99%"></div></div>
                        </li>
                    </ul>
                </div>
                <div class="skill-category">
                    <h3><i class="fas fa-server"></i> Backend</h3>
                    <ul class="skill-list">
                        <li>Node.js <span>92%</span>
                            <div class="skill-bar"><div class="skill-level" style="width: 92%"></div></div>
                        </li>
                        <li>Python/Django <span>88%</span>
                            <div class="skill-bar"><div class="skill-level" style="width: 88%"></div></div>
                        </li>
                        <li>PostgreSQL <span>90%</span>
                            <div class="skill-bar"><div class="skill-level" style="width: 90%"></div></div>
                        </li>
                        <li>MongoDB <span>85%</span>
                            <div class="skill-bar"><div class="skill-level" style="width: 85%"></div></div>
                        </li>
                    </ul>
                </div>
                <div class="skill-category">
                    <h3><i class="fas fa-tools"></i> Lainnya</h3>
                    <ul class="skill-list">
                        <li>Git/GitHub <span>96%</span>
                            <div class="skill-bar"><div class="skill-level" style="width: 96%"></div></div>
                        </li>
                        <li>Docker <span>80%</span>
                            <div class="skill-bar"><div class="skill-level" style="width: 80%"></div></div>
                        </li>
                        <li>UI/UX Design <span>75%</span>
                            <div class="skill-bar"><div class="skill-level" style="width: 75%"></div></div>
                        </li>
                        <li>Machine Learning <span>70%</span>
                            <div class="skill-bar"><div class="skill-level" style="width: 70%"></div></div>
                        </li>
                    </ul>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact">
        <div class="container">
            <div class="section-title">
                <h2>Kontak & CV</h2>
                <p>Hubungi saya untuk kolaborasi atau unduh CV lengkap</p>
            </div>
            <div class="contact-container">
                <div class="contact-info">
                    <div class="contact-card">
                        <h3><i class="fas fa-envelope"></i> Email</h3>
                        <p>alex.chandra@example.com</p>
                    </div>
                    <div class="contact-card">
                        <h3><i class="fas fa-map-marker-alt"></i> Lokasi</h3>
                        <p>Jakarta, Indonesia</p>
                    </div>
                    <div class="contact-card">
                        <h3><i class="fas fa-download"></i> Download CV</h3>
                        <p>Unduh CV lengkap saya dalam format PDF</p>
                        <a href="#" class="btn download-cv">Download CV</a>
                    </div>
                </div>
                <div class="contact-info">
                    <div class="contact-card">
                        <h3><i class="fas fa-share-alt"></i> Media Sosial</h3>
                        <p>Terhubung dengan saya melalui platform berikut:</p>
                        <div class="social-links">
                            <a href="#"><i class="fab fa-github"></i></a>
                            <a href="#"><i class="fab fa-linkedin-in"></i></a>
                            <a href="#"><i class="fab fa-twitter"></i></a>
                            <a href="#"><i class="fab fa-instagram"></i></a>
                        </div>
                    </div>
                    <div class="contact-card">
                        <h3><i class="fas fa-paper-plane"></i> Kirim Pesan</h3>
                        <p>Ingin berkolaborasi atau punya pertanyaan?</p>
                        <a href="mailto:alex.chandra@example.com" class="btn">Kirim Email</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <a href="#" class="footer-logo">Porto<span>folio</span></a>
                <p>Full Stack Developer & AI Researcher</p>
                <p class="copyright">© 2023 Alex Chandra. Semua hak dilindungi.</p>
            </div>
        </div>
    </footer>

    <script>
        // Mobile Menu Toggle
        const menuToggle = document.getElementById('menuToggle');
        const navLinks = document.querySelector('.nav-links');
        
        menuToggle.addEventListener('click', () => {
            navLinks.classList.toggle('active');
        });
        
        // Close menu when clicking a link
        document.querySelectorAll('.nav-links a').forEach(link => {
            link.addEventListener('click', () => {
                navLinks.classList.remove('active');
            });
        });
        
        // Header scroll effect
        window.addEventListener('scroll', () => {
            const header = document.getElementById('header');
            if (window.scrollY > 50) {
                header.classList.add('scrolled');
            } else {
                header.classList.remove('scrolled');
            }
        });
        
        // Scroll animation for elements
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };
        
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                }
            });
        }, observerOptions);
        
        // Observe elements for animation
        document.querySelectorAll('.portfolio-item, .article-card, .timeline-item, .skill-category').forEach(el => {
            observer.observe(el);
        });
        
        // Animate skill bars on scroll
        const skillObserver = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    const skillLevels = entry.target.querySelectorAll('.skill-level');
                    skillLevels.forEach(level => {
                        // Already animated via inline style, just trigger reflow if needed
                        const width = level.style.width;
                        level.style.width = '0';
                        setTimeout(() => {
                            level.style.width = width;
                        }, 100);
                    });
                }
            });
        }, {threshold: 0.5});
        
        document.querySelectorAll('.skill-category').forEach(el => {
            skillObserver.observe(el);
        });
        
        // Smooth scrolling for anchor links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                
                const targetId = this.getAttribute('href');
                if(targetId === '#') return;
                
                const targetElement = document.querySelector(targetId);
                if(targetElement) {
                    window.scrollTo({
                        top: targetElement.offsetTop - 80,
                        behavior: 'smooth'
                    });
                }
            });
        });
    </script>
</body>
</html>
