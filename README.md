<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GeoSphere - Eksplorasi Bumi Kita</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* Variabel Warna Bumi */
        :root {
            --earth-brown: #8B4513;
            --rock-gray: #708090;
            --soil-red: #A0522D;
            --mineral-green: #556B2F;
            --sky-blue: #87CEEB;
            --deep-blue: #1E3A5F;
            --sand-tan: #D2B48C;
            --lava-red: #FF4500;
            --crystal-purple: #9370DB;
            --text-light: #F5F5F5;
            --text-dark: #333333;
        }
        
        /* Reset & Base Styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: #0c1a2a;
            color: var(--text-light);
            line-height: 1.6;
            background-image: 
                radial-gradient(circle at 20% 30%, rgba(30, 58, 95, 0.3) 0%, transparent 20%),
                radial-gradient(circle at 80% 70%, rgba(139, 69, 19, 0.2) 0%, transparent 20%);
            min-height: 100vh;
        }
        
        /* Header & Navigation */
        header {
            background: linear-gradient(to bottom, rgba(12, 26, 42, 0.95), rgba(12, 26, 42, 0.85));
            backdrop-filter: blur(10px);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            padding: 1rem 0;
            border-bottom: 1px solid rgba(135, 206, 235, 0.2);
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.3);
        }
        
        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 2rem;
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 0.75rem;
        }
        
        .logo-icon {
            color: var(--lava-red);
            font-size: 2rem;
        }
        
        .logo-text {
            font-size: 1.8rem;
            font-weight: 700;
            background: linear-gradient(to right, var(--sand-tan), var(--sky-blue));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }
        
        .nav-links {
            display: flex;
            gap: 1.5rem;
        }
        
        .nav-link {
            color: var(--text-light);
            text-decoration: none;
            font-weight: 600;
            font-size: 1.1rem;
            padding: 0.5rem 1rem;
            border-radius: 4px;
            transition: all 0.3s ease;
            position: relative;
        }
        
        .nav-link:hover {
            color: var(--sky-blue);
            background-color: rgba(135, 206, 235, 0.1);
        }
        
        .nav-link.active {
            color: var(--lava-red);
        }
        
        .nav-link.active::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 50%;
            transform: translateX(-50%);
            width: 60%;
            height: 3px;
            background-color: var(--lava-red);
            border-radius: 2px;
        }
        
        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            color: var(--text-light);
            font-size: 1.5rem;
            cursor: pointer;
        }
        
        /* Main Content */
        main {
            margin-top: 80px;
            padding: 2rem;
            max-width: 1200px;
            margin-left: auto;
            margin-right: auto;
        }
        
        /* Hero Section */
        .hero {
            text-align: center;
            padding: 4rem 2rem;
            background: linear-gradient(135deg, rgba(30, 58, 95, 0.7), rgba(139, 69, 19, 0.5));
            border-radius: 15px;
            margin-bottom: 3rem;
            position: relative;
            overflow: hidden;
            border: 1px solid rgba(135, 206, 235, 0.2);
        }
        
        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-image: url('https://images.unsplash.com/photo-1614732414444-096e5f1122d5?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80');
            background-size: cover;
            background-position: center;
            opacity: 0.2;
            z-index: -1;
        }
        
        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            background: linear-gradient(to right, var(--sand-tan), var(--sky-blue), var(--crystal-purple));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }
        
        .hero p {
            font-size: 1.3rem;
            max-width: 800px;
            margin: 0 auto 2rem;
            color: rgba(245, 245, 245, 0.9);
        }
        
        .cta-button {
            display: inline-block;
            background: linear-gradient(to right, var(--earth-brown), var(--lava-red));
            color: white;
            padding: 1rem 2.5rem;
            font-size: 1.2rem;
            font-weight: 600;
            text-decoration: none;
            border-radius: 50px;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(255, 69, 0, 0.3);
        }
        
        .cta-button:hover {
            transform: translateY(-5px);
            box-shadow: 0 6px 20px rgba(255, 69, 0, 0.5);
        }
        
        /* Content Sections */
        .section-title {
            font-size: 2.5rem;
            margin-bottom: 2rem;
            text-align: center;
            color: var(--sky-blue);
            position: relative;
            padding-bottom: 1rem;
        }
        
        .section-title::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 4px;
            background: linear-gradient(to right, var(--earth-brown), var(--lava-red));
            border-radius: 2px;
        }
        
        /* About Section */
        .about-section {
            margin-bottom: 4rem;
        }
        
        .about-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-bottom: 3rem;
        }
        
        .about-card {
            background: linear-gradient(145deg, rgba(30, 58, 95, 0.7), rgba(85, 107, 47, 0.5));
            border-radius: 10px;
            padding: 2rem;
            border: 1px solid rgba(135, 206, 235, 0.2);
            transition: transform 0.3s ease;
        }
        
        .about-card:hover {
            transform: translateY(-5px);
        }
        
        .about-card h3 {
            color: var(--sky-blue);
            margin-bottom: 1rem;
            font-size: 1.5rem;
            display: flex;
            align-items: center;
            gap: 0.75rem;
        }
        
        .about-card h3 i {
            color: var(--lava-red);
        }
        
        .about-card p {
            color: rgba(245, 245, 245, 0.9);
            margin-bottom: 1rem;
            line-height: 1.7;
        }
        
        .author-profile {
            display: flex;
            align-items: center;
            gap: 1.5rem;
            margin-top: 1.5rem;
            padding-top: 1.5rem;
            border-top: 1px solid rgba(135, 206, 235, 0.2);
        }
        
        .author-avatar {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            object-fit: cover;
            border: 3px solid var(--lava-red);
        }
        
        .author-info h4 {
            color: var(--sand-tan);
            margin-bottom: 0.5rem;
        }
        
        .author-info p {
            font-size: 0.9rem;
            color: rgba(245, 245, 245, 0.7);
        }
        
        .mission-values {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 1.5rem;
            margin-top: 2rem;
        }
        
        .mission-item {
            background-color: rgba(30, 58, 95, 0.3);
            padding: 1.5rem;
            border-radius: 8px;
            border-left: 4px solid var(--crystal-purple);
        }
        
        .mission-item h4 {
            color: var(--sand-tan);
            margin-bottom: 0.5rem;
        }
        
        /* Explore Section dengan Expandable Cards */
        .explore-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-bottom: 4rem;
        }
        
        .explore-card {
            background: linear-gradient(145deg, rgba(30, 58, 95, 0.7), rgba(85, 107, 47, 0.5));
            border-radius: 10px;
            overflow: hidden;
            transition: all 0.3s ease;
            border: 1px solid rgba(135, 206, 235, 0.2);
            cursor: pointer;
        }
        
        .explore-card.expanded {
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.4);
        }
        
        .card-header {
            padding: 1.5rem;
            background-color: rgba(30, 58, 95, 0.8);
            display: flex;
            align-items: center;
            justify-content: space-between;
            transition: background-color 0.3s ease;
        }
        
        .card-header:hover {
            background-color: rgba(30, 58, 95, 0.9);
        }
        
        .card-title-container {
            display: flex;
            align-items: center;
            gap: 1rem;
        }
        
        .card-icon {
            font-size: 2rem;
            color: var(--lava-red);
        }
        
        .card-title {
            font-size: 1.5rem;
            font-weight: 600;
        }
        
        .card-toggle {
            color: var(--sky-blue);
            font-size: 1.2rem;
            transition: transform 0.3s ease;
        }
        
        .explore-card.expanded .card-toggle {
            transform: rotate(180deg);
        }
        
        .card-content {
            padding: 0;
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.5s ease, padding 0.3s ease;
        }
        
        .explore-card.expanded .card-content {
            padding: 1.5rem;
            max-height: 1000px;
        }
        
        .card-image {
            width: 100%;
            height: 200px;
            object-fit: cover;
            border-radius: 8px;
            margin-bottom: 1rem;
        }
        
        .card-content h4 {
            color: var(--sand-tan);
            margin: 1.5rem 0 0.5rem;
            font-size: 1.2rem;
        }
        
        .card-content h4:first-child {
            margin-top: 0;
        }
        
        .card-content p {
            margin-bottom: 1rem;
            color: rgba(245, 245, 245, 0.9);
            line-height: 1.7;
        }
        
        .card-content ul {
            padding-left: 1.5rem;
            margin-bottom: 1rem;
        }
        
        .card-content li {
            margin-bottom: 0.5rem;
            color: rgba(245, 245, 245, 0.9);
        }
        
        .fact-box {
            background-color: rgba(139, 69, 19, 0.2);
            border-left: 4px solid var(--lava-red);
            padding: 1rem;
            margin: 1.5rem 0;
            border-radius: 0 4px 4px 0;
        }
        
        .fact-box strong {
            color: var(--sand-tan);
        }
        
        /* Gallery Section */
        .gallery-section {
            margin-bottom: 4rem;
        }
        
        .gallery-intro {
            text-align: center;
            max-width: 800px;
            margin: 0 auto 2rem;
            color: rgba(245, 245, 245, 0.9);
            font-size: 1.1rem;
        }
        
        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 1.5rem;
        }
        
        .gallery-item {
            border-radius: 8px;
            overflow: hidden;
            height: 250px;
            position: relative;
            cursor: pointer;
            transition: transform 0.3s ease;
        }
        
        .gallery-item:hover {
            transform: scale(1.05);
        }
        
        .gallery-img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s ease;
        }
        
        .gallery-item:hover .gallery-img {
            transform: scale(1.1);
        }
        
        .gallery-caption {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background: linear-gradient(to top, rgba(0, 0, 0, 0.8), transparent);
            padding: 1rem;
            color: white;
            transform: translateY(100%);
            transition: transform 0.3s ease;
        }
        
        .gallery-item:hover .gallery-caption {
            transform: translateY(0);
        }
        
        /* Stories Section dengan Gambar */
        .stories-section {
            margin-bottom: 4rem;
        }
        
        .stories-intro {
            text-align: center;
            max-width: 800px;
            margin: 0 auto 2rem;
            color: rgba(245, 245, 245, 0.9);
            font-size: 1.1rem;
        }
        
        .stories-container {
            display: flex;
            flex-direction: column;
            gap: 2rem;
        }
        
        .story-card {
            display: flex;
            background: linear-gradient(to right, rgba(30, 58, 95, 0.7), rgba(85, 107, 47, 0.5));
            border-radius: 10px;
            overflow: hidden;
            border: 1px solid rgba(135, 206, 235, 0.2);
            transition: transform 0.3s ease;
        }
        
        .story-card:hover {
            transform: translateY(-5px);
        }
        
        .story-image {
            flex: 0 0 250px;
            background-size: cover;
            background-position: center;
        }
        
        .story-content {
            flex: 1;
            padding: 1.5rem;
        }
        
        .story-title {
            font-size: 1.5rem;
            margin-bottom: 0.5rem;
            color: var(--sky-blue);
        }
        
        .story-date {
            color: var(--sand-tan);
            font-size: 0.9rem;
            margin-bottom: 1rem;
        }
        
        .story-excerpt {
            margin-bottom: 1rem;
            color: rgba(245, 245, 245, 0.9);
        }
        
        .story-link {
            color: var(--lava-red);
            text-decoration: none;
            font-weight: 600;
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
        }
        
        .story-link:hover {
            text-decoration: underline;
        }
        
        /* Earth Layers Section dengan Gambar */
        .layers-section {
            margin-bottom: 4rem;
        }
        
        .layers-intro {
            text-align: center;
            max-width: 800px;
            margin: 0 auto 2rem;
            color: rgba(245, 245, 245, 0.9);
            font-size: 1.1rem;
        }
        
        .layers-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }
        
        .layer-card {
            background: linear-gradient(145deg, rgba(30, 58, 95, 0.7), rgba(85, 107, 47, 0.5));
            border-radius: 10px;
            overflow: hidden;
            border: 1px solid rgba(135, 206, 235, 0.2);
            transition: transform 0.3s ease;
        }
        
        .layer-card:hover {
            transform: translateY(-5px);
        }
        
        .layer-image {
            width: 100%;
            height: 200px;
            object-fit: cover;
        }
        
        .layer-content {
            padding: 1.5rem;
        }
        
        .layer-title {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            color: var(--sky-blue);
            display: flex;
            align-items: center;
            gap: 0.75rem;
        }
        
        .layer-icon {
            color: var(--lava-red);
        }
        
        .layer-description {
            color: rgba(245, 245, 245, 0.9);
            margin-bottom: 1rem;
            line-height: 1.7;
        }
        
        .layer-facts {
            background-color: rgba(139, 69, 19, 0.2);
            padding: 1rem;
            border-radius: 8px;
            margin-top: 1rem;
        }
        
        .layer-facts h4 {
            color: var(--sand-tan);
            margin-bottom: 0.5rem;
        }
        
        .layer-facts ul {
            padding-left: 1.2rem;
        }
        
        .layer-facts li {
            margin-bottom: 0.3rem;
            color: rgba(245, 245, 245, 0.9);
        }
        
        /* Contact Section */
        .contact-section {
            margin-bottom: 4rem;
        }
        
        .contact-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }
        
        .contact-info {
            background: linear-gradient(145deg, rgba(30, 58, 95, 0.7), rgba(85, 107, 47, 0.5));
            border-radius: 10px;
            padding: 2rem;
            border: 1px solid rgba(135, 206, 235, 0.2);
        }
        
        .contact-info h3 {
            color: var(--sky-blue);
            margin-bottom: 1.5rem;
        }
        
        .contact-item {
            display: flex;
            align-items: center;
            gap: 1rem;
            margin-bottom: 1.5rem;
        }
        
        .contact-icon {
            width: 50px;
            height: 50px;
            background-color: rgba(135, 206, 235, 0.1);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--lava-red);
            font-size: 1.2rem;
        }
        
        .contact-details h4 {
            color: var(--sand-tan);
            margin-bottom: 0.3rem;
        }
        
        .contact-details p {
            color: rgba(245, 245, 245, 0.8);
        }
        
        .social-links {
            display: flex;
            gap: 1rem;
            margin-top: 2rem;
        }
        
        .social-link {
            width: 45px;
            height: 45px;
            background-color: rgba(135, 206, 235, 0.1);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--sky-blue);
            font-size: 1.2rem;
            text-decoration: none;
            transition: all 0.3s ease;
        }
        
        .social-link:hover {
            background-color: var(--lava-red);
            color: white;
            transform: translateY(-3px);
        }
        
        /* Footer */
        footer {
            background: linear-gradient(to top, rgba(12, 26, 42, 0.95), rgba(30, 58, 95, 0.8));
            padding: 3rem 2rem 1.5rem;
            margin-top: 4rem;
            border-top: 1px solid rgba(135, 206, 235, 0.2);
        }
        
        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-bottom: 2rem;
        }
        
        .footer-column h3 {
            font-size: 1.3rem;
            margin-bottom: 1.5rem;
            color: var(--sky-blue);
        }
        
        .footer-links {
            list-style: none;
        }
        
        .footer-links li {
            margin-bottom: 0.8rem;
        }
        
        .footer-links a {
            color: rgba(245, 245, 245, 0.8);
            text-decoration: none;
            transition: color 0.3s ease;
        }
        
        .footer-links a:hover {
            color: var(--lava-red);
        }
        
        .copyright {
            text-align: center;
            padding-top: 1.5rem;
            border-top: 1px solid rgba(135, 206, 235, 0.2);
            color: rgba(245, 245, 245, 0.7);
            font-size: 0.9rem;
        }
        
        /* Responsive Design */
        @media (max-width: 1100px) {
            .nav-links {
                gap: 1rem;
            }
            
            .nav-link {
                font-size: 1rem;
                padding: 0.5rem 0.8rem;
            }
        }
        
        @media (max-width: 992px) {
            .hero h1 {
                font-size: 2.8rem;
            }
            
            .story-card {
                flex-direction: column;
            }
            
            .story-image {
                flex: 0 0 150px;
            }
        }
        
        @media (max-width: 768px) {
            .nav-links {
                display: none;
                position: absolute;
                top: 100%;
                left: 0;
                right: 0;
                background-color: rgba(12, 26, 42, 0.95);
                flex-direction: column;
                padding: 1rem;
                border-top: 1px solid rgba(135, 206, 235, 0.2);
            }
            
            .nav-links.active {
                display: flex;
            }
            
            .mobile-menu-btn {
                display: block;
            }
            
            .hero h1 {
                font-size: 2.2rem;
            }
            
            .hero p {
                font-size: 1.1rem;
            }
            
            .explore-grid, .layers-grid, .about-container, .contact-container {
                grid-template-columns: 1fr;
            }
            
            .story-card, .layer-card {
                flex-direction: column;
            }
            
            .story-image {
                height: 200px;
                flex: none;
            }
        }
        
        @media (max-width: 576px) {
            .hero {
                padding: 3rem 1rem;
            }
            
            .section-title {
                font-size: 2rem;
            }
        }
    </style>
</head>
<body>
    <!-- Header & Navigation -->
    <header>
        <div class="nav-container">
            <div class="logo">
                <div class="logo-icon">
                    <i class="fas fa-mountain"></i>
                </div>
                <div class="logo-text">GeoSphere</div>
            </div>
            
            <button class="mobile-menu-btn" id="mobileMenuBtn">
                <i class="fas fa-bars"></i>
            </button>
            
            <nav class="nav-links" id="navLinks">
                <a href="#explore" class="nav-link active">Explore</a>
                <a href="#gallery" class="nav-link">Gallery</a>
                <a href="#layers" class="nav-link">Earth Layers</a>
                <a href="#stories" class="nav-link">Earth Stories</a>
                <a href="#about" class="nav-link">About</a>
                <a href="#contact" class="nav-link">Contact</a>
            </nav>
        </div>
    </header>
    
    <!-- Main Content -->
    <main>
        <!-- Hero Section -->
        <section class="hero">
            <h1>Menjelajahi Keajaiban Geologi Bumi</h1>
            <p>Temukan keindahan dan misteri planet kita melalui batuan, mineral, dan formasi geologi yang menakjubkan. Dari puncak gunung berapi hingga kedalaman lembah es, mari kita eksplorasi bersama.</p>
            <a href="#explore" class="cta-button">Mulai Eksplorasi</a>
        </section>
        
        <!-- Explore Section dengan Expandable Cards -->
        <section id="explore">
            <h2 class="section-title">Explore Geologi</h2>
            <div class="explore-grid">
                <!-- Card 1: Mineral & Kristal -->
                <div class="explore-card" id="mineral-card">
                    <div class="card-header" onclick="toggleExpand('mineral-card')">
                        <div class="card-title-container">
                            <div class="card-icon">
                                <i class="fas fa-gem"></i>
                            </div>
                            <h3 class="card-title">Mineral & Kristal</h3>
                        </div>
                        <div class="card-toggle">
                            <i class="fas fa-chevron-down"></i>
                        </div>
                    </div>
                    <div class="card-content">
                        <img src="/Users/eomseonghyeon/geosphere/mineral.jpeg" alt="Mineral dan Kristal" class="card-image">
                        
                        <p>Mineral adalah zat anorganik padat yang terbentuk secara alami dengan struktur kimia dan fisik tertentu. Kristal adalah bentuk mineral dengan susunan atom yang teratur.</p>
                        
                        <h4>Jenis-Jenis Mineral</h4>
                        <ul>
                            <li><strong>Silikat:</strong> Mineral paling umum di kerak bumi (contoh: kuarsa, feldspar)</li>
                            <li><strong>Karbonat:</strong> Mengandung ion karbonat (contoh: kalsit, dolomit)</li>
                            <li><strong>Oksida:</strong> Terbentuk dari oksigen dan logam (contoh: hematit, magnetit)</li>
                            <li><strong>Sulfida:</strong> Mengandung sulfur (contoh: pirit, galena)</li>
                        </ul>
                        
                        <div class="fact-box">
                            <p><strong>Fakta Menarik:</strong> Berlian adalah mineral paling keras di bumi dengan nilai 10 pada skala Mohs, sementara talk adalah mineral paling lunak dengan nilai 1.</p>
                        </div>
                        
                        <h4>Sifat Fisik Mineral</h4>
                        <p>Mineral dapat diidentifikasi melalui sifat fisiknya seperti kilap (logam, non-logam), warna, goresan, kekerasan, belahan, dan pecahan.</p>
                    </div>
                </div>
                
                <!-- Card 2: Formasi Batuan -->
                <div class="explore-card" id="rock-card">
                    <div class="card-header" onclick="toggleExpand('rock-card')">
                        <div class="card-title-container">
                            <div class="card-icon">
                                <i class="fas fa-mountain"></i>
                            </div>
                            <h3 class="card-title">Formasi Batuan</h3>
                        </div>
                        <div class="card-toggle">
                            <i class="fas fa-chevron-down"></i>
                        </div>
                    </div>
                    <div class="card-content">
                        <img src="/Users/eomseonghyeon/geosphere/batu.jpeg" alt="Formasi Batuan" class="card-image">
                        
                        <p>Batuan adalah agregat padat dari satu atau lebih mineral. Terdapat tiga jenis utama batuan berdasarkan proses pembentukannya.</p>
                        
                        <h4>Batuan Beku</h4>
                        <p>Terbentuk dari pembekuan magma atau lava. Contoh: granit (intrusif), basalt (ekstrusif).</p>
                        
                        <h4>Batuan Sedimen</h4>
                        <p>Terbentuk dari pengendapan material di permukaan bumi. Contoh: batu pasir, batu gamping, konglomerat.</p>
                        
                        <h4>Batuan Metamorf</h4>
                        <p>Terbentuk dari perubahan batuan lain akibat panas dan tekanan. Contoh: marmer (dari batu gamping), sabak (dari serpih).</p>
                        
                        <div class="fact-box">
                            <p><strong>Siklus Batuan:</strong> Batuan dapat berubah dari satu jenis ke jenis lain melalui proses geologi dalam siklus yang berkelanjutan.</p>
                        </div>
                        
                        <h4>Struktur Batuan</h4>
                        <p>Struktur seperti perlapisan, kekar, dan foliasi memberikan informasi tentang sejarah pembentukan batuan tersebut.</p>
                    </div>
                </div>
                
                <!-- Card 3: Vulkanologi -->
                <div class="explore-card" id="volcano-card">
                    <div class="card-header" onclick="toggleExpand('volcano-card')">
                        <div class="card-title-container">
                            <div class="card-icon">
                                <i class="fas fa-volcano"></i>
                            </div>
                            <h3 class="card-title">Vulkanologi</h3>
                        </div>
                        <div class="card-toggle">
                            <i class="fas fa-chevron-down"></i>
                        </div>
                    </div>
                    <div class="card-content">
                        <img src="/Users/eomseonghyeon/geosphere/vulkano.jpeg" alt="Gunung Berapi" class="card-image">
                        
                        <p>Vulkanologi adalah ilmu yang mempelajari gunung berapi, lava, magma, dan fenomena geologi terkait.</p>
                        
                        <h4>Jenis Gunung Berapi</h4>
                        <ul>
                            <li><strong>Stratovolcano:</strong> Gunung berapi tinggi dengan sisi curam (contoh: Fuji, Merapi)</li>
                            <li><strong>Perisai:</strong> Gunung berapi rendah dengan lereng landai (contoh: Mauna Loa)</li>
                            <li><strong>Cinder Cone:</strong> Gunung berapi kecil dari material vulkanik lepas</li>
                            <li><strong>Kaldera:</strong> Kawah vulkanik raksasa akibat letusan besar</li>
                        </ul>
                        
                        <h4>Material Vulkanik</h4>
                        <p>Letusan gunung berapi mengeluarkan berbagai material seperti lava, abu vulkanik, bom vulkanik, lapili, dan gas vulkanik (SO₂, CO₂, H₂S).</p>
                        
                        <div class="fact-box">
                            <p><strong>Ring of Fire:</strong> Sekitar 75% gunung berapi aktif dunia terletak di Cincin Api Pasifik, daerah dengan aktivitas seismik tinggi mengelilingi Samudera Pasifik.</p>
                        </div>
                        
                        <h4>Manfaat Gunung Berapi</h4>
                        <p>Meski berbahaya, gunung berapi memberikan manfaat seperti tanah subur, sumber energi panas bumi, mineral berharga, dan objek wisata.</p>
                    </div>
                </div>
            </div>
        </section>
        
        <!-- Gallery Section -->
        <section id="gallery" class="gallery-section">
            <h2 class="section-title">Galeri Geologi</h2>
            <p class="gallery-intro">Jelajahi keindahan formasi geologi dari seluruh penjuru dunia melalui koleksi gambar menakjubkan ini.</p>
            
            <div class="gallery-grid">
                <div class="gallery-item">
                    <img src="/Users/eomseonghyeon/geosphere/panas.jpeg" alt="Grand Prismatic Spring" class="gallery-img">
                    <div class="gallery-caption">Grand Prismatic Spring, USA</div>
                </div>
                
                <div class="gallery-item">
                    <img src="/Users/eomseonghyeon/geosphere/batu kapur.jpeg" alt="Batu Kapur" class="gallery-img">
                    <div class="gallery-caption">Istana Kapas (Pamukkale), Turki</div>
                </div>
                
                <div class="gallery-item">
                    <img src="/Users/eomseonghyeon/geosphere/gua kristal.jpeg" alt="Gua Kristal" class="gallery-img">
                    <div class="gallery-caption">Gua Kristal, Meksiko</div>
                </div>
                
                <div class="gallery-item">
                    <img src="/Users/eomseonghyeon/geosphere/kawah ijen.jpeg" alt="Kawah Ijen" class="gallery-img">
                    <div class="gallery-caption">Kawah Ijen, Indonesia</div>
                </div>
            </div>
        </section>
        
        <!-- Earth Layers Section -->
        <section id="layers" class="layers-section">
            <h2 class="section-title">Lapisan Bumi</h2>
            <p class="layers-intro">Bumi terdiri dari beberapa lapisan dengan karakteristik yang unik. Mari kita jelajahi setiap lapisan dari permukaan hingga inti bumi.</p>
            
            <div class="layers-grid">
                <!-- Kerak Bumi -->
                <div class="layer-card">
                    <img src="/Users/eomseonghyeon/geosphere/kerak.jpeg" alt="Kerak Bumi" class="layer-image">
                    <div class="layer-content">
                        <h3 class="layer-title">
                            <i class="fas fa-layer-group layer-icon"></i>
                            Kerak Bumi
                        </h3>
                        <p class="layer-description">Lapisan terluar dan terdingin bumi yang terdiri dari batuan padat. Kerak bumi dibagi menjadi kerak benua (lebih tebal, kurang padat) dan kerak samudera (lebih tipis, lebih padat).</p>
                        
                        <div class="layer-facts">
                            <h4>Fakta Menarik:</h4>
                            <ul>
                                <li>Ketebalan: 5-70 km</li>
                                <li>Suhu: 0-1000°C</li>
                                <li>Komposisi utama: Oksigen, Silikon, Aluminium</li>
                                <li>Terbagi menjadi lempeng tektonik</li>
                            </ul>
                        </div>
                    </div>
                </div>
                
                <!-- Mantel Bumi -->
                <div class="layer-card">
                    <img src="/Users/eomseonghyeon/geosphere/mantel.jpeg" alt="Mantel Bumi" class="layer-image">
                    <div class="layer-content">
                        <h3 class="layer-title">
                            <i class="fas fa-fire layer-icon"></i>
                            Mantel Bumi
                        </h3>
                        <p class="layer-description">Lapisan terbesar bumi yang berada di bawah kerak. Mantel terdiri dari batuan silikat yang kaya akan magnesium dan besi. Meski sebagian besar padat, material mantel dapat mengalir sangat lambat.</p>
                        
                        <div class="layer-facts">
                            <h4>Fakta Menarik:</h4>
                            <ul>
                                <li>Ketebalan: ~2.900 km</li>
                                <li>Suhu: 1.000-3.700°C</li>
                                <li>Komposisi utama: Silikon, Magnesium, Besi</li>
                                <li>Konveksi mantel menggerakkan lempeng tektonik</li>
                            </ul>
                        </div>
                    </div>
                </div>
                
                <!-- Inti Bumi -->
                <div class="layer-card">
                    <img src="/Users/eomseonghyeon/geosphere/inti.jpeg" alt="Inti Bumi" class="layer-image">
                    <div class="layer-content">
                        <h3 class="layer-title">
                            <i class="fas fa-circle layer-icon"></i>
                            Inti Bumi
                        </h3>
                        <p class="layer-description">Bagian terdalam bumi yang terdiri dari inti luar (cair) dan inti dalam (padat). Terbuat terutama dari besi dan nikel, inti bumi bertanggung jawab untuk menghasilkan medan magnet bumi.</p>
                        
                        <div class="layer-facts">
                            <h4>Fakta Menarik:</h4>
                            <ul>
                                <li>Radius total: ~3.485 km</li>
                                <li>Suhu: 5.000-6.000°C</li>
                                <li>Komposisi utama: Besi (85%), Nikel (10%)</li>
                                <li>Menghasilkan medan magnet pelindung bumi</li>
                            </ul>
                        </div>
                    </div>
                </div>
            </div>
        </section>
        
        <!-- Earth Stories Section -->
        <section id="stories" class="stories-section">
            <h2 class="section-title">Kisah Bumi</h2>
            <p class="stories-intro">Temukan cerita menarik tentang peristiwa geologi yang telah membentuk planet kita seperti yang kita kenal sekarang.</p>
            
            <div class="stories-container">
                <div class="story-card">
                    <div class="story-image" style="background-image:url(/Users/eomseonghyeon/geosphere/everest.jpeg)"></div>
                    <div class="story-content">
                        <h3 class="story-title">Pembentukan Pegunungan Himalaya</h3>
                        <div class="story-date">13 Mei 2023</div>
                        <p class="story-excerpt">Himalaya terbentuk dari tumbukan lempeng India dengan lempeng Eurasia sekitar 50 juta tahun yang lalu. Proses ini masih berlanjut hingga hari ini dengan ketinggian Himalaya yang terus bertambah sekitar 5 mm per tahun.</p>
                        <a href="https://nationalgeographic.grid.id/read/133783428/sejarah-pegunungan-himalaya-puncak-gunung-everest-dulunya-dasar-laut?page=all" class="story-link">Baca Selengkapnya <i class="fas fa-arrow-right"></i></a>
                    </div>
                </div>
                
                <div class="story-card">
                    <div class="story-image" style="background-image: url(/Users/eomseonghyeon/geosphere/letusan.jpeg)"></div>
                    <div class="story-content">
                        <h3 class="story-title">Letusan Krakatau 1883</h3>
                        <div class="story-date">25 Agustus 2025</div>
                        <p class="story-excerpt">Letusan Krakatau tahun 1883 adalah salah satu letusan vulkanik terhebat dalam sejarah. Suara letusannya terdengar hingga 4.800 km dan menyebabkan tsunami yang menghancurkan dengan ketinggian hingga 40 meter.</p>
                        <a href="https://rri.co.id/lain-lain/1791716/sejarah-letusan-krakatau-suara-terdahsyat-sepanjang-masa" class="story-link">Baca Selengkapnya <i class="fas fa-arrow-right"></i></a>
                    </div>
                </div>
                
                <div class="story-card">
                    <div class="story-image" style="background-image: url(/Users/eomseonghyeon/geosphere/great.jpeg)"></div>
                    <div class="story-content">
                        <h3 class="story-title">Pembentukan Great Barrier Reef</h3>
                        <div class="story-date">1 Februari 2024</div>
                        <p class="story-excerpt">Great Barrier Reef adalah struktur hidup terbesar di dunia yang terbentuk dari akumulasi kerangka koral selama jutaan tahun. Terumbu karang ini membentang sepanjang 2.300 km dan dapat dilihat dari luar angkasa.</p>
                        <a href="https://cairns--tours-com.translate.goog/article/how-was-the-great-barrier-reef-formed?_x_tr_sl=en&_x_tr_tl=id&_x_tr_hl=id&_x_tr_pto=tc" class="story-link">Baca Selengkapnya <i class="fas fa-arrow-right"></i></a>
                    </div>
                </div>
            </div>
        </section>

        <!-- About Section -->
        <section id="about" class="about-section">
            <h2 class="section-title">Tentang GeoSphere</h2>
            
            <div class="about-container">
                <!-- Tentang Website -->
                <div class="about-card">
                    <h3><i class="fas fa-globe-americas"></i> Tentang Website</h3>
                    <p>GeoSphere adalah platform edukasi geologi yang didedikasikan untuk membagikan keindahan dan keajaiban planet kita. Website ini bertujuan untuk membuat ilmu geologi dapat diakses oleh semua orang, dari pelajar hingga masyarakat umum.</p>
                    <p>Kami menyajikan informasi kompleks tentang bumi dalam format yang mudah dipahami, dilengkapi dengan visual menarik dan konten interaktif untuk pengalaman belajar yang lebih mendalam.</p>
                    
                    <div class="mission-values">
                        <div class="mission-item">
                            <h4>Misi Kami</h4>
                            <p>Menyebarluaskan pengetahuan geologi kepada masyarakat luas dan meningkatkan kesadaran akan pentingnya melestarikan bumi.</p>
                        </div>
                        <div class="mission-item">
                            <h4>Visi Kami</h4>
                            <p>Menjadi platform referensi geologi terpercaya yang menginspirasi generasi muda untuk mencintai dan mempelajari ilmu kebumian.</p>
                        </div>
                    </div>
                </div>
                
                <!-- Tentang Penulis -->
                <div class="about-card">
                    <h3><i class="fas fa-user-gear"></i> Tentang Penulis</h3>
                    <p>Saya adalah seorang siswa yang menyukai ilmu kebumian terutama ilmu geologi. Situs Geosphere ini lahir dari dua hal: tugas akhir semester sekolah dan kegilaan pribadi pada segala hal tentang planet kita.</p>
                    <p>Saya percaya geologi adalah kisah Bumi yang jarang diketahui banyak orang—ilmu yang menjelaskan dari mana kita berasal dan bagaimana planet ini bekerja.</p>
                    <p>Melalui tulisan sederhana di sini, saya ingin memperkenalkan geologi pada siapa saja, terutama pelajar, bahwa memahami batuan, gempa, gunung api, dan lapisan Bumi bukan hanya urusan ahli, tapi juga cara kita mengenal rumah kita sendiri.</p>
                    <p>Terima kasih sudah mampir ke sini. Situs ini masih terus berkembang, seperti halnya pengetahuan saya tentang geologi. Mari kita jaga Bumi dengan cara paling dasar: memahaminya.</p>
                    
                    
                    <div class="author-profile">
                        <img src="/Users/eomseonghyeon/geosphere/aku.jpeg" alt="Penulis GeoSphere" class="author-avatar">
                        <div class="author-info">
                            <h4>Syalikha Ramdhana</h4>
                            <p>Siswa SMA dan calon geologis masa depan.</p>
                            <p>“Setiap batuan adalah halaman, setiap lapisan bumi adalah bab dari buku Bumi yang tak pernah selesai ditulis.”</p>
                        </div>
                    </div>
                </div>
            </div>
            
            <!-- Why Geology Matters -->
            <div class="about-card" style="margin-top: 2rem;">
                <h3><i class="fas fa-heart"></i> Mengapa Geologi Penting?</h3>
                <p>Geologi bukan hanya ilmu tentang batuan dan mineral. Ilmu ini membantu kita memahami:</p>
                
                <div class="mission-values">
                    <div class="mission-item">
                        <h4>Sejarah Bumi</h4>
                        <p>Mempelajari masa lalu bumi untuk memprediksi masa depan dan memahami perubahan iklim.</p>
                    </div>
                    <div class="mission-item">
                        <h4>Sumber Daya Alam</h4>
                        <p>Menemukan dan mengelola sumber daya mineral, air, dan energi yang vital bagi kehidupan manusia.</p>
                    </div>
                    <div class="mission-item">
                        <h4>Mitigasi Bencana</h4>
                        <p>Memahami proses geologi untuk memprediksi dan mengurangi risiko bencana alam seperti gempa dan letusan gunung berapi.</p>
                    </div>
                </div>
                
                <p style="margin-top: 1.5rem;">Melalui GeoSphere, saya berharap dapat menginspirasi lebih banyak orang untuk tertarik dengan ilmu geologi dan turut serta dalam upaya melestarikan planet kita yang indah ini.</p>
            </div>
        </section>

        <!-- Contact Section -->
        <section id="contact" class="contact-section">
            <h2 class="section-title">Hubungi Kami</h2>
            
            <div class="contact-container">
                <!-- Contact Info -->
                <div class="contact-info">
                    <h3>Informasi Kontak</h3>
                    
                    <div class="contact-item">
                        <div class="contact-icon">
                            <i class="fas fa-envelope"></i>
                        </div>
                        <div class="contact-details">
                            <h4>Email</h4>
                            <p>ngs@nationalgeographic.org</p>
                        </div>
                    </div>
                    
                    <div class="contact-item">
                        <div class="contact-icon">
                            <i class="fas fa-phone"></i>
                        </div>
                        <div class="contact-details">
                            <h4>Telepon</h4>
                            <p>+1-813-979-6845</p>
                            <p>+1-202-857-7000</p>
                            <p>+1-202-857-7700</p>
                        </div>
                    </div>
                    
                    <div class="contact-item">
                        <div class="contact-icon">
                            <i class="fas fa-map-marker-alt"></i>
                        </div>
                        <div class="contact-details">
                            <h4>Alamat</h4>
                            <p>1145 17th Street NW</p>
                            <p>Washington, D.C. 20036, USA</p>
                        </div>
                    </div>
                    
                    <div class="social-links">
                        <a href="https://x.com/NatGeo" class="social-link">
                            <i class="fab fa-twitter"></i>
                        </a>
                        <a href="#https://www.instagram.com/natgeo/" class="social-link">
                            <i class="fab fa-instagram"></i>
                        </a>
                        <a href="https://www.youtube.com/@NatGeo" class="social-link">
                            <i class="fab fa-youtube"></i>
                        </a>
                    </div>
                </div>
                
                <!-- Contact Form -->
                <div class="contact-info">
                    <h3>Kirim Pesan</h3>
                    <form id="contactForm" style="display: flex; flex-direction: column; gap: 1rem;">
                        <input type="text" placeholder="Nama Lengkap" style="padding: 0.8rem; border-radius: 8px; border: 1px solid rgba(135, 206, 235, 0.3); background-color: rgba(30, 58, 95, 0.3); color: white;">
                        <input type="email" placeholder="Alamat Email" style="padding: 0.8rem; border-radius: 8px; border: 1px solid rgba(135, 206, 235, 0.3); background-color: rgba(30, 58, 95, 0.3); color: white;">
                        <input type="text" placeholder="Subjek" style="padding: 0.8rem; border-radius: 8px; border: 1px solid rgba(135, 206, 235, 0.3); background-color: rgba(30, 58, 95, 0.3); color: white;">
                        <textarea placeholder="Pesan Anda" rows="5" style="padding: 0.8rem; border-radius: 8px; border: 1px solid rgba(135, 206, 235, 0.3); background-color: rgba(30, 58, 95, 0.3); color: white; resize: vertical;"></textarea>
                        <button type="submit" style="background: linear-gradient(to right, var(--earth-brown), var(--lava-red)); color: white; padding: 1rem; border: none; border-radius: 8px; font-weight: 600; cursor: pointer; transition: all 0.3s ease;">Kirim Pesan</button>
                    </form>
                </div>
            </div>
        </section>
    </main>
    
    <!-- Footer -->
    <footer>
        <div class="footer-content">
            <div class="footer-column">
                <h3>GeoSphere</h3>
                <p>Portal edukasi geologi untuk memahami keajaiban planet kita. Mari bersama-sama menjelajahi dan melestarikan bumi.</p>
            </div>
            
            <div class="footer-column">
                <h3>Tautan Cepat</h3>
                <ul class="footer-links">
                    <li><a href="#about">About</a></li>
                    <li><a href="#explore">Explore</a></li>
                    <li><a href="#gallery">Gallery</a></li>
                    <li><a href="#stories">Earth Stories</a></li>
                    <li><a href="#layers">Earth Layers</a></li>
                    <li><a href="#contact">Contact</a></li>
                </ul>
            </div>
            
            <div class="footer-column">
                <h3>Sumber Daya</h3>
                <ul class="footer-links">
                    <li><a href="https://id.wikipedia.org/wiki/Geologi#Struktur_Bumi">Glosarium Geologi</a></li>
                    <li><a href="https://geologi.esdm.go.id/geomap">Peta Geologi</a></li>
                    <li><a href="https://webmineral-com.translate.goog/?_x_tr_sl=en&_x_tr_tl=id&_x_tr_hl=id&_x_tr_pto=tc">Database Mineral</a></li>
                    <li><a href="http://eprints.upnyk.ac.id/28768/1/13.b.1.%20Geologi%20dan%20Pengaruh%20Alterasi%20Terhadap%20Potensi%20Gerakan%20Tanah%20Daerah%20Citorek%20Kidul.pdf">Artikel Ilmiah</a></li>
                </ul>
            </div>
        </div>
        
        <div class="copyright">
            <p>&copy; 2025 GeoSphere. Semua hak dilindungi. | Dibuat dengan <i class="fas fa-heart" style="color: var(--lava-red)"></i> untuk bumi kita</p>
        </div>
    </footer>
    
    <script>
        // Mobile Menu Toggle
        document.getElementById('mobileMenuBtn').addEventListener('click', function() {
            document.getElementById('navLinks').classList.toggle('active');
        });
        
        // Close mobile menu when clicking on a link
        document.querySelectorAll('.nav-link').forEach(link => {
            link.addEventListener('click', function() {
                document.getElementById('navLinks').classList.remove('active');
                
                // Update active nav link
                document.querySelectorAll('.nav-link').forEach(item => {
                    item.classList.remove('active');
                });
                this.classList.add('active');
            });
        });
        
        // Fungsi untuk toggle expandable cards di section Explore
        function toggleExpand(cardId) {
            const card = document.getElementById(cardId);
            card.classList.toggle('expanded');
            
            // Tutup kartu lain jika yang ini dibuka (opsional)
            if (card.classList.contains('expanded')) {
                const allCards = document.querySelectorAll('.explore-card');
                allCards.forEach(otherCard => {
                    if (otherCard.id !== cardId && otherCard.classList.contains('expanded')) {
                        otherCard.classList.remove('expanded');
                    }
                });
            }
        }
        
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
        
        // Add hover effect to gallery items
        document.querySelectorAll('.gallery-item').forEach(item => {
            item.addEventListener('mouseenter', function() {
                this.style.zIndex = '10';
            });
            
            item.addEventListener('mouseleave', function() {
                this.style.zIndex = '1';
            });
        });
        
        // Buka kartu pertama secara default saat halaman dimuat
        document.addEventListener('DOMContentLoaded', function() {
            // Buka kartu pertama
            const firstCard = document.getElementById('mineral-card');
            if (firstCard) {
                firstCard.classList.add('expanded');
            }
            
            // Set active nav link berdasarkan section yang sedang dilihat
            window.addEventListener('scroll', function() {
                const sections = document.querySelectorAll('section');
                const navLinks = document.querySelectorAll('.nav-link');
                
                let currentSection = '';
                
                sections.forEach(section => {
                    const sectionTop = section.offsetTop - 100;
                    const sectionHeight = section.clientHeight;
                    if (window.scrollY >= sectionTop && window.scrollY < sectionTop + sectionHeight) {
                        currentSection = section.getAttribute('id');
                    }
                });
                
                navLinks.forEach(link => {
                    link.classList.remove('active');
                    if (link.getAttribute('href') === `#${currentSection}`) {
                        link.classList.add('active');
                    }
                });
            });
        });
        
        // Contact Form Submission
        document.getElementById('contactForm').addEventListener('submit', function(e) {
            e.preventDefault();
            alert('Terima kasih! Pesan Anda telah dikirim. Kami akan menghubungi Anda secepatnya.');
            this.reset();
        });
        
        // Image lazy loading effect untuk gallery
        document.querySelectorAll('.gallery-img').forEach(img => {
            img.addEventListener('load', function() {
                this.style.opacity = '1';
                this.style.transition = 'opacity 0.5s ease';
            });
            
            // Set initial opacity
            img.style.opacity = '0';
        });
    </script>
</body>
</html>
