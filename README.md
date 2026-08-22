<html lang="zh-TW" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Lin & Li | WEDDING</title>
    
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    
    <!-- Google Fonts: Cormorant Garamond & Noto Serif TC -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Alex+Brush&family=Cormorant+Garamond:ital,wght@0,400;0,500;0,600;0,700;1,400&family=Noto+Serif+TC:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    
    <!-- Lucide Icons CDN -->
    <script src="https://unpkg.com/lucide@latest"></script>

    <!-- Canvas Confetti for Form Submission Effect -->
    <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>


    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        morandi: {
                            warm: '#d4a373',      // 暖陽金色
                            sage: '#8da399',      // 鼠尾草綠
                            sand: '#e8dbce',      // 暖砂色
                            blush: '#e0b8b1',     // 莫蘭迪粉
                            dark: '#3d342f',      // 深咖暖木
                            ivory: '#fdfbf7',     // 奶油白
                            card: '#ffffff',      // 卡片純白
                        }
                    },
                    fontFamily: {
                        cormorant: ['"Cormorant Garamond"', 'serif'],
                        serif: ['"Noto Serif TC"', 'serif'],
                        script: ['"Alex Brush"', 'cursive'],
                    },
                    boxShadow: {
                        'soft-glow': '0 10px 30px -5px rgba(212, 163, 115, 0.18), 0 4px 12px -2px rgba(141, 163, 153, 0.12)',
                        'card-float': '0 20px 40px -15px rgba(61, 52, 47, 0.07)',
                    }
                }
            }
        }
    </script>

    <style>
        body {
            font-family: 'Noto Serif TC', serif;
            background-color: #fdfbf7;
            color: #3d342f;
            overflow-x: hidden;
        }

        /* 滾動條樣式優化 */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #fdfbf7;
        }
        ::-webkit-scrollbar-thumb {
            background: #d4a373;
            border-radius: 4px;
        }

        /* 柔和微光效果 */
        .glowing-card {
            background: rgba(255, 255, 255, 0.92);
            backdrop-filter: blur(12px);
            border: 1px solid rgba(255, 255, 255, 0.9);
            box-shadow: 0 14px 35px -5px rgba(212, 163, 115, 0.15), 0 6px 15px -3px rgba(0, 0, 0, 0.03);
        }

        /* 背景流光粒子動畫 */
        @keyframes pulseGlow {
            0%, 100% { opacity: 0.4; transform: scale(1); }
            50% { opacity: 0.7; transform: scale(1.05); }
        }
        .bg-glow-1 {
            animation: pulseGlow 8s infinite ease-in-out;
        }
        .bg-glow-2 {
            animation: pulseGlow 10s infinite ease-in-out 2s;
        }
    </style>
</head>
<body class="antialiased">

    <!-- 1. 頂端固定毛玻璃導覽列 -->
        <nav class="fixed top-0 left-0 right-0 z-50 backdrop-blur-md bg-white/70 border-b border-white/40 shadow-sm transition-all duration-300" id="navbar">
            <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="flex items-center justify-between h-20">
                    <!-- Logo / Couple Initials -->
                    <a href="#" class="flex items-center space-x-2 group">
                        <span class="font-cormorant text-2xl sm:text-3xl font-semibold tracking-wider text-morandi-warm group-hover:opacity-80 transition">Lin & Li</span>
                        <span class="w-1.5 h-1.5 rounded-full bg-morandi-sage inline-block"></span>
                    </a>
        
                    <!-- Desktop Menu -->
                    <div class="hidden md:flex items-center space-x-8 text-sm font-medium tracking-widest text-morandi-dark">
                        <a href="#countdown" class="hover:text-morandi-warm transition duration-200 py-1 border-b-2 border-transparent hover:border-morandi-warm">倒數時刻</a>
                        <a href="#details" class="hover:text-morandi-warm transition duration-200 py-1 border-b-2 border-transparent hover:border-morandi-warm">婚禮詳情</a>
                        <a href="#rsvp" class="px-5 py-2.5 rounded-full bg-morandi-warm text-white font-medium hover:bg-[#c29263] transition shadow-sm hover:shadow-md">出席回函</a>
                    </div>
        
                    <!-- Mobile Menu Button -->
                    <div class="md:hidden flex items-center">
                        <button id="mobile-menu-btn" class="p-2 rounded-md text-morandi-dark hover:text-morandi-warm focus:outline-none">
                            <i data-lucide="menu" class="w-6 h-6"></i>
                        </button>
                    </div>
                </div>
            </div>
        
            <!-- Mobile Menu Dropdown -->
            <div id="mobile-menu" class="hidden md:hidden bg-white/95 backdrop-blur-lg border-b border-stone-100 px-4 pt-2 pb-6 space-y-3 shadow-lg">
                <a href="#countdown" class="block px-3 py-2 rounded-md text-base text-morandi-dark hover:bg-morandi-ivory hover:text-morandi-warm">倒數時刻</a>
                <a href="#details" class="block px-3 py-2 rounded-md text-base text-morandi-dark hover:bg-morandi-ivory hover:text-morandi-warm">婚禮詳情</a>
                <a href="#rsvp" class="block text-center px-4 py-3 rounded-full bg-morandi-warm text-white font-medium hover:bg-[#c29263] mt-2">出席回函</a>
            </div>
        </nav>
        
        <!-- Hero Banner Section -->
        <section class="relative min-h-screen flex items-center justify-center pt-20 overflow-hidden bg-gradient-to-b from-[#f9f5f0] via-morandi-ivory to-white">
            <!-- Floating Soft Ambient Lights -->
            <div class="absolute top-1/4 left-10 w-72 h-72 rounded-full bg-morandi-warm/15 filter blur-3xl bg-glow-1"></div>
            <div class="absolute bottom-1/4 right-10 w-96 h-96 rounded-full bg-morandi-sage/15 filter blur-3xl bg-glow-2"></div>
        
            <div class="relative z-10 text-center px-4 max-w-4xl mx-auto py-12">
                <!-- Subtitle / Soul Slogan -->
                <p class="font-cormorant italic text-xl sm:text-3xl text-morandi-warm tracking-[0.25em] font-semibold uppercase mb-2">
                    WEDDING
                </p>
                <h2 class="text-xs sm:text-sm tracking-[0.3em] text-morandi-dark/70 uppercase mb-8">
                    誠摯邀請您見證我們的幸福時刻
                </h2>
        
                <!-- Main Title / Names -->
                <div class="my-6 space-y-2">
                    <h1 class="font-cormorant text-5xl sm:text-7xl lg:text-8xl font-light text-morandi-dark tracking-wide">
                        Lin <span class="font-script text-morandi-warm text-4xl sm:text-6xl mx-2">&</span> Li
                    </h1>
                    <p class="text-base sm:text-lg text-morandi-dark/80 tracking-widest pt-2">
                        林 義哲 <span class="mx-2 text-morandi-warm">|</span> 李 念蓁
                    </p>
                </div>
        
                <!-- Cover Image Frame -->
                <div class="my-8 mx-auto max-w-xs sm:max-w-md overflow-hidden rounded-[2rem] p-2.5 bg-white/80 backdrop-blur-md border border-white/90 shadow-card-float transform hover:scale-[1.01] transition duration-500">
                    <div class="overflow-hidden rounded-[1.5rem] relative aspect-[3/4]">
                        <img src="https://i.postimg.cc/dtxYRMX1/1A1A7214-2.jpg" 
                             alt="Lin & Li Wedding Cover" 
                             class="w-full h-full object-cover object-center shadow-inner"
                             onerror="this.onerror=null; this.src='https://placehold.co/800x1000/e8dbce/3d342f?text=Lin+%26+Li+Wedding';">
                    </div>
                </div>
        
                <!-- Preface / Invitation Message -->
                <div class="my-8 max-w-xl mx-auto p-6 sm:p-8 rounded-3xl bg-white/70 backdrop-blur-md border border-white/90 shadow-soft-glow text-center text-morandi-dark leading-relaxed">
                    <p class="font-medium text-morandi-warm text-base sm:text-lg mb-3">親愛的家人朋友們 :</p>
                    <p class="text-sm sm:text-base text-morandi-dark/90 mb-3">
                        經過5年時間的"慢跑" ，我們做了重要的決定，就是 ~ 我們要結婚啦 !
                    </p>
                    <p class="text-sm sm:text-base text-morandi-dark/80 mb-5">
                        誠摯地邀請最重要的你們前來參加我們的幸福饗宴，一同分享及見證這份喜悅與幸福，讓我們的大囍之日更有意義 !
                    </p>
                    <div class="pt-4 border-t border-stone-200/60 space-y-2">
                        <p class="text-xs sm:text-sm text-morandi-dark/70">
                            為了方便我們統計出席人數與安排座位，邀請您動動手指幫我們填寫以下資訊
                        </p>
                        <p class="text-sm sm:text-base font-medium text-morandi-warm">期待您的蒞臨❤</p>
                        <p class="font-medium text-base sm:text-lg text-morandi-dark tracking-wider pt-1">義哲 & 念蓁 敬邀</p>
                    </div>
                </div>
        
                <!-- Decorative Fine Line -->
                <div class="w-24 h-[1px] bg-gradient-to-r from-transparent via-morandi-warm/60 to-transparent mx-auto my-8"></div>
        
                <!-- Date & Location Brief -->
                <div class="inline-flex flex-col sm:flex-row items-center justify-center gap-2 sm:gap-6 text-sm sm:text-base text-morandi-dark/80 font-medium tracking-widest bg-white/50 backdrop-blur-sm px-6 py-3 rounded-full border border-white/60 shadow-sm">
                    <div class="flex items-center gap-2">
                        <i data-lucide="calendar" class="w-4 h-4 text-morandi-warm"></i>
                        <span>2026 年 11 月 22 日 (日)</span>
                    </div>
                    <span class="hidden sm:inline text-morandi-sage">•</span>
                    <div class="flex items-center gap-2">
                        <i data-lucide="map-pin" class="w-4 h-4 text-morandi-warm"></i>
                        <span>雲林縣大埤鄉憶滿樓婚宴會館</span>
                    </div>
                </div>
            </div>
        
            <!-- Scroll Down Indicator -->
            <a href="#countdown" class="absolute bottom-8 left-1/2 -translate-x-1/2 flex flex-col items-center gap-2 text-morandi-dark/50 hover:text-morandi-warm transition">
                <span class="text-xs tracking-widest uppercase font-cormorant">Scroll</span>
                <i data-lucide="chevron-down" class="w-4 h-4 animate-bounce"></i>
            </a>
        </section>
        
        <!-- 2. 計時器視覺 (核心亮點需求) -->
        <section id="countdown" class="py-20 relative bg-morandi-ivory border-y border-stone-200/50">
            <div class="max-w-5xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
                
                <div class="mb-12">
                    <span class="font-script text-3xl sm:text-4xl text-morandi-warm block mb-1">Counting Down</span>
                    <h2 class="font-cormorant text-2xl sm:text-3xl font-medium tracking-widest text-morandi-dark uppercase">
                        倒數我們的神聖時刻
                    </h2>
                    <div class="w-12 h-[1px] bg-morandi-sage mx-auto mt-4"></div>
                </div>
        
                <!-- 藝術感倒數計時器容器 -->
                <div class="inline-flex flex-wrap sm:flex-nowrap items-center justify-center gap-3 sm:gap-0 p-4 sm:p-6 rounded-3xl bg-stone-100/50 border border-white/60 shadow-inner">
                    
                    <!-- 卡片 1: 天 (Days) -->
                    <div class="flex flex-col items-center min-w-[85px] sm:min-w-[125px] p-4 sm:p-6 rounded-2xl glowing-card transform transition hover:-translate-y-1">
                        <span id="cd-days" class="font-cormorant text-4xl sm:text-6xl font-semibold text-morandi-warm tracking-tight">00</span>
                        <span class="text-xs sm:text-sm tracking-widest text-morandi-sage font-medium mt-2">DAYS / 天</span>
                    </div>
        
                    <!-- 垂直細線 1 -->
                    <div class="hidden sm:block w-[1px] h-16 bg-gradient-to-b from-transparent via-morandi-warm/40 to-transparent mx-3 sm:mx-6"></div>
        
                    <!-- 卡片 2: 時 (Hours) -->
                    <div class="flex flex-col items-center min-w-[85px] sm:min-w-[125px] p-4 sm:p-6 rounded-2xl glowing-card transform transition hover:-translate-y-1">
                        <span id="cd-hours" class="font-cormorant text-4xl sm:text-6xl font-semibold text-morandi-dark tracking-tight">00</span>
                        <span class="text-xs sm:text-sm tracking-widest text-morandi-sage font-medium mt-2">HOURS / 時</span>
                    </div>
        
                    <!-- 垂直細線 2 -->
                    <div class="hidden sm:block w-[1px] h-16 bg-gradient-to-b from-transparent via-morandi-warm/40 to-transparent mx-3 sm:mx-6"></div>
        
                    <!-- 卡片 3: 分 (Minutes) -->
                    <div class="flex flex-col items-center min-w-[85px] sm:min-w-[125px] p-4 sm:p-6 rounded-2xl glowing-card transform transition hover:-translate-y-1">
                        <span id="cd-minutes" class="font-cormorant text-4xl sm:text-6xl font-semibold text-morandi-dark tracking-tight">00</span>
                        <span class="text-xs sm:text-sm tracking-widest text-morandi-sage font-medium mt-2">MINS / 分</span>
                    </div>
        
                    <!-- 垂直細線 3 -->
                    <div class="hidden sm:block w-[1px] h-16 bg-gradient-to-b from-transparent via-morandi-warm/40 to-transparent mx-3 sm:mx-6"></div>
        
                    <!-- 卡片 4: 秒 (Seconds) -->
                    <div class="flex flex-col items-center min-w-[85px] sm:min-w-[125px] p-4 sm:p-6 rounded-2xl glowing-card transform transition hover:-translate-y-1">
                        <span id="cd-seconds" class="font-cormorant text-4xl sm:text-6xl font-semibold text-morandi-warm tracking-tight">00</span>
                        <span class="text-xs sm:text-sm tracking-widest text-morandi-sage font-medium mt-2">SECS / 秒</span>
                    </div>
        
                </div>
        
                <!-- 倒數下方暖心小字標語 -->
                <p class="mt-8 text-xs sm:text-sm text-morandi-dark/60 tracking-wider">
                    每一秒的遞減，都是我們向永恆幸福靠近的腳步
                </p>
        
            </div>
        </section>
        
        <!-- Wedding Details & Location Section -->
        <section id="details" class="py-24 bg-white relative border-b border-stone-200/50">
            <div class="max-w-5xl mx-auto px-4 sm:px-6 lg:px-8">
                
                <div class="text-center mb-16">
                    <span class="font-script text-3xl text-morandi-warm">Wedding Details</span>
                    <h2 class="font-cormorant text-3xl font-light tracking-widest text-morandi-dark uppercase">婚禮資訊與流程</h2>
                    <div class="w-12 h-[1px] bg-morandi-sage mx-auto mt-3"></div>
                </div>
        
                <!-- Details Info Cards Grid -->
                <div class="grid md:grid-cols-2 gap-8 mb-16 max-w-3xl mx-auto">
                    <!-- Date & Time -->
                    <div class="bg-white p-8 rounded-3xl border border-stone-100 shadow-sm text-center">
                        <div class="w-12 h-12 mx-auto mb-4 rounded-2xl bg-morandi-ivory flex items-center justify-center text-morandi-warm">
                            <i data-lucide="calendar-heart" class="w-6 h-6"></i>
                        </div>
                        <h3 class="font-medium text-morandi-dark mb-2">宴席日期</h3>
                        <p class="text-sm text-morandi-dark/80">2026 年 11 月 22 日 (星期日)</p>
                        <p class="text-xs text-morandi-sage mt-1">中午 12:00 賓客入座</p>
                    </div>
        
                    <!-- Location -->
                    <div class="bg-white p-8 rounded-3xl border border-stone-100 shadow-sm text-center">
                        <div class="w-12 h-12 mx-auto mb-4 rounded-2xl bg-morandi-ivory flex items-center justify-center text-morandi-warm">
                            <i data-lucide="map-pin" class="w-6 h-6"></i>
                        </div>
                        <h3 class="font-medium text-morandi-dark mb-2">宴會地點</h3>
                        <p class="text-sm text-morandi-dark/80 font-medium">憶滿樓婚宴會館</p>
                        <p class="text-xs text-morandi-sage mt-1">雲林縣大埤鄉北和村信義路20號</p>
                    </div>
                </div>
        
                <!-- 交通與停車資訊 Section -->
                <div class="bg-morandi-ivory/60 rounded-3xl p-8 sm:p-12 border border-stone-200/60 shadow-soft-glow mb-12">
                    <div class="text-center mb-10">
                        <span class="font-script text-2xl text-morandi-warm">Transportation</span>
                        <h3 class="font-cormorant text-2xl font-semibold text-morandi-dark mt-1">交通與停車指南</h3>
                        <p class="text-xs text-morandi-sage mt-1">憶滿樓婚宴會館 • 雲林縣大埤鄉北和村信義路20號</p>
                    </div>
        
                    <div class="grid md:grid-cols-3 gap-6">
                        <!-- 自行開車 & 停車資訊 -->
                        <div class="bg-white p-6 rounded-2xl border border-stone-100 shadow-sm flex flex-col justify-between">
                            <div>
                                <div class="flex items-center gap-3 mb-3 text-morandi-warm">
                                    <div class="w-10 h-10 rounded-xl bg-morandi-ivory flex items-center justify-center">
                                        <i data-lucide="car" class="w-5 h-5"></i>
                                    </div>
                                    <h4 class="font-medium text-morandi-dark text-base">自行開車 / 停車</h4>
                                </div>
                                <ul class="text-xs text-morandi-dark/80 space-y-2 leading-relaxed">
                                    <li class="flex items-start gap-1.5">
                                        <span class="text-morandi-warm font-bold">•</span>
                                        <span>國道一號下<strong>斗南交流道</strong>，接台1線往大埤方向行駛約 8-10 分鐘即可抵達。</span>
                                    </li>
                                    <li class="flex items-start gap-1.5">
                                        <span class="text-morandi-warm font-bold">•</span>
                                        <span>會館附設<strong>賓客專屬免費停車場</strong>及大型遊覽車停車區，停車十分便利。</span>
                                    </li>
                                </ul>
                            </div>
                        </div>
        
                        <!-- 台鐵火車 -->
                        <div class="bg-white p-6 rounded-2xl border border-stone-100 shadow-sm flex flex-col justify-between">
                            <div>
                                <div class="flex items-center gap-3 mb-3 text-morandi-warm">
                                    <div class="w-10 h-10 rounded-xl bg-morandi-ivory flex items-center justify-center">
                                        <i data-lucide="train" class="w-5 h-5"></i>
                                    </div>
                                    <h4 class="font-medium text-morandi-dark text-base">搭乘台鐵火車</h4>
                                </div>
                                <ul class="text-xs text-morandi-dark/80 space-y-2 leading-relaxed">
                                    <li class="flex items-start gap-1.5">
                                        <span class="text-morandi-warm font-bold">•</span>
                                        <span>請搭乘台鐵至<strong>「斗南火車站」</strong>下車。</span>
                                    </li>
                                    <li class="flex items-start gap-1.5">
                                        <span class="text-morandi-warm font-bold">•</span>
                                        <span>於站前轉搭計程車，車程約 <strong>10 分鐘</strong>即可輕鬆抵達婚宴會館。</span>
                                    </li>
                                </ul>
                            </div>
                        </div>
        
                        <!-- 台灣高鐵 -->
                        <div class="bg-white p-6 rounded-2xl border border-stone-100 shadow-sm flex flex-col justify-between">
                            <div>
                                <div class="flex items-center gap-3 mb-3 text-morandi-warm">
                                    <div class="w-10 h-10 rounded-xl bg-morandi-ivory flex items-center justify-center">
                                        <i data-lucide="navigation" class="w-5 h-5"></i>
                                    </div>
                                    <h4 class="font-medium text-morandi-dark text-base">搭乘台灣高鐵</h4>
                                </div>
                                <ul class="text-xs text-morandi-dark/80 space-y-2 leading-relaxed">
                                    <li class="flex items-start gap-1.5">
                                        <span class="text-morandi-warm font-bold">•</span>
                                        <span>請搭乘高鐵至<strong>「高鐵雲林站」</strong>下車。</span>
                                    </li>
                                    <li class="flex items-start gap-1.5">
                                        <span class="text-morandi-warm font-bold">•</span>
                                        <span>出站後轉搭計程車或預約接駁，車程約 <strong>25-30 分鐘</strong>抵達。</span>
                                    </li>
                                </ul>
                            </div>
                        </div>
                    </div>
        
                    <!-- Google 地圖按鈕 -->
                    <div class="mt-8 text-center">
                        <a href="https://maps.google.com/?cid=12570166551430556052" target="_blank" rel="noopener noreferrer" class="inline-flex items-center gap-2 px-6 py-3 rounded-full bg-morandi-warm text-white text-xs font-medium hover:bg-[#c29263] transition shadow-md hover:shadow-lg">
                            <i data-lucide="map-pin" class="w-4 h-4"></i>
                            <span>開啟 Google 地圖一鍵導航</span>
                        </a>
                    </div>
                </div>
        
                <!-- Program Timeline -->
                <div class="bg-white rounded-3xl p-8 sm:p-12 border border-stone-100 shadow-soft-glow">
                    <h3 class="font-cormorant text-2xl font-semibold text-center text-morandi-dark mb-8">當日活動流程 / Itinerary</h3>
                    <div class="grid grid-cols-1 sm:grid-cols-3 gap-6 text-center max-w-3xl mx-auto">
                        <div class="p-4 rounded-2xl bg-morandi-ivory/60">
                            <span class="font-cormorant text-xl text-morandi-warm font-semibold block">12:00</span>
                            <span class="text-sm text-morandi-dark font-medium mt-1 block">賓客報到入座</span>
                        </div>
                        <div class="p-4 rounded-2xl bg-morandi-ivory/60">
                            <span class="font-cormorant text-xl text-morandi-warm font-semibold block">12:30</span>
                            <span class="text-sm text-morandi-dark font-medium mt-1 block">午宴盛大開席</span>
                        </div>
                        <div class="p-4 rounded-2xl bg-morandi-ivory/60">
                            <span class="font-cormorant text-xl text-morandi-warm font-semibold block">15:00</span>
                            <span class="text-sm text-morandi-dark font-medium mt-1 block">送客與溫馨合照</span>
                        </div>
                    </div>
                </div>
        
            </div>
        </section>
        
        <!-- 3. 出席回函 RSVP Form Section -->
        <section id="rsvp" class="py-24 bg-white relative">
            <div class="max-w-3xl mx-auto px-4 sm:px-6 lg:px-8">
                
                <div class="text-center mb-12">
                    <span class="font-script text-3xl text-morandi-warm">R.S.V.P</span>
                    <h2 class="font-cormorant text-3xl font-light tracking-widest text-morandi-dark uppercase">出席回函</h2>
                    <p class="text-xs text-morandi-dark/60 mt-2">請於 2026 年 10 月 22 日前填寫，以便我們為您安排最佳席位</p>
                    <div class="w-12 h-[1px] bg-morandi-sage mx-auto mt-3"></div>
                </div>
        
                <!-- Form Card (對接 Google 表單) -->
                <iframe
        			name="submit-frame"
        			id="submit-frame"
        			style="display:none;">
        		</iframe>
        
        		<form
        			id="rsvp-form"
        			method="POST"
        			target="submit-frame"
        			class="bg-morandi-ivory p-8 sm:p-12 rounded-3xl border border-stone-200/60 shadow-card-float space-y-6">
        
        			<input type="hidden"
        				   id="submission-id"
        				   name="submissionId">
                    
                    <!-- 姓名與電話 -->
        			<div class="grid md:grid-cols-2 gap-6">
        				<div>
        					<label class="block text-xs uppercase font-semibold text-morandi-dark tracking-wider mb-2">
        						您的姓名 *
        					</label>
        					<input type="text"
        						   name="name"
        						   required
        						   placeholder="例：張小明"
        						   class="w-full px-4 py-3 rounded-xl border border-stone-200 bg-white focus:outline-none focus:ring-2 focus:ring-morandi-warm/50 text-sm">
        				</div>
        
        				<div>
        					<label class="block text-xs uppercase font-semibold text-morandi-dark tracking-wider mb-2">
        						聯絡電話 *
        					</label>
        					<input type="tel"
        						   name="phone"
        						   required
        						   placeholder="0912-345-678"
        						   class="w-full px-4 py-3 rounded-xl border border-stone-200 bg-white focus:outline-none focus:ring-2 focus:ring-morandi-warm/50 text-sm">
        				</div>
        			</div>
        
        
        			<!-- 是否出席 & 親友關係 -->
        			<div class="grid md:grid-cols-2 gap-6">
        
        				<!-- 是否出席 -->
        				<div>
        					<label class="block text-xs uppercase font-semibold text-morandi-dark tracking-wider mb-2">
        						是否出席婚宴 *
        					</label>
        
        					<div class="space-y-2">
        
        						<label class="flex items-center p-3 rounded-xl border border-stone-200 bg-white cursor-pointer hover:border-morandi-warm transition">
        							<input type="radio"
        								   name="attendance"
        								   value="出席，絕對到場 ! 🎉🥂"
        								   checked
        								   class="accent-[#d4a373] mr-2">
        
        							<span class="text-xs font-medium text-morandi-dark">
        								出席，絕對到場 ! 🎉🥂
        							</span>
        						</label>
        
        						<label class="flex items-center p-3 rounded-xl border border-stone-200 bg-white cursor-pointer hover:border-morandi-warm transition">
        							<input type="radio"
        								   name="attendance"
        								   value="遺憾無法出席，獻上溫馨祝福"
        								   class="accent-[#d4a373] mr-2">
        
        							<span class="text-xs font-medium text-morandi-dark">
        								遺憾無法出席，獻上溫馨祝福
        							</span>
        						</label>
        
        					</div>
        				</div>
        
        
        				<!-- 親友關係 -->
        				<div>
        					<label class="block text-xs uppercase font-semibold text-morandi-dark tracking-wider mb-2">
        						您是哪一方的親友 *
        					</label>
        
        					<div class="space-y-2">
        
        						<label class="flex items-center p-3 rounded-xl border border-stone-200 bg-white cursor-pointer hover:border-morandi-warm transition">
        							<input type="radio"
        								   name="relation"
        								   value="🤵義哲的親友"
        								   checked
        								   class="accent-[#d4a373] mr-2">
        
        							<span class="text-xs font-medium text-morandi-dark">
        								🤵 義哲的親友
        							</span>
        						</label>
        
        						<label class="flex items-center p-3 rounded-xl border border-stone-200 bg-white cursor-pointer hover:border-morandi-warm transition">
        							<input type="radio"
        								   name="relation"
        								   value="👰念蓁的親友"
        								   class="accent-[#d4a373] mr-2">
        
        							<span class="text-xs font-medium text-morandi-dark">
        								👰 念蓁的親友
        							</span>
        						</label>
        
        					</div>
        				</div>
        
        			</div>
        
        
        			<!-- 出席人數 / 素食 / 兒童座椅 -->
        			<div class="grid grid-cols-1 sm:grid-cols-3 gap-4">
        
        				<!-- 出席人數 -->
        				<div>
        					<label class="block text-xs uppercase font-semibold text-morandi-dark tracking-wider mb-2">
        						出席人數
        					</label>
        
        					<select name="guests"
        							class="w-full px-3 py-3 rounded-xl border border-stone-200 bg-white focus:outline-none focus:ring-2 focus:ring-morandi-warm/50 text-xs">
        
        						<option value="1位">1位</option>
        						<option value="2位">2位</option>
        						<option value="3位">3位</option>
        						<option value="4位">4位</option>
        						<option value="5位">5位</option>
        						<option value="6位">6位</option>
        						<option value="7位">7位</option>
        						<option value="8位">8位</option>
        						<option value="9位">9位</option>
        						<option value="10位">10位</option>
        
        					</select>
        				</div>
        
        
        				<!-- 素食需求 -->
        				<div>
        					<label class="block text-xs uppercase font-semibold text-morandi-dark tracking-wider mb-2">
        						素食需求
        					</label>
        
        					<select name="vegetarian"
        							class="w-full px-3 py-3 rounded-xl border border-stone-200 bg-white focus:outline-none focus:ring-2 focus:ring-morandi-warm/50 text-xs">
        
        						<option value="0">0 (無需求)</option>
        						<option value="1">1位</option>
        						<option value="2">2位</option>
        						<option value="3">3位</option>
        						<option value="4">4位</option>
        						<option value="5">5位</option>
        						<option value="6">6位</option>
        						<option value="7">7位</option>
        						<option value="8">8位</option>
        						<option value="9">9位</option>
        						<option value="10">10位</option>
        
        					</select>
        				</div>
        
        
        				<!-- 兒童座椅 -->
        				<div>
        					<label class="block text-xs uppercase font-semibold text-morandi-dark tracking-wider mb-2">
        						兒童座椅需求
        					</label>
        
        					<select name="childSeat"
        							class="w-full px-3 py-3 rounded-xl border border-stone-200 bg-white focus:outline-none focus:ring-2 focus:ring-morandi-warm/50 text-xs">
        
        						<option value="0">0 (無需求)</option>
        						<option value="1">1張</option>
        						<option value="2">2張</option>
        						<option value="3">3張</option>
        						<option value="4">4張</option>
        						<option value="5">5張</option>
        
        					</select>
        				</div>
        
        			</div>
        
        
        			<!-- 紙本喜帖需求 -->
        			<div>
        
        				<label class="block text-xs uppercase font-semibold text-morandi-dark tracking-wider mb-2">
        					紙本喜帖需求
        				</label>
        
        				<div class="grid sm:grid-cols-2 gap-3">
        
        					<label class="flex items-center p-3 rounded-xl border border-stone-200 bg-white cursor-pointer hover:border-morandi-warm transition">
        
        						<input type="radio"
        							   name="invitation"
        							   value="需要，請寄紙本喜帖給我"
        							   checked
        							   class="accent-[#d4a373] mr-2">
        
        						<span class="text-xs font-medium text-morandi-dark">
        							需要，請寄紙本喜帖給我
        						</span>
        
        					</label>
        
        
        					<label class="flex items-center p-3 rounded-xl border border-stone-200 bg-white cursor-pointer hover:border-morandi-warm transition">
        
        						<input type="radio"
        							   name="invitation"
        							   value="不用，我已經記起來婚禮資訊了"
        							   class="accent-[#d4a373] mr-2">
        
        						<span class="text-xs font-medium text-morandi-dark">
        							不用，我已經記起來婚禮資訊了
        						</span>
        
        					</label>
        
        				</div>
        
        			</div>
        
        
        			<!-- 郵遞區號與寄送地址 / 祝福小語 -->
        			<div class="grid md:grid-cols-3 gap-4">
        
        				<!-- 地址 -->
        				<div class="md:col-span-1">
        
        					<label class="block text-xs uppercase font-semibold text-morandi-dark tracking-wider mb-2">
        						郵遞區號/寄送地址
        					</label>
        
        					<input type="text"
        						   name="address"
        						   placeholder="例：63222 雲林縣..."
        						   class="w-full px-4 py-3 rounded-xl border border-stone-200 bg-white focus:outline-none focus:ring-2 focus:ring-morandi-warm/50 text-sm">
        
        				</div>
        
        
        				<!-- 祝福小語 -->
        				<div class="md:col-span-2">
        
        					<label class="block text-xs uppercase font-semibold text-morandi-dark tracking-wider mb-2">
        						祝福小語
        					</label>
        
        					<input type="text"
        						   id="blessing-input"
        						   name="blessing"
        						   placeholder="請寫下對新人的祝福..."
        						   class="w-full px-4 py-3 rounded-xl border border-stone-200 bg-white focus:outline-none focus:ring-2 focus:ring-morandi-warm/50 text-sm">
        
        				</div>
        
        			</div>
        
                    <!-- Submit Button -->
                    <button type="submit" id="submit-btn" class="w-full py-4 rounded-xl bg-morandi-warm text-white font-medium hover:bg-[#c29263] transition duration-300 shadow-md flex items-center justify-center gap-2">
                        <i data-lucide="send" class="w-4 h-4"></i>
                        <span>確認送出回函</span>
                    </button>
        
                </form>
        
            </div>
        </section>
        
        <!-- Blessing Wall Section -->
        <section class="py-20 bg-morandi-ivory border-t border-stone-200/60">
            <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="text-center mb-12">
                    <span class="font-script text-3xl text-morandi-sage">Warm Wishes</span>
                    <h2 class="font-cormorant text-2xl font-light tracking-widest text-morandi-dark uppercase">賓客祝福牆</h2>
                </div>
        
                <!-- Blessing Cards Stream -->
                <div id="blessing-wall" class="grid sm:grid-cols-2 gap-6">
                </div>
            </div>
        </section>
        
        <!-- Footer Section -->
        <footer class="py-12 bg-white border-t border-stone-100 text-center">
            <div class="max-w-4xl mx-auto px-4">
                <h3 class="font-cormorant text-3xl font-light text-morandi-warm mb-2">Lin & Li</h3>
                <p class="text-xs text-morandi-dark/60 tracking-widest uppercase mb-6">WEDDING • Thank you for sharing our joy</p>
                <p class="text-xs text-stone-400">© 2026 Lin & Li Wedding Invitation. All rights reserved.</p>
            </div>
        </footer>
        
        <!-- Custom Success Toast / Modal (Replaces Standard alert) -->
        <div id="modal-success" class="fixed inset-0 z-50 flex items-center justify-center bg-black/40 backdrop-blur-sm hidden opacity-0 transition-opacity duration-300">
            <div class="bg-white rounded-3xl p-8 max-w-sm w-full mx-4 text-center shadow-2xl border border-stone-100 transform scale-95 transition-transform duration-300" id="modal-box">
                <div class="w-16 h-16 mx-auto mb-4 rounded-full bg-morandi-warm/15 text-morandi-warm flex items-center justify-center">
                    <i data-lucide="heart-handshake" class="w-8 h-8"></i>
                </div>
                <h3 class="font-cormorant text-2xl font-semibold text-morandi-dark mb-2">已收到您的回函！</h3>
                <p class="text-xs text-morandi-dark/70 leading-relaxed mb-6">
                    非常感謝您的回覆與祝福！我們懷著無比期待的心情，盼望在婚宴當天與您歡聚。
                </p>
                <button id="close-modal-btn" class="w-full py-3 rounded-full bg-morandi-warm text-white font-medium text-sm hover:bg-[#c29263] transition">
                    好的，太棒了！
                </button>
            </div>
        </div>
        
        <script>
            // 初始化 Lucide 圖標
            lucide.createIcons();
        
            function initCountdown() {
                const targetDate = new Date('2026-11-22T12:00:00').getTime();
        
                function updateTimer() {
                    const now = new Date().getTime();
                    const difference = targetDate - now;
        
                    if (difference > 0) {
                        const days = Math.floor(difference / (1000 * 60 * 60 * 24));
                        const hours = Math.floor((difference % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
                        const minutes = Math.floor((difference % (1000 * 60 * 60)) / (1000 * 60));
                        const seconds = Math.floor((difference % (1000 * 60)) / 1000);
        
                        document.getElementById('cd-days').innerText = String(days).padStart(2, '0');
                        document.getElementById('cd-hours').innerText = String(hours).padStart(2, '0');
                        document.getElementById('cd-minutes').innerText = String(minutes).padStart(2, '0');
                        document.getElementById('cd-seconds').innerText = String(seconds).padStart(2, '0');
                    } else {
                        document.getElementById('cd-days').innerText = "00";
                        document.getElementById('cd-hours').innerText = "00";
                        document.getElementById('cd-minutes').innerText = "00";
                        document.getElementById('cd-seconds').innerText = "00";
                    }
                }
        
                updateTimer();
                setInterval(updateTimer, 1000);
            }
        
            const mobileMenuBtn = document.getElementById('mobile-menu-btn');
            const mobileMenu = document.getElementById('mobile-menu');
        
            mobileMenuBtn.addEventListener('click', () => {
                mobileMenu.classList.toggle('hidden');
            });
        
            document.querySelectorAll('#mobile-menu a').forEach(link => {
                link.addEventListener('click', () => {
                    mobileMenu.classList.add('hidden');
                });
            });
        	
        	
        	const GOOGLE_SCRIPT_URL =
        		"https://script.google.com/macros/s/AKfycbxr2jalKdyQfnn7AsCBmBNSYKFHu6dSrw10vJQrOh9G98kpg4BdVPzl8WRdP2ohiN_OSA/exec";
        
        	const rsvpForm = document.getElementById('rsvp-form');
        	const submitBtn = document.getElementById('submit-btn');
        	const modalSuccess = document.getElementById('modal-success');
        	const modalBox = document.getElementById('modal-box');
        	const closeModalBtn = document.getElementById('close-modal-btn');
        	const blessingInput = document.getElementById('blessing-input');
        	const blessingWall = document.getElementById('blessing-wall');
        
        	let submitting = false;
        
        
        	/*
        	 * 產生每次提交唯一 ID
        	 */
        	function createSubmissionId() {
        
        		if (window.crypto && crypto.randomUUID) {
        			return crypto.randomUUID();
        		}
        
        		return (
        			Date.now().toString(36) +
        			Math.random().toString(36).substring(2)
        		);
        	}
        
        
        	/*
        	 * 使用 JSONP 查詢 Apps Script
        	 * 確認 Sheet 中真的有 submissionId
        	 */
        	function checkSubmission(submissionId) {
        
        		return new Promise((resolve, reject) => {
        
        			const callbackName =
        				'rsvpCallback_' +
        				Date.now() +
        				'_' +
        				Math.floor(Math.random() * 100000);
        
        			const script = document.createElement('script');
        
        			const timer = setTimeout(() => {
        
        				cleanup();
        
        				reject(new Error('確認資料逾時'));
        
        			}, 8000);
        
        
        			function cleanup() {
        
        				clearTimeout(timer);
        
        				if (script.parentNode) {
        					script.parentNode.removeChild(script);
        				}
        
        				try {
        					delete window[callbackName];
        				} catch (e) {
        					window[callbackName] = undefined;
        				}
        			}
        
        
        			window[callbackName] = function (result) {
        
        				cleanup();
        
        				resolve(result);
        			};
        
        
        			script.onerror = function () {
        
        				cleanup();
        
        				reject(new Error('無法確認提交結果'));
        			};
        
        
        			script.src =
        				GOOGLE_SCRIPT_URL +
        				'?submissionId=' +
        				encodeURIComponent(submissionId) +
        				'&callback=' +
        				encodeURIComponent(callbackName) +
        				'&t=' +
        				Date.now();
        
        			document.body.appendChild(script);
        		});
        	}
        
        
        	/*
        	 * 等待 Google Sheet 確認資料存在
        	 */
        	async function waitForSubmission(submissionId) {
        
        		const maxRetry = 10;
        
        		for (let i = 0; i < maxRetry; i++) {
        
        			try {
        
        				const result =
        					await checkSubmission(submissionId);
        
        				if (
        					result &&
        					result.success === true &&
        					result.exists === true
        				) {
        					return true;
        				}
        
        			} catch (error) {
        
        				console.log(
        					'第 ' + (i + 1) + ' 次確認失敗',
        					error
        				);
        			}
        
        
        			/*
        			 * 等 1 秒再確認
        			 */
        			await new Promise(resolve =>
        				setTimeout(resolve, 1000)
        			);
        		}
        
        		return false;
        	}
        
        
        	/*
        	 * 顯示成功畫面
        	 */
        	function showSuccess() {
        
        		const userBlessing =
        			blessingInput.value.trim();
        
        
        		/*
        		 * 加到祝福牆
        		 */
        		if (userBlessing) {
        
        			const newCard =
        				document.createElement('div');
        
        			newCard.className =
        				"p-6 rounded-2xl bg-white border border-stone-100 shadow-sm transform transition duration-500 scale-95 opacity-0";
        
        			/*
        			 * 不使用 innerHTML 顯示使用者輸入
        			 * 避免 HTML Injection
        			 */
        			const header =
        				document.createElement('div');
        
        			header.className =
        				"flex items-center justify-between mb-3";
        
        
        			const guest =
        				document.createElement('span');
        
        			guest.className =
        				"font-medium text-sm text-morandi-dark";
        
        			guest.textContent =
        				"貴賓的祝福";
        
        
        			const time =
        				document.createElement('span');
        
        			time.className =
        				"text-xs text-morandi-sage";
        
        			time.textContent =
        				"剛剛";
        
        
        			header.appendChild(guest);
        			header.appendChild(time);
        
        
        			const text =
        				document.createElement('p');
        
        			text.className =
        				"text-xs sm:text-sm text-morandi-dark/80 leading-relaxed font-light";
        
        			text.textContent =
        				"「" + userBlessing + "」";
        
        
        			newCard.appendChild(header);
        			newCard.appendChild(text);
        
        			blessingWall.prepend(newCard);
        
        
        			setTimeout(() => {
        
        				newCard.classList.remove(
        					'scale-95',
        					'opacity-0'
        				);
        
        			}, 50);
        		}
        
        
        		/*
        		 * 彩帶效果
        		 */
        		if (typeof confetti === 'function') {
        
        			confetti({
        				particleCount: 80,
        				spread: 70,
        				origin: { y: 0.6 },
        				colors: [
        					'#d4a373',
        					'#8da399',
        					'#e0b8b1',
        					'#ffffff'
        				]
        			});
        		}
        
        
        		/*
        		 * 成功視窗
        		 */
        		modalSuccess.classList.remove('hidden');
        
        		setTimeout(() => {
        
        			modalSuccess.classList.remove(
        				'opacity-0'
        			);
        
        			modalBox.classList.remove(
        				'scale-95'
        			);
        
        		}, 10);
        	}
        
        
        	/*
        	 * 表單送出
        	 */
        	rsvpForm.addEventListener(
        		'submit',
        		async function (e) {
        
        			e.preventDefault();
        
        			if (submitting) {
        				return;
        			}
        
        
        			/*
        			 * HTML required 驗證
        			 */
        			if (!rsvpForm.checkValidity()) {
        
        				rsvpForm.reportValidity();
        				return;
        			}
        
        
        			submitting = true;
        
        			submitBtn.disabled = true;
        
        			submitBtn.innerHTML =
        				`<span>資料提交中...</span>`;
        
        
        			/*
        			 * 每次送出產生唯一 ID
        			 */
        			const submissionId =
        				createSubmissionId();
        
        			document.getElementById(
        				'submission-id'
        			).value = submissionId;
        
        
        			/*
        			 * 設定 Apps Script URL
        			 */
        			rsvpForm.action =
        				GOOGLE_SCRIPT_URL;
        
        
        			/*
        			 * 原生 submit 到 hidden iframe
        			 */
        			HTMLFormElement.prototype.submit.call(
        				rsvpForm
        			);
        
        
        			submitBtn.innerHTML =
        				`<span>正在確認資料...</span>`;
        
        
        			/*
        			 * 確認 Google Sheet
        			 */
        			const success =
        				await waitForSubmission(
        					submissionId
        				);
        
        
        			if (success) {
        
        				/*
        				 * 只有真的寫進 Google Sheet
        				 * 才顯示成功
        				 */
        				showSuccess();
        
        				rsvpForm.reset();
        
        			} else {
        
        				alert(
        					"資料尚未確認成功。\n\n" +
        					"請確認網路連線後重新送出，" +
        					"或聯絡新人確認是否收到回函。"
        				);
        			}
        
        
        			submitting = false;
        
        			submitBtn.disabled = false;
        
        			submitBtn.innerHTML =
        				`<i data-lucide="send"
        					class="w-4 h-4"></i>
        				 <span>確認送出回函</span>`;
        
        			lucide.createIcons();
        		}
        	);
        
            closeModalBtn.addEventListener('click', () => {
                modalSuccess.classList.add('opacity-0');
                modalBox.classList.add('scale-95');
                setTimeout(() => {
                    modalSuccess.classList.add('hidden');
                }, 300);
            });
        
            window.onload = function() {
                initCountdown();
            };
        </script>
</body>
</html>
