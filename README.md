# بيانات التفاسير القرآنية (JSON) — Quran Tafsir Dataset

بيانات القرآن الكريم كاملًا (114 سورة، 6236 آية) بصيغة JSON جاهزة للاستخدام في التطبيقات والمواقع.

تتضمن الملفات التفاسير التالية:

- التفسير الميسر
- تفسير الجلالين
- تفسير السعدي
- تفسير ابن كثير
- تفسير الوسيط لطنطاوي
- تفسير البغوي
- تفسير القرطبي
- تفسير الطبري

Complete Quran text (114 surahs, 6,236 ayahs) in JSON format ready for use in apps and websites.

The dataset includes the following tafsir sources:

- Al-Tafsir Al-Muyassar
- Tafsir Al-Jalalayn
- Tafsir As-Sa'di
- Tafsir Ibn Kathir
- Tafsir Al-Waseet (Tantawi)
- Tafsir Al-Baghawi
- Tafsir Al-Qurtubi
- Tafsir Al-Tabari

[العربية](#العربية) | [English](#english)

---

## العربية

### المحتويات

- 114 ملف JSON، ملف واحد لكل سورة، بالتسمية `NNN_اسم-السورة.json` (مثال: `001_al-fatiha.json`).
- كل آية تحتوي على: رقم الآية، نص الآية، ثم مصفوفة `tafsir` (تضم التفاسير المتاحة لهذه الآية).
- **تقسيم الآيات يتبع تفسير ابن كثير** (وهو تقسيم المصحف القياسي المتعارف عليه) في كل السور الـ 114، بما فيها السور التي لم تكن مكتملة في مصادر سابقة.
- إجمالي عدد الآيات في كل الملفات: **6236 آية**، وهو العدد الصحيح لآيات القرآن الكريم، وقد جرى التحقق من ذلك.

### شكل البيانات

```json
{
  "surah": "الفاتحة",
  "number": 1,
  "ayahs": [
    {
      "ayah_number": 1,
      "text": "بِسْمِ اللَّهِ الرَّحْمَٰنِ الرَّحِيمِ",
      "tafsir": [
        {
          "type": "تفسير الجلالين",
          "text": "..."
        },
        {
          "type": "التفسير الميسر",
          "text": "..."
        },
        {
          "type": "تفسير السعدي",
          "text": "..."
        },
        {
          "type": "تفسير ابن كثير",
          "text": "..."
        },
        {
          "type": "تفسير القرطبي",
          "text": "..."
        }
      ]
    }
  ]
}
```

### ملاحظة مهمة حول الحقول الفارغة

قد تجد في بعض الآيات نص تفسير فارغًا لأحد المفسرين (السعدي أو ابن كثير) على آية معينة. هذا **ليس خطأً أو نقصًا في البيانات**، بل هو أسلوب معروف عند بعض المفسرين في شرح عدة آيات متتالية قصيرة ضمن فقرة واحدة مرتبطة بآية سابقة، فتُترك الآية التالية دون تكرار للشرح. تم التحقق من هذا النمط بشكل منهجي عبر كل السور، ولم يظهر أي انقطاع مفاجئ في التفسير إلا في الحالتين المذكورتين أعلاه (سورة إبراهيم: 25، وسورة العلق: 12–19)، وكلتاهما تمت معالجتهما.

### تنبيه

هذا العمل هو تجميع آلي لبيانات من مصادر عامة متفرقة. رغم التحقق الدقيق من تطابق تقسيم الآيات وعددها الإجمالي (6236)، يُنصح بمراجعة النصوص عند الاستخدام في سياقات حساسة، ومقارنتها بنسخ مطبوعة أو موثوقة من كتب التفسير الأصلية.

---

## English

### Contents

- 114 JSON files, one per surah, named `NNN_surah-slug.json` (e.g. `001_al-fatiha.json`).
- Each ayah contains: ayah number, ayah text, and a `tafsir` array (with available commentaries for that ayah).
- **Ayah splitting follows Tafsir Ibn Kathir's numbering** (the standard mushaf convention) across all 114 surahs, including surahs that were incomplete in prior sources.
- Total ayahs across all files: **6,236** — the correct total for the Quran, verified during generation.

### Data shape

```json
{
  "surah": "الفاتحة",
  "number": 1,
  "ayahs": [
    {
      "ayah_number": 1,
      "text": "بِسْمِ اللَّهِ الرَّحْمَٰنِ الرَّحِيمِ",
      "tafsir": [
        {
          "type": "تفسير السعدي",
          "text": "..."
        },
        {
          "type": "تفسير ابن كثير",
          "text": "..."
        }
      ]
    }
  ]
}
```

### A note on empty tafsir fields

Some ayahs show an empty tafsir string for one of the two commentators. This is **not missing data** — it reflects a known stylistic convention where a commentator explains several short consecutive verses together under one earlier verse's entry, leaving the following verse(s) blank rather than repeating the explanation. This pattern was systematically checked across all 114 surahs; the only two genuine gaps found are the ones documented above, and both have been resolved.

### Disclaimer

This is an automated compilation from separate public sources. While ayah splitting and the total ayah count (6,236) were carefully verified, users are encouraged to cross-check the text against printed or otherwise authoritative editions of the original tafsir books before relying on it in sensitive contexts.
