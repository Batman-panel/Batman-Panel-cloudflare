# 🦇 Batman Panel — Cloudflare Edition

<p align="center">
  <b>🚀 A powerful VPN subscription & management panel running entirely on Cloudflare Workers.</b>
</p>

<p align="center">
  <b>یک پنل مدیریت و ساخت کانفیگ که به‌صورت کامل روی Cloudflare Workers اجرا می‌شود.</b>
</p>

<p align="center">

![Cloudflare Workers](https://img.shields.io/badge/Cloudflare-Workers-orange?style=for-the-badge\&logo=cloudflare)

![Cloudflare D1](https://img.shields.io/badge/Database-D1-blue?style=for-the-badge\&logo=cloudflare)

![Cloudflare KV](https://img.shields.io/badge/Storage-KV-yellow?style=for-the-badge\&logo=cloudflare)

![VLESS](https://img.shields.io/badge/Protocol-VLESS-purple?style=for-the-badge)

![Trojan](https://img.shields.io/badge/Protocol-Trojan-red?style=for-the-badge)

</p>

---

# 🌐 About the Project | درباره پروژه

## 🇬🇧 English

**Batman Panel — Cloudflare Edition** is a lightweight and self-contained VPN subscription and configuration management panel designed specifically for **Cloudflare Workers**.

The project does not require a VPS, Docker, Node.js server, or traditional web hosting.

Everything runs directly on Cloudflare.

The main application is contained in a single:

```text
Batman.js
```

file.

The project uses:

* ☁️ Cloudflare Workers for application runtime
* 🗄️ Cloudflare D1 for persistent database storage
* ⚡ Cloudflare KV for caching and temporary data
* 🔐 Secure authentication and sessions
* 🌐 VLESS & Trojan configuration generation
* 📦 Subscription management
* 🧪 Cloudflare IP testing
* 🤖 Personal Agent support
* ⚙️ Automatic IP optimization
* 📊 Usage and system monitoring

---

## 🇮🇷 فارسی

**Batman Panel — Cloudflare Edition** یک پنل سبک و کامل برای مدیریت کاربران، اشتراک‌ها و ساخت کانفیگ است که به‌صورت اختصاصی برای **Cloudflare Workers** طراحی شده است.

برای اجرای این نسخه نیازی به:

* ❌ VPS
* ❌ Docker
* ❌ Node.js Server
* ❌ هاست معمولی
* ❌ سرور لینوکس

ندارید.

کل پروژه مستقیماً روی Cloudflare اجرا می‌شود.

فایل اصلی پروژه:

```text
Batman.js
```

است و اطلاعات موردنیاز پروژه با استفاده از **D1** و **KV** ذخیره و مدیریت می‌شوند.

---

# ✨ Features | امکانات

### 👤 User Management

* Create users
* Edit users
* Delete users
* Enable / disable users
* Traffic limits
* Expiration dates
* Upload / Download statistics
* Connection limits
* Subscription management

### 🔐 Security

* Secure admin authentication
* PBKDF2-SHA256 password hashing
* Session management
* Secure cookies
* Login attempt protection
* Session expiration
* Password change support
* Security headers

### 🌐 Supported Configurations

**VLESS**

* WebSocket
* TLS
* Subscription
* QR Code
* Xray JSON

**Trojan**

* WebSocket
* TLS
* Subscription
* QR Code
* Xray JSON

### ⚡ Smart IP System

* Cloudflare IP discovery
* IP health checking
* Latency testing
* Jitter measurement
* Cloudflare location detection
* Healthy IP pool
* Automatic IP selection
* Personal IP optimization

### 🤖 Personal Agent

The optional Personal Agent can perform real network testing and report results back to the Cloudflare Worker.

It can test:

* VLESS
* Trojan
* Latency
* Stability
* Download samples
* Upload samples
* Egress information

---

# ☁️ Cloudflare Architecture

```text
                     ┌─────────────────────┐
                     │       Users         │
                     │ Browser / VPN Apps  │
                     └──────────┬──────────┘
                                │
                                ▼
                  ┌─────────────────────────┐
                  │   Cloudflare Workers    │
                  │      Batman Panel       │
                  └────────────┬────────────┘
                               │
                 ┌─────────────┴─────────────┐
                 │                           │
                 ▼                           ▼
        ┌────────────────┐         ┌────────────────┐
        │ Cloudflare D1  │         │ Cloudflare KV  │
        │    Database    │         │     Storage    │
        │      DB        │         │     CACHE      │
        └────────────────┘         └────────────────┘
```

---

# 🚀 Installation | نصب

## 🇬🇧 English

Setting up Batman Panel is very simple.

You only need:

```text
1 × Cloudflare Worker
1 × D1 Database
1 × KV Namespace
```

That's it. 🦇

---

## 🇮🇷 فارسی

راه‌اندازی Batman Panel بسیار ساده است.

فقط به این موارد نیاز دارید:

```text
1 × Cloudflare Worker
1 × D1 Database
1 × KV Namespace
```

یعنی برای اجرای نسخه Cloudflare پروژه فقط یک Worker، یک دیتابیس D1 و یک KV نیاز دارید.

---

# 1️⃣ Clone the Repository | دریافت پروژه

```bash
git clone https://github.com/Batman-panel/Batman-Panel-cloudflare.git
```

یا می‌توانید مستقیماً فایل `Batman.js` را از Repository دانلود کنید.

---

# 2️⃣ Create a Cloudflare Worker | ساخت Worker

وارد داشبورد Cloudflare شوید:

```text
Cloudflare Dashboard
        ↓
Workers & Pages
        ↓
Create Application
        ↓
Create Worker
```

یک Worker جدید ایجاد کنید.

سپس وارد بخش **Edit Code** شوید.

کد پیش‌فرض Worker را پاک کنید و محتوای:

```text
Batman.js
```

را جایگزین آن کنید.

سپس روی:

```text
Deploy
```

کلیک کنید.

---

# 3️⃣ Create D1 Database | ساخت دیتابیس D1

در Cloudflare وارد بخش:

```text
Workers & Pages
        ↓
Storage & Databases
        ↓
D1
        ↓
Create Database
```

یک D1 Database جدید بسازید.

برای مثال:

```text
batman-panel-db
```

می‌توانید هر نامی که می‌خواهید انتخاب کنید.

### Binding Name

هنگام اتصال D1 به Worker، نام Binding را دقیقاً قرار دهید:

```text
DB
```

⚠️ نام `DB` مهم است و باید دقیقاً همین باشد.

---

# 4️⃣ Create KV Namespace | ساخت KV

حالا وارد:

```text
Storage & Databases
        ↓
KV
        ↓
Create Namespace
```

شوید.

یک KV Namespace ایجاد کنید.

مثلاً:

```text
batman-cache
```

سپس آن را به Worker متصل کنید.

### Binding Name

نام Binding باید دقیقاً:

```text
CACHE
```

باشد.

⚠️ نام `CACHE` را تغییر ندهید.

---

# 5️⃣ Database Initialization | ساخت خودکار دیتابیس

یکی از مزیت‌های این نسخه این است که برای نصب اولیه نیازی ندارید Schema پروژه را به‌صورت دستی داخل D1 وارد کنید.

پس از اجرای Worker، پروژه جداول موردنیاز خود را ایجاد و مدیریت می‌کند.

ساختار کلی:

```text
Batman Panel
      │
      ├── DB
      │    └── Cloudflare D1
      │
      └── CACHE
           └── Cloudflare KV
```

---

# 6️⃣ First Login | اولین ورود

بعد از Deploy کردن Worker، آدرس Worker را باز کنید:

```text
https://YOUR-WORKER.workers.dev
```

در اولین اجرا، مراحل ایجاد حساب Administrator را انجام دهید.

⚠️ **Important**

در اولین اجرای پروژه حتماً حساب Administrator را سریع ایجاد کنید.

اگر Worker هنوز Claim نشده باشد، اولین شخصی که به Worker دسترسی پیدا کند می‌تواند فرآیند راه‌اندازی اولیه را انجام دهد.

---

# 7️⃣ Start Using Batman Panel | شروع استفاده

بعد از ورود به پنل می‌توانید:

```text
👤 Create Users
        ↓
🌐 Add Configurations
        ↓
📦 Create Subscription
        ↓
🔗 Generate Subscription Link
        ↓
📱 Connect with Client
```

کانفیگ‌های ساخته‌شده می‌توانند در قالب‌های مختلف در اختیار کاربر قرار بگیرند.

---

# 🔗 Subscription System | سیستم اشتراک

Batman Panel برای هر کاربر می‌تواند Subscription اختصاصی ایجاد کند.

امکانات:

* Subscription URL
* Unique subscription token
* VLESS links
* Trojan links
* QR Codes
* Xray JSON
* Multiple configurations
* Traffic information
* Expiration information

---

# 🌍 Cloudflare IP Testing | تست IP

پنل دارای سیستم بررسی IPهای Cloudflare است.

این سیستم می‌تواند اطلاعاتی مانند:

```text
Latency
Jitter
Success Rate
Cloudflare Colo
Region
Connection Stability
```

را بررسی کند.

همچنین پروژه بین **DNS Discovery** و **Real Network Testing** تفاوت قائل می‌شود.

یعنی صرفاً پیدا شدن یک IP توسط DNS به معنی سالم بودن آن IP نیست.

---

# 🤖 Personal Agent | ایجنت شخصی

برای تست واقعی‌تر شبکه، پروژه از **Personal Agent** نیز پشتیبانی می‌کند.

Agent می‌تواند IPها را از شبکه واقعی تست کرده و نتیجه را به Worker ارسال کند.

این قابلیت می‌تواند برای بررسی:

* VLESS
* Trojan
* Latency
* Stability
* Download
* Upload
* Egress

استفاده شود.

---

# ⚙️ Automatic Optimization | بهینه‌سازی خودکار

Batman Panel می‌تواند IPهای انتخاب‌شده را دوباره بررسی کند و در صورت نیاز گزینه مناسب‌تری انتخاب کند.

حالت‌های بهینه‌سازی شامل:

```text
latency
balanced
speed
```

هستند.

هدف این سیستم جلوگیری از تعویض بی‌دلیل IP و انتخاب IPهای مناسب‌تر بر اساس نتایج تست است.

---

# ⏱️ Cron Trigger | اجرای خودکار

برای اجرای عملیات Maintenance می‌توانید یک Cron Trigger نیز برای Worker تنظیم کنید.

پیشنهاد:

```text
*/5 * * * *
```

این Trigger می‌تواند برای عملیات‌هایی مانند:

* پاک کردن Sessionهای قدیمی
* پاک کردن Jobهای منقضی
* مدیریت داده‌های موقت
* Maintenance

استفاده شود.

---

# 📦 Project Structure | ساختار پروژه

پروژه عمداً بسیار ساده نگه داشته شده است:

```text
Batman-Panel-cloudflare/
│
└── Batman.js
```

تقریباً تمام منطق پروژه در همین Worker قرار دارد.

---

# 🔧 Required Bindings | Bindingهای موردنیاز

این قسمت بسیار مهم است.

| Service       | Binding |
| ------------- | ------- |
| Cloudflare D1 | `DB`    |
| Cloudflare KV | `CACHE` |

پس تنظیم نهایی Worker باید به شکل زیر باشد:

```text
DB      → Your D1 Database
CACHE   → Your KV Namespace
```

---

# ❌ No VPS Required | بدون نیاز به VPS

یکی از مهم‌ترین ویژگی‌های این نسخه:

```text
❌ VPS
❌ Docker
❌ Ubuntu Server
❌ Node.js Server
❌ npm install
❌ Nginx
❌ Apache
```

لازم نیست.

فقط:

```text
Cloudflare Worker
        +
D1
        +
KV
```

و پروژه آماده اجرا است. 🚀

---

# 🔄 Updating | بروزرسانی

برای بروزرسانی پروژه:

1. آخرین نسخه `Batman.js` را دریافت کنید.
2. کد Worker فعلی را باز کنید.
3. کد جدید را جایگزین کنید.
4. روی `Deploy` کلیک کنید.
5. D1 قبلی را نگه دارید.
6. KV قبلی را نگه دارید.

**D1 و KV را هنگام آپدیت حذف نکنید.**

---

# ⚠️ Important Notes | نکات مهم

Cloudflare دارای محدودیت‌ها و Quotaهای مخصوص خود است.

میزان مصرف و محدودیت‌ها به Plan و شرایط فعلی حساب Cloudflare بستگی دارد.

قبل از استفاده سنگین، مصرف:

```text
Workers
D1
KV
Requests
CPU Time
```

را از داشبورد Cloudflare بررسی کنید.

---

# 🦇 Why Batman Panel?

## 🇬🇧

A complete panel without the complexity of a traditional server.

```text
One Worker
+
One D1
+
One KV
=
Batman Panel 🦇
```

## 🇮🇷

بدون دردسر VPS و نصب‌های پیچیده، پنل را مستقیماً روی Cloudflare اجرا کنید.

```text
یک Worker
+
یک D1
+
یک KV
=
Batman Panel 🦇
```

---

# ⭐ Support the Project | حمایت از پروژه

اگر پروژه برای شما مفید بود، با دادن یک ⭐ به Repository از پروژه حمایت کنید.

**GitHub Repository:**

https://github.com/Batman-panel/Batman-Panel-cloudflare

---

# 🦇 Batman Panel

<p align="center">
  <b>Fast • Simple • Cloudflare Powered</b>
</p>

<p align="center">
  Made for the Cloud. Built for Batman. 🦇
</p>
