---
title: قم بإنشاء رابط مهام عبر المشروعات في Aspose.Tasks
linktitle: قم بإنشاء رابط مهام عبر المشروعات في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعزيز التعاون في المشروع باستخدام Aspose.Tasks لـ Java. تعلم كيفية إنشاء روابط المهام عبر المشروعات خطوة بخطوة. تعزيز الكفاءة الآن!
weight: 10
url: /ar/java/task-links/create-cross-project-task-link/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# قم بإنشاء رابط مهام عبر المشروعات في Aspose.Tasks

## مقدمة
في عالم إدارة المشاريع الديناميكي، تعد الكفاءة والتعاون أمرًا بالغ الأهمية. يوفر Aspose.Tasks for Java حلاً قويًا لتعزيز قدرات إدارة مشروعك. في هذا البرنامج التعليمي، سوف نتعمق في عملية إنشاء روابط المهام عبر المشروعات باستخدام Aspose.Tasks لـ Java. سيزودك هذا الدليل التفصيلي بالمهارات اللازمة لربط المهام بسلاسة عبر المشاريع المختلفة، مما يعزز التنسيق المحسن وسير العمل المبسط.
## المتطلبات الأساسية
قبل الشروع في هذا البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
- معرفة عملية ببرمجة جافا.
-  تم تثبيت Aspose.Tasks لـ Java. يمكنك تنزيله من[Aspose.Tasks لصفحة إصدار Java](https://releases.aspose.com/tasks/java/).
- الفهم الأساسي لإدارة المشروع وتبعيات المهام.
## حزم الاستيراد
لبدء العملية، فلنستورد الحزم الضرورية في بيئة Java لديك. وهذا يضمن أن لديك إمكانية الوصول إلى وظائف Aspose.Tasks الخاصة بـ Java. استخدم مقتطف الكود التالي:
```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.Tsk;
```
الآن، دعونا نقسم الكود أعلاه إلى خطوات مفهومة:
## الخطوة 1: إعداد بيئتك
قبل الغوص في التعليمات البرمجية، تأكد من تثبيت Java، ومن إضافة مكتبة Aspose.Tasks for Java بشكل صحيح إلى مشروعك.
## الخطوة 2: إنشاء مثيل المشروع
تهيئة مشروع جديد باستخدام مكتبة Aspose.Tasks:
```java
Project project = new Project();
```
## الخطوة 3: إضافة مهمة ملخصة
قم بإنشاء مهمة موجزة لتنظيم المهام المرتبطة وإدارتها:
```java
Task summary = project.getRootTask().getChildren().add("Summary Task");
```
## الخطوة 4: إضافة مهمة خارجية
لإنشاء ارتباط لمهمة من مشروع آخر، قم بإضافة مهمة خارجية إلى المهمة الموجزة:
```java
Task t2 = summary.getChildren().add("External Task");
t2.set(Tsk.EXTERNAL_TASK_PROJECT, "ExternalProject.mpp");
t2.set(Tsk.EXTERNAL_ID, 1);
t2.set(Tsk.IS_EXTERNAL_TASK, true);
t2.set(Tsk.IS_MANUAL, new NullableBool(false));
t2.set(Tsk.IS_SUMMARY, false);
```
## الخطوة 5: إضافة مهمة محلية
إضافة مهمة محلية إلى المهمة الموجزة. ستكون هذه المهمة مرتبطة بالمهمة الخارجية:
```java
Task t = summary.getChildren().add("Task");
```
## الخطوة 6: إنشاء رابط المهمة
إنشاء رابط المهمة بين المهمة الخارجية والمهمة المحلية:
```java
TaskLink link = project.getTaskLinks().add(t2, t);
link.setCrossProject(true);
link.setLinkType(TaskLinkType.FinishToStart);
link.setCrossProjectName("ExternalProject.mpp\\1");
```
## الخطوة 7: عرض النتائج
وأخيراً عرض نتيجة التحويل:
```java
System.out.println("Process completed Successfully");
```
## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية إنشاء روابط مهام عبر المشروعات باستخدام Aspose.Tasks لـ Java. تعمل هذه الوظيفة على تعزيز التعاون والتنسيق في إدارة المشاريع، مما يضمن التكامل السلس بين المهام في المشاريع المختلفة.
## الأسئلة الشائعة
### هل يمكنني ربط المهام من مشاريع خارجية متعددة في نفس المهمة الموجزة؟
نعم، يمكنك ربط المهام من مشاريع خارجية مختلفة ضمن نفس المهمة الموجزة، باتباع عملية مماثلة.
### ماذا يحدث إذا تم تعديل المهمة الخارجية في المشروع المرتبط؟
سوف تنعكس أي تعديلات على المهمة الخارجية في المهمة المرتبطة في مشروعك الحالي.
### هل من الممكن إنشاء روابط بين المهام بتنسيقات ملفات مختلفة؟
نعم، يدعم Aspose.Tasks for Java ربط المهام بين المشاريع بتنسيقات ملفات مختلفة.
### هل يمكنني إلغاء ربط المهام بمجرد ربطها عبر المشاريع؟
نعم، يمكنك إلغاء ربط المهام عن طريق إزالة رابط المهمة باستخدام طرق Aspose.Tasks المناسبة.
### هل هناك أي قيود على عدد المهام التي يمكن ربطها عبر المشاريع؟
يخضع عدد المهام التي يمكن ربطها لإمكانيات وقيود ترخيص Aspose.Tasks الخاص بك.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
