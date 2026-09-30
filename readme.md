<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=rect&color=050505&height=180&text=TUX%20//%20RIG&fontSize=60&fontAlignY=45&desc=Linux%20Gaming%20Hub%20•%20Zero%20Latency%20•%20Pure%20Monochrome&descFontSize=16&descAlignY=70&fontColor=ffffff&stroke=222222&strokeWidth=2" alt="TUX RIG Header" width="100%" />
</p>

<p align="center">
  <a href="https://github.com/aidzyki"><img src="https://img.shields.io/badge/CURATOR-AIDZYKI-050505?style=for-the-badge&logo=linux&logoColor=ffffff&borderColor=333333" alt="Curator aidzyki"></a>
  <a href="#"><img src="https://img.shields.io/badge/VULKAN-1.3%20READY-050505?style=for-the-badge&logo=vulkan&logoColor=ffffff&borderColor=333333" alt="Vulkan 1.3"></a>
  <a href="#"><img src="https://img.shields.io/badge/COMPOSITOR-GAMESCOPE-050505?style=for-the-badge&logo=valve&logoColor=ffffff&borderColor=333333" alt="Gamescope"></a>
  <a href="#"><img src="https://img.shields.io/badge/STYLE-MONOCHROME%20BRUTALISM-050505?style=for-the-badge&logo=tailwindcss&logoColor=ffffff&borderColor=333333" alt="Monochrome"></a>
  <a href="#"><img src="https://img.shields.io/badge/GENERATED_BY-AI-050505?style=for-the-badge&logo=openai&logoColor=ffffff&borderColor=333333" alt="AI Generated"></a>
</p>

---

## ⚡ О проекте

**TUX // RIG** — это бескомпромиссный веб-интерфейс и база знаний для энтузиастов гейминга на Linux. Никакого визуального мусора, цветных неоновых перегрузок и телеметрии: строгий монохромный дизайн (Monochrome / Brutalist Tech), глубокие черные тона, тактильная звуковая обратная связь на Web Audio API и утилиты для выжимания минимального инпут-лага в соревновательных играх.

Портал реализован по принципу **Single-File Architecture** (один файл `index.html`, объединяющий Tailwind CSS, интерактивный JavaScript и рендеринг на Canvas).

---

## 📸 Галерея интерфейса

<div align="center">
  <img src="https://images.unsplash.com/photo-1550745165-9bc0b252726f?q=80&w=1200&auto=format&fit=crop" width="100%" alt="TUX RIG Dark Minimal Environment Preview" style="border: 1px solid #222222; border-radius: 8px; margin-bottom: 12px;" />
  <p><em>Архитектура проекта оптимизирована для работы на ультрашироких 4K мониторах и мобильных экранах.</em></p>
</div>

<br>

| 🕹️ Генератор флагов Steam | 📊 Интерактивный MangoHud | 🛡️ Радар Античитов |
|:---:|:---:|:---:|
| <img src="https://images.unsplash.com/photo-1629654297299-c8506221ca97?q=80&w=400&auto=format&fit=crop" width="280" alt="Terminal" style="border: 1px solid #222;"/><br>Быстрый сбор `gamemoderun`, `gamescope` и ACO | <img src="https://images.unsplash.com/photo-1542751371-adc38448a05e?q=80&w=400&auto=format&fit=crop" width="280" alt="Telemetry" style="border: 1px solid #222;"/><br>Wireframe 3D сцена и генерация конфига | <img src="https://images.unsplash.com/photo-1563986768609-322da13575f3?q=80&w=400&auto=format&fit=crop" width="280" alt="Security" style="border: 1px solid #222;"/><br>Статусы EAC, BattlEye и Vanguard |

---

## 🔥 Ключевой функционал

- **Steam Launch Options Generator**:
  - Быстрая генерация идеальной строки параметров запуска (`%command%`).
  - Интеграция микрокомпозитора **Valve Gamescope** (разрешение, ограничение частоты кадров, FSR-апскейлинг, HDR).
  - Оптимизации пайплайна: компилятор шейдеров AMD ACO (`RADV_PERFTEST=aco`), NVIDIA DLSS/Reflex (`PROTON_ENABLE_NVAPI=1`), трассировка лучей DX12 (`VKD3D_CONFIG=dxr`) и Fast Sync (`MESA_VK_WSI_PRESENT_MODE=mailbox`).
  - Готовые пресеты для киберспорта (CS2, Apex) и кинематографичных AAA-тайтлов.

- **MangoHud Real-Time Studio**:
  - Живой симулятор оверлея поверх динамической 3D-проволочной (wireframe) сцены на HTML5 Canvas.
  - Настройка отображаемых датчиков (FPS, график фреймтайма, температуры, VRAM/RAM, версия драйверов).
  - Экспорт готового файла `~/.config/MangoHud/MangoHud.conf` в один клик.

- **База совместимости игр (Proton & Native Radar)**:
  - Проверенные конфигурации для *Counter-Strike 2*, *Cyberpunk 2077*, *Elden Ring*, *Apex Legends*, *Dota 2* и других.
  - Рекомендации по версиям раннеров (GE-Proton, Proton Experimental) и модальные карточки с подробным описанием твиков.

- **Distro Tuning Station**:
  - Декларативные конфиги для **NixOS** (Flake-структура с `programs.steam` и `gamescopeSession`).
  - Команды установки и настройки для **Arch Linux / CachyOS** (ядро BORE, sched-ext), **Fedora / Nobara** и **Bazzite**.
  - Патчи для включения Wayland Zero-Lag Tearing (`tearing-control-v1`) и ультранизколатентного звука PipeWire (`quantum 64`).

- **Античит-радар (Anti-Cheat Compatibility)**:
  - Живой фильтр статуса игр с Easy Anti-Cheat, BattlEye, Vanguard и Blizzard Warden.

- **Audio Feedback Engine**:
  - Встроенный звуковой движок на Web Audio API, генерирующий щелчки механического реле при кликах без подгрузки тяжелых внешних аудиофайлов.

- **Mobile First & Адаптивность**:
  - Складывающееся мобильное меню, адаптивный скролл таблиц, сенсорные зоны клика от 44px и плавающий watermark.

---

## 🛠️ Стек технологий

```
├── UI/Layout       : HTML5 / Tailwind CSS (Monochrome Dark Palette)
├── Icons           : Lucide Icons (CDN)
├── Typography      : Inter + JetBrains Mono (Google Fonts)
├── 3D Simulation   : HTML5 Canvas 2D API (Perspective Wireframe Renderer)
├── Sound FX        : Web Audio API (Synthesized Mechanical Clicks)
└── Packaging       : Zero-dependency Single HTML File
```

---

## 🚀 Быстрый запуск

Так как проект полностью содержится в одном файле, установка сторонних зависимостей (`npm`, `node`, сборщики) **не требуется**.

### Вариант 1. Открытие локально
Просто дважды кликните по файлу `index.html` или откройте его в любом современном браузере:
```bash
xdg-open index.html
```

### Вариант 2. Локальный веб-сервер через Python
```bash
# Клонируйте репозиторий
git clone https://github.com/aidzyki/tux-rig.git
cd tux-rig

# Запустите локальный сервер
python3 -m http.server 8080
```
После этого откройте в браузере: `http://localhost:8080`

### Вариант 3. Декларативный запуск через Nix
```bash
nix-shell -p python3 --run "python3 -m http.server 8080"
```

---

## 👤 Куратор & Станция // aidzyki

Все социальные ресурсы и контакты автора вынесены в отдельный монохромный модуль в нижней части портала:

- **Telegram**: [@aidzyki](https://t.me/aidzyki) — прямая связь, новости, игровые конфиги и обсуждения.
- **GitHub**: [aidzyki](https://github.com/aidzyki) — репозитории, dotfiles, Nix-флейки.
- **Steam**: `Aidzyki` — матчи и тестирование Proton GE.
- **VimeWorld**: `Aidzyki` — PvP-сессии на оптимизированном Linux JVM.

```
Rig Hardware & OS Specs:
├── OS          : NixOS Unstable (Flakes)
├── Window Mgr  : Hyprland (Wayland Tearing Protocol)
├── Kernel      : Linux-CachyOS (BORE Scheduler)
├── GPU Driver  : Mesa RADV ACO (Vulkan 1.3)
└── Audio       : PipeWire Low-Latency (64 samples buffer)
```

---

## 📄 Лицензия

Проект распространяется под свободной лицензией **MIT License**. Вы можете свободно модифицировать, форкать и использовать наработки в своих конфигах.

---

<div align="center">
  <br>
  <p>⚠️ <strong>Отказ от ответственности & AI-декларация:</strong></p>
  <p><em>Данный проект, включая всю верстку, JavaScript-движок, симулятор MangoHud, структуру документации и контент, <strong>полностью и целиком сгенерирован искусственным интеллектом</strong> по запросу автора.</em></p>
  <br>
  <code>SYSTEM STATUS: KERNEL OK // ZERO BLOAT // PURE LINUX</code>
</div>
