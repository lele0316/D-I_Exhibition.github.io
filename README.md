<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>NICE TOGETHER - SaloneSatellite 2026</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;900&display=swap" rel="stylesheet">
    <style>
        /* ============================================
           DESIGN SYSTEM - NICE TOGETHER EXHIBITION
           ============================================ */
        
        * {
            font-family: 'Inter', sans-serif;
        }
        
        /* ===== COLOR SYSTEM ===== */
        :root {
            --color-primary-green: #D9FF00;
            --color-primary-green-rgb: 217, 255, 0;
            --color-primary-purple: #B388EB;
            --color-primary-purple-rgb: 179, 136, 235;
            --color-white: #FFFFFF;
            --color-white-rgb: 255, 255, 255;
            --color-light-gray: #F0F0F0;
            --color-light-gray-rgb: 240, 240, 240;
            --color-dark-gray: #1A1A1A;
            --color-dark-gray-rgb: 26, 26, 26;
            
            --color-accent: #D9FF00;
            --color-highlight: #B388EB;
            
            --spacing-xs: 4px;
            --spacing-sm: 8px;
            --spacing-md: 16px;
            --spacing-lg: 24px;
            --spacing-xl: 32px;
            --spacing-2xl: 48px;
            --spacing-3xl: 64px;
            --spacing-4xl: 96px;
        }
        
        /* ===== TYPOGRAPHY SYSTEM ===== */
        .font-h1 {
            font-size: clamp(48px, 8vw, 72px);
            font-weight: 900;
            line-height: 0.9;
            letter-spacing: -0.02em;
        }
        
        .font-h2 {
            font-size: clamp(36px, 5vw, 48px);
            font-weight: 900;
            line-height: 1.1;
            letter-spacing: -0.01em;
        }
        
        .font-h3 {
            font-size: clamp(28px, 4vw, 36px);
            font-weight: 700;
            line-height: 1.2;
        }
        
        .font-h4 {
            font-size: clamp(20px, 3vw, 24px);
            font-weight: 600;
            line-height: 1.3;
        }
        
        .font-body-large {
            font-size: 18px;
            font-weight: 400;
            line-height: 1.6;
        }
        
        .font-body {
            font-size: 16px;
            font-weight: 400;
            line-height: 1.6;
        }
        
        .font-body-small {
            font-size: 14px;
            font-weight: 400;
            line-height: 1.5;
        }
        
        .font-caption {
            font-size: 12px;
            font-weight: 400;
            line-height: 1.4;
        }
        
        .font-brand {
            font-size: 48px;
            font-weight: 500;
            line-height: 1.1;
            letter-spacing: -0.02em;
        }
        
        .font-keyword {
            font-weight: 700;
            color: var(--color-primary-green);
        }
        
        .font-emphasis {
            color: var(--color-primary-green);
            font-weight: 600;
        }
        
        /* ===== BACKGROUND & TEXTURE ===== */
        .bg-poster-image {
            background-image: url('poster.png');
            background-size: cover;
            background-position: center;
            background-repeat: no-repeat;
            position: relative;
        }
        
        .bg-poster-image::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(135deg, rgba(179, 136, 235, 0.1) 0%, rgba(217, 255, 0, 0.1) 50%, rgba(179, 136, 235, 0.1) 100%);
            animation: overlayPulse 8s ease-in-out infinite;
            pointer-events: none;
        }
        
        @keyframes overlayPulse {
            0%, 100% { opacity: 0.3; }
            50% { opacity: 0.7; }
        }
        
        .bg-poster-image .bg-moving-elements {
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            overflow: hidden;
            pointer-events: none;
        }
        
        .bg-poster-image .moving-shape {
            position: absolute;
            background: linear-gradient(135deg, rgba(179, 136, 235, 0.15), rgba(217, 255, 0, 0.15));
            animation: moveShape 20s linear infinite;
        }
        
        .bg-poster-image .moving-shape:nth-child(1) {
            width: 200px;
            height: 200px;
            top: 10%;
            left: -100px;
            animation-delay: 0s;
        }
        
        .bg-poster-image .moving-shape:nth-child(2) {
            width: 150px;
            height: 150px;
            top: 60%;
            right: -80px;
            animation-delay: -5s;
            animation-direction: reverse;
        }
        
        .bg-poster-image .moving-shape:nth-child(3) {
            width: 100px;
            height: 100px;
            bottom: 20%;
            left: 30%;
            animation-delay: -10s;
        }
        
        @keyframes moveShape {
            0% { transform: translateX(0) translateY(0) rotate(0deg); }
            25% { transform: translateX(50px) translateY(-30px) rotate(90deg); }
            50% { transform: translateX(100px) translateY(0) rotate(180deg); }
            75% { transform: translateX(50px) translateY(30px) rotate(270deg); }
            100% { transform: translateX(0) translateY(0) rotate(360deg); }
        }
        
        .bg-gradient-poster {
            background: linear-gradient(135deg, #B388EB 0%, #D9FF00 50%, #B388EB 100%);
            background-size: 400% 400%;
            animation: gradientShift 15s cubic-bezier(0.4, 0, 0.2, 1) infinite;
        }
        
        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }
        
        @media (max-width: 768px) {
            .bg-gradient-poster {
                animation: none;
                background-position: 50% 50%;
            }
            
            .bg-poster-image .moving-shape {
                display: none;
            }
        }
        
        .bg-standard {
            background: var(--color-dark-gray);
        }
        
        .bg-texture {
            position: relative;
            overflow: hidden;
        }
        
        .bg-texture::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-image: 
                linear-gradient(45deg, rgba(255,255,255,0.03) 25%, transparent 25%),
                linear-gradient(-45deg, rgba(255,255,255,0.03) 25%, transparent 25%),
                linear-gradient(45deg, transparent 75%, rgba(255,255,255,0.03) 75%),
                linear-gradient(-45deg, transparent 75%, rgba(255,255,255,0.03) 75%);
            background-size: 60px 60px;
            background-position: 0 0, 0 30px, 30px -30px, -30px 0px;
            pointer-events: none;
        }
        
        /* ===== ANIMATIONS & TRANSITIONS ===== */
        .fade-in-up {
            opacity: 0;
            transform: translateY(30px);
            transition: opacity 0.5s ease-out, transform 0.5s ease-out;
        }
        
        .fade-in-up.visible {
            opacity: 1;
            transform: translateY(0);
        }
        
        .btn-hover {
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        }
        
        .btn-hover:hover {
            transform: scale(1.02);
            filter: brightness(1.1);
        }
        
        .btn-hover:active {
            transform: scale(0.98);
        }
        
        .card-hover {
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        }
        
        .card-hover:hover {
            transform: scale(1.02);
        }
        
        .nav-sticky {
            backdrop-filter: blur(20px);
            background: rgba(26, 26, 26, 0.8);
        }
        
        .hero-title {
            line-height: 0.85;
        }
        
        .square-dot {
            width: 12px;
            height: 12px;
            background: var(--color-primary-green);
            flex-shrink: 0;
        }
        
        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
        }
        
        .float-animation {
            animation: float 3s ease-in-out infinite;
        }
        
        .scroll-container {
            overflow-x: auto;
            scroll-snap-type: x mandatory;
            -webkit-overflow-scrolling: touch;
            scrollbar-width: none;
            -ms-overflow-style: none;
        }
        
        .scroll-container::-webkit-scrollbar {
            display: none;
        }
        
        .scroll-item {
            scroll-snap-align: start;
            flex-shrink: 0;
        }
        
        .content-max-width {
            max-width: 80rem;
        }
        
        .page-transition {
            transition: opacity 0.3s ease-in-out, transform 0.3s ease-in-out;
        }
        
        .modal-overlay {
            background: rgba(26, 26, 26, 0.95);
            backdrop-filter: blur(10px);
        }
        
        .focus-visible-ring:focus-visible {
            outline: 2px solid var(--color-primary-green);
            outline-offset: 2px;
        }
        
        .aria-label {
            position: absolute;
            width: 1px;
            height: 1px;
            padding: 0;
            margin: -1px;
            overflow: hidden;
            clip: rect(0, 0, 0, 0);
            white-space: nowrap;
            border: 0;
        }
        
        /* ===== SPECIAL ELEMENTS ===== */
        .milano-badge {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            padding: 8px 16px;
            background: linear-gradient(135deg, var(--color-primary-purple), var(--color-primary-green));
            border-radius: 50px;
            font-weight: 700;
            color: var(--color-dark-gray);
        }
        
        .cta-button {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 12px;
            padding: 16px 32px;
            background: linear-gradient(135deg, var(--color-primary-purple), var(--color-primary-green));
            border: none;
            border-radius: 50px;
            font-size: 18px;
            font-weight: 700;
            color: var(--color-dark-gray);
            cursor: pointer;
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        }
        
        .cta-button:hover {
            transform: scale(1.05);
            box-shadow: 0 10px 40px rgba(217, 255, 0, 0.3);
        }
        
        .cta-button:active {
            transform: scale(0.98);
        }
        
        .paragraph-spacing {
            margin-bottom: var(--spacing-lg);
        }
        
        .paragraph-spacing-small {
            margin-bottom: var(--spacing-md);
        }
        
        .lead-line-height {
            line-height: 1.5;
        }
    </style>
</head>
<body class="bg-standard text-white overflow-x-hidden">
    
    <!-- Navigation -->
    <nav id="navbar" class="fixed top-0 left-0 right-0 z-50 transition-all duration-300" role="navigation" aria-label="Main navigation">
        <div class="content-max-width mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-16 md:h-20">
                <a href="#home" class="text-2xl md:text-3xl font-black tracking-tight focus-visible-ring rounded">
                    <span class="text-[#D9FF00]">NICE</span> <span class="text-[#B388EB]">TOGETHER</span>
                </a>
                
                <div class="hidden md:flex items-center space-x-8">
                    <a href="#home" class="nav-link text-white hover:text-[#D9FF00] transition-colors font-medium focus-visible-ring rounded" data-en="Home" data-zh="首页">Home</a>
                    <a href="#about" class="nav-link text-white hover:text-[#D9FF00] transition-colors font-medium focus-visible-ring rounded" data-en="About" data-zh="关于">About</a>
                    <a href="#sections" class="nav-link text-white hover:text-[#D9FF00] transition-colors font-medium focus-visible-ring rounded" data-en="Sections" data-zh="板块">Sections</a>
                    <a href="#nice-planet" class="nav-link text-white hover:text-[#D9FF00] transition-colors font-medium focus-visible-ring rounded" data-en="Nice Planet" data-zh="美好星球">Nice Planet</a>
                    <a href="#nice-voice" class="nav-link text-white hover:text-[#D9FF00] transition-colors font-medium focus-visible-ring rounded" data-en="Nice Voice" data-zh="美好声音">Nice Voice</a>
                    <a href="#nice-partner" class="nav-link text-white hover:text-[#D9FF00] transition-colors font-medium focus-visible-ring rounded" data-en="Nice Partner" data-zh="美好伙伴">Nice Partner</a>
                    
                    <button id="langToggle" class="btn-hover px-4 py-2 bg-gradient-to-r from-[#B388EB] to-[#D9FF00] text-white font-bold rounded-full text-sm focus-visible-ring" aria-label="Toggle language">
                        <span id="langText">中文</span>
                    </button>
                </div>
                
                <div class="md:hidden flex items-center space-x-4">
                    <button id="langToggleMobile" class="btn-hover px-3 py-1.5 bg-gradient-to-r from-[#B388EB] to-[#D9FF00] text-white font-bold rounded-full text-xs focus-visible-ring" aria-label="Toggle language">
                        <span id="langTextMobile">中文</span>
                    </button>
                    <button id="mobileMenuBtn" class="text-white p-2 focus-visible-ring rounded" aria-label="Toggle mobile menu" aria-expanded="false">
                        <svg class="w-8 h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24" aria-hidden="true">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"/>
                        </svg>
                    </button>
                </div>
            </div>
        </div>
        
        <div id="mobileMenu" class="hidden md:hidden bg-gradient-to-br from-[#B388EB] to-[#D9FF00]" role="menu">
            <div class="px-4 py-8 space-y-6">
                <a href="#home" class="block text-xl font-bold text-white hover:text-[#1A1A1A] transition-colors focus-visible-ring rounded" role="menuitem" data-en="Home" data-zh="首页">Home</a>
                <a href="#about" class="block text-xl font-bold text-white hover:text-[#1A1A1A] transition-colors focus-visible-ring rounded" role="menuitem" data-en="About" data-zh="关于">About</a>
                <a href="#sections" class="block text-xl font-bold text-white hover:text-[#1A1A1A] transition-colors focus-visible-ring rounded" role="menuitem" data-en="Sections" data-zh="板块">Sections</a>
                <a href="#nice-planet" class="block text-xl font-bold text-white hover:text-[#1A1A1A] transition-colors focus-visible-ring rounded" role="menuitem" data-en="Nice Planet" data-zh="美好星球">Nice Planet</a>
                <a href="#nice-voice" class="block text-xl font-bold text-white hover:text-[#1A1A1A] transition-colors focus-visible-ring rounded" role="menuitem" data-en="Nice Voice" data-zh="美好声音">Nice Voice</a>
                <a href="#nice-partner" class="block text-xl font-bold text-white hover:text-[#1A1A1A] transition-colors focus-visible-ring rounded" role="menuitem" data-en="Nice Partner" data-zh="美好伙伴">Nice Partner</a>
            </div>
        </div>
    </nav>
    
    <!-- Hero Section -->
    <section id="home" class="min-h-screen bg-poster-image relative flex items-center">
        <div class="bg-moving-elements">
            <div class="moving-shape"></div>
            <div class="moving-shape"></div>
            <div class="moving-shape"></div>
        </div>
        
        <div class="absolute bottom-8 left-0 right-0 px-4">
            <div class="content-max-width mx-auto">
                <div class="text-center">
                    <a href="#about" class="inline-flex items-center gap-3 text-white font-bold text-xl md:text-2xl opacity-80 hover:opacity-100 transition-opacity float-animation focus-visible-ring rounded">
                        <span data-en="Scroll to Explore" data-zh="向下探索">Scroll to Explore</span>
                        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" aria-hidden="true">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 14l-7 7m0 0l-7-7m7 7V3"/>
                        </svg>
                    </a>
                </div>
            </div>
        </div>
    </section>
    
    <!-- About Section -->
    <section id="about" class="py-20 md:py-32 bg-standard relative overflow-hidden">
        <div class="content-max-width mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
            <div class="fade-in-up">
                <div class="flex items-center gap-4 mb-12">
                    <div class="square-dot"></div>
                    <h2 class="font-h2 text-white" data-en="About the Exhibition" data-zh="关于展览">About the Exhibition</h2>
                </div>
                
                <div class="grid md:grid-cols-2 gap-12 lg:gap-16 mb-16">
                    <div>
                        <p class="font-brand text-white mb-8">NICE TOGETHER</p>
                        
                        <div class="space-y-6">
                            <div class="paragraph-spacing">
                                <p class="font-body text-[#F0F0F0] lead-line-height" id="about-text-1">
                                    <span class="about-text-en">NICE Global is an innovation project launched in 2015 by the College of Design and Innovation (D&amp;I) at Tongji University, built upon years of research and practice in social innovation design. NICE stands for <span class="font-keyword">Neighborhood</span>, <span class="font-keyword">Innovation</span>, <span class="font-keyword">Creativity</span>, and <span class="font-keyword">Entrepreneurship</span>.</span>
                                    <span class="about-text-zh hidden">NICE Global 是同济大学设计创意学院（D&amp;I）于2015年启动的创新项目，基于多年的社会创新设计研究与实践。NICE 代表 <span class="font-keyword">Neighborhood</span>（邻里）、<span class="font-keyword">Innovation</span>（创新）、<span class="font-keyword">Creativity</span>（创意）和 <span class="font-keyword">Entrepreneurship</span>（创业）。</span>
                                </p>
                            </div>
                            
                            <div class="paragraph-spacing">
                                <p class="font-body text-[#F0F0F0] lead-line-height" id="about-text-2">
                                    <span class="about-text-en">The project aims to leverage global talent, creativity, technology, capital, and transformation support to focus on future lifestyles. Driven by design thinking and centered on user needs, it integrates interdisciplinary approaches and reverse innovation initiatives to catalyze the spillover of university knowledge and resources, creating new models and new economies.</span>
                                    <span class="about-text-zh hidden">该项目旨在汇聚全球人才、创意、技术、资本和转型支持，聚焦未来生活方式。以设计思维为驱动，以用户需求为中心，整合跨学科方法和逆向创新举措，促进大学知识和资源的溢出，创造新模式和新经济。</span>
                                </p>
                            </div>
                            
                            <div class="paragraph-spacing">
                                <p class="font-body text-[#F0F0F0] lead-line-height" id="about-text-3">
                                    <span class="about-text-en"><span class="font-emphasis">TOGETHER</span> is not a simple juxtaposition, but a deep intersection, not superficial collaboration, but mutual fulfilment and joint advancement. In 2026, we are bringing "NICE TOGETHER" to Milan. We sincerely invite you to join the NICE Global community to co-create and share responsible global impact.</span>
                                    <span class="about-text-zh hidden"><span class="font-emphasis">TOGETHER</span> 不是简单的并列，而是深度的交融；不是表面的合作，而是相互成就和共同进步。2026年，我们将 "NICE TOGETHER" 带到米兰。我们诚挚邀请您加入 NICE Global 社区，共同创造和分享负责任的全球影响力。</span>
                                </p>
                            </div>
                        </div>
                    </div>
                    
                    <div class="flex flex-col justify-between">
                        <div class="space-y-4 mb-8">
                            <div class="milano-badge">
                                <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">
                                    <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 15l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z"/>
                                </svg>
                                <span data-en="2026 MILANO" data-zh="2026 米兰">2026 MILANO</span>
                            </div>
                            
                            <div class="space-y-3 pt-4">
                                <div class="flex justify-between">
                                    <span class="text-[#F0F0F0] font-body" data-en="Date" data-zh="日期">Date</span>
                                    <span class="text-white font-bold">21-26.04.2026</span>
                                </div>
                                <div class="flex justify-between">
                                    <span class="text-[#F0F0F0] font-body" data-en="Location" data-zh="地点">Location</span>
                                    <span class="text-white font-bold">Booth A24, Hall 7</span>
                                </div>
                                <div class="flex justify-between">
                                    <span class="text-[#F0F0F0] font-body" data-en="Venue" data-zh="展馆">Venue</span>
                                    <span class="text-white font-bold">Fiera Milano-Rho</span>
                                </div>
                            </div>
                        </div>
                        
                        <div>
                            <button class="cta-button w-full md:w-auto" data-en="Join Us at SaloneSatellite" data-zh="加入我们在 SaloneSatellite">
                                <span>Join Us at SaloneSatellite</span>
                                <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 8l4 4m0 0l-4 4m4-4H3"/>
                                </svg>
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Sections Preview -->
    <section id="sections" class="py-20 md:py-32 bg-standard relative overflow-hidden">
        <div class="content-max-width mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
            <div class="fade-in-up">
                <div class="flex items-center gap-4 mb-16">
                    <div class="square-dot"></div>
                    <h2 class="font-h2 text-white" data-en="Exhibition Sections" data-zh="展览板块">Exhibition Sections</h2>
                </div>
                
                <div class="grid md:grid-cols-3 gap-6 lg:gap-8">
                    <a href="#nice-planet" class="card-hover bg-[#F0F0F0]/5 rounded-3xl p-8 border border-white/10 focus-visible-ring group">
                        <div class="aspect-square bg-gradient-to-br from-[#B388EB]/30 to-[#D9FF00]/30 rounded-2xl flex items-center justify-center mb-6">
                            <span class="text-6xl font-black text-white">01</span>
                        </div>
                        <h3 class="font-h3 text-white mb-4" data-en="Nice Planet" data-zh="美好星球">Nice Planet</h3>
                        <div class="inline-flex items-center gap-2 text-[#D9FF00] font-bold">
                            <span data-en="View More" data-zh="查看更多">View More</span>
                            <svg class="w-5 h-5 transition-transform group-hover:translate-x-1" fill="none" stroke="currentColor" viewBox="0 0 24 24" aria-hidden="true">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 8l4 4m0 0l-4 4m4-4H3"/>
                            </svg>
                        </div>
                    </a>
                    
                    <a href="#nice-voice" class="card-hover bg-[#F0F0F0]/5 rounded-3xl p-8 border border-white/10 focus-visible-ring group">
                        <div class="aspect-square bg-gradient-to-br from-[#D9FF00]/30 to-[#B388EB]/30 rounded-2xl flex items-center justify-center mb-6">
                            <span class="text-6xl font-black text-white">02</span>
                        </div>
                        <h3 class="font-h3 text-white mb-4" data-en="Nice Voice" data-zh="美好声音">Nice Voice</h3>
                        <div class="inline-flex items-center gap-2 text-[#D9FF00] font-bold">
                            <span data-en="View More" data-zh="查看更多">View More</span>
                            <svg class="w-5 h-5 transition-transform group-hover:translate-x-1" fill="none" stroke="currentColor" viewBox="0 0 24 24" aria-hidden="true">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 8l4 4m0 0l-4 4m4-4H3"/>
                            </svg>
                        </div>
                    </a>
                    
                    <a href="#nice-partner" class="card-hover bg-[#F0F0F0]/5 rounded-3xl p-8 border border-white/10 focus-visible-ring group">
                        <div class="aspect-square bg-gradient-to-br from-[#B388EB]/30 to-[#D9FF00]/30 rounded-2xl flex items-center justify-center mb-6">
                            <span class="text-6xl font-black text-white">03</span>
                        </div>
                        <h3 class="font-h3 text-white mb-4" data-en="Nice Partner" data-zh="美好伙伴">Nice Partner</h3>
                        <div class="inline-flex items-center gap-2 text-[#D9FF00] font-bold">
                            <span data-en="View More" data-zh="查看更多">View More</span>
                            <svg class="w-5 h-5 transition-transform group-hover:translate-x-1" fill="none" stroke="currentColor" viewBox="0 0 24 24" aria-hidden="true">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 8l4 4m0 0l-4 4m4-4H3"/>
                            </svg>
                        </div>
                    </a>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Nice Planet Section -->
    <section id="nice-planet" class="py-20 md:py-32 bg-standard relative overflow-hidden">
        <div class="content-max-width mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
            <div class="fade-in-up">
                <div class="flex items-center gap-4 mb-12">
                    <div class="square-dot"></div>
                    <h2 class="font-h2 text-white">Nice Planet</h2>
                </div>
                
                <div class="md:hidden">
                    <div class="scroll-container flex gap-6 pb-4" role="list" aria-label="Nice Planet works">
                        <button class="scroll-item w-72 card-hover bg-[#F0F0F0]/5 rounded-2xl overflow-hidden border border-white/10 text-left focus-visible-ring" onclick="openWorkDetail('planet', 1)" role="listitem" aria-label="View Eco Design details">
                            <div class="aspect-square bg-gradient-to-br from-[#B388EB]/30 to-[#D9FF00]/30 flex items-center justify-center">
                                <span class="text-[#1A1A1A] font-bold">Work 1</span>
                            </div>
                            <div class="p-6">
                                <h4 class="font-h4 text-white mb-2" data-en="Eco Design" data-zh="生态设计">Eco Design</h4>
                                <p class="text-[#D9FF00] font-medium" data-en="Designer A" data-zh="设计师A">Designer A</p>
                            </div>
                        </button>
                        <button class="scroll-item w-72 card-hover bg-[#F0F0F0]/5 rounded-2xl overflow-hidden border border-white/10 text-left focus-visible-ring" onclick="openWorkDetail('planet', 2)" role="listitem" aria-label="View Nature Harmony details">
                            <div class="aspect-square bg-gradient-to-br from-[#D9FF00]/30 to-[#B388EB]/30 flex items-center justify-center">
                                <span class="text-[#1A1A1A] font-bold">Work 2</span>
                            </div>
                            <div class="p-6">
                                <h4 class="font-h4 text-white mb-2" data-en="Nature Harmony" data-zh="自然和谐">Nature Harmony</h4>
                                <p class="text-[#D9FF00] font-medium" data-en="Designer B" data-zh="设计师B">Designer B</p>
                            </div>
                        </button>
                        <button class="scroll-item w-72 card-hover bg-[#F0F0F0]/5 rounded-2xl overflow-hidden border border-white/10 text-left focus-visible-ring" onclick="openWorkDetail('planet', 3)" role="listitem" aria-label="View Sustainable Future details">
                            <div class="aspect-square bg-gradient-to-br from-[#B388EB]/30 to-[#D9FF00]/30 flex items-center justify-center">
                                <span class="text-[#1A1A1A] font-bold">Work 3</span>
                            </div>
                            <div class="p-6">
                                <h4 class="font-h4 text-white mb-2" data-en="Sustainable Future" data-zh="可持续未来">Sustainable Future</h4>
                                <p class="text-[#D9FF00] font-medium" data-en="Designer C" data-zh="设计师C">Designer C</p>
                            </div>
                        </button>
                        <button class="scroll-item w-72 card-hover bg-[#F0F0F0]/5 rounded-2xl overflow-hidden border border-white/10 text-left focus-visible-ring" onclick="openWorkDetail('planet', 4)" role="listitem" aria-label="View Earth Care details">
                            <div class="aspect-square bg-gradient-to-br from-[#D9FF00]/30 to-[#B388EB]/30 flex items-center justify-center">
                                <span class="text-[#1A1A1A] font-bold">Work 4</span>
                            </div>
                            <div class="p-6">
                                <h4 class="font-h4 text-white mb-2" data-en="Earth Care" data-zh="地球关怀">Earth Care</h4>
                                <p class="text-[#D9FF00] font-medium" data-en="Designer D" data-zh="设计师D">Designer D</p>
                            </div>
                        </button>
                    </div>
                </div>
                
                <div class="hidden md:grid md:grid-cols-2 lg:grid-cols-4 gap-6" role="list" aria-label="Nice Planet works">
                    <button class="card-hover bg-[#F0F0F0]/5 rounded-2xl overflow-hidden border border-white/10 text-left focus-visible-ring" onclick="openWorkDetail('planet', 1)" role="listitem" aria-label="View Eco Design details">
                        <div class="aspect-square bg-gradient-to-br from-[#B388EB]/30 to-[#D9FF00]/30 flex items-center justify-center">
                            <span class="text-[#1A1A1A] font-bold">Work 1</span>
                        </div>
                        <div class="p-6">
                            <h4 class="font-h4 text-white mb-2" data-en="Eco Design" data-zh="生态设计">Eco Design</h4>
                            <p class="text-[#D9FF00] font-medium" data-en="Designer A" data-zh="设计师A">Designer A</p>
                        </div>
                    </button>
                    <button class="card-hover bg-[#F0F0F0]/5 rounded-2xl overflow-hidden border border-white/10 text-left focus-visible-ring" onclick="openWorkDetail('planet', 2)" role="listitem" aria-label="View Nature Harmony details">
                        <div class="aspect-square bg-gradient-to-br from-[#D9FF00]/30 to-[#B388EB]/30 flex items-center justify-center">
                            <span class="text-[#1A1A1A] font-bold">Work 2</span>
                        </div>
                        <div class="p-6">
                            <h4 class="font-h4 text-white mb-2" data-en="Nature Harmony" data-zh="自然和谐">Nature Harmony</h4>
                            <p class="text-[#D9FF00] font-medium" data-en="Designer B" data-zh="设计师B">Designer B</p>
                        </div>
                    </button>
                    <button class="card-hover bg-[#F0F0F0]/5 rounded-2xl overflow-hidden border border-white/10 text-left focus-visible-ring" onclick="openWorkDetail('planet', 3)" role="listitem" aria-label="View Sustainable Future details">
                        <div class="aspect-square bg-gradient-to-br from-[#B388EB]/30 to-[#D9FF00]/30 flex items-center justify-center">
                            <span class="text-[#1A1A1A] font-bold">Work 3</span>
                        </div>
                        <div class="p-6">
                            <h4 class="font-h4 text-white mb-2" data-en="Sustainable Future" data-zh="可持续未来">Sustainable Future</h4>
                            <p class="text-[#D9FF00] font-medium" data-en="Designer C" data-zh="设计师C">Designer C</p>
                        </div>
                    </button>
                    <button class="card-hover bg-[#F0F0F0]/5 rounded-2xl overflow-hidden border border-white/10 text-left focus-visible-ring" onclick="openWorkDetail('planet', 4)" role="listitem" aria-label="View Earth Care details">
                        <div class="aspect-square bg-gradient-to-br from-[#D9FF00]/30 to-[#B388EB]/30 flex items-center justify-center">
                            <span class="text-[#1A1A1A] font-bold">Work 4</span>
                        </div>
                        <div class="p-6">
                            <h4 class="font-h4 text-white mb-2" data-en="Earth Care" data-zh="地球关怀">Earth Care</h4>
                            <p class="text-[#D9FF00] font-medium" data-en="Designer D" data-zh="设计师D">Designer D</p>
                        </div>
                    </button>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Nice Voice Section -->
    <section id="nice-voice" class="py-20 md:py-32 bg-standard relative overflow-hidden">
        <div class="content-max-width mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
            <div class="fade-in-up">
                <div class="flex items-center gap-4 mb-12">
                    <div class="square-dot"></div>
                    <h2 class="font-h2 text-white">Nice Voice</h2>
                </div>
                
                <div class="md:hidden">
                    <div class="scroll-container flex gap-6 pb-4" role="list" aria-label="Nice Voice works">
                        <button class="scroll-item w-72 card-hover bg-[#F0F0F0]/5 rounded-2xl overflow-hidden border border-white/10 text-left focus-visible-ring" onclick="openWorkDetail('voice', 1)" role="listitem" aria-label="View Human Connection details">
                            <div class="aspect-square bg-gradient-to-br from-[#B388EB]/30 to-[#D9FF00]/30 flex items-center justify-center">
                                <span class="text-[#1A1A1A] font-bold">Work 1</span>
                            </div>
                            <div class="p-6">
                                <h4 class="font-h4 text-white mb-2" data-en="Human Connection" data-zh="人际连接">Human Connection</h4>
                                <p class="text-[#D9FF00] font-medium" data-en="Designer E" data-zh="设计师E">Designer E</p>
                            </div>
                        </button>
                        <button class="scroll-item w-72 card-hover bg-[#F0F0F0]/5 rounded-2xl overflow-hidden border border-white/10 text-left focus-visible-ring" onclick="openWorkDetail('people', 2)" role="listitem" aria-label="View Community Bond details">
                            <div class="aspect-square bg-gradient-to-br from-[#D9FF00]/30 to-[#B388EB]/30 flex items-center justify-center">
                                <span class="text-[#1A1A1A] font-bold">Work 2</span>
                            </div>
                            <div class="p-6">
                                <h4 class="font-h4 text-white mb-2" data-en="Community Bond" data-zh="社区纽带">Community Bond</h4>
                                <p class="text-[#D9FF00] font-medium" data-en="Designer F" data-zh="设计师F">Designer F</p>
                            </div>
                        </button>
                        <button class="scroll-item w-72 card-hover bg-[#F0F0F0]/5 rounded-2xl overflow-hidden border border-white/10 text-left focus-visible-ring" onclick="openWorkDetail('people', 3)" role="listitem" aria-label="View Empathy Design details">
                            <div class="aspect-square bg-gradient-to-br from-[#B388EB]/30 to-[#D9FF00]/30 flex items-center justify-center">
                                <span class="text-[#1A1A1A] font-bold">Work 3</span>
                            </div>
                            <div class="p-6">
                                <h4 class="font-h4 text-white mb-2" data-en="Empathy Design" data-zh="同理设计">Empathy Design</h4>
                                <p class="text-[#D9FF00] font-medium" data-en="Designer G" data-zh="设计师G">Designer G</p>
                            </div>
                        </button>
                        <button class="scroll-item w-72 card-hover bg-[#F0F0F0]/5 rounded-2xl overflow-hidden border border-white/10 text-left focus-visible-ring" onclick="openWorkDetail('people', 4)" role="listitem" aria-label="View Social Impact details">
                            <div class="aspect-square bg-gradient-to-br from-[#D9FF00]/30 to-[#B388EB]/30 flex items-center justify-center">
                                <span class="text-[#1A1A1A] font-bold">Work 4</span>
                            </div>
                            <div class="p-6">
                                <h4 class="font-h4 text-white mb-2" data-en="Social Impact" data-zh="社会影响">Social Impact</h4>
                                <p class="text-[#D9FF00] font-medium" data-en="Designer H" data-zh="设计师H">Designer H</p>
                            </div>
                        </button>
                    </div>
                </div>
                
                <div class="hidden md:grid md:grid-cols-2 lg:grid-cols-4 gap-6" role="list" aria-label="Nice Voice works">
                    <button class="card-hover bg-[#F0F0F0]/5 rounded-2xl overflow-hidden border border-white/10 text-left focus-visible-ring" onclick="openWorkDetail('voice', 1)" role="listitem" aria-label="View Human Connection details">
                        <div class="aspect-square bg-gradient-to-br from-[#B388EB]/30 to-[#D9FF00]/30 flex items-center justify-center">
                            <span class="text-[#1A1A1A] font-bold">Work 1</span>
                        </div>
                        <div class="p-6">
                            <h4 class="font-h4 text-white mb-2" data-en="Human Connection" data-zh="人际连接">Human Connection</h4>
                            <p class="text-[#D9FF00] font-medium" data-en="Designer E" data-zh="设计师E">Designer E</p>
                        </div>
                    </button>
                    <button class="card-hover bg-[#F0F0F0]/5 rounded-2xl overflow-hidden border border-white/10 text-left focus-visible-ring" onclick="openWorkDetail('people', 2)" role="listitem" aria-label="View Community Bond details">
                        <div class="aspect-square bg-gradient-to-br from-[#D9FF00]/30 to-[#B388EB]/30 flex items-center justify-center">
                            <span class="text-[#1A1A1A] font-bold">Work 2</span>
                        </div>
                        <div class="p-6">
                            <h4 class="font-h4 text-white mb-2" data-en="Community Bond" data-zh="社区纽带">Community Bond</h4>
                            <p class="text-[#D9FF00] font-medium" data-en="Designer F" data-zh="设计师F">Designer F</p>
                        </div>
                    </button>
                    <button class="card-hover bg-[#F0F0F0]/5 rounded-2xl overflow-hidden border border-white/10 text-left focus-visible-ring" onclick="openWorkDetail('people', 3)" role="listitem" aria-label="View Empathy Design details">
                        <div class="aspect-square bg-gradient-to-br from-[#B388EB]/30 to-[#D9FF00]/30 flex items-center justify-center">
                            <span class="text-[#1A1A1A] font-bold">Work 3</span>
                        </div>
                        <div class="p-6">
                            <h4 class="font-h4 text-white mb-2" data-en="Empathy Design" data-zh="同理设计">Empathy Design</h4>
                            <p class="text-[#D9FF00] font-medium" data-en="Designer G" data-zh="设计师G">Designer G</p>
                        </div>
                    </button>
                    <button class="card-hover bg-[#F0F0F0]/5 rounded-2xl overflow-hidden border border-white/10 text-left focus-visible-ring" onclick="openWorkDetail('people', 4)" role="listitem" aria-label="View Social Impact details">
                        <div class="aspect-square bg-gradient-to-br from-[#D9FF00]/30 to-[#B388EB]/30 flex items-center justify-center">
                            <span class="text-[#1A1A1A] font-bold">Work 4</span>
                        </div>
                        <div class="p-6">
                            <h4 class="font-h4 text-white mb-2" data-en="Social Impact" data-zh="社会影响">Social Impact</h4>
                            <p class="text-[#D9FF00] font-medium" data-en="Designer H" data-zh="设计师H">Designer H</p>
                        </div>
                    </button>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Nice Partner Section -->
    <section id="nice-partner" class="py-20 md:py-32 bg-standard relative overflow-hidden">
        <div class="content-max-width mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
            <div class="fade-in-up">
                <div class="flex items-center gap-4 mb-12">
                    <div class="square-dot"></div>
                    <h2 class="font-h2 text-white">Nice Partner</h2>
                </div>
                
                <div class="md:hidden">
                    <div class="scroll-container flex gap-6 pb-4" role="list" aria-label="Nice Partner works">
                        <button class="scroll-item w-72 card-hover bg-[#F0F0F0]/5 rounded-2xl overflow-hidden border border-white/10 text-left focus-visible-ring" onclick="openWorkDetail('partner', 1)" role="listitem" aria-label="View Tech Synergy details">
                            <div class="aspect-square bg-gradient-to-br from-[#B388EB]/30 to-[#D9FF00]/30 flex items-center justify-center">
                                <span class="text-[#1A1A1A] font-bold">Work 1</span>
                            </div>
                            <div class="p-6">
                                <h4 class="font-h4 text-white mb-2" data-en="Tech Synergy" data-zh="技术协同">Tech Synergy</h4>
                                <p class="text-[#D9FF00] font-medium" data-en="Designer I" data-zh="设计师I">Designer I</p>
                            </div>
                        </button>
                        <button class="scroll-item w-72 card-hover bg-[#F0F0F0]/5 rounded-2xl overflow-hidden border border-white/10 text-left focus-visible-ring" onclick="openWorkDetail('partner', 2)" role="listitem" aria-label="View Collaborative Creation details">
                            <div class="aspect-square bg-gradient-to-br from-[#D9FF00]/30 to-[#B388EB]/30 flex items-center justify-center">
                                <span class="text-[#1A1A1A] font-bold">Work 2</span>
                            </div>
                            <div class="p-6">
                                <h4 class="font-h4 text-white mb-2" data-en="Collaborative Creation" data-zh="协作创造">Collaborative Creation</h4>
                                <p class="text-[#D9FF00] font-medium" data-en="Designer J" data-zh="设计师J">Designer J</p>
                            </div>
                        </button>
                        <button class="scroll-item w-72 card-hover bg-[#F0F0F0]/5 rounded-2xl overflow-hidden border border-white/10 text-left focus-visible-ring" onclick="openWorkDetail('partner', 3)" role="listitem" aria-label="View Innovation Partnership details">
                            <div class="aspect-square bg-gradient-to-br from-[#B388EB]/30 to-[#D9FF00]/30 flex items-center justify-center">
                                <span class="text-[#1A1A1A] font-bold">Work 3</span>
                            </div>
                            <div class="p-6">
                                <h4 class="font-h4 text-white mb-2" data-en="Innovation Partnership" data-zh="创新伙伴">Innovation Partnership</h4>
                                <p class="text-[#D9FF00] font-medium" data-en="Designer K" data-zh="设计师K">Designer K</p>
                            </div>
                        </button>
                        <button class="scroll-item w-72 card-hover bg-[#F0F0F0]/5 rounded-2xl overflow-hidden border border-white/10 text-left focus-visible-ring" onclick="openWorkDetail('partner', 4)" role="listitem" aria-label="View Future Alliance details">
                            <div class="aspect-square bg-gradient-to-br from-[#D9FF00]/30 to-[#B388EB]/30 flex items-center justify-center">
                                <span class="text-[#1A1A1A] font-bold">Work 4</span>
                            </div>
                            <div class="p-6">
                                <h4 class="font-h4 text-white mb-2" data-en="Future Alliance" data-zh="未来联盟">Future Alliance</h4>
                                <p class="text-[#D9FF00] font-medium" data-en="Designer L" data-zh="设计师L">Designer L</p>
                            </div>
                        </button>
                    </div>
                </div>
                
                <div class="hidden md:grid md:grid-cols-2 lg:grid-cols-4 gap-6" role="list" aria-label="Nice Partner works">
                    <button class="card-hover bg-[#F0F0F0]/5 rounded-2xl overflow-hidden border border-white/10 text-left focus-visible-ring" onclick="openWorkDetail('partner', 1)" role="listitem" aria-label="View Tech Synergy details">
                        <div class="aspect-square bg-gradient-to-br from-[#B388EB]/30 to-[#D9FF00]/30 flex items-center justify-center">
                            <span class="text-[#1A1A1A] font-bold">Work 1</span>
                        </div>
                        <div class="p-6">
                            <h4 class="font-h4 text-white mb-2" data-en="Tech Synergy" data-zh="技术协同">Tech Synergy</h4>
                            <p class="text-[#D9FF00] font-medium" data-en="Designer I" data-zh="设计师I">Designer I</p>
                        </div>
                    </button>
                    <button class="card-hover bg-[#F0F0F0]/5 rounded-2xl overflow-hidden border border-white/10 text-left focus-visible-ring" onclick="openWorkDetail('partner', 2)" role="listitem" aria-label="View Collaborative Creation details">
                        <div class="aspect-square bg-gradient-to-br from-[#D9FF00]/30 to-[#B388EB]/30 flex items-center justify-center">
                            <span class="text-[#1A1A1A] font-bold">Work 2</span>
                        </div>
                        <div class="p-6">
                            <h4 class="font-h4 text-white mb-2" data-en="Collaborative Creation" data-zh="协作创造">Collaborative Creation</h4>
                            <p class="text-[#D9FF00] font-medium" data-en="Designer J" data-zh="设计师J">Designer J</p>
                        </div>
                    </button>
                    <button class="card-hover bg-[#F0F0F0]/5 rounded-2xl overflow-hidden border border-white/10 text-left focus-visible-ring" onclick="openWorkDetail('partner', 3)" role="listitem" aria-label="View Innovation Partnership details">
                        <div class="aspect-square bg-gradient-to-br from-[#B388EB]/30 to-[#D9FF00]/30 flex items-center justify-center">
                            <span class="text-[#1A1A1A] font-bold">Work 3</span>
                        </div>
                        <div class="p-6">
                            <h4 class="font-h4 text-white mb-2" data-en="Innovation Partnership" data-zh="创新伙伴">Innovation Partnership</h4>
                            <p class="text-[#D9FF00] font-medium" data-en="Designer K" data-zh="设计师K">Designer K</p>
                        </div>
                    </button>
                    <button class="card-hover bg-[#F0F0F0]/5 rounded-2xl overflow-hidden border border-white/10 text-left focus-visible-ring" onclick="openWorkDetail('partner', 4)" role="listitem" aria-label="View Future Alliance details">
                        <div class="aspect-square bg-gradient-to-br from-[#D9FF00]/30 to-[#B388EB]/30 flex items-center justify-center">
                            <span class="text-[#1A1A1A] font-bold">Work 4</span>
                        </div>
                        <div class="p-6">
                            <h4 class="font-h4 text-white mb-2" data-en="Future Alliance" data-zh="未来联盟">Future Alliance</h4>
                            <p class="text-[#D9FF00] font-medium" data-en="Designer L" data-zh="设计师L">Designer L</p>
                        </div>
                    </button>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Footer -->
    <footer class="py-16 bg-standard border-t border-white/10">
        <div class="content-max-width mx-auto px-4 sm:px-6 lg:px-8">
            <div class="fade-in-up">
                <div class="flex flex-col md:flex-row items-center justify-between gap-8 mb-12 pb-12 border-b border-white/10">
                    <div class="text-center md:text-left">
                        <p class="font-bold text-white text-base md:text-lg">Salone del Mobile.Milano</p>
                    </div>
                    <div class="text-center">
                        <p class="font-bold text-white text-base md:text-lg">TONGJI UNIVERSITY</p>
                        <p class="font-bold text-[#F0F0F0] text-xs md:text-sm">COLLEGE OF DESIGN AND INNOVATION</p>
                    </div>
                    <div class="text-center md:text-right">
                        <p class="font-bold text-white text-base md:text-lg">TONGJI UNIVERSITY</p>
                        <p class="font-bold text-[#F0F0F0] text-xs md:text-sm">SHANGHAI INTERNATIONAL COLLEGE OF DESIGN AND INNOVATION</p>
                    </div>
                </div>
                
                <div class="text-center">
                    <p class="text-[#F0F0F0] text-sm">© 2026 NICE TOGETHER. All Rights Reserved.</p>
                    <div class="mt-4 flex justify-center gap-6">
                        <a href="#" class="text-[#F0F0F0] hover:text-[#D9FF00] transition-colors text-sm focus-visible-ring rounded" data-en="Contact" data-zh="联系我们">Contact</a>
                        <a href="#" class="text-[#F0F0F0] hover:text-[#D9FF00] transition-colors text-sm focus-visible-ring rounded" data-en="Instagram" data-zh="Instagram">Instagram</a>
                        <a href="#" class="text-[#F0F0F0] hover:text-[#D9FF00] transition-colors text-sm focus-visible-ring rounded" data-en="WeChat" data-zh="微信">WeChat</a>
                    </div>
                </div>
            </div>
        </div>
    </footer>
    
    <!-- Work Detail Modal -->
    <div id="workModal" class="fixed inset-0 z-50 hidden" role="dialog" aria-modal="true" aria-labelledby="workModalTitle">
        <div class="modal-overlay absolute inset-0" onclick="closeWorkDetail()"></div>
        <div class="relative z-10 h-full overflow-y-auto">
            <div class="min-h-screen py-12 px-4">
                <div class="max-w-3xl mx-auto">
                    <button onclick="closeWorkDetail()" class="btn-hover mb-8 text-white flex items-center gap-2 focus-visible-ring rounded" aria-label="Close work details">
                        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" aria-hidden="true">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 19l-7-7m0 0l7-7m-7 7h18"/>
                        </svg>
                        <span data-en="Back" data-zh="返回">Back</span>
                    </button>
                    
                    <div class="bg-[#1A1A1A] rounded-3xl overflow-hidden border border-white/10">
                        <div class="aspect-video bg-gradient-to-br from-[#B388EB] to-[#D9FF00] flex items-center justify-center">
                            <span class="text-[#1A1A1A] font-bold text-2xl" data-en="Work Detail Image" data-zh="作品详情图片">Work Detail Image</span>
                        </div>
                        <div class="p-8">
                            <h2 id="workModalTitle" class="font-h2 text-white mb-4" data-en="Work Title" data-zh="作品名称">Work Title</h2>
                            <p class="text-[#D9FF00] font-bold mb-6" data-en="Designer Name" data-zh="设计师姓名">Designer Name</p>
                            <div class="text-[#F0F0F0] leading-relaxed space-y-4">
                                <p data-en="This is a detailed description of the work, including its design concept, inspiration, materials, and production process. It explores the relationship between humanity, technology, and the environment." data-zh="这是作品的详细描述，包括设计理念、灵感来源、材料和制作工艺。它探索了人类、技术与环境之间的关系。">This is a detailed description of the work, including its design concept, inspiration, materials, and production process. It explores the relationship between humanity, technology, and the environment.</p>
                                <p data-en="Design concept and inspiration: This work draws inspiration from nature and traditional craftsmanship, aiming to create harmony between humans and their surroundings." data-zh="设计理念与灵感：本作品从自然和传统工艺中汲取灵感，旨在创造人类与环境之间的和谐。">Design concept and inspiration: This work draws inspiration from nature and traditional craftsmanship, aiming to create harmony between humans and their surroundings.</p>
                                <p data-en="Materials and production process: Using sustainable materials and innovative techniques, this piece demonstrates a commitment to environmental responsibility." data-zh="材料与制作工艺：采用可持续材料和创新技术，这件作品体现了对环境责任的承诺。">Materials and production process: Using sustainable materials and innovative techniques, this piece demonstrates a commitment to environmental responsibility.</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <script>
        let currentLang = localStorage.getItem('lang') || 'en';
        
        const worksData = {
            planet: [
                { title: { en: 'Eco Design', zh: '生态设计' }, designer: { en: 'Designer A', zh: '设计师A' } },
                { title: { en: 'Nature Harmony', zh: '自然和谐' }, designer: { en: 'Designer B', zh: '设计师B' } },
                { title: { en: 'Sustainable Future', zh: '可持续未来' }, designer: { en: 'Designer C', zh: '设计师C' } },
                { title: { en: 'Earth Care', zh: '地球关怀' }, designer: { en: 'Designer D', zh: '设计师D' } }
            ],
            voice: [
                { title: { en: 'Human Connection', zh: '人际连接' }, designer: { en: 'Designer E', zh: '设计师E' } },
                { title: { en: 'Community Bond', zh: '社区纽带' }, designer: { en: 'Designer F', zh: '设计师F' } },
                { title: { en: 'Empathy Design', zh: '同理设计' }, designer: { en: 'Designer G', zh: '设计师G' } },
                { title: { en: 'Social Impact', zh: '社会影响' }, designer: { en: 'Designer H', zh: '设计师H' } }
            ],
            partner: [
                { title: { en: 'Tech Synergy', zh: '技术协同' }, designer: { en: 'Designer I', zh: '设计师I' } },
                { title: { en: 'Collaborative Creation', zh: '协作创造' }, designer: { en: 'Designer J', zh: '设计师J' } },
                { title: { en: 'Innovation Partnership', zh: '创新伙伴' }, designer: { en: 'Designer K', zh: '设计师K' } },
                { title: { en: 'Future Alliance', zh: '未来联盟' }, designer: { en: 'Designer L', zh: '设计师L' } }
            ]
        };
        
        function toggleLanguage() {
            currentLang = currentLang === 'en' ? 'zh' : 'en';
            localStorage.setItem('lang', currentLang);
            updateLanguage();
        }
        
        function updateLanguage() {
            const langText = currentLang === 'en' ? '中文' : 'EN';
            document.getElementById('langText').textContent = langText;
            document.getElementById('langTextMobile').textContent = langText;
            
            document.querySelectorAll('[data-en]').forEach(el => {
                el.textContent = el.getAttribute(`data-${currentLang}`);
            });
            
            document.querySelectorAll('.about-text-en').forEach(el => {
                if (currentLang === 'en') {
                    el.classList.remove('hidden');
                } else {
                    el.classList.add('hidden');
                }
            });
            
            document.querySelectorAll('.about-text-zh').forEach(el => {
                if (currentLang === 'zh') {
                    el.classList.remove('hidden');
                } else {
                    el.classList.add('hidden');
                }
            });
            
            document.documentElement.lang = currentLang;
        }
        
        const mobileMenuBtn = document.getElementById('mobileMenuBtn');
        const mobileMenu = document.getElementById('mobileMenu');
        
        mobileMenuBtn.addEventListener('click', () => {
            const isHidden = mobileMenu.classList.toggle('hidden');
            mobileMenuBtn.setAttribute('aria-expanded', !isHidden);
        });
        
        mobileMenu.querySelectorAll('a').forEach(link => {
            link.addEventListener('click', () => {
                mobileMenu.classList.add('hidden');
                mobileMenuBtn.setAttribute('aria-expanded', 'false');
            });
        });
        
        const navbar = document.getElementById('navbar');
        
        window.addEventListener('scroll', () => {
            if (window.scrollY > 50) {
                navbar.classList.add('nav-sticky');
            } else {
                navbar.classList.remove('nav-sticky');
            }
        });
        
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
        
        document.querySelectorAll('.fade-in-up').forEach(el => {
            observer.observe(el);
        });
        
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });
        
        function openWorkDetail(section, index) {
            const work = worksData[section][index - 1];
            if (work) {
                const modal = document.getElementById('workModal');
                const titleEl = modal.querySelector('#workModalTitle');
                const designerEl = modal.querySelector('p.text-\\[\\#D9FF00\\]');
                
                titleEl.textContent = work.title[currentLang];
                designerEl.textContent = work.designer[currentLang];
                
                modal.classList.remove('hidden');
                document.body.style.overflow = 'hidden';
                modal.focus();
            }
        }
        
        function closeWorkDetail() {
            document.getElementById('workModal').classList.add('hidden');
            document.body.style.overflow = '';
        }
        
        document.getElementById('langToggle').addEventListener('click', toggleLanguage);
        document.getElementById('langToggleMobile').addEventListener('click', toggleLanguage);
        
        updateLanguage();
        
        document.addEventListener('keydown', (e) => {
            if (e.key === 'Escape') {
                closeWorkDetail();
            }
        });
    </script>
</body>
</html>
