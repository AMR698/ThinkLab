# Stage 7 – الرحلة التفصيلية شاشة بشاشة

Output: one file per main module (or per user type for small products):
`08 الرحلة التفصيلية - <اسم الملف> - <اسم المشروع>`. Visual style: the user's detailed journey reference
("ملف التعليم والتطوير").

## Content
1. Opening `paragraph`:
   "بصفتي خبير تجربة المستخدم (UX Specialist) ومصمم حلول الأنظمة، إليك الهندسة البنائية والتفكيك الإجرائي الكامل لرحلة
   <المستخدم> في "<الملف>"، مصممة باللهجة والثقافة <المصرية> الراقية والمألوفة، ومفككة بالكامل إلى شاشات، وأزرار،
   ووظائف فرعية، وحالات الخطأ والنجاح، دون دمج أو تلخيص:"
2. Phases with `phase` blocks: "المرحلة الأولى: <name> (<English name>)", "المرحلة الثانية: ..." … Typical phases:
   Onboarding & Setup → The Hub (main screen) → one phase per section/tab of the module → Notifications & Alerts →
   Settings/Permissions → Offline & Edge Cases.
3. Under each phase a `steps` block with 8–20 items. Each step is ONE sentence pattern:
   - "عند فتح/الدخول على ... يرى شاشة تحتوي على ..."
   - "يرى أسفل ... زر مكتوب عليه: \"<نص الزر باللهجة>\"."
   - "عند الضغط على زر \"...\"، تفتح له شاشة \"...\" تحتوي على ..."
   - `{"error": "عند ... يظهر نص أحمر أسفل الحقل: \"<الرسالة>\"."}` – auto-numbered across the file.
   - `{"success": "تفتح شاشة نجاح منبثقة تحتوي على علامة (صح) خضراء متحركة ونص: \"...\""}`
   Cover: empty states (motivating sentence, never a blank page), loading states, permission denied, no internet,
   validation errors, timeouts, and confirmation dialogs for destructive actions.
4. Every field: placeholder text (نص رمزي), validation rule, and its error message.
5. Every list: what each row/card shows, its colour badges and their meaning.
