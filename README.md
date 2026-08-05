<!DOCTYPE html>
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
                    林 先生 <span class="mx-2 text-morandi-warm">|</span> 李 小姐
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
            <form id="rsvp-form" class="bg-morandi-ivory p-8 sm:p-12 rounded-3xl border border-stone-200/60 shadow-card-float space-y-6">
                
                <!-- 姓名與電話 -->
                <div class="grid md:grid-cols-2 gap-6">
                    <div>
                        <label class="block text-xs uppercase font-semibold text-morandi-dark tracking-wider mb-2">您的姓名 *</label>
                        <input type="text" name="entry.1402597420" required placeholder="例：張小明" class="w-full px-4 py-3 rounded-xl border border-stone-200 bg-white focus:outline-none focus:ring-2 focus:ring-morandi-warm/50 text-sm">
                    </div>
                    <div>
                        <label class="block text-xs uppercase font-semibold text-morandi-dark tracking-wider mb-2">聯絡電話 *</label>
                        <input type="tel" name="entry.272354315" required placeholder="0912-345-678" class="w-full px-4 py-3 rounded-xl border border-stone-200 bg-white focus:outline-none focus:ring-2 focus:ring-morandi-warm/50 text-sm">
                    </div>
                </div>

                <!-- 是否出席 & 親友關係 -->
                <div class="grid md:grid-cols-2 gap-6">
                    <div>
                        <label class="block text-xs uppercase font-semibold text-morandi-dark tracking-wider mb-2">是否出席婚宴 *</label>
                        <div class="space-y-2">
                            <label class="flex items-center p-3 rounded-xl border border-stone-200 bg-white cursor-pointer hover:border-morandi-warm transition">
                                <input type="radio" name="entry.154417609" value="出席，絕對到場 ! 🎉🥂" checked class="accent-[#d4a373] mr-2">
                                <span class="text-xs font-medium text-morandi-dark">出席，絕對到場 ! 🎉🥂</span>
                            </label>
                            <label class="flex items-center p-3 rounded-xl border border-stone-200 bg-white cursor-pointer hover:border-morandi-warm transition">
                                <input type="radio" name="entry.154417609" value="遺憾無法出席，獻上溫馨祝福" class="accent-[#d4a373] mr-2">
                                <span class="text-xs font-medium text-morandi-dark">遺憾無法出席，獻上溫馨祝福</span>
                            </label>
                        </div>
                    </div>
                    <div>
                        <label class="block text-xs uppercase font-semibold text-morandi-dark tracking-wider mb-2">您是哪一方的親友 *</label>
                        <div class="space-y-2">
                            <label class="flex items-center p-3 rounded-xl border border-stone-200 bg-white cursor-pointer hover:border-morandi-warm transition">
                                <input type="radio" name="entry.1432689929" value="🤵義哲的親友" checked class="accent-[#d4a373] mr-2">
                                <span class="text-xs font-medium text-morandi-dark">🤵 義哲的親友</span>
                            </label>
                            <label class="flex items-center p-3 rounded-xl border border-stone-200 bg-white cursor-pointer hover:border-morandi-warm transition">
                                <input type="radio" name="entry.1432689929" value="👰 念蓁的親友" class="accent-[#d4a373] mr-2">
                                <span class="text-xs font-medium text-morandi-dark">👰 念蓁的親友</span>
                            </label>
                        </div>
                    </div>
                </div>

                <!-- 出席人數 / 素食 / 兒童座椅 -->
                <div class="grid grid-cols-1 sm:grid-cols-3 gap-4">
                    <div>
                        <label class="block text-xs uppercase font-semibold text-morandi-dark tracking-wider mb-2">出席人數</label>
                        <select name="entry.2009077261" class="w-full px-3 py-3 rounded-xl border border-stone-200 bg-white focus:outline-none focus:ring-2 focus:ring-morandi-warm/50 text-xs">
                            <option value="1位">1位</option>
                            <option value="2位">2位</option>
                            <option value="3位">3位</option>
                            <option value="4位">4位</option>
                            <option value="5位或以上">5位或以上</option>
                        </select>
                    </div>
                    <div>
                        <label class="block text-xs uppercase font-semibold text-morandi-dark tracking-wider mb-2">素食需求</label>
                        <select name="entry.1054835683" class="w-full px-3 py-3 rounded-xl border border-stone-200 bg-white focus:outline-none focus:ring-2 focus:ring-morandi-warm/50 text-xs">
                            <option value="不需要">不需要</option>
                            <option value="1位">1位</option>
                            <option value="2位">2位</option>
                            <option value="3位">3位</option>
                        </select>
                    </div>
                    <div>
                        <label class="block text-xs uppercase font-semibold text-morandi-dark tracking-wider mb-2">兒童座椅需求</label>
                        <select name="entry.2128240145" class="w-full px-3 py-3 rounded-xl border border-stone-200 bg-white focus:outline-none focus:ring-2 focus:ring-morandi-warm/50 text-xs">
                            <option value="不需要">不需要</option>
                            <option value="1張">1張</option>
                            <option value="2張">2張</option>
                            <option value="3張">3張</option>
                        </select>
                    </div>
                </div>

                <!-- 紙本喜帖需求 -->
                <div>
                    <label class="block text-xs uppercase font-semibold text-morandi-dark tracking-wider mb-2">紙本喜帖需求</label>
                    <div class="grid sm:grid-cols-2 gap-3">
                        <label class="flex items-center p-3 rounded-xl border border-stone-200 bg-white cursor-pointer hover:border-morandi-warm transition">
                            <input type="radio" name="entry.2074213116" value="需要，請寄紙本喜帖給我" checked class="accent-[#d4a373] mr-2">
                            <span class="text-xs font-medium text-morandi-dark">需要，請寄紙本喜帖給我</span>
                        </label>
                        <label class="flex items-center p-3 rounded-xl border border-stone-200 bg-white cursor-pointer hover:border-morandi-warm transition">
                            <input type="radio" name="entry.2074213116" value="不需要，電子喜帖即可" class="accent-[#d4a373] mr-2">
                            <span class="text-xs font-medium text-morandi-dark">不需要，電子喜帖即可</span>
                        </label>
                    </div>
                </div>

                <!-- 郵遞區號與寄送地址 / 祝福小語 -->
                <div class="grid md:grid-cols-3 gap-4">
                    <div>
                        <label class="block text-xs uppercase font-semibold text-morandi-dark tracking-wider mb-2">郵遞區號</label>
                        <input type="text" name="entry.1228361035" placeholder="例：63222" class="w-full px-4 py-3 rounded-xl border border-stone-200 bg-white focus:outline-none focus:ring-2 focus:ring-morandi-warm/50 text-sm">
                    </div>
                    <div class="md:col-span-2">
                        <label class="block text-xs uppercase font-semibold text-morandi-dark tracking-wider mb-2">寄送地址 / 祝福小語</label>
                        <input type="text" id="blessing-input" name="entry.1589999982" placeholder="請填寫收件地址或寫下對新人的祝福..." class="w-full px-4 py-3 rounded-xl border border-stone-200 bg-white focus:outline-none focus:ring-2 focus:ring-morandi-warm/50 text-sm">
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
                <!-- Preset Card 1 -->
                <div class="p-6 rounded-2xl bg-white border border-stone-100 shadow-sm">
                    <div class="flex items-center justify-between mb-3">
                        <span class="font-medium text-sm text-morandi-dark">陳小姐 (Sophia 大學閨蜜)</span>
                        <span class="text-xs text-morandi-sage">Just now</span>
                    </div>
                    <p class="text-xs sm:text-sm text-morandi-dark/80 leading-relaxed font-light">
                        「恭喜 Sophia！看到你們一路走來這麼幸福真的超級感動，祝你們白頭偕老，永浴愛河！」
                    </p>
                </div>

                <!-- Preset Card 2 -->
                <div class="p-6 rounded-2xl bg-white border border-stone-100 shadow-sm">
                    <div class="flex items-center justify-between mb-3">
                        <span class="font-medium text-sm text-morandi-dark">林先生 (Julian 公司好友)</span>
                        <span class="text-xs text-morandi-sage">1 hour ago</span>
                    </div>
                    <p class="text-xs sm:text-sm text-morandi-dark/80 leading-relaxed font-light">
                        「恭喜杰哥娶得美嬌娘！祝你們新婚快樂，早生貴子，婚後也要繼續幸福滿滿喔！」
                    </p>
                </div>
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

        const GOOGLE_FORM_URL = "https://docs.google.com/forms/d/e/1FAIpQLSdUI0_xb0oxU0bxOqZS3Tpm6nWTr68infO50Z42rAt6SJDctQ/formResponse";
        const rsvpForm = document.getElementById('rsvp-form');
        const submitBtn = document.getElementById('submit-btn');
        const modalSuccess = document.getElementById('modal-success');
        const modalBox = document.getElementById('modal-box');
        const closeModalBtn = document.getElementById('close-modal-btn');
        const blessingInput = document.getElementById('blessing-input');
        const blessingWall = document.getElementById('blessing-wall');

        rsvpForm.addEventListener('submit', (e) => {
            e.preventDefault();

            // 禁用按鈕防止重複發送
            submitBtn.disabled = true;
            submitBtn.innerHTML = `<span>提交中...</span>`;

            // 收集表單數據
            const formData = new FormData(rsvpForm);

            // 送出資料至 Google Form (無跨域阻止體驗)
            fetch(GOOGLE_FORM_URL, {
                method: 'POST',
                mode: 'no-cors',
                body: formData
            }).then(() => {
                // 送出成功的UI回饋
                const userBlessing = blessingInput.value.trim();
                if (userBlessing) {
                    const newCard = document.createElement('div');
                    newCard.className = "p-6 rounded-2xl bg-white border border-stone-100 shadow-sm transform transition duration-500 scale-95 opacity-0";
                    newCard.innerHTML = `
                        <div class="flex items-center justify-between mb-3">
                            <span class="font-medium text-sm text-morandi-dark">貴賓的祝福</span>
                            <span class="text-xs text-morandi-sage">剛剛</span>
                        </div>
                        <p class="text-xs sm:text-sm text-morandi-dark/80 leading-relaxed font-light">
                            「${userBlessing}」
                        </p>
                    `;
                    blessingWall.prepend(newCard);
                    setTimeout(() => {
                        newCard.classList.remove('scale-95', 'opacity-0');
                    }, 50);
                }

                if (typeof confetti === 'function') {
                    confetti({
                        particleCount: 80,
                        spread: 70,
                        origin: { y: 0.6 },
                        colors: ['#d4a373', '#8da399', '#e0b8b1', '#ffffff']
                    });
                }

                modalSuccess.classList.remove('hidden');
                setTimeout(() => {
                    modalSuccess.classList.remove('opacity-0');
                    modalBox.classList.remove('scale-95');
                }, 10);

                rsvpForm.reset();
            }).catch(error => {
                console.error("提交表單發生錯誤:", error);
            }).finally(() => {
                submitBtn.disabled = false;
                submitBtn.innerHTML = `<i data-lucide="send" class="w-4 h-4"></i><span>確認送出回函</span>`;
                lucide.createIcons();
            });
        });

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
