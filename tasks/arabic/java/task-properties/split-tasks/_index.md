---
title: تقسيم المهام في Aspose.Tasks
linktitle: تقسيم المهام في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: إدارة المهام الرئيسية في Java باستخدام Aspose.Tasks! تعرف على كيفية تقسيم المهام بكفاءة للحصول على جداول زمنية محسنة للمشروع. التحميل الان!
weight: 29
url: /ar/java/task-properties/split-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تقسيم المهام في Aspose.Tasks

## مقدمة
هل تواجه صعوبة في إدارة المهام في مشروع Java الخاص بك؟ يوفر Aspose.Tasks for Java حلاً قويًا لتقسيم المهام بكفاءة، وتعزيز قدرات إدارة المشروع. في هذا البرنامج التعليمي، سنرشدك خلال عملية تقسيم المهام باستخدام Aspose.Tasks لـ Java، مما يساعدك على تحسين الجداول الزمنية لمشروعك وتخصيص الموارد.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
- تم تثبيت Java Development Kit (JDK) على جهازك.
-  تم تنزيل Aspose.Tasks لمكتبة Java وإضافتها إلى مشروعك. يمكنك تنزيله من[Aspose.Tasks لوثائق جافا](https://reference.aspose.com/tasks/java/).
## حزم الاستيراد
ابدأ باستيراد الحزم الضرورية إلى مشروع Java الخاص بك:
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
// إنشاء مشروع جديد
Project splitTaskProject = new Project();
```
## الخطوة 2: تعيين تقويم المشروع
قم بتعيين إعدادات تقويم المشروع لتحديد الجدول الزمني:
```java
// احصل على تقويم قياسي
Calendar calendar = splitTaskProject.get(Prj.CALENDAR);
// ضبط إعدادات التقويم للمشروع
java.util.Calendar cal = java.util.Calendar.getInstance();
// ... (تابع مع المثال)
```
## الخطوة 3: إضافة مهمة الجذر
أضف مهمة جذرية إلى مشروعك:
```java
// مهمة الجذر
Task rootTask = splitTaskProject.getRootTask();
rootTask.set(Tsk.NAME, "Root");
```
## الخطوة 4: إضافة مهمة جديدة للتقسيم
أضف مهمة جديدة إلى مشروعك الذي تريد تقسيمه:
```java
// إضافة مهمة جديدة
Task taskToSplit = rootTask.getChildren().add("Task1");
taskToSplit.set(Tsk.DURATION, splitTaskProject.getDuration(3));
```
## الخطوة 5: إنشاء تعيين الموارد
إنشاء تعيين مورد جديد للمهمة:
```java
// إنشاء تعيين موارد جديد
ResourceAssignment splitResourceAssignment = splitTaskProject.getResourceAssignments().add(taskToSplit, null);
```
## الخطوة 6: إنشاء بيانات موزعة على الوقت
إنشاء بيانات موزعة على الوقت لتعيين الموارد:
```java
// إنشاء بيانات موزعة على الوقت لتخصيص الموارد
splitResourceAssignment.timephasedDataFromTaskDuration(calendar);
```
## الخطوة 7: تقسيم المهمة
تقسيم المهمة إلى أجزاء متعددة:
```java
// قسم المهمة إلى 3 أجزاء
java.util.Calendar cal = java.util.Calendar.getInstance();
java.util.Calendar cal2 = java.util.Calendar.getInstance();
// ... (تابع مع المثال)
```
## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية تقسيم المهام باستخدام Aspose.Tasks لـ Java. تعمل هذه المكتبة القوية على تبسيط إدارة المهام في مشاريع Java، مما يوفر حلولاً فعالة لتحسين الجداول الزمنية للمشروع وتخصيص الموارد.
## أسئلة مكررة
### هل يمكنني تقسيم المهام بفترات مختلفة؟
نعم، يمكنك تعديل مدة المهام حسب متطلبات مشروعك.
### هل Aspose.Tasks for Java متوافق مع جميع إصدارات Java؟
تم تصميم Aspose.Tasks for Java للعمل بسلاسة مع إصدارات Java المختلفة، مما يضمن التوافق.
### هل يمكنني استخدام Aspose.Tasks لـ Java مجانًا؟
يقدم Aspose.Tasks for Java نسخة تجريبية مجانية، مما يسمح لك باستكشاف ميزاته قبل إجراء عملية شراء.
### كيف يمكنني الحصول على دعم Aspose.Tasks لـ Java؟
 قم بزيارة[Aspose.Tasks لمنتدى دعم جافا](https://forum.aspose.com/c/tasks/15) للحصول على المساعدة والتواصل مع المجتمع.
### هل أحتاج إلى ترخيص مؤقت لـ Aspose.Tasks لـ Java؟
 يمكنك الحصول على ترخيص مؤقت من[هذا الرابط](https://purchase.aspose.com/temporary-license/) لأغراض الاختبار والتقييم.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
