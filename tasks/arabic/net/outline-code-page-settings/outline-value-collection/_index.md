---
title: إدارة القيم التفصيلية لمشروع MS باستخدام Aspose.Tasks
linktitle: مجموعة من القيم التفصيلية في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية إدارة القيم التفصيلية في ملفات Microsoft Project باستخدام Aspose.Tasks لـ .NET. برنامج تعليمي خطوة بخطوة مع أمثلة التعليمات البرمجية.
type: docs
weight: 17
url: /ar/net/outline-code-page-settings/outline-value-collection/
---
## مقدمة
يوفر Aspose.Tasks for .NET مجموعة شاملة من الميزات للتفاعل مع ملفات Microsoft Project. إحدى هذه الميزات هي القدرة على إدارة قيم المخطط التفصيلي داخل المشروع. في هذا البرنامج التعليمي، سنستكشف كيفية جمع القيم التفصيلية ومعالجتها باستخدام Aspose.Tasks لـ .NET.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
1.  Aspose.Tasks لـ .NET: يمكنك تنزيل المكتبة من[هنا](https://releases.aspose.com/tasks/net/).
2. بيئة التطوير: تأكد من تثبيت IDE مناسب، مثل Visual Studio.
3. المعرفة الأساسية بـ C#: الإلمام بلغة البرمجة C# سيكون مفيدًا.
## استيراد مساحات الأسماء
في ملف التعليمات البرمجية C# الخاص بك، قم باستيراد مساحات الأسماء الضرورية للوصول إلى فئات Aspose.Tasks وطرقها:
```csharp
using Aspose.Tasks;
using System;

```
دعنا نقسم المثال المقدم إلى خطوات متعددة:
## الخطوة 1: تحميل ملف المشروع
 أولاً، قم بتهيئة أ`Project` كائن عن طريق تحميل ملف Microsoft Project موجود:
```csharp
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
## الخطوة 2: مسح قيم المخطط التفصيلي الموجودة
بعد ذلك، قم بمسح أي قيم مخطط تفصيلي موجودة من المشروع:
```csharp
foreach (var outlineCode in project.OutlineCodes)
{
    if (outlineCode.Values.Count <= 0)
    {
        continue;
    }
    if (!outlineCode.Values.IsReadOnly)
    {
        outlineCode.Values.Clear();
    }
}
```
## الخطوة 3: تحديد رمز المخطط التفصيلي الجديد
الآن، حدد رمز المخطط التفصيلي الجديد مع الوصف والقيمة:
```csharp
var codeDefinition = new OutlineCodeDefinition
{
    Alias = "New task outline code1",
    FieldId = ((int)ExtendedAttributeTask.OutlineCode1).ToString(),
    FieldName = "Outline Code1"
};
var value = new OutlineValue { Description = "Value description", ValueId = 1, Value = "123456", Type = OutlineValueType.Number };
codeDefinition.Values.Add(value);
project.OutlineCodes.Add(codeDefinition);
```
## الخطوة 4: تحديث قيمة المخطط التفصيلي
تحديث قيمة رمز المخطط التفصيلي:
```csharp
codeDefinition.Values[0].Value = "654321";
```
## الخطوة 5: التكرار على قيم المخطط التفصيلي
قم بالتكرار من خلال قيم المخطط التفصيلي وطباعة تفاصيلها:
```csharp
foreach (var definitionValue in codeDefinition.Values)
{
    Console.WriteLine("Value: " + definitionValue.Value);
    Console.WriteLine("Value Id: " + definitionValue.ValueId);
    Console.WriteLine("Value Guid: " + definitionValue.ValueGuid);
    Console.WriteLine();
}
```
## الخطوة 6: التعامل مع القيم التفصيلية
قم بإجراء عمليات مثل إزالة القيم التفصيلية وإدراجها ونسخها حسب الحاجة:
```csharp
if (codeDefinition.Values.Contains(value))
{
    codeDefinition.Values.Remove(value);
}
codeDefinition.Values.Insert(0, value);
Console.WriteLine("Index of inserted value: " + codeDefinition.Values.IndexOf(value));
codeDefinition.Values.RemoveAt(codeDefinition.Values.Count - 1);
var codeDefinition2 = new OutlineCodeDefinition
{
    Alias = "New outline code 2",
    FieldId = ((int)ExtendedAttributeTask.OutlineCode2).ToString(),
    FieldName = "Outline Code2"
};
var outlineValues = new OutlineValue[codeDefinition.Values.Count];
codeDefinition.Values.CopyTo(outlineValues, 0);
foreach (var outlineValue in outlineValues)
{
    codeDefinition2.Values.Add(outlineValue);
}
```
## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية العمل مع القيم التفصيلية في ملفات Microsoft Project باستخدام Aspose.Tasks لـ .NET. باتباع الخطوات المتوفرة، يمكنك إدارة القيم التفصيلية داخل مشاريعك بكفاءة، مما يتيح قدرًا أكبر من التحكم والمرونة.
## الأسئلة الشائعة
### س: هل يمكنني التعامل مع رموز المخطط التفصيلي المتعددة في وقت واحد؟
ج: نعم، يمكنك تحديد ومعالجة رموز المخطط التفصيلي المتعددة داخل المشروع باستخدام Aspose.Tasks.
### س: هل Aspose.Tasks متوافق مع الإصدارات المختلفة من ملفات Microsoft Project؟
ج: نعم، يدعم Aspose.Tasks إصدارات مختلفة من ملفات Microsoft Project، بما في ذلك تنسيقات MPP وXML.
### س: كيف يمكنني معالجة الأخطاء أثناء العمل باستخدام القيم التفصيلية؟
ج: يمكنك تنفيذ آليات معالجة الأخطاء مثل كتل محاولة الالتقاط لإدارة الاستثناءات بأمان.
### س: هل يمكنني تخصيص مظهر القيم التفصيلية في مشروعي؟
ج: نعم، يوفر Aspose.Tasks واجهات برمجة تطبيقات واسعة النطاق لتخصيص مظهر وسلوك قيم المخطط التفصيلي وفقًا لمتطلباتك.
### س: أين يمكنني العثور على موارد إضافية ودعم لـ Aspose.Tasks؟
 ج: يمكنك زيارة[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15) لدعم المجتمع واستكشاف[توثيق](https://reference.aspose.com/tasks/net/) للحصول على معلومات مفصلة حول واجهات برمجة التطبيقات والميزات.