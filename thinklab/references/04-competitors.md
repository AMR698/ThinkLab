# File 06 – المنافسين

Output file: `06 المنافسين - <اسم المشروع>`.

## Research (mandatory)
Web-search for: local competitors in the target country, regional (MENA/GCC) players, global products used locally,
and indirect alternatives (Excel, paper, generic ERP, WhatsApp groups). Visit pricing pages where possible.
Aim for **6–12 competitors**. Record the date prices were checked. Never invent a price – write "غير معلن" if not public.

## Content
1. **ملخص المنافسة** – paragraph: how crowded, who leads, where the gap is.
2. **جدول المنافسين** – headers: المنافس، الدولة، النوع (مباشر/غير مباشر)، أهم المميزات، السعر، نقاط القوة، نقاط الضعف.
3. **مقارنة المميزات** – table: rows = 10–15 key features (including our AI/unique ones), columns = our product + top 4
   competitors, cells ✅ / ❌ / جزئي. Use `highlight_row` is not needed here; put our product as the first column.
4. **بطاقة لكل منافس رئيسي** – `item` per top 3–5 competitors: label = name, text = positioning, lines = strengths,
   weaknesses, pricing, what users complain about (from reviews when available).
5. **الفجوات التي نستغلها** – `point` blocks; strongest in `[[hl:..]]`.
6. **ميزتنا التنافسية** – paragraph: the one-line positioning statement + why it is hard to copy.
7. `sources`.

## Block skeleton
```
banner(yellow) "المنافسين: <اسم المشروع>"
paragraph
table "جدول المنافسين"
table "مقارنة المميزات"
banner(cyan_white) "أبرز المنافسين" → item × 3–5
banner(cyan) "الفجوات التي نستغلها" → point × n
banner(cyan_white) "ميزتنا التنافسية" → paragraph
sources
```
