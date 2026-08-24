---
date: 2026-08-24
description: تعلم كيفية إضافة مورد ms project، وتعيين السعر القياسي وخصائص المورد
  الأخرى في MS Project باستخدام Aspose.Tasks for Java، وإدارة الموارد بكفاءة.
keywords:
- add resource ms project
- set resource rate
- manage ms project resources
- create ms project file
lastmod: 2026-08-24
linktitle: تعيين خصائص المورد في Aspose.Tasks
og_description: إضافة مورد ms project وتعيين السعر القياسي باستخدام Aspose.Tasks for
  Java. تعلم المتطلبات المسبقة، والكود خطوة بخطوة، وحلول المشكلات في هذا الدليل المختصر.
og_image_alt: Screenshot of Aspose.Tasks Java code setting resource rates
og_title: إضافة مورد ms project وتعيين السعر باستخدام Aspose.Tasks (Java)
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to add resource ms project, set standard rate and other resource
    properties in MS Project using Aspose.Tasks for Java, and manage resources efficiently.
  headline: How to add resource ms project with Aspose.Tasks
  type: TechArticle
- description: Learn how to add resource ms project, set standard rate and other resource
    properties in MS Project using Aspose.Tasks for Java, and manage resources efficiently.
  name: How to add resource ms project with Aspose.Tasks
  steps:
  - name: Install JDK 8 or newer. You can download it from the [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
    text: Install JDK 8 or newer. You can download it from the [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
  - name: Choose an IDE such as IntelliJ IDEA, Eclipse, or NetBeans and configure
      it for Java development.
    text: Choose an IDE such as IntelliJ IDEA, Eclipse, or NetBeans and configure
      it for Java development.
  - name: Download the latest Aspose.Tasks for Java package from the [download page](https://releases.aspose.com/tasks/java/).
    text: Download the latest Aspose.Tasks for Java package from the [download page](https://releases.aspose.com/tasks/java/).
  - name: Add the JAR files to your project’s classpath or declare the Maven/Gradle
      dependency as shown in the product documentation.
    text: Add the JAR files to your project’s classpath or declare the Maven/Gradle
      dependency as shown in the product documentation.
  type: HowTo
- questions:
  - answer: Yes, it supports all major Project formats, including large files with
      thousands of tasks and resources, preserving every field without data loss.
    question: Can Aspose.Tasks for Java handle complex MS Project files?
  - answer: Yes, you can access a free trial of Aspose.Tasks for Java from the [Aspose.Tasks
      free trial page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: You can seek assistance on the [support forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I get support for Aspose.Tasks for Java?
  - answer: A temporary license is available from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for evaluation?
  - answer: Purchase a full license from the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase a licensed version?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose tasks
- java project automation
- ms project resources
- resource rate
title: كيفية إضافة مورد ms project باستخدام Aspose.Tasks
url: /ar/java/resource-management/set-resource-properties/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة مورد ms project وتعيين السعر في Aspose.Tasks

## مقدمة
إذا كنت تطور تطبيقات Java تحتاج إلى قراءة أو كتابة ملفات Microsoft Project، فإن **إضافة مورد ms project** وتكوين سعره القياسي هو إجراء روتيني ولكنه أساسي. في هذا الدليل ستتعرف على كيفية إنشاء كائن `Project`، إضافة مورد، وتعيين كل من السعر القياسي وسعر العمل الإضافي باستخدام Aspose.Tasks لـ Java. في النهاية ستتمكن من أتمتة حسابات التكلفة والحفاظ على جداول مشروعك محدثة دون الحاجة إلى تثبيت Microsoft Project.

## إجابات سريعة
- **ما هو الصنف الذي يمثل ملف Project؟** `Project`
- **ما هو الاستدعاء الذي يضيف موردًا جديدًا؟** `project.getResources().add()`
- **كيف تقوم بتعيين السعر القياسي؟** `rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(...))`
- **هل يلزم وجود ترخيص للاستخدام في الإنتاج؟** نعم، يجب تحميل ترخيص Aspose.Tasks صالح.
- **ما إصدارات Java المدعومة؟** Java 8 وما بعدها (يوصى بـ Java 17+).

## ما هو “set standard rate”؟
عملية *set standard rate* تعين تكلفة ساعية افتراضية للمورد. يُستخدم هذا السعر من قبل مديري المشاريع لحساب نفقات العمالة، إنشاء تقارير التكلفة، وتوقع الميزانيات، مما يضمن أن حسابات التكلفة تعكس السعر المتوقع للعمل الذي يقوم به كل مورد طوال دورة حياة المشروع.

## لماذا يتم تعيين الأسعار باستخدام Aspose.Tasks؟
يمكن لـ Aspose.Tasks معالجة **أكثر من 50 صيغة إدخال وإخراج**، بما في ذلك ملفات MPP، MPX، XML، وPrimavera، ويتعامل مع مشاريع مئات الصفحات دون تحميل الملف بالكامل إلى الذاكرة. يتيح ذلك معالجة دفعات عالية السرعة على خوادم Windows أو Linux أو macOS، مما يقلل الجهد اليدوي بنسبة تصل إلى 90 % في سيناريوهات الأتمتة النموذجية.

## المتطلبات المسبقة
قبل البدء، تأكد من جاهزية العناصر التالية:

### إعداد بيئة تطوير Java
1. ثبت JDK 8 أو أحدث. يمكنك تنزيله من [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. اختر بيئة تطوير متكاملة (IDE) مثل IntelliJ IDEA أو Eclipse أو NetBeans وقم بإعدادها لتطوير Java.

### تثبيت Aspose.Tasks لـ Java
1. حمّل أحدث حزمة Aspose.Tasks لـ Java من [download page](https://releases.aspose.com/tasks/java/).  
2. أضف ملفات JAR إلى مسار الفئة (classpath) في مشروعك أو أعلن عن تبعية Maven/Gradle كما هو موضح في وثائق المنتج.

## استيراد الحزم
استورد الفئات الأساسية من Aspose.Tasks التي ستحتاجها. يتيح لك هذا الوصول إلى الأنواع `Project` و`Resource` و`Rsc` المستخدمة لاحقًا.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import java.math.BigDecimal;
```

## الخطوة 1: إنشاء كائن مشروع
الصنف `Project` هو الكائن الأعلى مستوى الذي يمثل ملف MS Project كامل في الذاكرة. إنشاءه ينتج مشروعًا فارغًا يمكنك ملؤه بالمهام والموارد والبيانات الأخرى.

```java
Project project = new Project();
```

## الخطوة 2: إضافة مورد (add resource ms project)
الصنف `Resource` يمثل موردًا واحدًا في المشروع مثل شخص أو جهاز أو مادة. إضافة مورد عبر `project.getResources().add()` تُعيد كائن `Resource` غير فارغ جاهز لتكوين الخصائص.

```java
Resource rsc = project.getResources().add("Rsc");
```

## الخطوة 3: تعيين خصائص المورد (how to set rates)
تحتوي تعداد `Rsc` على ثوابت لحقول المورد مثل `STANDARD_RATE` و`OVERTIME_RATE`.  
تُعيّن السعر القياسي وسعر العمل الإضافي عن طريق استدعاء `set` على كائن `Resource` مع قيم تعداد `Rsc` المناسبة. تُخزن الأسعار كـ `BigDecimal` للحفاظ على الدقة المالية.

```java
// Set standard rate for the resource
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(15));
// Set overtime rate for the resource
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(20));
```

## المشكلات الشائعة والحلول
| المشكلة | سبب حدوثها | الحل |
|-------|----------------|-----|
| `NullPointerException` عند استدعاء `set` | لم يتم إضافة المورد بشكل صحيح. | تأكد من أن `project.getResources().add()` يعيد كائن `Resource` غير فارغ. |
| تظهر الأسعار كـ 0 في الملف المحفوظ | استخدام `int` بدلاً من `BigDecimal`. | استخدم دائمًا `BigDecimal.valueOf()` للقيم المالية. |
| لم يتم العثور على الترخيص | ملف الترخيص لم يتم تحميله قبل إنشاء `Project`. | حمّل الترخيص (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`) عند بدء البرنامج. |

## الخلاصة
أنت الآن تعرف كيفية **إضافة مورد ms project**، إنشاء كائن `Project`، و**تعيين السعر القياسي وسعر العمل الإضافي** باستخدام Aspose.Tasks لـ Java. تتيح لك هذه القدرة أتمتة حسابات التكلفة، إنشاء تقارير مخصصة، وإدارة موارد MS Project بالكامل من أي تطبيق Java.

## الأسئلة المتكررة
**س: هل يمكن لـ Aspose.Tasks لـ Java التعامل مع ملفات MS Project المعقدة؟**  
ج: نعم، يدعم جميع صيغ Project الرئيسية، بما في ذلك الملفات الكبيرة التي تحتوي على آلاف المهام والموارد، مع الحفاظ على كل حقل دون فقدان البيانات.

**س: هل هناك نسخة تجريبية مجانية متاحة؟**  
ج: نعم، يمكنك الوصول إلى نسخة تجريبية مجانية من Aspose.Tasks لـ Java من خلال [Aspose.Tasks free trial page](https://releases.aspose.com/).

**س: أين يمكنني الحصول على الدعم لـ Aspose.Tasks لـ Java؟**  
ج: يمكنك طلب المساعدة في [support forum](https://forum.aspose.com/c/tasks/15).

**س: كيف أحصل على ترخيص مؤقت للتقييم؟**  
ج: الترخيص المؤقت متاح عبر [temporary license page](https://purchase.aspose.com/temporary-license/).

**س: أين يمكنني شراء نسخة مرخصة؟**  
ج: اشترِ ترخيصًا كاملًا من خلال [purchase page](https://purchase.aspose.com/buy).

---

**آخر تحديث:** 2026-08-24  
**تم الاختبار مع:** Aspose.Tasks لـ Java 24.12 (أحدث نسخة وقت الكتابة)  
**المؤلف:** Aspose

## دروس ذات صلة

- [كيفية إنشاء الموارد – إدارة الموارد باستخدام Aspose.Tasks لـ Java](/tasks/java/resource-management/)
- [إضافة مورد إلى المشروع باستخدام Aspose.Tasks لـ Java](/tasks/java/resource-management/create-resources/)
- [كيفية إضافة مورد إلى المشروع ومعالجة خصائص تأخير التسوية في Aspose.Tasks](/tasks/java/resource-assignments/leveling-delay-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}