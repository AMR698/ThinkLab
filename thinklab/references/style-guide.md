# Writing style (applies to every stage)

The documents must read like the user's own reference files: Arabic, rich, concrete, and long.

1. **Language**: Modern Standard Arabic for analysis; **Egyptian dialect, polite and warm** for anything the end user sees
   (button labels, welcome messages, error and success messages), e.g. "يلا نبدأ الرحلة", "تمام، اتسجل طلبك".
   If the user's target market is outside Egypt, use that country's dialect for UI text and say so once.
   Exception: the per-user files 04-N are written in Modern Standard Arabic throughout, like the reference
   "حارس البوابة" file (see `04-role-file.md`).
2. **English terms are welcome** inside Arabic text (Dashboard, Barcode, AI Agent, Digital Twin, SaaS). Card titles are English
   ("Card 1: Warehouse Core & Inventory OS") like the reference files.
3. **Detail, not summary**: never write "وغيرها" or "إلخ". List every item. A feature card normally has 25–60 bullets,
   a user file 10–25 pages. The user explicitly wants "دون دمج أو تلخيص".
4. **Concrete UI**: name the screen, what the user sees, the exact button text in quotes, what happens on tap,
   every error state with its exact message, and the success state.
5. **Trust & emotion**: the user cares about "لا صفحات بيضاء" (empty states show motivating sentences), clear status messages
   (جارٍ الإرسال / تم الإرسال / فشل الإرسال / أعد المحاولة / آخر تحديث منذ 10 دقائق), permissions per role, and an
   emotional "wow" moment at onboarding ("رسالة عبقرية تشعره بفخر الانضمام").
6. **"### الهدف منه:"** after every main module – one sentence on how the user should feel.
7. **"يجب مراعاة"** for legal, financial, privacy and safety constraints relevant to the country (licences, tax/e-invoice
   rules, data protection, KYC/AML when money is involved, protection of minors).
8. **Realism**: every suggested feature must be buildable. Mark AI or heavy features as later phases when they need data
   that does not exist on day one. Never invent statistics, prices or competitor facts – those come from web research with sources.
9. **Colours carry meaning**: cyan for user types/keywords/journey names, pink for module names, red for warnings and
   "يجب مراعاة", cyan highlight (`!` items / `[[hl:..]]`) for the most distinctive features.
