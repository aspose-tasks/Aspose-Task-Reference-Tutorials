---
date: 2026-02-20
description: تعلم كيفية حساب تباين تكلفة المشروع وإدارة تكاليف المهام في جافا باستخدام
  Aspose.Tasks. اتبع دليلنا خطوة بخطوة لتحديد التكلفة والتحكم في الميزانيات.
linktitle: Manage Task Costs in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: احسب تباين تكلفة المشروع باستخدام Aspose.Tasks للـ Java
url: /ar/java/task-properties/manage-task-cost/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# احسب تباين تكلفة المشروع باستخدام Aspose.Tasks

## المقدمة
في هذا الدرس الشامل ستكتشف **كيفية حساب تباين تكلفة المشروع** وإدارة تكاليف المهام بفعالية داخل تطبيقات Java الخاصة بك باستخدام Aspose.Tasks. سواءً كنت تتبع مشروعًا داخليًا صغيرًا أو تنفيذًا مؤسسيًا واسع النطاق، فإن فهم تباين التكلفة يساعدك على الحفاظ على الميزانيات في مسارها واكتشاف التجاوزات مبكرًا.

## إجابات سريعة
- **ما هو تباين التكلفة؟** الفرق بين التكلفة المخططة (الثابتة) والتكلفة الفعلية (المتبقية).  
- **ما هي طريقة API التي تحدد تكلفة المهمة؟** `task.set(Tsk.COST, BigDecimal.valueOf(...))`.  
- **هل أحتاج إلى ترخيص للتطوير؟** النسخة التجريبية المجانية تكفي للاختبار؛ يلزم ترخيص تجاري للإنتاج.  
- **هل يمكنني استرجاع بيانات تكلفة على مستوى المشروع؟** نعم، عبر الوصول إلى خصائص تكلفة المهمة الجذرية.  
- **ما نسخة Java المدعومة؟** Aspose.Tasks يعمل مع Java 8 وما فوق.

## ما هو “حساب تباين تكلفة المشروع”؟
يعني حساب تباين تكلفة المشروع مقارنة **التكلفة الثابتة** التي خططت لها أصلاً لمهمة أو مشروع مع **التكلفة المتبقية** التي تعكس العمل المتبقي إنجازه. يُظهر التباين ما إذا كنت تحت أو فوق الميزانية، مما يتيح لك إجراء تعديلات استباقية.

## لماذا تستخدم Aspose.Tasks لحساب تباين تكلفة المشروع؟
- **واجهة برمجة تطبيقات Java خالية من .NET** – لا تحتاج إلى مكتبات أصلية.  
- **خصائص غنية لإدارة التكلفة** (`COST`, `FIXED_COST`, `REMAINING_COST`, `COST_VARIANCE`).  
- **تكامل سهل** مع مشاريع Maven/Gradle الحالية.  
- **تقارير دقيقة** يمكن تصديرها إلى ملفات MS Project®.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من وجود ما يلي:

1. **مجموعة تطوير Java (JDK)** – يجب تثبيت Java 8 أو أحدث.  
2. **مكتبة Aspose.Tasks for Java** – قم بتنزيلها من الموقع الرسمي **[here](https://releases.aspose.com/tasks/java/)**.  
3. بيئة تطوير متكاملة أو أداة بناء (IntelliJ, Eclipse, Maven, Gradle) لتجميع وتشغيل الكود النموذجي.

## استيراد الحزم
أضف الفئات المطلوبة من Aspose.Tasks إلى ملف مصدر Java الخاص بك لتتمكن من العمل مع المشاريع والمهام.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.math.BigDecimal;
// Import Aspose.Tasks classes
```

## دليل خطوة بخطوة

### الخطوة 1: إعداد مشروعك
أولاً، أنشئ كائن `Project` جديد وحدد المجلد الذي قد تخزن فيه الملفات المُولدة.

```java
// Set the path to your document directory
String dataDir = "Your Document Directory";
// Create a new project
Project project = new Project();
```

### الخطوة 2: إضافة مهمة جديدة
أضف مهمة تحت المهمة الجذرية. هنا سنقوم بتعيين التكاليف.

```java
// Add a new task to the root task
Task task = project.getRootTask().getChildren().add("Task");
```

### الخطوة 3: تعيين تكلفة المهمة – **كيفية تعيين التكلفة**
عيّن تكلفة مخططة للمهمة. في سيناريو واقعي قد تأتي هذه القيمة من جدول ميزانية.

```java
// Set the task cost to 800
task.set(Tsk.COST, BigDecimal.valueOf(800));
```

### الخطوة 4: استرجاع وعرض معلومات التكلفة – **كيفية إدارة التكاليف**
الآن سنقرأ الخصائص المختلفة للتكلفة، بما في ذلك تباين التكلفة المحسوب.

```java
// Retrieve and print task information
System.out.println("Remaining Cost: " + task.get(Tsk.REMAINING_COST));
System.out.println("Fixed Cost: " + task.get(Tsk.FIXED_COST));
System.out.println("Cost Variance: " + task.get(Tsk.COST_VARIANCE));
// Retrieve and print project-level cost information
System.out.println("Project Cost: " + project.getRootTask().get(Tsk.COST));
System.out.println("Project Fixed Cost: " + project.getRootTask().get(Tsk.FIXED_COST));
System.out.println("Project Remaining Cost: " + project.getRootTask().get(Tsk.REMAINING_COST));
System.out.println("Project Cost Variance: " + project.getRootTask().get(Tsk.COST_VARIANCE));
```

**ما ستراه:**  
- `Remaining Cost` يعكس العمل الذي لم يُستكمل بعد.  
- `Fixed Cost` هو الأساس الذي حددته (800 في هذا المثال).  
- `Cost Variance` يتم حسابه تلقائيًا كـ **Fixed – Remaining**.  
- القيم نفسها متاحة على مستوى المشروع (المهمة الجذرية)، مما يتيح لك **حساب تباين تكلفة المشروع** عبر جميع المهام.

### الخطوة 5: تكرار للمهام الإضافية (اختياري)
إذا كان مشروعك يحتوي على عدة مراحل، كرر الخطوات 2‑4 لكل مهمة. جمع التباينات الفردية يمنحك تباين تكلفة المشروع الكلي.

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|---------|-------|------|
| `NullPointerException` عند الوصول إلى خصائص المهمة | لم تتم إضافة المهمة إلى هيكل المشروع. | تأكد من استدعاء `project.getRootTask().getChildren().add(...)` قبل تعيين التكاليف. |
| قيمة التكلفة تظهر كـ `0` | استخدام `int` بدلاً من `BigDecimal`. | استخدم دائمًا `BigDecimal.valueOf(...)` كما هو موضح. |
| تباين غير متوقع (سلبي) | `REMAINING_COST` يتجاوز `FIXED_COST`. | تحقق من تحديث التكلفة المتبقية مع تقدم العمل. |

## الأسئلة المتكررة

**س: أين يمكنني العثور على وثائق Aspose.Tasks for Java؟**  
ج: يمكنك الوصول إلى الوثائق **[here](https://reference.aspose.com/tasks/java/)**.

**س: كيف يمكنني تنزيل مكتبة Aspose.Tasks for Java؟**  
ج: قم بتنزيل المكتبة **[here](https://releases.aspose.com/tasks/java/)**.

**س: أين يمكنني شراء Aspose.Tasks for Java؟**  
ج: يمكنك شراؤها **[here](https://purchase.aspose.com/buy)**.

**س: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Tasks for Java؟**  
ج: نعم، يمكنك الحصول على نسخة تجريبية مجانية **[here](https://releases.aspose.com/)**.

**س: أين يمكنني طلب الدعم لـ Aspose.Tasks for Java؟**  
ج: زر منتدى الدعم **[here](https://forum.aspose.com/c/tasks/15)**.

---

**آخر تحديث:** 2026-02-20  
**تم الاختبار مع:** Aspose.Tasks for Java 24.12 (أحدث نسخة وقت الكتابة)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}