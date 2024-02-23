---
title: جمع مشروع MS للأجزاء المقسمة في Aspose.Tasks
linktitle: مجموعة من الأجزاء المنقسمة في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية جمع الأجزاء المقسمة في MS Project باستخدام Aspose.Tasks لـ .NET. يرشدك هذا البرنامج التعليمي الشامل خلال العملية خطوة بخطوة.
type: docs
weight: 19
url: /ar/net/rate-recurring-tasks/split-part-collection/
---
## مقدمة
في هذا البرنامج التعليمي، سوف نتعمق في كيفية جمع الأجزاء المقسمة في MS Project باستخدام Aspose.Tasks لـ .NET. يمكن أن يكون تقسيم المهام إلى أجزاء جانبًا حاسمًا في إدارة المشاريع، ويوفر Aspose.Tasks طرقًا ملائمة للتعامل مع هذا الأمر بكفاءة.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
1. تثبيت Aspose.Tasks لـ .NET: تأكد من تثبيت Aspose.Tasks لـ .NET. يمكنك تنزيله من[هنا](https://releases.aspose.com/tasks/net/).
2. المعرفة الأساسية بـ C#: الإلمام بلغة البرمجة C# سيكون مفيدًا لأننا سنكتب مقتطفات من التعليمات البرمجية في C#.

## استيراد مساحات الأسماء
في مشروع C# الخاص بك، قم بتضمين مساحات الأسماء الضرورية:
```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;

```

## الخطوة 1: قم بإعداد مشروعك
أولاً، قم بإنشاء مشروع جديد في بيئة التطوير المتكاملة (IDE) المفضلة لديك وتأكد من الإشارة إلى Aspose.Tasks لـ .NET بشكل صحيح.
## الخطوة 2: تهيئة كائن المشروع
```csharp
// المسار إلى دليل المستندات.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Splits.mpp");
```
قم بتهيئة كائن مشروع جديد بالمسار إلى ملف MS Project الخاص بك.
## الخطوة 3: استرداد المهمة والتكرار على الأجزاء المقسمة
```csharp
var task = project.RootTask.Children.GetById(1);
// التكرار على الأجزاء المقسمة
Console.WriteLine("Iterate over split parts");
Console.WriteLine("Split parts count:" + task.SplitParts.Count);
foreach (var splitPart in task.SplitParts)
{
    Console.WriteLine("Start: " + splitPart.Start);
    Console.WriteLine("Finish: " + splitPart.Finish);
}
```
قم باسترجاع المهمة من المشروع وكررها على أجزائه المقسمة، مع طباعة تاريخي البدء والانتهاء.
## الخطوة 4: احصل على تقسيم الجزء حسب الفهرس
```csharp
// احصل على الجزء حسب الفهرس
var split = task.SplitParts[0];
Console.WriteLine("Split start: " + split.Start);
```
استرجع جزءًا محددًا مقسمًا حسب الفهرس واطبع تاريخ البدء الخاص به.

## خاتمة
يمكن أن تؤدي إدارة الأجزاء المقسمة في ملفات MS Project إلى تعزيز كفاءة إدارة المشروع بشكل كبير. يعمل Aspose.Tasks for .NET على تبسيط هذه العملية من خلال توفير واجهات برمجة التطبيقات البديهية للتعامل مع المهام المقسمة بسلاسة.
## الأسئلة الشائعة
### س: هل يمكنني تقسيم المهام ديناميكيًا أثناء وقت التشغيل؟
ج: نعم، يمكنك تقسيم المهام برمجيًا باستخدام Aspose.Tasks لـ .NET.
### س: هل يدعم Aspose.Tasks جميع إصدارات ملفات MS Project؟
ج: يدعم Aspose.Tasks إصدارات مختلفة من ملفات MS Project، مما يضمن التوافق عبر الأنظمة الأساسية المختلفة.
### س: هل هناك نسخة تجريبية متاحة لأغراض الاختبار؟
 ج: نعم، يمكنك الحصول على نسخة تجريبية مجانية من[هنا](https://releases.aspose.com/) للتقييم.
### س: كيف يمكنني الحصول على تراخيص مؤقتة لمشاريعي؟
 ج: يمكن الحصول على التراخيص المؤقتة من[هنا](https://purchase.aspose.com/temporary-license/) للاستخدام على المدى القصير.
### س: أين يمكنني طلب المساعدة أو الدعم فيما يتعلق بـ Aspose.Tasks؟
 ج: يمكنك زيارة منتدى Aspose.Tasks[هنا](https://forum.aspose.com/c/tasks/15) لطلب المساعدة من المجتمع أو فريق دعم Aspose.