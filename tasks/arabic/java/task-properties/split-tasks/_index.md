---
date: 2026-02-26
description: تعلم كيفية تقسيم المهام باستخدام Aspose.Tasks للـ Java – الدليل الشامل
  حول كيفية تقسيم المهام، وتعيين تقويم المشروع، وإنشاء تخصيص الموارد.
linktitle: Split Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: كيفية تقسيم المهام في Aspose.Tasks
url: /ar/java/task-properties/split-tasks/
weight: 29
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تقسيم المهام في Aspose.Tasks

## المقدمة
إذا كنت تبحث عن **كيفية تقسيم المهام** في مشروع يعتمد على Java، فقد وصلت إلى المكان الصحيح. توفر لك Aspose.Tasks for Java طريقة برمجية نظيفة لتقسيم مهمة طويلة إلى أجزاء أصغر يمكن التحكم فيها، مما يساعد على موازنة الموارد، وإعداد تقارير دقيقة، وتحسين جداول المشروع. في هذا الدليل سنستعرض العملية بالكامل — من إعداد تقويم المشروع إلى إنشاء تعيين مورد وأخيرًا تقسيم المهمة إلى عدة أقسام.

## إجابات سريعة
- **ما هو تقسيم المهام؟** تقسيم مهمة واحدة إلى عدة فترات أصغر مع الحفاظ على إجمالي مدتها.  
- **لماذا نقوم بتقسيم المهام في Java؟** يتيح تخصيص موارد دقيق وتتبع تقدم أفضل.  
- **أي مكتبة تساعد في ذلك؟** توفر Aspose.Tasks for Java طرقًا مدمجة للتقسيم والتوقيت المرحلي.  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تكفي للتطوير؛ الترخيص مطلوب للإنتاج.  
- **ما نسخة Java المدعومة؟** تعمل المكتبة مع Java 8 وأحدث.

## المتطلبات المسبقة
قبل الغوص في الدليل، تأكد من توفر المتطلبات التالية:
- مجموعة تطوير Java (JDK) مثبتة على جهازك.  
- مكتبة Aspose.Tasks for Java تم تنزيلها وإضافتها إلى مشروعك. يمكنك تنزيلها من [توثيق Aspose.Tasks for Java](https://reference.aspose.com/tasks/java/).

## استيراد الحزم
ابدأ باستيراد الحزم اللازمة إلى مشروع Java الخاص بك:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
```

## الخطوة 1: إنشاء مشروع جديد
ابدأ بإنشاء مشروع جديد باستخدام مكتبة Aspose.Tasks:

```java
// Create a new project
Project splitTaskProject = new Project();
```

## الخطوة 2: ضبط تقويم المشروع
ضبط **تقويم المشروع** يحدد أيام العمل، والعطلات، والجدول الزمني العام لخطتك. هذه الخطوة أساسية لحسابات التوقيت المرحلي الدقيقة.

```java
// Get a standard calendar
Calendar calendar = splitTaskProject.get(Prj.CALENDAR);
// Set project's calendar settings
java.util.Calendar cal = java.util.Calendar.getInstance();
// ... (continue with the example)
```

## الخطوة 3: إضافة مهمة جذر
كل مشروع يحتاج إلى حاوية جذر. إضافة مهمة جذر تمنحك مكانًا لإرفاق جميع المهام اللاحقة.

```java
// Root task
Task rootTask = splitTaskProject.getRootTask();
rootTask.set(Tsk.NAME, "Root");
```

## الخطوة 4: إضافة مهمة جديدة للتقسيم
أنشئ المهمة التي تريد تقسيمها. هنا نحدد مدة ثلاثة أيام كمثال.

```java
// Add a new task
Task taskToSplit = rootTask.getChildren().add("Task1");
taskToSplit.set(Tsk.DURATION, splitTaskProject.getDuration(3));
```

## الخطوة 5: إنشاء تعيين مورد
**تعيين المورد** يربط موردًا (أو عنصرًا نائبًا) بالمهمة. هذا مطلوب قبل إنشاء بيانات التوقيت المرحلي.

```java
// Create a new resource assignment
ResourceAssignment splitResourceAssignment = splitTaskProject.getResourceAssignments().add(taskToSplit, null);
```

## الخطوة 6: توليد بيانات التوقيت المرحلي
تمثل بيانات التوقيت المرحلي كيفية توزيع العمل على مدة المهمة. توليدها يجهز المهمة للتقسيم.

```java
// Generate resource assignment timephased data
splitResourceAssignment.timephasedDataFromTaskDuration(calendar);
```

## الخطوة 7: تقسيم المهمة
الآن نقوم **بتقسيم المهمة إلى أجزاء**. في هذا المثال نقسم المهمة ذات الثلاثة أيام إلى ثلاثة أقسام يومية.

```java
// Split the task into 3 parts
java.util.Calendar cal = java.util.Calendar.getInstance();
java.util.Calendar cal2 = java.util.Calendar.getInstance();
// ... (continue with the example)
```

## لماذا نقسم المهام؟
يمنحك تقسيم المهام تحكمًا أدق في:
- **موازنة الموارد:** تعيين موارد مختلفة لكل جزء.  
- **تتبع التقدم:** تحديث الحالة على أساس كل جزء.  
- **التقارير:** إنشاء مخططات جانت وتقارير أكثر تفصيلًا.

## المشكلات الشائعة والحلول
- **فقدان بيانات التقويم:** تأكد من استدعاء `timephasedDataFromTaskDuration` قبل التقسيم.  
- **أقسام ذات مدة صفرية:** تحقق من أن كل فترة مقسمة لها مدة غير صفرية؛ وإلا سيتجاهلها المكتبة.  
- **استثناءات الترخيص:** التشغيل بدون ترخيص صالح قد يضيف علامة مائية إلى الملفات المصدرة.

## الأسئلة المتكررة
### هل يمكنني تقسيم المهام بمدد مختلفة؟
نعم، يمكنك تعديل مدة كل جزء لتتناسب مع متطلبات مشروعك.

### هل Aspose.Tasks for Java متوافق مع جميع إصدارات Java؟
تم تصميم Aspose.Tasks for Java للعمل بسلاسة مع Java 8 وأحدث، مما يضمن توافقًا واسعًا.

### هل يمكنني استخدام Aspose.Tasks for Java مجانًا؟
توفر Aspose.Tasks for Java نسخة تجريبية مجانية، تسمح لك باستكشاف ميزاتها قبل الشراء.

### كيف يمكنني الحصول على دعم لـ Aspose.Tasks for Java؟
قم بزيارة [منتدى دعم Aspose.Tasks for Java](https://forum.aspose.com/c/tasks/15) للحصول على المساعدة والتواصل مع المجتمع.

### هل أحتاج إلى ترخيص مؤقت لـ Aspose.Tasks for Java؟
يمكنك الحصول على ترخيص مؤقت من [هذا الرابط](https://purchase.aspose.com/temporary-license/) لأغراض الاختبار والتقييم.

---

**آخر تحديث:** 2026-02-26  
**تم الاختبار مع:** Aspose.Tasks for Java 24.11  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}