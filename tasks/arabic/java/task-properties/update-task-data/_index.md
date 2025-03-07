---
title: قم بتحديث بيانات المهمة إلى تنسيق MPP في Aspose.Tasks
linktitle: قم بتحديث بيانات المهمة إلى تنسيق MPP في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية تحديث بيانات المهمة إلى تنسيق MPP باستخدام Aspose.Tasks لـ Java. اتبع دليلنا خطوة بخطوة لإدارة المشاريع بكفاءة.
weight: 35
url: /ar/java/task-properties/update-task-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# قم بتحديث بيانات المهمة إلى تنسيق MPP في Aspose.Tasks

## مقدمة
مرحبًا بك في دليلنا خطوة بخطوة حول تحديث بيانات المهمة إلى تنسيق MPP باستخدام Aspose.Tasks لـ Java. في هذا البرنامج التعليمي، سنرشدك خلال العملية، مع التأكد من أنك تفهم كل خطوة بوضوح. يوفر Aspose.Tasks for Java حلاً قويًا للعمل مع ملفات Microsoft Project، وبنهاية هذا الدليل، ستتمكن من تحديث بيانات المهمة بكفاءة بتنسيق MPP.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
-  Aspose.Tasks لـ Java: تأكد من تثبيت مكتبة Aspose.Tasks. يمكنك تنزيله من[صفحة الإصدار](https://releases.aspose.com/tasks/java/).
- Java Development Kit (JDK): تأكد من تثبيت Java على نظامك.
- بيئة التطوير المتكاملة (IDE): استخدم بيئة تطوير متكاملة (IDE) من اختيارك لتطوير Java.
## حزم الاستيراد
ابدأ باستيراد الحزم الضرورية إلى مشروع Java الخاص بك. يوضح المقتطف التالي كيفية استيراد الحزم:
```java
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.examples.TaskLinks.UpdatedTaskLinkDataToMpp;
```
## 1. إنشاء وتكوين المهمة الأولية
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
long OneSec = 1000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
Project project = new Project(dataDir + "project.xml");
Task task1 = project.getRootTask().getChildren().add("First task");
//... (تابع مع بقية الكود)
```
## 2. قم بتعيين تاريخ البدء والمدة
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 12, 10, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, project.getDuration(24, TimeUnitType.Hour));
//... (تابع مع بقية الكود)
```
## 3. قم بإنشاء مهمة ملخصة
```java
Task summary = project.getRootTask().getChildren().add("Summary task");
summary.getChildren().add(task1);
//... (تابع مع بقية الكود)
```
## 4. حدد الموعد النهائي وملاحظات المهمة
```java
cal.setTime(task1.get(Tsk.START));
cal.add(java.util.Calendar.DATE, 10);
task1.set(Tsk.DEADLINE, cal.getTime());
task1.set(Tsk.NOTES_TEXT, "The first task.");
//... (تابع مع بقية الكود)
```
## 5. تكوين قيود المهمة
```java
task1.set(Tsk.DURATION_FORMAT, TimeUnitType.DayEstimated);
task1.set(Tsk.CONSTRAINT_TYPE, ConstraintType.FinishNoLaterThan);
//... (تابع مع بقية الكود)
```
## 6. إنشاء مهام إضافية
```java
//إنشاء 10 مهام جديدة
for (int i = 0; i < 10; i++) {
    //... (تابع مع بقية الكود)
}
//... (تابع مع بقية الكود)
```
## 7. احفظ المشروع
```java
// احفظ المشروع
project.save(dataDir + "WritingUpdatedTaskDataToMpp.mpp", SaveFileFormat.Mpp);
```
باتباع هذه الخطوات، تكون قد قمت بنجاح بتحديث بيانات المهمة إلى تنسيق MPP باستخدام Aspose.Tasks لـ Java.
## خاتمة
تهانينا! لقد أكملت دليلاً شاملاً حول تحديث بيانات المهمة بتنسيق MPP باستخدام Aspose.Tasks لـ Java. تعمل هذه المكتبة القوية على تبسيط مهام إدارة المشاريع، مما يجعلها أداة قيمة لمطوري Java.
## الأسئلة الشائعة
### س: أين يمكنني العثور على وثائق Aspose.Tasks الخاصة بـ Java؟
 ج: الوثائق متاحة[هنا](https://reference.aspose.com/tasks/java/).
### س: كيف يمكنني تنزيل Aspose.Tasks لـ Java؟
 ج: يمكنك تحميله من[صفحة الإصدار](https://releases.aspose.com/tasks/java/).
### س: هل هناك نسخة تجريبية مجانية متاحة؟
 ج: نعم، يمكنك الوصول إلى النسخة التجريبية المجانية[هنا](https://releases.aspose.com/).
### س: أين يمكنني الحصول على الدعم لـ Aspose.Tasks لـ Java؟
 ج: قم بزيارة منتدى الدعم[هنا](https://forum.aspose.com/c/tasks/15).
### س: هل تقدمون تراخيص مؤقتة لأغراض الاختبار؟
 ج: نعم، يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
