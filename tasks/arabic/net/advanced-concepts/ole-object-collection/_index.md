---
date: 2026-03-14
description: تعلم كيفية استخراج الملفات المضمنة وتحميل ملف المشروع باستخدام Aspose.Tasks
  لـ .NET. يوضح هذا البرنامج التعليمي استخراج كائنات OLE خطوة بخطوة.
linktitle: Collection of OLE Objects in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: استخراج الملفات المدمجة من كائنات OLE في Aspose.Tasks
url: /ar/net/advanced-concepts/ole-object-collection/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# استخراج الملفات المضمنة من كائنات OLE في Aspose.Tasks

## المقدمة

في هذا البرنامج التعليمي ستقوم **باستخراج الملفات المضمنة** التي تُخزن ككائنات OLE داخل ملف Microsoft Project باستخدام Aspose.Tasks لـ .NET. سواء كنت بحاجة إلى سحب مستندات Word المرتبطة، أو جداول Excel، أو ملفات النص الغني، تُظهر الخطوات أدناه كيفية **تحميل ملف المشروع**، اكتشاف كل إدخال OLE، وكتابة المحتوى الثنائي مرة أخرى إلى القرص. في النهاية ستصبح مرتاحًا مع سير عمل **c# extract ole** كامل يمكنك إعادة استخدامه في تطبيقاتك الخاصة.

## إجابات سريعة
- **ماذا يعني “استخراج الملفات المضمنة”؟** يعني قراءة الحمولة الثنائية لكائنات OLE وحفظها كملفات منفصلة على القرص.  
- **أي طريقة API تقوم بتحميل المشروع؟** `new Project(filePath)` من مساحة الأسماء Aspose.Tasks.  
- **هل يمكنني تصدير كائنات OLE من أي نوع؟** فقط الصيغ التي يمكن لـ Aspose.Tasks التعرف عليها (مثل RTF، Word، Excel) مدعومة.  
- **هل أحتاج إلى ترخيص لهذا؟** نسخة تجريبية مجانية تعمل للتقييم؛ الترخيص التجاري مطلوب للإنتاج.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6/7.

## ما معنى “استخراج الملفات المضمنة” في سياق كائنات OLE؟

يتيح OLE (Object Linking and Embedding) للملف Project احتواء نسخ كاملة من المستندات الخارجية. استخراج تلك الملفات المضمنة يمنحك وصولًا مباشرًا إلى المحتوى الأصلي دون الحاجة لفتح ملف Project في Microsoft Project.

## لماذا نحتاج إلى استخراج الملفات المضمنة من كائنات OLE؟

- **الحفاظ على البيانات الأصلية:** الاحتفاظ بنسخة احتياطية من كل مستند مرفق.  
- **أتمتة التقارير:** سحب تقارير Word أو Excel من العديد من المشاريع دفعة واحدة.  
- **التكامل مع أنظمة أخرى:** إمداد الملفات المستخرجة إلى أنظمة إدارة المستندات أو خطوط التحليل.

## المتطلبات المسبقة

قبل أن تبدأ، تأكد من وجود ما يلي:

1. **Visual Studio** – أي نسخة حديثة (2019، 2022 أو أحدث).  
2. **Aspose.Tasks for .NET** – قم بتنزيله وتثبيته من [here](https://releases.aspose.com/tasks/net/).  
3. **معرفة أساسية بـ C#** – يجب أن تكون مرتاحًا مع الحلقات، المجموعات، وعمليات الإدخال/الإخراج للملفات.  

## استيراد مساحات الأسماء

لبدء العمل، استورد مساحات الأسماء الضرورية إلى مشروعك:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;
```

## الخطوة 1: تحميل ملف المشروع

أولاً، حمّل ملف Project الذي يحتوي على كائنات OLE التي تريد استخراجها:

```csharp
var project = new Project(DataDir + "Embedded.mpp");
```

> **نصيحة:** يجب أن يشير `DataDir` إلى المجلد الذي يوجد فيه ملف `.mpp` الخاص بك. هذه الخطوة تلبي متطلب **load project file**.

## الخطوة 2: تعريف امتدادات الملفات

أنشئ جدولًا يربط معرفات `FileFormat` الخاصة بـ OLE بأسماء ملفات الإخراج المطلوبة. هذا يجعل من السهل **export ole objects** بالامتدادات الصحيحة:

```csharp
IDictionary<string, string> extensions = new Dictionary<string, string>
{
    { "RTF", "_rtfFile_out.rtf" },
    { "MSWordDoc", "_wordFile_out.docx" },
    { "ExcelML12", "_excelFile_out.xlsx" }
};
```

## الخطوة 3: التجول عبر كائنات OLE واستخراج الملفات المضمنة

الآن، امشِ عبر كل كائن OLE في المشروع، تحقق من أن صيغته مدعومة، واكتب المحتوى الثنائي إلى ملف جديد:

```csharp
foreach (var oleObject in project.OleObjects)
{
    if (string.IsNullOrEmpty(oleObject.FileFormat) || !extensions.ContainsKey(oleObject.FileFormat))
    {
        continue;
    }

    var path = OutDir + "EmbeddedContent_" + extensions[oleObject.FileFormat];
    using (var stream = new FileStream(path, FileMode.Create))
    {
        stream.Write(oleObject.Content, 0, oleObject.Content.Length);
    }
}
```

> **نصيحة احترافية:** يجب أن يكون `OutDir` دليلًا قابلاً للكتابة. سيقوم الكود أعلاه بإنشاء ملفات مثل `EmbeddedContent__wordFile_out.docx`، مما يؤدي فعليًا إلى **extract ole objects** من المشروع.

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|-------|--------|----------|
| لا يتم إنشاء أي ملفات | `OutDir` غير موجود أو لا يملك صلاحية كتابة | تأكد من وجود الدليل وأن التطبيق لديه صلاحية الكتابة. |
| صيغة ملف غير متوقعة | `FileFormat` لكائن OLE غير موجود في القاموس | أضف الصيغة المفقودة إلى القاموس `extensions`. |
| كائنات OLE الكبيرة تسبب ضغطًا على الذاكرة | تحميل العديد من الكائنات الكبيرة مرة واحدة | عالج الكائنات واحدًا تلو الآخر كما هو موضح، أو قم ببثها مباشرة إلى القرص. |

## الأسئلة المتكررة

**س: ما هو كائن OLE؟**  
ج: كائن OLE (Object Linking and Embedding) هو تقنية تتيح تضمين أو ربط ملفات من تطبيقات أخرى داخل مستند.

**س: كيف يمكنني تثبيت Aspose.Tasks لـ .NET؟**  
ج: يمكنك تنزيل Aspose.Tasks لـ .NET من [here](https://releases.aspose.com/tasks/net/) واتباع تعليمات التثبيت المتوفرة.

**س: هل يمكنني العمل مع كائنات OLE في Aspose.Tasks دون معرفة مسبقة بـ C#؟**  
ج: رغم أن المعرفة الأساسية بـ C# موصى بها، فإن Aspose.Tasks يوفر وثائق شاملة وبرامج تعليمية تساعد المستخدمين على البدء بغض النظر عن خلفيتهم البرمجية.

**س: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Tasks؟**  
ج: نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Tasks من [here](https://releases.aspose.com/).

**س: أين يمكنني العثور على الدعم لـ Aspose.Tasks؟**  
ج: يمكنك طلب الدعم وطرح الأسئلة على منتدى Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

---

**آخر تحديث:** 2026-03-14  
**تم الاختبار مع:** Aspose.Tasks 24.11 لـ .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}