# Files 04-N – ملف لكل مستخدم: "<الدور> — المميزات ورحلة المستخدم"

**One file per agreed user type, and nothing else for journeys.** Do NOT create separate structure or detailed-journey
files: everything about this user (features + every screen + every edge case) lives in this one file.
Output name: `04-<N> <الدور> — المميزات ورحلة المستخدم` (N = 1, 2, 3… in the order of the agreed users).

The model is the user's reference file "حارس البوابة — المميزات ورحلة المستخدم". Set `"theme": "role"` in the JSON:
Sans Arabic font, blue Word-style headings (h1 with a rule under it, h2, h3 dark blue, h4 italic), bold key phrases
inside sentences, grey table headers, thin dividers between sections.

## Writing rules
- **Modern Standard Arabic, narrative, present tense**: "يضغط على **الوردية**. فتفتح شاشة تحتوي في أعلاها على …".
  Every action → what opens → what he sees → what each button does.
- **Bold** (`**…**`) the screen names, button actions and the start of every condition: `**إذا كان الرمز خاطئاً:**`.
- Button labels and on-screen messages in double quotes: زر "ابدأ"، رسالة "لا يوجد اتصال.".
- Variable values in square brackets: [اسم الزائر]، [عدد]، [الوقت].
- Every screen ends with one **"حالات <الشاشة>:"** paragraph covering: الفارغة (a sentence + the main action, never a
  blank page) · التحميل (grey placeholders, main action never delayed) · الخطأ (message + "إعادة المحاولة") ·
  دون اتصال (what still works, what waits for sync).
- Privacy, permissions and "who sees what" are stated inside the journey where they matter.
- Be exhaustive: a role file is typically 10–25 pages. No "إلخ"، no summaries.
- Content must follow the discussion: this user's agreed MVP + ⭐ features; ⏳ features only in the roadmap line.

## Structure (in this exact order)

### Header
```json
{"type":"h1","text":"<الدور> — المميزات ورحلة المستخدم","before":0},
{"type":"meta","items":[
  {"label":"التطبيق","text":"<اسم المنتج>"},
  {"label":"الواجهة","text":"تطبيق موبايل ميداني — يعمل دون اتصال"},
  {"label":"الكروت","text":"الدخول · الوردية · الجولات · …"},
  {"label":"شريط التنقل","text":"الشات · الإعدادات — الرئيسية — البحث · المساعد"},
  {"label":"عدد المميزات","text":"<العدد الفعلي لنقاط القسم الأول>"}]},
{"type":"divider"}
```

### القسم الأول — المميزات
`h1` "القسم الأول — المميزات"، then for every card of the home screen (and finally the assistant / nav-bar items):
`h2` card name → for every group inside it `subtitle` (bold) → `bullets` (short noun phrases, one feature each).
Count all bullets and put the number in the header "عدد المميزات".

### القسم الصفري — أنواع الدور وحالاته الاستثنائية
- `paragraph` "إجابات الأسئلة الستة قبل كتابة الرحلة:" and `subtitle` "والسؤال الصفري: هل هذا الدور نوع واحد أم أنواع؟"
- `table` (`"header_style":"grey"`) headers: النوع | ما يميّزه | ما يختلف في شاشاته — one row per sub-type of this role
  (e.g. main gate guard / service gate guard / patrol guard / shift supervisor).
- `paragraph`: "والفروق أعلاه موصوفة داخل الرحلة نفسها — وتُعلن هنا ليعرفها المصمم والمطوّر قبل البدء لا بعده."
- `table` (grey) headers: السؤال | ما استُخرج — exactly these six questions:
  1. ما الذي يبدأ وينتهي في عمله؟
  2. هل يشارك غيره في نفس الصلاحية؟
  3. ماذا لو كان هو الطرف المعني بالقرار؟
  4. ما الذي يخفيه أو يصفّيه ثم يعود إليه؟
  5. ما الذي قد ينفد أو يُسحب؟
  6. ما الذي لا يجوز أن يتوقف مهما حدث؟
  (+ optional 7: ما الإعدادات التي يضبطها وقد تتعارض؟) – answers are short "·"-separated lists.
- `paragraph` "وتُوصف هذه كلها في القسم السابع."

### القسم الثاني — رحلة البداية
First launch → splash → login/registration fields (in order) → verification → permissions (camera / location /
notifications, each with its one-sentence reason and the alternative if refused) → first-time setup → arrival at home.
Every field's validation error and every failure (wrong code, expired code, no connection) as bold conditions.
Include data preparation for offline use if the product works offline.

### القسم الثالث — الصفحة الرئيسية
Top bar (name, context, connection indicator) → the big primary card → the other cards and their badges → nav bar
(exact order and position of items) → always-visible elements (e.g. emergency button).
Then `h3` "حالات الصفحة الرئيسية" with الفارغة / التحميل / الخطأ / دون اتصال as bold-led paragraphs.

### القسم الرابع — رحلة الكروت
For each card: `h2` "الكارت الأول: <الاسم>" → opening paragraphs (what the screen shows) → `h3` per flow inside it
→ `h4` for special cases worth their own heading (e.g. "الزائر يقول إنه صاحب الوحدة"). Every flow: happy path,
every branch (`**إذا …:**`), what is logged and who is notified, and its "حالات …" paragraph.

### القسم الخامس — عناصر شريط التنقل
`h2` per item (البحث، الشات، الإشعارات، الإعدادات، المساعد…) with the same narrative detail.

### القسم السادس — دورة حياة الاستخدام
`h2` each: الفتح اللاحق · الدخول من إشعار · طلب إذن الإشعارات · انتهاء الجلسة · التحديث الإلزامي · تبديل السياق ·
المزامنة · الخروج.

### القسم السابع — سيناريوهات <طبيعة الاستخدام>
Intro sentence on who this applies to, then `h2` per scenario relevant to this role and product, e.g.: نفاد البطارية ·
الجهاز البديل أو المشترك · شخصان على نفس الصلاحية · الوردية/الجلسة الممتدة · إعادة تشغيل التطبيق أثناء عملية ·
امتلاء الذاكرة المحلية · تعارض البيانات بين جهازين · تغيّر الصلاحية أثناء العمل · تعارض الإعدادات أو التعليمات.
Each: what he sees, what the system does automatically, what is never lost.

### القسم الثامن — إمكانية الوصول في كل شاشة
`bullets`: touch target sizes, font scaling, contrast (incl. outdoor / dim warehouse), screen reader labels, voice input,
one-hand use, colour never the only signal, haptic/sound confirmations, RTL correctness.

### القسم التاسع — القياس
`table` (grey) headers: المؤشر | كيف يُقاس | الهدف — 6–10 metrics for this role (time to complete the main task,
error rate, offline share, adoption after 2 weeks, …).

Put a `divider` before every `h1` from القسم الصفري onward.
