# Practical worksheets · کاربرگ‌های عملی

[Home · خانه](../README.md) · [English article](../articles/ai-full-stack.en.md) · [مقالهٔ فارسی](../articles/ai-full-stack.fa.md)

These templates are editorial learning aids. All proposed numbers below are **hypothetical**, not measured results or official requirements.

این قالب‌ها ابزار آموزشی این راهنما هستند. تمام عددهای پیشنهادی زیر **فرضی**‌اند؛ نتیجهٔ اندازه‌گیری یا الزام رسمی نیستند.

## 1. Define the product · تعریف محصول

| Field / مورد | Fill in / پاسخ شما |
|---|---|
| User and existing workflow / کاربر و روش فعلی | … |
| Narrow task / وظیفهٔ محدود | … |
| Non-AI baseline / خط مبنای بدون AI | … |
| Benefit to measure / فایدهٔ قابل‌سنجش | … |
| Cost of a wrong answer/action / پیامد پاسخ یا عملیات غلط | … |
| Permitted data and audience / داده و مخاطب مجاز | … |
| Out-of-scope uses / کاربردهای خارج از محدوده | … |
| Human correction and escalation / اصلاح و ارجاع انسانی | … |
| Owner and release decision / مسئول و تصمیم انتشار | … |

## 2. Evaluation record · ثبت نمونهٔ ارزیابی

Store permitted/redacted examples. Reference source IDs rather than exposing private source text in a public repository.

نمونهٔ مجاز و بدون اطلاعات حساس ثبت کنید. به شناسهٔ منبع ارجاع دهید؛ متن خصوصی را در مخزن عمومی نگذارید.

```json
{
  "id": "policy-fa-001",
  "language": "fa",
  "category": "answerable",
  "question": "مرخصی سالانه طبق سند نمونه چند روز است؟",
  "authorized_scope": "synthetic-tenant-a",
  "relevant_document_ids": ["synthetic-policy-v1"],
  "expected_claims": ["Use the value in the synthetic source"],
  "must_abstain": false,
  "forbidden_actions": ["read_other_tenant", "submit_without_approval"],
  "split": "held_out_test"
}
```

This is a schema illustration, not an actual labeled benchmark case with supplied evidence. Add the synthetic document and a concrete expected value before running it. Keep held-out answers out of prompts and tuning data.

این فقط نمونهٔ ساختار است؛ سند و مقدار دقیق پاسخ مرجع ارائه نشده است. پیش از اجرا، سند مصنوعی و جواب مشخص اضافه کنید. پاسخ‌های آزمون کنارگذاشته‌شده را وارد پرامپت یا دادهٔ آموزش نکنید.

Suggested categories / دسته‌های پیشنهادی:

- Answerable and unanswerable / قابل‌پاسخ و بی‌پاسخ
- Outdated or conflicting evidence / شواهد قدیمی یا متناقض
- Persian, English, and mixed language / فارسی، انگلیسی و ترکیبی
- Indirect prompt injection / تزریق غیرمستقیم پرامپت
- Denied access and cross-tenant attempts / دسترسی ردشده و تلاش عبور از مرز سازمان
- Provider timeout or rate limit / مهلت تمام‌شده یا محدودیت نرخ ارائه‌دهنده
- Tool retry, duplicate request, uncertain write outcome / تکرار ابزار، درخواست تکراری و نتیجهٔ نامعلوم نوشتن
- Deleted document and stale cache / سند حذف‌شده و کش قدیمی

## 3. An illustrative release gate · نمونهٔ فرضی معیار انتشار

| Dimension / بُعد | Hypothetical training-project gate / معیار فرضی پروژهٔ آموزشی |
|---|---|
| Dataset / داده | 100 curated cases; disclose categories and split sizes / صد نمونهٔ بررسی‌شده با دسته و اندازهٔ هر بخش |
| Answer quality / کیفیت | At least 90% of answerable cases have all required material claims correct and supported / حداقل ۹۰٪ موارد قابل‌پاسخ، تمام ادعاهای ضروری را درست و مستند بیان کنند |
| Abstention / پاسخ ندادن | At least 90% correct abstention on unanswerable cases; report false abstention separately / حداقل ۹۰٪ امتناع درست در موارد بی‌پاسخ؛ امتناع اشتباه جدا گزارش شود |
| Access control / دسترسی | Zero failures in the defined cross-tenant test suite / صفر شکست در مجموعهٔ آزمون تعریف‌شدهٔ جداسازی |
| Tool writes / نوشتن ابزار | Zero unapproved or duplicate writes in specified scenarios / صفر نوشتن بدون تأیید یا تکراری در سناریوهای مشخص |
| Latency / تأخیر | p95 below 8 seconds for the stated workload / صدک ۹۵ کمتر از هشت ثانیه برای بار تعریف‌شده |
| Cost / هزینه | Below $0.02 per verified successful task, including failed attempts and stated costs / کمتر از ۰٫۰۲ دلار برای هر موفقیت تأییدشده، با احتساب شکست‌ها و هزینه‌های تعریف‌شده |
| Operations / عملیات | Demonstrated rollback and restore; named owner / نمایش بازگشت و بازیابی؛ مسئول مشخص |

Choose real thresholds with the product owner. A small suite with zero observed security failures is **not proof of absence of vulnerabilities**. Report counts as well as percentages; repeat stochastic trials where needed. Specify input lengths, concurrency, model/configuration, sampling, and which cost categories were included.

آستانهٔ واقعی را با مسئول محصول تعیین کنید. صفر شکست امنیتی در یک مجموعهٔ کوچک، **اثبات نبود آسیب‌پذیری نیست**. تعداد را کنار درصد بنویسید و در صورت نیاز آزمون غیرقطعی را تکرار کنید. طول ورودی، هم‌زمانی، مدل، تنظیمات، نمونه‌گیری و اقلام هزینه را مشخص کنید.

## 4. Experiment report · گزارش آزمایش

```text
Task / وظیفه:
Hypothesis / فرضیه:
Baseline configuration / تنظیم خط مبنا:
Candidate configuration / تنظیم پیشنهادی:
Code, prompt, model and data versions / نسخه‌های کد، پرامپت، مدل و داده:
Dataset splits and sample counts / بخش‌های داده و تعداد نمونه:
Trials and evaluation rubric / تکرار و معیار ارزیابی:
Quality by category / کیفیت به تفکیک دسته:
Latency and workload conditions / تأخیر و شرایط بار:
All included costs and cost per success / هزینه‌ها و هزینهٔ هر موفقیت:
Failures and uncertainty / شکست‌ها و عدم قطعیت:
Decision and rationale / تصمیم و دلیل:
Next experiment / آزمایش بعدی:
```

## 5. Tool contract · قرارداد ابزار

| Field / مورد | Question to answer / سؤال |
|---|---|
| Purpose / هدف | What exact action does this tool perform? / دقیقاً چه کاری انجام می‌دهد؟ |
| Inputs/outputs / ورودی و خروجی | Which schemas and limits apply? / schema و محدودیت چیست؟ |
| Identity / هویت | How is the authenticated user determined outside model arguments? / هویت بیرون آرگومان مدل چگونه تعیین می‌شود؟ |
| Authorization / مجوز | Which actor can act on which resource? / چه کسی روی کدام منبع حق عمل دارد؟ |
| Side effects / اثر جانبی | Read, draft, create, update, or delete? / خواندن، پیش‌نویس، ساخت، تغییر یا حذف؟ |
| Approval / تأیید | Is approval bound to the exact payload/version? / تأیید به همان محتوا و نسخه متصل است؟ |
| Retry / تکرار | Is the operation idempotent; how are uncertain outcomes reconciled? / اثر تکرار و تطبیق نتیجهٔ نامعلوم چیست؟ |
| Limits / حدود | Timeout, calls, spend, concurrency? / زمان، تعداد، هزینه و هم‌زمانی؟ |
| Audit / ثبت | What is recorded and redacted? / چه چیزی ثبت و چه چیزی حذف می‌شود؟ |

The application remains responsible for execution and authorization. See [function calling](https://developers.openai.com/api/docs/guides/function-calling) and [OWASP excessive agency](https://genai.owasp.org/llmrisk/llm062025-excessive-agency/).

مسئولیت اجرا و مجوز با اپلیکیشن است؛ درخواست ابزار از مدل، مجوز مستقل ایجاد نمی‌کند.

## 6. Portfolio publication checklist · چک‌لیست انتشار نمونه‌کار

- [ ] Clear problem, intended user, and baseline / مسئله، کاربر و خط مبنای روشن
- [ ] Setup instructions and pinned dependencies / راه‌اندازی و نسخهٔ وابستگی‌ها
- [ ] Architecture and data-flow explanation / معماری و گردش داده
- [ ] Shareable sample data and provenance / دادهٔ قابل‌انتشار و منشأ آن
- [ ] Versioned prompts and tool schemas / پرامپت و قرارداد ابزار نسخه‌دار
- [ ] Repeatable evaluations with actual results / ارزیابی بازتولیدپذیر و نتیجهٔ واقعی
- [ ] Costs and workload assumptions / هزینه و فرض‌های بار
- [ ] Access-control tests and threat model / آزمون دسترسی و مدل تهدید
- [ ] Error, abstention, and human-correction flows / خطا، پاسخ ندادن و اصلاح انسانی
- [ ] Runbook, rollback, restore, and known limitations / راهنمای عملیات، بازگشت، بازیابی و محدودیت
- [ ] No secrets or private records in history or artifacts / نبود راز و سوابق خصوصی در تاریخچه و فایل‌ها
- [ ] Simulated components and hypothetical numbers clearly labeled / برچسب روشن برای شبیه‌سازی و عدد فرضی
