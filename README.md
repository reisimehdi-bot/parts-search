# آپدیت موجودی قطعات

این ریپو فقط برای **به‌روزرسانی روزانه موجودی** است.  
کاتالوگ کامل داخل `index.html` سایت است؛ اینجا فقط عدد موجودی (`stock`) عوض می‌شود.

## فایل‌های مهم

| فایل | توضیح |
|------|--------|
| `stock.csv` | **فایل اصلی روزانه** — کد کالا + موجودی |
| `stock_update.json` | پشتیبان همان موجودی‌ها (اختیاری) |
| `index.html` | سایت جستجو (اگر از همین ریپو هاست می‌کنید) |

## کار روزانه (۱ دقیقه)

1. فایل `stock.csv` را باز کنید.
2. ستون `stock` را تغییر دهید.
3. ذخیره کنید (ترجیحاً UTF-8).
4. همین فایل را در GitHub آپلود / Commit کنید.

فرمت:

```text
code,stock
2000-CAP-0001,20
2000-CAP-0002,3175
2000-CAP-0003,0
```

## کار با گوشی اندروید

- با **Google Sheets** یا **Microsoft Excel** فایل `.csv` را باز کنید.
- بعد از ویرایش: Download / Export به‌صورت **CSV**.
- در GitHub دوباره آپلود کنید.

## تنظیم آدرس در سایت

داخل `index.html` این دو خط را با آدرس ریپوی خودتان پر کنید:

```javascript
var GITHUB_STOCK_CSV_URL = "https://raw.githubusercontent.com/reisimehdi-bot/reisimehdi-bot/main/stock.csv";
var GITHUB_STOCK_JSON_URL = "https://raw.githubusercontent.com/reisimehdi-bot/reisimehdi-bot/main/stock_update.json";
```

`GITHUB_DATA_URL` را خالی بگذارید تا کل کاتالوگ عوض نشود.

## اولویت بارگذاری موجودی در سایت

1. `stock.csv` از GitHub  
2. اگر نبود → `stock_update.json`  
3. اگر نبود → کش مرورگر  
4. در نهایت → موجودی داخل خود `index.html`

## نکات

- کد کالا (`code`) باید دقیقاً با کد داخل سایت یکی باشد.
- کالای **جدید** فقط با ویرایش CSV اضافه نمی‌شود؛ برای کالای جدید باید کاتالوگ (`index.html`) را یک‌بار به‌روز کنید.
- بعد از Commit گاهی ۳۰–۶۰ ثانیه طول می‌کشد تا آدرس `raw` به‌روز شود.
- ریپو را **Public** بگذارید تا `raw.githubusercontent.com` بدون توکن کار کند.

---

جزئیات بیشتر: فایل `راهنمای-آپدیت-موجودی.md`

