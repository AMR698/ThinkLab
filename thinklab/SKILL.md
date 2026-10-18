---
name: thinklab
description: Discuss a startup / app / software project idea with the user (who will use it, which features, suggestions) and then produce a full set of styled Arabic PDFs (plus DOCX) - idea analysis, system and user features, one complete file per user type (features + screen-by-screen journey + edge cases), market analysis, competitors and pricing. Use whenever the user shares a project idea or asks to study, analyse, evaluate or plan one (e.g. "عندي فكرة مشروع", "حلل الفكرة", "فكرة مشروع للمخازن", "دراسة سوق", "المنافسين", "تسعير", "رحلة المستخدم", "ThinkLab").
---

# ThinkLab – من الفكرة إلى ملفات المشروع

Two phases:
1. **النقاش (Discovery)** – a real back-and-forth conversation: understand the idea, agree on the user types,
   then agree on the features of each user (you suggest, the user picks / removes / adds), then confirm.
   No files are generated in this phase.
2. **الملفات** – after the user confirms, generate ALL documents back to back, without stopping between files.
   Every document looks like the user's own reference documents (Arabic RTL; pink/cyan/red/yellow styling for 01–03 and
   05–07, blue Word-style headings for the per-user files 04-N).

Talk to the user in their language (default: Egyptian Arabic, friendly and short). Read
`references/style-guide.md` and `references/json-format.md` once at the start.

## Phase 1 – النقاش
Follow `references/00-discovery.md` exactly: Round 1 فهم الفكرة → Round 2 المستخدمين → Round 3 المميزات لكل مستخدم →
Round 4 التأكيد. One round at a time, then wait. Do not skip it and do not produce any PDF before the confirmation,
unless the user explicitly asks to skip the discussion.

Every question is **multiple choice with room for a free-text answer**: use the clickable-options question tool when
you have one (e.g. `ask_user_input` on claude.ai), recommendation first marked "(اقتراحي)"; otherwise use the
أ/ب/ج + ✍️ text format. Details in `references/00-discovery.md` → "How to ask".

## Phase 2 – الملفات (in this order)

| # | File(s) | Reference to read first |
|---|---|---|
| 01 | `01 تحليل الفكرة` | `references/01-idea-analysis.md` |
| 02–03 | `02 مميزات النظام`, `03 مميزات المستخدم` | `references/02-features.md` |
| 04-N | `04-1 <الدور> — المميزات ورحلة المستخدم`, `04-2 …` – exactly ONE file per agreed user type | `references/04-role-file.md` |
| 05 | `05 تحليل السوق` (web research) | `references/03-market.md` |
| 06 | `06 المنافسين` (web research) | `references/04-competitors.md` |
| 07 | `07 التسعير` (web research) | `references/05-pricing.md` |

Never create separate structure / detailed-journey / per-module files: every screen and edge case of a user goes inside
that user's single 04-N file. Total files = 6 + number of agreed user types.

For each file:
1. Read its reference file.
2. Files 05–07: do real web research (several searches in parallel, Arabic and English) and cite sources.
   Never invent numbers, prices or competitor facts. If web search is unavailable, say so and mark figures as "تقدير".
3. Content MUST follow what was agreed in the discussion: the same user types, the same features
   (MVP / ⭐ / later), the user's additions and removals. Be exhaustive – full detail, not summaries.
4. Write the JSON (format in `references/json-format.md`) to `<work>/NN-name.json`
   (`<work>` = `/mnt/user-data/outputs/thinklab-<project-slug>/` if that folder exists, otherwise a working folder you choose).
5. Generate:
   ```bash
   python3 <skill-dir>/scripts/build_doc.py <work>/NN-name.json --out <work>
   ```
   The script writes a `.docx` and converts it to `.pdf` with LibreOffice (fonts bundled in `assets/fonts`).
   If the PDF step reports FAILED, deliver the DOCX and say so.
6. Share the PDF right away with ONE line ("✅ خلص ملف 01 تحليل الفكرة") and continue immediately with the next file.
   Do NOT ask for approval between files.

If your reply gets cut off or you run out of room, say exactly which files are done and which remain, and tell the user
to write "كمّل"; then continue from the next unfinished file.

**At the end**: list all generated files in order, give 3–5 key takeaways, and ask:
"عاوز تعدّل في ملف معين؟ قولي رقم الملف والتعديل." An edit regenerates only the affected file(s)
(and any later file that depends on it, e.g. a removed feature must disappear from the user files too).

## Quality checklist before generating each PDF
- Matches the agreed users and features from the discussion.
- Arabic, detailed, no "إلخ"; UI text in the target market's dialect; English terms where natural.
- Correct block types for the file (see the skeleton in its reference file).
- Feature cards: 25–60 bullets each, the user's ⭐ picks marked with `!`.
- User files 04-N: all nine sections of `04-role-file.md`, every screen with its "حالات" paragraph, button text in quotes,
  every branch as a bold "إذا …:" sentence.
- Market / competitors / pricing: every figure has a source or is labelled "تقدير" with the calculation.
