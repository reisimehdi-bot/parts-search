# آپدیت موجودی قطعات

این ریپو فقط برای **به‌روزرسانی روزانه موجودی** است.  
کاتالوگ کامل داخل `index.html` است؛ اینجا فقط عدد موجودی (`stock`) عوض می‌شود.

## فایل‌های مهم

| فایل | توضیح |
|------|--------|
| `stock.csv` | **فایل اصلی روزانه** — کد کالا + موجودی (UTF-8) |
| `stock_update.json` | پشتیبان همان موجودی‌ها (اختیاری) |
| `index.html` | سایت جستجو |

## کار روزانه روی ویندوز (Excel)

1. فایل `stock.csv` را از GitHub دانلود کنید.
2. با **Excel** باز کنید.
3. فقط ستون `stock` را تغییر دهید (ستون `code` را دست نزنید).
4. ذخیره:
   - **File → Save As**
   - نوع فایل: **CSV UTF-8 (Comma delimited) (*.csv)**
   - اگر این گزینه نبود: **CSV (Comma delimited)** سپس با Notepad به UTF-8 ذخیره کنید.
5. همان فایل را در GitHub جایگزین کنید (Upload file → Commit).
6. ۳۰–۶۰ ثانیه صبر کنید، سپس سایت را با **Ctrl+F5** باز کنید.

### فرمت صحیح

```text
code,stock
2000-CAP-0001,20
2000-CAP-0002,3175
2000-CAP-0003,0
```

- هدر حتماً `code,stock` باشد.
- ردیف خالی نگذارید.
- برای «ناموجود» می‌توانید خالی بگذارید یا `0` بنویسید (از `-` استفاده نکنید).
- کد ناقص مثل `1000` یا `3000` alone نگذارید.

## کار با گوشی

- با Google Sheets یا Excel موبایل باز کنید.
- Export / Download به‌صورت **CSV**.
- در GitHub آپلود کنید.

## تنظیم آدرس در سایت

داخل `index.html`:

```javascript
var GITHUB_STOCK_CSV_URL = "https://raw.githubusercontent.com/reisimehdi-bot/parts-search/main/stock.csv";
var GITHUB_STOCK_JSON_URL = "https://raw.githubusercontent.com/reisimehdi-bot/parts-search/main/stock_update.json";
```

`GITHUB_DATA_URL` را خالی بگذارید.

## اولویت بارگذاری موجودی

1. `stock.csv` از GitHub  
2. اگر نبود → `stock_update.json`  
3. اگر نبود → کش مرورگر  
4. در نهایت → موجودی داخل `index.html`

## نکات

- کد کالا باید دقیقاً با کد داخل سایت یکی باشد.
- کالای **جدید** با CSV اضافه نمی‌شود؛ باید `index.html` را به‌روز کنید.
- ریپو را **Public** نگه دارید.
- بعد از Commit گاهی ۳۰–۶۰ ثانیه طول می‌کشد تا `raw.githubusercontent.com` به‌روز شود.
- اگر موجودی عوض نشد: Ctrl+F5 یا پنجره ناشناس (Incognito).
