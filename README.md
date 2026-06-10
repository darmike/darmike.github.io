Crypto Backtest PRO — PWA для iOS/Android

Це **Progressive Web App** — працює як звичайна мобільна app, але без потреби в Mac чи App Store.

-----

## 🚀 Швидкий старт (на iOS iPhone)

### **Крок 1: Розмісти файли на хостингу**

Потрібна будь-яка безплатна платформа з HTTPS:

#### **Варіант A: GitHub Pages (рекомендовано, найпростіше)**

```bash
# 1. Створи репозиторій на GitHub: username.github.io
# 2. Скопіюй 3 файли в корінь репо:
#    - index.html
#    - manifest.json
#    - sw.js

# 3. Commit & Push
git add .
git commit -m "Add crypto backtest app"
git push
```

**Твоя app буде тут:** `https://username.github.io`

-----

#### **Варіант B: Netlify (5 хвилин)**

```
1. Йди на netlify.com
2. "Add new site" → "Deploy manually"
3. Перетягни 3 файла
4. Готово! Твоя URL: https://random-name.netlify.app
```

-----

#### **Варіант C: Vercel (автоматичний)**

```
1. vercel.com → "New Project"
2. Загрузи GitHub repo
3. Готово, auto-deploys на кожен push
```

-----

### **Крок 2: Відкрий на iPhone**

1. **Відкрий Safari**
1. Йди на твою URL (наприклад `https://username.github.io`)
1. Натисни **Share** ↑
1. Прокрути вниз → **Add to Home Screen**
1. Назви app (наприклад “Backtest”)
1. **Add** → готово! 🎉

Тепер має app прямо на Home Screen, як звичайна app.

-----

## 📊 Як користуватися

1. **Вибери стратегію:**
- RSI + MACD (momentum)
- SMA Crossover (trend)
- Bollinger Bands (reversal)
1. **Вибери період:** 1 місяц, 3, 6, 12 місяців
1. **Натисни “Запустити”**
1. **Читай результати:**
- Total Return % — загальний дохід
- Win Rate % — % прибільних сделок
- Profit Factor — качество стратегії
- Sharpe Ratio — дохід на ризик
- Max Drawdown — найбільша втрата
1. **Таблиця ТОП-5 сделок** внизу

-----

## 🔧 Що всередині файлів

|Файл           |Для чого                                 |
|---------------|-----------------------------------------|
|`index.html`   |Основний app (React + Recharts)          |
|`manifest.json`|Налаштування PWA (іконки, назва, colors) |
|`sw.js`        |Service Worker (offline режим, кешування)|

-----

## 🎨 Доступ Offline

Service Worker автоматично **кешує все**, тому app працює без інтернету (з закешеданними даними).

-----

## 🌐 Розмісти на своєму домені (опціонально)

Якщо маєш свій домен з HTTPS:

```bash
# 1. FTP/SFTP загрузи 3 файла в корінь
# 2. Переконайся що файл .htaccess має Content-Type

# Для Apache (.htaccess)
<IfModule mod_mime.c>
    AddType application/json .json
</IfModule>

# Для Nginx (nginx.conf)
types {
    application/json json;
    application/javascript js;
    text/html html;
}
```

-----

## 📲 Тестування локально (Windows/Linux/Mac)

Якщо хочеш тестити перед розміщенням:

```bash
# Python 3
python -m http.server 8000

# Node.js (якщо встановлено)
npx http-server

# Jди на http://localhost:8000
```

-----

## ✅ Що потрібно для iOS PWA

- ✓ HTTPS (обов’язково!)
- ✓ `manifest.json` з коректною назвою/іконкою
- ✓ `index.html` з meta tags для iOS
- ✓ Service Worker для offline роботи

**Все вже налаштовано в наших файлах!**

-----

## 🐛 Якщо щось не працює

### **App не з’являється в “Add to Home Screen”**

- Перевір що ти використовуєш **HTTPS** (GitHub Pages/Netlify мають його за замовчуванням)
- Спробуй **Ctrl+Shift+Delete** (очистити кеш Safari)
- Перевантажи сторінку

### **Дані не зберігаються offline**

- Service Worker потребує 10-15 секунд на перший вход для кешування
- Спробуй відкрити app, почекай, потім вийди в offline

### **Графіки не показуються**

- Перевір що Recharts завантажився з CDN (дивись Console)
- Якщо CDN не доступна — можна скачати локально

-----

## 🎯 Наступні кроки

1. **Розміщу на GitHub Pages** (найпростіше)
1. **Відкрий на iPhone → Add to Home Screen**
1. **Тестуй стратегії** без ризику
1. Коли матимеш стратегію що працює — переходи до **реальної торгівлі** з малими сумами

-----

## 💡 Pro Tips

- **Робота на мобільному інтернеті:** Після першого завантаження все кешується — працює навіть без інтернету
- **Темна тема:** Автоматично адаптується до iOS Dark Mode
- **Безпека:** Жоден твій API key не відправляється на сервер (все робиться локально)

-----

**Питання? Потрібна допомога?** 📧

Успіхів з аналізом! 🚀
