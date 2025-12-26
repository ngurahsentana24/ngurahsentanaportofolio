<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ngurah Sentana | Data Scientist & Computer Science Portfolio</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&family=Space+Grotesk:wght@300;400;500;600;700&family=JetBrains+Mono:wght@300;400;500&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://unpkg.com/3d-force-graph/dist/3d-force-graph.css">
    <style>
        :root {
            --primary-color: #ffffff;
            --secondary-color: #1a1a2e;
            --accent-color: #2563eb;
            --accent-light: #3b82f6;
            --accent-dark: #1d4ed8;
            --success-color: #10b981;
            --warning-color: #f59e0b;
            --danger-color: #ef4444;
            --light-gray: #f8fafc;
            --medium-gray: #e2e8f0;
            --dark-gray: #64748b;
            --glass-bg: rgba(255, 255, 255, 0.85);
            --glass-border: rgba(255, 255, 255, 0.2);
            --shadow: 0 10px 25px rgba(0, 0, 0, 0.05);
            --shadow-lg: 0 20px 40px rgba(0, 0, 0, 0.1);
            --transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.1);
            --border-radius: 16px;
            --border-radius-lg: 24px;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
            overflow-x: hidden;
        }

        body {
            font-family: 'Inter', sans-serif;
            line-height: 1.6;
            color: #1e293b;
            background-color: var(--primary-color);
            min-height: 100vh;
            overflow-x: hidden;
        }

        h1, h2, h3, h4 {
            font-family: 'Space Grotesk', sans-serif;
            font-weight: 700;
            margin-bottom: 1rem;
            color: var(--secondary-color);
        }

        p {
            color: #475569;
            margin-bottom: 1rem;
        }

        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header & Navigation Minimalis */
        header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(15px);
            z-index: 1000;
            transition: var(--transition);
            border-bottom: 1px solid rgba(0, 0, 0, 0.05);
            padding: 15px 0;
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: 800;
            color: var(--secondary-color);
            text-decoration: none;
            display: flex;
            align-items: center;
            position: relative;
            font-family: 'JetBrains Mono', monospace;
        }

        .logo span {
            color: var(--accent-color);
            margin-left: 5px;
        }

        .logo::after {
            content: '>';
            color: var(--accent-color);
            margin-left: 5px;
            animation: blink 1s infinite;
        }

        @keyframes blink {
            0%, 100% { opacity: 1; }
            50% { opacity: 0; }
        }

        .nav-links {
            display: flex;
            list-style: none;
        }

        .nav-links li {
            margin-left: 2.5rem;
            position: relative;
        }

        .nav-links a {
            text-decoration: none;
            color: var(--secondary-color);
            font-weight: 500;
            transition: var(--transition);
            position: relative;
            padding: 5px 0;
            font-size: 0.95rem;
            font-family: 'JetBrains Mono', monospace;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background: linear-gradient(90deg, var(--accent-color), var(--accent-light));
            transition: width 0.3s ease;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .nav-links a:hover {
            color: var(--accent-color);
        }

        .menu-toggle {
            display: none;
            font-size: 1.5rem;
            cursor: pointer;
            color: var(--secondary-color);
        }

        /* Hero Section dengan Asimetri */
        .hero {
            padding: 180px 0 100px;
            position: relative;
            overflow: hidden;
            background: linear-gradient(135deg, #f0f9ff 0%, #fef2f2 100%);
            border-radius: 0 0 80px 80px;
        }

        .hero::before {
            content: '';
            position: absolute;
            width: 600px;
            height: 600px;
            border-radius: 50%;
            background: radial-gradient(circle, rgba(59, 130, 246, 0.05) 0%, rgba(59, 130, 246, 0) 70%);
            top: -300px;
            right: -200px;
            z-index: 0;
        }

        .hero::after {
            content: '';
            position: absolute;
            width: 400px;
            height: 400px;
            border-radius: 50%;
            background: radial-gradient(circle, rgba(239, 68, 68, 0.05) 0%, rgba(239, 68, 68, 0) 70%);
            bottom: -200px;
            left: -150px;
            z-index: 0;
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
            padding-right: 3rem;
            max-width: 600px;
        }

        .hero-text h1 {
            font-size: 4rem;
            line-height: 1.1;
            margin-bottom: 1.5rem;
            background: linear-gradient(90deg, var(--secondary-color), var(--accent-color));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            position: relative;
        }

        .hero-text h1::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 0;
            width: 100px;
            height: 5px;
            background: linear-gradient(90deg, var(--accent-color), var(--accent-light));
            border-radius: 5px;
        }

        .hero-text p {
            font-size: 1.2rem;
            margin-bottom: 2.5rem;
            max-width: 500px;
            color: #4b5563;
        }

        .btn {
            display: inline-flex;
            align-items: center;
            padding: 14px 35px;
            background: linear-gradient(90deg, var(--accent-color), var(--accent-light));
            color: white;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            transition: var(--transition);
            border: none;
            cursor: pointer;
            position: relative;
            overflow: hidden;
            z-index: 1;
            box-shadow: var(--shadow);
            font-family: 'Inter', sans-serif;
        }

        .btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 0;
            height: 100%;
            background: linear-gradient(90deg, var(--accent-dark), var(--accent-color));
            transition: width 0.5s ease;
            z-index: -1;
            border-radius: 50px;
        }

        .btn:hover::before {
            width: 100%;
        }

        .btn:hover {
            transform: translateY(-5px);
            box-shadow: var(--shadow-lg);
        }

        .btn-outline {
            background: transparent;
            border: 2px solid var(--accent-color);
            color: var(--accent-color);
        }

        .btn-outline:hover {
            background: var(--accent-color);
            color: white;
        }

        .hero-image {
            flex: 1;
            text-align: center;
            position: relative;
        }

        .profile-img-container {
            position: relative;
            display: inline-block;
            border-radius: var(--border-radius-lg);
            overflow: hidden;
            transform: rotate(3deg);
            box-shadow: var(--shadow-lg);
        }

        .profile-img {
            width: 400px;
            height: 500px;
            object-fit: cover;
            transition: var(--transition);
            filter: grayscale(0.2) contrast(1.1);
        }

        .profile-img-container:hover {
            transform: rotate(0deg);
        }

        .profile-img-container::before {
            content: '';
            position: absolute;
            top: 20px;
            left: -20px;
            right: 20px;
            bottom: -20px;
            border-radius: var(--border-radius-lg);
            background: linear-gradient(45deg, var(--accent-color), var(--success-color));
            z-index: -1;
            opacity: 0.5;
            filter: blur(20px);
        }

        /* Foto Session Grid */
        .photo-session {
            padding: 100px 0;
            background-color: var(--light-gray);
            border-radius: 80px 80px 0 0;
            margin-top: -50px;
            position: relative;
            z-index: 2;
        }

        .photo-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 20px;
            margin-top: 40px;
        }

        .photo-item {
            height: 300px;
            border-radius: var(--border-radius);
            overflow: hidden;
            position: relative;
            box-shadow: var(--shadow);
            transition: var(--transition);
        }

        .photo-item:hover {
            transform: translateY(-10px);
            box-shadow: var(--shadow-lg);
        }

        .photo-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
        }

        .photo-item:hover img {
            transform: scale(1.1);
        }

        /* Ask Me Section */
        .ask-me-section {
            padding: 100px 0;
            background-color: white;
        }

        .ask-container {
            display: flex;
            gap: 50px;
            align-items: center;
        }

        .ask-form-container {
            flex: 1;
        }

        .ask-form {
            background: var(--glass-bg);
            backdrop-filter: blur(10px);
            border: 1px solid var(--glass-border);
            border-radius: var(--border-radius);
            padding: 40px;
            box-shadow: var(--shadow);
        }

        .form-group {
            margin-bottom: 25px;
        }

        .form-group label {
            display: block;
            margin-bottom: 10px;
            font-weight: 600;
            color: var(--secondary-color);
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 15px;
            border: 1px solid var(--medium-gray);
            border-radius: 10px;
            font-family: 'Inter', sans-serif;
            font-size: 1rem;
            transition: var(--transition);
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: var(--accent-color);
            box-shadow: 0 0 0 3px rgba(37, 99, 235, 0.1);
        }

        .ask-response {
            flex: 1;
            background: linear-gradient(135deg, #f0f9ff 0%, #e0f2fe 100%);
            border-radius: var(--border-radius);
            padding: 40px;
            box-shadow: var(--shadow);
            min-height: 300px;
            position: relative;
            overflow: hidden;
        }

        .response-header {
            display: flex;
            align-items: center;
            margin-bottom: 20px;
        }

        .response-header i {
            font-size: 1.5rem;
            color: var(--accent-color);
            margin-right: 15px;
        }

        .response-content {
            font-size: 1.1rem;
            line-height: 1.8;
            color: #374151;
        }

        .response-placeholder {
            color: var(--dark-gray);
            font-style: italic;
        }

        /* Download CV Section */
        .download-cv-section {
            padding: 80px 0;
            background: linear-gradient(135deg, #f8fafc 0%, #f1f5f9 100%);
            text-align: center;
        }

        .download-card {
            background: white;
            border-radius: var(--border-radius);
            padding: 50px;
            box-shadow: var(--shadow-lg);
            max-width: 600px;
            margin: 0 auto;
            position: relative;
            overflow: hidden;
        }

        .download-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 8px;
            height: 100%;
            background: linear-gradient(to bottom, var(--accent-color), var(--success-color));
        }

        .download-icon {
            font-size: 3rem;
            color: var(--accent-color);
            margin-bottom: 20px;
        }

        .download-btn {
            margin-top: 30px;
            display: inline-flex;
            align-items: center;
            gap: 10px;
        }

        /* Cards Grid Section */
        .cards-section {
            padding: 100px 0;
            background-color: white;
        }

        .section-title {
            text-align: center;
            margin-bottom: 4rem;
            position: relative;
        }

        .section-title h2 {
            font-size: 3rem;
            display: inline-block;
            position: relative;
            padding-bottom: 15px;
        }

        .section-title h2::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 5px;
            background: linear-gradient(90deg, var(--accent-color), var(--accent-light));
            border-radius: 5px;
        }

        .section-title p {
            color: var(--dark-gray);
            font-size: 1.1rem;
            max-width: 600px;
            margin: 1rem auto 0;
        }

        .cards-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 30px;
        }

        .card {
            background: white;
            border-radius: var(--border-radius);
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
            border: 1px solid var(--medium-gray);
            cursor: pointer;
            position: relative;
        }

        .card:hover {
            transform: translateY(-15px);
            box-shadow: var(--shadow-lg);
            border-color: var(--accent-color);
        }

        .card-header {
            padding: 25px 25px 15px;
            position: relative;
        }

        .card-icon {
            font-size: 2rem;
            color: var(--accent-color);
            margin-bottom: 15px;
        }

        .card-badge {
            position: absolute;
            top: 20px;
            right: 20px;
            padding: 5px 15px;
            background: var(--success-color);
            color: white;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 600;
        }

        .card-badge.ongoing {
            background: var(--warning-color);
        }

        .card-content {
            padding: 0 25px 25px;
        }

        .card-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            margin-top: 15px;
        }

        .tag {
            padding: 5px 12px;
            background: #eff6ff;
            color: var(--accent-color);
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 500;
        }

        /* Competency Network Section */
        .competency-section {
            padding: 100px 0;
            background: linear-gradient(135deg, #f8fafc 0%, #e0e7ff 100%);
        }

        .competency-container {
            display: flex;
            gap: 50px;
            align-items: center;
        }

        .competency-text {
            flex: 1;
        }

        .competency-visualization {
            flex: 1;
            height: 500px;
            border-radius: var(--border-radius);
            overflow: hidden;
            box-shadow: var(--shadow-lg);
            background: white;
        }

        .skill-list {
            list-style: none;
            margin-top: 30px;
        }

        .skill-list li {
            margin-bottom: 15px;
            display: flex;
            align-items: center;
        }

        .skill-list i {
            color: var(--accent-color);
            margin-right: 15px;
            font-size: 1.2rem;
        }

        /* Collaboration Section */
        .collaboration-section {
            padding: 100px 0;
            background-color: white;
            text-align: center;
        }

        .collaboration-logos {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 40px;
            margin-top: 50px;
        }

        .collaboration-logo {
            width: 120px;
            height: 120px;
            background: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: var(--shadow);
            transition: var(--transition);
            font-size: 2.5rem;
            color: var(--accent-color);
        }

        .collaboration-logo:hover {
            transform: translateY(-10px) scale(1.1);
            box-shadow: var(--shadow-lg);
        }

        /* Modal Popup */
        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.7);
            backdrop-filter: blur(5px);
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 2000;
            opacity: 0;
            visibility: hidden;
            transition: all 0.3s ease;
        }

        .modal-overlay.active {
            opacity: 1;
            visibility: visible;
        }

        .modal {
            background: white;
            border-radius: var(--border-radius);
            width: 90%;
            max-width: 800px;
            max-height: 90vh;
            overflow-y: auto;
            box-shadow: var(--shadow-lg);
            position: relative;
            transform: translateY(50px);
            transition: transform 0.4s ease;
        }

        .modal-overlay.active .modal {
            transform: translateY(0);
        }

        .modal-header {
            padding: 30px 30px 20px;
            border-bottom: 1px solid var(--medium-gray);
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .modal-close {
            background: none;
            border: none;
            font-size: 1.5rem;
            cursor: pointer;
            color: var(--dark-gray);
            transition: var(--transition);
        }

        .modal-close:hover {
            color: var(--danger-color);
        }

        .modal-content {
            padding: 30px;
        }

        .modal-footer {
            padding: 20px 30px;
            border-top: 1px solid var(--medium-gray);
            text-align: right;
        }

        /* Footer */
        footer {
            background: var(--secondary-color);
            color: white;
            padding: 70px 0 30px;
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 40px;
            margin-bottom: 50px;
        }

        .footer-column h3 {
            color: white;
            margin-bottom: 25px;
            font-size: 1.3rem;
        }

        .footer-links {
            list-style: none;
        }

        .footer-links li {
            margin-bottom: 12px;
        }

        .footer-links a {
            color: #cbd5e1;
            text-decoration: none;
            transition: var(--transition);
        }

        .footer-links a:hover {
            color: white;
            padding-left: 5px;
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
            background: rgba(255, 255, 255, 0.1);
            color: white;
            border-radius: 50%;
            text-decoration: none;
            transition: var(--transition);
        }

        .social-links a:hover {
            background: var(--accent-color);
            transform: translateY(-5px);
        }

        .copyright {
            text-align: center;
            padding-top: 30px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            color: #94a3b8;
            font-size: 0.9rem;
        }

        /* Responsive Design */
        @media (max-width: 1100px) {
            .hero-content {
                flex-direction: column;
                text-align: center;
            }
            
            .hero-text {
                padding-right: 0;
                margin-bottom: 60px;
                max-width: 100%;
            }
            
            .hero-text h1 {
                font-size: 3.2rem;
            }
            
            .ask-container, .competency-container {
                flex-direction: column;
            }
            
            .footer-content {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        @media (max-width: 768px) {
            .menu-toggle {
                display: block;
            }
            
            .nav-links {
                position: fixed;
                top: 80px;
                left: -100%;
                width: 100%;
                height: calc(100vh - 80px);
                background: rgba(255, 255, 255, 0.98);
                backdrop-filter: blur(20px);
                flex-direction: column;
                align-items: center;
                justify-content: flex-start;
                padding-top: 60px;
                transition: var(--transition);
                border-top: 1px solid rgba(0, 0, 0, 0.05);
            }
            
            .nav-links.active {
                left: 0;
            }
            
            .nav-links li {
                margin: 20px 0;
            }
            
            .hero-text h1 {
                font-size: 2.8rem;
            }
            
            .section-title h2 {
                font-size: 2.5rem;
            }
            
            .profile-img {
                width: 300px;
                height: 400px;
            }
            
            .photo-grid {
                grid-template-columns: 1fr;
            }
            
            .cards-grid {
                grid-template-columns: 1fr;
            }
            
            .footer-content {
                grid-template-columns: 1fr;
            }
        }

        /* Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fadeInRight {
            from {
                opacity: 0;
                transform: translateX(50px);
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

        /* Utility Classes */
        .fade-in {
            animation: fadeInUp 1s ease;
        }

        .float-animation {
            animation: float 6s ease-in-out infinite;
        }
    </style>
</head>
<body>
    <!-- Header & Navigation -->
    <header id="header">
        <div class="container">
            <nav>
                <a href="#" class="logo">NgurahSentana<span>_</span></a>
                <div class="menu-toggle" id="menuToggle">
                    <i class="fas fa-bars"></i>
                </div>
                <ul class="nav-links">
                    <li><a href="#home">Beranda</a></li>
                    <li><a href="#about">Perkenalan</a></li>
                    <li><a href="#projects">Proyek</a></li>
                    <li><a href="#competency">Kompetensi</a></li>
                    <li><a href="#collaboration">Kolaborasi</a></li>
                    <li><a href="#contact">Kontak</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="container">
            <div class="hero-content fade-in">
                <div class="hero-text">
                    <h1>Ngurah Sentana</h1>
                    <p>Data Scientist & Computer Science Specialist dengan fusi keahlian di bidang Statistika, Machine Learning, dan Pengembangan Perangkat Lunak. Menciptakan solusi berbasis data yang elegan dan fungsional.</p>
                    <div style="display: flex; gap: 15px; flex-wrap: wrap;">
                        <a href="#projects" class="btn">Lihat Proyek</a>
                        <a href="#contact" class="btn btn-outline">Hubungi Saya</a>
                    </div>
                </div>
                <div class="hero-image float-animation">
                    <div class="profile-img-container">
                        <img src="https://images.unsplash.com/photo-1568602471122-7832951cc4c5?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80" alt="Foto Ngurah Sentana" class="profile-img">
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Photo Session -->
    <section class="photo-session" id="about">
        <div class="container">
            <div class="section-title">
                <h2>Foto Session</h2>
                <p>Momen dalam eksplorasi data, coding, dan presentasi</p>
            </div>
            <div class="photo-grid">
                <div class="photo-item">
                    <img src="https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80" alt="Analisis Data">
                </div>
                <div class="photo-item">
                    <img src="https://images.unsplash.com/photo-1515879218367-8466d910aaa4?ixlib=rb-4.0.3&auto=format&fit=crop&w=1469&q=80" alt="Coding Session">
                </div>
                <div class="photo-item">
                    <img src="https://images.unsplash.com/photo-1545235617-9465d2a55698?ixlib=rb-4.0.3&auto=format&fit=crop&w=1480&q=80" alt="Presentasi">
                </div>
            </div>
        </div>
    </section>

    <!-- Ask Me Section -->
    <section class="ask-me-section">
        <div class="container">
            <div class="section-title">
                <h2>Tanyakan Saya</h2>
                <p>Ajukan pertanyaan dan dapatkan jawaban yang informatif</p>
            </div>
            <div class="ask-container">
                <div class="ask-form-container">
                    <div class="ask-form">
                        <div class="form-group">
                            <label for="question">Pertanyaan Anda</label>
                            <textarea id="question" rows="6" placeholder="Tulis pertanyaan Anda di sini..."></textarea>
                        </div>
                        <div class="form-group">
                            <label for="email">Email (opsional, untuk notifikasi jawaban)</label>
                            <input type="email" id="email" placeholder="nama@email.com">
                        </div>
                        <button type="button" class="btn" id="askButton">Ajukan Pertanyaan</button>
                    </div>
                </div>
                <div class="ask-response">
                    <div class="response-header">
                        <i class="fas fa-robot"></i>
                        <h3>Jawaban</h3>
                    </div>
                    <div class="response-content" id="responseContent">
                        <p class="response-placeholder">Jawaban akan muncul di sini setelah Anda mengajukan pertanyaan.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Download CV Section -->
    <section class="download-cv-section">
        <div class="container">
            <div class="download-card">
                <div class="download-icon">
                    <i class="fas fa-file-download"></i>
                </div>
                <h2>Curriculum Vitae</h2>
                <p>Unduh CV lengkap saya untuk melihat pengalaman, pendidikan, dan pencapaian profesional secara detail.</p>
                <a href="https://drive.google.com/file/d/1EXAMPLE/view?usp=sharing" target="_blank" class="btn download-btn">
                    <i class="fas fa-download"></i> Download CV (PDF)
                </a>
            </div>
        </div>
    </section>

    <!-- Projects, Articles, Certificates, Experience -->
    <section class="cards-section" id="projects">
        <div class="container">
            <div class="section-title">
                <h2>Portofolio</h2>
                <p>Kumpulan proyek, artikel, sertifikat, dan pengalaman profesional</p>
            </div>
            
            <!-- Proyek -->
            <h3 style="margin-top: 60px; margin-bottom: 30px;">Proyek</h3>
            <div class="cards-grid" id="projectsGrid">
                <!-- Cards akan diisi oleh JavaScript -->
            </div>
            
            <!-- Artikel & Publikasi -->
            <h3 style="margin-top: 60px; margin-bottom: 30px;">Artikel & Publikasi</h3>
            <div class="cards-grid" id="articlesGrid">
                <!-- Cards akan diisi oleh JavaScript -->
            </div>
            
            <!-- Sertifikat -->
            <h3 style="margin-top: 60px; margin-bottom: 30px;">Sertifikat</h3>
            <div class="cards-grid" id="certificatesGrid">
                <!-- Cards akan diisi oleh JavaScript -->
            </div>
            
            <!-- Pengalaman -->
            <h3 style="margin-top: 60px; margin-bottom: 30px;">Pengalaman</h3>
            <div class="cards-grid" id="experienceGrid">
                <!-- Cards akan diisi oleh JavaScript -->
            </div>
        </div>
    </section>

    <!-- Competency Section -->
    <section class="competency-section" id="competency">
        <div class="container">
            <div class="section-title">
                <h2>Kompetensi</h2>
                <p>Keahlian dalam Statistics, Data Science, dan Computer Science</p>
            </div>
            <div class="competency-container">
                <div class="competency-text">
                    <h3>Peta Keahlian Interdisipliner</h3>
                    <p>Saya membangun jembatan antara teori statistika, praktik data science, dan rekayasa perangkat lunak untuk menciptakan solusi yang komprehensif.</p>
                    <ul class="skill-list">
                        <li><i class="fas fa-chart-line"></i> <strong>Statistika:</strong> Analisis Regresi, Bayesian Statistics, Time Series Analysis</li>
                        <li><i class="fas fa-brain"></i> <strong>Data Science:</strong> Machine Learning, Deep Learning, Natural Language Processing</li>
                        <li><i class="fas fa-code"></i> <strong>Computer Science:</strong> Algorithm Design, Software Architecture, Cloud Computing</li>
                        <li><i class="fas fa-database"></i> <strong>Data Engineering:</strong> ETL Pipelines, Big Data Technologies, Database Optimization</li>
                        <li><i class="fas fa-project-diagram"></i> <strong>Visualisasi:</strong> Interactive Dashboards, 3D Data Visualization, Storytelling with Data</li>
                    </ul>
                </div>
                <div class="competency-visualization">
                    <div id="network-graph"></div>
                </div>
            </div>
        </div>
    </section>

    <!-- Collaboration Section -->
    <section class="collaboration-section" id="collaboration">
        <div class="container">
            <div class="section-title">
                <h2>Koneksi & Kolaborasi</h2>
                <p>Terhubung dan berkolaborasi dengan profesional dan institusi</p>
            </div>
            <div class="collaboration-logos">
                <div class="collaboration-logo">
                    <i class="fab fa-github"></i>
                </div>
                <div class="collaboration-logo">
                    <i class="fab fa-linkedin"></i>
                </div>
                <div class="collaboration-logo">
                    <i class="fas fa-university"></i>
                </div>
                <div class="collaboration-logo">
                    <i class="fas fa-flask"></i>
                </div>
                <div class="collaboration-logo">
                    <i class="fas fa-chart-bar"></i>
                </div>
            </div>
        </div>
    </section>

    <!-- Modal Popup -->
    <div class="modal-overlay" id="modalOverlay">
        <div class="modal">
            <div class="modal-header">
                <h3 id="modalTitle">Judul Detail</h3>
                <button class="modal-close" id="modalClose">&times;</button>
            </div>
            <div class="modal-content" id="modalContent">
                <p>Konten detail akan muncul di sini.</p>
            </div>
            <div class="modal-footer">
                <a href="#" class="btn" id="modalLink" target="_blank">Kunjungi Link</a>
            </div>
        </div>
    </div>

    <!-- Footer -->
    <footer id="contact">
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>Ngurah Sentana</h3>
                    <p>Data Scientist & Computer Science Specialist dengan pendekatan interdisipliner untuk menyelesaikan masalah kompleks.</p>
                    <div class="social-links">
                        <a href="https://github.com/NgurahSentana" target="_blank"><i class="fab fa-github"></i></a>
                        <a href="https://linkedin.com/in/ngurahsentana" target="_blank"><i class="fab fa-linkedin-in"></i></a>
                        <a href="https://twitter.com/ngurahsentana" target="_blank"><i class="fab fa-twitter"></i></a>
                        <a href="mailto:ngurah.sentana@example.com"><i class="fas fa-envelope"></i></a>
                    </div>
                </div>
                <div class="footer-column">
                    <h3>Navigasi</h3>
                    <ul class="footer-links">
                        <li><a href="#home">Beranda</a></li>
                        <li><a href="#about">Perkenalan</a></li>
                        <li><a href="#projects">Proyek</a></li>
                        <li><a href="#competency">Kompetensi</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Portofolio</h3>
                    <ul class="footer-links">
                        <li><a href="#projects">Proyek</a></li>
                        <li><a href="#projects">Artikel</a></li>
                        <li><a href="#projects">Sertifikat</a></li>
                        <li><a href="#projects">Pengalaman</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Kontak</h3>
                    <ul class="footer-links">
                        <li><a href="mailto:ngurah.sentana@example.com">ngurah.sentana@example.com</a></li>
                        <li><a href="tel:+621234567890">+62 123 4567 890</a></li>
                        <li><a href="https://github.com/NgurahSentana" target="_blank">GitHub</a></li>
                        <li><a href="https://linkedin.com/in/ngurahsentana" target="_blank">LinkedIn</a></li>
                    </ul>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; 2023 Ngurah Sentana. Semua hak dilindungi. Dibuat dengan <i class="fas fa-heart" style="color: #ef4444;"></i> dan data.</p>
            </div>
        </div>
    </footer>

    <!-- JavaScript -->
    <script src="https://cdn.jsdelivr.net/npm/three@0.132.2/build/three.min.js"></script>
    <script src="https://unpkg.com/3d-force-graph"></script>
    <script>
        // Data untuk portofolio
        const portfolioData = {
            projects: [
                {
                    id: 1,
                    title: "Sistem Prediksi Pasar Finansial",
                    description: "Model machine learning untuk prediksi pergerakan pasar saham dengan akurasi 87% menggunakan LSTM dan data real-time.",
                    tags: ["Python", "TensorFlow", "LSTM", "Time Series"],
                    link: "https://github.com/NgurahSentana/stock-prediction",
                    ongoing: false,
                    icon: "fas fa-chart-line"
                },
                {
                    id: 2,
                    title: "Analisis Sentimen Media Sosial",
                    description: "NLP pipeline untuk analisis sentimen real-time dari platform media sosial dengan transformer models.",
                    tags: ["NLP", "Python", "Transformers", "FastAPI"],
                    link: "https://github.com/NgurahSentana/sentiment-analysis",
                    ongoing: true,
                    icon: "fas fa-comment-alt"
                },
                {
                    id: 3,
                    title: "Visualisasi Data Interaktif 3D",
                    description: "Dashboard visualisasi data 3D untuk dataset kompleks dengan WebGL dan Three.js.",
                    tags: ["JavaScript", "Three.js", "D3.js", "WebGL"],
                    link: "https://github.com/NgurahSentana/3d-data-viz",
                    ongoing: false,
                    icon: "fas fa-cube"
                }
            ],
            articles: [
                {
                    id: 1,
                    title: "Implementasi Bayesian Statistics dalam A/B Testing",
                    description: "Artikel tentang penerapan metode Bayesian untuk pengujian A/B yang lebih efisien.",
                    tags: ["Statistics", "Bayesian", "A/B Testing"],
                    link: "https://medium.com/@ngurahsentana/bayesian-ab-testing",
                    ongoing: false,
                    icon: "fas fa-book"
                },
                {
                    id: 2,
                    title: "Optimasi Algoritma untuk Big Data",
                    description: "Teknik optimasi algoritma untuk pemrosesan dataset berukuran besar.",
                    tags: ["Algorithms", "Big Data", "Optimization"],
                    link: "https://medium.com/@ngurahsentana/big-data-optimization",
                    ongoing: false,
                    icon: "fas fa-database"
                },
                {
                    id: 3,
                    title: "Architecture Modern Data Pipeline",
                    description: "Membangun data pipeline yang scalable dan maintainable (dalam penulisan).",
                    tags: ["Data Engineering", "Pipeline", "Architecture"],
                    link: "#",
                    ongoing: true,
                    icon: "fas fa-project-diagram"
                }
            ],
            certificates: [
                {
                    id: 1,
                    title: "Google Data Analytics Professional",
                    description: "Sertifikasi profesional analisis data dari Google.",
                    tags: ["Data Analytics", "Google"],
                    link: "https://coursera.org/certificates/data-analytics",
                    ongoing: false,
                    icon: "fas fa-award"
                },
                {
                    id: 2,
                    title: "AWS Machine Learning Specialty",
                    description: "Sertifikasi spesialis machine learning di platform AWS.",
                    tags: ["AWS", "Machine Learning", "Cloud"],
                    link: "https://aws.amazon.com/certification/",
                    ongoing: false,
                    icon: "fas fa-cloud"
                },
                {
                    id: 3,
                    title: "Deep Learning Specialization",
                    description: "Spesialisasi deep learning dari deeplearning.ai (sedang berjalan).",
                    tags: ["Deep Learning", "Neural Networks"],
                    link: "https://coursera.org/specializations/deep-learning",
                    ongoing: true,
                    icon: "fas fa-brain"
                }
            ],
            experiences: [
                {
                    id: 1,
                    title: "Lead Data Scientist - TechCorp",
                    description: "Memimpin tim data science untuk pengembangan model prediktif dan solusi AI.",
                    tags: ["Leadership", "Data Science", "AI"],
                    link: "https://techcorp.example.com",
                    ongoing: false,
                    icon: "fas fa-briefcase"
                },
                {
                    id: 2,
                    title: "Research Assistant - University AI Lab",
                    description: "Asisten penelitian di laboratorium AI universitas, fokus pada computer vision.",
                    tags: ["Research", "Computer Vision", "Academia"],
                    link: "https://university.edu/ai-lab",
                    ongoing: false,
                    icon: "fas fa-flask"
                },
                {
                    id: 3,
                    title: "Freelance Data Consultant",
                    description: "Konsultan data untuk berbagai perusahaan startup dan enterprise.",
                    tags: ["Consulting", "Freelance", "Data Strategy"],
                    link: "#",
                    ongoing: true,
                    icon: "fas fa-user-tie"
                }
            ]
        };

        // Fungsi untuk membuat card
        function createCard(item, type) {
            return `
                <div class="card" data-id="${item.id}" data-type="${type}">
                    <div class="card-header">
                        <div class="card-icon">
                            <i class="${item.icon}"></i>
                        </div>
                        ${item.ongoing ? '<span class="card-badge ongoing">Ongoing</span>' : ''}
                        <h3>${item.title}</h3>
                    </div>
                    <div class="card-content">
                        <p>${item.description}</p>
                        <div class="card-tags">
                            ${item.tags.map(tag => `<span class="tag">${tag}</span>`).join('')}
                        </div>
                    </div>
                </div>
            `;
        }

        // Render semua card
        function renderCards() {
            const projectsGrid = document.getElementById('projectsGrid');
            const articlesGrid = document.getElementById('articlesGrid');
            const certificatesGrid = document.getElementById('certificatesGrid');
            const experienceGrid = document.getElementById('experienceGrid');

            projectsGrid.innerHTML = portfolioData.projects.map(item => createCard(item, 'project')).join('');
            articlesGrid.innerHTML = portfolioData.articles.map(item => createCard(item, 'article')).join('');
            certificatesGrid.innerHTML = portfolioData.certificates.map(item => createCard(item, 'certificate')).join('');
            experienceGrid.innerHTML = portfolioData.experiences.map(item => createCard(item, 'experience')).join('');
        }

        // Modal functions
        function openModal(item, type) {
            const modalOverlay = document.getElementById('modalOverlay');
            const modalTitle = document.getElementById('modalTitle');
            const modalContent = document.getElementById('modalContent');
            const modalLink = document.getElementById('modalLink');
            
            modalTitle.textContent = item.title;
            modalContent.innerHTML = `
                <p>${item.description}</p>
                <p><strong>Tags:</strong> ${item.tags.join(', ')}</p>
                <p><strong>Status:</strong> ${item.ongoing ? 'Sedang berjalan' : 'Selesai'}</p>
                <p><strong>Tipe:</strong> ${type.charAt(0).toUpperCase() + type.slice(1)}</p>
            `;
            
            modalLink.href = item.link;
            modalLink.textContent = type === 'project' ? 'Lihat di GitHub' : 
                                  type === 'article' ? 'Baca Artikel' : 
                                  type === 'certificate' ? 'Lihat Sertifikat' : 
                                  'Lihat Detail';
            
            modalOverlay.classList.add('active');
            document.body.style.overflow = 'hidden';
        }

        function closeModal() {
            const modalOverlay = document.getElementById('modalOverlay');
            modalOverlay.classList.remove('active');
            document.body.style.overflow = 'auto';
        }

        // Ask me functionality
        function setupAskMe() {
            const askButton = document.getElementById('askButton');
            const questionInput = document.getElementById('question');
            const responseContent = document.getElementById('responseContent');
            
            const responses = [
                "Berdasarkan pengalaman saya di bidang data science, saya merekomendasikan pendekatan berbasis machine learning untuk masalah ini. Model yang sesuai tergantung pada karakteristik data Anda.",
                "Untuk optimasi performa dalam pengolahan data besar, pertimbangkan untuk menggunakan teknik parallel processing dan memilih struktur data yang efisien.",
                "Statistika Bayesian sangat berguna ketika Anda memiliki data terbatas tetapi memiliki pengetahuan domain yang kuat untuk dijadikan prior.",
                "Dalam membangun pipeline data, penting untuk mempertimbangkan aspek scalability dan maintainability dari awal desain.",
                "Visualisasi data 3D dapat memberikan insight yang tidak terlihat dalam visualisasi 2D tradisional, terutama untuk data spasial atau multivariat.",
                "Untuk proyek AI production, pastikan untuk menyertakan monitoring model dan pipeline retraining yang otomatis."
            ];
            
            askButton.addEventListener('click', function() {
                const question = questionInput.value.trim();
                if (question) {
                    // Simulate thinking
                    responseContent.innerHTML = '<p><i class="fas fa-spinner fa-spin"></i> Memproses pertanyaan...</p>';
                    
                    setTimeout(() => {
                        const randomResponse = responses[Math.floor(Math.random() * responses.length)];
                        responseContent.innerHTML = `
                            <p><strong>Pertanyaan Anda:</strong> "${question}"</p>
                            <p><strong>Jawaban:</strong> ${randomResponse}</p>
                            <p style="margin-top: 20px; font-size: 0.9rem; color: #6b7280;"><i>Ini adalah jawaban simulasi. Untuk konsultasi lebih lanjut, silakan hubungi saya melalui email.</i></p>
                        `;
                    }, 1500);
                } else {
                    responseContent.innerHTML = '<p class="response-placeholder">Silakan masukkan pertanyaan terlebih dahulu.</p>';
                }
            });
        }

        // Initialize network visualization
        function initNetworkGraph() {
            const container = document.getElementById('network-graph');
            
            // Fallback jika 3d-force-graph tidak tersedia
            if (!container) return;
            
            container.innerHTML = `
                <div style="width:100%; height:100%; display:flex; align-items:center; justify-content:center; background:linear-gradient(135deg, #f0f9ff 0%, #e0e7ff 100%);">
                    <div style="text-align:center; padding:20px;">
                        <i class="fas fa-project-diagram" style="font-size:3rem; color:#2563eb; margin-bottom:20px;"></i>
                        <h3 style="color:#1e293b;">Peta Keahlian Interaktif</h3>
                        <p style="color:#64748b;">Visualisasi 3D koneksi keahlian dalam Statistics, Data Science, dan Computer Science.</p>
                    </div>
                </div>
            `;
            
            // Kode untuk 3D force graph akan diimplementasikan jika library tersedia
            // try {
            //     const Graph = ForceGraph3D();
            //     const myGraph = Graph(container);
            //     
            //     // Data untuk graph
            //     const graphData = {
            //         nodes: [
            //             { id: 'Statistics', group: 1 },
            //             { id: 'Data Science', group: 2 },
            //             { id: 'Computer Science', group: 3 },
            //             { id: 'Machine Learning', group: 2 },
            //             { id: 'Deep Learning', group: 2 },
            //             { id: 'Big Data', group: 3 },
            //             { id: 'Visualization', group: 2 },
            //             { id: 'Cloud Computing', group: 3 },
            //             { id: 'Python', group: 4 },
            //             { id: 'R', group: 4 },
            //             { id: 'SQL', group: 4 }
            //         ],
            //         links: [
            //             { source: 'Statistics', target: 'Data Science' },
            //             { source: 'Data Science', target: 'Computer Science' },
            //             { source: 'Data Science', target: 'Machine Learning' },
            //             { source: 'Machine Learning', target: 'Deep Learning' },
            //             { source: 'Computer Science', target: 'Big Data' },
            //             { source: 'Data Science', target: 'Visualization' },
            //             { source: 'Computer Science', target: 'Cloud Computing' },
            //             { source: 'Data Science', target: 'Python' },
            //             { source: 'Statistics', target: 'R' },
            //             { source: 'Data Science', target: 'SQL' }
            //         ]
            //     };
            //     
            //     myGraph.graphData(graphData);
            // } catch (e) {
            //     console.log("3D Force Graph tidak tersedia, menggunakan fallback");
            // }
        }

        // Initialize everything
        document.addEventListener('DOMContentLoaded', function() {
            // Render cards
            renderCards();
            
            // Setup ask me functionality
            setupAskMe();
            
            // Initialize network graph
            initNetworkGraph();
            
            // Mobile menu toggle
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
                    header.style.boxShadow = "0 5px 20px rgba(0, 0, 0, 0.05)";
                } else {
                    header.style.boxShadow = "none";
                }
            });
            
            // Modal functionality
            document.querySelectorAll('.card').forEach(card => {
                card.addEventListener('click', function() {
                    const id = parseInt(this.dataset.id);
                    const type = this.dataset.type;
                    
                    let item;
                    switch(type) {
                        case 'project':
                            item = portfolioData.projects.find(p => p.id === id);
                            break;
                        case 'article':
                            item = portfolioData.articles.find(a => a.id === id);
                            break;
                        case 'certificate':
                            item = portfolioData.certificates.find(c => c.id === id);
                            break;
                        case 'experience':
                            item = portfolioData.experiences.find(e => e.id === id);
                            break;
                    }
                    
                    if (item) {
                        openModal(item, type);
                    }
                });
            });
            
            // Close modal
            document.getElementById('modalClose').addEventListener('click', closeModal);
            document.getElementById('modalOverlay').addEventListener('click', function(e) {
                if (e.target === this) {
                    closeModal();
                }
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
            
            // Dynamic year in footer
            document.querySelector('.copyright').innerHTML = document.querySelector('.copyright').innerHTML.replace('2023', new Date().getFullYear());
        });
    </script>
</body>
</html>
