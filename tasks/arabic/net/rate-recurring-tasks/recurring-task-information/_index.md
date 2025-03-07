---
title: استخراج معلومات المهمة المتكررة في Aspose.Tasks
linktitle: استخراج معلومات المهمة المتكررة في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية استخراج معلومات المهام المتكررة من ملفات MS Project باستخدام Aspose.Tasks لـ .NET. التكامل السهل لمطوري .NET.
weight: 13
url: /ar/net/rate-recurring-tasks/recurring-task-information/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# استخراج معلومات المهمة المتكررة في Aspose.Tasks

## مقدمة
Aspose.Tasks for .NET هي مكتبة قوية تسمح للمطورين بالعمل مع ملفات Microsoft Project في تطبيقات .NET الخاصة بهم. في هذا البرنامج التعليمي، سنستكشف كيفية استخراج معلومات المهام المتكررة من ملفات MS Project باستخدام Aspose.Tasks.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
1. الفهم الأساسي للغة البرمجة C#.
2. تم تثبيت Visual Studio على نظامك.
3.  تم تثبيت Aspose.Tasks لمكتبة .NET. يمكنك تنزيله من[هنا](https://releases.aspose.com/tasks/net/).
## استيراد مساحات الأسماء
للبدء، قم باستيراد مساحات الأسماء الضرورية في كود C# الخاص بك:
```csharp
    using Aspose.Tasks;
    using System;
    
```
الآن، دعونا نقسم المثال إلى عدة خطوات:
## الخطوة 1: إعداد مسار ملف المشروع
```csharp
String DataDir = "Your Document Directory";
```
 يستبدل`"Your Document Directory"` مع المسار إلى ملف MS Project الخاص بك.
## الخطوة 2: قم بتحميل ملف MS Project
```csharp
var project = new Project(DataDir + "TestRecurringTask2016.mpp");
```
 يقوم هذا الخط بتهيئة ملف جديد`Project` الكائن عن طريق تحميل ملف MS Project المحدد بواسطة المسار.
## الخطوة 3: قراءة المعلومات المتكررة للمهام
```csharp
foreach (var task in project.RootTask.SelectAllChildTasks())
{
    var info = task.RecurringInfo;
    if (info == null)
    {
        continue;
    }
    // الوصول وعرض معلومات المهمة المتكررة
    Console.WriteLine("Start Date: " + info.StartDate);
    Console.WriteLine("Duration: " + info.Duration);
    Console.WriteLine("End Date: " + info.EndDate);
    // استمر في عرض معلومات المهمة المتكررة الأخرى حسب الحاجة
}
```
تتكرر هذه الحلقة خلال جميع المهام في المشروع وتتحقق مما إذا كانت كل مهمة تحتوي على معلومات متكررة مرتبطة بها. إذا حدث ذلك، فإنه يسترد ويعرض خصائص مختلفة للمهمة المتكررة، مثل تاريخ البدء والمدة وتاريخ الانتهاء وما إلى ذلك.
## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية استخراج معلومات المهام المتكررة من ملفات MS Project باستخدام Aspose.Tasks لـ .NET. ومن خلال هذه المعرفة، يمكنك الآن دمج هذه الوظيفة في تطبيقات .NET الخاصة بك للعمل مع المهام المتكررة بشكل أكثر كفاءة.
## الأسئلة الشائعة
### س: هل يمكنني تعديل معلومات المهمة المتكررة باستخدام Aspose.Tasks لـ .NET؟
ج: نعم، يمكنك تعديل معلومات المهمة المتكررة برمجيًا باستخدام واجهات برمجة التطبيقات المتوفرة.
### س: هل يدعم Aspose.Tasks تنسيقات ملفات المشروع الأخرى إلى جانب MS Project؟
ج: نعم، يدعم Aspose.Tasks تنسيقات ملفات المشروع المختلفة مثل MPP، وXML، وCSV.
### س: هل تتوفر نسخة تجريبية مجانية من Aspose.Tasks لـ .NET؟
 ج: نعم، يمكنك تنزيل نسخة تجريبية مجانية من[هنا](https://releases.aspose.com/).
### س: أين يمكنني العثور على وثائق Aspose.Tasks لـ .NET؟
 ج: يمكنك العثور على الوثائق[هنا](https://reference.aspose.com/tasks/net/).
### س: كيف يمكنني الحصول على الدعم الفني لـ Aspose.Tasks لـ .NET؟
 ج: يمكنك الحصول على الدعم الفني من منتدى Aspose.Tasks[هنا](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
