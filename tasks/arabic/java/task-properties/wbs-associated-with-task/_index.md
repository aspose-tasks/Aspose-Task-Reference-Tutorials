---
date: 2026-03-03
description: تعلم كيفية إعادة ترقيم WBS في Aspose.Tasks للـ Java، وإدارة تقسيم العمل
  وتخصيص رموز WBS بفعالية مع أمثلة خطوة بخطوة.
linktitle: WBS Associated with Task in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: كيفية إعادة ترقيم WBS في Aspose.Tasks للـ Java
url: /ar/java/task-properties/wbs-associated-with-task/
weight: 36
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إعادة ترقيم WBS في Aspose.Tasks للـ Java

## مقدمة
إذا كنت بحاجة إلى **كيفية إعادة ترقيم WBS** في ملف Microsoft Project باستخدام Aspose.Tasks للـ Java، فأنت في المكان الصحيح. يشرح هذا الدليل كيفية قراءة رموز WBS الحالية، وتخصيصها، ثم إعادة ترقيم الهيكل الهرمي بحيث يبقى مشروعك منظمًا. سواءً كنت تقوم بتنظيف جدول زمني قديم أو بناء جدول جديد من الصفر، فإن إتقان هذه الخطوات سيساعدك على **إدارة تقسيم العمل** بثقة.

## إجابات سريعة
- **ماذا يفعل إعادة ترقيم WBS؟** يعيد حساب الترقيم الهرمي للمهام ليعكس أي تغييرات هيكلية.  
- **أي فئة تقوم بإعادة الترميز؟** `Project.renumberWBSCode`.  
- **هل أحتاج إلى ترخيص لتشغيل الكود؟** يلزم وجود ترخيص Aspose.Tasks صالح للاستخدام في بيئة الإنتاج.  
- **هل يمكنني تخصيص تنسيق WBS؟** نعم—استخدم `Task.set(Tsk.WBS, "...")` لتعيين أي سلسلة نصية تريدها.  
- **ما هي المتطلبات الأساسية؟** Java JDK، مكتبة Aspose.Tasks للـ Java، وملف مشروع صالح (.mpp).

## ما هو هيكل تقسيم العمل (WBS)؟
هيكل تقسيم العمل (WBS) هو تمثيل هرمي لمخرجات المشروع ومهامه. يحصل كل مهمة على رمز (مثال: 1.2.3) يعكس موقعها في الهرم. يصبح إعادة الترميز ضروريًا عندما تُضاف أو تُحذف أو تُعاد ترتيب المهام، لضمان بقاء الرموز منطقية وسهلة القراءة.

## لماذا إدارة تقسيم العمل وتخصيص رموز WBS؟
- **الوضوح:** تجعل رموز WBS الواضحة من السهل على أصحاب المصلحة العثور على المهام.  
- **التقارير:** تعتمد العديد من أدوات التقارير على ترقيم متسق.  
- **المرونة:** تسمح الرموز المخصصة لك بمواءمة هيكل المشروع مع المعايير الداخلية.  

## المتطلبات الأساسية
قبل الغوص في الكود، تأكد من أن لديك ما يلي:

- Java Development Kit (JDK) مثبت على جهازك.  
- مكتبة Aspose.Tasks للـ Java مضافة إلى مشروعك. يمكنك الحصول عليها من [هنا](https://releases.aspose.com/tasks/java/).  

## استيراد الحزم
تأكد من استيراد الحزم اللازمة لبدء مشروعك:

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.ArrayList;
import java.util.List;
```

## قراءة رموز WBS
أولاً، سنقرأ رموز WBS الحالية حتى تتمكن من رؤية ما تتعامل معه.

### الخطوة 1: تحميل المشروع
```java
Project project = new Project("Your Document Directory" + "input.mpp");
```

### الخطوة 2: جمع المهام
```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```

### الخطوة 3: التحليل والتخصيص
```java
for (Task tsk : collector.getTasks()) {
    System.out.println(tsk.get(Tsk.WBS));
    System.out.println(tsk.get(Tsk.WBS_LEVEL));
    tsk.set(Tsk.WBS, "custom wbs");
}
```

المقتطف أعلاه يطبع WBS الحالي ومستوى كل مهمة، ثم يوضح **تخصيص رموز WBS** عن طريق تعيين سلسلة جديدة.

## إعادة ترقيم رموز WBS للمهام
الآن دعنا نعيد ترقيم هيكل WBS فعليًا.

### الخطوة 1: تحميل المشروع (مثال إعادة الترميز)
```java
Project project = new Project("Your Document Directory" + "RenumberExample.mpp");
```

### الخطوة 2: تحديد جميع المهام
```java
List<Task> tasks = (List<Task>) project.getRootTask().selectAllChildTasks();
```

### الخطوة 3: إخراج رموز WBS الأولية
```java
System.out.println("WBS codes before: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```

### الخطوة 4: إعادة ترقيم رموز WBS
```java
List<Integer> listIds = new ArrayList<>();
listIds.add(1);
listIds.add(2);
listIds.add(3);
project.renumberWBSCode(listIds);
```

### الخطوة 5: إخراج رموز WBS المحدثة
```java
System.out.println("\nWBS codes after: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```

باتباع هذه الخطوات، ستتمكن بفعالية من **إعادة ترقيم WBS** لأي مجموعة من المهام في ملف مشروعك.

## المشكلات الشائعة والحلول
- **WBS لا يتغير بعد استدعاء `set`:** تأكد من أنك تعمل على نسخة المهمة الصحيحة وأن المشروع يتم حفظه بعد التعديلات.  
- **`renumberWBSCode` يطرح استثناءً:** تحقق من أن قائمة المعرفات تتطابق مع عدد المهام ذات المستوى الأعلى؛ وإلا لن يتمكن الأسلوب من تعيين الأرقام الجديدة بشكل صحيح.  
- **قيمة WBS مفقودة:** قد تحتوي بعض المهام على قيمة `null` لـ WBS إذا تم استيرادها من ملف لم يحدد واحدة. استخدم قيمة بديلة قبل الطباعة.  

## الأسئلة المتكررة

**س: أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Tasks للـ Java؟**  
ج: الوثائق متاحة [هنا](https://reference.aspose.com/tasks/java/).

**س: كيف يمكنني تحميل Aspose.Tasks للـ Java؟**  
ج: يمكنك تحميله [هنا](https://releases.aspose.com/tasks/java/).

**س: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Tasks للـ Java؟**  
ج: نعم، يمكنك الحصول على نسخة تجريبية مجانية [هنا](https://releases.aspose.com/).

**س: أين يمكنني الحصول على الدعم لـ Aspose.Tasks للـ Java؟**  
ج: زر [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15) للحصول على الدعم.

**س: هل يمكنني الحصول على ترخيص مؤقت لـ Aspose.Tasks للـ Java؟**  
ج: نعم، احصل على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

**س: هل يمكنني إعادة تسمية تنسيق WBS بعد إعادة الترميز؟**  
ج: بالتأكيد. بعد استدعاء `renumberWBSCode`، يمكنك التجول عبر المهام وتطبيق `task.set(Tsk.WBS, "NewFormat-" + task.get(Tsk.WBS))` لتتناسب مع تسمياتك.

**س: هل تؤثر إعادة الترميز على تبعيات المهام؟**  
ج: لا. الطريقة تقوم فقط بتحديث سلسلة WBS؛ روابط المهام والقيود تظل دون تغيير.

---

**آخر تحديث:** 2026-03-03  
**تم الاختبار مع:** Aspose.Tasks للـ Java 24.12 (الأحدث)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}