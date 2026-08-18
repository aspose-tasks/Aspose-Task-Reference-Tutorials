---
date: 2026-02-23
description: تعلم كيفية تعيين تاريخ بدء المشروع، وتحديد مدة المهمة، وحفظ المشروع بصيغة
  MPP باستخدام Aspose.Tasks للغة Java. إدارة المهام الأصلية والفرعية بكفاءة.
linktitle: Set Project Start Date and Manage Parent and Child Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: تحديد تاريخ بدء المشروع وإدارة المهام الأصلية والفرعية في Aspose.Tasks
url: /ar/java/task-properties/parent-child-tasks/
weight: 24
---

 translate Q and A.

At bottom, "Last Updated:", "Tested With:", "Author:" translate.

Make sure not to translate URLs.

Now produce final content.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تعيين تاريخ بدء المشروع وإدارة المهام الأصلية والفرعية في Aspose.Tasks

## المقدمة
تُعدّ تنظيم المهام بفعالية العمود الفقري لإدارة المشاريع الناجحة، و**تعيين تاريخ بدء المشروع** بشكل صحيح هو الخطوة الأولى نحو جدول زمني منظم جيدًا. في هذا الدرس ستتعرف على كيفية **تعيين تاريخ بدء المشروع**، وضبط مدد المهام، وإدارة علاقات الأصل‑الفرع باستخدام Aspose.Tasks for Java. في النهاية، ستكون جاهزًا لـ **حفظ المشروع كملف MPP**، وتحديث نسب إكمال المهام، وتخصيص خصائص المهام لتناسب أي سيناريو واقعي.

## إجابات سريعة
- **كيف يمكنني تعيين تاريخ بدء المشروع؟** استخدم `proj.set(Prj.START_DATE, startDate);` بعد تهيئة كائن `Project`.  
- **هل يمكنني إضافة مهام فرعية تحت مهمة أصلية؟** نعم – استدعِ `parentTask.getChildren().add("Child Task")`.  
- **بأي صيغة يحفظ Aspose.Tasks الملف؟** استخدم `SaveFileFormat.Mpp` لـ **حفظ المشروع كملف MPP**.  
- **كيف يمكنني تحديث إكمال المهمة؟** عيّن `Tsk.PERCENT_COMPLETE` على كائن المهمة.  
- **أين يمكنني الحصول على ترخيص مؤقت؟** زر صفحة الترخيص المؤقت المرتبطة في الأسئلة المتكررة.

## المتطلبات المسبقة
قبل الغوص في الدرس، تأكد من توفر المتطلبات التالية:
- فهم أساسي لبرمجة Java.  
- مكتبة Aspose.Tasks for Java مثبتة. يمكنك تنزيلها [هنا](https://releases.aspose.com/tasks/java/).  
- بيئة تطوير متكاملة (IDE) للـ Java مُعدّة على نظامك.

## استيراد الحزم
للبدء، استورد الحزم الضرورية إلى مشروع Java الخاص بك. هذه الحزم تسهّل التكامل السلس مع وظائف Aspose.Tasks for Java.
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

## الخطوة 1: تعيين تاريخ بدء المشروع
ابدأ بتعيين تاريخ بدء المشروع والمعلمات ذات الصلة.
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project proj = new Project(dataDir + "Blank2010.mpp");
proj.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
// Additional code for package imports can be added here
double oneDay = 8d * 60d * 60d * 10000000d;
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, 9, 13, 8, 0, 0);
Date startDate = cal.getTime();
proj.set(Prj.START_DATE, startDate);
```

## الخطوة 2: إضافة مهمة أصلية (المهمة 1)
أنشئ مهمة أصلية باسم "Task 1" واضبط خصائصها، بما في ذلك **set task duration**.
```java
Task task1 = proj.getRootTask().getChildren().add("Task 1");
cal.set(2014, 9, 13, 8, 0, 0);
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, proj.getDuration(29, TimeUnitType.Day));
```

## الخطوة 3: إضافة مهمة أصلية (المهمة 2) مع مهام فرعية
الآن، أضف مهمة أصلية أخرى باسم "Task 2" وضمّن المهام الفرعية (Task 3 و Task 4).
```java
Task task2 = proj.getRootTask().getChildren().add("Task 2");
// Add child tasks to Task 2
Task task3 = task2.getChildren().add("Task 3");
Task task4 = task2.getChildren().add("Task 4");
// Additional configuration for Task 3 and Task 4 can be added here
```

## الخطوة 4: ضبط المهام الفرعية
حدد تواريخ البدء، والمدة، والقيود للمهمة 3 والمهمة 4.
```java
// Configure Task 3
cal.set(2014, 9, 15, 8, 0, 0);
task3.set(Tsk.START, cal.getTime());
task3.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task3.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task3.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
// Configure Task 4
cal.set(2014, 9, 17, 8, 0, 0);
task4.set(Tsk.START, cal.getTime());
task4.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task4.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task4.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
```

## الخطوة 5: تحديث نسبة إكمال المهمة
عدّل نسبة الإكمال للمهمة 3 والمهمة 4 – هذه هي الطريقة لـ **update task completion**.
```java
task3.set(Tsk.PERCENT_COMPLETE, 50);
task4.set(Tsk.PERCENT_COMPLETE, 70);
```

## الخطوة 6: حفظ المشروع
أخيرًا، **save project as MPP** مع التغييرات المطبقة.
```java
proj.save(dataDir + "ProjectJava.mpp", SaveFileFormat.Mpp);
```

هذا الدليل خطوة بخطوة يوضح كيفية إدارة المهام الأصلية والفرعية بفعالية باستخدام Aspose.Tasks for Java. جرّب تكوينات مختلفة لتناسب متطلبات مشروعك.

## لماذا تخصيص خصائص المهمة؟
يمنحك تخصيص خصائص المهمة مثل تواريخ البدء، والمدة، والقيود، ونسب الإكمال سيطرة دقيقة على سلوك الجدول الزمني. سواء كنت بحاجة لمزامنة المهام مع توافر الموارد أو فرض قواعد عمل، يتيح لك Aspose.Tasks **customize task properties** برمجيًا.

## المشكلات الشائعة والحلول
| المشكلة | الحل |
|-------|----------|
| **لم يتم تطبيق تاريخ البدء** | تأكد من استدعاء `proj.set(Prj.START_DATE, …)` **بعد** إنشاء كائن `Project` وقبل إضافة المهام. |
| **المهام الفرعية ترث قيودًا خاطئة** | عيّن كل من `ConstraintType` و `ConstraintDate` للفرع صراحةً، كما هو موضح في الخطوة 4. |
| **الملف المحفوظ لا يمكن فتحه في MS Project** | تحقق من أنك تستخدم أحدث نسخة من Aspose.Tasks واحفظ باستخدام `SaveFileFormat.Mpp`. |
| **النسبة لا تظهر في الواجهة** | بعد ضبط `Tsk.PERCENT_COMPLETE`، استدعِ `proj.calculateTaskSchedule()` إذا كنت تحتاج إلى إعادة حساب التواريخ. |

## الأسئلة المتكررة
### هل Aspose.Tasks for Java متوافق مع صيغ ملفات مشروع مختلفة؟
نعم، يدعم Aspose.Tasks for Java صيغ ملفات مشروع متعددة، بما في ذلك MPP و XML.

### هل يمكنني تخصيص خصائص المهمة بما يتجاوز ما تم تغطيته في هذا الدرس؟
بالتأكيد! يوفر Aspose.Tasks for Java خيارات تخصيص واسعة لخصائص المهمة.

### هل هناك منتدى مجتمع لـ Aspose.Tasks يمكنني طلب الدعم منه؟
نعم، يمكنك زيارة [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15) للحصول على دعم المجتمع.

### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Tasks for Java؟
يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

### أين يمكنني العثور على وثائق شاملة لـ Aspose.Tasks for Java؟
الوثائق متاحة [هنا](https://reference.aspose.com/tasks/java/).

**أسئلة وإجابات إضافية**

**س: كيف يمكنني الحصول على ترخيص مؤقت برمجيًا؟**  
ج: حمّل ملف الترخيص المؤقت باستخدام `License license = new License(); license.setLicense("Aspose.Tasks.lic");`.

**س: هل يمكنني تغيير وحدة مدة المهمة الافتراضية؟**  
ج: نعم – عدّل معامل `TimeUnitType` في `proj.getDuration(value, TimeUnitType.YourChoice)`.

**س: ما الإصدار المطلوب من Aspose.Tasks لاستخدام `SaveFileFormat.Mpp`؟**  
ج: جميع الإصدارات الحديثة (2022‑2026) تدعم الحفظ كملف MPP؛ راجع ملاحظات الإصدار لأي تغييرات كسرية.

---

**آخر تحديث:** 2026-02-23  
**تم الاختبار مع:** Aspose.Tasks for Java 24.11  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}