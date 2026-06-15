# DoA Matrix® — مصفوفة الصلاحيات المؤسسية

[![Netlify Status](https://api.netlify.com/api/v1/badges/YOUR_BADGE_ID/deploy-status)](https://app.netlify.com/sites/YOUR_SITE_NAME/deploys)

> أداة احترافية لبناء مصفوفة فصل الصلاحيات وفق الأنظمة السعودية والمعايير الدولية.

**© المعتصم الماضي — جميع الحقوق محفوظة**

---

## نظرة سريعة

| الخاصية | القيمة |
|---------|--------|
| الإصدار | v22 |
| الحجم | 296 KB — ملف واحد |
| المتطلبات | أي متصفح حديث |
| الخادم | لا يوجد — Client-Side بالكامل |
| البيانات | localStorage محلي فقط |

---

## هيكل المشروع

```
doa-matrix/
├── index.html          ← الأداة الكاملة (ملف واحد)
├── netlify.toml        ← إعدادات Netlify
├── .gitignore
├── README.md
└── .github/
    └── workflows/
        └── deploy.yml  ← GitHub Actions (اختياري)
```

---

## النشر على Netlify

### الخيار A — GitHub + Netlify (موصى به) ✅

**أفضل خيار:** تحديث تلقائي عند كل push.

#### الخطوة 1 — رفع المشروع على GitHub

```bash
# في مجلد المشروع
git init
git add .
git commit -m "initial: DoA Matrix v22"
git branch -M main
git remote add origin https://github.com/USERNAME/doa-matrix.git
git push -u origin main
```

#### الخطوة 2 — ربط Netlify بـ GitHub

1. اذهب لـ [app.netlify.com](https://app.netlify.com)
2. اضغط **Add new site → Import an existing project**
3. اختر **Deploy with GitHub**
4. اختر repository: `doa-matrix`
5. إعدادات البناء:
   - **Branch:** `main`
   - **Build command:** *(اتركه فارغاً)*
   - **Publish directory:** `.`
6. اضغط **Deploy site**

#### الخطوة 3 — تخصيص الرابط (اختياري)

في **Site settings → Domain management → Custom subdomain:**
```
doamatrix → https://doamatrix.netlify.app
```

---

### الخيار B — Drag & Drop (أسرع للنشر الأولي)

1. اذهب لـ [app.netlify.com/drop](https://app.netlify.com/drop)
2. اسحب مجلد `doa-matrix` كاملاً وأفلته
3. احصل على رابطك في 10 ثوانٍ

---

### الخيار C — Netlify CLI

```bash
# تثبيت CLI
npm install -g netlify-cli

# تسجيل الدخول
netlify login

# نشر أولي
netlify deploy --dir . --prod

# تحديثات لاحقة
netlify deploy --dir . --prod
```

---

## التحديث في المستقبل

### مع GitHub (تلقائي):
```bash
# عدّل index.html
git add index.html
git commit -m "update: وصف التعديل"
git push
# Netlify يتحدث تلقائياً في 30 ثانية
```

### بدون GitHub (يدوي):
1. عدّل `index.html`
2. اذهب لـ Netlify → Deploys → **Drag and drop**
3. اسحب المجلد مجدداً

---

## إدارة أكواد الدعوة

أكواد الدخول موجودة في `index.html` في متغير `INVITE_CODES`.

للبحث عنها:
```
Ctrl+F → INVITE_CODES
```

لإضافة كود جديد:
```javascript
"NEWCODE-25": { label:"اسم المدعو", org:"الجهة", role:"user", used:false },
```

بعد التعديل → ارفع الملف مجدداً على GitHub → Netlify يتحدث تلقائياً.

---

## قراءة سجلات الزوار

افتح الموقع في المتصفح → F12 → Console → اكتب:

```javascript
// سجل الزوار
showAdminLog()

// سجل الملاحظات
showFeedbackLog()

// مسح الجلسة الحالية
clearMySession()
```

---

## الأمان

- لا بيانات تُرسَل لأي خادم خارجي
- كل المعالجة في المتصفح (Client-Side)
- localStorage فقط — لا cookies — لا tracking
- Security headers مُفعَّلة عبر `netlify.toml`

---

## المراجع التنظيمية

- نظام الشركات السعودي 1443هـ
- لائحة حوكمة الشركات — CMA 1444هـ
- دليل حوكمة البنوك — SAMA 2022
- الدليل الاسترشادي — قرار مجلس الوزراء 92/2024
- مبادئ OECD 2023 + ISO 37000

---

*DoA Matrix® v22 | كتالوج 2025.5 | © المعتصم الماضي*
