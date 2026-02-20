---
date: 2026-02-20
description: استكشف كيفية إضافة مهمة إلى المشروع وإدارة الفترات الزمنية باستخدام Aspose.Tasks
  للغة Java. تعلم كيفية تعيين المدة وكيفية تحويل المدة بسهولة.
linktitle: Manage Durations of Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: إضافة مهمة إلى المشروع وإدارة الفترات الزمنية باستخدام Aspose.Tasks
url: /ar/java/task-properties/manage-durations/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة مهمة إلى المشروع وإدارة الفترات الزمنية باستخدام Aspose.Tasks

## المقدمة
في هذا البرنامج التعليمي ستتعلم **كيفية إضافة مهمة إلى المشروع** والتحكم في مدتها باستخدام Aspose.Tasks للغة Java. سواءً كنت تبني أداة تخطيط مشروع جديدة أو توسّع حلاً موجودًا، فإن إتقان التعامل مع مدة المهمة أمر أساسي للجدولة الدقيقة وإعداد التقارير.

## إجابات سريعة
- **ماذا يعني “add task to project”?** يقوم بإنشاء كائن مهمة جديد تحت جذر المشروع أو تحت مهمة ملخص محددة.  
- **أي فئة تمثل مدة زمنية؟** `com.aspose.tasks.Duration`.  
- **كيف يتم تعيين المدة؟** استخدم `task.set(Tsk.DURATION, project.getDuration(value, TimeUnitType))`.  
- **هل يمكنني تحويل مدة زمنية إلى وحدة أخرى؟** نعم، استدعِ `duration.convert(TimeUnitType.Hour)` أو أي `TimeUnitType` أخرى.  
- **هل أحتاج إلى ترخيص للاستخدام في الإنتاج؟** يلزم وجود ترخيص صالح لـ Aspose.Tasks للاستخدام التجاري.

## ما هو “add task to project”؟
إضافة مهمة إلى مشروع يعني إنشاء كائن `Task` وربطه بهيكل مهام المشروع. هذه العملية هي الخطوة الأولى قبل أن تتمكن من تعريف العمل أو الموارد أو المدة لتلك المهمة.

## لماذا إدارة مدد المهام؟
تؤدي المدّات الدقيقة إلى جداول زمنية واقعية، وتخصيص موارد فعال، وتحليل المسار الحرج. باستخدام Aspose.Tasks يمكنك تعيين، قراءة، تحويل، وتعديل المدّات برمجيًا، مما يمنحك سيطرة كاملة على جداول المشروع.

## المتطلبات المسبقة
قبل البدء، تأكد من توفر ما يلي:

- Java Development Kit (JDK): تأكد من تثبيت Java على جهازك. يمكنك تنزيله [هنا](https://www.oracle.com/java/technologies/javase-downloads.html).
- مكتبة Aspose.Tasks: قم بتنزيل وإدراج مكتبة Aspose.Tasks في مشروعك. يمكنك العثور على المكتبة [هنا](https://releases.aspose.com/tasks/java/).

## استيراد الحزم
في مشروع Java الخاص بك، استورد الحزم اللازمة للعمل مع Aspose.Tasks:
```java
import com.aspose.tasks.Duration;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## الخطوة 1: إعداد مشروعك
```java
// Create a new project
Project project = new Project();
```

## الخطوة 2: إضافة مهمة جديدة (add task to project)
```java
// Add a new task to the project
Task task = project.getRootTask().getChildren().add("Task");
```

## كيفية تعيين المدة
الآن بعد أن تم إنشاء المهمة، يمكنك تحديد طولها. بشكل افتراضي، تُعبّر المدّات بالأيام.

## الخطوة 3: الحصول على مدة المهمة وتحويلها
```java
// Get task duration in days (default time unit)
Duration duration = task.get(Tsk.DURATION);
System.out.println("Duration equals 1 day: " + duration.toString().equals("1 day"));
// Convert duration to hours time unit
duration = duration.convert(TimeUnitType.Hour);
System.out.println("Duration equals 8 hrs: " + duration.toString().equals("8 hrs"));
```

## كيفية تحويل المدة
طريقة `convert` تتيح لك تحويل كائن `Duration` من `TimeUnitType` إلى آخر (مثلاً، أيام → ساعات، أسابيع → أيام).

## الخطوة 4: تحديث مدة المهمة إلى أسبوع واحد
```java
// Increase task duration to 1 week
task.set(Tsk.DURATION, project.getDuration(1, TimeUnitType.Week));
System.out.println("Duration equals 1 wk: " + task.get(Tsk.DURATION).toString().equals("1 wk"));
```

## الخطوة 5: تقليل مدة المهمة
```java
// Decrease task duration
task.set(Tsk.DURATION, task.get(Tsk.DURATION).subtract(0.5));
System.out.println("Duration equals 0.5 wks: " + task.get(Tsk.DURATION).toString().equals("0.5 wks"));
```

باتباع هذه الخطوات، لقد نجحت في **إضافة مهمة إلى مشروع** وإدارة مدتها باستخدام Aspose.Tasks للغة Java.

## الأخطاء الشائعة والنصائح
- **خطأ شائع:** نسيان تحويل المدة قبل إجراء العمليات الحسابية قد يؤدي إلى نتائج غير صحيحة. تحقق دائمًا من الوحدة باستخدام `duration.getTimeUnit()`.
- **نصيحة:** استخدم `project.getDuration(value, TimeUnitType)` لإنشاء مدّات بالوحدة المطلوبة بدلاً من تحويلها لاحقًا.
- **خطأ شائع:** تعيين مدة سلبية سيتسبب في رمي استثناء. تأكد من التحقق من صحة القيم المدخلة.

## الخاتمة
في هذا الدليل غطينا كيفية **إضافة مهمة إلى مشروع**، قراءة مدتها الافتراضية، **تعيين المدة**، و**تحويل المدة** إلى وحدات زمنية مختلفة. يمكنك الآن دمج هذه التقنيات في تطبيقات جدولة أكبر لتخطيط مشروع دقيق.

## الأسئلة المتكررة
### هل Aspose.Tasks متوافق مع جميع إصدارات Java؟
Aspose.Tasks متوافق مع Java 6 والإصدارات الأحدث.

### هل يمكنني استخدام Aspose.Tasks في المشاريع التجارية؟
نعم، يمكنك استخدام Aspose.Tasks في المشاريع الشخصية والتجارية على حد سواء. زر [هنا](https://purchase.aspose.com/buy) للحصول على تفاصيل الترخيص.

### أين يمكنني العثور على دعم وموارد إضافية؟
قم بزيارة [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15) للحصول على دعم المجتمع والنقاشات.

### كيف يمكنني الحصول على ترخيص مؤقت لأغراض الاختبار؟
يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/) للاختبار والتقييم.

### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Tasks؟
نعم، يمكنك الوصول إلى النسخة التجريبية المجانية [هنا](https://releases.aspose.com/) لاستكشاف Aspose.Tasks قبل الشراء.

## الأسئلة المتكررة

**س: كيف يمكنني تغيير مدة المهمة بعد تعيينها؟**  
ج: استرجع المدة الحالية باستخدام `task.get(Tsk.DURATION)`, عدّلها (مثلًا `add`، `subtract` أو `convert`)، ثم عيّنها مرة أخرى باستخدام `task.set(Tsk.DURATION, newDuration)`.

**س: هل يمكنني تعيين مدة بالدقائق؟**  
ج: نعم، استخدم `TimeUnitType.Minute` عند استدعاء `project.getDuration(value, TimeUnitType.Minute)`.

**س: هل يؤدي تغيير المدة إلى تحديث تواريخ بدء وانتهاء المهمة تلقائيًا؟**  
ج: فقط إذا تم ضبط وضع جدولة المشروع على الوضع التلقائي. وإلا قد تحتاج إلى إعادة حساب الجدول باستخدام `project.calculateCriticalPath()`.

**س: هل يمكن استرجاع المدة كقيمة رقمية خام؟**  
ج: استدعِ `duration.getTimeSpan()` للحصول على القيمة الرقمية في الوحدة الزمنية الحالية.

**س: ماذا يحدث إذا قمت بطرح قيمة أكبر من المدة الحالية؟**  
ج: ستقوم الـ API برمي استثناء `ArgumentOutOfRangeException`. تأكد دائمًا من أن المدة الناتجة تبقى موجبة.

---

**آخر تحديث:** 2026-02-20  
**تم الاختبار مع:** Aspose.Tasks للغة Java (الأحدث)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}