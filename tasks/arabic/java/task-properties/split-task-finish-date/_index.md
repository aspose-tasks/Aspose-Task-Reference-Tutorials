---
title: تقسيم تاريخ انتهاء المهمة في Aspose.Tasks
linktitle: تقسيم تاريخ انتهاء المهمة في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية تقسيم تواريخ انتهاء المهمة بسهولة باستخدام Aspose.Tasks لـ Java. تعزيز إدارة المشروع بجداول زمنية دقيقة.
weight: 28
url: /ar/java/task-properties/split-task-finish-date/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تقسيم تاريخ انتهاء المهمة في Aspose.Tasks

## مقدمة
في إدارة المشاريع، يعد فهم الجداول الزمنية للمهام أمرًا بالغ الأهمية لإنجاز المشروع بنجاح. يوفر Aspose.Tasks for Java ميزات قوية للتعامل مع مهام المشروع بكفاءة. في هذا البرنامج التعليمي، سنتعمق في تقسيم تواريخ انتهاء المهام باستخدام Aspose.Tasks، مما يساعدك على إدارة الجداول الزمنية للمشروع بفعالية.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
- المعرفة الأساسية ببرمجة جافا.
-  تم تثبيت Aspose.Tasks لمكتبة Java. يمكنك تنزيله[هنا](https://releases.aspose.com/tasks/java/).
- تم إعداد بيئة تطوير Java.
## حزم الاستيراد
ابدأ بتضمين الحزم الضرورية في مشروع Java الخاص بك:
```java
import com.aspose.tasks.*;
```
## الخطوة 1: ابحث عن مهمة مقسمة
حدد المهمة التي تريد تقسيمها داخل المشروع:
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// قراءة المشروع
String projectName = dataDir + "SplitTask.mpp";
Project project = new Project(projectName);
Task splitTask = project.getRootTask().getChildren().getByUid(1);
```
## الخطوة 2: ابحث عن تقويم المشروع
استرجع تقويم المشروع لإجراء حسابات دقيقة للتاريخ:
```java
Calendar calendar = project.get(Prj.CALENDAR);
```
## الخطوة 3: حساب تاريخ انتهاء المهمة بمدد مختلفة
الآن، قم بحساب تاريخ انتهاء المهمة لفترات مختلفة:
## الخطوة 3.1: مدة 8 ساعات
```java
System.out.println("Start Date: " + splitTask.get(Tsk.START) + "\n+ Duration 8 hours\nFinish Date: " + calendar.getTaskFinishDateFromDuration(splitTask, 8d));
```
كرر الكود أعلاه لفترات مختلفة، واضبط الساعات وفقًا لذلك.
## خاتمة
يعد إتقان فن التعامل مع تواريخ انتهاء المهام أمرًا محوريًا لإدارة المشاريع بشكل فعال. يعمل Aspose.Tasks for Java على تبسيط هذه العملية، مما يسمح لك بتبسيط الجداول الزمنية لمشروعك دون عناء.
## الأسئلة الشائعة
### س1: كيف يمكنني تنزيل Aspose.Tasks لـ Java؟
 ج1: يمكنك تنزيله[هنا](https://releases.aspose.com/tasks/java/).
### س2: أين يمكنني العثور على وثائق Aspose.Tasks؟
 ج2: راجع الوثائق[هنا](https://reference.aspose.com/tasks/java/).
### س3: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Tasks؟
 ج3: الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).
### س4: أين يمكنني طلب الدعم لـ Aspose.Tasks؟
 ج4: قم بزيارة منتدى الدعم[هنا](https://forum.aspose.com/c/tasks/15).
### س5: هل يمكنني شراء Aspose.Tasks؟
 ج5: نعم، يمكنك شرائه[هنا](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
