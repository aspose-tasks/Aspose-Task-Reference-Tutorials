---
date: 2026-04-09
description: تعلم كيفية فحص الدائرة والتحقق من سلامة ملفات Microsoft Project باستخدام
  Aspose.Tasks لـ .NET.
keywords:
- how to check circuit
- check project structure
- validate microsoft project
- project file integrity check
linktitle: تحقق من الدائرة في Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: كيفية فحص الدائرة في Aspose.Tasks
url: /ar/net/calendar-scheduling/check-circuit/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية فحص الدائرة في Aspose.Tasks

## مقدمة

في عالم تطوير .NET، إدارة المهام والمشروعات بفعالية أمر أساسي. **How to check circuit** في ملف المشروع هو مطلب شائع عندما تحتاج إلى ضمان سلامة جدول Microsoft Project. توفر Aspose.Tasks for .NET واجهة برمجة تطبيقات بسيطة تتيح لك التحقق من بنية المشروع واكتشاف التسلسلات الهرمية المكسورة ببضع أسطر من الشيفرة.

## إجابات سريعة
- **ما الذي يفعله “check circuit”؟** يقوم بمسح التسلسل الهرمي للمهام للبحث عن مراجع دائرية أو روابط أب‑ابن مكسورة.  
- **لماذا هو مهم؟** يساعد في الحفاظ على ملف مشروع نظيف ويمنع أخطاء الحساب في Microsoft Project.  
- **أي مكتبة تُستخدم؟** Aspose.Tasks for .NET.  
- **هل أحتاج إلى ترخيص؟** يلزم الحصول على ترخيص مؤقت للإنتاج؛ نسخة تجريبية مجانية تكفي للاختبار.  
- **المنصات المدعومة؟** .NET Framework، .NET Core، و .NET 5/6+.

## ما هو فحص دائرة المشروع؟

فحص الدائرة (يُسمى أحيانًا “التحقق من البنية”) يتنقل عبر كل مهمة بدءًا من المهمة الجذرية ويتأكد من أن كل مهمة فرعية تشير إلى أب صالح. إذا تم العثور على حلقة أو مهمة يتيمة، تقوم المكتبة بإلقاء استثناء `TasksException`، مما يتيح لك معالجة المشكلة برمجيًا.

## لماذا التحقق من صحة ملفات Microsoft Project؟

- **منع أخطاء الحساب:** المراجع الدائرية يمكن أن تفسد حسابات الجدول.  
- **الحفاظ على سلامة البيانات:** يضمن أن كل مهمة تنتمي إلى تسلسل هرمي صحيح.  
- **أتمتة فحوص الجودة:** مفيد في خطوط CI حيث تُنشأ ملفات المشروع أو تُعدل تلقائيًا.  
- **توفير الوقت:** اكتشاف المشكلات مبكرًا بدلاً من تصحيح جدول مكسور في Microsoft Project.

## المتطلبات المسبقة

قبل الغوص في الشرح، تأكد من توفر المتطلبات التالية:

1. Visual Studio: تأكد من تثبيت Visual Studio على نظامك.  
2. Aspose.Tasks for .NET: قم بتحميل وتثبيت مكتبة Aspose.Tasks for .NET من [here](https://releases.aspose.com/tasks/net/).  
3. معرفة أساسية بـ C#: الإلمام بلغة البرمجة C# ضروري لمتابعة الأمثلة.

## استيراد مساحات الأسماء

في مشروع C# الخاص بك، أدرج مساحات الأسماء التالية للوصول إلى الفئات والطرق المطلوبة:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;
```

## الخطوة 1: تحميل ملف المشروع

ابدأ بتحميل ملف Microsoft Project (.mpp) الذي تريد فحصه للتأكد من عدم وجود بنية مكسورة. استخدم الفئة `Project` لتحميل الملف.

```csharp
var project = new Project(DataDir + "ParentChildTasks.mpp");
```

## الخطوة 2: فحص بنية المشروع

لكشف أي بنية مكسورة داخل المشروع، سنستخدم الفئة `CheckCircuit` مع طريقة `TaskUtils.Apply`. هذه الخطوة **تتحقق من بنية المشروع** وسترفع استثناء إذا تم العثور على دائرة.

```csharp
try
{
    TaskUtils.Apply(project.RootTask, new CheckCircuit(), 0);
}
catch (TasksException ex)
{
    Console.WriteLine(ex);
}
```

## الأخطاء الشائعة والنصائح

- **خطأ:** نسيان تغليف الاستدعاء داخل `try/catch`. عملية `CheckCircuit` تُطلق استثناء `TasksException` عند اكتشاف مشكلة، لذا يجب دائمًا معالجتها بلطف.  
- **نصيحة:** استخدم `project.RootTask` كنقطة الدخول؛ تمرير أي مهمة أخرى قد يتسبب في فقدان المشكلات العليا.  
- **نصيحة:** بعد إصلاح الدائرة، يمكنك إعادة تشغيل الفحص لتأكيد سلامة ملف المشروع.

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Tasks for .NET مع أطر .NET أخرى؟**  
ج: نعم، Aspose.Tasks for .NET متوافق مع أطر .NET المختلفة، بما في ذلك .NET Core و .NET Framework.

**س: هل هناك نسخة تجريبية متاحة قبل الشراء؟**  
ج: نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Tasks for .NET من [here](https://releases.aspose.com/).

**س: كيف يمكنني الحصول على دعم لـ Aspose.Tasks for .NET؟**  
ج: يمكنك طلب المساعدة من منتدى مجتمع Aspose.Tasks عبر [here](https://forum.aspose.com/c/tasks/15).

**س: هل أحتاج إلى ترخيص مؤقت لأغراض الاختبار؟**  
ج: نعم، يمكنك الحصول على ترخيص مؤقت من [here](https://purchase.aspose.com/temporary-license/) للاختبار.

**س: أين يمكنني شراء Aspose.Tasks for .NET؟**  
ج: يمكنك شراء النسخة الكاملة من Aspose.Tasks for .NET عبر [here](https://purchase.aspose.com/buy).

## الخلاصة

باتباعك لهذا الدليل، تعلمت **كيفية فحص الدائرة** في مشروع Aspose.Tasks، مما يضمن صحة ملف المشروع والحفاظ على تسلسل هرمي نظيف للمهام. دمج هذا الفحص في عملية البناء أو الاستيراد يمكن أن يوفر ساعات من التصحيح اليدوي ويحافظ على موثوقية جداولك.

---

**آخر تحديث:** 2026-04-09  
**تم الاختبار مع:** Aspose.Tasks for .NET (latest version)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}