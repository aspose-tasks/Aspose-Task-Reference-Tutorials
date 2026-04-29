---
date: 2026-01-18
description: تعلم كيفية إنشاء قائمة مهام في Java وإضافة مهمة إلى Microsoft Project،
  وتعيين خط أساس دون استخدام MS Project باستخدام Aspose.Tasks.
linktitle: Creating a Task Baseline in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: إنشاء قائمة مهام Java – خط أساس مشروع MS باستخدام Aspose.Tasks
url: /ar/java/task-baselines/create-task-baseline/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء قائمة مهام Java – خط أساس مشروع MS باستخدام Aspose.Tasks

## المقدمة
في هذا البرنامج التعليمي، ستقوم **بإنشاء قائمة مهام Java** عن طريق إنشاء خط أساس لمهام Microsoft Project باستخدام Aspose.Tasks for Java. يتيح لك Aspose.Tasks العمل مع ملفات Project دون الحاجة إلى تثبيت Microsoft Project، بحيث يمكنك **إضافة مهمة إلى Microsoft Project**، تعديل الموارد، وحتى **تعيين خط أساس دون MS Project**—كل ذلك من خلال شفرة Java الصافية.

## إجابات سريعة
- **ماذا يفعل Aspose.Tasks؟** يوفر واجهة برمجة تطبيقات Java لإنشاء وقراءة وتحرير ملفات Microsoft Project دون الحاجة إلى MS Project.  
- **هل أحتاج إلى تثبيت Microsoft Project؟** لا، Aspose.Tasks يعمل بشكل مستقل.  
- **ما نسخة Java المطلوبة؟** JDK 8 أو أعلى.  
- **هل يمكنني تعيين خط أساس لمهمة واحدة؟** نعم، استخدم `setBaseline` مع قائمة مهام.  
- **هل تحتاج إلى ترخيص للإنتاج؟** نعم، الترخيص التجاري يزيل حدود التقييم.

## ما هو خط أساس المهمة؟
يسجل خط أساس المهمة القيم الأصلية المخططة للبداية، والانتهاء، والعمل للمهمة. وهو يعمل كنقطة مرجعية لمقارنة التقدم الفعلي مع الخطة الأصلية.

## لماذا تستخدم Aspose.Tasks لإنشاء قائمة مهام Java؟
- **عدم الاعتماد على MS Project** – مثالي لأتمتة الخادم.  
- **تحكم كامل** في المهام والموارد والتقويمات عبر شفرة Java.  
- **توافق عبر الإصدارات** مع ملفات Project من 2007 إلى 2024.

## المتطلبات المسبقة
1. **مجموعة تطوير Java (JDK)** – قم بتثبيت JDK 8 أو أحدث.  
2. **Aspose.Tasks for Java** – قم بتنزيل المكتبة من [رابط التحميل](https://releases.aspose.com/tasks/java/).  

## استيراد الحزم
لبدء العمل مع Aspose.Tasks في مشروع Java الخاص بك، استورد الحزم اللازمة:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## الخطوة 1: إنشاء كائن Project
```java
Project project = new Project();
```
هنا نقوم بإنشاء كائن `Project` جديد – يمثل ملف MS Project الذي سيحتوي على قائمة المهام الخاصة بنا.

## الخطوة 2: إضافة مهمة إلى المشروع
```java
Task task = project.getRootTask().getChildren().add("Task");
```
باستخدام `getRootTask()` نصل إلى جذر هيكل المشروع ونقوم **بإضافة مهمة إلى Microsoft Project**. السلسلة `"Task"` هي اسم المهمة؛ يمكنك استبدالها بأي وصف تحتاجه.

## الخطوة 3: تعيين خط أساس للمهام المحددة
```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
لـ **تعيين خط أساس دون MS Project**، أنشئ قائمة بالمهام التي تريد إنشاء خط أساس لها (هنا `myList`) ومررها إلى `setBaseline`. قم بملء `myList` بالمهام التي أضفتها إذا كنت تحتاج إلى خط أساس انتقائي فقط.

## الخطوة 4: تعيين خط أساس للمشروع بأكمله
```java
project.setBaseline(BaselineType.Baseline);
```
إذا كنت تفضل إنشاء خط أساس للمشروع بالكامل في استدعاء واحد، فقط استدعِ `setBaseline` مع `BaselineType` المطلوب.

## كيفية إضافة مهمة إلى Microsoft Project باستخدام Aspose.Tasks
بخلاف المهمة الواحدة المعروضة أعلاه، يمكنك إضافة مهام متعددة، مهام فرعية، وتعيين الموارد. كل استدعاء لـ `add()` يُعيد كائن `Task` يمكنك تكوينه أكثر (المدة، تاريخ البدء، إلخ).

## كيفية تعيين خط أساس دون MS Project
يتيح Aspose.Tasks إنشاء خط أساس بالكامل عبر الشفرة. يمكنك تعيين أنواع مختلفة من الخط الأساسي (Baseline, Baseline1‑Baseline10) عن طريق تغيير تعداد `BaselineType`، مما يسمح لك بتتبع عدة إصدارات من الخط الأساسي دون الحاجة إلى فتح MS Project.

## المشكلات الشائعة والحلول
- **عدم ظهور الخط الأساسي:** تأكد من استدعاء `project.save("output.mpp")` بعد تعيين الخط الأساسي (تم حذف خطوة الحفظ هنا للتبسيط).  
- **قائمة المهام تظهر فارغة:** تحقق من أنك تضيف المهام إلى الوالد الصحيح (`getRootTask()` أو مهمة فرعية).  
- **أخطاء عدم تطابق الإصدارات:** استخدم أحدث ملف JAR لـ Aspose.Tasks لضمان التوافق مع صيغ .mpp الأحدث.

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Tasks for Java دون تثبيت Microsoft Project؟**  
ج: نعم، Aspose.Tasks يعمل بشكل مستقل ولا يتطلب Microsoft Project على الجهاز المضيف.

**س: هل Aspose.Tasks for Java متوافق مع إصدارات مختلفة من Microsoft Project؟**  
ج: بالتأكيد. المكتبة تدعم ملفات Project من 2007 حتى أحدث إصدارات 2024.

**س: هل يمكنني تعديل موارد المشروع باستخدام Aspose.Tasks for Java؟**  
ج: نعم، يمكنك إضافة وتحديث وحذف الموارد برمجيًا، تمامًا مثل المهام.

**س: هل يدعم Aspose.Tasks for Java تعيين تبعيات المهام؟**  
ج: نعم، يمكنك تعريف علاقات السلف‑اللاحق باستخدام فئة `TaskLink`.

**س: هل يتوفر دعم فني لـ Aspose.Tasks for Java؟**  
ج: نعم، يمكنك الحصول على المساعدة عبر [منتدى الدعم](https://forum.aspose.com/c/tasks/15)، حيث يرد فريق Aspose والمجتمع على الاستفسارات.

## الخلاصة
باتباع هذه الخطوات، تعلمت كيفية **إنشاء قائمة مهام Java**، **إضافة مهمة إلى Microsoft Project**، و**تعيين خط أساس دون MS Project** باستخدام Aspose.Tasks. يسهّل هذا النهج أتمتة المشاريع، يلغي الحاجة إلى تثبيت Project على سطح المكتب، ويمنحك تحكمًا برمجيًا كاملاً في بيانات مشروعك.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**آخر تحديث:** 2026-01-18  
**تم الاختبار باستخدام:** Aspose.Tasks for Java 24.12  
**المؤلف:** Aspose  

---