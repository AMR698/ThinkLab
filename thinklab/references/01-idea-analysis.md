# File 01 – تحليل الفكرة وما يجب مراعاته

Output file: `01 تحليل الفكرة - <اسم المشروع>`. Visual style: reference file 00 (yellow/cyan banners, `ؐ` points, `֎` items).

## What to analyse
1. **الفكرة باختصار** – one strong paragraph: who, what problem, what the product does.
2. **المشكلة** – real pains of the target users today (manual work, losses, delays, lack of visibility…).
3. **الفئة المستهدفة** – every agreed user type that will touch the product (decision maker, daily operator, manager,
   accountant, customer, driver…) in `[[cyan:..]]`. Also the buyer vs the user.
4. **الحل والقيمة المضافة** – why this is better than what they do today; the "wow" angle.
5. **أفكار واقعية تُضاف للمشروع** – 8–15 concrete, buildable additions that make the idea stronger
   (each: what it is + why it matters). Mark the strongest with `[[hl:..]]`.
6. **SWOT** – four `item` blocks: نقاط القوة / نقاط الضعف / الفرص / التهديدات.
7. **المخاطر وكيف نتعامل معها** – technical, market, legal, adoption.
8. **يجب مراعاة الآتي** – UX and trust rules for this specific product, written like reference file 00:
   empty states, permissions per role, error/status messages, offline behaviour, notifications, security settings,
   accessibility. Then legal/financial constraints with `must`.
9. **مقترح أن يكون في الناف بار** – the suggested navigation bar items with `item` blocks and their contents.
10. **الحكم المبدئي** – feasibility score out of 10 with reasons, and the recommended MVP scope in one paragraph.

## Block skeleton
```
banner(yellow) "تحليل فكرة: <اسم المشروع>"
paragraph – الفكرة باختصار
banner(cyan_white) "المشكلة"            → point × n
banner(cyan_white) "الفئة المستهدفة"      → point × n
banner(cyan_white) "الحل والقيمة المضافة" → paragraph / point
banner(cyan_white) "أفكار واقعية تُضاف للمشروع" → item × 8–15
banner(cyan_white) "تحليل SWOT"          → item × 4 (lines for each bullet)
banner(cyan_white) "المخاطر"            → point × n
banner(yellow) "يجب مراعاة الآتي"         → point × n, must × n
banner(cyan) "مقترح أن يكون في الناف بار" → item × n
banner(cyan_white) "الحكم المبدئي"        → paragraph
```

This file is written AFTER the discussion (`00-discovery.md`). Use the agreed assumptions, the agreed user types
(section 3 lists exactly them, ⏳ later users marked as such) and put the user's chosen ⭐ ideas and cross-cutting ideas
in section 5. Do not re-ask questions here.
