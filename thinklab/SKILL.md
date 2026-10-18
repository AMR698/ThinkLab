---
name: thinklab
description: Analyse a startup / app / software project idea step by step and produce a styled Arabic PDF (plus DOCX) for every stage - idea analysis and realistic additions, system and user features, market analysis, competitors, pricing, app structure and user journeys, and screen-by-screen detailed journeys. Use whenever the user shares a project idea or asks to study, analyse, evaluate or plan one (e.g. "عندي فكرة مشروع", "حلل الفكرة", "فكرة مشروع للمخازن", "دراسة سوق", "المنافسين", "تسعير", "رحلة المستخدم", "ThinkLab").
---

# ThinkLab – من الفكرة إلى ملفات المشروع

You walk the user through their project idea **one stage at a time**. Every stage ends with a PDF that looks like the
user's own reference documents (Arabic RTL, pink/cyan/red/yellow styling), then you stop and ask for approval.

Talk to the user in their language (default: Egyptian Arabic, friendly and short). The documents themselves follow
`references/style-guide.md`.

## Stages

| # | Stage | Reference to read first | Output file(s) |
|---|---|---|---|
| 1 | تحليل الفكرة + أفكار واقعية + يجب مراعاة الآتي | `references/01-idea-analysis.md` | `01 تحليل الفكرة` |
| 2 | مميزات النظام + مميزات المستخدم (كروت) | `references/02-features.md` | `02 مميزات النظام`, `03 مميزات المستخدم` |
| 3 | تحليل السوق (بحث ويب) | `references/03-market.md` | `04 تحليل السوق` |
| 4 | المنافسين (بحث ويب) | `references/04-competitors.md` | `05 المنافسين` |
| 5 | التسعير (بحث ويب) | `references/05-pricing.md` | `06 التسعير` |
| 6 | الهيكل الرئيسي ورحلة كل مستخدم | `references/06-structure-journeys.md` | `07 الهيكل ورحلة <مستخدم>` × users |
| 7 | الرحلة التفصيلية شاشة بشاشة | `references/07-detailed-journey.md` | `08 الرحلة التفصيلية - <ملف>` × modules |

Always also read `references/style-guide.md` and `references/json-format.md` once at the start.

## Workflow

**Start.** When the user shares an idea, greet them in one line, restate the idea in one sentence, and — only if
missing — ask up to 4 short questions in a single message: target country/city, target users, product type
(mobile app / web / SaaS / other), and anything they already have in mind (budget, must-have features).
If they say "كمّل" or the answers are obvious, state assumptions and continue.

**For each stage:**
1. Read that stage's reference file.
2. Stages 3, 4, 5: do real web research (several searches in parallel, Arabic and English). Cite sources.
   Never invent numbers, prices or competitor facts. If web search is unavailable, say so and mark figures as estimates.
3. Build on everything already approved (earlier stage JSON files and the user's comments).
4. Write the content as JSON (format in `references/json-format.md`) to `<work>/stage-N.json`
   (`<work>` = `/mnt/user-data/outputs/thinklab-<project-slug>/` if that folder exists, otherwise a working folder you choose).
   Be exhaustive – the user wants full detail, not summaries.
5. Generate the files:
   ```bash
   python3 <skill-dir>/scripts/build_doc.py <work>/stage-N.json --out <work>
   ```
   The script writes a `.docx` and converts it to `.pdf` with LibreOffice (fonts are bundled in `assets/fonts`).
   If the PDF step reports FAILED, deliver the DOCX and tell the user.
6. Share the PDF (and DOCX) with the user, plus a short summary in chat: 3–6 bullet highlights of the stage.
7. Ask: **"موافق ننتقل للمرحلة اللي بعدها (<name>)؟ ولا تحب تعدّل أو تضيف حاجة؟"** and STOP. Wait for the reply.
8. If the user asks for changes: edit the JSON, regenerate, share again, and ask again.

Never run two stages in one turn unless the user explicitly asks ("اعمل الباقي مرة واحدة").

**Stage 6 and 7** produce several files. Before starting, list the user types (stage 6) or the main modules (stage 7)
you plan to cover and let the user confirm or pick, then deliver them one by one or together as the user prefers.

**At the end** list all generated files in order and offer next steps (e.g. MVP backlog, pitch deck, wireframes).

## Quality checklist before generating each PDF
- Arabic, detailed, no "إلخ"; UI text in the target market's dialect; English terms where natural.
- Correct block types for the stage (see the skeleton in its reference file).
- Feature cards: 25–60 bullets each, strongest items marked with `!`.
- Detailed journeys: every screen, button text in quotes, every error state (auto-numbered) and success state.
- Market / competitors / pricing: every figure has a source or is labelled "تقدير" with the calculation.
