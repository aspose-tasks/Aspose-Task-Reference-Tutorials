---
title: التلاعب بمعايير مجموعة مشروع MS في Aspose.Tasks
linktitle: معايير المجموعة في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: اكتشف كيفية التعامل مع ملفات MS Project برمجياً في .NET باستخدام Aspose.Tasks. استرداد مجموعة المهام ومعلومات المعيار بأمثلة خطوة بخطوة.
type: docs
weight: 27
url: /ar/net/tasks-project-management/group-criteria/
---
## مقدمة
Aspose.Tasks for .NET عبارة عن واجهة برمجة تطبيقات قوية تسهل العمل مع ملفات Microsoft Project في تطبيقات .NET الخاصة بك. سواء كنت تقوم بتطوير برامج إدارة المشاريع أو تحتاج إلى معالجة بيانات المشروع برمجيًا، فإن Aspose.Tasks يقدم مجموعة شاملة من الميزات لتلبية احتياجاتك.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
### 1. المعرفة بـ C# و.NET Framework
يعد الإلمام بلغة البرمجة C# و.NET Framework أمرًا ضروريًا لفهم الأمثلة المقدمة في هذا البرنامج التعليمي وتنفيذها.
### 2. تثبيت Aspose.Tasks لـ .NET
 تأكد من تثبيت Aspose.Tasks for .NET في بيئة التطوير الخاصة بك. يمكنك تحميل المكتبة من[هنا](https://releases.aspose.com/tasks/net/) واتبع تعليمات التثبيت المقدمة.
### 3. بيئة التطوير المتكاملة (IDE)
قم بتثبيت IDE مثل Visual Studio على نظامك لكتابة كود C# وتنفيذه.

## استيراد مساحات الأسماء
للبدء، قم باستيراد مساحات الأسماء الضرورية في كود C# الخاص بك:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## الخطوة 1: قم بتحميل ملف Microsoft Project
أولاً، حدد المسار إلى ملف Microsoft Project الخاص بك:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```
 يستبدل`"Your Document Directory"` مع المسار إلى ملف المشروع الخاص بك.
## الخطوة 2: استرداد معلومات مجموعات المهام
بعد ذلك، قم باسترداد معلومات حول مجموعات المهام في المشروع:
```csharp
Console.WriteLine("Task Groups Count: " + project.TaskGroups.Count);
var group = project.TaskGroups.ToList()[1];
Console.WriteLine("Task Group Name: " + group.Name);
Console.WriteLine("Task Group Criteria count: " + group.GroupCriteria.Count);
```
يقوم مقتطف التعليمات البرمجية هذا بطباعة العدد الإجمالي لمجموعات المهام، ويسترد مجموعة المهام الثانية واسمها وعدد المعايير التي تحتوي عليها.
## الخطوة 3: استرداد معلومات معيار مجموعة المهام
الآن، دعونا نتعمق في تفاصيل معيار محدد ضمن مجموعة المهام:
```csharp
var criterion = group.GroupCriteria.ToList()[0];
Console.WriteLine("Task Criterion Index: " + criterion.Index);
Console.WriteLine("Task Criterion Field: " + criterion.Field);
Console.WriteLine("Task Criterion GroupOn: " + criterion.GroupOn);
Console.WriteLine("Task Criterion Cell Color: " + criterion.CellColor);
Console.WriteLine("Task Criterion Font Color: " + criterion.FontColor);
Console.WriteLine("Task Criterion Group Interval: " + criterion.GroupInterval);
Console.WriteLine("Task Criterion Start At: " + criterion.StartAt);
```
يعرض هذا الجزء خصائص مختلفة للمعيار مثل الفهرس والحقل ومعلومات التجميع ولون الخلية ولون الخط والفاصل الزمني للمجموعة ونقطة البداية.
## الخطوة 4: استرداد معلومات الخط الخاص بالمعيار
وأخيرًا، احصل على تفاصيل المعيار المتعلقة بالخط:
```csharp
Console.WriteLine("Font Name: " + criterion.Font.FontFamily);
Console.WriteLine("Font Size: " + criterion.Font.Size);
Console.WriteLine("Font Style: " + criterion.Font.Style);
Console.WriteLine("Ascending/Descending: " + criterion.Ascending);
```
تقوم هذه الخطوة بطباعة اسم الخط وحجمه ونمطه وما إذا كان المعيار قد تم فرزه بترتيب تصاعدي أو تنازلي.

## خاتمة
في هذا البرنامج التعليمي، اكتشفنا كيفية استخدام Aspose.Tasks لـ .NET لاسترداد معلومات حول مجموعات المهام والمعايير من ملف Microsoft Project. باتباع الدليل خطوة بخطوة، يمكنك العمل بكفاءة مع بيانات المشروع برمجيًا في تطبيقات .NET الخاصة بك.
## الأسئلة الشائعة
### هل يستطيع Aspose.Tasks التعامل مع ملفات Microsoft Project الكبيرة؟
تم تحسين Aspose.Tasks للتعامل مع ملفات المشاريع الكبيرة بكفاءة، مما يضمن الأداء العالي والموثوقية.
### هل Aspose.Tasks متوافق مع كافة إصدارات Microsoft Project؟
نعم، يدعم Aspose.Tasks إصدارات مختلفة من Microsoft Project، مما يضمن التوافق عبر تنسيقات الملفات المختلفة.
### هل يمكنني معالجة بيانات المشروع باستخدام Aspose.Tasks؟
بالتأكيد، يوفر Aspose.Tasks وظائف واسعة النطاق لمعالجة بيانات المشروع، بما في ذلك المهام والموارد والتقويمات والمزيد.
### هل يقدم Aspose.Tasks الدعم لمنصات .NET المختلفة؟
نعم، يدعم Aspose.Tasks منصات .NET المتعددة بما في ذلك .NET Framework و.NET Core و.NET Standard.
### هل يوجد منتدى مجتمعي لـ Aspose.Tasks حيث يمكنني طلب المساعدة؟
 نعم يمكنك زيارة[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15) لطرح الأسئلة ومشاركة المعرفة والتعاون مع المستخدمين الآخرين.