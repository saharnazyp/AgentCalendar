<div dir="rtl">

# 📅 Calendar & Meeting Agent — دستیار تقویم و جلسات

ایجنت مدیریت تقویم و جلسات دفتر مدیرعامل، ساخته‌شده روی **Google Apps Script**.
شامل سه ماژول مستقل:

| ماژول | فایل | کار |
|------|------|-----|
| گزارش روزانه | `src/DailySummary.gs` | خواندن جلسات امروز، خلاصه‌سازی با هوش مصنوعی و ارسال به تلگرام + ایمیل |
| همگام‌سازی رنگ | `src/ColorSync.gs` | کپی رنگ و وضعیت busy رویدادها روی تقویم رییس |
| مانیتور جلسات | `src/MeetingMonitor.gs` + `src/Index.html` | داشبورد زنده با شمارش معکوس، مهمان‌ها، لینک و فایل‌های پیوست |

---

#
---

## 🚀 راه‌اندازی سریع

۱. یک پروژه‌ی Apps Script بسازید (script.google.com).
۲. فایل‌های پوشه‌ی `src/` را در پروژه قرار دهید.
۳. در **Project Settings → Script Properties** این کلیدها را وارد کنید:

</div>

```
TELEGRAM_BOT_TOKEN   = توکن جدید بات
CHAT_ID              = @آدرس کانال شما 
BOSS_CALENDAR_ID     = ایمیل دریافت کننده جلسات 
RECIPIENT_EMAIL      = a@example.com, b@example.com
BOSS_EMAIL           = boss@example.com
```

<div dir="rtl">

۴. سرویس پیشرفته‌ی **Google Calendar API** را فعال کنید (Services → ＋ → Calendar).
۵. تابع `createDailyTrigger` را یک‌بار اجرا کنید تا تریگر روزانه‌ی ساعت ۷ صبح ساخته شود.
۶. برای مانیتور: **Deploy → New deployment → Web app**.

راهنمای کامل گام‌به‌گام در [`docs/setup.md`](docs/setup.md).

## 📂 ساختار

</div>

```
calendar-meeting-agent/
├── README.md
├── LICENSE
├── .gitignore
├── .clasp.json.example
├── src/
│   ├── appsscript.json      ← manifest (timezone, advanced services, scopes)
│   ├── Config.gs            ← خواندن تنظیمات از Script Properties
│   ├── Helpers.gs           ← توابع مشترک
│   ├── DailySummary.gs      ← گزارش روزانه تلگرام/ایمیل
│   ├── ColorSync.gs         ← همگام‌سازی رنگ تقویم
│   ├── MeetingMonitor.gs    ← بک‌اند مانیتور جلسات
│   └── Index.html           ← داشبورد مانیتور
└── docs/
    └── setup.md
```

<div dir="rtl">

## 📝 مجوز

[MIT](LICENSE)

</div>
