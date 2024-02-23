---
title: تكوين طرق عرض الاستخدام في Aspose.Tasks
linktitle: تكوين طرق عرض الاستخدام في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية تكوين طرق عرض استخدام المهام في Aspose.Tasks لـ .NET. تعزيز تصور المشروع بخطوات تفصيلية. قم بتنزيل المكتبة الآن!
type: docs
weight: 17
url: /ar/net/text-view-configuration/usage-views/
---
## مقدمة
إذا كنت مطور .NET وتتطلع إلى تحسين قدرات إدارة مشروعك، فإن Aspose.Tasks هي أداة قوية تسمح لك بمعالجة ملفات Microsoft Project دون عناء. في هذا البرنامج التعليمي، سنركز على تكوين طرق عرض الاستخدام باستخدام Aspose.Tasks لـ .NET. تابع للحصول على رؤى حول عرض طرق عرض استخدام المهام مع تفاصيل لتحسين تصور المشروع.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
- مكتبة Aspose.Tasks: تأكد من دمج مكتبة Aspose.Tasks في مشروع .NET الخاص بك. إذا لم يكن الأمر كذلك، يمكنك تنزيله[هنا](https://releases.aspose.com/tasks/net/) واتبع تعليمات التثبيت.
- دليل المستندات: قم بإعداد دليل حيث يتم تخزين مستندات مشروعك. استبدل "دليل المستندات الخاص بك" في مقتطفات التعليمات البرمجية بالمسار الفعلي إلى دليل المستند.
## استيراد مساحات الأسماء
في مقتطف الشفرة المقدم، ستلاحظ استخدام مساحات أسماء معينة. تأكد من تضمينها في مشروعك لتحقيق التكامل السلس:
```csharp
using Aspose.Tasks;
using Aspose.Tasks.Visualization;
using Aspose.Tasks.Saving;
```
## الخطوة 1: عرض عرض استخدام المهام مع التفاصيل
لنبدأ بعرض طريقة عرض استخدام المهمة مع التفاصيل. اتبع الخطوات التالية:
## الخطوة 1.1: تحميل المشروع
```csharp
// المسار إلى دليل المستندات.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "TaskUsageViewWithDetails.mpp");
```
## الخطوة 1.2: احصل على العرض
```csharp
UsageView view = (TaskUsageView)project.DefaultView;
```
## الخطوة 1.3: تخصيص إعدادات العرض
```csharp
view.DisplayDetailsHeaderColumn = false;
view.RepeatDetailsHeaderOnAllRows = false;
view.DisplayShortDetailHeaderNames = false;
view.AlignDetailsData = HorizontalStringAlignment.Near;
```
## الخطوة 1.4: حفظ المشروع بصيغة PDF
```csharp
project.Save(DataDir + "task_usage1_out.pdf", SaveFileFormat.Pdf);
```
## الخطوة 2: عرض عمود رأس التفاصيل
في هذه الخطوة، سنقوم بتعديل إعدادات العرض لعرض عمود رأس التفاصيل وحفظ المشروع بصيغة PDF:
## الخطوة 2.1: عرض عمود رأس التفاصيل
```csharp
view.DisplayDetailsHeaderColumn = true;
```
## الخطوة 2.2: كرر رأس التفاصيل في جميع الصفوف
```csharp
view.RepeatDetailsHeaderOnAllRows = true;
view.AlignDetailsData = HorizontalStringAlignment.Far;
```
## الخطوة 2.3: حفظ المشروع بصيغة PDF
```csharp
project.Save(DataDir + "task_usage2_out.pdf", SaveFileFormat.Pdf);
```
## خاتمة
تهانينا! لقد قمت بتكوين طرق عرض الاستخدام بنجاح في Aspose.Tasks. يوفر هذا البرنامج التعليمي أساسًا لإدارة المشروعات والتصور بكفاءة باستخدام مكتبة Aspose.Tasks.

### الأسئلة الشائعة
### س: أين يمكنني العثور على وثائق Aspose.Tasks؟
 الوثائق الشاملة متاحة[هنا](https://reference.aspose.com/tasks/net/).
### س: كيف يمكنني تنزيل Aspose.Tasks لـ .NET؟
 تحميل المكتبة[هنا](https://releases.aspose.com/tasks/net/).
### س: أين يمكنني شراء Aspose.Tasks؟
 يمكنك شراء Aspose.Tasks[هنا](https://purchase.aspose.com/buy).
### س: هل هناك نسخة تجريبية مجانية متاحة؟
 نعم، استكشف النسخة التجريبية المجانية[هنا](https://releases.aspose.com/).
### س: هل تحتاج إلى دعم أو لديك أسئلة؟
 قم بزيارة منتدى الدعم[هنا](https://forum.aspose.com/c/tasks/15).