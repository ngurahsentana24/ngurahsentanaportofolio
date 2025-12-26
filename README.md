<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ngurah Sentana | Data Scientist & Computer Science Portfolio</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&family=Space+Grotesk:wght@300;400;500;600;700&family=JetBrains+Mono:wght@300;400;500&display=swap" rel="stylesheet">
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
            transition: background-color 0.3s ease;
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

        /* Cards */
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

        .project-image-container {
            height: 180px;
            overflow: hidden;
            position: relative;
        }

        .project-image, .article-image {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
        }

        .project-card:hover .project-image,
        .article-card:hover .article-image {
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
        .certificate-icon, .experience-icon {
            padding: 25px 25px 15px;
            text-align: center;
            background: linear-gradient(135deg, #f0f9ff 0%, #e0f2fe 100%);
        }

        .certificate-icon i, .experience-icon i {
            font-size: 2.5rem;
            color: var(--accent-color);
        }

        /* Organizations */
        .organization-icon {
            padding: 25px 25px 15px;
            text-align: center;
            background: linear-gradient(135deg, #f0f9ff 0%, #e0f2fe 100%);
        }

        .organization-icon i {
            font-size: 2.5rem;
            color: var(--accent-color);
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
                    <li><a href="#competency" data-i18n="nav.competency">Competency</a></li>
                    <li><a href="#testimonials" data-i18n="nav.testimonials">Testimonials</a></li>
                </ul>
                <div class="header-right">
                    <div class="language-switcher">
                        <button class="active" id="langEN">EN</button>
                        <button id="langID">ID</button>
                    </div>
                    <a href="https://drive.google.com/file/d/1EXAMPLE/view?usp=sharing" target="_blank" class="header-cv">
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
                        <img src="https://images.unsplash.com/photo-1568602471122-7832951cc4c5?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80" alt="Foto Ngurah Sentana" class="profile-img">
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

        // Data for portfolio
        const portfolioData = {
            projects: [
                {
                    id: 1,
                    title: "Financial Market Prediction System",
                    description: "Machine learning model for stock market movement prediction with 87% accuracy using LSTM.",
                    image: "https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80",
                    tags: ["Python", "TensorFlow", "LSTM", "Finance"],
                    link: "https://github.com/NgurahSentana/stock-prediction",
                    status: "completed",
                    detailedDescription: "This project implements a sophisticated LSTM neural network for predicting stock market trends. The model processes real-time financial data with 87% accuracy. Features include real-time data processing, automated retraining, and comprehensive backtesting.",
                    technologies: ["Python 3.9", "TensorFlow 2.8", "Keras", "Pandas", "NumPy", "Scikit-learn"],
                    date: "2023"
                },
                {
                    id: 2,
                    title: "Social Media Sentiment Analysis",
                    description: "NLP pipeline for real-time sentiment analysis from social media platforms.",
                    image: "https://images.unsplash.com/photo-1611605698335-8b1569810432?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80",
                    tags: ["NLP", "Python", "Transformers", "FastAPI"],
                    link: "https://github.com/NgurahSentana/sentiment-analysis",
                    status: "ongoing",
                    detailedDescription: "Real-time sentiment analysis system that processes social media data streams using BERT-based transformer models. Supports multiple languages and provides real-time dashboards for sentiment tracking.",
                    technologies: ["PyTorch", "Transformers", "FastAPI", "Docker", "Redis", "MongoDB"],
                    date: "2023"
                },
                {
                    id: 3,
                    title: "3D Interactive Data Visualization",
                    description: "3D data visualization dashboard for complex datasets using WebGL.",
                    image: "https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80",
                    tags: ["JavaScript", "Three.js", "D3.js", "WebGL"],
                    link: "https://github.com/NgurahSentana/3d-data-viz",
                    status: "completed",
                    detailedDescription: "Interactive 3D visualization platform for exploring complex multi-dimensional datasets. Users can rotate, zoom, filter, and interact with data points in real-time.",
                    technologies: ["React", "Three.js", "D3.js", "WebGL", "Node.js", "Express"],
                    date: "2023"
                },
                {
                    id: 4,
                    title: "Healthcare Analytics Platform",
                    description: "Analytics platform for healthcare data with predictive models.",
                    image: "https://images.unsplash.com/photo-1559757148-5c350d0d3c56?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80",
                    tags: ["Healthcare", "Machine Learning", "Python", "Flask"],
                    link: "https://github.com/NgurahSentana/healthcare-analytics",
                    status: "completed",
                    detailedDescription: "Comprehensive healthcare analytics platform that processes patient data to predict outcomes and suggest interventions. Implements privacy-preserving techniques for sensitive medical data.",
                    technologies: ["Python", "Flask", "SQL", "XGBoost", "Scikit-learn", "HIPAA Compliance"],
                    date: "2022"
                }
            ],
            articles: [
                {
                    id: 1,
                    title: "Bayesian Statistics in A/B Testing",
                    description: "Research on applying Bayesian methods for more efficient A/B testing.",
                    image: "https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80",
                    journal: "Journal of Data Science",
                    date: "March 2023",
                    doi: "https://doi.org/10.1234/jds.2023.001",
                    abstract: "This paper presents a novel Bayesian approach to A/B testing that reduces required sample sizes by 40% while maintaining statistical power.",
                    keywords: ["Bayesian Statistics", "A/B Testing", "Experimental Design"],
                    detailedDescription: "In-depth research on Bayesian statistical methods applied to A/B testing scenarios, showing significant improvements over traditional frequentist approaches."
                },
                {
                    id: 2,
                    title: "Algorithm Optimization for Big Data",
                    description: "Techniques for optimizing algorithms for large-scale data processing.",
                    image: "https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80",
                    journal: "International Journal of Computer Science",
                    date: "January 2023",
                    doi: "https://doi.org/10.5678/ijcs.2023.002",
                    abstract: "This research explores optimization techniques for processing massive datasets efficiently.",
                    keywords: ["Big Data", "Algorithm Optimization", "Distributed Computing"],
                    detailedDescription: "Comprehensive study of algorithm optimization techniques for big data processing, including parallel processing and distributed computing approaches."
                }
            ],
            experiences: [
                {
                    id: 1,
                    title: "Lead Data Scientist",
                    company: "TechCorp",
                    period: "2022 - Present",
                    description: "Leading data science team for predictive model development and AI solutions.",
                    achievements: [
                        "Led development of machine learning pipeline reducing processing time by 60%",
                        "Implemented automated model monitoring system improving accuracy by 25%",
                        "Mentored team of 5 junior data scientists",
                        "Reduced infrastructure costs by 40% through optimization"
                    ],
                    images: [
                        "https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80",
                        "https://images.unsplash.com/photo-1559757148-5c350d0d3c56?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80"
                    ]
                },
                {
                    id: 2,
                    title: "Research Assistant",
                    company: "University AI Lab",
                    period: "2020 - 2022",
                    description: "Research assistant focusing on computer vision and deep learning.",
                    achievements: [
                        "Published 3 papers in top-tier journals",
                        "Developed novel object detection algorithm with 95% accuracy",
                        "Collaborated with international research teams",
                        "Presented findings at 5 international conferences"
                    ],
                    images: [
                        "https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80"
                    ]
                }
            ],
            organizations: [
                {
                    id: 1,
                    title: "Data Science Association",
                    role: "Active Member",
                    period: "2021 - Present",
                    description: "Professional organization for data scientists and analysts.",
                    activities: [
                        "Organized monthly workshops for 100+ members",
                        "Led community project improving local business analytics",
                        "Presented at annual conference 2022",
                        "Mentored 15 junior data scientists"
                    ],
                    images: [
                        "https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80"
                    ]
                },
                {
                    id: 2,
                    title: "AI Research Community",
                    role: "Research Contributor",
                    period: "2020 - Present",
                    description: "Community of AI researchers and practitioners.",
                    activities: [
                        "Contributed to open-source AI projects",
                        "Reviewed 50+ research papers",
                        "Organized study groups on advanced ML topics",
                        "Collaborated on international research projects"
                    ],
                    images: [
                        "https://images.unsplash.com/photo-1559757148-5c350d0d3c56?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80"
                    ]
                }
            ],
            certificates: [
                {
                    id: 1,
                    title: "Google Data Analytics",
                    description: "Professional data analytics certification from Google.",
                    issuer: "Google via Coursera",
                    date: "December 2022",
                    link: "https://coursera.org/certificates/data-analytics",
                    image: "https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80"
                },
                {
                    id: 2,
                    title: "AWS Machine Learning",
                    description: "AWS specialist certification in machine learning.",
                    issuer: "Amazon Web Services",
                    date: "October 2022",
                    link: "https://aws.amazon.com/certification/",
                    image: "https://images.unsplash.com/photo-1559757148-5c350d0d3c56?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80"
                }
            ],
            awards: [
                {
                    id: 1,
                    title: "Best Data Science Project",
                    organization: "Data Science Association",
                    date: "2023",
                    description: "Awarded for innovative use of machine learning in financial market prediction.",
                    image: "https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80",
                    details: "Recognized for developing a novel LSTM-based stock prediction model that achieved 87% accuracy in live trading simulations."
                },
                {
                    id: 2,
                    title: "Speaker at AI Conference",
                    organization: "AI Summit 2023",
                    date: "2023",
                    description: "Invited speaker on 'Ethical AI Implementation in Healthcare'.",
                    image: "https://images.unsplash.com/photo-1559757148-5c350d0d3c56?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80",
                    details: "Delivered keynote speech on ethical considerations in healthcare AI to an audience of 500+ professionals."
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
                    { name: "Statistical Analysis", percentage: 90 },
                    { name: "Regression Models", percentage: 85 },
                    { name: "Bayesian Statistics", percentage: 80 },
                    { name: "Time Series Analysis", percentage: 75 },
                    { name: "Experimental Design", percentage: 85 }
                ],
                dataScience: [
                    { name: "Machine Learning", percentage: 95 },
                    { name: "Deep Learning", percentage: 85 },
                    { name: "Natural Language Processing", percentage: 80 },
                    { name: "Computer Vision", percentage: 75 },
                    { name: "Data Visualization", percentage: 90 }
                ],
                computerScience: [
                    { name: "Python Programming", percentage: 95 },
                    { name: "Software Architecture", percentage: 85 },
                    { name: "Algorithm Design", percentage: 90 },
                    { name: "Database Systems", percentage: 80 },
                    { name: "Cloud Computing", percentage: 75 }
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
                clients: { value: portfolioData.testimonials.length, trend: 30 }
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

        // Create experience card
        function createExperienceCard(experience) {
            return `
                <div class="experience-card" data-id="${experience.id}" data-type="experience">
                    <div class="experience-icon">
                        <i class="fas fa-briefcase"></i>
                    </div>
                    <div class="card-content">
                        <h3>${experience.title}</h3>
                        <p><strong>${experience.company}</strong></p>
                        <p>${experience.description}</p>
                        <div class="card-footer">
                            <span class="card-date">${experience.period}</span>
                            <a href="#" class="view-more">View Details <i class="fas fa-arrow-right"></i></a>
                        </div>
                    </div>
                </div>
            `;
        }

        // Create organization card
        function createOrganizationCard(organization) {
            return `
                <div class="organization-card" data-id="${organization.id}" data-type="organization">
                    <div class="organization-icon">
                        <i class="fas fa-users"></i>
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

        // Create certificate card
        function createCertificateCard(certificate) {
            return `
                <div class="certificate-card" data-id="${certificate.id}" data-type="certificate">
                    <div class="certificate-icon">
                        <i class="fas fa-award"></i>
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

        // Create award card
        function createAwardCard(award) {
            return `
                <div class="award-card" data-id="${award.id}" data-type="award">
                    <div class="experience-icon">
                        <i class="fas fa-trophy"></i>
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
            const hoverElements = document.querySelectorAll('a, button, .project-card, .article-card, .certificate-card, .experience-card, .award-card, .organization-card');
            
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
            document.querySelectorAll('.project-card, .article-card, .certificate-card, .experience-card, .award-card, .organization-card, .skill-category, .testimonial-card').forEach(el => {
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
            
            // Card click events
            document.addEventListener('click', function(e) {
                // View more links
                if (e.target.closest('.view-more')) {
                    e.preventDefault();
                    const card = e.target.closest('[data-type]');
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
                }
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
