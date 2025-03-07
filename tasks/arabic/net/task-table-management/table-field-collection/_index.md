---
title: إتقان مجموعات حقول الجدول في Aspose.Tasks لـ .NET
linktitle: مجموعة من حقول الجدول في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: استكشف العالم الديناميكي لإدارة المشاريع باستخدام Aspose.Tasks لـ .NET. تعرف على كيفية التعامل مع مجموعات حقول الجدول للحصول على تجربة مشروع مخصصة.
weight: 13
url: /ar/net/task-table-management/table-field-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إتقان مجموعات حقول الجدول في Aspose.Tasks لـ .NET

## مقدمة
Aspose.Tasks for .NET هي مكتبة قوية تسهل إدارة المشاريع من خلال توفير وظائف واسعة النطاق للعمل مع ملفات Microsoft Project. في هذا البرنامج التعليمي، سوف نتعمق في مجموعة حقول الجدول في Aspose.Tasks، ونستكشف كيفية التعامل معها وإدارتها بكفاءة باستخدام C#.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك الإعداد التالي:
- معرفة عملية بلغة البرمجة C#.
-  تم تثبيت Aspose.Tasks لمكتبة .NET. يمكنك تنزيله[هنا](https://releases.aspose.com/tasks/net/).
- بيئة تطوير متكاملة (IDE) مثل Visual Studio.
## استيراد مساحات الأسماء
أولاً، تأكد من استيراد مساحات الأسماء الضرورية في بداية ملف C# الخاص بك:
```csharp
    using Aspose.Tasks;
    using System;
    
```
الآن، دعونا نقسم كل مثال إلى خطوات متعددة بتنسيق دليل خطوة بخطوة.
## الخطوة 1: قم بتعيين دليل المستندات
قم بتعيين المسار إلى دليل المستندات الخاص بك حيث يوجد ملف المشروع الخاص بك.
```csharp
String DataDir = "Your Document Directory";
```
## الخطوة 2: تحميل ملف المشروع
قم بتحميل ملف المشروع باستخدام مكتبة Aspose.Tasks.
```csharp
var project = new Project(DataDir + "Project1.mpp");
```
## الخطوة 3: التكرار على حقول الجدول
قم بالتكرار فوق حقول الجدول داخل المشروع.
```csharp
foreach (var tbl in project.Tables)
{
    Console.WriteLine("Table name: " + tbl.Name);
    Console.WriteLine("Is collection of table fields read-only?: " + tbl.TableFields.IsReadOnly);
    //التكرار على حقول الجدول
    Console.WriteLine("Print table fields of " + project.Get(Prj.Name) + " project.");
    Console.WriteLine("Table count: " + tbl.TableFields.Count);
    foreach (var fld in tbl.TableFields)
    {
        Console.WriteLine("Field Title: " + fld.Title);
        Console.WriteLine("Field Field: " + fld.Field);
        Console.WriteLine();
    }
}
```
## الخطوة 4: إضافة حقل جدول جديد
إضافة حقل جدول جديد إلى الجدول الموجود.
```csharp
var table = project.Tables.ToList()[0];
var field = new TableField();
field.Title = "New Table Field";
table.TableFields.Add(field);
```
## الخطوة 5: أدخل حقل جديد
قم بإدراج حقل جديد في موضع محدد داخل الجدول.
```csharp
var field2 = new TableField();
field2.Title = "New Table Field 2";
var idx = table.TableFields.IndexOf(field);
table.TableFields.Insert(idx, field2);
```
## الخطوة 6: تحرير حقل الجدول الجديد
قم بتحرير حقل الجدول المضاف حديثًا باستخدام الوصول إلى الفهرس.
```csharp
table.TableFields[idx].WrapHeader = true;
```
## الخطوة 7: إزالة الحقل
قم بإزالة حقل الجدول واحدًا تلو الآخر أو قم بمسح المجموعة بأكملها.
```csharp
Console.WriteLine("The collection contains the new table field?: " + table.TableFields.Contains(field));
// قم بإزالة الحقل
table.TableFields.RemoveAt(idx);
```
## الخطوة 8: مسح المجموعة
امسح مجموعة حقول الجدول إما واحدة تلو الأخرى أو بالكامل.
```csharp
if (deleteOneByOne)
{
    // إزالة واحدا تلو الآخر
    var tableFields = new TableField[table.TableFields.Count];
    table.TableFields.CopyTo(tableFields, 0);
    foreach (var fld in tableFields)
    {
        table.TableFields.Remove(fld);
    }
}
else
{
    // امسح المجموعة بالكامل
    table.TableFields.Clear();
}
```
لقد نجحت الآن في استكشاف مجموعة حقول الجدول في Aspose.Tasks لـ .NET، مما يتيح لك إدارتها ومعالجتها وفقًا لمتطلبات مشروعك.
## خاتمة
في الختام، فإن فهم كيفية العمل مع مجموعات حقول الجدول في Aspose.Tasks لـ .NET يفتح إمكانيات إدارة المشروع وتخصيصه بكفاءة. بفضل المرونة التي يوفرها Aspose.Tasks، يمكن للمطورين تصميم تطبيقاتهم لتلبية احتياجات المشروع المحددة بسلاسة.
## أسئلة مكررة
### هل يمكنني استخدام Aspose.Tasks لـ .NET مع أي إصدار من ملفات Microsoft Project؟
نعم، يدعم Aspose.Tasks إصدارات مختلفة من ملفات Microsoft Project، مما يضمن التوافق والمرونة.
### هل من الممكن إنشاء حقول الجدول وتعديلها ديناميكيًا أثناء وقت التشغيل؟
قطعاً! كما هو موضح في البرنامج التعليمي، يمكنك إضافة حقول الجدول وإدراجها وتحريرها وإزالتها ديناميكيًا حسب الحاجة.
### هل هناك أي اعتبارات ترخيص لاستخدام Aspose.Tasks لـ .NET في مشروع تجاري؟
 نعم، أنت بحاجة إلى ترخيص صالح لاستخدام Aspose.Tasks لـ .NET في مشروع تجاري. يمكنك الحصول على ترخيص[هنا](https://purchase.aspose.com/buy).
### كيف يمكنني الحصول على الدعم أو طلب المساعدة فيما يتعلق بـ Aspose.Tasks لـ .NET؟
 قم بزيارة[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15)للحصول على الدعم وطرح الأسئلة والتعاون مع المجتمع.
### هل تتوفر نسخة تجريبية مجانية من Aspose.Tasks لـ .NET؟
 نعم، يمكنك استكشاف ميزات Aspose.Tasks لـ .NET من خلال النسخة التجريبية المجانية. تنزيله[هنا](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
