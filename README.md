# TikTok You — AI Embedded Ad Skipper (v22)

An enhanced build based on **TikTok You 5.0 (47.4.3)** that automatically detects and skips embedded sponsor integrations inside TikTok videos while keeping all original mod features intact.

> **Latest Release:** [v22](https://github.com/bombarocket/tiktok-you-updates/releases/tag/v22) · [Direct APK Download](https://github.com/bombarocket/tiktok-you-updates/releases/download/v22/TikTok_You-5.0(47.4.3).apk)

---

## Features

- **Embedded Ad & Silent Banner Detection**
  - Detects both **spoken sponsorships** and **silent animated banner overlays** (VPNs, case-opening / drop / skin-trading services, marketplaces, Telegram bots, mobile/reward apps) even when there is no URL, @handle, or voiceover.
  - Rejects bare brand mentions, clothing logos, film/anime edits, and ordinary story dialogue to avoid false skips.
  - Supports multiple separate ad insertions in a single video.
- **Frame-Accurate Boundaries & Playback Controls**
  - Uses local video frames and real presentation timestamps (PTS) to pinpoint banner entrance/exit.
  - **Timeline Markers:** Green = verified auto-skip; Amber = probable/manual skip.
  - **Undo Protection:** Includes a quick **Undo** button after an automatic skip and protects manual user seeks.
- **Multiple AI Providers & Offline Fallback**
  - **Google Gemini (Free Tier):** `gemini-3.1-flash-lite`, `gemini-3.5-flash-lite`, `gemini-3.5-flash`, `gemini-3.6-flash`, `gemini-3.7-flash`, `gemini-3.8-flash`, `gemini-3-flash-preview` with automatic model rotation on 429/503.
  - **OpenRouter (:free):** Supports free multimodal video/image models fetched live from OpenRouter (e.g. `google/gemma-4-31b-it:free`, `google/gemma-4-26b-a4b-it:free`, `nvidia/nemotron-3.5-super-vl:free`, etc.) using a separate OpenRouter key.
  - **Offline Mode (No API):** Built-in Russian **Vosk** speech model for on-device detection when offline or out of quota, plus hidden local WebVTT subtitle caching.
- **Traffic & Token Optimization**
  - 1.5 fps discovery on Wi-Fi, 5 fps frame-proof verification, single-window scan up to 72s, and a **7-day local result cache** (cached videos skip instantly with zero API calls).
- **Original Mod Features Preserved**
  - Built-in feed ad removal, clean watermark-free downloads, auto-scroll, publish timestamps, and story likes/reposts via Pine hook compatibility.
- **In-App Auto-Updater**
  - Checks `version.json` on startup and manually from Mod Settings.

---

## Installation & Setup

1. **First-time install:** If you currently have the official TikTok app or another author's TikTok You APK installed, **uninstall it first** (this build uses its own signing key). Future updates from this repository will install cleanly over each other without losing data.
2. **Download & install** the latest APK from [Releases](https://github.com/bombarocket/tiktok-you-updates/releases/latest).
3. **Configure your API key (free):**
   - Get a free Gemini API key from [Google AI Studio](https://aistudio.google.com/apikey) (or an OpenRouter key).
   - Open TikTok → **Profile → ☰ → Settings and privacy → Настройки мода → Автопропуск рекламы → Ключ API** and paste your key.
   - Open **Проверить модели и подключение** to verify the key works.
   - *(Optional)* Enable **Только локально: без API** to run purely on-device using the built-in Russian speech model.

---

## Security & Privacy

- **No secrets inside the APK:** Automated scans verify that no personal API keys or signing keys are embedded in the distributed APK.
- Your API key is stored locally in private app preferences on your device and sent only to your chosen provider (Google Gemini or OpenRouter).

---

## Инструкция на русском

### 1. Установка и обновления

1. **Перед первой установкой** удалите официальный TikTok или другой мод TikTok You (у этой сборки своя подпись, поэтому поверх чужого APK она не встанет).
2. Скачайте свежий APK со страницы [Releases](https://github.com/bombarocket/tiktok-you-updates/releases/latest) и установите.
3. Все следующие версии из этого репозитория можно устанавливать **поверх без удаления** — вход в аккаунт, ключ и настройки сохранятся.

### 2. Как получить бесплатный ключ Google Gemini (AI Studio)

Мод использует личный бесплатный ключ — это нужно, чтобы у каждого пользователя была собственная бесплатная квота Google, не зависящая от чужих лимитов. Карта и оплата не требуются.

1. Откройте [Google AI Studio — API Keys](https://aistudio.google.com/apikey) и войдите в аккаунт Google.
2. Нажмите **Create API key** → выберите существующий проект (или создайте новый).
3. Скопируйте полученный ключ (обычно начинается с `AIza...`) и никому его не передавайте.

### 3. Куда вставить ключ и как включить

1. Откройте TikTok и перейдите в настройки: **Профиль → ☰ → Настройки и конфиденциальность**.
2. Внизу экрана нажмите красную кнопку **Настройки мода ›**.
3. Откройте раздел **Автопропуск рекламы**.
4. В блоке **Анализ** нажмите **Ключ API**, вставьте ключ Gemini и нажмите **Сохранить**.
5. Нажмите **Проверить модели и подключение** — если всё настроено верно, мод подтвердит связь, а в списке **Бесплатная модель** будут доступны модели `Gemini` с автоматическим переключением при лимитах.

### 4. Запасные варианты (OpenRouter и офлайн без API)

- **OpenRouter (`:free`):** если квота Google закончилась или удобнее другой провайдер, выберите в **Сервис AI → OpenRouter · эксперимент**, вставьте отдельный бесплатный ключ OpenRouter, нажмите **Проверить модели и подключение** и выберите бесплатную мультимодальную модель (`:free`). Платные модели заблокированы на уровне кода.
- **Без API (офлайн):** в разделе **Локальная проверка · эксперимент** можно включить **Только локально: без API** — для распознавания русской речи будет использоваться встроенная модель Vosk прямо на устройстве (без облачных ключей, но короткие немые баннеры без текста/озвучки локальная речь может пропустить).
- **Обновления:** при выходе новой версии мод предупредит на старте; вручную можно проверить кнопкой **Проверить обновления** в разделе **Состояние**.
