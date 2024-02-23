---
title: دليل تخصيص أنماط نص الجدول في Aspose.Tasks
linktitle: تكوين أنماط نص الجدول في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تحسين تصور المشروع باستخدام Aspose.Tasks لـ .NET. تعلم كيفية تكوين أنماط نص الجدول خطوة بخطوة. تعزيز الكفاءة والعرض.
type: docs
weight: 14
url: /ar/net/task-table-management/table-text-styles/
---
## مقدمة
في عالم إدارة المشاريع، يعد التصور الفعال للمهام أمرًا بالغ الأهمية لتحقيق النجاح. يوفر Aspose.Tasks for .NET حلاً قويًا لتخصيص أنماط نص الجدول، مما يسمح لك بتخصيص مظهر العناصر النصية في مشروعك. في هذا الدليل التفصيلي، سنرشدك خلال عملية تكوين أنماط نص الجدول باستخدام Aspose.Tasks لـ .NET.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك ما يلي:
-  Aspose.Tasks لـ .NET: تأكد من تثبيت أحدث إصدار من Aspose.Tasks لـ .NET. يمكنك تنزيله[هنا](https://releases.aspose.com/tasks/net/).
- دليل المستندات: قم بإعداد دليل لمستنداتك. استبدل "دليل المستندات الخاص بك" في الكود بالمسار الفعلي.
-  ترخيص Aspose صالح: يتطلب هذا المثال ترخيص Aspose صالحًا. يمكنك شراء ترخيص كامل[هنا](https://purchase.aspose.com/buy) أو الحصول على ترخيص مؤقت لمدة 30 يومًا[هنا](https://purchase.aspose.com/temporary-license/).
## استيراد مساحات الأسماء
قبل البدء في البرمجة، قم باستيراد مساحات الأسماء اللازمة للاستفادة من وظائف Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
الآن، دعونا نقسم المثال إلى عدة خطوات:
## الخطوة 1: تحميل المشروع وتعيين خصائص المشروع
```csharp
var project = new Project(DataDir + "Project2.mpp");
project.Set(Prj.NewTasksAreManual, false);
```
## الخطوة 2: الوصول إلى عرض مخطط جانت
```csharp
var view = (GanttChartView)project.Views.ToList()[0];
```
## الخطوة 3: تخصيص نمط نص اسم المهمة
```csharp
var style1 = new TableTextStyle(1);
style1.Field = Field.TaskName;
style1.Font = new FontDescriptor("Impact", 12F, FontStyles.Bold | FontStyles.Italic);
view.TableTextStyles.Add(style1);
```
## الخطوة 4: تخصيص نمط نص مدة المهمة
```csharp
var style2 = new TableTextStyle(2);
style2.Field = Field.TaskDurationText;
style2.Font = new FontDescriptor("Impact", 16F, FontStyles.Underline);
view.TableTextStyles.Add(style2);
```
## الخطوة 5: احفظ المشروع باستخدام الأنماط المخصصة
```csharp
SimpleSaveOptions options = new MPPSaveOptions
{
    WriteViewData = true
};
project.Save(DataDir + "WorkWithTableTextStyle_out.mpp", options);
```
## الخطوة 6: التعامل مع استثناء الترخيص
```csharp
catch (NotSupportedException ex)
{
    Console.WriteLine(
        ex.Message
        + "\nThis example will only work if you apply a valid Aspose License. You can purchase a full license or get a 30-day temporary license from [Aspose](http://www.aspose.com/purchase/default.aspx.");
}
```
## خاتمة
يوفر تخصيص أنماط نص الجدول في Aspose.Tasks لـ .NET طريقة مرنة وفعالة لتحسين التمثيل المرئي لمشروعك. من خلال بضع خطوات بسيطة، يمكنك إنشاء تجربة إدارة مشروع أكثر تخصيصًا وتأثيرًا.
## أسئلة مكررة
### هل يمكنني استخدام Aspose.Tasks لـ .NET بدون ترخيص؟
 لا، يلزم وجود ترخيص Aspose صالح لهذه الوظيفة. يمكنك الحصول على ترخيص[هنا](https://purchase.aspose.com/buy) أو احصل على ترخيص مؤقت لمدة 30 يومًا[هنا](https://purchase.aspose.com/temporary-license/).
### كيف أقوم بتحديث نمط الخط لسمات المهام الأخرى؟
 ببساطة قم بإنشاء المزيد`TableTextStyle` المثيلات، وتحديد الحقل المطلوب وإعدادات الخط.
### هل هناك إصدار تجريبي متاح لـ Aspose.Tasks لـ .NET؟
 نعم يمكنك تحميل النسخة التجريبية[هنا](https://releases.aspose.com/).
### هل هناك خيارات تصور أخرى توفرها Aspose.Tasks؟
نعم، يقدم Aspose.Tasks ميزات تصور متنوعة لتلبية احتياجات إدارة المشاريع المختلفة.
### هل يمكنني تخصيص الأنماط لأنواع مهام محددة؟
بالتأكيد، يمكنك توسيع التخصيص ليشمل أنواع المهام المختلفة عن طريق ضبط إعدادات الحقل والخط وفقًا لذلك.