<!DOCTYPE html>
<html lang="ru" class="dark scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TUX // RIG — Linux Gaming Portal (aidzyki edition)</title>
    <!-- Fonts: Inter & JetBrains Mono -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&family=JetBrains+Mono:wght@400;500;700&display=swap" rel="stylesheet">
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Lucide Icons -->
    <script src="https://unpkg.com/lucide@latest"></script>
    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    colors: {
                        mono: {
                            base: '#070707',
                            surface: '#0f0f0f',
                            panel: '#141414',
                            elevated: '#1a1a1a',
                            border: '#262626',
                            borderLight: '#3d3d3d',
                            muted: '#71717a',
                            text: '#d4d4d8',
                            high: '#ffffff'
                        }
                    },
                    fontFamily: {
                        sans: ['Inter', '-apple-system', 'BlinkMacSystemFont', 'sans-serif'],
                        mono: ['"JetBrains Mono"', 'monospace']
                    }
                }
            }
        }
    </script>
    <style>
        /* Strict Monochrome Theme Adjustments */
        ::-webkit-scrollbar {
            width: 6px;
            height: 6px;
        }
        ::-webkit-scrollbar-track {
            background: #070707;
        }
        ::-webkit-scrollbar-thumb {
            background: #262626;
            border-radius: 3px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #52525b;
        }
        .mono-card {
            background-color: #0f0f0f;
            border: 1px solid #262626;
            transition: border-color 0.2s ease, box-shadow 0.2s ease;
        }
        .mono-card:hover {
            border-color: #52525b;
        }
        .mono-border {
            border: 1px solid #262626;
        }
        .mono-btn-primary {
            background-color: #ffffff;
            color: #000000;
            transition: all 0.15s ease;
        }
        .mono-btn-primary:hover {
            background-color: #d4d4d8;
        }
        .mono-btn-secondary {
            background-color: #141414;
            border: 1px solid #262626;
            color: #ffffff;
            transition: all 0.15s ease;
        }
        .mono-btn-secondary:hover {
            border-color: #ffffff;
            background-color: #1f1f1f;
        }
        /* Subtle scanlines for HUD monitor simulator */
        .hud-scanline {
            background: linear-gradient(rgba(18, 16, 16, 0) 50%, rgba(0, 0, 0, 0.4) 50%);
            background-size: 100% 4px;
            pointer-events: none;
        }
    </style>
</head>
<body class="bg-mono-base text-mono-text font-sans selection:bg-white selection:text-black antialiased overflow-x-hidden min-h-screen">

    <!-- FLOATING WATERMARK (AIDZYKI ARCHIVE) -->
    <aside class="fixed bottom-4 right-4 z-50 pointer-events-auto">
        <a href="#aidzyki-profile" class="group flex items-center space-x-2.5 px-3 py-1.5 rounded-lg border border-mono-border bg-mono-surface/90 backdrop-blur-md shadow-2xl hover:border-white transition-all duration-200">
            <span class="relative flex h-2 w-2">
                <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-white opacity-75"></span>
                <span class="relative inline-flex rounded-full h-2 w-2 bg-white"></span>
            </span>
            <span class="font-mono text-[10px] tracking-wider text-neutral-400 group-hover:text-white uppercase transition">
                <strong class="text-white font-semibold">AIDZYKI</strong> // SYSTEM ARCHIVE
            </span>
            <span class="text-[9px] font-mono px-1 rounded bg-neutral-800 text-neutral-300">v2.6</span>
        </a>
    </aside>

    <!-- Global Toast Container -->
    <div id="toastContainer" class="fixed top-20 right-4 z-50 flex flex-col space-y-2 pointer-events-none max-w-sm w-full"></div>

    <!-- Navigation Header -->
    <header class="sticky top-0 z-40 border-b border-mono-border bg-mono-base/90 backdrop-blur-xl">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 h-16 flex items-center justify-between">
            
            <!-- Branding / Logo -->
            <div class="flex items-center space-x-3">
                <a href="#" class="flex items-center space-x-2.5 group">
                    <div class="w-8 h-8 rounded border border-mono-border bg-mono-panel flex items-center justify-center text-white group-hover:border-white transition">
                        <i data-lucide="terminal" class="w-4 h-4"></i>
                    </div>
                    <div>
                        <div class="flex items-center space-x-2">
                            <span class="font-mono font-bold tracking-tight text-white text-base">TUX<span class="text-neutral-500">//</span>RIG</span>
                            <span class="hidden sm:inline-block text-[10px] font-mono uppercase px-1.5 py-0.5 rounded border border-mono-border text-neutral-400">MONOCHROME</span>
                        </div>
                    </div>
                </a>
            </div>

            <!-- Desktop Nav Links -->
            <nav class="hidden md:flex items-center space-x-1 font-mono text-xs text-neutral-400">
                <a href="#launch-generator" class="px-3 py-1.5 rounded hover:text-white hover:bg-mono-panel transition">параметры-запуска</a>
                <a href="#proton-radar" class="px-3 py-1.5 rounded hover:text-white hover:bg-mono-panel transition">радар-игр</a>
                <a href="#mangohud-sim" class="px-3 py-1.5 rounded hover:text-white hover:bg-mono-panel transition">mangohud</a>
                <a href="#distro-station" class="px-3 py-1.5 rounded hover:text-white hover:bg-mono-panel transition">сетап-дистро</a>
                <a href="#anticheat-radar" class="px-3 py-1.5 rounded hover:text-white hover:bg-mono-panel transition">античит</a>
                <a href="#aidzyki-profile" class="px-3 py-1.5 rounded text-white border border-mono-border hover:border-white transition">@aidzyki</a>
            </nav>

            <!-- Actions: SFX Toggle & Mobile Menu Trigger -->
            <div class="flex items-center space-x-2">
                <button id="soundToggleBtn" onclick="toggleAudio()" class="px-2.5 py-1.5 rounded border border-mono-border bg-mono-panel hover:border-neutral-400 text-neutral-300 text-xs font-mono flex items-center space-x-1.5 transition" title="Звук интерфейса">
                    <i id="soundIcon" data-lucide="volume-2" class="w-3.5 h-3.5 text-white"></i>
                    <span id="soundLabel" class="hidden sm:inline text-[11px]">SFX: ON</span>
                </button>

                <!-- Mobile Hamburger Button -->
                <button id="mobileMenuBtn" onclick="toggleMobileMenu()" class="md:hidden p-2 rounded border border-mono-border bg-mono-panel text-white hover:border-white transition" aria-label="Открыть меню">
                    <i id="menuIcon" data-lucide="menu" class="w-5 h-5"></i>
                </button>
            </div>
        </div>

        <!-- Mobile Navigation Drawer -->
        <div id="mobileDrawer" class="hidden md:hidden border-b border-mono-border bg-mono-surface px-4 py-4 space-y-3 font-mono text-xs">
            <a href="#launch-generator" onclick="closeMobileMenu()" class="block py-2 text-neutral-300 hover:text-white border-b border-mono-border/50">_01. параметры запуска Steam</a>
            <a href="#proton-radar" onclick="closeMobileMenu()" class="block py-2 text-neutral-300 hover:text-white border-b border-mono-border/50">_02. база совместимости игр</a>
            <a href="#mangohud-sim" onclick="closeMobileMenu()" class="block py-2 text-neutral-300 hover:text-white border-b border-mono-border/50">_03. mangohud симулятор</a>
            <a href="#distro-station" onclick="closeMobileMenu()" class="block py-2 text-neutral-300 hover:text-white border-b border-mono-border/50">_04. тюнинг NixOS / Arch</a>
            <a href="#anticheat-radar" onclick="closeMobileMenu()" class="block py-2 text-neutral-300 hover:text-white border-b border-mono-border/50">_05. радар античитов EAC/BE</a>
            <a href="#aidzyki-profile" onclick="closeMobileMenu()" class="block py-2 text-white font-semibold">_06. профиль & контакты aidzyki</a>
        </div>
    </header>

    <main class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-8 sm:py-12 space-y-16 sm:space-y-24">

        <!-- Hero Section -->
        <section class="border-b border-mono-border pb-12 sm:pb-16 pt-4">
            <div class="max-w-4xl space-y-6">
                <div class="inline-flex items-center space-x-2 px-2.5 py-1 rounded border border-mono-border bg-mono-panel text-neutral-300 font-mono text-xs">
                    <span class="w-1.5 h-1.5 rounded-full bg-white animate-pulse"></span>
                    <span>PROTON 9.0 // WAYLAND TEARING PROTOCOL // MESA ACO // KERNEL 6.12+</span>
                </div>

                <h1 class="text-3xl sm:text-5xl lg:text-6xl font-extrabold tracking-tight text-white uppercase leading-none font-mono">
                    Linux Gaming.<br>
                    <span class="text-neutral-500">Pure Performance.</span>
                </h1>

                <p class="text-neutral-400 text-sm sm:text-base leading-relaxed max-w-2xl font-sans">
                    Бескомпромиссная боевая станция на свободном ядре. Отсутствие мусорной телеметрии, прямой вывод через Vulkan VKD3D, микрокомпозитор Gamescope и нулевой инпут-лаг для соревновательных шутеров и AAA-тайтлов.
                </p>

                <div class="flex flex-wrap gap-3 pt-2">
                    <a href="#launch-generator" onclick="playClick()" class="mono-btn-primary px-5 py-2.5 rounded font-mono text-xs font-bold uppercase tracking-wider flex items-center space-x-2">
                        <i data-lucide="terminal" class="w-4 h-4"></i>
                        <span>Генератор Steam флагов</span>
                    </a>
                    <a href="#aidzyki-profile" onclick="playClick()" class="mono-btn-secondary px-5 py-2.5 rounded font-mono text-xs uppercase tracking-wider flex items-center space-x-2">
                        <i data-lucide="user" class="w-4 h-4"></i>
                        <span>Куратор: aidzyki</span>
                    </a>
                </div>
            </div>

            <!-- Quick Telemetry Specs -->
            <div class="grid grid-cols-2 md:grid-cols-4 gap-3 sm:gap-4 mt-12 font-mono text-xs">
                <div class="p-4 rounded border border-mono-border bg-mono-surface">
                    <div class="text-neutral-500 uppercase text-[10px]">Steam Top 100</div>
                    <div class="text-2xl font-bold text-white mt-1">94%</div>
                    <div class="text-neutral-400 text-[11px] mt-0.5">Совместимо через Proton</div>
                </div>
                <div class="p-4 rounded border border-mono-border bg-mono-surface">
                    <div class="text-neutral-500 uppercase text-[10px]">Vulkan Backend</div>
                    <div class="text-2xl font-bold text-white mt-1">1.3+</div>
                    <div class="text-neutral-400 text-[11px] mt-0.5">VKD3D-Proton / DXVK</div>
                </div>
                <div class="p-4 rounded border border-mono-border bg-mono-surface">
                    <div class="text-neutral-500 uppercase text-[10px]">Input Delay</div>
                    <div class="text-2xl font-bold text-white mt-1">~1.2 ms</div>
                    <div class="text-neutral-400 text-[11px] mt-0.5">Wayland Tearing On</div>
                </div>
                <div class="p-4 rounded border border-mono-border bg-mono-surface">
                    <div class="text-neutral-500 uppercase text-[10px]">Audio Latency</div>
                    <div class="text-2xl font-bold text-white mt-1">64 spl</div>
                    <div class="text-neutral-400 text-[11px] mt-0.5">PipeWire Pro-Audio</div>
                </div>
            </div>
        </section>

        <!-- AIDZYKI PROFILE & SOCIALS SECTION -->
        <section id="aidzyki-profile" class="scroll-mt-20">
            <div class="flex items-center justify-between border-b border-mono-border pb-3 mb-6">
                <div class="flex items-center space-x-2">
                    <i data-lucide="shield" class="w-4 h-4 text-white"></i>
                    <h2 class="font-mono text-sm font-bold uppercase tracking-wider text-white">Curator & Rig Master // aidzyki</h2>
                </div>
                <span class="text-neutral-500 text-xs font-mono">ID: aidzyki // verified</span>
            </div>

            <div class="grid grid-cols-1 lg:grid-cols-12 gap-6 items-stretch">
                <!-- Profile Identity Card -->
                <div class="lg:col-span-4 mono-card rounded-lg p-6 flex flex-col justify-between space-y-6">
                    <div>
                        <div class="flex items-center space-x-4 mb-4">
                            <div class="w-14 h-14 rounded border border-mono-borderLight bg-mono-panel flex items-center justify-center text-white font-mono text-xl font-bold">
                                AZ
                            </div>
                            <div>
                                <h3 class="text-lg font-mono font-bold text-white tracking-wide">aidzyki</h3>
                                <p class="text-xs text-neutral-400 font-mono">Linux Gamer & NixOS Enthusiast</p>
                                <div class="mt-1 inline-flex items-center space-x-1.5 text-[10px] font-mono text-white bg-mono-elevated px-2 py-0.5 rounded border border-mono-border">
                                    <span class="w-1.5 h-1.5 rounded-full bg-white"></span>
                                    <span>STATUS: ONLINE // GAMING</span>
                                </div>
                            </div>
                        </div>
                        <p class="text-xs text-neutral-300 font-sans leading-relaxed">
                            Сборка, поддержка и оптимизация Linux-окружения для киберспорта и AAA-гейминга. Кастомные конфиги NixOS, Hyprland без задержек и тонкая настройка Proton под Steam.
                        </p>
                    </div>

                    <!-- System Rig Specs Quickview -->
                    <div class="p-3 rounded bg-mono-panel border border-mono-border font-mono text-[11px] space-y-1">
                        <div class="text-neutral-500 text-[10px] uppercase font-bold tracking-wider">Battle Station Specs:</div>
                        <div class="flex justify-between text-neutral-300">
                            <span>OS:</span>
                            <span class="text-white">NixOS Unstable / Hyprland</span>
                        </div>
                        <div class="flex justify-between text-neutral-300">
                            <span>Kernel:</span>
                            <span class="text-white">Linux-CachyOS (BORE)</span>
                        </div>
                        <div class="flex justify-between text-neutral-300">
                            <span>GPU / Driver:</span>
                            <span class="text-white">Radeon RX / Mesa ACO</span>
                        </div>
                    </div>
                </div>

                <!-- Socials & Platforms Grid -->
                <div class="lg:col-span-8 grid grid-cols-1 sm:grid-cols-2 gap-4">
                    <!-- Telegram -->
                    <a href="https://t.me/aidzyki" target="_blank" rel="noopener noreferrer" onclick="playClick()" class="mono-card rounded-lg p-5 flex flex-col justify-between hover:border-white group transition">
                        <div>
                            <div class="flex items-center justify-between mb-2">
                                <span class="font-mono text-xs text-neutral-400 uppercase tracking-wider">Telegram Channel & PM</span>
                                <i data-lucide="send" class="w-4 h-4 text-white group-hover:translate-x-0.5 transition"></i>
                            </div>
                            <div class="text-base font-mono font-bold text-white group-hover:underline">@aidzyki</div>
                            <p class="text-xs text-neutral-400 mt-2 font-sans">
                                Прямая связь, обсуждение игровых сборок, конфигов ядра и решение траблов с Proton.
                            </p>
                        </div>
                        <div class="mt-4 pt-3 border-t border-mono-border flex items-center justify-between text-[11px] font-mono text-neutral-400">
                            <span>Сообщество & Чат</span>
                            <span class="text-white font-semibold">t.me/aidzyki &rarr;</span>
                        </div>
                    </a>

                    <!-- Roblox -->
                    <div class="mono-card rounded-lg p-5 flex flex-col justify-between">
                        <div>
                            <div class="flex items-center justify-between mb-2">
                                <span class="font-mono text-xs text-neutral-400 uppercase tracking-wider">Roblox Identity</span>
                                <i data-lucide="gamepad-2" class="w-4 h-4 text-white"></i>
                            </div>
                            <div class="text-base font-mono font-bold text-white">@zov_aidzyki</div>
                            <p class="text-xs text-neutral-400 mt-2 font-sans">
                                Игровой никнейм в Roblox. Запуск через нативный Linux-клиент Vinegar / Sober с Vulkan API.
                            </p>
                        </div>
                        <div class="mt-4 pt-3 border-t border-mono-border flex items-center justify-between text-[11px] font-mono text-neutral-400">
                            <span>Платформа: Sober/Soba</span>
                            <button onclick="copySnippet('zov_aidzyki')" class="hover:text-white underline">Скопировать ник</button>
                        </div>
                    </div>

                    <!-- Steam & VimeWorld -->
                    <div class="mono-card rounded-lg p-5 flex flex-col justify-between">
                        <div>
                            <div class="flex items-center justify-between mb-2">
                                <span class="font-mono text-xs text-neutral-400 uppercase tracking-wider">Steam & VimeWorld</span>
                                <i data-lucide="crosshair" class="w-4 h-4 text-white"></i>
                            </div>
                            <div class="text-base font-mono font-bold text-white">Aidzyki</div>
                            <p class="text-xs text-neutral-400 mt-2 font-sans">
                                Steam профиль и VimeWorld аккаунт. Совместные катки в CS2, TF2, Dota 2 и соревновательные PvP-сервера.
                            </p>
                        </div>
                        <div class="mt-4 pt-3 border-t border-mono-border flex items-center justify-between text-[11px] font-mono text-neutral-400">
                            <span>Handle: Aidzyki</span>
                            <button onclick="copySnippet('Aidzyki')" class="hover:text-white underline">Скопировать ник</button>
                   
