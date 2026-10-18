# JSON format for `scripts/build_doc.py`

Every stage document is one JSON file:

```json
{
  "file_name": "01 تحليل الفكرة - نظام المخازن",
  "title": "تحليل الفكرة",
  "blocks": [ ... ]
}
```

`file_name` becomes the output name (`.docx` and `.pdf`). Blocks render top to bottom.

## Inline markup (works inside every `text`, `label`, `lines`, list item, table cell)
| Markup | Result |
|---|---|
| `**نص**` | bold |
| `[[red:نص]]` | red text (FF0000) |
| `[[darkred:نص]]` | dark red (C00000) |
| `[[cyan:نص]]` | cyan text (00B0F0) – keywords, user types, journey names |
| `[[pink:نص]]` | pink text (FF0066) |
| `[[green:نص]]` | green text |
| `[[pinkbg:نص]]` | white text on pink background |
| `[[yellowbg:نص]]` | yellow background |
| `[[hl:نص]]` | cyan highlight – a key differentiator |
| `[[mark:نص]]` | yellow highlight |

## Shared blocks
- `{"type":"basmala"}` – centred "بسم الله الرحمن الرحيم" (optional `text`).
- `{"type":"banner","text":"...","style":"yellow|cyan|cyan_white|pink|title"}` – full-width coloured bar.
  - `yellow`: red text on yellow, centred (e.g. "يجب مراعاة الآتي", "الرحلات داخل الملفات")
  - `cyan`: big pink text on cyan, centred (e.g. "مقترح أن يكون في الناف بار")
  - `cyan_white`: white text on cyan, centred (e.g. "رحلة ولي الأمر داخل الشئون الإدارية")
  - `pink`: white text on pink, centred
  - `title`: black text on yellow, right aligned (e.g. "مميزاته داخل التطبيق")
- `{"type":"paragraph","text":"...","align":"both|right|center"}`
- `{"type":"spacer","lines":1}`
- `{"type":"table","title":"...","headers":[...],"rows":[[...],...],"highlight_row":0}` – RTL table, cyan header.
  `highlight_row` (optional, 0-based) tints a row – use it for "our product" in comparisons.
- `{"type":"sources","items":[{"title":"...","url":"..."}]}` – sources list at the end.

## Considerations style (reference file 00)
- `{"type":"point","text":"...","lines":["..."]}` – cyan `ؐ` bullet; `lines` are continuation paragraphs.
- `{"type":"item","label":"البحث","text":"...","lines":["..."]}` – pink `֎` + pink label + text.

## Structure style (reference file 01)
- `{"type":"intro","label":"عند بداية استخدام التطبيق","text":"...","lines":["..."]}` – red `❒` + red label.
- `{"type":"module","label":"الشؤون الإدارية","text":"هذا الملف يكون خاصًا بـ... يشمل:","list":["...","..."],"goal":"..."}`
  – `֎` + label on pink background, inline dash list "- أ. - ب.", then "### الهدف منه: ...".
- `{"type":"goal","text":"..."}` – standalone "### الهدف منه:" line.
- `{"type":"must","text":"...","label":"يجب مراعاة"}` – dark-red label + text.
- `{"type":"journey","name":"انتظام","text":"وفيها : ...","lines":["..."],"buttons":["...","..."]}`
  – red `❒` + "رحلة" + cyan name; buttons render as "والأزرار: - أ. - ب.".

## Feature cards style (reference files 02 / 03)
- `{"type":"card","title":"Warehouse Core & Inventory OS","style":"yellow|cyan","items":["...","!highlighted item", {"text":"...","highlight":true}]}`
  – "Card N:" is added automatically (numbered across the file) unless the title already starts with "Card".
  – An item starting with `!` is highlighted in cyan (use for the strongest / AI / unique features).

## Legacy detailed-journey blocks (do NOT use for new projects – user journeys go in the 04-N user files)
- `{"type":"phase","text":"المرحلة الأولى: شاشات الترحيب والتهيئة الرقمية (Onboarding & Setup)"}` – blue heading.
- `{"type":"steps","items":["...", {"error":"..."}, {"success":"..."}, {"note":"..."}]}`
  – bullet list. `error` is auto-numbered across the whole file: "حالة الخطأ (1): ...", "حالة الخطأ (2): ...".

## Per-user file style (reference "حارس البوابة — المميزات ورحلة المستخدم") – files 04-N
Put `"theme": "role"` at the top level of the JSON (next to `file_name`). It switches to a Sans Arabic font, Arial for
Latin text, 10.5pt body, wider margins and right-aligned paragraphs. Blocks:
- `{"type":"h1","text":"القسم الأول — المميزات"}` – blue 16pt with a thin rule under it (`"before":0` for the very first one).
- `{"type":"h2","text":"الكارت الأول: الدخول"}` – blue 13pt.
- `{"type":"h3","text":"الزائر المدعو"}` – dark blue 12pt.
- `{"type":"h4","text":"الزائر يقول إنه صاحب الوحدة"}` – blue italic 11pt.
- `{"type":"meta","items":[{"label":"التطبيق","text":"..."}, ...]}` – bold label + text lines (file header).
- `{"type":"subtitle","text":"دخول الزوار"}` – bold group title inside a feature card.
- `{"type":"bullets","items":["...","..."]}` – • list.
- `{"type":"divider"}` – thin horizontal line between sections.
- `{"type":"paragraph","text":"**إذا كان الرمز خاطئاً:** \"الرمز غير صحيح.\""}` – narrative sentence; `**…**` for the bold parts.
- `{"type":"table","headers":[...],"rows":[...],"header_style":"grey"}` – grey header row, black text.
