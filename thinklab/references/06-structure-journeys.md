# Stage 6 – الهيكل الرئيسي ورحلات المستخدمين

Output: one file per user type: `07 الهيكل ورحلة <نوع المستخدم> - <اسم المشروع>`
(e.g. رحلة مدير المخزن، رحلة أمين المخزن، رحلة المشتريات). Visual style: reference file 01.

## Content (follow this order exactly)
1. `basmala`.
2. `intro` "عند بداية استخدام التطبيق": the two entry paths – new user (`[[cyan:مستخدم جديد]]`: registration form →
   approval → what appears → privacy consent → a proud, exciting welcome message) and existing user (phone/code login →
   welcome message → main screen with `[[red:N أيقونات]]`).
3. One `module` per main icon of the home screen (4–6 modules): label = module name, text = "هذا الملف يكون خاصًا بـ ... يشمل:",
   `list` = everything inside it, `goal` = how the user should feel. Add `must` lines after modules that touch money,
   personal data, or legal obligations.
4. `banner(cyan_white)` "رحلة <نوع المستخدم> داخل <الملف الأهم>": describe the first screen of that module
   (cards, what each card shows), then the quick-glance areas (like "اطمئن سريعا" / "طلبات سريعة" / "بين يديك")
   with `paragraph` blocks.
5. `banner(yellow)` "الرحلات داخل الملفات": one `journey` per sub-journey (6–12): name in cyan, what the user sees,
   what happens on tap, example messages, and `buttons`. Include the status lifecycle for any request
   (جديد / قيد المراجعة / مقبول / مرفوض / يحتاج تعديل).
6. Repeat 4–5 for the other main modules if they have distinct journeys.
7. Final `banner(cyan_white)` closing sentence: "انتهت رحلته داخل ..." with what comes next.
