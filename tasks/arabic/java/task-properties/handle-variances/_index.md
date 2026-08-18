---
date: 2026-02-20
description: تعلم كيفية تعيين تاريخ بدء المشروع وإدارة اختلافات المشروع باستخدام Aspose.Tasks
  للغة Java. يوضح هذا الدليل أيضًا كيفية تعيين مدة المهمة بكفاءة.
linktitle: Handle Task Variances in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: تعيين تاريخ بدء المشروع ومعالجة اختلافات المهام Aspose.Tasks
url: /ar/java/task-properties/handle-variances/
weight: 19
---

/products/products-backtop-button >}}

Then horizontal rule "---"

Then metadata lines:

**Last Updated:** 2026-02-20  
**Tested With:** Aspose.Tasks latest Java release  
**Author:** Aspose

Translate labels but keep dates and names.

**Last Updated:** -> "**آخر تحديث:** 2026-02-20"

**Tested With:** -> "**تم الاختبار مع:** Aspose.Tasks latest Java release" maybe keep English for release name.

**Author:** -> "**المؤلف:** Aspose"

Make sure to keep markdown bold formatting.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تعيين تاريخ بدء المشروع ومعالجة تباينات المهام Aspose.Tasks

## المقدمة
في عالم إدارة المشاريع، **set project start date** هو أحد أولى الإجراءات التي تتخذها لتوفير أساس صلب لجدولك الزمني. تجعل Aspose.Tasks for Java هذه الخطوة—وتعاملها اللاحق مع تباينات المهام—سهلة وموثوقة. في هذا البرنامج التعليمي ستتعلم كيفية تعيين تاريخ بدء المشروع، تعيين مدة المهمة، وإدارة تباينات المشروع بفعالية.

## إجابات سريعة
- **ما هي الطريقة الأساسية لتعيين تاريخ بدء المشروع؟** استخدم `project.set(Prj.START_DATE, …)` مع كائن `java.util.Calendar`.  
- **أي فئة تمثل خط الأساس لتتبع التباين؟** `BaselineType.Baseline`.  
- **هل يمكنني تعديل تواريخ بدء وإيقاف المهمة بعد تعيين خط الأساس؟** نعم، فقط قم بتحديث `Tsk.START` و `Tsk.STOP`.  
- **هل أحتاج إلى ترخيص للاستخدام التطويري؟** ترخيص مؤقت متاح للتقييم.  
- **ما هو إصدار Aspose.Tasks المتوافق مع هذا الكود؟** أحدث إصدار من Aspose.Tasks for Java.

## ما هو **set project start date**؟
تحديد تاريخ بدء المشروع يحدد اليوم التقويمي الذي تُحسب منه جميع تواريخ المهام. يؤثر ذلك على حسابات الجدول الزمني، تحليل المسار الحرج، وإنشاء خط الأساس، مما يجعله ضروريًا لإدارة التباينات بدقة.

## لماذا نحدد تاريخ بدء المشروع وندير التباينات؟
- **القابلية للتنبؤ:** يضع خط أساس معروف للمقارنة مع التقدم الفعلي.  
- **المرونة:** يتيح لك تعديل تواريخ المهام الفردية دون فقدان الخطة الأصلية.  
- **التقارير:** يتيح تقارير تباين واضحة تُظهر تأخر الجدول أو الانتهاء المبكر.  

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من وجود ما يلي:

- بيئة تطوير جافا – JDK مثبت وIDE أو أداة بناء جاهزة.  
- مكتبة Aspose.Tasks – قم بتنزيل المكتبة **[هنا](https://releases.aspose.com/tasks/java/)**.  

## استيراد الحزم
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## الخطوة 1: إعداد المشروع
أنشئ كائن `Project` جديد سيحمل جميع المهام ومعلومات الجدول الزمني.

```java
Project project = new Project();
```

## الخطوة 2: إضافة مهمة
أضف مهمة تحت المهمة الجذرية. ستكون هذه العنصر العملي الذي سنقوم بتعديله لاحقًا.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## الخطوة 3: تعيين تاريخ البدء والمدة
حدد تاريخ بدء المشروع ومنح المهمة مدة. هذا يوضح **set task duration** عمليًا.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
task.set(Tsk.DURATION, project.getDuration(2));
```

## الخطوة 4: تعيين خط الأساس
أنشئ خط أساس حتى تتمكن لاحقًا من مقارنة التواريخ المخططة مع الفعلية—وهو أساسي لـ **manage project variances**.

```java
project.setBaseline(BaselineType.Baseline);
```

## الخطوة 5: تعديل تواريخ بدء وإيقاف المهمة
قم بتعديل تواريخ بدء وإيقاف المهمة لمحاكاة سيناريو تباين.

```java
cal.set(2013, Calendar.NOVEMBER, 29, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2013, Calendar.NOVEMBER, 27, 8, 0, 0);
task.set(Tsk.STOP, cal.getTime());
```

*لا تتردد في تعديل التواريخ والمدة لتتناسب مع احتياجات مشروعك المحددة.*

## المشكلات الشائعة والنصائح
- **يجب تعيين خط الأساس قبل تعديل التواريخ.** إذا قمت بتغيير التواريخ أولاً، سيسجل خط الأساس الجدول المعدل بدلاً من الخطة الأصلية.  
- **أشهر التقويم تبدأ من الصفر.** تذكر أن `Calendar.FEBRUARY` يساوي الشهر 1، وليس 2.  
- **وحدات المدة:** `project.getDuration(2)` ينشئ مدة يومين بشكل افتراضي؛ عدّل الوحدة إذا كنت تحتاج ساعات أو أسابيع.

## الخلاصة
من خلال إتقان كيفية **set project start date**، **set task duration**، و **manage project variances**، ستحصل على سيطرة كاملة على جدول مشروعك باستخدام Aspose.Tasks for Java. الخطوات السابقة توفر أساسًا صلبًا يمكنك توسيعه إلى سيناريوهات أكثر تعقيدًا مثل المشاريع متعددة المراحل، تخصيص الموارد، والتقارير الآلية.

## الأسئلة المتكررة
### هل Aspose.Tasks مناسب لجميع احتياجات إدارة المشاريع؟
Aspose.Tasks هي أداة متعددة الاستخدامات مناسبة لمجموعة واسعة من متطلبات إدارة المشاريع، وتوفر مرونة وميزات قوية.

### هل يمكنني دمج Aspose.Tasks في مشروع Java الحالي الخاص بي؟
نعم، يمكنك بسهولة دمج Aspose.Tasks في مشروع Java الخاص بك باتباع الوثائق المتوفرة **[هنا](https://reference.aspose.com/tasks/java/)**.

### هل تتوفر رخصة مؤقتة لـ Aspose.Tasks؟
نعم، يمكنك الحصول على رخصة مؤقتة لـ Aspose.Tasks **[هنا](https://purchase.aspose.com/temporary-license/)**.

### أين يمكنني الحصول على الدعم لـ Aspose.Tasks؟
للحصول على الدعم والمناقشات، زر منتدى Aspose.Tasks **[هنا](https://forum.aspose.com/c/tasks/15)**.

### هل يمكنني تنزيل Aspose.Tasks لـ Java؟
نعم، قم بتنزيل أحدث نسخة من Aspose.Tasks لـ Java **[هنا](https://releases.aspose.com/tasks/java/)**.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**آخر تحديث:** 2026-02-20  
**تم الاختبار مع:** Aspose.Tasks latest Java release  
**المؤلف:** Aspose