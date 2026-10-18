# File 06 – تحليل السوق

Output file: `06 تحليل السوق - <اسم المشروع>`. Visual style: reference file 00 + tables.

## Research (mandatory)
Use web search. Run several searches in parallel, in Arabic and English, for the target country and region:
market size and growth of the category, number of target businesses/users (official statistics agencies such as
CAPMAS in Egypt, GASTAT in Saudi Arabia), digital adoption, regulations (e-invoicing, data protection), investment and
startup activity in the space, recent news (last 2 years). Prefer official statistics, reputable research firms and news.
Every number must have a source; if none is found, say "تقدير" and show the calculation.

## Content
1. **ملخص السوق** – one paragraph verdict: is the market attractive now and why.
2. **حجم السوق** – table: TAM / SAM / SOM with value, how it was calculated, source. SOM = realistic 3-year share.
3. **شرائح العملاء** – table: الشريحة، الحجم التقريبي، الألم الأساسي، القدرة على الدفع، الأولوية.
4. **اتجاهات السوق** – `point` blocks (digital transformation, regulations, AI, e-commerce growth…).
5. **المحركات والعوائق** – two `item` blocks with lines.
6. **القوانين والتنظيمات** – `must` blocks.
7. **فرصة الدخول** – where to start (city / segment / channel) and why.
8. `sources` block.

## Block skeleton
```
banner(yellow) "تحليل السوق: <اسم المشروع> – <الدولة>"
paragraph
table "حجم السوق"
table "شرائح العملاء"
banner(cyan_white) "اتجاهات السوق" → point × n
banner(cyan_white) "المحركات والعوائق" → item × 2
banner(yellow) "يجب مراعاة" → must × n
banner(cyan_white) "فرصة الدخول" → paragraph / point
sources
```
