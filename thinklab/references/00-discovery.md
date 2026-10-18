# Stage 0 – جلسة النقاش (Discovery) – before ANY file

The user wants a real conversation before documents: who uses the product, which features, your suggestions,
and their choices. **Do not generate any PDF until round 4 is confirmed.** Never skip this stage, even when the
idea is detailed, unless the user explicitly says "من غير نقاش" / "اعمل الملفات على طول".

Rules for every round:
- One round at a time, then STOP and wait for the reply.
- Egyptian Arabic, warm and short sentences.
- Use what the user already said; don't re-ask it. If they answer briefly ("تمام", "كمّل"), accept your recommendations.
- Keep a running "المتفق عليه" in your head; everything later must follow it.

## How to ask – multiple choice + free text (IMPORTANT)
The user wants every question as **clickable choices, with room to write their own answer**, not as long text.

**If you have a tool that shows the user questions with clickable options** (on claude.ai it is usually called
`ask_user_input` / `ask_user_input_v0`), use it for every question in every round:
- Each question: a short, plain title + 2–4 options. **Your recommendation is the first option and ends with "(اقتراحي)".**
- **Every option must be understandable on its own**: a short name + a few plain words on what it does for the user,
  e.g. "طلب مستند بالصورة: العميل يصوّر الفاتورة وتوصل للمكتب على طول" – never a bare label like "طلب مستند بالصورة".
- **No numbers inside options** (no "134 مهام شهرية…"). Numbers are only for the text lists in chat.
- **"(اقتراحي)" on the 1–2 strongest options only**, never on all of them.
- **Do not pre-select options** – the user picks; if they skip, use your recommendation.
- Simple everyday Egyptian Arabic in options; explain any technical term in the same option.
- Single choice for "pick one" questions; multi-select for "pick all that apply" (users, features, ideas).
- Respect the tool's limits (typically up to 3 questions per call, 2–4 options per question). If a round has more,
  split it into several calls one after another.
- Before the first call of a round, write one short line in chat ending with:
  "اختار من الاختيارات، ولو عندك رأي تاني اكتبه في الشات ✍️".
- Long content (the list of user types with their roles, the numbered feature lists) goes in chat as short text
  FIRST; the tool is only for the decisions.

**If no such tool is available**, write the same questions in chat in this exact shape:
```
1) المنصة؟
   أ) ويب للمدير + موبايل لأمين المخزن (اقتراحي)
   ب) موبايل بس
   ج) ويب بس
   ✍️ أو اكتب رأيك
```
and end with: "ردّ بالشكل ده: 1أ 2ب 3: (رأيك)، أو قول «تمام» لو موافق على اقتراحاتي".

## Round 1 – فهم الفكرة
1. Restate the idea in 2 lines the way you understood it.
2. Ask only what is missing (max 5 single-choice questions), e.g.:
   - الشريحة الأولى؟ (تجار جملة وموزعين (اقتراحي) / مصانع صغيرة / محلات ليها مخزن / متاجر أونلاين)
   - المنصة؟ (ويب + موبايل (اقتراحي) / موبايل بس / ويب بس)
   - حدود النظام؟ (مخزن + فواتير بيع وشراء بسيطة (اقتراحي) / مخزن بس / نظام حسابات كامل)
   - نموذج الربح؟ (اشتراك شهري بباقات (اقتراحي) / اشتراك سنوي / بيع مرة واحدة)
   - السوق؟ (القاهرة والجيزة الأول (اقتراحي) / مصر كلها / دولة تانية)
   Then one open line: "فيه منافس شايفه أو حاجة لازم تكون موجودة؟ اكتبها ✍️"

## Round 2 – مين اللي هيستخدم النظام؟
1. In chat, list **every** user type you propose (usually 4–10), numbered: name in bold, one line on what they do,
   one line on what they can / cannot do. Mark recommended ones for the first version with ⭐ and later ones with ⏳.
   Include non-obvious ones (viewer-only partner, external accountant, driver, customer, supplier portal, platform admin…).
2. Then ask with **multi-select**: "مين يكون في النسخة الأولى؟" – the user types as options (4 per question, split
   into several questions if needed; ⭐ ones first, marked "(اقتراحي)").
3. Plus: "تضيف نوع مستخدم تاني؟" – multi-select with 2–4 extra suggestions + "لا، كده كفاية" + ✍️ write your own.

## Round 3 – المميزات لكل مستخدم
For each agreed user type (1–2 user types per message if there are many; continue in the next message after the reply):
- **أساسي (MVP)** – numbered features without which the product does not work for this user.
- **⭐ مقترحات مني تميزك** – numbered smart / differentiating ideas (AI, automation, WhatsApp, offline, wow moments),
  each with a short "ليه؟".
- **⏳ مرحلة لاحقة** – numbered features that need data, integrations or budget.
Numbering is continuous across the whole message so the user can also reply in text ("شيل 4 و 17، ضيف كذا").
Show the lists in chat, then ask per user type:
- **Multi-select**: "أنهي ⭐ مقترحات عاجباك؟" – the ⭐ ideas as options (4 per question, split if more).
- **Single choice**: "المميزات الأساسية؟" – "أعتمدها كلها (اقتراحي)" / "أشيل حاجات (اكتب الأرقام في الشات)" /
  "أضيف حاجات (اكتبها في الشات)".
After the user types are covered, show **"أفكار واقعية تضيفها للمشروع كله"** (5–10 numbered cross-cutting ideas)
and ask with multi-select which ones to keep.

## Round 4 – التأكيد
Summarise what was agreed in a compact message:
- الافتراضات (السوق، المنصة، نموذج الربح، الشريحة الأولى)
- المستخدمين المعتمدين
- عدد المميزات لكل مستخدم (أساسي / مقترح / لاحق) + أهم 5 مميزات مميزة
- قائمة الملفات اللي هتطلع بالترتيب (01، 02، 03، ثم ملف واحد لكل مستخدم 04-1، 04-2…، ثم 05، 06، 07)
Then ask one single-choice question: **"أبدأ أطلع الملفات كلها ورا بعض؟"** –
"أيوه، ابدأ (اقتراحي)" / "استنى، عاوز أعدّل حاجة".

When the user confirms, move to file generation (see SKILL.md) without further questions.
