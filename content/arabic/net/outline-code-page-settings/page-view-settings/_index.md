---
title: قم بتخصيص إعدادات عرض صفحة مشروع MS في Aspose.Tasks
linktitle: قم بتكوين إعدادات عرض الصفحة في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية تكوين إعدادات عرض الصفحة في Aspose.Tasks لـ .NET لتخصيص تنسيق الطباعة لمستندات Microsoft Project الخاصة بك.
type: docs
weight: 21
url: /ar/net/outline-code-page-settings/page-view-settings/
---
## مقدمة
يعد Microsoft Project أداة قوية لإدارة المشاريع، ولكن في بعض الأحيان تحتاج إلى تخصيص طريقة عرض مشروعك وطباعته. باستخدام Aspose.Tasks for .NET، يمكنك بسهولة تكوين إعدادات عرض الصفحة لتلبية متطلباتك المحددة. في هذا البرنامج التعليمي، سنرشدك خلال العملية خطوة بخطوة.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
1.  Aspose.Tasks لـ .NET: تأكد من تنزيل وتثبيت Aspose.Tasks لمكتبة .NET. يمكنك تنزيله من[هنا](https://releases.aspose.com/tasks/net/).
2. ملف Microsoft Project: قم بإعداد ملف Microsoft Project الذي تريد تكوين إعدادات عرض الصفحة له.

## استيراد مساحات الأسماء
أولاً، تحتاج إلى استيراد مساحات الأسماء الضرورية للعمل مع Aspose.Tasks في مشروع .NET الخاص بك.
```csharp
    
    using Aspose.Tasks.Saving;
```
## الخطوة 1: تحميل ملف المشروع
 ابدأ بتحميل ملف Microsoft Project الخاص بك إلى مثيل`Project` فصل.
```csharp
// المسار إلى دليل المستندات.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Input.mpp");
```
## الخطوة 2: تعيين عدد الأعمدة الأولى
حدد عدد الأعمدة الأولى التي سيتم طباعتها على كافة الصفحات.
```csharp
project.DefaultView.PageInfo.PageViewSettings.FirstColumnsCount = 2;
```
## الخطوة 3: طباعة الملاحظات
اختر ما إذا كنت تريد طباعة الملاحظات مع المشروع.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintNotes = true;
```
## الخطوة 4: ملاءمة الجدول الزمني لنهاية الصفحة
قرر ما إذا كنت تريد ملاءمة المقياس الزمني لنهاية الصفحة عند الطباعة.
```csharp
project.DefaultView.PageInfo.PageViewSettings.FitTimescaleToEndOfPage = true;
```
## الخطوة 5: طباعة كافة أعمدة الورقة
حدد ما إذا كنت تريد طباعة كافة أعمدة الورقة في طريقة العرض.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintAllSheetColumns = true;
```
## الخطوة 6: طباعة الصفحات الفارغة
اختر ما إذا كنت تريد طباعة صفحات فارغة من طريقة العرض.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintBlankPages = false;
```
## الخطوة 7: طباعة الأعمدة الأولى في جميع الصفحات
قم بتعيين ما إذا كنت تريد طباعة عدد محدد من الأعمدة الأولى في كافة الصفحات.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintFirstColumnsCountOnAllPages = true;
```
## الخطوة 8: احفظ المشروع بالإعدادات التي تم تكوينها
وأخيرًا، احفظ المشروع باستخدام إعدادات عرض الصفحة التي تم تكوينها، مع تحديد تنسيق الإخراج، مثل PDF.
```csharp
project.Save(DataDir + "ProjectWithComments_out.pdf", SaveFileFormat.Pdf);
```

## خاتمة
يعد تكوين إعدادات عرض صفحة Microsoft Project في Aspose.Tasks لـ .NET أمرًا مباشرًا ويسمح لك بتخصيص تنسيق الطباعة وفقًا لاحتياجاتك المحددة. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك التأكد من تقديم مستندات مشروعك كما هو مطلوب تمامًا.
## الأسئلة الشائعة
### س: هل يمكنني تكوين إعدادات عرض الصفحة لتنسيقات ملفات أخرى إلى جانب PDF؟
ج: نعم، يدعم Aspose.Tasks تنسيقات ملفات متنوعة لحفظ المشاريع، بما في ذلك XLSX وMPP وHTML.
### س: هل هناك أي قيود على عدد الأعمدة التي يمكنني طباعتها؟
ج: يتيح لك Aspose.Tasks تخصيص عدد الأعمدة المراد طباعتها بناءً على متطلباتك.
### س: هل يمكنني تطبيق إعدادات عرض صفحة مختلفة لمشاريع مختلفة؟
ج: نعم، يمكنك ضبط إعدادات عرض الصفحة بشكل مستقل لكل ملف مشروع تعمل به.
### س: هل Aspose.Tasks متوافق مع كافة إصدارات Microsoft Project؟
ج: يوفر Aspose.Tasks التوافق مع Microsoft Project 2003 والإصدارات الأحدث.
### س: أين يمكنني العثور على مزيد من المساعدة أو الدعم لـ Aspose.Tasks؟
 ج: يمكنك زيارة[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15)لأية استفسارات أو مشاكل تواجهك أثناء الاستخدام.