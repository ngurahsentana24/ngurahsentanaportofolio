<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ngurah Sentana | Data Scientist & Computer Science Portfolio</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&family=Space+Grotesk:wght@300;400;500;600;700&family=JetBrains+Mono:wght@300;400;500&display=swap" rel="stylesheet">
    <style>
        /* Semua kode CSS yang sama */
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
            --border-radius: 12px;
            --border-radius-lg: 20px;
            --max-width: 1200px;
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
            cursor: default;
        }

        /* Custom Cursor */
        .cursor-dot {
            width: 8px;
            height: 8px;
            background-color: var(--accent-color);
            border-radius: 50%;
            position: fixed;
            pointer-events: none;
            z-index: 9999;
            transition: transform 0.1s ease;
        }

        .cursor-outline {
            width: 40px;
            height: 40px;
            border: 2px solid var(--accent-color);
            border-radius: 50%;
            position: fixed;
            pointer-events: none;
            z-index: 9998;
            transition: all 0.2s ease-out;
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
            width: 95%;
            max-width: var(--max-width);
            margin: 0 auto;
            padding: 0 15px;
        }

        /* Header & Navigation */
        header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            background: rgba(255, 255, 255, 0.97);
            backdrop-filter: blur(15px);
            z-index: 1000;
            transition: var(--transition);
            border-bottom: 1px solid rgba(0, 0, 0, 0.05);
            padding: 12px 0;
            transform: translateY(0);
        }

        header.hidden {
            transform: translateY(-100%);
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
        }

        .logo {
            font-size: 1.6rem;
            font-weight: 800;
            color: var(--secondary-color);
            text-decoration: none;
            display: flex;
            align-items: center;
            position: relative;
            font-family: 'JetBrains Mono', monospace;
            white-space: nowrap;
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
            flex-wrap: wrap;
            justify-content: center;
            margin: 0 15px;
            gap: 10px;
        }

        .nav-links li {
            position: relative;
        }

        .nav-links a {
            text-decoration: none;
            color: var(--secondary-color);
            font-weight: 500;
            transition: var(--transition);
            position: relative;
            padding: 6px 12px;
            font-size: 0.9rem;
            font-family: 'JetBrains Mono', monospace;
            border-radius: 6px;
        }

        .nav-links a:hover {
            color: var(--accent-color);
            background: rgba(37, 99, 235, 0.05);
        }

        .nav-links a.active {
            color: var(--accent-color);
            background: rgba(37, 99, 235, 0.1);
        }

        .menu-toggle {
            display: none;
            font-size: 1.4rem;
            cursor: pointer;
            color: var(--secondary-color);
            padding: 5px;
        }

        .header-right {
            display: flex;
            align-items: center;
            gap: 12px;
            flex-wrap: nowrap;
            white-space: nowrap;
        }

        .language-switcher {
            display: flex;
            gap: 4px;
            background: var(--light-gray);
            border-radius: 20px;
            padding: 4px;
            border: 1px solid var(--medium-gray);
        }

        .language-switcher button {
            background: none;
            border: none;
            padding: 6px 14px;
            border-radius: 16px;
            font-family: 'Inter', sans-serif;
            font-weight: 500;
            font-size: 0.85rem;
            cursor: pointer;
            transition: var(--transition);
        }

        .language-switcher button.active {
            background: var(--accent-color);
            color: white;
        }

        .language-switcher button:hover:not(.active) {
            background: rgba(0, 0, 0, 0.05);
        }

        .header-cv {
            padding: 8px 18px;
            background: linear-gradient(90deg, var(--accent-color), var(--accent-light));
            color: white;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            transition: var(--transition);
            font-size: 0.85rem;
            display: flex;
            align-items: center;
            gap: 6px;
            white-space: nowrap;
        }

        .header-cv:hover {
            transform: translateY(-2px);
            box-shadow: var(--shadow);
        }

        /* Hero Section */
        .hero {
            padding: 150px 0 80px;
            position: relative;
            overflow: hidden;
            background: linear-gradient(135deg, #f0f9ff 0%, #fef2f2 100%);
            border-radius: 0 0 60px 60px;
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
            max-width: 600px;
        }

        .hero-text h1 {
            font-size: 3.2rem;
            line-height: 1.1;
            margin-bottom: 1.2rem;
            background: linear-gradient(90deg, var(--secondary-color), var(--accent-color));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }

        .hero-text p {
            font-size: 1.1rem;
            margin-bottom: 2rem;
            max-width: 500px;
            color: #4b5563;
        }

        .btn {
            display: inline-flex;
            align-items: center;
            padding: 12px 28px;
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

        .btn:hover {
            transform: translateY(-3px);
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

        .btn-small {
            padding: 8px 16px;
            font-size: 0.85rem;
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
            transform: rotate(2deg);
            box-shadow: var(--shadow-lg);
        }

        .profile-img {
            width: 320px;
            height: 400px;
            object-fit: cover;
            transition: var(--transition);
            filter: grayscale(0.2) contrast(1.1);
        }

        .profile-img-container:hover {
            transform: rotate(0deg);
        }

        /* Stats Section */
        .stats-section {
            padding: 60px 0;
            background-color: white;
        }

        .stats-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
            gap: 20px;
        }

        .stat-card {
            background: white;
            border-radius: var(--border-radius);
            padding: 30px 20px;
            text-align: center;
            box-shadow: var(--shadow);
            border: 1px solid var(--medium-gray);
            transition: var(--transition);
            position: relative;
            overflow: hidden;
        }

        .stat-card:hover {
            transform: translateY(-5px);
            box-shadow: var(--shadow-lg);
            border-color: var(--accent-color);
        }

        .stat-icon {
            font-size: 2rem;
            color: var(--accent-color);
            margin-bottom: 15px;
        }

        .stat-number {
            font-size: 2.5rem;
            font-weight: 800;
            color: var(--secondary-color);
            margin-bottom: 8px;
            font-family: 'Space Grotesk', sans-serif;
        }

        .stat-label {
            color: var(--dark-gray);
            font-size: 0.95rem;
            font-weight: 500;
        }

        .stat-trend {
            position: absolute;
            top: 15px;
            right: 15px;
            font-size: 0.75rem;
            font-weight: 600;
            padding: 3px 8px;
            border-radius: 12px;
            background: var(--success-color);
            color: white;
        }

        .stat-trend.negative {
            background: var(--danger-color);
        }

        /* Section Container with Slider */
        .section-container {
            position: relative;
            overflow: hidden;
        }

        .section-content {
            display: flex;
            overflow-x: auto;
            scroll-behavior: smooth;
            scrollbar-width: none;
            padding: 20px 5px 40px;
            gap: 20px;
            margin: 0 -5px;
        }

        .section-content::-webkit-scrollbar {
            display: none;
        }

        .section-slider-nav {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-top: 20px;
        }

        .slider-nav-btn {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            border: 2px solid var(--accent-color);
            background: white;
            color: var(--accent-color);
            font-size: 1rem;
            cursor: pointer;
            transition: var(--transition);
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .slider-nav-btn:hover {
            background: var(--accent-color);
            color: white;
        }

        .slider-nav-btn.disabled {
            opacity: 0.3;
            cursor: not-allowed;
        }

        .project-card, .article-card, .certificate-card, .experience-card, .award-card, .organization-card {
            flex: 0 0 320px;
            background: white;
            border-radius: var(--border-radius);
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
            border: 1px solid var(--medium-gray);
            cursor: pointer;
            opacity: 0;
            transform: translateY(20px);
            position: relative;
        }

        .project-card.visible, .article-card.visible, .certificate-card.visible, 
        .experience-card.visible, .award-card.visible, .organization-card.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .project-card:hover, .article-card:hover, .certificate-card:hover,
        .experience-card:hover, .award-card:hover, .organization-card:hover {
            transform: translateY(-10px);
            box-shadow: var(--shadow-lg);
            border-color: var(--accent-color);
        }

        /* PERBAIKAN: Menambahkan image container untuk experience dan organization */
        .project-image-container, .experience-image-container, .organization-image-container {
            height: 180px;
            overflow: hidden;
            position: relative;
        }

        .project-image, .article-image, .experience-image, .organization-image {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
        }

        .project-card:hover .project-image,
        .article-card:hover .article-image,
        .experience-card:hover .experience-image,
        .organization-card:hover .organization-image {
            transform: scale(1.05);
        }

        .project-status {
            position: absolute;
            top: 12px;
            right: 12px;
            padding: 4px 12px;
            background: var(--success-color);
            color: white;
            border-radius: 20px;
            font-size: 0.75rem;
            font-weight: 600;
            z-index: 2;
        }

        .project-status.ongoing {
            background: var(--warning-color);
        }

        .card-content {
            padding: 20px;
        }

        .card-content h3 {
            margin-bottom: 10px;
            font-size: 1.2rem;
            line-height: 1.3;
        }

        .card-content p {
            font-size: 0.9rem;
            color: #64748b;
            line-height: 1.5;
            margin-bottom: 15px;
        }

        .card-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 6px;
            margin-top: 15px;
        }

        .tag {
            padding: 4px 10px;
            background: #eff6ff;
            color: var(--accent-color);
            border-radius: 15px;
            font-size: 0.75rem;
            font-weight: 500;
        }

        .card-footer {
            margin-top: 15px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .card-date {
            font-size: 0.8rem;
            color: var(--dark-gray);
        }

        .view-more {
            font-size: 0.85rem;
            color: var(--accent-color);
            text-decoration: none;
            font-weight: 600;
            display: flex;
            align-items: center;
            gap: 5px;
        }

        .view-more:hover {
            text-decoration: underline;
        }

        /* Articles */
        .article-image-container {
            height: 150px;
            overflow: hidden;
            position: relative;
        }

        .article-header {
            padding: 20px 20px 10px;
            background: linear-gradient(135deg, #f0f9ff 0%, #e0f2fe 100%);
        }

        .article-journal {
            font-size: 0.85rem;
            color: var(--accent-color);
            font-weight: 600;
            margin-bottom: 5px;
        }

        /* Certificates & Experience */
        /* DIHAPUS karena akan menggunakan gambar */
        /*
        .certificate-icon, .experience-icon {
            padding: 25px 25px 15px;
            text-align: center;
            background: linear-gradient(135deg, #f0f9ff 0%, #e0f2fe 100%);
        }

        .certificate-icon i, .experience-icon i {
            font-size: 2.5rem;
            color: var(--accent-color);
        }
        */

        /* PERBAIKAN: Menambahkan image container untuk certificate */
        .certificate-image-container {
            height: 180px;
            overflow: hidden;
            position: relative;
        }

        .certificate-image {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
        }

        .certificate-card:hover .certificate-image {
            transform: scale(1.05);
        }

        /* PERBAIKAN: Menambahkan image container untuk award */
        .award-image-container {
            height: 180px;
            overflow: hidden;
            position: relative;
        }

        .award-image {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
        }

        .award-card:hover .award-image {
            transform: scale(1.05);
        }

        /* Organizations */
        /* DIHAPUS karena akan menggunakan gambar */
        /*
        .organization-icon {
            padding: 25px 25px 15px;
            text-align: center;
            background: linear-gradient(135deg, #f0f9ff 0%, #e0f2fe 100%);
        }

        .organization-icon i {
            font-size: 2.5rem;
            color: var(--accent-color);
        }
        */

        /* Collaboration Section */
        .collaboration-section {
            background: linear-gradient(135deg, #f0f9ff 0%, #e0f2fe 100%);
        }

        .collaboration-container {
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center;
        }

        .collaboration-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            gap: 30px;
            width: 100%;
            margin-top: 30px;
        }

        .collaboration-item {
            background: white;
            border-radius: var(--border-radius);
            padding: 25px;
            box-shadow: var(--shadow);
            transition: var(--transition);
            border: 1px solid var(--medium-gray);
            text-align: center;
            cursor: pointer;
            opacity: 0;
            transform: translateY(20px);
        }

        .collaboration-item.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .collaboration-item:hover {
            transform: translateY(-10px);
            box-shadow: var(--shadow-lg);
            border-color: var(--accent-color);
        }

        .collaboration-icon {
            display: block;
            font-size: 2.5rem;
            color: var(--accent-color);
            margin-bottom: 15px;
            transition: var(--transition);
        }

        .collaboration-item:hover .collaboration-icon {
            transform: scale(1.2);
        }

        .collaboration-name {
            font-weight: 600;
            color: var(--secondary-color);
            font-size: 0.95rem;
        }

        /* Photos Section */
        .photos-section {
            background-color: white;
        }

        .photos-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 20px;
            margin-top: 30px;
        }

        .photo-item {
            position: relative;
            border-radius: var(--border-radius);
            overflow: hidden;
            cursor: pointer;
            height: 250px;
            opacity: 0;
            transform: translateY(20px);
            box-shadow: var(--shadow);
            transition: var(--transition);
        }

        .photo-item.visible {
            opacity: 1;
            transform: translateY(0);
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
            transform: scale(1.05);
        }

        .photo-overlay {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background: linear-gradient(to top, rgba(0,0,0,0.7), transparent);
            color: white;
            padding: 15px;
            transform: translateY(20px);
            opacity: 0;
            transition: var(--transition);
        }

        .photo-item:hover .photo-overlay {
            opacity: 1;
            transform: translateY(0);
        }

        .photo-title {
            font-weight: 600;
            font-size: 0.9rem;
            margin-bottom: 5px;
        }

        .photo-date {
            font-size: 0.8rem;
            opacity: 0.9;
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
            border-radius: var(--border-radius-lg);
            width: 90%;
            max-width: 700px;
            max-height: 90vh;
            overflow-y: auto;
            box-shadow: var(--shadow-lg);
            position: relative;
            transform: translateY(40px);
            transition: transform 0.4s ease;
        }

        .modal-overlay.active .modal {
            transform: translateY(0);
        }

        .modal-header {
            padding: 25px 25px 20px;
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
            padding: 5px;
        }

        .modal-close:hover {
            color: var(--danger-color);
        }

        .modal-content {
            padding: 25px;
        }

        .modal-image {
            width: 100%;
            height: 200px;
            object-fit: cover;
            border-radius: var(--border-radius);
            margin-bottom: 20px;
        }

        /* Modal Slider for Experience and Organizations */
        .modal-slider {
            position: relative;
            margin: 20px 0;
        }

        .modal-slider-content {
            display: flex;
            overflow-x: auto;
            scroll-behavior: smooth;
            scrollbar-width: none;
            gap: 15px;
            padding: 10px 0;
        }

        .modal-slider-content::-webkit-scrollbar {
            display: none;
        }

        .modal-slider-card {
            flex: 0 0 280px;
            background: var(--light-gray);
            border-radius: var(--border-radius);
            padding: 20px;
            border-left: 4px solid var(--accent-color);
        }

        .modal-slider-card h4 {
            margin-bottom: 10px;
            font-size: 1rem;
        }

        .modal-slider-card p {
            font-size: 0.9rem;
            margin-bottom: 0;
        }

        .modal-slider-nav {
            display: flex;
            justify-content: center;
            gap: 10px;
            margin-top: 15px;
        }

        .modal-slider-btn {
            width: 30px;
            height: 30px;
            border-radius: 50%;
            border: 1px solid var(--accent-color);
            background: white;
            color: var(--accent-color);
            font-size: 0.8rem;
            cursor: pointer;
            transition: var(--transition);
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .modal-slider-btn:hover {
            background: var(--accent-color);
            color: white;
        }

        .modal-footer {
            padding: 20px 25px;
            border-top: 1px solid var(--medium-gray);
            text-align: right;
        }

        /* Testimonials */
        .testimonials-slider {
            position: relative;
            max-width: 800px;
            margin: 0 auto;
        }

        .testimonial-card {
            background: white;
            border-radius: var(--border-radius);
            padding: 40px;
            box-shadow: var(--shadow);
            border: 1px solid var(--medium-gray);
            text-align: center;
            position: relative;
            opacity: 0;
            transform: translateY(20px);
            transition: opacity 0.5s ease, transform 0.5s ease;
        }

        .testimonial-card.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .testimonial-text {
            font-size: 1.2rem;
            font-style: italic;
            color: #475569;
            margin-bottom: 30px;
            position: relative;
            padding: 0 30px;
            line-height: 1.6;
        }

        .testimonial-text::before,
        .testimonial-text::after {
            content: '"';
            font-size: 4rem;
            color: var(--accent-color);
            opacity: 0.2;
            position: absolute;
            font-family: Georgia, serif;
        }

        .testimonial-text::before {
            top: -20px;
            left: 0;
        }

        .testimonial-text::after {
            bottom: -40px;
            right: 0;
        }

        .testimonial-author {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 15px;
            margin-top: 20px;
        }

        .author-avatar {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            object-fit: cover;
            border: 3px solid var(--accent-color);
            padding: 2px;
            background: white;
        }

        .author-icon {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--accent-color), var(--accent-light));
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 1.5rem;
            border: 3px solid var(--accent-color);
        }

        .author-info h4 {
            margin-bottom: 5px;
            font-size: 1.1rem;
        }

        .author-info p {
            color: var(--dark-gray);
            font-size: 0.9rem;
            margin-bottom: 0;
        }

        .testimonial-nav {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-top: 30px;
        }

        .testimonial-dots {
            display: flex;
            gap: 10px;
            justify-content: center;
            margin-top: 20px;
        }

        .testimonial-dot {
            width: 12px;
            height: 12px;
            border-radius: 50%;
            background: var(--medium-gray);
            cursor: pointer;
            transition: var(--transition);
        }

        .testimonial-dot.active {
            background: var(--accent-color);
            transform: scale(1.2);
        }

        /* Ask Me Section */
        .ask-container {
            display: flex;
            gap: 30px;
            align-items: stretch;
        }

        .ask-form-container {
            flex: 1;
        }

        .ask-form {
            background: white;
            border: 1px solid var(--medium-gray);
            border-radius: var(--border-radius);
            padding: 30px;
            box-shadow: var(--shadow);
            height: 100%;
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            color: var(--secondary-color);
            font-size: 0.9rem;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 12px;
            border: 1px solid var(--medium-gray);
            border-radius: 8px;
            font-family: 'Inter', sans-serif;
            font-size: 0.95rem;
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
            padding: 30px;
            box-shadow: var(--shadow);
            display: flex;
            flex-direction: column;
        }

        .response-header {
            display: flex;
            align-items: center;
            margin-bottom: 20px;
        }

        .response-header i {
            font-size: 1.3rem;
            color: var(--accent-color);
            margin-right: 12px;
        }

        .response-content {
            flex: 1;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 20px 0;
        }

        .response-placeholder {
            color: var(--dark-gray);
            font-style: italic;
            margin-bottom: 20px;
        }

        .whatsapp-btn {
            display: inline-flex;
            align-items: center;
            gap: 10px;
            padding: 12px 24px;
            background: #25D366;
            color: white;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            transition: var(--transition);
            margin-top: 10px;
        }

        .whatsapp-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(37, 211, 102, 0.2);
        }

        /* Footer */
        footer {
            background: var(--secondary-color);
            color: white;
            padding: 50px 0 20px;
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 30px;
            margin-bottom: 40px;
        }

        .footer-column h3 {
            color: white;
            margin-bottom: 20px;
            font-size: 1.2rem;
        }

        .footer-links {
            list-style: none;
        }

        .footer-links li {
            margin-bottom: 10px;
        }

        .footer-links a {
            color: #cbd5e1;
            text-decoration: none;
            font-size: 0.9rem;
            transition: var(--transition);
        }

        .footer-links a:hover {
            color: white;
            padding-left: 5px;
        }

        .social-links {
            display: flex;
            gap: 12px;
            margin-top: 15px;
        }

        .social-links a {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 36px;
            height: 36px;
            background: rgba(255, 255, 255, 0.1);
            color: white;
            border-radius: 50%;
            text-decoration: none;
            transition: var(--transition);
        }

        .social-links a:hover {
            background: var(--accent-color);
            transform: translateY(-3px);
        }

        .copyright {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            color: #cbd5e1;
            font-size: 0.85rem;
        }

        /* Section Styling */
        section {
            padding: 80px 0;
            position: relative;
            opacity: 0;
            transform: translateY(30px);
            transition: opacity 0.8s ease, transform 0.8s ease;
        }

        section.visible {
            opacity: 1;
            transform: translateY(0);
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
            padding-bottom: 12px;
        }

        .section-title h2::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background: linear-gradient(90deg, var(--accent-color), var(--accent-light));
            border-radius: 4px;
        }

        .section-title p {
            color: var(--dark-gray);
            font-size: 1rem;
            max-width: 500px;
            margin: 1rem auto 0;
        }

        /* Visitor Counter */
        .visitor-counter {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background: linear-gradient(135deg, var(--accent-color), var(--accent-light));
            color: white;
            padding: 12px 20px;
            border-radius: 50px;
            box-shadow: var(--shadow-lg);
            z-index: 999;
            display: flex;
            align-items: center;
            gap: 10px;
            font-size: 0.9rem;
            transition: var(--transition);
            backdrop-filter: blur(10px);
        }

        .visitor-counter:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.15);
        }

        .visitor-counter i {
            font-size: 1.2rem;
        }

        /* Competency Section */
        .competency-section {
            background-color: var(--light-gray);
        }

        .skills-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 30px;
        }

        .skill-category {
            background: white;
            border-radius: var(--border-radius);
            padding: 30px;
            box-shadow: var(--shadow);
            border: 1px solid var(--medium-gray);
            opacity: 0;
            transform: translateY(30px);
        }

        .skill-category.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .skill-category h3 {
            margin-bottom: 20px;
            display: flex;
            align-items: center;
        }

        .skill-category h3 i {
            margin-right: 15px;
            color: var(--accent-color);
            font-size: 1.5rem;
        }

        .skill-item {
            margin-bottom: 20px;
        }

        .skill-header {
            display: flex;
            justify-content: space-between;
            margin-bottom: 8px;
        }

        .skill-name {
            font-weight: 600;
            color: var(--secondary-color);
        }

        .skill-percentage {
            font-weight: 600;
            color: var(--accent-color);
            font-family: 'JetBrains Mono', monospace;
        }

        .skill-bar {
            height: 8px;
            background: var(--light-gray);
            border-radius: 4px;
            overflow: hidden;
        }

        .skill-progress {
            height: 100%;
            background: linear-gradient(90deg, var(--accent-color), var(--accent-light));
            border-radius: 4px;
            width: 0;
            transition: width 1.5s ease;
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

        @keyframes float {
            0%, 100% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(-15px);
            }
        }

        @keyframes pulse {
            0% {
                transform: scale(1);
                box-shadow: var(--shadow);
            }
            50% {
                transform: scale(1.05);
                box-shadow: var(--shadow-lg);
            }
            100% {
                transform: scale(1);
                box-shadow: var(--shadow);
            }
        }

        @keyframes progressAnimation {
            from { width: 0; }
            to { width: var(--target-width); }
        }

        /* Responsive Design */
        @media (max-width: 992px) {
            .hero-content {
                flex-direction: column;
                text-align: center;
            }
            
            .hero-text {
                padding-right: 0;
                margin-bottom: 50px;
                max-width: 100%;
            }
            
            .hero-text h1 {
                font-size: 2.8rem;
            }
            
            .ask-container {
                flex-direction: column;
            }
            
            .profile-img {
                width: 280px;
                height: 350px;
            }

            .cursor-dot,
            .cursor-outline {
                display: none;
            }
        }

        @media (max-width: 768px) {
            .menu-toggle {
                display: block;
                order: 1;
            }
            
            .logo {
                order: 0;
                flex: 1;
            }
            
            .header-right {
                order: 2;
            }
            
            .nav-links {
                position: fixed;
                top: 70px;
                left: -100%;
                width: 100%;
                height: calc(100vh - 70px);
                background: rgba(255, 255, 255, 0.98);
                backdrop-filter: blur(20px);
                flex-direction: column;
                align-items: center;
                justify-content: flex-start;
                padding-top: 40px;
                transition: var(--transition);
                border-top: 1px solid rgba(0, 0, 0, 0.05);
                z-index: 999;
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
            
            .container {
                width: 100%;
                padding: 0 15px;
            }
            
            .header-cv span {
                display: none;
            }
            
            .header-cv i {
                margin-right: 0;
            }

            .visitor-counter {
                bottom: 10px;
                right: 10px;
                font-size: 0.8rem;
                padding: 10px 16px;
            }
        }

        @media (max-width: 480px) {
            .hero-text h1 {
                font-size: 1.8rem;
            }
            
            .section-title h2 {
                font-size: 1.8rem;
            }
            
            .stat-number {
                font-size: 2rem;
            }
            
            .btn {
                padding: 10px 22px;
                font-size: 0.9rem;
            }
            
            .modal {
                width: 95%;
            }
            
            .project-card, .article-card, .certificate-card, 
            .experience-card, .award-card, .organization-card {
                flex: 0 0 280px;
            }

            .testimonial-text {
                font-size: 1rem;
                padding: 0 15px;
            }

            .testimonial-text::before,
            .testimonial-text::after {
                font-size: 3rem;
            }
        }

        /* Utility Classes */
        .fade-in {
            animation: fadeInUp 0.8s ease;
        }

        .float-animation {
            animation: float 5s ease-in-out infinite;
        }

        .pulse {
            animation: pulse 2s infinite;
        }

        /* Page Transition */
        .page-transition {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: var(--accent-color);
            z-index: 9999;
            transform: translateY(100%);
            transition: transform 0.6s cubic-bezier(0.86, 0, 0.07, 1);
        }

        .page-transition.active {
            transform: translateY(0);
        }
    </style>
</head>
<body>
    <!-- Custom Cursor -->
    <div class="cursor-dot" id="cursorDot"></div>
    <div class="cursor-outline" id="cursorOutline"></div>

    <!-- Page Transition Overlay -->
    <div class="page-transition" id="pageTransition"></div>

    <!-- Header & Navigation -->
    <header id="header">
        <div class="container">
            <nav>
                <a href="#" class="logo">NgurahSentana<span>_</span></a>
                <div class="menu-toggle" id="menuToggle">
                    <i class="fas fa-bars"></i>
                </div>
                <ul class="nav-links">
                    <li><a href="#home" data-i18n="nav.home">Home</a></li>
                    <li><a href="#projects" data-i18n="nav.projects">Projects</a></li>
                    <li><a href="#articles" data-i18n="nav.publications">Publications</a></li>
                    <li><a href="#experience" data-i18n="nav.experience">Experience</a></li>
                    <li><a href="#organizations" data-i18n="nav.organizations">Organizations</a></li>
                    <li><a href="#certificates" data-i18n="nav.certificates">Certificates</a></li>
                    <li><a href="#awards" data-i18n="nav.awards">Awards</a></li>
                    <li><a href="#collaborations" data-i18n="nav.collaborations">Collaborations</a></li>
                    <li><a href="#photos" data-i18n="nav.photos">Photos</a></li>
                    <li><a href="#competency" data-i18n="nav.competency">Competency</a></li>
                    <li><a href="#testimonials" data-i18n="nav.testimonials">Testimonials</a></li>
                </ul>
                <div class="header-right">
                    <div class="language-switcher">
                        <button class="active" id="langEN">EN</button>
                        <button id="langID">ID</button>
                    </div>
                    <a href="https://drive.google.com/file/d/1mOZOAM-TmwQTRuSFJh-xNK2BA4WfJYDD/view?usp=drive_link" target="_blank" class="header-cv">
                        <i class="fas fa-download"></i>
                        <span>CV</span>
                    </a>
                </div>
            </nav>
        </div>
    </header>

    <!-- Visitor Counter -->
    <div class="visitor-counter" id="visitorCounter">
        <i class="fas fa-eye"></i>
        <span id="visitorCount">0</span> visitors
    </div>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="container">
            <div class="hero-content fade-in">
                <div class="hero-text">
                    <h1 data-i18n="hero.title">Ngurah Sentana</h1>
                    <p data-i18n="hero.description">Data Scientist & Computer Science Specialist with expertise in Statistics, Machine Learning, and Software Development. Creating elegant and functional data-driven solutions.</p>
                    <div style="display: flex; gap: 12px; flex-wrap: wrap;">
                        <a href="#projects" class="btn" data-i18n="hero.view_projects">View Projects</a>
                        <a href="#contact" class="btn btn-outline" data-i18n="hero.contact_me">Contact Me</a>
                    </div>
                </div>
                <div class="hero-image float-animation">
                    <div class="profile-img-container">
                        <img src="https://raw.githubusercontent.com/ngurahsentana24/Archive/main/photos/pribadi.jpeg" alt="Foto Ngurah Sentana" class="profile-img">
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Stats Section -->
    <section class="stats-section">
        <div class="container">
            <div class="stats-container" id="statsContainer">
                <!-- Stats will be filled by JavaScript -->
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section class="projects-section" id="projects">
        <div class="container">
            <div class="section-title">
                <h2 data-i18n="projects.title">Projects</h2>
                <p data-i18n="projects.description">Data science and software development projects</p>
            </div>
            <div class="section-container">
                <div class="section-content" id="projectsContent">
                    <!-- Cards will be filled by JavaScript -->
                </div>
                <div class="section-slider-nav">
                    <button class="slider-nav-btn" id="projectsPrev">
                        <i class="fas fa-chevron-left"></i>
                    </button>
                    <button class="slider-nav-btn" id="projectsNext">
                        <i class="fas fa-chevron-right"></i>
                    </button>
                </div>
            </div>
        </div>
    </section>

    <!-- Articles Section -->
    <section class="articles-section" id="articles">
        <div class="container">
            <div class="section-title">
                <h2 data-i18n="articles.title">Publications</h2>
                <p data-i18n="articles.description">Research papers and articles</p>
            </div>
            <div class="section-container">
                <div class="section-content" id="articlesContent">
                    <!-- Cards will be filled by JavaScript -->
                </div>
                <div class="section-slider-nav">
                    <button class="slider-nav-btn" id="articlesPrev">
                        <i class="fas fa-chevron-left"></i>
                    </button>
                    <button class="slider-nav-btn" id="articlesNext">
                        <i class="fas fa-chevron-right"></i>
                    </button>
                </div>
            </div>
        </div>
    </section>

    <!-- Experience Section -->
    <section class="experience-section" id="experience">
        <div class="container">
            <div class="section-title">
                <h2 data-i18n="experience.title">Work Experience</h2>
                <p data-i18n="experience.description">Professional journey and work experience</p>
            </div>
            <div class="section-container">
                <div class="section-content" id="experienceContent">
                    <!-- Cards will be filled by JavaScript -->
                </div>
                <div class="section-slider-nav">
                    <button class="slider-nav-btn" id="experiencePrev">
                        <i class="fas fa-chevron-left"></i>
                    </button>
                    <button class="slider-nav-btn" id="experienceNext">
                        <i class="fas fa-chevron-right"></i>
                    </button>
                </div>
            </div>
        </div>
    </section>

    <!-- Organizations Section -->
    <section class="organizations-section" id="organizations">
        <div class="container">
            <div class="section-title">
                <h2 data-i18n="organizations.title">Organizations</h2>
                <p data-i18n="organizations.description">Professional and academic organizations</p>
            </div>
            <div class="section-container">
                <div class="section-content" id="organizationsContent">
                    <!-- Cards will be filled by JavaScript -->
                </div>
                <div class="section-slider-nav">
                    <button class="slider-nav-btn" id="organizationsPrev">
                        <i class="fas fa-chevron-left"></i>
                    </button>
                    <button class="slider-nav-btn" id="organizationsNext">
                        <i class="fas fa-chevron-right"></i>
                    </button>
                </div>
            </div>
        </div>
    </section>

    <!-- Certificates Section -->
    <section class="certificates-section" id="certificates">
        <div class="container">
            <div class="section-title">
                <h2 data-i18n="certificates.title">Certificates</h2>
                <p data-i18n="certificates.description">Professional certifications</p>
            </div>
            <div class="section-container">
                <div class="section-content" id="certificatesContent">
                    <!-- Cards will be filled by JavaScript -->
                </div>
                <div class="section-slider-nav">
                    <button class="slider-nav-btn" id="certificatesPrev">
                        <i class="fas fa-chevron-left"></i>
                    </button>
                    <button class="slider-nav-btn" id="certificatesNext">
                        <i class="fas fa-chevron-right"></i>
                    </button>
                </div>
            </div>
        </div>
    </section>

    <!-- Awards Section -->
    <section class="awards-section" id="awards">
        <div class="container">
            <div class="section-title">
                <h2 data-i18n="awards.title">Awards</h2>
                <p data-i18n="awards.description">Achievements and recognitions</p>
            </div>
            <div class="section-container">
                <div class="section-content" id="awardsContent">
                    <!-- Cards will be filled by JavaScript -->
                </div>
                <div class="section-slider-nav">
                    <button class="slider-nav-btn" id="awardsPrev">
                        <i class="fas fa-chevron-left"></i>
                    </button>
                    <button class="slider-nav-btn" id="awardsNext">
                        <i class="fas fa-chevron-right"></i>
                    </button>
                </div>
            </div>
        </div>
    </section>

    <!-- Collaborations Section -->
    <section class="collaboration-section" id="collaborations">
        <div class="container">
            <div class="section-title">
                <h2 data-i18n="collaborations.title">Collaborations</h2>
                <p data-i18n="collaborations.description">Organizations and institutions I've collaborated with</p>
            </div>
            <div class="collaboration-container">
                <div class="collaboration-content" id="collaborationsContent">
                    <!-- Items will be filled by JavaScript -->
                </div>
            </div>
        </div>
    </section>

    <!-- Photos Section -->
    <section class="photos-section" id="photos">
        <div class="container">
            <div class="section-title">
                <h2 data-i18n="photos.title">Photos</h2>
                <p data-i18n="photos.description">Moments from professional journey</p>
            </div>
            <div class="photos-grid" id="photosGrid">
                <!-- Items will be filled by JavaScript -->
            </div>
        </div>
    </section>

    <!-- Competency Section -->
    <section class="competency-section" id="competency">
        <div class="container">
            <div class="section-title">
                <h2 data-i18n="competency.title">Competency</h2>
                <p data-i18n="competency.description">Skills and expertise in Statistics, Data Science, and Computer Science</p>
            </div>
            <div class="skills-container" id="skillsContainer">
                <!-- Skills will be filled by JavaScript -->
            </div>
        </div>
    </section>

    <!-- Testimonials Section -->
    <section class="testimonials-section" id="testimonials">
        <div class="container">
            <div class="section-title">
                <h2 data-i18n="testimonials.title">Testimonials</h2>
                <p data-i18n="testimonials.description">What colleagues and clients say</p>
            </div>
            <div class="testimonials-slider">
                <div class="testimonial-card" id="testimonialCard">
                    <!-- Testimonial will be filled by JavaScript -->
                </div>
                <div class="testimonial-nav">
                    <button id="prevTestimonial"><i class="fas fa-chevron-left"></i></button>
                    <button id="nextTestimonial"><i class="fas fa-chevron-right"></i></button>
                </div>
                <div class="testimonial-dots" id="testimonialDots">
                    <!-- Dots will be filled by JavaScript -->
                </div>
            </div>
        </div>
    </section>

    <!-- Ask Me Section -->
    <section class="ask-me-section">
        <div class="container">
            <div class="section-title">
                <h2 data-i18n="ask.title">Ask Me</h2>
                <p data-i18n="ask.description">Have questions? Let's connect!</p>
            </div>
            <div class="ask-container">
                <div class="ask-form-container">
                    <div class="ask-form">
                        <div class="form-group">
                            <label for="question" data-i18n="ask.question_label">Your Question</label>
                            <textarea id="question" rows="5" data-i18n-placeholder="ask.question_placeholder" placeholder="Write your question here..."></textarea>
                        </div>
                        <div class="form-group">
                            <label for="email" data-i18n="ask.email_label">Email (optional)</label>
                            <input type="email" id="email" data-i18n-placeholder="ask.email_placeholder" placeholder="name@email.com">
                        </div>
                        <button type="button" class="btn" id="askButton" data-i18n="ask.ask_button">Ask Question</button>
                    </div>
                </div>
                <div class="ask-response">
                    <div class="response-header">
                        <i class="fas fa-comments"></i>
                        <h3 data-i18n="ask.connect">Let's Connect</h3>
                    </div>
                    <div class="response-content">
                        <p class="response-placeholder" data-i18n="ask.response_placeholder">Submit your question or connect directly via WhatsApp for immediate assistance.</p>
                        <a href="https://wa.me/621234567890" target="_blank" class="whatsapp-btn">
                            <i class="fab fa-whatsapp"></i>
                            <span data-i18n="ask.whatsapp">Chat on WhatsApp</span>
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Modal Popup -->
    <div class="modal-overlay" id="modalOverlay">
        <div class="modal">
            <div class="modal-header">
                <h3 id="modalTitle">Detail Title</h3>
                <button class="modal-close" id="modalClose">&times;</button>
            </div>
            <div class="modal-content" id="modalContent">
                <!-- Content will be filled by JavaScript -->
            </div>
            <div class="modal-footer">
                <button class="btn btn-outline" id="modalCloseBtn" data-i18n="modal.close">Close</button>
                <a href="#" class="btn" id="modalLink" target="_blank" data-i18n="modal.view_more">View More</a>
            </div>
        </div>
    </div>

    <!-- Footer -->
    <footer id="contact">
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3 data-i18n="footer.name">Ngurah Sentana</h3>
                    <p data-i18n="footer.description">Data Scientist & Computer Science Specialist creating data-driven solutions.</p>
                    <div class="social-links">
                        <a href="https://github.com/NgurahSentana" target="_blank"><i class="fab fa-github"></i></a>
                        <a href="https://linkedin.com/in/ngurahsentana" target="_blank"><i class="fab fa-linkedin-in"></i></a>
                        <a href="https://twitter.com/ngurahsentana" target="_blank"><i class="fab fa-twitter"></i></a>
                        <a href="mailto:ngurah.sentana@example.com"><i class="fas fa-envelope"></i></a>
                    </div>
                </div>
                <div class="footer-column">
                    <h3 data-i18n="footer.portfolio">Portfolio</h3>
                    <ul class="footer-links">
                        <li><a href="#projects" data-i18n="nav.projects">Projects</a></li>
                        <li><a href="#articles" data-i18n="nav.publications">Publications</a></li>
                        <li><a href="#experience" data-i18n="nav.experience">Experience</a></li>
                        <li><a href="#certificates" data-i18n="nav.certificates">Certificates</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3 data-i18n="footer.achievements">Achievements</h3>
                    <ul class="footer-links">
                        <li><a href="#organizations" data-i18n="nav.organizations">Organizations</a></li>
                        <li><a href="#awards" data-i18n="nav.awards">Awards</a></li>
                        <li><a href="#collaborations" data-i18n="nav.collaborations">Collaborations</a></li>
                        <li><a href="#photos" data-i18n="nav.photos">Photos</a></li>
                        <li><a href="#testimonials" data-i18n="nav.testimonials">Testimonials</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3 data-i18n="footer.contact">Contact</h3>
                    <ul class="footer-links">
                        <li><a href="mailto:ngurah.sentana@example.com">ngurah.sentana@example.com</a></li>
                        <li><a href="tel:+621234567890">+62 123 4567 890</a></li>
                        <li><a href="https://wa.me/621234567890" target="_blank">WhatsApp</a></li>
                        <li><a href="#ask" data-i18n="ask.title">Ask Me</a></li>
                    </ul>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; <span id="currentYear">2023</span> Ngurah Sentana. <span data-i18n="footer.rights">All rights reserved.</span></p>
            </div>
        </div>
    </footer>

    <!-- JavaScript -->
    <script>
        // Translation data
        const translations = {
            en: {
                // Navigation
                "nav.home": "Home",
                "nav.projects": "Projects",
                "nav.publications": "Publications",
                "nav.experience": "Experience",
                "nav.organizations": "Organizations",
                "nav.certificates": "Certificates",
                "nav.awards": "Awards",
                "nav.collaborations": "Collaborations",
                "nav.photos": "Photos",
                "nav.competency": "Competency",
                "nav.testimonials": "Testimonials",
                
                // Hero Section
                "hero.title": "Ngurah Sentana",
                "hero.description": "Data Scientist & Computer Science Specialist with expertise in Statistics, Machine Learning, and Software Development.",
                "hero.view_projects": "View Projects",
                "hero.contact_me": "Contact Me",
                
                // Sections
                "projects.title": "Projects",
                "projects.description": "Data science and software development projects",
                "articles.title": "Publications",
                "articles.description": "Research papers and articles",
                "experience.title": "Work Experience",
                "experience.description": "Professional journey and work experience",
                "organizations.title": "Organizations",
                "organizations.description": "Professional and academic organizations",
                "certificates.title": "Certificates",
                "certificates.description": "Professional certifications",
                "awards.title": "Awards",
                "awards.description": "Achievements and recognitions",
                "collaborations.title": "Collaborations",
                "collaborations.description": "Organizations and institutions I've collaborated with",
                "photos.title": "Photos",
                "photos.description": "Moments from professional journey",
                "competency.title": "Competency",
                "competency.description": "Skills and expertise in Statistics, Data Science, and Computer Science",
                "testimonials.title": "Testimonials",
                "testimonials.description": "What colleagues and clients say",
                
                // Ask Section
                "ask.title": "Ask Me",
                "ask.description": "Have questions? Let's connect!",
                "ask.question_label": "Your Question",
                "ask.question_placeholder": "Write your question here...",
                "ask.email_label": "Email (optional)",
                "ask.email_placeholder": "name@email.com",
                "ask.ask_button": "Ask Question",
                "ask.connect": "Let's Connect",
                "ask.response_placeholder": "Submit your question or connect directly via WhatsApp for immediate assistance.",
                "ask.whatsapp": "Chat on WhatsApp",
                
                // Footer
                "footer.name": "Ngurah Sentana",
                "footer.description": "Data Scientist & Computer Science Specialist creating data-driven solutions.",
                "footer.portfolio": "Portfolio",
                "footer.achievements": "Achievements",
                "footer.contact": "Contact",
                "footer.rights": "All rights reserved.",
                
                // Modal
                "modal.view_more": "View More",
                "modal.close": "Close"
            },
            id: {
                // Navigation
                "nav.home": "Beranda",
                "nav.projects": "Proyek",
                "nav.publications": "Publikasi",
                "nav.experience": "Pengalaman",
                "nav.organizations": "Organisasi",
                "nav.certificates": "Sertifikat",
                "nav.awards": "Penghargaan",
                "nav.collaborations": "Kolaborasi",
                "nav.photos": "Foto",
                "nav.competency": "Kompetensi",
                "nav.testimonials": "Testimoni",
                
                // Hero Section
                "hero.title": "Ngurah Sentana",
                "hero.description": "Spesialis Data Scientist & Computer Science dengan keahlian dalam Statistika, Machine Learning, dan Pengembangan Perangkat Lunak.",
                "hero.view_projects": "Lihat Proyek",
                "hero.contact_me": "Hubungi Saya",
                
                // Sections
                "projects.title": "Proyek",
                "projects.description": "Proyek data science dan pengembangan perangkat lunak",
                "articles.title": "Publikasi",
                "articles.description": "Makalah penelitian dan artikel",
                "experience.title": "Pengalaman Kerja",
                "experience.description": "Perjalanan profesional dan pengalaman kerja",
                "organizations.title": "Organisasi",
                "organizations.description": "Organisasi profesional dan akademik",
                "certificates.title": "Sertifikat",
                "certificates.description": "Sertifikasi profesional",
                "awards.title": "Penghargaan",
                "awards.description": "Pencapaian dan pengakuan",
                "collaborations.title": "Kolaborasi",
                "collaborations.description": "Organisasi dan institusi yang pernah saya kolaborasi",
                "photos.title": "Foto",
                "photos.description": "Momen dari perjalanan profesional",
                "competency.title": "Kompetensi",
                "competency.description": "Keterampilan dan keahlian dalam Statistika, Data Science, dan Computer Science",
                "testimonials.title": "Testimoni",
                "testimonials.description": "Apa kata rekan dan klien",
                
                // Ask Section
                "ask.title": "Tanyakan Saya",
                "ask.description": "Ada pertanyaan? Mari terhubung!",
                "ask.question_label": "Pertanyaan Anda",
                "ask.question_placeholder": "Tulis pertanyaan Anda di sini...",
                "ask.email_label": "Email (opsional)",
                "ask.email_placeholder": "nama@email.com",
                "ask.ask_button": "Ajukan Pertanyaan",
                "ask.connect": "Mari Terhubung",
                "ask.response_placeholder": "Kirim pertanyaan Anda atau hubungi langsung via WhatsApp untuk bantuan langsung.",
                "ask.whatsapp": "Chat di WhatsApp",
                
                // Footer
                "footer.name": "Ngurah Sentana",
                "footer.description": "Spesialis Data Scientist & Computer Science menciptakan solusi berbasis data.",
                "footer.portfolio": "Portofolio",
                "footer.achievements": "Pencapaian",
                "footer.contact": "Kontak",
                "footer.rights": "Semua hak dilindungi.",
                
                // Modal
                "modal.view_more": "Lihat Selengkapnya",
                "modal.close": "Tutup"
            }
        };

        // Current language
        let currentLang = 'en';

        // Data for portfolio - DIPERBAIKI: Menambahkan gambar untuk experience dan organizations
        const portfolioData = {
            projects: [
                {
                    id: 1,
                    title: "Joint Research: Modelling Shelf Life Banana Image with ANN",
                    description: "Artificial Neural Network model for predicting banana shelf life using image processing techniques.",
                    image: "https://images.unsplash.com/photo-1571771894821-ce9b6c11b08e?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80",
                    tags: ["Research", "Python", "ANN", "Image Processing", "Agriculture"],
                    link: "#",
                    status: "completed",
                    detailedDescription: "This research project develops an ANN model to predict banana shelf life from visual characteristics. The model analyzes color, texture, and spot patterns to estimate optimal ripeness and storage duration.",
                    technologies: ["Python", "TensorFlow", "OpenCV", "Scikit-learn", "Pandas", "NumPy"],
                    date: "2025"
                },
                {
                    id: 2,
                    title: "Comparison of VaR and CVaR in ESG Stocks, LQ45, and Combined Portfolios",
                    description: "Risk analysis comparing Value at Risk and Conditional Value at Risk across different portfolio types during pandemic periods.",
                    image: "https://images.unsplash.com/photo-1611974789855-9c2a0a7236a3?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80",
                    tags: ["Finance", "Risk Analysis", "ESG", "Portfolio", "Research"],
                    link: "#",
                    status: "completed",
                    detailedDescription: "Comprehensive financial research comparing risk measurement methodologies across ESG-focused stocks, LQ45 index, and hybrid portfolios. Analysis covers pre-pandemic, mid-pandemic, and post-pandemic crisis periods.",
                    technologies: ["R", "Python", "Quantitative Finance", "Statistical Analysis", "Excel"],
                    date: "2025"
                },
                {
                    id: 3,
                    title: "Platform X Sentiment Analysis with Logistic Regression and Random Forest",
                    description: "Social media sentiment classification using machine learning algorithms for real-time opinion mining.",
                    image: "https://images.unsplash.com/photo-1611605698335-8b1569810432?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80",
                    tags: ["NLP", "Machine Learning", "Sentiment Analysis", "Social Media", "Python"],
                    link: "#",
                    status: "completed",
                    detailedDescription: "Sentiment analysis system for Platform X (formerly Twitter) data using Logistic Regression and Random Forest algorithms. Features include real-time data streaming, emoji interpretation, and trend detection.",
                    technologies: ["Python", "Scikit-learn", "NLTK", "Tweepy API", "Pandas", "Flask"],
                    date: "2025"
                },
                {
                    id: 4,
                    title: "Comparison of Food Security and Waste Clustering in Indonesian Provinces",
                    description: "Geospatial clustering analysis of food security and waste patterns across Indonesian provinces.",
                    image: "https://images.unsplash.com/photo-1556909114-f6e7ad7d3136?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80",
                    tags: ["Data Science", "Clustering", "K-Means", "SOM", "Geospatial"],
                    link: "#",
                    status: "completed",
                    detailedDescription: "Comparative study using K-Means and Self-Organizing Maps (SOM) to cluster Indonesian provinces based on food security indicators and waste management metrics. Includes interactive visualization of regional patterns.",
                    technologies: ["Python", "Scikit-learn", "MiniSom", "GeoPandas", "Matplotlib", "Folium"],
                    date: "2025"
                },
                {
                    id: 5,
                    title: "World University Ranking Dashboard Report",
                    description: "Interactive dashboard for analyzing and comparing global university rankings across multiple metrics.",
                    image: "https://images.unsplash.com/photo-1562774053-701939374585?ixlib=rb-4.0.3&auto=format&fit=crop&w=1464&q=80",
                    tags: ["Data Visualization", "Dashboard", "Education", "Analytics", "Tableau"],
                    link: "https://worldrankdashboard.streamlit.app/",
                    status: "completed",
                    detailedDescription: "Comprehensive dashboard analyzing world university rankings from THE. Features include multi-year trend analysis, country comparisons, and correlation between ranking factors.",
                    technologies: ["Streamlit", "Python", "Pandas", "SQL", "Data Visualization"],
                    date: "2025"
                },
                {
                    id: 6,
                    title: "West Java Tourism Interactive Dashboard and Application",
                    description: "Digital platform for promoting and managing tourism destinations in West Java province.",
                    image: "https://images.unsplash.com/photo-1544551763-46a013bb70d5?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80",
                    tags: ["Web Development", "Tourism", "Dashboard", "GIS", "Mobile App"],
                    link: "https://ngurahsentana24.shinyapps.io/Wisatajawabarat",
                    status: "completed",
                    detailedDescription: "Full-stack tourism platform featuring interactive maps, destination recommendations, visitor analytics, and booking system. Includes mobile application for tourists and web dashboard for administrators.",
                    technologies: ["R Shiny", "SQL", "JavaScript", "Leaflet", "Express.js"],
                    date: "2025"
                },
                {
                    id: 7,
                    title: "Trash Analysis Interactive Dashboard and Application",
                    description: "Waste management analytics platform for monitoring and optimizing trash collection and recycling.",
                    image: "https://images.unsplash.com/photo-1532996122724-e3c354a0b15b?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80",
                    tags: ["Environmental Tech", "Dashboard", "Analytics", "IoT", "Sustainability"],
                    link: "#",
                    status: "ongoing",
                    detailedDescription: "Smart waste management system with real-time monitoring of trash levels, collection routes optimization, and recycling rate tracking. Integrates IoT sensor data with predictive analytics.",
                    technologies: ["R Shiny", "Python", "IoT Sensors", "Predictive Analytics", "PostgreSQL"],
                    date: "2025"
                },
                {
                    id: 8,
                    title: "Supply Chain Management System - National Nutrition Agency",
                    description: "Digital transformation of supply chain operations for national nutrition distribution programs.",
                    image: "https://raw.githubusercontent.com/ngurahsentana24/Archive/main/photos/sppg.jpeg",
                    tags: ["Supply Chain", "Management System", "Logistics", "ERP", "Public Health"],
                    link: "#",
                    status: "completed",
                    detailedDescription: "Enterprise resource planning system for managing nutrition supply chain from procurement to distribution. Features include inventory management, demand forecasting, and distribution tracking.",
                    technologies: ["R", "Python", "SQL", "Supply Chain Analytics", "ERP Systems"],
                    date: "2025"
                },
                {
                    id: 9,
                    title: "ICODMI International Conference - SSMI Committee",
                    description: "Research paper presentation at international conference on data mining and informatics.",
                    image: "https://raw.githubusercontent.com/ngurahsentana24/Archive/main/photos/icodmi.jpeg",
                    tags: ["Conference", "Research", "Academic", "Data Mining", "Presentation"],
                    link: "#",
                    status: "completed",
                    detailedDescription: "Presented research paper on advanced data mining techniques at ICODMI International Conference. Paper focused on scalable machine learning algorithms for large-scale datasets.",
                    technologies: ["Academic Writing", "Research Presentation", "Data Mining", "Machine Learning"],
                    date: "2025"
                },
                {
                    id: 10,
                    title: "Teaching Assistant - Data Science Course",
                    description: "Assisted in teaching undergraduate data science course, covering fundamentals and practical applications.",
                    image: "https://images.unsplash.com/photo-1503676260728-1c00da094a0b?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80",
                    tags: ["Teaching", "Education", "Data Science", "Mentoring", "Python"],
                    link: "#",
                    status: "completed",
                    detailedDescription: "Teaching assistant responsibilities included conducting lab sessions, grading assignments, developing course materials, and providing one-on-one tutoring for data science concepts and programming.",
                    technologies: ["Python", "R", "Tidymodels", "Teaching", "Curriculum Development"],
                    date: "2025"
                },
                {
                    id: 11,
                    title: "Teaching Assistant - Relational Data Management Course",
                    description: "Assisted in teaching database management systems focusing on relational models and SQL.",
                    image: "https://raw.githubusercontent.com/ngurahsentana24/Archive/main/photos/mdr.jpeg",
                    tags: ["Database", "SQL", "Teaching", "Data Modeling", "SAS"],
                    link: "#",
                    status: "completed",
                    detailedDescription: "Supported students in understanding relational database concepts, SQL query optimization, normalization, and database design principles through workshops and individual consultations.",
                    technologies: ["SQL", "MySQL", "Database Design", "ERD", "SAS"],
                    date: "2025"
                },
                {
                    id: 12,
                    title: "Teaching Assistant - Engineering Statistics Course",
                    description: "Assisted in teaching statistical methods for engineering applications and data analysis.",
                    image: "https://raw.githubusercontent.com/ngurahsentana24/Archive/main/photos/statek.jpeg",
                    tags: ["Statistics", "Engineering", "Teaching", "R", "Data Analysis"],
                    link: "#",
                    status: "completed",
                    detailedDescription: "Facilitated understanding of statistical concepts including probability distributions, hypothesis testing, regression analysis, and experimental design specifically for engineering contexts.",
                    technologies: ["R", "Statistical Analysis", "Engineering Mathematics", "Hypothesis Testing", "Regression"],
                    date: "2025"
                }
            ],
            articles: [
                {
                    "id": 1,
                    "title": "Integration of RFM, K-Means, and XGBoost for Customer Retention Optimization in Online Retail",
                    "description": "Integrative research applying RFM analysis, K-Means clustering, and XGBoost for customer churn prediction and segmentation in online retail.",
                    "image": "https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80",
                    "journal": "Konstelasi: Scientific Journal of Duta Wacana Christian University Students",
                    "date": "June 2025",
                    "doi": "https://doi.org/10.24002/konstelasi.v5i1.11409",
                    "abstract": "Customer retention is a critical aspect of business, particularly in the retail and banking industries. This study integrates RFM (Recency, Frequency, Monetary) analysis, K-Means Clustering, and XGBoost to optimize customer retention strategies. RFM analysis is used to group customers based on purchasing behavior, while K-Means Clustering enables more in-depth segmentation. XGBoost is employed to predict churn with high accuracy. The results show that Frequency is the dominant factor in determining churn, with prediction accuracy reaching 99.77%. A case study on the Online Retail dataset identifies four customer clusters with distinct characteristics and churn rates. Strategic recommendations focus on increasing transaction frequency and service personalization. This research contributes to the development of more effective and targeted retention strategies.",
                    "keywords": ["RFM Analysis", "XGBoost", "Customer Retention", "Churn Prediction", "K-Means Clustering"],
                    "detailedDescription": "Comprehensive research integrating three analytical approaches for customer retention optimization. The RFM method is used for behavioral profiling, K-Means for cluster segmentation, and XGBoost for predictive churn modeling with very high accuracy. The case study is applied to an Online Retail dataset, with implementation results demonstrating the effectiveness of personalized retention strategies based on cluster segmentation."
                },
                {
                    "id": 3,
                    "title": "Evaluation of Fast Food Promotion Effectiveness Using a Hybrid Approach of Robust Non-Parametric Methods and Monte Carlo Simulation Based on Market Size Segmentation",
                    "description": "A hybrid approach combining non-parametric tests, Random Forest, and Monte Carlo simulation to evaluate and optimize fast food promotional strategies across different market segments.",
                    "image": "https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80",
                    "journal": "Jurnal Akuntansi, Ekonomi dan Manajemen Bisnis",
                    "date": "July 2025",
                    "doi": "https://doi.org/10.30871/jaemb.v13i1.9313",
                    "abstract": "The fast food industry is highly competitive, requiring effective promotional strategies to drive sales and maintain customer loyalty. This study evaluates the effectiveness of fast food promotions using a hybrid approach combining robust non-parametric methods, Random Forest, and Monte Carlo simulation. The analysis focuses on segmenting the market by Market Size (Large, Medium, Small) to identify the most impactful promotional strategies for each segment. Non-parametric A/B testing using the Kruskal-Wallis test revealed significant differences in sales across promotions, with Promotion 1 emerging as the most effective overall. The Random Forest model highlighted LocationID as the most critical factor influencing sales, particularly in Large markets. Monte Carlo simulation further demonstrated that Promotion 1 yields the highest Expected Monetary Value (EMV), making it the optimal choice for long-term sales growth. The findings emphasize the importance of tailoring promotional strategies to specific market segments, considering factors such as location, timing, and store history. This study provides actionable insights for businesses to optimize promotional campaigns, enhance sales performance, and achieve sustainable growth in the fast food industry.",
                    "keywords": ["Fast Food Restaurant", "Promotion Strategy", "Non-Parametric Methods", "Monte Carlo Simulation", "Market Segmentation"],
                    "detailedDescription": "A comprehensive evaluation of promotional effectiveness in the fast food sector using a novel hybrid methodology. The study segments markets by size and applies robust non-parametric statistical tests (Kruskal-Wallis) to compare promotion performance, followed by Random Forest modeling to identify key sales drivers. Monte Carlo simulations are then used to forecast long-term financial outcomes and calculate the Expected Monetary Value of each promotional strategy, providing data-driven recommendations for campaign optimization."
                },
                {
                    "id": 3,
                    "title": "Detection of Adulteration in Coconut Milk Using Cuckoo Search-Optimized XGBoost on High-Dimensional FTIR Spectral Data",
                    "description": "A novel method combining FTIR spectroscopy and machine learning for rapid, non-destructive detection of coconut milk adulteration.",
                    "image": "https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80",
                    "journal": "Jurnal Ilmiah Pendidikan Indonesia",
                    "date": "July 2025",
                    "doi": "https://doi.org/10.29100/jipi.v10i3.8376",
                    "abstract": "Coconut milk adulteration is an important issue because it can reduce food quality and endanger consumers. This study aims to develop a rapid and accurate detection method for coconut milk adulteration using a combination of FTIR spectroscopy technology and the XGBoost machine learning algorithm optimized with the Cuckoo Search Algorithm (CSA). FTIR spectral data from traditional and instant coconut milk samples were analyzed using Standard Normal Variate (SNV) and Savitzky-Golay (SG) preprocessing to reduce noise and clarify spectral features. The XGBoost model was then optimized through CSA with hyperparameter tuning. The results showed that the combination of SNV+SG preprocessing increased the model accuracy by 84.44%, with a precision of 92.73% and an F1-score of 79.94%. In addition, CSA optimization provided a 19.7% increase in accuracy compared to the model without tuning. These findings prove the effectiveness of the CSA-XGBoost approach in analyzing high-dimensional spectral data and is a potential solution in efficiently detecting the authenticity of coconut milk. In conclusion, this approach has the potential to be widely applied to test the authenticity of other food products quickly, non-destructively and accurately.",
                    "keywords": ["Adulteration", "FTIR Spectroscopy", "XGBoost", "Cuckoo Search Algorithm", "Spectral Preprocessing"],
                    "detailedDescription": "This research presents an innovative machine learning pipeline for food authenticity testing. It integrates Fourier Transform Infrared (FTIR) spectroscopy with an advanced XGBoost model whose hyperparameters are optimized using the nature-inspired Cuckoo Search Algorithm. The study demonstrates significant improvements in detection accuracy through proper spectral preprocessing (SNV and Savitzky-Golay) and metaheuristic optimization, offering a fast, non-destructive solution for quality control in the food industry."
                },
                {
                    "id": 4,
                    "title": "Performance Comparison of Random Forest and XGBoost Optimized with Cuckoo Search Algorithm for Coconut Milk Adulteration Detection Using FTIR Spectroscopy",
                    "description": "Comparative study of machine learning models optimized with metaheuristic algorithms for detecting adulteration in coconut milk using spectroscopy data.",
                    "image": "https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80",
                    "journal": "Journal of Mathematics and Computer Science",
                    "date": "October 2025",
                    "doi": "https://doi.org/10.35580/jmathcos.v8i2.7817",
                    "abstract": "Coconut milk has emerged as a strategic food commodity in the global tropical region, with market demand growing at 7.2% per annum since 2021. This increasing demand has led to sophisticated adulteration practices, including dilution with water. Such adulteration not only reduces the nutritional value but also poses serious health risks, including food poisoning and allergic reactions. This study developed an innovative detection method combining Fourier Transform Infrared (FTIR) spectroscopy with a sophisticated machine learning algorithm. We analyzed 719 coconut milk samples (wavelength range 2500-4000 nm) consisting of traditional market products and instant commercial products. This study aims to develop an FTIR-based coconut milk adulteration detection model by optimizing RF and XGBoost parameters using CSA and evaluating the comparative performance of the two models in identifying different types of adulterants. The spectral data underwent rigorous preprocessing using a combination of Standard Normal Variate (SNV) and Savitzky-Golay (SG) techniques to overcome the effects of noise and light scattering, which significantly improved feature extraction. The results show that CSA-optimized XGBoost achieves superior performance with 92% accuracy and 91% F1 score, outperforming Random Forest in all evaluation metrics. The model shows particular strength in precision (98%), indicating its outstanding ability to minimize false positives in adulteration detection. Stability tests through 30 experimental repetitions reveal that the combination of XGBoost+CSA maintains consistent performance with minimal variance, confirming its reliability for industrial applications. Comparative analysis shows that the combination of SNV+SG preprocessing improves the accuracy of the baseline model by 9-12%, while CSA optimization provides an additional performance improvement of 10-15%. This research makes significant contributions to food science and safety. This study demonstrates the effectiveness of CSA in optimizing spectroscopic models, achieving 19.5% higher precision.",
                    "keywords": ["FTIR Spectroscopy", "Random Forest", "XGBoost", "Coconut Milk Adulteration", "Cuckoo Search Algorithm"],
                    "detailedDescription": "This comprehensive research compares two powerful machine learning algorithms—Random Forest and XGBoost—for detecting adulteration in coconut milk using FTIR spectral data. Both models are enhanced with the Cuckoo Search Algorithm for hyperparameter optimization. The study involves extensive preprocessing techniques (SNV and Savitzky-Golay) and rigorous validation, demonstrating that CSA-optimized XGBoost significantly outperforms Random Forest across all metrics, offering a robust, non-destructive solution for food authenticity testing in industrial applications."
                },
                {
                    "id": 5,
                    "title": "Evaluating FastText and Glove Embeddings for Sentiment Analysis of AI-Generated Ghibli-Style Images",
                    "description": "Comparative analysis of word embedding techniques for sentiment classification of public reactions to AI-generated Ghibli-style artwork.",
                    "image": "https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80",
                    "journal": "Journal of Artificial Intelligence and Computing",
                    "date": "October 2025",
                    "doi": "https://doi.org/10.30871/jaic.v9i5.10600",
                    "abstract": "The development of text-to-image generation technology based on artificial intelligence has triggered mixed public reactions, especially when applied to iconic visual styles such as Studio Ghibli. This research aims to evaluate public sentiment towards the phenomenon of Ghibli-style AI images by comparing two static word embedding methods, namely FastText and GloVe, on three classification algorithms: Logistic Regression, Random Forest, and Convolutional Neural Network (CNN). Data in the form of Indonesian tweets were collected from Twitter using hashtags such as #ghibli, #ghiblistyle, and #hayaomiyazaki during the period 25 March to 25 April 2025. Each tweet was manually labelled with positive or negative sentiment, then preprocessed and represented using pre-trained FastText and GloVe embeddings. Evaluation was conducted using accuracy, precision, recall, and F1-score metrics, both macro and weighted. Results showed that FastText consistently performed the best on most models, especially in terms of precision and overall accuracy, thanks to its ability to handle sub-word information and spelling variations in social media texts. The combination of CNN with FastText yielded the highest performance with a macro F1-score of 76.56% and accuracy of 84.69%. However, GloVe still showed competitive performance in recall on the Logistic Regression model, making it relevant for contexts that prioritise sentiment detection coverage. This study emphasizes the importance of selecting embeddings and models that are appropriate to the characteristics of the data and the purpose of the analysis in informal social media-based sentiment classification.",
                    "keywords": ["Sentiment Analysis", "Word Embedding", "FastText", "GloVe", "Ghibli AI"],
                    "detailedDescription": "This research investigates public sentiment toward AI-generated Studio Ghibli-style images by comparing the effectiveness of FastText and GloVe word embeddings across multiple machine learning classifiers. Using a dataset of Indonesian tweets, the study demonstrates that FastText, with its sub-word information capabilities, outperforms GloVe in handling informal social media language, achieving optimal results when combined with a CNN model. The findings provide valuable insights for selecting appropriate NLP techniques for sentiment analysis on noisy, real-world social media data."
                },
                {
                    "id": 6,
                    "title": "Palm Oil Adulteration Detection Using Model Averaging of Machine Learning Classifiers on Simulated Chemical Data",
                    "description": "A machine learning framework using model averaging of KNN, SVM, and Random Forest to detect palm oil adulteration from synthetic FTIR spectral data.",
                    "image": "https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80",
                    "journal": "International Journal of Oil Palm",
                    "date": "October 2025",
                    "doi": "https://doi.org/10.5281/zenodo.139",
                    "abstract": "Palm oil adulteration poses significant health and economic risks, necessitating accurate detection methods. This study develops a machine learning framework combining KNN, SVM, and Random Forest via weighted model averaging to analyze synthetic FTIR spectra simulating pure and adulterated palm oil. SVM emerged as the top performer (97.3% accuracy), significantly outperforming Random Forest (86.9%) and KNN (85.9%). Principal Component Analysis revealed distinct clustering, with PC1 (63.3% variance) strongly correlate with key adulteration markers like ester C=O (1745 cm⁻¹) and OH (3300 cm⁻¹) vibrations. Spectral segmentation identified the 1000–1100 cm⁻¹ region (C-O stretches) as most critical for detection, enabling a proposed two-stage screening protocol that reduces analysis time by 60% while maintaining >90% accuracy for 5% adulterant concentrations. The synthetic dataset, validated against experimental references, replicated physicochemical trends, including peak broadening in oxidized samples (+20% FWHM) and dye-specific N=O peaks (1520 cm⁻¹). Model averaging enhanced stability, reducing performance variability to 1.2% versus 3.5–4.8% for individual models. These results highlight SVM’s superiority in handling high-dimensional spectral data and non-linear patterns, while the methodological advances—including noise modeling (SNR = 40 dB) and feature selection—offer practical solutions for portable FTIR devices. The framework supports real-time adulteration screening in resource-limited settings, with implications for food safety regulation and IoT-based quality monitoring in global palm oil supply chains.",
                    "keywords": ["Palm Oil Adulteration", "Model Averaging", "Simulated Data", "Machine Learning", "Ensemble Learning"],
                    "detailedDescription": "This research presents an innovative ensemble learning approach for detecting palm oil adulteration using synthetic FTIR spectroscopy data. The study compares KNN, SVM, and Random Forest classifiers, finding SVM to be the most accurate. Through weighted model averaging, the framework significantly improves prediction stability and reliability. Key spectral regions for adulteration detection are identified, enabling the development of an efficient two-stage screening protocol. The use of simulated data validated against experimental references demonstrates a practical, cost-effective method for food safety monitoring, particularly suitable for portable devices and resource-limited environments."
                },
                {
                    "id": 7,
                    "title": "Classification of Cardiovascular and Chronic Respiratory Diseases Utilizing Ensemble Models with Data Exploration Techniques",
                    "description": "Evaluation of data preprocessing and ensemble learning methods for classifying non-communicable diseases using BPJS health insurance claims data.",
                    "image": "https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80",
                    "journal": "Jurnal Ilmiah Pendidikan Indonesia",
                    "date": "2025",
                    "doi": "https://doi.org/10.29100/jipi.v10i4.9311",
                    "abstract": "Non-communicable diseases, especially cardiovascular and chronic respiratory conditions, contribute significantly to Indonesia’s healthcare burden and BPJS expenditure. Health claim data often suffer from class imbalance, multicollinearity, and outliers that impair model accuracy. This study evaluates the impact of essential data exploration techniques such as winsorizing, correlation and VIF analysis, variable selection, and SMOTE on the performance of ensemble classifiers. The dataset comprises 497,439 BPJS health insurance claims from 2022, including 27 predictors (14 numerical and 13 categorical). Two data pipelines were compared: one without preprocessing and another incorporating systematic data exploration. Five ensemble models were tested, namely Decision Tree, Extra Trees, Random Forest, XGBoost, and LightGBM. Model performance was assessed using F1-score, balanced accuracy, and G-mean across 20 stratified cross-validations. The results show that preprocessing substantially improves classification fairness and accuracy. Bagging models, particularly Random Forest, achieved the highest improvement, with balanced accuracy and G-mean increasing from around 0.93 to 0.99. Boosting models showed modest gains. These findings highlight that rigorous data exploration enhances ensemble classifier performance, enabling more reliable disease classification and supporting fairer, data-driven decision-making in BPJS health management.",
                    "keywords": ["BPJS Health Insurance", "Data Exploration", "Ensemble Learning", "Preprocessing", "Random Forest"],
                    "detailedDescription": "This research investigates the critical role of data preprocessing techniques—including outlier handling (winsorizing), multicollinearity reduction (VIF analysis), and class imbalance correction (SMOTE)—in improving the performance of ensemble machine learning models for disease classification. Using a large-scale BPJS health claims dataset, the study demonstrates that systematic data exploration significantly enhances model fairness and accuracy, with Random Forest showing the most substantial gains. The findings provide a robust framework for handling real-world healthcare data challenges and support the development of more equitable and accurate predictive models for public health management."
                },
               {
                    "id": 8,
                    "title": "Development of Situ Gede Lake Tourism and Local MSMEs through Web-Based Digital Promotion and Data Analysis",
                    "description": "On Progress",
                    "image": "https://images.unsplash.com/photo-1506744038136-46273834b3fb?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80",
                    "journal": "",
                    "date": "",
                    "doi": "",
                    "abstract": "",
                    "keywords": [],
                    "detailedDescription": ""
                  },
                  {
                    "id": 9,
                    "title": "Modeling Climate Change In The Asean Region Using Co₂ Trade Network-Based Spatial-Temporal Graph Neural Network (St-Gnn) And Impact Analysis On Indonesia",
                    "description": "On Reviewer",
                    "image": "https://images.unsplash.com/photo-1611273426858-450d8e3c9fce?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80",
                    "journal": "",
                    "date": "",
                    "doi": "",
                    "abstract": "",
                    "keywords": [],
                    "detailedDescription": ""
                  },
                  {
                    "id": 10,
                    "title": "Optimizing Sustainable and Efficient Supply Chains A Hybrid Metaheuristic Approach Combining Komodo Mlipir, Human Learning, and Simulated Annealing",
                    "description": "On Progress",
                    "image": "https://images.unsplash.com/photo-1555949963-aa79dcee981c?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80",
                    "journal": "",
                    "date": "",
                    "doi": "",
                    "abstract": "",
                    "keywords": [],
                    "detailedDescription": ""
                  },
                  {
                    "id": 11,
                    "title": "Multi-Explainable Machine Learning Approach for Food Security Index Classification in Indonesia",
                    "description": "On Progress",
                    "image": "ttps://images.unsplash.com/photo-1581094794329-c8112a89af12?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80",
                    "journal": "",
                    "date": "",
                    "doi": "",
                    "abstract": "",
                    "keywords": [],
                    "detailedDescription": ""
                  },
                  {
                    "id": 12,
                    "title": "Perbandingan Metode Interpolasi Spasial Idw Dan Adaptive Idw Untuk Estimasi Konsentrasi Pm2.5 (Studi Kasus : Amerika Serikat Tahun 2024)",
                    "description": "On Progress",
                    "image": "https://images.unsplash.com/photo-1635070041078-e363dbe005cb?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80",
                    "journal": "",
                    "date": "",
                    "doi": "",
                    "abstract": "",
                    "keywords": [],
                    "detailedDescription": ""
                  },
                  {
                    "id": 13,
                    "title": "Evaluation of Tree-Based Models for Predicting Social Assistance Recipient Status Based on National Socio-Economic Survey (SUSENAS) 2024",
                    "description": "On Progress",
                    "image": "",
                    "journal": "",
                    "date": "",
                    "doi": "",
                    "abstract": "",
                    "keywords": [],
                    "detailedDescription": ""
                  }
            ],
            experiences: [
                {
                    id: 1,
                    title: "Researcher",
                    company: "Freelance & Academic Projects",
                    period: "2023 – Present",
                    description: "Applying statistical methods, data science techniques, and machine learning approaches to generate insights and contribute to knowledge development. Conducting data-driven experiments and analyzing complex datasets to address real-world problems.",
                    image: "https://images.unsplash.com/photo-1554475900-0a0350bad5c8?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80", // PERBAIKAN: Menambahkan gambar
                    achievements: [
                        "Published research papers in national journal about statistical and machine learning",
                        "Developed predictive models for agricultural and financial applications with high accuracy rates",
                        "Conducted comprehensive risk analysis comparing VaR and CVaR methodologies across portfolio types",
                        "Implemented ANN models for image-based shelf life prediction in agricultural products"
                    ],
                    images: [
                        "https://images.unsplash.com/photo-1554475900-0a0350bad5c8?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80",
                        "https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80"
                    ]
                },
                {
                    id: 2,
                    title: "Freelance Data Scientist",
                    company: "Freelance Projects",
                    period: "2023 – Present",
                    description: "Providing end-to-end solutions in data collection, cleansing, analysis, and visualization to support diverse business needs. Building predictive models, analyzing performance metrics, developing dashboards, and delivering actionable insights across various industries.",
                    image: "https://images.unsplash.com/photo-1559757148-5c350d0d3c56?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80", // PERBAIKAN: Menambahkan gambar
                    achievements: [
                        "Delivered data-driven solutions for clients across e-commerce, healthcare, and tourism sectors",
                        "Built interactive dashboards that improved decision-making efficiency",
                        "Developed predictive models for sales forecasting",
                        "Created comprehensive analytics for supply chain and waste management systems"
                    ],
                    images: [
                        "https://raw.githubusercontent.com/ngurahsentana24/Archive/main/photos/sppg.jpeg",
                        "https://images.unsplash.com/photo-1611974789855-9c2a0a7236a3?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80"
                    ]
                },
                {
                    id: 3,
                    title: "Data Analyst Lead",
                    company: "Lumbung Group",
                    period: "Apr 2024 – 2025",
                    description: "Overseeing the end-to-end process of transforming raw data into actionable business insights. Analyzing sales performance, conducting product and shop analysis, and leading comprehensive business evaluations to identify growth opportunities and optimize company strategies.",
                    image: "https://images.unsplash.com/photo-1552664730-d307ca884978?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80", // PERBAIKAN: Menambahkan gambar
                    achievements: [
                        "Led analyst team in delivering insights that contributed to 30% sales growth in target segments",
                        "Developed and implemented data analysis frameworks reducing report generation time by 50%",
                        "Created predictive models for optimization",
                        "Mentored and trained 5 analysts in SQL and data visualization techniques",
                        "Designed reporting systems that saved 15+ hours weekly in manual work"
                    ],
                    images: [
                        "https://images.unsplash.com/photo-1552664730-d307ca884978?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80",
                        "https://images.unsplash.com/photo-1460925895917-afdab827c52f?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80"
                    ]
                },
                {
                    id: 4,
                    title: "Data Analyst",
                    company: "Lumbung Group",
                    period: "Jan 2023 – Mar 2024",
                    description: "Analyzing sales data and performance trends, conducting in-depth product and shop analysis, and carrying out comprehensive business analysis to identify growth opportunities and improve operational efficiency.",
                    image: "https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80", // PERBAIKAN: Menambahkan gambar
                    achievements: [
                        "Identified key market trends that led to development of 3 new successful product lines",
                        "Optimized pricing strategies resulting in 8% increase in profit margins",
                        "Created interactive dashboards that improved cross-departmental data accessibility",
                        "Developed customer segmentation models that increased campaign",
                        "Streamlined data collection processes reducing data processing time"
                    ],
                    images: [
                        "https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80",
                        "https://images.unsplash.com/photo-1552664730-d307ca884978?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80"
                    ]
                },
                {
                    id: 5,
                    title: "Teaching Assistant - Multiple Courses",
                    company: "University Academic Department",
                    period: "2025",
                    description: "Assisted in teaching undergraduate courses in Data Science, Relational Data Management, and Engineering Statistics. Conducted lab sessions, developed course materials, and provided individual tutoring to students.",
                    image: "https://images.unsplash.com/photo-1503676260728-1c00da094a0b?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80", // PERBAIKAN: Menambahkan gambar
                    achievements: [
                        "Improved average student performance",
                        "Developed practical case studies that enhanced student engagement and learning outcomes",
                        "Created comprehensive grading rubrics that improved assessment consistency",
                        "Mentored student groups on 10+ capstone projects"
                    ],
                    images: [
                        "https://raw.githubusercontent.com/ngurahsentana24/Archive/main/photos/mdr.jpeg",
                        "https://raw.githubusercontent.com/ngurahsentana24/Archive/main/photos/statek.jpeg"
                    ]
                },
                {
                    id: 6,
                    title: "Data Analyst Intern",
                    company: "Ruang Guru",
                    period: "Feb 2022 – Jul 2022",
                    description: "Gained solid knowledge in SQL, data analysis, and data visualization by working on various projects and case studies. Translated raw data into meaningful insights and actionable recommendations for educational technology applications.",
                    image: "https://images.unsplash.com/photo-1523050854058-8df90110c9f1?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80", // PERBAIKAN: Menambahkan gambar
                    achievements: [
                        "Developed user engagement analysis dashboard that identified key drop-off points",
                        "Created learning effectiveness metrics that informed curriculum improvements",
                        "Presented data-driven recommendations"
                    ],
                    images: [
                        "https://images.unsplash.com/photo-1523050854058-8df90110c9f1?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80",
                        "https://images.unsplash.com/photo-1577896851231-70ef18881754?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80"
                    ]
                }
            ],
            organizations: [
                {
                  id: 1,
                  title: "HIMPRO PASCASARJANA STATISTIKA",
                  role: "Chairman",
                  period: "2025",
                  description: "Postgraduate Statistics Student Association.",
                  image: "https://images.unsplash.com/photo-1523580494863-6f3031224c94?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80", // PERBAIKAN: Menambahkan gambar
                  activities: [
                    "Led academic, organizational, and community engagement programs",
                    "Coordinated events and fostered collaboration among postgraduate students",
                    "Enhanced the organization's contribution to scientific and professional development"
                  ],
                  images: [
                      "https://raw.githubusercontent.com/ngurahsentana24/Archive/main/photos/himpro.jpeg",
                      "https://raw.githubusercontent.com/ngurahsentana24/Archive/main/photos/SSD.jpeg",
                  ]
                },
                {
                  id: 2,
                  title: "Keluarga LPDP IPB 12.0",
                  role: "Head of the Social and Community Service Division",
                  period: "2025",
                  description: "Social and community service division.",
                  image: "https://images.unsplash.com/photo-1517048676732-d65bc937f952?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80", // PERBAIKAN: Menambahkan gambar
                  activities: [
                    "Coordinated social initiatives and managed community engagement programs",
                    "Led teams in delivering impactful projects",
                    "Strengthened student contributions to society"
                  ],
                  images: [
                      "https://raw.githubusercontent.com/ngurahsentana24/Archive/main/photos/sosmas2.jpeg",
                      "https://raw.githubusercontent.com/ngurahsentana24/Archive/main/photos/Sosmas.jpeg"
                  ]
                },
                {
                  id: 3,
                  title: "DPM PM Udayana",
                  role: "Chairman",
                  period: "2022",
                  description: "Student Representative Council at Udayana University.",
                  image: "https://images.unsplash.com/photo-1542744173-8e7e53415bb0?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80", // PERBAIKAN: Menambahkan gambar
                  activities: [
                    "Led the legislative body and managed student aspirations",
                    "Oversaw organizational governance",
                    "Ensured strategic collaboration between students and university leadership"
                  ],
                  images: []
                },
                {
                  id: 4,
                  title: "DPM PM Udayana",
                  role: "Commission III for Aspiration and Advocacy",
                  period: "2021",
                  description: "Student Representative Council at Udayana University.",
                  image: "https://images.unsplash.com/photo-1577896851231-70ef18881754?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80", // PERBAIKAN: Menambahkan gambar
                  activities: [
                    "Contributed to student representation and policy discussions",
                    "Served as Chair of the Temu Rektor event",
                    "Led coordination and execution of strategic forum between students and university leadership"
                  ],
                  images: []
                },
                {
                  id: 5,
                  title: "UKM PRAMUKA RACANA UDAYANA MAHENDRADATTA",
                  role: "Vice Chairman",
                  period: "2021",
                  description: "Scout Student Organization.",
                  image: "https://images.unsplash.com/photo-1524178234883-043d5c3f3cf4?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80", // PERBAIKAN: Menambahkan gambar
                  activities: [
                    "Developed leadership and organizational management skills",
                    "Chaired the major event TAKSAKA",
                    "Oversaw planning, coordination, and successful execution of events"
                  ],
                  images: []
                },
                {
                  id: 6,
                  title: "UDAYANA FOCUS",
                  role: "Vice Chairman",
                  period: "2020",
                  description: "Student organization in creative media.",
                  image: "https://images.unsplash.com/photo-1545235617-9465d2a55698?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80", // PERBAIKAN: Menambahkan gambar
                  activities: [
                    "Led activities and enhanced members' creative skills",
                    "Managed visual storytelling projects",
                    "Chaired the flagship event Ufonity, overseeing its full execution"
                  ],
                  images: []
                }
            ],
            certificates: [
                {
                    id: 1,
                    title: "IBM MACHINE LEARNING",
                    description: "Machine learning certification from IBM.",
                    issuer: "IBM",
                    date: "2024",
                    link: "",
                    image: "https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80"
                },
                {
                    id: 2,
                    title: "IBM DATA SCIENCE",
                    description: "Data science certification from IBM.",
                    issuer: "IBM",
                    date: "2024",
                    link: "",
                    image: "https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80"
                },
                {
                    id: 3,
                    title: "R FUNDAMENTAL",
                    description: "Fundamental R programming certification.",
                    issuer: "DQLab",
                    date: "2022",
                    link: "",
                    image: "https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80"
                },
                {
                    id: 4,
                    title: "SQL FUNDAMENTAL",
                    description: "Fundamental SQL database certification.",
                    issuer: "DQLab",
                    date: "2022",
                    link: "",
                    image: "https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80"
                }
            ],
            awards: [
                {
                    id: 1,
                    title: "BEST PAPER",
                    organization: "IJOP",
                    date: "2025",
                    description: "Awarded for outstanding research paper.",
                    image: "https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80",
                    details: "Recognized for excellence in academic writing and research contribution."
                },
                {
                    id: 2,
                    title: "BEST PRESENTER",
                    organization: "Konstelasi",
                    date: "2025",
                    description: "Awarded for exceptional presentation skills.",
                    image: "https://images.unsplash.com/photo-1559757148-5c350d0d3c56?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80",
                    details: "Recognized for outstanding presentation delivery and communication skills."
                },
                {
                    id: 3,
                    title: "PRESENTER ICDSOS STIS",
                    organization: "STIS",
                    date: "2025",
                    description: "Presenter at ICDSOS STIS conference.",
                    image: "https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80",
                    details: "Selected as presenter at ICDSOS STIS academic conference."
                },
                {
                    id: 4,
                    title: "2ND MILLENIAL ESSAY COMPETITION",
                    organization: "FKIP Universitas Lampung",
                    date: "2022",
                    description: "Achieved 2nd place in essay competition.",
                    image: "https://images.unsplash.com/photo-1559757148-5c350d0d3c56?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80",
                    details: "Awarded 2nd place in national essay competition."
                },
                {
                    id: 5,
                    title: "2ND MILLENIAL ESSAY COMPETITION",
                    organization: "FKIP Universitas Lampung",
                    date: "2021",
                    description: "Achieved 2nd place in essay competition.",
                    image: "https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80",
                    details: "Awarded 2nd place in national essay competition."
                },
                {
                    id: 6,
                    title: "3RD LEMM ESSAY COMPETITION",
                    organization: "FMIPA, Universitas Negeri Yogyakarta",
                    date: "2021",
                    description: "Achieved 3rd place in essay competition.",
                    image: "https://images.unsplash.com/photo-1559757148-5c350d0d3c56?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80",
                    details: "Awarded 3rd place in LEMM essay competition."
                },
                {
                    id: 7,
                    title: "TOP 5 ESSAY WRITING MATHLICIOUS",
                    organization: "Institut Agama Islam Negeri Kudus",
                    date: "2021",
                    description: "Top 5 finalist in essay competition.",
                    image: "https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80",
                    details: "Selected as top 5 finalist in Mathlicious essay competition."
                },
                {
                    id: 8,
                    title: "3RD GEMASTE ESSAY COMPETITION",
                    organization: "Universitas Negeri Semarang",
                    date: "2021",
                    description: "Achieved 3rd place in essay competition.",
                    image: "https://images.unsplash.com/photo-1559757148-5c350d0d3c56?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80",
                    details: "Awarded 3rd place in GEMASTE essay competition."
                }
            ],
            collaborations: [
                {
                    id: 1,
                    name: "Google",
                    icon: "fab fa-google",
                    link: "https://www.google.com"
                },
                {
                    id: 2,
                    name: "Microsoft",
                    icon: "fab fa-microsoft",
                    link: "https://www.microsoft.com"
                },
                {
                    id: 3,
                    name: "GitHub",
                    icon: "fab fa-github",
                    link: "https://github.com"
                },
                {
                    id: 4,
                    name: "Python",
                    icon: "fab fa-python",
                    link: "https://www.python.org"
                },
                {
                    id: 5,
                    name: "R Shiny",
                    icon: "fas fa-chart-line",
                    link: "https://shiny.rstudio.com"
                },
                {
                    id: 6,
                    name: "SAS",
                    icon: "fas fa-database",
                    link: "https://www.sas.com"
                },
                {
                    id: 7,
                    name: "ResearchGate",
                    icon: "fab fa-researchgate",
                    link: "https://www.researchgate.net"
                },
                {
                    id: 8,
                    name: "ORCID",
                    icon: "fas fa-id-card",
                    link: "https://orcid.org"
                },
                {
                    id: 9,
                    name: "Google Scholar",
                    icon: "fas fa-graduation-cap",
                    link: "https://scholar.google.com"
                },
                {
                    id: 10,
                    name: "RPubs",
                    icon: "fas fa-code",
                    link: "https://rpubs.com"
                }
            ],
            photos: [
                {
                    id: 1,
                    url: "https://raw.githubusercontent.com/ngurahsentana24/Archive/main/photos/SSD.jpeg",
                    alt: "Statistic and Data Science Student",
                    title: "Statistic and Data Science Student",
                    date: "2024",
                    description: "Statistic and Data Science Student IPB University"
                },
                {
                    id: 2,
                    url: "https://raw.githubusercontent.com/ngurahsentana24/Archive/main/photos/himpro.jpeg",
                    alt: "Team Collaboration",
                    title: "Himpo Pascasasrjana Statistika dan Sains Data",
                    date: "2025",
                    description: "Collaborating with team members on Himpo Pascasasrjana Statistika dan Sains Data"
                },
                {
                    id: 3,
                    url: "https://raw.githubusercontent.com/ngurahsentana24/Archive/main/photos/sosmas2.jpeg",
                    alt: "Team",
                    title: "LPDP IPB 12.0",
                    date: "2025",
                    description: "SOSMAS LPDP IPB 12.0"
                },
                {
                    id: 4,
                    url: "https://images.unsplash.com/photo-1556761175-5973dc0f32e7?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80",
                    alt: "Workshop Facilitation",
                    title: "Leading Data Science Workshop",
                    date: "2022",
                    description: "Facilitating hands-on data science workshop for students"
                },
                {
                    id: 5,
                    url: "https://raw.githubusercontent.com/ngurahsentana24/Archive/main/photos/mdr.jpeg",
                    alt: "Mentoring with engginering statistic student",
                    title: "Mentoring with engginering statistic student",
                    date: "2025",
                    description: "Mentoring with statistic student"
                },
                {
                    id: 6,
                    url: "https://raw.githubusercontent.com/ngurahsentana24/Archive/main/photos/statek.jpeg",
                    alt: "Mentoring Session",
                    title: "Mentoring with engginering statistic student",
                    date: "2023",
                    description: "Mentoring with engginering statistic student"
                }
            ],
            testimonials: [
                {
                    id: 1,
                    text: "Working with Ngurah was transformative for our data analytics capabilities. His machine learning models improved our prediction accuracy by 35% and his attention to detail is exceptional.",
                    author: "Sarah Johnson",
                    role: "CTO at TechCorp",
                    avatar: "https://randomuser.me/api/portraits/women/32.jpg"
                },
                {
                    id: 2,
                    text: "Ngurah's statistical insights and technical expertise were instrumental in our research project. He has a unique ability to translate complex concepts into actionable solutions.",
                    author: "Dr. Michael Chen",
                    role: "Research Director, University AI Lab",
                    avatar: "https://randomuser.me/api/portraits/men/75.jpg"
                },
                {
                    id: 3,
                    text: "The data visualization platform Ngurah built for us revolutionized how we analyze complex datasets. His work is both technically sophisticated and user-friendly.",
                    author: "Emma Wilson",
                    role: "Product Manager at DataTech",
                    avatar: "https://randomuser.me/api/portraits/women/44.jpg"
                },
                {
                    id: 4,
                    text: "Ngurah's mentorship helped our junior team members grow significantly. His ability to explain complex concepts clearly is remarkable.",
                    author: "David Kim",
                    role: "Team Lead, Analytics Division",
                    avatar: null
                }
            ],
            skills: {
                statistics: [
                    { name: "Statistical Analysis", percentage: 92 },
                    { name: "Regression Models", percentage: 88 },
                    { name: "Time Series Analysis", percentage: 80 },
                    { name: "Experimental Design", percentage: 80 },
                    { name: "Risk Analysis (VaR/CVaR)", percentage: 85 }
                ],
                dataScience: [
                    { name: "Machine Learning", percentage: 90 },
                    { name: "Data Visualization", percentage: 95 },
                    { name: "Natural Language Processing", percentage: 80 },
                    { name: "Clustering Algorithms", percentage: 85 },
                    { name: "Dashboard Development", percentage: 92 }
                ],
                computerScience: [ 
                    { name: "Python Programming", percentage: 90 },
                    { name: "R Programming", percentage: 90 },
                    { name: "SQL Database", percentage: 88 },
                    { name: "Data Analysis", percentage: 92 },
                    { name: "Statistical Software (SAS)", percentage: 85 }
                ]
            }
        };

        // Visitor statistics
        let visitorStats = {
            total: 0,
            today: 0,
            thisWeek: 0,
            thisMonth: 0,
            lastMonth: 0
        };

        // Calculate statistics with trends
        function calculateStats() {
            const now = new Date();
            const startYear = 2019;
            const yearsExperience = now.getFullYear() - startYear;
            
            // Mock trend data (would come from analytics in real app)
            const trends = {
                projects: { value: portfolioData.projects.filter(p => p.status === 'completed').length, trend: 15 },
                publications: { value: portfolioData.articles.length, trend: 25 },
                certificates: { value: portfolioData.certificates.length, trend: 10 },
                experience: { value: yearsExperience, trend: 0 },
                awards: { value: portfolioData.awards.length, trend: 20 },
                clients: { value: portfolioData.testimonials.length, trend: 30 },
                collaborations: { value: portfolioData.collaborations.length, trend: 20 },
                photos: { value: portfolioData.photos.length, trend: 15 }
            };
            
            return trends;
        }

        // Create stat card
        function createStatCard(stat, label, icon) {
            const stats = calculateStats();
            const data = stats[stat];
            
            return `
                <div class="stat-card">
                    <div class="stat-icon">
                        <i class="${icon}"></i>
                    </div>
                    <div class="stat-number">${data.value}</div>
                    <div class="stat-label">${label}</div>
                    ${data.trend > 0 ? `<span class="stat-trend">↑ ${data.trend}%</span>` : 
                       data.trend < 0 ? `<span class="stat-trend negative">↓ ${Math.abs(data.trend)}%</span>` : ''}
                </div>
            `;
        }

        // Create project card
        function createProjectCard(project) {
            return `
                <div class="project-card" data-id="${project.id}" data-type="project">
                    <div class="project-image-container">
                        <img src="${project.image}" alt="${project.title}" class="project-image">
                        <span class="project-status ${project.status}">${project.status === 'completed' ? 'Completed' : 'Ongoing'}</span>
                    </div>
                    <div class="card-content">
                        <h3>${project.title}</h3>
                        <p>${project.description}</p>
                        <div class="card-tags">
                            ${project.tags.map(tag => `<span class="tag">${tag}</span>`).join('')}
                        </div>
                        <div class="card-footer">
                            <span class="card-date">${project.date}</span>
                            <a href="#" class="view-more">View More <i class="fas fa-arrow-right"></i></a>
                        </div>
                    </div>
                </div>
            `;
        }

        // Create article card
        function createArticleCard(article) {
            return `
                <div class="article-card" data-id="${article.id}" data-type="article">
                    <div class="article-image-container">
                        <img src="${article.image}" alt="${article.title}" class="article-image">
                    </div>
                    <div class="card-content">
                        <h3>${article.title}</h3>
                        <p>${article.description}</p>
                        <div class="card-footer">
                            <span class="card-date">${article.date}</span>
                            <a href="#" class="view-more">View More <i class="fas fa-arrow-right"></i></a>
                        </div>
                    </div>
                </div>
            `;
        }

        // PERBAIKAN: Mengubah createExperienceCard untuk menampilkan gambar
        function createExperienceCard(experience) {
            return `
                <div class="experience-card" data-id="${experience.id}" data-type="experience">
                    <div class="experience-image-container">
                        <img src="${experience.image}" alt="${experience.title}" class="experience-image">
                    </div>
                    <div class="card-content">
                        <h3>${experience.title}</h3>
                        <p><strong>${experience.company}</strong></p>
                        <p>${experience.description.substring(0, 100)}...</p>
                        <div class="card-footer">
                            <span class="card-date">${experience.period}</span>
                            <a href="#" class="view-more">View Details <i class="fas fa-arrow-right"></i></a>
                        </div>
                    </div>
                </div>
            `;
        }

        // PERBAIKAN: Mengubah createOrganizationCard untuk menampilkan gambar
        function createOrganizationCard(organization) {
            return `
                <div class="organization-card" data-id="${organization.id}" data-type="organization">
                    <div class="organization-image-container">
                        <img src="${organization.image}" alt="${organization.title}" class="organization-image">
                    </div>
                    <div class="card-content">
                        <h3>${organization.title}</h3>
                        <p><strong>${organization.role}</strong></p>
                        <p>${organization.description}</p>
                        <div class="card-footer">
                            <span class="card-date">${organization.period}</span>
                            <a href="#" class="view-more">View Details <i class="fas fa-arrow-right"></i></a>
                        </div>
                    </div>
                </div>
            `;
        }

        // PERBAIKAN: Mengubah createCertificateCard untuk menampilkan gambar
        function createCertificateCard(certificate) {
            return `
                <div class="certificate-card" data-id="${certificate.id}" data-type="certificate">
                    <div class="certificate-image-container">
                        <img src="${certificate.image}" alt="${certificate.title}" class="certificate-image">
                    </div>
                    <div class="card-content">
                        <h3>${certificate.title}</h3>
                        <p>${certificate.description}</p>
                        <p><strong>${certificate.issuer}</strong></p>
                        <div class="card-footer">
                            <span class="card-date">${certificate.date}</span>
                            <a href="#" class="view-more">View More <i class="fas fa-arrow-right"></i></a>
                        </div>
                    </div>
                </div>
            `;
        }

        // PERBAIKAN: Mengubah createAwardCard untuk menampilkan gambar
        function createAwardCard(award) {
            return `
                <div class="award-card" data-id="${award.id}" data-type="award">
                    <div class="award-image-container">
                        <img src="${award.image}" alt="${award.title}" class="award-image">
                    </div>
                    <div class="card-content">
                        <h3>${award.title}</h3>
                        <p><strong>${award.organization}</strong></p>
                        <p>${award.description}</p>
                        <div class="card-footer">
                            <span class="card-date">${award.date}</span>
                            <a href="#" class="view-more">View Details <i class="fas fa-arrow-right"></i></a>
                        </div>
                    </div>
                </div>
            `;
        }

        // Function to create collaboration item
        function createCollaborationItem(collab) {
            return `
                <div class="collaboration-item" data-id="${collab.id}" data-type="collaboration">
                    <a href="${collab.link}" target="_blank" class="collaboration-icon">
                        <i class="${collab.icon}"></i>
                    </a>
                    <div class="collaboration-name">${collab.name}</div>
                </div>
            `;
        }

        // Function to create photo item
        function createPhotoItem(photo) {
            return `
                <div class="photo-item" data-id="${photo.id}" data-type="photo">
                    <img src="${photo.url}" alt="${photo.alt}">
                    <div class="photo-overlay">
                        <div class="photo-title">${photo.title}</div>
                        <div class="photo-date">${photo.date}</div>
                    </div>
                </div>
            `;
        }

        // Create testimonial card
        function createTestimonialCard(testimonial) {
            const avatar = testimonial.avatar ? 
                `<img src="${testimonial.avatar}" alt="${testimonial.author}" class="author-avatar">` :
                `<div class="author-icon"><i class="fas fa-user"></i></div>`;
            
            return `
                <div class="testimonial-card" data-id="${testimonial.id}">
                    <div class="testimonial-text">
                        ${testimonial.text}
                    </div>
                    <div class="testimonial-author">
                        ${avatar}
                        <div class="author-info">
                            <h4>${testimonial.author}</h4>
                            <p>${testimonial.role}</p>
                        </div>
                    </div>
                </div>
            `;
        }

        // Create skill category
        function createSkillCategory(categoryName, skills) {
            const icons = {
                statistics: "fas fa-chart-bar",
                dataScience: "fas fa-brain",
                computerScience: "fas fa-laptop-code" 
            };
            
            return `
                <div class="skill-category" data-category="${categoryName}">
                    <h3><i class="${icons[categoryName]}"></i> ${categoryName.split(/(?=[A-Z])/).join(' ')}</h3>
                    ${skills.map(skill => `
                        <div class="skill-item">
                            <div class="skill-header">
                                <span class="skill-name">${skill.name}</span>
                                <span class="skill-percentage">${skill.percentage}%</span>
                            </div>
                            <div class="skill-bar">
                                <div class="skill-progress" data-width="${skill.percentage}"></div>
                            </div>
                        </div>
                    `).join('')}
                </div>
            `;
        }

        // Render all elements
        function renderPortfolio() {
            const stats = calculateStats();
            
            // Render stats
            const statsContainer = document.getElementById('statsContainer');
            statsContainer.innerHTML = `
                ${createStatCard('projects', 'Projects', 'fas fa-project-diagram')}
                ${createStatCard('publications', 'Publications', 'fas fa-book')}
                ${createStatCard('certificates', 'Certificates', 'fas fa-award')}
                ${createStatCard('experience', 'Years Experience', 'fas fa-briefcase')}
                ${createStatCard('awards', 'Awards', 'fas fa-trophy')}
                ${createStatCard('clients', 'Happy Clients', 'fas fa-users')}
                ${createStatCard('collaborations', 'Collaborations', 'fas fa-handshake')}
                ${createStatCard('photos', 'Photos', 'fas fa-camera')}
            `;
            
            // Render projects (ongoing first)
            const sortedProjects = [...portfolioData.projects].sort((a, b) => {
                if (a.status === 'ongoing' && b.status !== 'ongoing') return -1;
                if (a.status !== 'ongoing' && b.status === 'ongoing') return 1;
                return new Date(b.date) - new Date(a.date);
            });
            
            const projectsContent = document.getElementById('projectsContent');
            projectsContent.innerHTML = sortedProjects.map(createProjectCard).join('');
            
            // Render articles (newest first)
            const sortedArticles = [...portfolioData.articles].sort((a, b) => new Date(b.date) - new Date(a.date));
            const articlesContent = document.getElementById('articlesContent');
            articlesContent.innerHTML = sortedArticles.map(createArticleCard).join('');
            
            // Render experiences (newest first)
            const experiencesContent = document.getElementById('experienceContent');
            experiencesContent.innerHTML = portfolioData.experiences.map(createExperienceCard).join('');
            
            // Render organizations
            const organizationsContent = document.getElementById('organizationsContent');
            organizationsContent.innerHTML = portfolioData.organizations.map(createOrganizationCard).join('');
            
            // Render certificates (newest first)
            const sortedCertificates = [...portfolioData.certificates].sort((a, b) => new Date(b.date) - new Date(a.date));
            const certificatesContent = document.getElementById('certificatesContent');
            certificatesContent.innerHTML = sortedCertificates.map(createCertificateCard).join('');
            
            // Render awards (newest first)
            const sortedAwards = [...portfolioData.awards].sort((a, b) => new Date(b.date) - new Date(a.date));
            const awardsContent = document.getElementById('awardsContent');
            awardsContent.innerHTML = sortedAwards.map(createAwardCard).join('');
            
            // Render collaborations
            const collaborationsContent = document.getElementById('collaborationsContent');
            collaborationsContent.innerHTML = portfolioData.collaborations.map(createCollaborationItem).join('');
            
            // Render photos
            const photosGrid = document.getElementById('photosGrid');
            photosGrid.innerHTML = portfolioData.photos.map(createPhotoItem).join('');
            
            // Render testimonials
            updateTestimonial();
            
            // Render testimonial dots
            const testimonialDots = document.getElementById('testimonialDots');
            testimonialDots.innerHTML = portfolioData.testimonials.map((_, index) => 
                `<div class="testimonial-dot ${index === 0 ? 'active' : ''}" data-index="${index}"></div>`
            ).join('');
            
            // Render skills
            const skillsContainer = document.getElementById('skillsContainer');
            skillsContainer.innerHTML = `
                ${createSkillCategory('statistics', portfolioData.skills.statistics)}
                ${createSkillCategory('dataScience', portfolioData.skills.dataScience)}
                ${createSkillCategory('computerScience', portfolioData.skills.computerScience)}
            `;
            
            // Add event listeners to all cards
            setTimeout(() => {
                addCardEventListeners();
            }, 100);
        }

        // Add event listeners to cards
        function addCardEventListeners() {
            // View more links
            document.querySelectorAll('.view-more').forEach(link => {
                link.addEventListener('click', function(e) {
                    e.preventDefault();
                    const card = this.closest('[data-type]');
                    const id = parseInt(card.dataset.id);
                    const type = card.dataset.type;
                    
                    let item;
                    switch(type) {
                        case 'project': item = portfolioData.projects.find(p => p.id === id); break;
                        case 'article': item = portfolioData.articles.find(a => a.id === id); break;
                        case 'experience': item = portfolioData.experiences.find(e => e.id === id); break;
                        case 'organization': item = portfolioData.organizations.find(o => o.id === id); break;
                        case 'certificate': item = portfolioData.certificates.find(c => c.id === id); break;
                        case 'award': item = portfolioData.awards.find(a => a.id === id); break;
                    }
                    
                    if (item) openModal(item, type);
                });
            });
            
            // Collaboration items
            document.querySelectorAll('.collaboration-item').forEach(item => {
                item.addEventListener('click', function() {
                    const id = parseInt(this.dataset.id);
                    const collabItem = portfolioData.collaborations.find(c => c.id === id);
                    if (collabItem) openModal(collabItem, 'collaboration');
                });
            });
            
            // Photo items
            document.querySelectorAll('.photo-item').forEach(item => {
                item.addEventListener('click', function() {
                    const id = parseInt(this.dataset.id);
                    const photoItem = portfolioData.photos.find(p => p.id === id);
                    if (photoItem) openModal(photoItem, 'photo');
                });
            });
        }

        // Initialize slider functionality
        function initSliders() {
            const sections = ['projects', 'articles', 'experience', 'organizations', 'certificates', 'awards'];
            
            sections.forEach(section => {
                const content = document.getElementById(`${section}Content`);
                const prevBtn = document.getElementById(`${section}Prev`);
                const nextBtn = document.getElementById(`${section}Next`);
                
                if (content && prevBtn && nextBtn) {
                    const scrollAmount = 320;
                    
                    prevBtn.addEventListener('click', () => {
                        content.scrollBy({ left: -scrollAmount, behavior: 'smooth' });
                    });
                    
                    nextBtn.addEventListener('click', () => {
                        content.scrollBy({ left: scrollAmount, behavior: 'smooth' });
                    });
                    
                    // Update button states
                    const updateButtons = () => {
                        const maxScroll = content.scrollWidth - content.clientWidth;
                        prevBtn.disabled = content.scrollLeft <= 0;
                        nextBtn.disabled = content.scrollLeft >= maxScroll;
                        
                        prevBtn.classList.toggle('disabled', content.scrollLeft <= 0);
                        nextBtn.classList.toggle('disabled', content.scrollLeft >= maxScroll);
                    };
                    
                    content.addEventListener('scroll', updateButtons);
                    updateButtons();
                }
            });
        }

        // Modal functions
        function openModal(item, type) {
            const modalOverlay = document.getElementById('modalOverlay');
            const modalTitle = document.getElementById('modalTitle');
            const modalContent = document.getElementById('modalContent');
            const modalLink = document.getElementById('modalLink');
            
            modalTitle.textContent = item.title;
            
            let content = '';
            let linkText = '';
            let linkUrl = '#';
            
            switch(type) {
                case 'project':
                    content = `
                        <img src="${item.image}" alt="${item.title}" class="modal-image">
                        <p><strong>Description:</strong> ${item.detailedDescription}</p>
                        <p><strong>Status:</strong> ${item.status === 'completed' ? 'Completed' : 'Ongoing'}</p>
                        <p><strong>Technologies:</strong> ${item.technologies.join(', ')}</p>
                        <div class="card-tags" style="margin-top: 20px;">
                            ${item.tags.map(tag => `<span class="tag">${tag}</span>`).join('')}
                        </div>
                    `;
                    linkText = 'View on GitHub';
                    linkUrl = item.link;
                    break;
                    
                case 'article':
                    content = `
                        <img src="${item.image}" alt="${item.title}" class="modal-image">
                        <p><strong>Journal:</strong> ${item.journal}</p>
                        <p><strong>Publication Date:</strong> ${item.date}</p>
                        <p><strong>Abstract:</strong> ${item.abstract}</p>
                        <p><strong>Keywords:</strong> ${item.keywords.join(', ')}</p>
                        <p><strong>Detailed Description:</strong> ${item.detailedDescription}</p>
                    `;
                    linkText = item.doi !== '#' ? 'View Publication' : 'Coming Soon';
                    linkUrl = item.doi;
                    break;
                    
                case 'experience':
                    content = `
                        <img src="${item.image}" alt="${item.title}" class="modal-image">
                        <p><strong>Company:</strong> ${item.company}</p>
                        <p><strong>Period:</strong> ${item.period}</p>
                        <p><strong>Description:</strong> ${item.description}</p>
                        
                        <div class="modal-slider">
                            <h4>Key Achievements:</h4>
                            <div class="modal-slider-content" id="experienceAchievements">
                                ${item.achievements.map(achievement => `
                                    <div class="modal-slider-card">
                                        <h4>${achievement.split(':')[0] || 'Achievement'}</h4>
                                        <p>${achievement.split(':')[1] || achievement}</p>
                                    </div>
                                `).join('')}
                            </div>
                            ${item.achievements.length > 1 ? `
                                <div class="modal-slider-nav">
                                    <button class="modal-slider-btn" id="expPrev"><i class="fas fa-chevron-left"></i></button>
                                    <button class="modal-slider-btn" id="expNext"><i class="fas fa-chevron-right"></i></button>
                                </div>
                            ` : ''}
                        </div>
                        
                        ${item.images && item.images.length > 0 ? `
                            <div class="modal-slider" style="margin-top: 30px;">
                                <h4>Gallery:</h4>
                                <div class="modal-slider-content" id="experienceGallery">
                                    ${item.images.map(img => `
                                        <div class="modal-slider-card">
                                            <img src="${img}" alt="Gallery" style="width: 100%; height: 150px; object-fit: cover; border-radius: 8px; margin-bottom: 10px;">
                                            <p>Work environment and achievements</p>
                                        </div>
                                    `).join('')}
                                </div>
                                ${item.images.length > 1 ? `
                                    <div class="modal-slider-nav">
                                        <button class="modal-slider-btn" id="expGalleryPrev"><i class="fas fa-chevron-left"></i></button>
                                        <button class="modal-slider-btn" id="expGalleryNext"><i class="fas fa-chevron-right"></i></button>
                                    </div>
                                ` : ''}
                            </div>
                        ` : ''}
                    `;
                    linkText = 'Learn More';
                    linkUrl = '#';
                    break;
                    
                case 'organization':
                    content = `
                        <img src="${item.image}" alt="${item.title}" class="modal-image">
                        <p><strong>Role:</strong> ${item.role}</p>
                        <p><strong>Period:</strong> ${item.period}</p>
                        <p><strong>Description:</strong> ${item.description}</p>
                        
                        <div class="modal-slider">
                            <h4>Activities & Contributions:</h4>
                            <div class="modal-slider-content" id="orgActivities">
                                ${item.activities.map(activity => `
                                    <div class="modal-slider-card">
                                        <h4>${activity.split(':')[0] || 'Activity'}</h4>
                                        <p>${activity.split(':')[1] || activity}</p>
                                    </div>
                                `).join('')}
                            </div>
                            ${item.activities.length > 1 ? `
                                <div class="modal-slider-nav">
                                    <button class="modal-slider-btn" id="orgPrev"><i class="fas fa-chevron-left"></i></button>
                                    <button class="modal-slider-btn" id="orgNext"><i class="fas fa-chevron-right"></i></button>
                                </div>
                            ` : ''}
                        </div>
                        
                        ${item.images && item.images.length > 0 ? `
                            <div class="modal-slider" style="margin-top: 30px;">
                                <h4>Gallery:</h4>
                                <div class="modal-slider-content" id="orgGallery">
                                    ${item.images.map(img => `
                                        <div class="modal-slider-card">
                                            <img src="${img}" alt="Gallery" style="width: 100%; height: 150px; object-fit: cover; border-radius: 8px; margin-bottom: 10px;">
                                            <p>Organization events and activities</p>
                                        </div>
                                    `).join('')}
                                </div>
                                ${item.images.length > 1 ? `
                                    <div class="modal-slider-nav">
                                        <button class="modal-slider-btn" id="orgGalleryPrev"><i class="fas fa-chevron-left"></i></button>
                                        <button class="modal-slider-btn" id="orgGalleryNext"><i class="fas fa-chevron-right"></i></button>
                                    </div>
                                ` : ''}
                            </div>
                        ` : ''}
                    `;
                    linkText = 'Learn More';
                    linkUrl = '#';
                    break;
                    
                case 'certificate':
                    content = `
                        ${item.image ? `<img src="${item.image}" alt="${item.title}" class="modal-image">` : ''}
                        <p><strong>Description:</strong> ${item.description}</p>
                        <p><strong>Issuer:</strong> ${item.issuer}</p>
                        <p><strong>Date:</strong> ${item.date}</p>
                    `;
                    linkText = 'View Certificate';
                    linkUrl = item.link;
                    break;
                    
                case 'award':
                    content = `
                        ${item.image ? `<img src="${item.image}" alt="${item.title}" class="modal-image">` : ''}
                        <p><strong>Organization:</strong> ${item.organization}</p>
                        <p><strong>Date:</strong> ${item.date}</p>
                        <p><strong>Description:</strong> ${item.description}</p>
                        ${item.details ? `<p><strong>Details:</strong> ${item.details}</p>` : ''}
                    `;
                    linkText = 'Learn More';
                    linkUrl = '#';
                    break;
                    
                case 'collaboration':
                    content = `
                        <div style="text-align: center; margin: 20px 0;">
                            <i class="${item.icon}" style="font-size: 5rem; color: var(--accent-color);"></i>
                        </div>
                        <p style="text-align: center; font-size: 1.2rem;"><strong>${item.name}</strong></p>
                        <p style="text-align: center;">Collaboration with ${item.name} on various data science and AI projects.</p>
                        <p style="text-align: center;">Working together to advance data-driven solutions and innovations.</p>
                    `;
                    linkText = 'Visit Website';
                    linkUrl = item.link;
                    break;
                    
                case 'photo':
                    content = `
                        <img src="${item.url}" alt="${item.alt}" class="modal-image" style="height: 300px;">
                        <h4>${item.title}</h4>
                        <p><strong>Date:</strong> ${item.date}</p>
                        <p><strong>Description:</strong> ${item.description}</p>
                    `;
                    linkText = 'View Original';
                    linkUrl = item.url;
                    break;
            }
            
            modalContent.innerHTML = content;
            modalLink.textContent = linkText;
            modalLink.href = linkUrl;
            
            modalOverlay.classList.add('active');
            document.body.style.overflow = 'hidden';
            
            // Initialize modal sliders
            setTimeout(() => {
                initModalSliders();
            }, 100);
        }

        function initModalSliders() {
            // Experience achievements slider
            const expContent = document.getElementById('experienceAchievements');
            const expPrev = document.getElementById('expPrev');
            const expNext = document.getElementById('expNext');
            
            if (expContent && expPrev && expNext) {
                expPrev.addEventListener('click', () => {
                    expContent.scrollBy({ left: -300, behavior: 'smooth' });
                });
                expNext.addEventListener('click', () => {
                    expContent.scrollBy({ left: 300, behavior: 'smooth' });
                });
            }
            
            // Experience gallery slider
            const expGalleryContent = document.getElementById('experienceGallery');
            const expGalleryPrev = document.getElementById('expGalleryPrev');
            const expGalleryNext = document.getElementById('expGalleryNext');
            
            if (expGalleryContent && expGalleryPrev && expGalleryNext) {
                expGalleryPrev.addEventListener('click', () => {
                    expGalleryContent.scrollBy({ left: -300, behavior: 'smooth' });
                });
                expGalleryNext.addEventListener('click', () => {
                    expGalleryContent.scrollBy({ left: 300, behavior: 'smooth' });
                });
            }
            
            // Organization activities slider
            const orgContent = document.getElementById('orgActivities');
            const orgPrev = document.getElementById('orgPrev');
            const orgNext = document.getElementById('orgNext');
            
            if (orgContent && orgPrev && orgNext) {
                orgPrev.addEventListener('click', () => {
                    orgContent.scrollBy({ left: -300, behavior: 'smooth' });
                });
                orgNext.addEventListener('click', () => {
                    orgContent.scrollBy({ left: 300, behavior: 'smooth' });
                });
            }
            
            // Organization gallery slider
            const orgGalleryContent = document.getElementById('orgGallery');
            const orgGalleryPrev = document.getElementById('orgGalleryPrev');
            const orgGalleryNext = document.getElementById('orgGalleryNext');
            
            if (orgGalleryContent && orgGalleryPrev && orgGalleryNext) {
                orgGalleryPrev.addEventListener('click', () => {
                    orgGalleryContent.scrollBy({ left: -300, behavior: 'smooth' });
                });
                orgGalleryNext.addEventListener('click', () => {
                    orgGalleryContent.scrollBy({ left: 300, behavior: 'smooth' });
                });
            }
        }

        function closeModal() {
            const modalOverlay = document.getElementById('modalOverlay');
            modalOverlay.classList.remove('active');
            document.body.style.overflow = 'auto';
        }

        // Testimonial navigation
        let currentTestimonial = 0;
        
        function updateTestimonial() {
            const testimonialCard = document.getElementById('testimonialCard');
            testimonialCard.innerHTML = createTestimonialCard(portfolioData.testimonials[currentTestimonial]);
            testimonialCard.classList.add('visible');
            
            // Update dots
            document.querySelectorAll('.testimonial-dot').forEach((dot, index) => {
                dot.classList.toggle('active', index === currentTestimonial);
            });
        }

        // Ask me functionality
        function setupAskMe() {
            const askButton = document.getElementById('askButton');
            const questionInput = document.getElementById('question');
            
            askButton.addEventListener('click', function() {
                const question = questionInput.value.trim();
                if (question) {
                    // Simple response
                    const email = document.getElementById('email').value;
                    if (email) {
                        alert(`Thank you for your question! We'll respond to ${email} within 24 hours.`);
                    } else {
                        alert('Thank you for your question! Connect via WhatsApp for immediate assistance.');
                    }
                    questionInput.value = '';
                    document.getElementById('email').value = '';
                } else {
                    alert('Please enter your question first.');
                }
            });
        }

        // Visitor counter
        function updateVisitorCounter() {
            // Load from localStorage
            const stats = JSON.parse(localStorage.getItem('visitorStats') || '{}');
            const now = new Date();
            const today = now.toDateString();
            
            // Initialize if empty
            if (!stats.total) {
                stats.total = 0;
                stats.daily = {};
                stats.lastVisit = null;
            }
            
            // Check if first visit today
            if (stats.lastVisit !== today) {
                stats.total++;
                stats.daily[today] = (stats.daily[today] || 0) + 1;
                stats.lastVisit = today;
                
                // Save to localStorage
                localStorage.setItem('visitorStats', JSON.stringify(stats));
            }
            
            // Calculate weekly and monthly stats
            const oneWeekAgo = new Date(now.getTime() - 7 * 24 * 60 * 60 * 1000);
            const oneMonthAgo = new Date(now.getTime() - 30 * 24 * 60 * 60 * 1000);
            
            let weekly = 0;
            let monthly = 0;
            
            Object.entries(stats.daily).forEach(([date, count]) => {
                const visitDate = new Date(date);
                if (visitDate >= oneWeekAgo) weekly += count;
                if (visitDate >= oneMonthAgo) monthly += count;
            });
            
            // Update display
            document.getElementById('visitorCount').textContent = stats.total.toLocaleString();
            
            // Store in global variable
            visitorStats = {
                total: stats.total,
                today: stats.daily[today] || 0,
                thisWeek: weekly,
                thisMonth: monthly,
                lastMonth: Math.max(0, stats.total - monthly)
            };
            
            // Update counter every hour
            setTimeout(updateVisitorCounter, 60 * 60 * 1000);
        }

        // Custom cursor
        function initCustomCursor() {
            const cursorDot = document.getElementById('cursorDot');
            const cursorOutline = document.getElementById('cursorOutline');
            
            document.addEventListener('mousemove', (e) => {
                cursorDot.style.left = `${e.pageX}px`;
                cursorDot.style.top = `${e.pageY}px`;
                
                cursorOutline.style.left = `${e.pageX}px`;
                cursorOutline.style.top = `${e.pageY}px`;
            });
            
            // Hover effects
            const hoverElements = document.querySelectorAll('a, button, .project-card, .article-card, .certificate-card, .experience-card, .award-card, .organization-card, .collaboration-item, .photo-item');
            
            hoverElements.forEach(el => {
                el.addEventListener('mouseenter', () => {
                    cursorDot.style.transform = 'scale(1.5)';
                    cursorOutline.style.transform = 'scale(1.5)';
                });
                
                el.addEventListener('mouseleave', () => {
                    cursorDot.style.transform = 'scale(1)';
                    cursorOutline.style.transform = 'scale(1)';
                });
            });
            
            // Click effect
            document.addEventListener('click', () => {
                cursorDot.style.transform = 'scale(0.5)';
                setTimeout(() => {
                    cursorDot.style.transform = 'scale(1)';
                }, 100);
            });
        }

        // Initialize scroll animations
        function initScrollAnimations() {
            const observerOptions = {
                threshold: 0.1,
                rootMargin: '0px 0px -30px 0px'
            };
            
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('visible');
                        
                        // Animate skill bars
                        if (entry.target.classList.contains('skill-category')) {
                            setTimeout(() => {
                                const progressBars = entry.target.querySelectorAll('.skill-progress');
                                progressBars.forEach(bar => {
                                    const width = bar.dataset.width;
                                    bar.style.width = `${width}%`;
                                });
                            }, 300);
                        }
                    }
                });
            }, observerOptions);
            
            // Observe sections
            document.querySelectorAll('section').forEach(el => {
                observer.observe(el);
            });
            
            // Observe cards
            document.querySelectorAll('.project-card, .article-card, .certificate-card, .experience-card, .award-card, .organization-card, .collaboration-item, .photo-item, .skill-category, .testimonial-card').forEach(el => {
                observer.observe(el);
            });
        }

        // Smooth scrolling with offset
        function initSmoothScrolling() {
            document.querySelectorAll('a[href^="#"]').forEach(anchor => {
                anchor.addEventListener('click', function(e) {
                    e.preventDefault();
                    
                    const targetId = this.getAttribute('href');
                    if (targetId === '#') return;
                    
                    const targetElement = document.querySelector(targetId);
                    if (targetElement) {
                        // Page transition
                        const pageTransition = document.getElementById('pageTransition');
                        pageTransition.classList.add('active');
                        
                        setTimeout(() => {
                            const headerHeight = document.getElementById('header').offsetHeight;
                            const targetPosition = targetElement.getBoundingClientRect().top + window.pageYOffset - headerHeight;
                            
                            window.scrollTo({
                                top: targetPosition,
                                behavior: 'smooth'
                            });
                            
                            // Remove transition after scroll
                            setTimeout(() => {
                                pageTransition.classList.remove('active');
                            }, 600);
                        }, 300);
                    }
                });
            });
        }

        // Header hide/show on scroll
        function initHeaderScroll() {
            let lastScrollTop = 0;
            const header = document.getElementById('header');
            
            window.addEventListener('scroll', () => {
                const scrollTop = window.pageYOffset || document.documentElement.scrollTop;
                
                if (scrollTop > lastScrollTop && scrollTop > 100) {
                    // Scroll down
                    header.classList.add('hidden');
                } else {
                    // Scroll up
                    header.classList.remove('hidden');
                }
                
                lastScrollTop = scrollTop;
            });
        }

        // Page transition
        function animatePageTransition() {
            const pageTransition = document.getElementById('pageTransition');
            pageTransition.classList.add('active');
            
            setTimeout(() => {
                pageTransition.classList.remove('active');
            }, 600);
        }

        // Translate page
        function translatePage(lang) {
            currentLang = lang;
            
            document.querySelectorAll('[data-i18n]').forEach(element => {
                const key = element.getAttribute('data-i18n');
                if (translations[lang] && translations[lang][key]) {
                    element.textContent = translations[lang][key];
                }
            });
            
            document.querySelectorAll('[data-i18n-placeholder]').forEach(element => {
                const key = element.getAttribute('data-i18n-placeholder');
                if (translations[lang] && translations[lang][key]) {
                    element.placeholder = translations[lang][key];
                }
            });
            
            document.querySelectorAll('.language-switcher button').forEach(btn => {
                if (btn.id === `lang${lang.toUpperCase()}`) {
                    btn.classList.add('active');
                } else {
                    btn.classList.remove('active');
                }
            });
        }

        // Initialize everything
        document.addEventListener('DOMContentLoaded', function() {
            // Render portfolio
            renderPortfolio();
            
            // Setup visitor counter
            updateVisitorCounter();
            
            // Setup ask me
            setupAskMe();
            
            // Initialize sliders
            initSliders();
            
            // Initialize animations
            initScrollAnimations();
            
            // Initialize smooth scrolling
            initSmoothScrolling();
            
            // Initialize header scroll
            initHeaderScroll();
            
            // Initialize custom cursor
            initCustomCursor();
            
            // Mobile menu
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
            
            // Language switcher
            document.getElementById('langEN').addEventListener('click', () => {
                if (currentLang !== 'en') {
                    animatePageTransition();
                    setTimeout(() => {
                        translatePage('en');
                    }, 300);
                }
            });
            
            document.getElementById('langID').addEventListener('click', () => {
                if (currentLang !== 'id') {
                    animatePageTransition();
                    setTimeout(() => {
                        translatePage('id');
                    }, 300);
                }
            });
            
            // Testimonial navigation
            document.getElementById('prevTestimonial').addEventListener('click', () => {
                currentTestimonial = (currentTestimonial - 1 + portfolioData.testimonials.length) % portfolioData.testimonials.length;
                updateTestimonial();
            });
            
            document.getElementById('nextTestimonial').addEventListener('click', () => {
                currentTestimonial = (currentTestimonial + 1) % portfolioData.testimonials.length;
                updateTestimonial();
            });
            
            // Testimonial dots
            document.querySelectorAll('.testimonial-dot').forEach(dot => {
                dot.addEventListener('click', function() {
                    currentTestimonial = parseInt(this.dataset.index);
                    updateTestimonial();
                });
            });
            
            // Modal close
            document.getElementById('modalClose').addEventListener('click', closeModal);
            document.getElementById('modalCloseBtn').addEventListener('click', closeModal);
            document.getElementById('modalOverlay').addEventListener('click', function(e) {
                if (e.target === this) {
                    closeModal();
                }
            });
            
            // Set current year
            document.getElementById('currentYear').textContent = new Date().getFullYear();
            
            // Add pulse animation to important elements
            const importantElements = document.querySelectorAll('.btn, .header-cv, .logo');
            importantElements.forEach(el => {
                el.classList.add('pulse');
            });
            
            // Update float animation
            const heroImage = document.querySelector('.hero-image');
            heroImage.classList.add('float-animation');
        });
    </script>
</body>
</html>
