---
date: 2026-03-14
description: تعلم كيفية تحديد مخطط قاعدة البيانات لقاعدة بيانات Microsoft Project
  باستخدام Aspose.Tasks، وكيفية استيراد بيانات المشروع إلى تطبيقات .NET.
linktitle: Specify database schema for Project DB with Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: حدد مخطط قاعدة البيانات لقاعدة بيانات المشروع باستخدام Aspose.Tasks
url: /ar/net/advanced-concepts/msp-database-settings/
weight: 19
---

 content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إعدادات قاعدة بيانات Microsoft Project في Aspose.Tasks

## المقدمة

إذا كنت تعمل مع قواعد بيانات Microsoft Project في تطبيقات .NET الخاصة بك باستخدام Aspose.Tasks، فستحتاج إلى **تحديد مخطط قاعدة البيانات** وتكوين الإعدادات اللازمة **لإستيراد بيانات المشروع** بسلاسة. سيوجهك هذا البرنامج التعليمي خلال العملية خطوة بخطوة، موضحًا **كيفية تكوين تفاصيل الاتصال**، **إنشاء سلسلة اتصال .NET**، وأخيرًا **حفظ المشروع كملف MPP**.

## إجابات سريعة
- **ما هو الهدف الأساسي؟** تحديد مخطط قاعدة البيانات واستيراد قاعدة بيانات Project إلى تطبيق .NET.  
- **ما المكتبة المطلوبة؟** Aspose.Tasks لـ .NET.  
- **كيف يمكنني الاتصال بـ Project Server؟** عن طريق إنشاء سلسلة اتصال SQL صحيحة واستخدام `MspDbSettings`.  
- **ما هو تنسيق الملف الناتج؟** ملف MPP يتم حفظه باستخدام `SaveFileFormat.Mpp`.  
- **هل يمكنني تغيير اسم المخطط؟** نعم، قم بتعيين الخاصية `Schema` في `MspDbSettings`.

## كيفية تحديد مخطط قاعدة البيانات لـ Project DB

فهم سبب الحاجة إلى **تحديد مخطط قاعدة البيانات** أمر أساسي. في العديد من بيئات المؤسسات، قاعدة بيانات Project Server توجد تحت مخطط مخصص (مثل `dbo`، `psdata`). من خلال تعيين المخطط صراحةً، تضمن أن Aspose.Tasks يستعلم عن الجداول الصحيحة، مما يمنع الأخطاء أثناء التشغيل ويضمن استيراد بيانات دقيق.

## المتطلبات المسبقة

قبل البدء، تأكد من وجود ما يلي:

1. Aspose.Tasks لـ .NET: قم بتنزيل وتثبيت مكتبة Aspose.Tasks من [هنا](https://releases.aspose.com/tasks/net/).  
2. الوصول إلى قاعدة بيانات Microsoft Project: يجب أن يكون لديك إمكانية الوصول إلى قاعدة بيانات Microsoft Project لاستيراد البيانات منها.  

## استيراد مساحات الأسماء

أولاً، تأكد من استيراد مساحات الأسماء الضرورية إلى مشروعك:

```csharp
using Aspose.Tasks;
using System;
using System.Data.SqlClient;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
```

## الخطوة 1: إنشاء سلسلة الاتصال

قم بإنشاء سلسلة الاتصال بقاعدة بيانات Microsoft Project الخاصة بك. هنا تقوم **بإنشاء سلسلة اتصال .NET** وتحدد أيضًا **كيفية الاتصال بـ Project Server**.

```csharp
var connectionString = new SqlConnectionStringBuilder();
connectionString.DataSource = "192.168.56.2,1433";
connectionString.Encrypt = true;
connectionString.TrustServerCertificate = true;
connectionString.InitialCatalog = "ProjectServer_Published";
connectionString.NetworkLibrary = "DBMSSOCN";
connectionString.UserID = "sa";
connectionString.Password = "*";
connectionString.ConnectTimeout = 2;
```

> **نصيحة احترافية:** تحقق مرة أخرى من قيم `DataSource` و `InitialCatalog`؛ يجب أن تتطابق مع عنوان الخادم الخاص بك واسم قاعدة البيانات المنشورة.

## الخطوة 2: تكوين MspDbSettings

أنشئ مثيلًا من `MspDbSettings`، مرّر سلسلة الاتصال، و**حدد مخطط قاعدة البيانات** عن طريق تعيين الخاصية `Schema`. هذا يخبر Aspose.Tasks أي مخطط يجب الاستعلام منه.

```csharp
var settings = new MspDbSettings(connectionString.ConnectionString, new Guid("E6426C44-D6CB-4B9C-AF16-48910ACE0F54"));
settings.Schema = "dbo";
```

هنا نوفر أيضًا معرف GUID للمشروع الذي يحدد المشروع المحدد الذي تريد تحميله.

## الخطوة 3: تحميل بيانات المشروع

أنشئ كائنًا من نوع `Project` باستخدام الإعدادات المكوّنة. هذه الخطوة تقوم فعليًا **بإستيراد بيانات المشروع** من قاعدة البيانات إلى كائن .NET.

```csharp
var project = new Project(settings);
```

## الخطوة 4: حفظ بيانات المشروع

أخيرًا، احفظ المشروع المحمّل كملف MPP على القرص. هذا يوضح **حفظ المشروع كملف MPP** باستخدام واجهة برمجة تطبيقات Aspose.Tasks.

```csharp
project.Save(OutDir + "ImportProjectDataFromDatabase_out.mpp", SaveFileFormat.Mpp);
```

بعد تشغيل الكود، ستجد ملف `ImportProjectDataFromDatabase_out.mpp` في دليل الإخراج، جاهزًا للفتح في Microsoft Project.

## الخلاصة

في هذا البرنامج التعليمي، تعلمت كيفية **تحديد مخطط قاعدة البيانات** لقاعدة بيانات Microsoft Project، **تكوين الاتصال**، **استيراد بيانات المشروع**، و**حفظ المشروع كملف MPP** باستخدام Aspose.Tasks لـ .NET. تتيح هذه الخطوات دمج بيانات Project Server بسلاسة في تطبيقاتك المخصصة، مما يساعدك على بناء حلول إدارة مشاريع قوية.

## الأسئلة المتكررة

### س1: هل يمكنني استخدام Aspose.Tasks مع إصدارات مختلفة من قواعد بيانات Microsoft Project؟
A1: نعم، يدعم Aspose.Tasks إصدارات مختلفة من قواعد بيانات Microsoft Project، مما يوفر مرونة في التكامل.

### س2: كيف يمكنني استكشاف مشكلات الاتصال بقاعدة البيانات؟
A2: تأكد من أن سلسلة الاتصال مُكوّنة بشكل صحيح مع الاعتمادات وتفاصيل قاعدة البيانات المناسبة. يمكنك أيضًا الرجوع إلى الوثائق أو طلب الدعم من [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### س3: هل هناك نسخة تجريبية متاحة لـ Aspose.Tasks؟
A3: نعم، يمكنك الحصول على نسخة تجريبية مجانية من [هنا](https://releases.aspose.com/).

### س4: هل يمكنني تخصيص المخطط لتفاعل قاعدة البيانات؟
A4: نعم، يمكنك تحديد المخطط لكائن `MspDbSettings` وفقًا لبنية قاعدة البيانات الخاصة بك.

### س5: أين يمكنني العثور على وثائق أكثر تفصيلاً حول استخدام Aspose.Tasks؟
A5: يمكنك استكشاف الوثائق الشاملة [هنا](https://reference.aspose.com/tasks/net/) للحصول على رؤى مفصلة حول وظائف Aspose.Tasks.

**س: هل يعمل هذا النهج مع قواعد بيانات Azure SQL؟**  
A: بالتأكيد. فقط قم بتعديل `DataSource` إلى اسم خادم Azure الخاص بك وتأكد من تمكين إعدادات TLS/SSL.

**س: كيف أتعامل مع قواعد بيانات Project الكبيرة دون انقضاء المهلة؟**  
A: قم بزيادة قيمة `ConnectTimeout` في سلسلة الاتصال وفكّر في تحميل المشاريع على دفعات إذا لزم الأمر.

---

**آخر تحديث:** 2026-03-14  
**تم الاختبار مع:** Aspose.Tasks 24.12 لـ .NET  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}