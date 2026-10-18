# File 07 – التسعير

Output file: `07 التسعير - <اسم المشروع>`.

Build on the competitor prices from file 06 (research more if needed). Use the **local currency** of the target market
and show USD in brackets where useful. State the exchange rate and date used.

## Content
1. **ملخص التسعير** – recommended model in one paragraph.
2. **نماذج التسعير المناسبة** – `item` per model (اشتراك شهري/سنوي لكل مستخدم، لكل مخزن/فرع، حسب حجم العمليات،
   Freemium، رسوم إعداد، عمولة، ترخيص دائم…) with pros/cons for this market. Mark the recommended one.
3. **الباقات المقترحة** – table: الباقة، السعر الشهري، السعر السنوي، الحدود (مستخدمين/فروع/أصناف)، أهم ما تشمله، الفئة المناسبة.
   Usually 3–4 tiers (مجانية/أساسية/احترافية/مؤسسات).
4. **مقارنة بأسعار المنافسين** – table with our tiers vs competitors' closest tiers; `highlight_row` for ours.
5. **مصادر دخل إضافية** – `point` blocks (تركيب، تدريب، أجهزة باركود، تكاملات، تقارير مدفوعة، marketplace…).
6. **تكلفة التطوير والتشغيل التقديرية** – table: البند، MVP، النسخة الكاملة (فريق، مدة، بنية سحابية، تسويق) –
   clearly labelled as estimates for the local market.
7. **نقطة التعادل** – simple calculation: monthly costs ÷ average revenue per customer = customers needed.
8. **يجب مراعاة** – taxes (VAT), e-invoicing, payment gateways, refunds.
9. `sources`.

## Block skeleton
```
banner(yellow) "التسعير: <اسم المشروع>"
paragraph
banner(cyan_white) "نماذج التسعير" → item × n
table "الباقات المقترحة"
table "مقارنة بالمنافسين"
banner(cyan_white) "مصادر دخل إضافية" → point × n
table "تكلفة التطوير والتشغيل التقديرية"
banner(cyan_white) "نقطة التعادل" → paragraph
banner(yellow) "يجب مراعاة" → must × n
sources
```
