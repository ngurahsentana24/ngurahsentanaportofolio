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

        .header-actions {
            display: flex;
            align-items: center;
            gap: 15px;
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

        .btn-small {
            padding: 10px 20px;
            font-size: 0.9rem;
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

        /* Section Styling */
        section {
            padding: 100px 0;
            position: relative;
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

        /* Projects Section */
        .projects-section {
            background-color: white;
        }

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 30px;
        }

        .project-card {
            background: white;
            border-radius: var(--border-radius);
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
            border: 1px solid var(--medium-gray);
            cursor: pointer;
            position: relative;
            opacity: 0;
            transform: translateY(30px);
        }

        .project-card.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .project-card:hover {
            transform: translateY(-15px);
            box-shadow: var(--shadow-lg);
            border-color: var(--accent-color);
        }

        .project-image-container {
            height: 200px;
            overflow: hidden;
            position: relative;
        }

        .project-image {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
        }

        .project-card:hover .project-image {
            transform: scale(1.1);
        }

        .project-status {
            position: absolute;
            top: 15px;
            right: 15px;
            padding: 5px 15px;
            background: var(--success-color);
            color: white;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 600;
            z-index: 2;
        }

        .project-status.ongoing {
            background: var(--warning-color);
        }

        .project-content {
            padding: 25px;
        }

        .project-content h3 {
            margin-bottom: 10px;
            font-size: 1.4rem;
        }

        .project-tags {
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

        /* Articles Section */
        .articles-section {
            background-color: var(--light-gray);
        }

        .articles-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 30px;
        }

        .article-card {
            background: white;
            border-radius: var(--border-radius);
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
            border: 1px solid var(--medium-gray);
            cursor: pointer;
            position: relative;
            opacity: 0;
            transform: translateY(30px);
        }

        .article-card.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .article-card:hover {
            transform: translateY(-15px);
            box-shadow: var(--shadow-lg);
            border-color: var(--accent-color);
        }

        .article-header {
            padding: 25px 25px 15px;
            background: linear-gradient(135deg, #f0f9ff 0%, #e0f2fe 100%);
        }

        .article-journal {
            font-size: 0.9rem;
            color: var(--accent-color);
            font-weight: 600;
            margin-bottom: 5px;
        }

        .article-date {
            font-size: 0.85rem;
            color: var(--dark-gray);
        }

        .article-content {
            padding: 0 25px 25px;
        }

        .doi-link {
            display: inline-block;
            margin-top: 15px;
            font-size: 0.85rem;
            color: var(--accent-color);
            text-decoration: none;
            font-family: 'JetBrains Mono', monospace;
        }

        .doi-link:hover {
            text-decoration: underline;
        }

        /* Certificates Section */
        .certificates-section {
            background-color: white;
        }

        .certificates-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 30px;
        }

        .certificate-card {
            background: white;
            border-radius: var(--border-radius);
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
            border: 1px solid var(--medium-gray);
            cursor: pointer;
            position: relative;
            opacity: 0;
            transform: translateY(30px);
        }

        .certificate-card.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .certificate-card:hover {
            transform: translateY(-15px);
            box-shadow: var(--shadow-lg);
            border-color: var(--accent-color);
        }

        .certificate-icon {
            padding: 30px 30px 20px;
            text-align: center;
            background: linear-gradient(135deg, #f0f9ff 0%, #e0f2fe 100%);
        }

        .certificate-icon i {
            font-size: 3rem;
            color: var(--accent-color);
        }

        .certificate-content {
            padding: 0 25px 25px;
        }

        /* Experience Section */
        .experience-section {
            background-color: var(--light-gray);
        }

        .experience-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 30px;
        }

        .experience-card {
            background: white;
            border-radius: var(--border-radius);
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
            border: 1px solid var(--medium-gray);
            cursor: pointer;
            position: relative;
            opacity: 0;
            transform: translateY(30px);
        }

        .experience-card.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .experience-card:hover {
            transform: translateY(-15px);
            box-shadow: var(--shadow-lg);
            border-color: var(--accent-color);
        }

        .experience-period {
            padding: 20px 25px 15px;
            background: linear-gradient(135deg, #f0f9ff 0%, #e0f2fe 100%);
            font-family: 'JetBrains Mono', monospace;
            font-weight: 600;
            color: var(--accent-color);
        }

        .experience-content {
            padding: 0 25px 25px;
        }

        /* Competency Section */
        .competency-section {
            background-color: white;
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

        /* Collaboration Section */
        .collaboration-section {
            background-color: var(--light-gray);
        }

        .collaboration-container {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 40px;
            margin-top: 50px;
        }

        .collaboration-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center;
            width: 150px;
            transition: var(--transition);
            opacity: 0;
            transform: translateY(30px);
        }

        .collaboration-item.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .collaboration-icon {
            width: 80px;
            height: 80px;
            background: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: var(--shadow);
            transition: var(--transition);
            font-size: 2rem;
            color: var(--accent-color);
            margin-bottom: 15px;
        }

        .collaboration-item:hover .collaboration-icon {
            transform: translateY(-10px) scale(1.1);
            box-shadow: var(--shadow-lg);
            background: linear-gradient(135deg, var(--accent-color), var(--accent-light));
            color: white;
        }

        .collaboration-name {
            font-weight: 600;
            color: var(--secondary-color);
            margin-top: 10px;
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

        /* Photo Session */
        .photo-session {
            padding: 100px 0;
            background-color: var(--light-gray);
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
            opacity: 0;
            transform: translateY(30px);
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
            transform: scale(1.1);
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

        .modal-image {
            width: 100%;
            height: 300px;
            object-fit: cover;
            border-radius: var(--border-radius);
            margin-bottom: 25px;
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
            color: #cbd5e1;
            font-size: 0.9rem;
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

        @keyframes progressAnimation {
            from { width: 0; }
            to { width: var(--target-width); }
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
            
            .projects-grid,
            .articles-grid,
            .certificates-grid,
            .experience-grid {
                grid-template-columns: 1fr;
            }
            
            .footer-content {
                grid-template-columns: 1fr;
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
                    <li><a href="#home">Home</a></li>
                    <li><a href="#projects">Projects</a></li>
                    <li><a href="#articles">Publications</a></li>
                    <li><a href="#certificates">Certificates</a></li>
                    <li><a href="#experience">Experience</a></li>
                    <li><a href="#competency">Competency</a></li>
                    <li><a href="#collaboration">Collaboration</a></li>
                </ul>
                <div class="header-actions">
                    <a href="https://drive.google.com/file/d/1EXAMPLE/view?usp=sharing" target="_blank" class="btn btn-small">
                        <i class="fas fa-download"></i> Download CV
                    </a>
                </div>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="container">
            <div class="hero-content fade-in">
                <div class="hero-text">
                    <h1>Ngurah Sentana</h1>
                    <p>Data Scientist & Computer Science Specialist with expertise in Statistics, Machine Learning, and Software Development. Creating elegant and functional data-driven solutions.</p>
                    <div style="display: flex; gap: 15px; flex-wrap: wrap;">
                        <a href="#projects" class="btn">View Projects</a>
                        <a href="#contact" class="btn btn-outline">Contact Me</a>
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

    <!-- Projects Section -->
    <section class="projects-section" id="projects">
        <div class="container">
            <div class="section-title">
                <h2>Projects</h2>
                <p>Data science and software development projects showcasing practical applications</p>
            </div>
            <div class="projects-grid" id="projectsGrid">
                <!-- Cards will be filled by JavaScript -->
            </div>
        </div>
    </section>

    <!-- Articles Section -->
    <section class="articles-section" id="articles">
        <div class="container">
            <div class="section-title">
                <h2>Publications</h2>
                <p>Research papers and articles published in scientific journals</p>
            </div>
            <div class="articles-grid" id="articlesGrid">
                <!-- Cards will be filled by JavaScript -->
            </div>
        </div>
    </section>

    <!-- Certificates Section -->
    <section class="certificates-section" id="certificates">
        <div class="container">
            <div class="section-title">
                <h2>Certificates</h2>
                <p>Professional certifications and completed courses</p>
            </div>
            <div class="certificates-grid" id="certificatesGrid">
                <!-- Cards will be filled by JavaScript -->
            </div>
        </div>
    </section>

    <!-- Experience Section -->
    <section class="experience-section" id="experience">
        <div class="container">
            <div class="section-title">
                <h2>Experience</h2>
                <p>Professional journey and work experience</p>
            </div>
            <div class="experience-grid" id="experienceGrid">
                <!-- Cards will be filled by JavaScript -->
            </div>
        </div>
    </section>

    <!-- Competency Section -->
    <section class="competency-section" id="competency">
        <div class="container">
            <div class="section-title">
                <h2>Competency</h2>
                <p>Skills and expertise in Statistics, Data Science, and Computer Science</p>
            </div>
            <div class="skills-container" id="skillsContainer">
                <!-- Skill categories will be filled by JavaScript -->
            </div>
        </div>
    </section>

    <!-- Collaboration Section -->
    <section class="collaboration-section" id="collaboration">
        <div class="container">
            <div class="section-title">
                <h2>Collaboration & Connections</h2>
                <p>Platforms and tools for professional collaboration</p>
            </div>
            <div class="collaboration-container" id="collaborationContainer">
                <!-- Collaboration items will be filled by JavaScript -->
            </div>
        </div>
    </section>

    <!-- Ask Me Section -->
    <section class="ask-me-section">
        <div class="container">
            <div class="section-title">
                <h2>Ask Me</h2>
                <p>Ask questions and get informative answers</p>
            </div>
            <div class="ask-container">
                <div class="ask-form-container">
                    <div class="ask-form">
                        <div class="form-group">
                            <label for="question">Your Question</label>
                            <textarea id="question" rows="6" placeholder="Write your question here..."></textarea>
                        </div>
                        <div class="form-group">
                            <label for="email">Email (optional, for answer notifications)</label>
                            <input type="email" id="email" placeholder="name@email.com">
                        </div>
                        <button type="button" class="btn" id="askButton">Ask Question</button>
                    </div>
                </div>
                <div class="ask-response">
                    <div class="response-header">
                        <i class="fas fa-robot"></i>
                        <h3>Answer</h3>
                    </div>
                    <div class="response-content" id="responseContent">
                        <p class="response-placeholder">Answer will appear here after you submit a question.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Photo Session -->
    <section class="photo-session">
        <div class="container">
            <div class="section-title">
                <h2>Photo Session</h2>
                <p>Moments in data exploration, coding, and presentations</p>
            </div>
            <div class="photo-grid" id="photoGrid">
                <!-- Photo items will be filled by JavaScript -->
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
                <a href="#" class="btn" id="modalLink" target="_blank">Visit Link</a>
            </div>
        </div>
    </div>

    <!-- Footer -->
    <footer id="contact">
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>Ngurah Sentana</h3>
                    <p>Data Scientist & Computer Science Specialist with an interdisciplinary approach to solving complex problems.</p>
                    <div class="social-links">
                        <a href="https://github.com/NgurahSentana" target="_blank"><i class="fab fa-github"></i></a>
                        <a href="https://linkedin.com/in/ngurahsentana" target="_blank"><i class="fab fa-linkedin-in"></i></a>
                        <a href="https://twitter.com/ngurahsentana" target="_blank"><i class="fab fa-twitter"></i></a>
                        <a href="mailto:ngurah.sentana@example.com"><i class="fas fa-envelope"></i></a>
                    </div>
                </div>
                <div class="footer-column">
                    <h3>Navigation</h3>
                    <ul class="footer-links">
                        <li><a href="#home">Home</a></li>
                        <li><a href="#projects">Projects</a></li>
                        <li><a href="#articles">Publications</a></li>
                        <li><a href="#certificates">Certificates</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Portfolio</h3>
                    <ul class="footer-links">
                        <li><a href="#experience">Experience</a></li>
                        <li><a href="#competency">Competency</a></li>
                        <li><a href="#collaboration">Collaboration</a></li>
                        <li><a href="#contact">Contact</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Contact</h3>
                    <ul class="footer-links">
                        <li><a href="mailto:ngurah.sentana@example.com">ngurah.sentana@example.com</a></li>
                        <li><a href="tel:+621234567890">+62 123 4567 890</a></li>
                        <li><a href="https://github.com/NgurahSentana" target="_blank">GitHub</a></li>
                        <li><a href="https://linkedin.com/in/ngurahsentana" target="_blank">LinkedIn</a></li>
                    </ul>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; <span id="currentYear">2023</span> Ngurah Sentana. All rights reserved. Created with <i class="fas fa-heart" style="color: #ef4444;"></i> and data.</p>
            </div>
        </div>
    </footer>

    <!-- JavaScript -->
    <script>
        // Data for portfolio
        const portfolioData = {
            projects: [
                {
                    id: 1,
                    title: "Financial Market Prediction System",
                    description: "Machine learning model for stock market movement prediction with 87% accuracy using LSTM and real-time data.",
                    image: "https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80",
                    tags: ["Python", "TensorFlow", "LSTM", "Time Series", "Finance"],
                    link: "https://github.com/NgurahSentana/stock-prediction",
                    status: "completed",
                    detailedDescription: "This project implements a sophisticated LSTM neural network for predicting stock market trends. The model processes real-time financial data, including price movements, trading volumes, and technical indicators. Achieved 87% accuracy on test data with proper cross-validation techniques.",
                    technologies: ["Python 3.9", "TensorFlow 2.8", "Keras", "Pandas", "NumPy", "Scikit-learn"]
                },
                {
                    id: 2,
                    title: "Social Media Sentiment Analysis",
                    description: "NLP pipeline for real-time sentiment analysis from social media platforms using transformer models.",
                    image: "https://images.unsplash.com/photo-1611605698335-8b1569810432?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80",
                    tags: ["NLP", "Python", "Transformers", "FastAPI", "Docker"],
                    link: "https://github.com/NgurahSentana/sentiment-analysis",
                    status: "ongoing",
                    detailedDescription: "Real-time sentiment analysis system that processes social media data streams. Uses BERT-based transformer models for accurate sentiment classification. Features include multilingual support, topic modeling, and real-time dashboard visualization.",
                    technologies: ["PyTorch", "Transformers", "FastAPI", "Docker", "Redis", "MongoDB"]
                },
                {
                    id: 3,
                    title: "3D Interactive Data Visualization",
                    description: "3D data visualization dashboard for complex datasets using WebGL and Three.js.",
                    image: "https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80",
                    tags: ["JavaScript", "Three.js", "D3.js", "WebGL", "React"],
                    link: "https://github.com/NgurahSentana/3d-data-viz",
                    status: "completed",
                    detailedDescription: "Interactive 3D visualization platform for exploring complex multi-dimensional datasets. Users can rotate, zoom, and filter data in real-time. Features multiple visualization modes including scatter plots, heat maps, and network graphs.",
                    technologies: ["React", "Three.js", "D3.js", "WebGL", "Node.js"]
                },
                {
                    id: 4,
                    title: "Healthcare Analytics Platform",
                    description: "Analytics platform for healthcare data with predictive models for patient outcomes.",
                    image: "https://images.unsplash.com/photo-1559757148-5c350d0d3c56?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80",
                    tags: ["Healthcare", "Machine Learning", "Python", "Flask", "SQL"],
                    link: "https://github.com/NgurahSentana/healthcare-analytics",
                    status: "completed",
                    detailedDescription: "Comprehensive healthcare analytics platform that processes patient data to predict outcomes and suggest interventions. Implements privacy-preserving techniques for handling sensitive medical data.",
                    technologies: ["Python", "Flask", "SQL", "XGBoost", "Scikit-learn", "HIPAA Compliance"]
                },
                {
                    id: 5,
                    title: "E-commerce Recommendation Engine",
                    description: "Personalized product recommendation system for e-commerce using collaborative filtering.",
                    image: "https://images.unsplash.com/photo-1556742049-0cfed4f6a45d?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80",
                    tags: ["Recommendation", "Machine Learning", "Python", "Spark", "AWS"],
                    link: "https://github.com/NgurahSentana/recommendation-engine",
                    status: "ongoing",
                    detailedDescription: "Scalable recommendation engine that processes user behavior data to provide personalized product suggestions. Implements both collaborative filtering and content-based approaches.",
                    technologies: ["Apache Spark", "Python", "AWS S3", "Docker", "Kubernetes"]
                },
                {
                    id: 6,
                    title: "Autonomous Vehicle Simulation",
                    description: "Simulation environment for testing autonomous vehicle algorithms using reinforcement learning.",
                    image: "https://images.unsplash.com/photo-1549317661-bd32c8ce0db2?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80",
                    tags: ["AI", "Reinforcement Learning", "Python", "Unity", "ROS"],
                    link: "https://github.com/NgurahSentana/autonomous-vehicle",
                    status: "completed",
                    detailedDescription: "High-fidelity simulation environment for developing and testing autonomous vehicle algorithms. Uses reinforcement learning for decision making and path planning.",
                    technologies: ["Python", "Unity", "ROS", "TensorFlow", "OpenAI Gym"]
                }
            ],
            articles: [
                {
                    id: 1,
                    title: "Bayesian Statistics Implementation in A/B Testing",
                    description: "Research on applying Bayesian methods for more efficient A/B testing.",
                    journal: "Journal of Data Science",
                    date: "March 2023",
                    doi: "https://doi.org/10.1234/jds.2023.001",
                    abstract: "This paper presents a novel Bayesian approach to A/B testing that reduces required sample sizes by 40% while maintaining statistical power. The method incorporates prior knowledge and provides more interpretable results than traditional frequentist approaches.",
                    keywords: ["Bayesian Statistics", "A/B Testing", "Experimental Design", "Data Science"],
                    citation: "Sentana, N. (2023). Bayesian Statistics Implementation in A/B Testing. Journal of Data Science, 15(2), 123-145."
                },
                {
                    id: 2,
                    title: "Algorithm Optimization for Big Data Processing",
                    description: "Techniques for optimizing algorithms for large-scale data processing.",
                    journal: "International Journal of Computer Science",
                    date: "January 2023",
                    doi: "https://doi.org/10.5678/ijcs.2023.002",
                    abstract: "This research explores various optimization techniques for processing massive datasets efficiently. We present a novel distributed algorithm that reduces processing time by 60% compared to traditional approaches while maintaining accuracy.",
                    keywords: ["Big Data", "Algorithm Optimization", "Distributed Computing", "Performance"],
                    citation: "Sentana, N. (2023). Algorithm Optimization for Big Data Processing. International Journal of Computer Science, 28(1), 45-67."
                },
                {
                    id: 3,
                    title: "Modern Data Pipeline Architecture",
                    description: "Building scalable and maintainable data pipelines (in progress).",
                    journal: "Data Engineering Review",
                    date: "Expected June 2024",
                    doi: "#",
                    abstract: "This ongoing research focuses on modern architectures for data pipelines that balance scalability, maintainability, and performance. Preliminary results show significant improvements in pipeline reliability and development efficiency.",
                    keywords: ["Data Engineering", "Pipeline Architecture", "Scalability", "Maintainability"],
                    citation: "Sentana, N. (2024). Modern Data Pipeline Architecture. Data Engineering Review. (In Progress)"
                }
            ],
            certificates: [
                {
                    id: 1,
                    title: "Google Data Analytics Professional Certificate",
                    description: "Professional data analytics certification from Google.",
                    issuer: "Google via Coursera",
                    date: "December 2022",
                    link: "https://coursera.org/certificates/data-analytics",
                    credentialId: "G-DAP-2022-12345"
                },
                {
                    id: 2,
                    title: "AWS Machine Learning Specialty",
                    description: "AWS specialist certification in machine learning.",
                    issuer: "Amazon Web Services",
                    date: "October 2022",
                    link: "https://aws.amazon.com/certification/",
                    credentialId: "AWS-MLS-2022-67890"
                },
                {
                    id: 3,
                    title: "Deep Learning Specialization",
                    description: "Deep learning specialization certificate.",
                    issuer: "deeplearning.ai",
                    date: "August 2022",
                    link: "https://coursera.org/specializations/deep-learning",
                    credentialId: "DLS-2022-54321"
                },
                {
                    id: 4,
                    title: "TensorFlow Developer Certificate",
                    description: "TensorFlow developer certification.",
                    issuer: "TensorFlow",
                    date: "June 2022",
                    link: "https://www.tensorflow.org/certificate",
                    credentialId: "TFD-2022-98765"
                }
            ],
            experiences: [
                {
                    id: 1,
                    title: "Lead Data Scientist",
                    company: "TechCorp",
                    period: "2022 - Present",
                    description: "Leading data science team for predictive model development and AI solutions.",
                    responsibilities: [
                        "Led a team of 5 data scientists in developing predictive models",
                        "Implemented machine learning pipelines that improved prediction accuracy by 25%",
                        "Collaborated with product teams to integrate AI features into existing products",
                        "Mentored junior data scientists and conducted technical training sessions"
                    ],
                    technologies: ["Python", "TensorFlow", "PyTorch", "AWS", "Docker"]
                },
                {
                    id: 2,
                    title: "Research Assistant",
                    company: "University AI Lab",
                    period: "2020 - 2022",
                    description: "Research assistant focusing on computer vision and deep learning.",
                    responsibilities: [
                        "Conducted research on object detection algorithms",
                        "Published 3 papers in peer-reviewed journals",
                        "Developed novel approaches for medical image analysis",
                        "Collaborated with PhD students on research projects"
                    ],
                    technologies: ["PyTorch", "OpenCV", "Python", "MATLAB", "Linux"]
                },
                {
                    id: 3,
                    title: "Data Science Intern",
                    company: "DataTech Solutions",
                    period: "2019 - 2020",
                    description: "Internship focusing on data analysis and visualization projects.",
                    responsibilities: [
                        "Developed dashboard for business analytics",
                        "Cleaned and processed large datasets for analysis",
                        "Created predictive models for customer behavior",
                        "Presented findings to senior management"
                    ],
                    technologies: ["Python", "R", "Tableau", "SQL", "Scikit-learn"]
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
            },
            collaborations: [
                { name: "GitHub", icon: "fab fa-github", link: "https://github.com/NgurahSentana" },
                { name: "LinkedIn", icon: "fab fa-linkedin", link: "https://linkedin.com/in/ngurahsentana" },
                { name: "Kaggle", icon: "fab fa-kaggle", link: "https://kaggle.com/ngurahsentana" },
                { name: "Google Scholar", icon: "fas fa-graduation-cap", link: "https://scholar.google.com/citations?user=ngurahsentana" },
                { name: "ResearchGate", icon: "fab fa-researchgate", link: "https://researchgate.net/profile/Ngurah_Sentana" },
                { name: "Medium", icon: "fab fa-medium", link: "https://medium.com/@ngurahsentana" },
                { name: "Tableau", icon: "fas fa-chart-bar", link: "https://public.tableau.com/app/profile/ngurah.sentana" },
                { name: "R Shiny", icon: "fas fa-chart-line", link: "https://shinyapps.io/user/ngurahsentana" }
            ],
            photos: [
                { url: "https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80", alt: "Data Analysis" },
                { url: "https://images.unsplash.com/photo-1515879218367-8466d910aaa4?ixlib=rb-4.0.3&auto=format&fit=crop&w=1469&q=80", alt: "Coding Session" },
                { url: "https://images.unsplash.com/photo-1545235617-9465d2a55698?ixlib=rb-4.0.3&auto=format&fit=crop&w=1480&q=80", alt: "Presentation" },
                { url: "https://images.unsplash.com/photo-1555949963-aa79dcee981c?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80", alt: "Machine Learning" },
                { url: "https://images.unsplash.com/photo-1558494949-ef010cbdcc31?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80", alt: "Team Collaboration" },
                { url: "https://images.unsplash.com/photo-1529107386315-e1a2ed48a620?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80", alt: "Conference" }
            ]
        };

        // Function to create project card
        function createProjectCard(project) {
            return `
                <div class="project-card" data-id="${project.id}" data-type="project">
                    <div class="project-image-container">
                        <img src="${project.image}" alt="${project.title}" class="project-image">
                        <span class="project-status ${project.status}">${project.status === 'completed' ? 'Completed' : 'Ongoing'}</span>
                    </div>
                    <div class="project-content">
                        <h3>${project.title}</h3>
                        <p>${project.description}</p>
                        <div class="project-tags">
                            ${project.tags.map(tag => `<span class="tag">${tag}</span>`).join('')}
                        </div>
                    </div>
                </div>
            `;
        }

        // Function to create article card
        function createArticleCard(article) {
            return `
                <div class="article-card" data-id="${article.id}" data-type="article">
                    <div class="article-header">
                        <div class="article-journal">${article.journal}</div>
                        <div class="article-date">Published: ${article.date}</div>
                    </div>
                    <div class="article-content">
                        <h3>${article.title}</h3>
                        <p>${article.description}</p>
                        ${article.doi !== '#' ? `<a href="${article.doi}" class="doi-link" target="_blank">DOI: ${article.doi.split('//')[1]}</a>` : ''}
                    </div>
                </div>
            `;
        }

        // Function to create certificate card
        function createCertificateCard(certificate) {
            return `
                <div class="certificate-card" data-id="${certificate.id}" data-type="certificate">
                    <div class="certificate-icon">
                        <i class="fas fa-award"></i>
                    </div>
                    <div class="certificate-content">
                        <h3>${certificate.title}</h3>
                        <p>${certificate.description}</p>
                        <p><strong>Issuer:</strong> ${certificate.issuer}</p>
                        <p><strong>Date:</strong> ${certificate.date}</p>
                        ${certificate.credentialId ? `<p><strong>Credential ID:</strong> ${certificate.credentialId}</p>` : ''}
                    </div>
                </div>
            `;
        }

        // Function to create experience card
        function createExperienceCard(experience) {
            return `
                <div class="experience-card" data-id="${experience.id}" data-type="experience">
                    <div class="experience-period">${experience.period}</div>
                    <div class="experience-content">
                        <h3>${experience.title}</h3>
                        <p><strong>${experience.company}</strong></p>
                        <p>${experience.description}</p>
                    </div>
                </div>
            `;
        }

        // Function to create skill category
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

        // Function to create collaboration item
        function createCollaborationItem(collab) {
            return `
                <div class="collaboration-item" data-link="${collab.link}">
                    <a href="${collab.link}" target="_blank" class="collaboration-icon">
                        <i class="${collab.icon}"></i>
                    </a>
                    <div class="collaboration-name">${collab.name}</div>
                </div>
            `;
        }

        // Function to create photo item
        function createPhotoItem(photo, index) {
            return `
                <div class="photo-item" data-index="${index}">
                    <img src="${photo.url}" alt="${photo.alt}">
                </div>
            `;
        }

        // Render all elements
        function renderPortfolio() {
            // Render projects
            const projectsGrid = document.getElementById('projectsGrid');
            projectsGrid.innerHTML = portfolioData.projects.map(createProjectCard).join('');
            
            // Render articles
            const articlesGrid = document.getElementById('articlesGrid');
            articlesGrid.innerHTML = portfolioData.articles.map(createArticleCard).join('');
            
            // Render certificates
            const certificatesGrid = document.getElementById('certificatesGrid');
            certificatesGrid.innerHTML = portfolioData.certificates.map(createCertificateCard).join('');
            
            // Render experiences
            const experienceGrid = document.getElementById('experienceGrid');
            experienceGrid.innerHTML = portfolioData.experiences.map(createExperienceCard).join('');
            
            // Render skills
            const skillsContainer = document.getElementById('skillsContainer');
            skillsContainer.innerHTML = `
                ${createSkillCategory('statistics', portfolioData.skills.statistics)}
                ${createSkillCategory('dataScience', portfolioData.skills.dataScience)}
                ${createSkillCategory('computerScience', portfolioData.skills.computerScience)}
            `;
            
            // Render collaborations
            const collaborationContainer = document.getElementById('collaborationContainer');
            collaborationContainer.innerHTML = portfolioData.collaborations.map(createCollaborationItem).join('');
            
            // Render photos
            const photoGrid = document.getElementById('photoGrid');
            photoGrid.innerHTML = portfolioData.photos.map(createPhotoItem).join('');
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
                        <div class="project-tags" style="margin-top: 20px;">
                            ${item.tags.map(tag => `<span class="tag">${tag}</span>`).join('')}
                        </div>
                    `;
                    linkText = 'View on GitHub';
                    linkUrl = item.link;
                    break;
                    
                case 'article':
                    content = `
                        <p><strong>Journal:</strong> ${item.journal}</p>
                        <p><strong>Publication Date:</strong> ${item.date}</p>
                        <p><strong>Abstract:</strong> ${item.abstract}</p>
                        <p><strong>Keywords:</strong> ${item.keywords.join(', ')}</p>
                        <p><strong>Citation:</strong> ${item.citation}</p>
                    `;
                    linkText = item.doi !== '#' ? 'View DOI' : 'Coming Soon';
                    linkUrl = item.doi;
                    break;
                    
                case 'certificate':
                    content = `
                        <p><strong>Description:</strong> ${item.description}</p>
                        <p><strong>Issuer:</strong> ${item.issuer}</p>
                        <p><strong>Date:</strong> ${item.date}</p>
                        ${item.credentialId ? `<p><strong>Credential ID:</strong> ${item.credentialId}</p>` : ''}
                    `;
                    linkText = 'View Certificate';
                    linkUrl = item.link;
                    break;
                    
                case 'experience':
                    content = `
                        <p><strong>Company:</strong> ${item.company}</p>
                        <p><strong>Period:</strong> ${item.period}</p>
                        <p><strong>Description:</strong> ${item.description}</p>
                        <p><strong>Key Responsibilities:</strong></p>
                        <ul style="margin-left: 20px; margin-bottom: 20px;">
                            ${item.responsibilities.map(resp => `<li>${resp}</li>`).join('')}
                        </ul>
                        <p><strong>Technologies Used:</strong> ${item.technologies.join(', ')}</p>
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
                "Based on my experience in data science, I recommend a machine learning approach for this problem. The appropriate model depends on your data characteristics.",
                "For performance optimization in big data processing, consider using parallel processing techniques and efficient data structures.",
                "Bayesian statistics is particularly useful when you have limited data but strong domain knowledge for priors.",
                "When building data pipelines, it's important to consider scalability and maintainability from the design phase.",
                "3D data visualization can provide insights not visible in traditional 2D visualizations, especially for spatial or multivariate data.",
                "For AI production projects, ensure to include model monitoring and automated retraining pipelines."
            ];
            
            askButton.addEventListener('click', function() {
                const question = questionInput.value.trim();
                if (question) {
                    // Simulate thinking
                    responseContent.innerHTML = '<p><i class="fas fa-spinner fa-spin"></i> Processing question...</p>';
                    
                    setTimeout(() => {
                        const randomResponse = responses[Math.floor(Math.random() * responses.length)];
                        responseContent.innerHTML = `
                            <p><strong>Your Question:</strong> "${question}"</p>
                            <p><strong>Answer:</strong> ${randomResponse}</p>
                            <p style="margin-top: 20px; font-size: 0.9rem; color: #6b7280;"><i>This is a simulated response. For detailed consultation, please contact me via email.</i></p>
                        `;
                    }, 1500);
                } else {
                    responseContent.innerHTML = '<p class="response-placeholder">Please enter a question first.</p>';
                }
            });
        }

        // Initialize scroll animations
        function initScrollAnimations() {
            const observerOptions = {
                threshold: 0.1,
                rootMargin: '0px 0px -50px 0px'
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
            
            // Observe elements for animation
            document.querySelectorAll('.project-card, .article-card, .certificate-card, .experience-card, .skill-category, .collaboration-item, .photo-item').forEach(el => {
                observer.observe(el);
            });
        }

        // Initialize everything
        document.addEventListener('DOMContentLoaded', function() {
            // Render portfolio
            renderPortfolio();
            
            // Setup ask me functionality
            setupAskMe();
            
            // Initialize scroll animations
            initScrollAnimations();
            
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
            document.addEventListener('click', function(e) {
                // Project cards
                if (e.target.closest('.project-card')) {
                    const card = e.target.closest('.project-card');
                    const id = parseInt(card.dataset.id);
                    const type = card.dataset.type;
                    const item = portfolioData.projects.find(p => p.id === id);
                    if (item) openModal(item, type);
                }
                
                // Article cards
                if (e.target.closest('.article-card')) {
                    const card = e.target.closest('.article-card');
                    const id = parseInt(card.dataset.id);
                    const type = card.dataset.type;
                    const item = portfolioData.articles.find(a => a.id === id);
                    if (item) openModal(item, type);
                }
                
                // Certificate cards
                if (e.target.closest('.certificate-card')) {
                    const card = e.target.closest('.certificate-card');
                    const id = parseInt(card.dataset.id);
                    const type = card.dataset.type;
                    const item = portfolioData.certificates.find(c => c.id === id);
                    if (item) openModal(item, type);
                }
                
                // Experience cards
                if (e.target.closest('.experience-card')) {
                    const card = e.target.closest('.experience-card');
                    const id = parseInt(card.dataset.id);
                    const type = card.dataset.type;
                    const item = portfolioData.experiences.find(e => e.id === id);
                    if (item) openModal(item, type);
                }
                
                // Photo items
                if (e.target.closest('.photo-item')) {
                    const photoItem = e.target.closest('.photo-item');
                    const index = parseInt(photoItem.dataset.index);
                    const photo = portfolioData.photos[index];
                    
                    const modalOverlay = document.getElementById('modalOverlay');
                    const modalTitle = document.getElementById('modalTitle');
                    const modalContent = document.getElementById('modalContent');
                    const modalLink = document.getElementById('modalLink');
                    
                    modalTitle.textContent = photo.alt;
                    modalContent.innerHTML = `
                        <img src="${photo.url}" alt="${photo.alt}" class="modal-image">
                        <p>${photo.alt}</p>
                    `;
                    modalLink.textContent = 'View Image';
                    modalLink.href = photo.url;
                    
                    modalOverlay.classList.add('active');
                    document.body.style.overflow = 'hidden';
                }
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
            
            // Set current year in footer
            document.getElementById('currentYear').textContent = new Date().getFullYear();
        });
    </script>
</body>
</html>
