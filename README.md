# تِجارتي · كتالوج الهوية البصرية

13 اتجاه بصري كامل لتطبيق تِجارتي — جاهز للنشر على Vercel.

## الملفات

```
tijarti-deploy/
├── index.html      ← الكتالوج الكامل (single-file، self-contained)
├── vercel.json     ← إعدادات Vercel (security headers + cache)
├── robots.txt      ← منع محرّكات البحث من الفهرسة
└── README.md       ← هذا الملف
```

## كيف ترفعه على Vercel · 3 طرق

### الطريقة 1 · الأسهل (Drag & Drop) ⭐

1. ادخل [vercel.com/new](https://vercel.com/new)
2. سجّل دخول (أو أنشئ حساب — مجاني)
3. اضغط **"Deploy without Git"** (أو ابحث عن "Browse all templates" → "Other")
4. اسحب مجلّد `tijarti-deploy` كاملاً وأفلته
5. سمّ المشروع: مثلاً `tijarti-catalog` أو `tijarti-brand`
6. اضغط **Deploy**

النتيجة: لينك مثل `https://tijarti-catalog.vercel.app` خلال 30 ثانية. هذا اللينك تشاركه مع الناس.

### الطريقة 2 · Vercel CLI (للمطوّرين)

```bash
npm install -g vercel
cd tijarti-deploy
vercel
```

اتبع الأسئلة. أوّل مرّة بيسأل عن إعدادات المشروع — اضغط Enter لكل سؤال (الإعدادات الافتراضية تعمل).

للنشر النهائي (production):
```bash
vercel --prod
```

### الطريقة 3 · GitHub + Vercel (للتحديثات المستمرّة)

1. أنشئ repo جديد على GitHub، ارفع محتويات `tijarti-deploy/` فيه
2. ادخل [vercel.com/new](https://vercel.com/new) → اختر **Import Git Repository**
3. اختر الـrepo، اضغط Deploy

كل مرّة تـcommit بـGitHub، Vercel ينشر تلقائياً نسخة جديدة.

## بعد النشر

### لو بدّك دومين مخصّص
في Vercel Dashboard → Project → Settings → Domains → أضف الدومين تبعك.

### لو بدّك حماية كلمة سرّ
Project → Settings → Deployment Protection → Vercel Authentication. هذا يخلّي اللينك متاح فقط لناس عندهم حساب Vercel — للقطاع الخاص فقط (في الخطّة المجانية، الميزة الأشمل بكلمة سرّ متاحة في Pro).

طريقة بديلة لقفل اللينك مجاناً: استخدم خدمة مثل [vercel-deploy-protect](https://github.com/) أو ضع HTTP Basic Auth بـVercel Edge Function.

### لجمع آراء الناس
اقترح هذه الأدوات (مجانية):
- **Tally.so** — استمارة تعليقات أنيقة، تنطبع بـRTL
- **Typeform** — استمارة تفاعلية
- **Google Forms** — الأبسط
- **Cal.com / Calendly** — حجز مكالمة لجلسة feedback مباشرة

ضع رابط الاستمارة بنهاية الكتالوج — أو في إيميل/واتساب مع لينك Vercel.

## ملاحظات تقنية

- الملف self-contained بالكامل — كل CSS وJavaScript جوّاه. ما في dependencies خارجية إلا fonts من Google Fonts (cached محلياً عند المستخدم).
- يعمل على Mobile + Desktop + Tablet.
- لا يحتاج build step. Vercel يخدمه كـstatic file مباشرة.
- Page weight ≈ 405KB (HTML + CSS + JS). Fonts إضافية حسب المتصفّح.
- لا يجمع أي بيانات. لا analytics بعد. لو بدّك تضيف Plausible أو Vercel Analytics لاحقاً، 5 دقائق شغل.

## التحديثات

كل ما عدّلت `index.html` (مثلاً غيّرت لون أو نصّ)، ارفع النسخة الجديدة:
- إذا CLI: `vercel --prod`
- إذا Git: `git push`
- إذا Drag & Drop: ادخل Project → Deployments → Create Deployment → اسحب الملف الجديد

النسخ القديمة بتفضل محفوظة في Vercel — تقدر ترجع لها أيّ وقت.
