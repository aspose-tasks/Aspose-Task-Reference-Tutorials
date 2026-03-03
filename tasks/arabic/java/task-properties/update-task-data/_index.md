---
date: 2026-03-03
description: تعلم كيفية تحديث بيانات المهمة إلى تنسيق MPP باستخدام Aspose Tasks Java.
  اتبع دليلنا خطوة بخطوة لإدارة مشاريع فعّالة.
linktitle: Update Task Data to MPP Format in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: aspose tasks java – تحديث بيانات المهمة إلى تنسيق MPP
url: /ar/java/task-properties/update-task-data/
weight: 35
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تحديث بيانات المهمة إلى تنسيق MPP في Aspose.Tasks

## المقدمة
مرحبًا بكم في دليلنا خطوة بخطوة حول **تحديث بيانات المهمة إلى تنسيق MPP باستخدام Aspose.Tasks for Java**. في هذا الدرس ستتعلم كيفية التعامل مع ملفات المشروع برمجيًا باستخدام *aspose tasks java*، من إنشاء مهمة ملخص إلى تحويل مشروع XML إلى ملف MPP. في النهاية ستتمكن من إدارة مهام المشروع بفعالية ودمج الحل في تطبيقات Java الخاصة بك.

## إجابات سريعة
- **ماذا يغطي هذا الدرس؟** تحديث بيانات المهمة وحفظ المشروع كملف MPP باستخدام Aspose.Tasks for Java.  
- **هل أحتاج إلى ترخيص؟** يتطلب الترخيص المؤقت أو الكامل للاستخدام في الإنتاج؛ تتوفر نسخة تجريبية مجانية.  
- **ما هو بيئة التطوير المتكاملة (IDE) الأفضل؟** أي بيئة تطوير Java (IntelliJ IDEA, Eclipse, VS Code) ستعمل.  
- **هل يمكنني تحويل XML إلى MPP؟** نعم – المثال يقوم بتحميل مشروع XML ويحفظه كملف MPP.  
- **كم عدد المهام التي تم إنشاؤها؟** العينة تنشئ مهمة رئيسية واحدة، مهمة ملخص، وعشرة مهام إضافية.

## ما هو Aspose.Tasks for Java؟
Aspose.Tasks for Java هو API قوي يتيح للمطورين قراءة وكتابة وتعديل ملفات Microsoft Project (MPP، XML، وأكثر) دون الحاجة إلى تثبيت Microsoft Project. يدعم التلاعب الكامل على مستوى المشروع، بما في ذلك إنشاء المهام، معالجة القيود، وتحويل صيغ الملفات.

## لماذا نستخدم Aspose.Tasks Java لإدارة المشاريع؟
- **تحكم كامل** في خصائص المهمة مثل تاريخ البدء، المدة، والقيود.  
- **تحويل سلس** بين XML و MPP، مما يتيح التكامل مع خطوط بيانات المشاريع الحالية.  
- **بدون COM interop** – Java نقي، مثالي لبيئات متعددة المنصات.  
- **أداء عالي** لملفات المشاريع الكبيرة، مما يجعلها مناسبة للحلول على مستوى المؤسسات.

## المتطلبات المسبقة
قبل أن نبدأ الدرس، تأكد من توفر المتطلبات التالية:
- Aspose.Tasks for Java: تأكد من تثبيت مكتبة Aspose.Tasks. يمكنك تنزيلها من [صفحة الإصدار](https://releases.aspose.com/tasks/java/).
- Java Development Kit (JDK): تأكد من تثبيت Java على نظامك.
- Integrated Development Environment (IDE): استخدم بيئة تطوير من اختيارك لتطوير Java.

## استيراد الحزم
ابدأ باستيراد الحزم اللازمة إلى مشروع Java الخاص بك. يوضح المقتطف التالي كيفية استيراد الحزم:

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

## كيفية إنشاء مهمة ملخص
مهمة الملخص تجمع المهام الفرعية ذات الصلة، مما يمنحك نظرة عالية المستوى على حزم العمل. في الشيفرة أدناه نقوم بإنشاء مهمة ملخص وربط المهمة الأولى كطفل لها.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
long OneSec = 1000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
Project project = new Project(dataDir + "project.xml");
Task task1 = project.getRootTask().getChildren().add("First task");
//... (Continue with the rest of the code)
```

## كيفية تعيين تاريخ البدء للمهمة
تعيين تاريخ البدء أمر أساسي للجدولة الدقيقة. يستخدم المثال كائن `Calendar` لتحديد تاريخ بدء المشروع ويعيّنه للمهمة.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 12, 10, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, project.getDuration(24, TimeUnitType.Hour));
//... (Continue with the rest of the code)
```

## كيفية تحويل XML إلى MPP
يمكن للـ API قراءة ملف مشروع XML وحفظه مباشرة كملف MPP، مما يسهل الهجرة من الصيغ القديمة.

```java
Task summary = project.getRootTask().getChildren().add("Summary task");
summary.getChildren().add(task1);
//... (Continue with the rest of the code)
```

## كيفية تعيين الموعد النهائي وإضافة ملاحظات للمهمة
المواعيد النهائية تساعد على إبقاء المهام على المسار الصحيح، بينما توفر الملاحظات سياقًا لأعضاء الفريق.

```java
cal.setTime(task1.get(Tsk.START));
cal.add(java.util.Calendar.DATE, 10);
task1.set(Tsk.DEADLINE, cal.getTime());
task1.set(Tsk.NOTES_TEXT, "The first task.");
//... (Continue with the rest of the code)
```

## كيفية تكوين قيود المهمة وتحديث مدة المهمة
القيود مثل *Finish No Later Than* توجه المجدول. يمكنك أيضًا تغيير صيغة المدة لتعكس الأيام المقدرة.

```java
task1.set(Tsk.DURATION_FORMAT, TimeUnitType.DayEstimated);
task1.set(Tsk.CONSTRAINT_TYPE, ConstraintType.FinishNoLaterThan);
//... (Continue with the rest of the code)
```

## كيفية إنشاء مهام إضافية (إدارة مهام المشروع)
يوضح الحلقة أدناه كيفية إنشاء مهام متعددة برمجيًا، وهو طلب شائع عند استيراد بيانات ضخمة.

```java
// Create 10 new tasks
for (int i = 0; i < 10; i++) {
    //... (Continue with the rest of the code)
}
//... (Continue with the rest of the code)
```

## كيفية حفظ المشروع (تصدير إلى MPP)
أخيرًا، احفظ التغييرات عن طريق حفظ المشروع كملف MPP.

```java
// Save the Project
project.save(dataDir + "WritingUpdatedTaskDataToMpp.mpp", SaveFileFormat.Mpp);
```

باتباع هذه الخطوات، لقد نجحت في **تحديث بيانات المهمة إلى تنسيق MPP باستخدام aspose tasks java**. الآن لديك أساس قوي لإدارة مهام المشروع، إنشاء مهام ملخص، تعيين تواريخ البدء، وتحويل مشاريع XML إلى MPP.

## الخاتمة
تهانينا! لقد أكملت دليلًا شاملًا حول تحديث بيانات المهمة إلى تنسيق MPP باستخدام Aspose.Tasks for Java. هذه المكتبة القوية تبسط مهام إدارة المشاريع، مما يجعلها أداة قيمة لمطوري Java الذين يحتاجون إلى **إدارة مهام المشروع** برمجيًا.

## الأسئلة المتكررة

### س: أين يمكنني العثور على وثائق Aspose.Tasks for Java؟
ج: الوثائق متاحة [هنا](https://reference.aspose.com/tasks/java/).

### س: كيف يمكنني تنزيل Aspose.Tasks for Java؟
ج: يمكنك تنزيله من [صفحة الإصدار](https://releases.aspose.com/tasks/java/).

### س: هل تتوفر نسخة تجريبية مجانية؟
ج: نعم، يمكنك الوصول إلى النسخة التجريبية [هنا](https://releases.aspose.com/).

### س: أين يمكنني الحصول على الدعم لـ Aspose.Tasks for Java؟
ج: زر منتدى الدعم [هنا](https://forum.aspose.com/c/tasks/15).

### س: هل تقدمون تراخيص مؤقتة لأغراض الاختبار؟
ج: نعم، يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**آخر تحديث:** 2026-03-03  
**تم الاختبار مع:** Aspose.Tasks for Java 24.11 (latest)  
**المؤلف:** Aspose  

---