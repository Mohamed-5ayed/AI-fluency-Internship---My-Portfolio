### 1. Honest "Where It Breaks" List (قائمة الأخطاء ونقاط الضعف المكتشفة)
لقد قمت باختبار الموقع بعنف (إدخال بيانات فارغة، قيم عشوائية، الضغط المزدوج السريع، وتجربة شاشات مختلفة)، وهذه هي النتيجة:

| الحالة (Edge Case / Test) | المشكلة المكتشفة (What Broke) | التصنيف والقرار (Fix-Now vs. Known Limitation) |
| :--- | :--- | :--- |
| **إرسال الفورم فارغاً (Empty Submit)** | كان المتصفح يظهر تنبيه HTML افتراضي، لكن لم يكن هناك تنبيه مرئي واقع في التصميم. | **Fix-Now:** تمت إضافة خصائص `required` وتحسين رسائل التحقق (Validation). |
| **الضغط المزدوج على زر الإرسال (Double Submit)** | إمكانية الضغط على زر الإرسال مرتين متتاليتين قبل اكتمال الاستجابة. | **Fix-Now:** إضافة حالة تعطيل الزر (Button Disabled State + Loading Text) أثناء عملية الإرسال لمنع الإرسال المزدوج. |
| **فتح الموقع من متصفح هاتف قديم / ضيق للغاية** | بعض الهوامش (Margins) كانت تلتصق بحواف الشاشة بشكل غير مريح بصرياً. | **Fix-Now:** تحديث قواعد الـ CSS Media Queries لزيادة الحشو الجانبي (Padding). |
| **البحث عن الموقع محلياً وسرعة التحميل** | غياب وصف الـ SEO ووسوم المعاينة، وبطء بسيط بسبب حجم صور المشاريع الكبيرة. | **Fix-Now:** إضافة وسوم الـ Meta Tags وضغط الصور. |
| **سلوك غير متوقع عند انقطاع الإنترنت فجأة أثناء الإرسال** | لا يظهر للمستخدم تنبيه يفيد بفشل الاتصال بالشبكة مؤقتاً. | **Known Limitation:** سيتم معالجتها في التحديث القادم عبر إضافة Catch Block متقدم لإدارة الأخطاء الشبكية. |

---

### 2. Basic SEO & Meta Tags Added (تحسين محركات البحث والبيانات الوصفية)
تمت إضافة الوسوم التالية داخل قسم `<head>` لضمان ظهور الموقع بشكل احترافي عند مشاركته على وسائل التواصل وسهولة أرشفته:
```html
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Mohamed | Frontend Developer & AI Student</title>
<meta name="description" content="Portfolio of Mohamed, a computer science student specializing in Artificial Intelligence and front-end web development.">
<!-- Open Graph / Social Share Preview -->
<meta property="og:title" content="Mohamed | Frontend Developer & AI Student">
<meta property="og:description" content="Explore my projects, web apps, and AI integrations.">
<meta property="og:type" content="website">