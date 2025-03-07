---
title: إدارة مهام الوالدين والطفل في Aspose.Tasks
linktitle: إدارة مهام الوالدين والطفل في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعزيز كفاءة إدارة المشاريع باستخدام Aspose.Tasks لـ Java. تعلم كيفية إدارة مهام الوالدين والطفل خطوة بخطوة. نبدأ الآن!
weight: 24
url: /ar/java/task-properties/parent-child-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إدارة مهام الوالدين والطفل في Aspose.Tasks

## مقدمة
في مجال إدارة المشاريع، يعد التنظيم الفعال للمهام أمرًا بالغ الأهمية. يوفر Aspose.Tasks for Java حلاً قويًا لإدارة مهام الوالدين والطفل بكفاءة. في هذا البرنامج التعليمي، سنرشدك خلال عملية استخدام Aspose.Tasks لـ Java لتبسيط مهام مشروعك.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
- الفهم الأساسي لبرمجة جافا.
-  تم تثبيت Aspose.Tasks لمكتبة Java. يمكنك تنزيله[هنا](https://releases.aspose.com/tasks/java/).
- تم إعداد بيئة تطوير Java المتكاملة (IDE) على نظامك.
## حزم الاستيراد
للبدء، قم باستيراد الحزم الضرورية إلى مشروع Java الخاص بك. تسهل هذه الحزم التكامل السلس مع Aspose.Tasks لوظائف Java.
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.io.IOException;
import java.util.Date;
import java.util.List;
```
## الخطوة 1: تحديد تاريخ بدء المشروع
ابدأ بتحديد تاريخ بدء المشروع والمعلمات الأخرى ذات الصلة.
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Project proj = new Project(dataDir + "Blank2010.mpp");
proj.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
// يمكن إضافة رمز إضافي لواردات الحزمة هنا
double oneDay = 8d * 60d * 60d * 10000000d;
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, 9, 13, 8, 0, 0);
Date startDate = cal.getTime();
proj.set(Prj.START_DATE, startDate);
```
## الخطوة 2: إضافة مهمة رئيسية (المهمة 1)
قم بإنشاء مهمة أصل باسم "المهمة 1" وقم بتكوين خصائصها.
```java
Task task1 = proj.getRootTask().getChildren().add("Task 1");
cal.set(2014, 9, 13, 8, 0, 0);
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, proj.getDuration(29, TimeUnitType.Day));
```
## الخطوة 3: إضافة مهمة الأصل (المهمة 2) مع المهام التابعة
الآن، قم بإضافة مهمة رئيسية أخرى تسمى "المهمة 2" وقم بتضمين المهام الفرعية (المهمة 3 والمهمة 4).
```java
Task task2 = proj.getRootTask().getChildren().add("Task 2");
// أضف مهام فرعية إلى المهمة 2
Task task3 = task2.getChildren().add("Task 3");
Task task4 = task2.getChildren().add("Task 4");
// يمكن إضافة تكوين إضافي للمهمة 3 والمهمة 4 هنا
```
## الخطوة 4: تكوين المهام الفرعية
حدد تواريخ البدء والمدد والقيود للمهمة 3 والمهمة 4.
```java
// تكوين المهمة 3
cal.set(2014, 9, 15, 8, 0, 0);
task3.set(Tsk.START, cal.getTime());
task3.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task3.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task3.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
// تكوين المهمة 4
cal.set(2014, 9, 17, 8, 0, 0);
task4.set(Tsk.START, cal.getTime());
task4.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task4.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task4.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
```
## الخطوة 5: تحديث النسبة المئوية لاكتمال المهمة
اضبط نسبة الإنجاز للمهمة 3 والمهمة 4.
```java
task3.set(Tsk.PERCENT_COMPLETE, 50);
task4.set(Tsk.PERCENT_COMPLETE, 70);
```
## الخطوة 6: احفظ المشروع
وأخيرا، احفظ المشروع بالتغييرات المطبقة.
```java
proj.save(dataDir + "ProjectJava.mpp", SaveFileFormat.Mpp);
```
يوضح هذا الدليل خطوة بخطوة كيفية إدارة المهام الرئيسية والفرعية بشكل فعال باستخدام Aspose.Tasks لـ Java. قم بتجربة تكوينات مختلفة لتناسب متطلبات مشروعك.
## خاتمة
في الختام، يعمل Aspose.Tasks for Java على تمكين المطورين من التعامل مع مهام المشروع بكفاءة، مما يضمن التنظيم والتتبع السلس. قم بتنفيذ الخطوات الموضحة لتعزيز قدرات إدارة المشروع الخاص بك.
## الأسئلة الشائعة
### هل Aspose.Tasks for Java متوافق مع تنسيقات ملفات المشروع المختلفة؟
نعم، يدعم Aspose.Tasks for Java تنسيقات ملفات المشروع المختلفة، بما في ذلك MPP وXML.
### هل يمكنني تخصيص خصائص المهمة بما يتجاوز ما تم تناوله في هذا البرنامج التعليمي؟
قطعاً! يوفر Aspose.Tasks for Java خيارات تخصيص واسعة النطاق لخصائص المهمة.
### هل يوجد منتدى مجتمعي لـ Aspose.Tasks حيث يمكنني طلب الدعم؟
 نعم يمكنك زيارة[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15) لدعم المجتمع.
### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Tasks لـ Java؟
 يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).
### أين يمكنني العثور على وثائق شاملة لـ Aspose.Tasks لـ Java؟
 الوثائق متاحة[هنا](https://reference.aspose.com/tasks/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
