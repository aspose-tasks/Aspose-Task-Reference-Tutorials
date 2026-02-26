---
date: 2026-02-26
description: تعلم كيفية حفظ المشروع كملف PDF وتوليد ورقة المهام باستخدام Aspose.Tasks
  للغة Java. صدّر ملف MPP إلى PDF بسرعة مع هذا الدليل خطوة بخطوة.
linktitle: Render Task Sheet in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: حفظ المشروع كملف PDF – إنشاء ورقة المهام باستخدام Aspose.Tasks للغة Java
url: /ar/java/task-properties/render-task-sheet/
weight: 27
---

 not to translate URLs inside markdown links.

Also code block placeholders remain.

Let's produce final content.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# حفظ المشروع كملف PDF – إنشاء ورقة مهام في Aspose.Tasks

## المقدمة
في هذا الدليل الشامل ستكتشف كيفية **حفظ المشروع كملف PDF** وإنشاء ورقة مهام باستخدام Aspose.Tasks for Java. سواءً كنت بحاجة لتصدير ملف MPP إلى PDF لمراجعات أصحاب المصلحة أو ببساطة تريد إنشاء ورقة مهام نظيفة للتقارير، فإن هذا البرنامج التعليمي يمرّ بك عبر كل خطوة، يوضح لماذا كل إعداد مهم، ويظهر لك الشيفرة الدقيقة التي تحتاج لتشغيلها.

## إجابات سريعة
- **ماذا يفعل “حفظ المشروع كملف pdf”؟** يقوم بتحويل ملف Microsoft Project (MPP) إلى مستند PDF، مع إمكانية تنسيقه كورقة مهام.  
- **ما هو التنسيق المستخدم لورقة‑مهام PDF؟** الخيار `PresentationFormat.TaskSheet` في `PdfSaveOptions`.  
- **هل أحتاج إلى ترخيص لتشغيل الشيفرة؟** يلزم ترخيص مؤقت أو كامل للإنتاج؛ نسخة تجريبية مجانية تكفي للتقييم.  
- **ما هي المتطلبات الأساسية؟** Java JDK، مكتبة Aspose.Tasks for Java، وملف مشروع صالح (مثل *.mpp).  
- **هل يمكنني تخصيص تخطيط PDF؟** نعم، توفر Aspose.Tasks العديد من خصائص `PdfSaveOptions` للتنسيق وإعداد الصفحات.

## ما هو “حفظ المشروع كملف pdf”؟
حفظ المشروع كملف PDF يحول بيانات المشروع الداخلية إلى مستند محمول للقراءة فقط. هذا مثالي لمشاركة الجداول الزمنية، أوراق المهام، أو تقارير الحالة مع أصحاب المصلحة الذين لا يمتلكون Microsoft Project مثبتًا.

## لماذا نقوم بإنشاء ورقة مهام؟
تقدم ورقة المهام كل مهمة في عرض جدولي، تُظهر المعرفات، الأسماء، تواريخ البدء/الانتهاء، وغيرها من الحقول. تحويلها إلى PDF يضمن تنسيقًا ثابتًا عبر الأنظمة ويسهل طباعتها أو دمجها في مستندات أخرى.

## المتطلبات المسبقة
قبل أن تبدأ، تأكد من وجود ما يلي:

1. **Java Development Kit (JDK)** – أحدث نسخة مثبتة ومتاحة عبر `java`/`javac` في PATH.  
2. **Aspose.Tasks for Java** – حمّل المكتبة من الموقع الرسمي [هنا](https://releases.aspose.com/tasks/java/).  
3. ملف **مشروع** صالح (`*.mpp`) تريد تحويله، مثال: `NewProductDev.mpp`.  

## استيراد الحزم
أولاً، استورد الفئات المطلوبة من Aspose.Tasks. هذه الاستيرادات تمنحك الوصول إلى خيارات حفظ PDF، صيغ العرض، وكائن `Project` الأساسي.

```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
```

## دليل خطوة بخطوة

### الخطوة 1: تعيين دليل المستندات
حدد المجلد الذي يتواجد فيه ملف MPP المصدر والمجلد الذي سيُكتب فيه ملف PDF الناتج. يمكن استخدام مسار مطلق أو نسبي؛ فقط تأكد من وجود المجلد.

```java
String dataDir = "Your Document Directory";
```

### الخطوة 2: تحميل ملف المشروع
أنشئ كائن `Project` بتحميل ملف MPP الموجود. يمثل هذا الكائن هيكل المشروع بالكامل في الذاكرة.

```java
Project project = new Project(dataDir + "NewProductDev.mpp");
```

### الخطوة 3: تكوين خيارات الحفظ – تصدير MPP إلى PDF
أنشئ كائن `PdfSaveOptions` وأخبر Aspose.Tasks أنك تريد أن يتم تصدير PDF كـ **ورقة مهام**. هذه هي الخطوة الأساسية لحالة الاستخدام *export project pdf*.

```java
SaveOptions options = new PdfSaveOptions();
options.setPresentationFormat(PresentationFormat.TaskSheet);
```

### الخطوة 4: حفظ المشروع كورقة مهام – حفظ المشروع كملف PDF
استدعِ طريقة `save` على كائن `Project`، مع تمرير اسم الملف الهدف والخيارات التي تم تكوينها. هذا الإجراء **يحول ملف MPP إلى PDF** مُنسق كورقة مهام.

```java
project.save(dataDir + "taskSheet.pdf", options);
```

### الخطوة 5: مراجعة النتيجة
انتقل إلى الدليل الذي حددته (`dataDir`). يجب أن ترى الملف `taskSheet.pdf` يحتوي على قائمة منسقة بشكل أنيق لجميع المهام. افتحه بأي عارض PDF للتحقق من نجاح التحويل.

## المشكلات الشائعة والحلول
- **FileNotFoundException** – تأكد من أن `dataDir` ينتهي بفاصل مسار (`/` أو `\\`) وأن اسم ملف MPP صحيح.  
- **LicenseException** – إذا ظهرت أخطاء الترخيص، قم بتطبيق ترخيص مؤقت أو مُشتَر قبل استدعاء أي API من Aspose.Tasks.  
- **PDF فارغ** – تحقق من أن المشروع يحتوي فعليًا على مهام؛ مشروع فارغ سينتج PDF فارغ.

## الأسئلة المتكررة

**س: هل Aspose.Tasks متوافق مع جميع إصدارات Java؟**  
ج: نعم، يعمل Aspose.Tasks مع مجموعة واسعة من إصدارات Java. راجع [الوثائق](https://reference.aspose.com/tasks/java/) للمزيد من التفاصيل.

**س: هل يمكن تجربة Aspose.Tasks قبل الشراء؟**  
ج: بالتأكيد! استكشف النسخة التجريبية المجانية [هنا](https://releases.aspose.com/).

**س: أين يمكن العثور على دعم Aspose.Tasks؟**  
ج: انضم إلى مجتمع Aspose.Tasks على [المنتدى](https://forum.aspose.com/c/tasks/15) للحصول على الدعم والنقاشات.

**س: كيف أحصل على ترخيص مؤقت لـ Aspose.Tasks؟**  
ج: احصل على ترخيصك المؤقت [هنا](https://purchase.aspose.com/temporary-license/).

**س: أين يمكنني شراء Aspose.Tasks for Java؟**  
ج: اشترِ Aspose.Tasks for Java [هنا](https://purchase.aspose.com/buy).

## الخاتمة
باتباعك لهذه الخطوات تكون قد تعلمت كيفية **حفظ المشروع كملف PDF**، وتحديدًا إنشاء ورقة مهام، باستخدام Aspose.Tasks for Java. تتيح لك هذه القدرة *تصدير MPP إلى PDF* بسرعة، مشاركة لقطات مشروع قابلة للقراءة، ودمج بيانات المشروع في سير عمل تقارير أوسع.

---

**آخر تحديث:** 2026-02-26  
**تم الاختبار مع:** Aspose.Tasks for Java 24.11  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}