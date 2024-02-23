---
title: إعدادات قاعدة البيانات في Aspose.Tasks
linktitle: إعدادات قاعدة البيانات في Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: تعرف على كيفية استيراد المشاريع من قاعدة بيانات Primavera باستخدام Aspose.Tasks لـ .NET. احصل على إرشادات خطوة بخطوة في هذا البرنامج التعليمي الشامل.
type: docs
weight: 29
url: /ar/net/calendar-scheduling/database-settings/
---
## مقدمة

Aspose.Tasks for .NET هي مكتبة قوية تسمح للمطورين بالعمل مع ملفات Microsoft Project في تطبيقات .NET الخاصة بهم. في هذا البرنامج التعليمي، سنركز على استيراد المشاريع من قاعدة بيانات Primavera باستخدام Aspose.Tasks.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من أن لديك ما يلي:

- المعرفة الأساسية بلغة البرمجة C#.
- تم تثبيت Visual Studio على نظامك.
-  تم تثبيت Aspose.Tasks لمكتبة .NET. يمكنك تنزيله من[هنا](https://releases.aspose.com/tasks/net/).
- الوصول إلى قاعدة بيانات بريمافيرا، بالإضافة إلى الأذونات اللازمة.

## استيراد مساحات الأسماء

أولاً، تحتاج إلى استيراد مساحات الأسماء الضرورية إلى مشروع C# الخاص بك. توفر مساحات الأسماء هذه إمكانية الوصول إلى الفئات والأساليب اللازمة للعمل مع Aspose.Tasks لـ .NET.

```csharp
using Aspose.Tasks;
using System;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;

```

الآن، دعونا نقسم رمز المثال المقدم إلى خطوات متعددة:

## الخطوة 1: تحديد سلسلة الاتصال

```csharp
var connectionString = "Data Source=" + DataDir + "\\PPMDBSQLite.db";
```

 في هذه الخطوة، نقوم بتحديد سلسلة الاتصال للاتصال بقاعدة بيانات بريمافيرا. تأكد من استبدال`DataDir` مع الدليل الذي يوجد به ملف قاعدة البيانات الخاصة بك.

## الخطوة 2: إنشاء إعدادات قاعدة البيانات

```csharp
var settings = new PrimaveraDbSettings(connectionString, 4502);
```

 هنا، نقوم بإنشاء مثيل`PrimaveraDbSettings` فئة، وتمرير سلسلة الاتصال ومعرف المشروع كمعلمات. اضبط معرف المشروع حسب متطلباتك.

## الخطوة 3: تعيين اسم الموفر الثابت

```csharp
settings.ProviderInvariantName = "System.Data.SQLite";
```

حدد الاسم الثابت للموفر. في هذا المثال، نستخدم SQLite، ولكن يمكنك تغييره بناءً على موفر قاعدة البيانات لديك.

## الخطوة 4: تحميل المشروع

```csharp
var project = new Project(settings);
```

 إنشاء جديد`Project` الكائن، وتمرير إعدادات قاعدة البيانات كمعلمة.

## الخطوة 5: حفظ المشروع

```csharp
project.Save(OutDir + "SupportForSQLiteDatabase_out.mpp", SaveFileFormat.Mpp);
```

وأخيرا، احفظ المشروع في الموقع المطلوب بتنسيق الملف المحدد.

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية استيراد المشاريع من قاعدة بيانات Primavera باستخدام Aspose.Tasks لـ .NET. باتباع الخطوات المتوفرة، يمكنك دمج وظيفة استيراد المشروع بسلاسة في تطبيقات .NET الخاصة بك.

## الأسئلة الشائعة

### س1: هل يمكنني استيراد مشاريع من موفري قواعد بيانات مختلفين باستخدام Aspose.Tasks لـ .NET؟

A1: نعم، يمكنك استيراد المشاريع من موفري قواعد البيانات المختلفين عن طريق ضبط سلسلة الاتصال واسم الموفر الثابت وفقًا لذلك.

### س2: هل تتوفر نسخة تجريبية مجانية من Aspose.Tasks لـ .NET؟

 ج2: نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Tasks لـ .NET من[هنا](https://releases.aspose.com/).

### س3: أين يمكنني العثور على وثائق Aspose.Tasks لـ .NET؟

 ج3: يمكنك العثور على الوثائق[هنا](https://reference.aspose.com/tasks/net/).

### س٤: كيف يمكنني الحصول على دعم Aspose.Tasks لـ .NET؟

 ج4: يمكنك الحصول على الدعم من منتدى مجتمع Aspose.Tasks[هنا](https://forum.aspose.com/c/tasks/15).

### س5: هل أحتاج إلى ترخيص مؤقت لاستخدام Aspose.Tasks لـ .NET؟

 ج5: إذا كنت تريد تقييم الأداء الوظيفي الكامل للمكتبة، فيمكنك الحصول على ترخيص مؤقت من[هنا](https://purchase.aspose.com/temporary-license/).