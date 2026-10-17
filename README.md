````markdown
# 🕋 Quran Tafsir JSON Dataset | قاعدة بيانات تفاسير القرآن الكريم

[![JSON Data](https://img.shields.io/badge/Format-JSON-blue.svg)](#)
[![Quran Ayahs](https://img.shields.io/badge/Ayahs-6236-success.svg)](#)
[![Surahs](https://img.shields.io/badge/Surahs-114-success.svg)](#)
[![Open Source](https://img.shields.io/badge/Open%20Source-%E2%9D%A4-red.svg)](#)

بيانات القرآن الكريم كاملًا (114 سورة، 6236 آية) مع 8 تفاسير معتمدة، مهيأة ومنسقة بصيغة **JSON** لتكون جاهزة للاستخدام المباشر في تطبيقات الجوال، ومواقع الويب، وتطبيقات الخوادم (مثل Node.js) ومشاريع الذكاء الاصطناعي.

A comprehensive, structured JSON database for the Holy Quran and its interpretations (Tafsir). Ready to be integrated into Islamic apps, RESTful APIs, and AI models.

[العربية](#العربية) | [English](#english)

---

## 📌 مميزات المستودع (Features)

- **بيانات مهيكلة (Structured Data):** سهلة الاستعلام والربط مع قواعد البيانات مثل MongoDB.
- **جاهزة للواجهات البرمجية (API-Ready):** مثالية لبناء REST APIs لتطبيقات القرآن الكريم.
- **دقة عالية:** تم مطابقة وتقسيم الآيات (6236 آية) بناءً على تقسيم مصحف المدينة المعتمد.

## العربية

### 📚 التفاسير المتاحة

يحتوي المستودع على 8 من أمهات كتب التفسير:

1. التفسير الميسر
2. تفسير الجلالين
3. تفسير السعدي
4. تفسير ابن كثير
5. تفسير الوسيط (لطنطاوي)
6. تفسير البغوي
7. تفسير القرطبي
8. تفسير الطبري

### 📂 هيكلة الملفات

- 114 ملف JSON، ملف واحد لكل سورة، بالتسمية `NNN_اسم-السورة.json` (مثال: `001_al-fatiha.json`).
- كل آية تحتوي على: `رقم الآية`، `نص الآية`، ومصفوفة `tafsir` (تضم التفاسير المتاحة لهذه الآية).
- **تقسيم الآيات يتبع تفسير ابن كثير** (وهو تقسيم المصحف القياسي المتعارف عليه) في كل السور الـ 114.
- إجمالي عدد الآيات في كل الملفات: **6236 آية** (وهو العدد الصحيح لآيات القرآن الكريم).

### 💻 كيفية الاستخدام في المشاريع (مثال Node.js)

```javascript
// قراءة ملف سورة الفاتحة
const alFatiha = require('./001_al-fatiha.json');

// طباعة نص الآية الأولى وتفسير ابن كثير لها
const firstAyah = alFatiha.ayahs[0];
console.log('الآية:', firstAyah.text);

const ibnKathir = firstAyah.tafsir.find((t) => t.type === 'تفسير ابن كثير');
console.log('التفسير:', ibnKathir.text);
```
````

### 🧩 شكل البيانات (JSON Schema)

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
          "type": "تفسير ابن كثير",
          "text": "..."
        }
      ]
    }
  ]
}
```

> **⚠️ ملاحظة مهمة حول الحقول الفارغة:**
> قد تجد في بعض الآيات نص تفسير فارغًا لأحد المفسرين على آية معينة. هذا **ليس خطأً أو نقصًا في البيانات**، بل هو أسلوب معروف عند بعض المفسرين في شرح عدة آيات متتالية قصيرة ضمن فقرة واحدة مرتبطة بآية سابقة، فتُترك الآية التالية دون تكرار للشرح.

> **⚖️ تنبيه:**
> هذا العمل هو تجميع آلي لبيانات من مصادر عامة. رغم التحقق الدقيق من تطابق تقسيم الآيات وعددها الإجمالي، يُنصح بمراجعة النصوص عند الاستخدام في سياقات حساسة ومقارنتها بالنسخ المطبوعة.

---

## English

### 📚 Included Tafsir Sources

The dataset includes the following trusted interpretations:

1. Al-Tafsir Al-Muyassar
2. Tafsir Al-Jalalayn
3. Tafsir As-Sa'di
4. Tafsir Ibn Kathir
5. Tafsir Al-Waseet (Tantawi)
6. Tafsir Al-Baghawi
7. Tafsir Al-Qurtubi
8. Tafsir Al-Tabari

### 📂 File Structure

- 114 JSON files, one per surah, named `NNN_surah-slug.json` (e.g., `001_al-fatiha.json`).
- Each ayah contains: `ayah_number`, `text` (Arabic text), and a `tafsir` array (with available commentaries).
- **Ayah splitting follows Tafsir Ibn Kathir's numbering** (the standard mushaf convention) across all 114 surahs.
- Total ayahs across all files: **6,236** (the verified correct total for the Quran).

### 🧩 Data Shape Example

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

> **⚠️ A note on empty tafsir fields:**
> Some ayahs show an empty tafsir string for commentators. This is **not missing data**. It reflects a known stylistic convention where a commentator explains several short consecutive verses together under an earlier verse's entry, leaving the following verse(s) blank rather than repeating the explanation.

> **⚖️ Disclaimer:**
> This is an automated compilation from separate public sources. While ayah splitting and the total ayah count were carefully verified, users are encouraged to cross-check the text against authoritative printed editions before relying on it in sensitive applications.

---

## 🔍 Keywords / Tags

`quran-api` `quran-json` `tafsir-api` `quran-database` `islamic-api` `quranic-dataset` `tafseer` `ibn-kathir` `al-jalalayn` `quran-data` `arabic-nlp` `quran-developer-tools` `mosahaf` `القرآن-الكريم` `تفاسير-القرآن` `قاعدة-بيانات-القرآن` `تطبيقات-إسلامية`

```

<ElicitationsGroup>

```
