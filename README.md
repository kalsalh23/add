# أطباء طيبة الأمام 🩺

منصة من واجهة واحدة لجمع بيانات الأطباء وإرسالها مباشرة إلى قاعدة بيانات **Supabase** لاستخدامها لاحقاً.

## الروابط

- الموقع المنشور (Vercel): https://tayba-doctors.vercel.app
- المستودع (GitHub): https://github.com/kalsalh23/add
- لوحة مشروع Vercel: https://vercel.com/kalsalh23s-projects/tayba-doctors

## الواجهة

نموذج واحد يجمع البيانات التالية:

| الحقل | العمود في قاعدة البيانات |
|------|--------------------------|
| 👨‍⚕️ الاسم | `name` |
| 🩺 الاختصاص | `specialty` |
| 📍 الموقع | `location` |
| 📅 أيام الدوام | `work_days` (مصفوفة، اختيار الأيام من القائمة) |
| 🕐 أوقات الدوام | `work_times` |
| 🚫 يوم العطلة | `day_off` |
| 📞 رقم التواصل | `phone` |

عند الضغط على زر **«إرسال البيانات»** يُضاف السجل إلى جدول `doctors` في Supabase عبر REST API.

## قاعدة البيانات (Supabase)

- الجدول: `public.doctors` (id, name, specialty, location, work_days[], work_times, day_off, phone, created_at)
- مفعّل **Row Level Security** مع سياسة تسمح **بالإضافة (insert)** للدور `anon`.
- رابط المشروع ومفتاح `anon` موجودان داخل `index.html`؛ وهما مصمّمان للاستخدام العلني من جهة العميل ولا يكشفان بيانات الجدول.

## بنية المشروع

```
tayba-doctors/
├── index.html   # الواجهة الكاملة (HTML + CSS + JavaScript — صفحة واحدة)
├── README.md
└── .gitignore
```

## النشر

المشروع منشور على Vercel ومرتبط بهذا المستودع على فرع `main`؛ أي تحديث يُرفع إلى المستودع يُنشر تلقائياً على الموقع.
