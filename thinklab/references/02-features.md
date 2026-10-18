# Stage 2 – المميزات (مميزات النظام + مميزات كل مستخدم)

Output files (two, like the user's references 02 and 03):
- `02 مميزات النظام - <اسم المشروع>` – back-office / admin side. Title banner: "مميزاته داخل التطبيق".
- `03 مميزات المستخدم - <اسم المشروع>` – what each end-user type gets. Title banner: "مميزات المستخدم داخل التطبيق".
  If there are several user types, one `banner(cyan_white)` per user type followed by its cards.

## How to build the cards
- Group features into **6–12 cards**, each an "operating system" for one domain, English title, e.g.
  `Card 1: Inventory Core & Item Master OS`, `Card 2: Receiving, Put-away & Quality OS`,
  `Card 3: Orders, Picking & Dispatch OS`, `Card 4: Stock Counting & Audit OS`, `Card 5: Purchasing & Suppliers OS`,
  `Card 6: Finance, Costing & E-Invoicing OS`, `Card 7: Analytics, Forecasting & AI Agents OS`,
  `Card 8: Permissions, Security & Audit Trail OS`, `Card 9: Integrations & Mobile/Offline OS`.
- Each card: **25–60 bullets** in the order: basics → workflows → dashboards/alerts → smart/AI features → memory & agents.
  Mix Arabic and English like the references ("• Next Best Action لكل صنف", "• Smart Reorder Engine").
- Start each bullet with what it does, not with a verb in the imperative.
- Prefix the strongest / unique / AI items with `!` (cyan highlight), roughly 10–20% of items.
- Realism: put a final card `Card N: Roadmap – MVP vs Later` with bullets "MVP: ..." / "المرحلة الثانية: ..." /
  "المرحلة الثالثة: ..." so the user sees what ships first.

## Block skeleton
```
banner(title) "مميزاته داخل التطبيق"
card × n  (style "yellow" in file 02, style "cyan" in file 03)
```
