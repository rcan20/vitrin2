# ویترین ۲ (vitrin2)

فروشگاه نمایشی: فرانت‌اند ساده (HTML/JS) + بک‌اند Django.

```
vitrin2/
├── frontend/index.html   # صفحه فروشگاه
└── backend/              # Django API (محصولات، کد تخفیف، سفارش)
```

## اجرا

### ۱) بک‌اند
```bash
cd backend
python -m venv venv
source venv/bin/activate          # ویندوز: venv\Scripts\activate
pip install -r requirements.txt
python manage.py migrate
python manage.py seed_demo        # محصولات نمونه + کد تخفیف OFF10
python manage.py createsuperuser
python manage.py runserver        # http://127.0.0.1:8000
```

### ۲) فرانت‌اند (ترمینال دوم)
```bash
cd frontend
python -m http.server 5500
```
بعد باز کن: http://127.0.0.1:5500

> فایل را با دوبار کلیک (`file://`) باز نکن؛ CORS اجازه نمی‌دهد.

## تنظیمات
- آدرس بک‌اند: `const API` در `frontend/index.html`
- آدرس فرانت: متغیر محیطی `CORS_ALLOWED_ORIGINS` (پیش‌فرض: پورت ۵۵۰۰)
- ارسال رایگان/هزینه ارسال: `backend/config/settings.py` و `const FREE/SHIP` در فرانت (باید یکی باشند)

جزئیات API: `backend/README.md`
