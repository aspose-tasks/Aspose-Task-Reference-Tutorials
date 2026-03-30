---
date: 2026-03-16
description: تعلم كيفية إزالة كائنات OLE باستخدام Aspose.Tasks لـ .NET، واكتشف كيفية
  إدارة OLE ومسح OLE بفعالية في مشاريعك.
linktitle: How to Remove OLE Objects in Aspose.Tasks for .NET
second_title: Aspose.Tasks .NET API
title: كيفية إزالة كائنات OLE في Aspose.Tasks لـ .NET
url: /ar/net/advanced-concepts/ole-objects/
weight: 22
---

 present; they are placeholders. So we keep them.

Also ensure we keep the blockquote formatting.

Now produce final answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إزالة كائنات OLE في Aspose.Tasks لـ .NET

## المقدمة

يمنحك Aspose.Tasks لـ .NET التحكم الكامل في كائنات OLE (Object Linking and Embedding) التي تعيش داخل ملفات Microsoft Project. في هذا البرنامج التعليمي ستتعلم **كيفية إزالة كائنات OLE**، وكيفية **إدارة محتوى OLE**، والخطوات الدقيقة **لإزالة بيانات OLE** عندما لا تكون بحاجة إليها بعد الآن. في النهاية، ستتمكن من تحميل ملف مشروع، فحص كائنات OLE المضمنة، حذفها بأمان، وحفظ المشروع المنقّح — كل ذلك باستخدام كود C# نظيف وقابل للقراءة.

## إجابات سريعة
- **ما هي الطريقة الأساسية لإزالة كائنات OLE؟** استخدم `project.OleObjects.Clear()` ثم احفظ المشروع.  
- **هل أحتاج إلى ترخيص خاص؟** يتطلب الاستخدام في بيئة الإنتاج ترخيصًا صالحًا لـ Aspose.Tasks.  
- **ما إصدارات .NET المدعومة؟** .NET Framework 4.5+، .NET Core 3.1+، .NET 5/6+.  
- **هل يمكنني فحص محتوى OLE قبل إزالته؟** نعم، يمكنك التكرار عبر `project.OleObjects` لقراءة الخصائص أو بايتات المحتوى.  
- **هل من الآمن مسح كائنات OLE في المشاريع الكبيرة؟** بالتأكيد – العملية سريعة ولا تؤثر على بيانات المشروع الأخرى.

## ما معنى “إزالة كائنات OLE” في سياق Aspose.Tasks؟

يعني إزالة كائنات OLE حذف الملفات المضمنة (صور، جداول Excel، مستندات Word، إلخ) المخزنة داخل ملف Microsoft Project (.mpp). هذا مفيد عندما تريد تقليل حجم الملف، إزالة المراجع القديمة، أو الالتزام بسياسات الاحتفاظ بالبيانات.

## لماذا إدارة كائنات OLE باستخدام Aspose.Tasks؟

- **تحكم دقيق** – الوصول إلى معرف كل كائن OLE، اسمه، والبايتات الخام.  
- **أتمتة** – تنظيف عشرات المشاريع برمجيًا دون فتحها في Microsoft Project.  
- **دعم عبر الإصدارات** – يعمل مع ملفات Project من 2007 إلى 2023.  

## المتطلبات المسبقة

قبل أن نبدأ، تأكد من أن لديك:

1. **Aspose.Tasks لـ .NET** مثبتًا. يمكنك تنزيله من [هنا](https://releases.aspose.com/tasks/net/).  
2. معرفة أساسية بـ **C#** وبيئة **.NET**.  
3. بيئة تطوير مثل **Visual Studio** (الإصدار Community أو أعلى).  

## استيراد مساحات الأسماء

أولاً، استورد مساحات الأسماء التي تكشف عن API الخاص بـ Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## كيفية إدارة كائنات OLE – دليل خطوة بخطوة

أدناه نستعرض ثلاث سيناريوهات شائعة:

1. **فحص كائنات OLE** – قراءة خصائصها ومقتطف من المحتوى الثنائي.  
2. **مسح جميع كائنات OLE** – العملية الأساسية “إزالة كائنات OLE”.  
3. **قراءة معلومات موضع العرض البصري** – مفيد عندما تحتاج إلى تعديل طريقة ظهور كائنات OLE في مخطط جانت أو عروض أخرى.

### السيناريو 1: فحص كائنات OLE

#### الخطوة 1: تحميل ملف المشروع  
```csharp
var project = new Project("TaskImage2010.mpp");
```

#### الخطوة 2: الوصول إلى كائنات OLE  
```csharp
List<OleObject> oleObjects = project.OleObjects.ToList();
```

#### الخطوة 3: التكرار عبر كائنات OLE  
```csharp
foreach (var oleObject in oleObjects)
{
    // Access and print OLE object properties
    Console.WriteLine("Id: " + oleObject.Id);
    Console.WriteLine("Name: " + oleObject.Name);
    // Continue for other properties
}
```

#### الخطوة 4: استرجاع جزء صغير من المحتوى الثنائي (اختياري)  
```csharp
private string Get10Bytes(OleObject oleObject)
{
    byte[] bytes = oleObject.Content;
    var chunk = new byte[10];
    Array.Copy(bytes, chunk, 10);
    var builder = new StringBuilder();
    foreach (var b in chunk)
    {
        builder.Append(b + ", ");
    }

    builder.Remove(builder.Length - 3, 1);
    return builder.ToString();
}
```

### السيناريو 2: كيفية مسح OLE – إزالة جميع الكائنات المضمنة

#### الخطوة 1: تحميل ملف المشروع  
```csharp
var project = new Project("TaskImage2010.mpp");
```

#### الخطوة 2: مسح كائنات OLE  
```csharp
project.OleObjects.Clear();
```

#### الخطوة 3: حفظ المشروع المنقّح  
```csharp
project.Save("ClearedProject.mpp");
```

> **نصيحة احترافية:** بعد مسح كائنات OLE، يمكنك استدعاء `project.Save` باسم ملف مختلف للحفاظ على الأصل دون تعديل.

### السيناريو 3: الحصول على خصائص موضع الكائن البصري

#### الخطوة 1: تحميل ملف المشروع  
```csharp
var project = new Project("TaskImage2010.mpp");
```

#### الخطوة 2: الوصول إلى أول كائن OLE وموقعه في عرض جانت  
```csharp
var oleObject = project.OleObjects.First();
var view = project.Views.First(v => v.Name == "&Gantt Chart");
var oleObjectPlacement = view.VisualObjectsPlacements.First(p => p.OleObjectId == oleObject.Id);
```

#### الخطوة 3: استرجاع خصائص الموضع  
```csharp
Console.WriteLine("BorderLineColor: {0}", oleObjectPlacement.BorderLineColor);
Console.WriteLine("BorderLineThickness: {0}", oleObjectPlacement.BorderLineThickness);
if (oleObjectPlacement.TaskId > 0)
{
    Console.WriteLine("Attached to task: {0}", oleObjectPlacement.TaskId);
}
else
{
    Console.WriteLine("Attached to timescale date: {0}", oleObjectPlacement.TimescaleDate);
}
```

## مشكلات شائعة واستكشاف الأخطاء

| المشكلة | السبب | الحل |
|-------|--------|-----|
| `project.OleObjects` فارغ | ملف .mpp المصدر لا يحتوي على كائنات OLE. | تحقق من أن ملف المشروع فعلاً يضم بيانات OLE (مثل ورقة Excel مرفقة). |
| `project.Save` يثير استثناءً | الملف مقفل أو لا تملك صلاحيات كتابة. | أغلق أي نسخ مفتوحة من الملف وتأكد من أن المجلد الهدف قابل للكتابة. |
| بايتات المحتوى تبدو تالفة | تقوم بقراءة مصفوفة البايت الكاملة كنص. | استخدم `Get10Bytes` أو اكتب البايتات إلى ملف لتفحصها في عارض مناسب. |

## الأسئلة المتكررة

**س: هل يمكن لـ Aspose.Tasks التعامل مع صيغ OLE المختلفة؟**  
ج: نعم، يدعم الصور، مستندات Office، ملفات PDF، والعديد من صيغ OLE الأخرى.

**س: هل الـ API متوافق مع إصدارات Microsoft Project القديمة؟**  
ج: بالتأكيد – يعمل Aspose.Tasks مع ملفات Project من 2007 حتى أحدث إصدارات 2023.

**س: كيف يمكنني إزالة كائنات OLE محددة فقط بدلاً من مسح الكل؟**  
ج: حدد الـ `OleObject` المطلوب عبر `Id` أو `Name` ثم استدعِ `project.OleObjects.Remove(oleObject)` قبل الحفظ.

**س: هل مسح كائنات OLE يؤثر على تبعيات المهام أو الجداول الزمنية؟**  
ج: لا. كائنات OLE هي عناصر بصرية مستقلة؛ إزالتها لا تعدل علاقات المهام.

**س: أين يمكنني العثور على مزيد من الأمثلة حول معالجة OLE؟**  
ج: راجع الوثائق الرسمية لـ Aspose.Tasks ومرجع API لفئات `OleObject` و `VisualObjectsPlacements`.

## الخاتمة

لقد غطينا كل ما تحتاجه **لإزالة كائنات OLE** وإدارة محتوى OLE في Aspose.Tasks لـ .NET. باتباع الأمثلة خطوة بخطوة، يمكنك فحص، مسح، وتعديل موضع كائنات OLE البصري، مما يجعل ملفات المشروع أكثر خفة وتركيزًا.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**آخر تحديث:** 2026-03-16  
**تم الاختبار مع:** Aspose.Tasks 24.11 for .NET  
**المؤلف:** Aspose