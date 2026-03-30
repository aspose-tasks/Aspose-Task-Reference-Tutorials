---
date: 2026-02-28
description: تعلم كيفية الحصول على المدة بالدقائق، الأيام، الساعات، الأسابيع، والشهور
  باستخدام Aspose.Tasks للغة Java. دليل مفصل مع أمثلة على الشيفرة.
linktitle: Task Duration in Different Units with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: كيفية الحصول على المدة بوحدات مختلفة باستخدام Aspose.Tasks
url: /ar/java/task-properties/task-duration-different-units/
weight: 32
---

.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية الحصول على المدة بوحدات مختلفة باستخدام Aspose.Tasks

## المقدمة
فهم **كيفية الحصول على المدة** للمهام هو جزء أساسي من أي سير عمل لإدارة المشاريع. سواء كنت تحتاج الدقائق لتتبع دقيق أو الشهور للتخطيط على مستوى عالٍ، تجعل Aspose.Tasks for Java عملية التحويل بسيطة. في هذا الدليل سنرشدك إلى استخراج مدة المهمة بالدقائق، الأيام، الساعات، الأسابيع، والشهور، مع شرح لماذا قد تكون كل وحدة مفيدة في المشاريع الواقعية.

## إجابات سريعة
- **ماذا يعني “كيفية الحصول على المدة”؟** هو عملية استخراج فترة زمنية للمهمة وتحويلها إلى الوحدة التي تحتاجها.  
- **أي طريقة API تقوم بالتحويل؟** `Task.get(Tsk.DURATION).convert(TimeUnitType.<Unit>)`.  
- **هل أحتاج إلى ترخيص لتشغيل الكود؟** نسخة تجريبية مجانية تكفي للاختبار؛ الترخيص التجاري مطلوب للإنتاج.  
- **هل يمكنني التحويل إلى وحدات مخصصة؟** يمكنك سلاسل التحويلات أو استخدام `TimeSpan` للحسابات المخصصة.  
- **هل الكود متوافق مع Java 17؟** نعم، Aspose.Tasks يدعم Java 8 والإصدارات الأحدث.

## ما هو “كيفية الحصول على المدة” في Aspose.Tasks؟
تخزن Aspose.Tasks طول المهمة ككائن `Duration`. من خلال استدعاء طريقة `convert` وتحديد `TimeUnitType` (Minute, Hour, Day, Week, Month)، يمكنك استرجاع القيمة نفسها معبرًا عنها بالوحدة المطلوبة. هذه المرونة تتيح لك إنشاء تقارير، إجراء حسابات، أو تغذية بيانات إلى أنظمة أخرى دون الحاجة إلى حسابات يدوية.

## لماذا نستخدم Aspose.Tasks لتحويل المدة؟
- **الدقة:** يتعامل مع استثناءات التقويم، وقت العمل، والتقويمات غير القياسية تلقائيًا.  
- **الأداء:** تحويل بسطر واحد يتجنب الحلقات أو التحليل المخصص.  
- **القابلية للنقل:** يعمل بنفس الطريقة عبر بيئات Windows، Linux، و macOS.  
- **التكامل:** يندمج بسلاسة في تطبيقات Java الحالية التي تستخدم Aspose.Tasks.

## المتطلبات المسبقة
قبل الغوص في الكود، تأكد من وجود:

- مجموعة تطوير جافا (JDK) مثبتة  
- مكتبة Aspose.Tasks for Java. يمكنك تنزيلها [هنا](https://releases.aspose.com/tasks/java/)  
- فهم أساسي لبرمجة Java

## استيراد الحزم
في مشروع Java الخاص بك، أدرج مكتبة Aspose.Tasks. أضف بيان الاستيراد التالي في بداية الكود:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## الخطوة 1: إعداد المشروع
أنشئ مشروع Java جديد في بيئتك المفضلة (IntelliJ, Eclipse, VS Code, إلخ) وأضف ملف JAR الخاص بـ Aspose.Tasks إلى مسار الفئة (classpath). هذا يضمن توفر الفئات المذكورة أعلاه وقت التجميع.

## الخطوة 2: قراءة قالب المشروع
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Read MS Project template file
String fileName = dataDir + "project.xml";
// Read the input file as Project
Project project = new Project(fileName);
```

استبدل `"Your Document Directory"` بالمجلد الفعلي الذي يحتوي على ملف المشروع `.xml` أو `.mpp`.

## الخطوة 3: استرجاع مهمة
```java
// Get a task to calculate its duration in different formats
Task task = project.getRootTask().getChildren().getById(1);
```

استدعاء `getById(1)` يجلب المهمة التي معرفها 1. عدّل المعرف لاستهداف مهمة مختلفة في ملفك.

## الخطوة 4: المدة بالدقائق – كيفية الحصول على المدة بالدقائق؟
```java
// Get the duration in Minutes
double mins = task.get(Tsk.DURATION).convert(TimeUnitType.Minute).toDouble();
```

المتغير `mins` الآن يحمل طول المهمة معبرًا عنه بالدقائق.

## الخطوة 5: المدة بالأيام – كيفية الحصول على المدة بالأيام؟
```java
// Get the duration in Days
double days = task.get(Tsk.DURATION).convert(TimeUnitType.Day).toDouble();
```

استخدم هذه القيمة عندما تحتاج إلى دقة على مستوى اليوم للتقارير أو تخصيص الموارد.

## الخطوة 6: المدة بالساعات – كيفية الحصول على المدة بالساعات؟
```java
// Get the duration in Hours
double hours = task.get(Tsk.DURATION).convert(TimeUnitType.Hour).toDouble();
```

الساعات مفيدة لسجلات الوقت أو عندما تريد تقسيم اليوم إلى نوبات عمل.

## الخطوة 7: المدة بالأسابيع – كيفية الحصول على المدة بالأسابيع؟
```java
// Get the duration in Weeks
double weeks = task.get(Tsk.DURATION).convert(TimeUnitType.Week).toDouble();
```

الأسابيع غالبًا ما تُستخدم في مخططات جانت عالية المستوى أو تخطيط المعالم.

## الخطوة 8: المدة بالشهور – كيفية الحصول على المدة بالشهور؟
```java
// Get the duration in Months
double months = task.get(Tsk.DURATION).convert(TimeUnitType.Month).toDouble();
```

المدة على مستوى الشهور تساعد عندما تقوم بمواءمة مراحل المشروع مع الفترات المالية.

## المشكلات الشائعة والحلول
| العَرَض | السبب المحتمل | الحل |
|---------|--------------|-----|
| `NullPointerException` على `task` | معرف مهمة غير صحيح أو عدم وجود أبناء | تحقق من وجود معرف المهمة باستخدام `project.getRootTask().getChildren()` |
| قيم غير متوقعة (مثل 0) | المشروع يستخدم تقويمًا مخصصًا بأيام غير عمل | تأكد من تعريف تقويم المشروع بشكل صحيح أو استخدم `project.getCalendar()` لفحصه |
| التحويل يُرجع أسابيع ككسر | الأسابيع تُحسب بناءً على طول الأسبوع الافتراضي للمشروع (عادة 5 أيام) | اضرب في 5 إذا كنت تحتاج أسابيع تقويمية، أو عدّل إعدادات التقويم |

## الأسئلة المتكررة
### س: هل يمكنني استخدام Aspose.Tasks for Java مع أي بيئة تطوير Java؟
ج: نعم، Aspose.Tasks for Java متوافق مع أي بيئة تطوير متكاملة (IDE) للغة Java.

### س: كيف يمكنني الحصول على معرف المهمة في ملف Microsoft Project؟
ج: يمكنك فحص ملف المشروع يدويًا أو استدعاء `project.getRootTask().getChildren()` والتكرار عبر المجموعة لقراءة `ID` لكل مهمة.

### س: هل Aspose.Tasks مناسب للتعامل مع مشاريع واسعة النطاق؟
ج: بالتأكيد. تم تصميم Aspose.Tasks لمعالجة المشاريع التي تحتوي على آلاف المهام والموارد بكفاءة.

### س: أين يمكنني العثور على مزيد من الوثائق؟
ج: زر [الوثائق](https://reference.aspose.com/tasks/java/) للحصول على مراجع API شاملة، عينات كود، ودلائل أفضل الممارسات.

### س: هل يمكنني تجربة Aspose.Tasks for Java قبل الشراء؟
ج: نعم، يمكنك استكشاف [نسخة تجريبية مجانية](https://releases.aspose.com/) لتقييم إمكانياتها.

---

**آخر تحديث:** 2026-02-28  
**تم الاختبار مع:** Aspose.Tasks for Java 24.12  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}