---
date: 2026-01-23
description: تعلم كيفية تعيين مدة الخط الأساسي وإنشاء نسخة من المشروع باستخدام Aspose.Tasks
  للغة Java. يساعدك هذا الدليل خطوة بخطوة على إدارة خطوط الأساس للمهام بفعالية.
linktitle: How to Set Baseline Duration in Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: كيفية تعيين مدة الخط الأساسي في Aspose.Tasks للغة Java
url: /ar/java/task-baselines/task-baseline-duration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تعيين مدة الخط الأساسي في Aspose.Tasks للغة Java

## المقدمة
يُعد تعيين الخط الأساسي خطوة أساسية لتتبع تقدم المشروع مقارنةً بالخطة الأصلية. في هذا الدرس ستتعلم **كيفية تعيين مدة الخط الأساسي** للمهام في Microsoft Project باستخدام مكتبة Aspose.Tasks للغة Java، وسترى لماذا يمكن أن يوفر لك إنشاء الخط الأساسي مبكرًا الوقت والجهد لاحقًا.

## إجابات سريعة
- **ماذا يعني “تعيين الخط الأساسي”؟** يقوم بتسجيل تاريخ البدء، تاريخ الانتهاء، والمدة الأصلية للمهمة حتى تتمكن من مقارنة التغييرات المستقبلية.  
- **أي فئة في Aspose.Tasks تُنشئ مشروعًا؟** فئة `Project` – ستتعلم أيضًا كيفية **إنشاء نسخة مشروع** بشكل صحيح.  
- **هل أحتاج إلى ترخيص لتشغيل الكود؟** ترخيص تجريبي مجاني يكفي للاختبار؛ الترخيص التجاري مطلوب للإنتاج.  
- **هل يمكنني استرجاع الخطوط الأساسية المؤقتة؟** نعم، تتيح لك Aspose.Tasks الاستعلام عن الخطوط الأساسية المؤقتة وتكاليفها الثابتة.  
- **ما نسخة Java المطلوبة؟** يُنصح باستخدام Java 8 أو أحدث.

## ما هو الخط الأساسي للمهمة ولماذا يتم تعيينه؟
يُسجل الخط الأساسي للمهمة الجدول الزمني المخطط (تاريخ البدء، تاريخ الانتهاء، والمدة) في نقطة زمنية محددة. من خلال تعيين الخط الأساسي تُنشئ نقطة مرجعية تُسهل اكتشاف انحراف الجدول، تجاوز التكاليف، وإفراط تخصيص الموارد مع تطور المشروع.

## لماذا نستخدم Aspose.Tasks لإدارة الخطوط الأساسية؟
- **توافق كامل مع .mpp** – قراءة وكتابة ملفات Microsoft Project الأصلية دون الحاجة إلى تثبيت Office.  
- **API غني** – الوصول إلى بيانات الخط الأساسي، الخطوط الأساسية المؤقتة، والمعلومات الزمنية برمجيًا.  
- **متعدد المنصات** – يعمل على Windows، Linux، و macOS مع أي JDK قياسي.

## المتطلبات المسبقة
1. **بيئة تطوير Java** – تثبيت وتكوين JDK 8+.  
2. **Aspose.Tasks للغة Java** – تنزيل المكتبة من [هنا](https://releases.aspose.com/tasks/java/).  
3. **IDE أو أداة بناء** – Maven، Gradle، أو أي بيئة تطوير تفضلها.

## استيراد الحزم
أولاً، استورد الفئات الضرورية إلى مشروع Java الخاص بك:

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```

## الخطوة 1: إنشاء نسخة مشروع
إنشاء نسخة مشروع هو الأساس لأي تعديل لاحق. تُظهر هذه الخطوة كيفية **إنشاء نسخة مشروع** باستخدام Aspose.Tasks:

```java
Project project = new Project();
```

## الخطوة 2: إنشاء خط أساسي للمهمة
أضف مهمة جديدة إلى جذر المشروع وقم بتعيين خطها الأساسي. هذا يسجل الجدول الزمني الأصلي للمهمة:

```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## الخطوة 3: عرض معلومات الخط الأساسي للمهمة
استرجع الخط الأساسي الذي أنشأته للتو واطبع خصائصه الرئيسية. يساعدك ذلك على التحقق من أن الخط الأساسي تم تعيينه بشكل صحيح:

```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## الخطوة 4: فحص الخط الأساسي المؤقت والتكلفة الثابتة
إذا كنت تعمل مع خطوط أساسية مؤقتة، يمكنك الاستعلام عما إذا كان الخط الأساسي الحالي مؤقتًا وأية تكلفة ثابتة مرتبطة به:

```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```

## الخطوة 5: طباعة البيانات الزمنية المرحلية
تُظهر البيانات الزمنية المرحلية كيفية توزيع الخط الأساسي على مدار الوقت. قم بالتكرار عبر المجموعة لتفحص كل إدخال:

```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```

باتباع هذه الخطوات، يمكنك **كيفية تعيين مدة الخط الأساسي** لأي مهمة واسترجاع معلومات الخط الأساسي التفصيلية باستخدام Aspose.Tasks للغة Java.

## المشكلات الشائعة والحلول
- **الخط الأساسي لا يظهر في MS Project:** تأكد من أنك استدعيت `project.setBaseline(BaselineType.Baseline)` **بعد** إضافة المهمة.  
- **NullPointerException عند استدعاء `getBaselines()`**: تحقق من أن المهمة أضيفت إلى المشروع قبل تعيين الخط الأساسي.  
- **عدم توافق وحدة الوقت:** استخدم `TimeUnitType` لتنسيق المدة بشكل صحيح، خاصةً عند العمل مع تقاويم مخصصة.

## الأسئلة المتكررة
### ما هو الخط الأساسي للمهمة في MS Project؟
الخط الأساسي للمهمة في MS Project هو لقطة للجدول الزمني المخطط مبدئيًا للمهمة، تشمل تاريخ البدء، تاريخ الانتهاء، والمدة.

### لماذا إدارة الخطوط الأساسية للمهمة مهمة؟
تساعد إدارة الخطوط الأساسية للمهمة في مقارنة الجدول المخطط مع التقدم الفعلي للمشروع، مما يُسهل المتابعة واتخاذ القرار.

### هل يمكن تعديل الخط الأساسي للمهمة بعد تعيينه؟
نعم، يمكنك تعديل الخطوط الأساسية للمهمة في MS Project لتعكس التغييرات في خطة المشروع. ومع ذلك، من الضروري توثيق أي انحرافات عن الخط الأساسي الأصلي.

### هل تدعم Aspose.Tasks وظائف إدارة مشاريع أخرى؟
نعم، توفر Aspose.Tasks مجموعة واسعة من الميزات لإدارة المشاريع، بما في ذلك جدولة المهام، تخصيص الموارد، وإنشاء مخططات جانت.

### أين يمكنني العثور على دعم Aspose.Tasks؟
يمكنك العثور على الدعم في [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15)، حيث يمكنك طرح الأسئلة والتفاعل مع المستخدمين الآخرين.

## أسئلة متكررة إضافية
**س: هل يجب استدعاء `setBaseline` لكل مهمة على حدة؟**  
ج: لا. استدعاء `project.setBaseline(BaselineType.Baseline)` يسجل الخط الأساسي لجميع المهام في المشروع مرة واحدة.

**س: كيف يمكنني تعيين خط أساسي مؤقت لمهمة محددة؟**  
ج: استخدم `project.setBaseline(BaselineType.Baseline1)` (أو Baseline2‑Baseline10) بعد تحديث جدول المهمة.

**س: هل يمكن تصدير بيانات الخط الأساسي إلى CSV؟**  
ج: نعم. قم بالتكرار عبر `task.getBaselines()` واكتب الحقول المطلوبة إلى ملف CSV باستخدام I/O القياسي في Java.

**س: هل يمكنني قراءة ملف .mpp موجود يحتوي بالفعل على خطوط أساسية؟**  
ج: بالتأكيد. حمّل الملف باستخدام `new Project("myproject.mpp")` ثم وصول إلى خطوط الأساس لكل مهمة كما هو موضح أعلاه.

**س: هل تتعامل Aspose.Tasks مع ملفات متعددة المشاريع؟**  
ج: تعمل Aspose.Tasks مع ملفات .mpp لمشروع واحد. بالنسبة لسيناريوهات المشاريع المتعددة، يمكنك دمج المشاريع برمجيًا.

---

**آخر تحديث:** 2026-01-23  
**تم الاختبار مع:** Aspose.Tasks للغة Java 24.12  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}