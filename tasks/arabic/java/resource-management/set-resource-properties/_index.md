---
date: 2026-01-18
description: تعلم كيفية تعيين السعر القياسي وغيرها من خصائص الموارد في MS Project
  باستخدام Aspose.Tasks للغة Java، بما في ذلك كيفية إضافة موارد إلى MS Project وإدارة
  الموارد بكفاءة.
linktitle: Set Resource Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: كيفية تعيين السعر القياسي للموارد في Aspose.Tasks
url: /ar/java/resource-management/set-resource-properties/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تعيين السعر القياسي للموارد في Aspose.Tasks

## مقدمة
إذا كنت تبني تطبيقات Java تحتاج إلى التفاعل مع ملفات Microsoft Project، فإن **setting the standard rate** لمورد هو أحد أكثر المهام شيوعًا. في هذا البرنامج التعليمي ستتعلم كيفية **set standard rate** وغيرها من خصائص الموارد باستخدام Aspose.Tasks for Java. بنهاية الدليل ستكون قادرًا على إنشاء كائن مشروع، إضافة مورد إلى ملف MS Project، وإدارة موارد MS Project بثقة.

## إجابات سريعة
- **ما هو الصنف الأساسي للعمل مع ملف Project؟** `Project`
- **أي طريقة تضيف موردًا جديدًا؟** `project.getResources().add()`
- **كيف تقوم بتعيين السعر القياسي؟** `rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(...))`
- **هل أحتاج إلى ترخيص للإنتاج؟** نعم، يلزم وجود ترخيص Aspose.Tasks صالح.
- **أي نسخة من Java مدعومة؟** Java 8+ (يوصى بأحدث JDK).

## ما هو “set standard rate”؟
عملية *set standard rate* تعين تكلفة ساعة افتراضية للمورد. يستخدم مديرو المشاريع هذه القيمة لحساب تكاليف العمالة، إنشاء تقارير التكلفة، وتوقع الميزانيات.

## لماذا تعيين الأسعار باستخدام Aspose.Tasks؟
- **لا حاجة لتثبيت Microsoft Project** – تعديل الملفات مباشرةً من Java.
- **دقة كاملة** – جميع حقول الموارد، بما في ذلك العمل الإضافي وأسعار التكلفة، تُحافظ عليها.
- **متعدد المنصات** – يعمل على Windows وLinux وmacOS.
- **صديق للأتمتة** – مثالي للمعالجة الدفعية أو التكامل مع خطوط أنابيب CI.

## المتطلبات المسبقة
قبل البدء، تأكد من أن لديك ما يلي:

### إعداد بيئة تطوير Java
1. تثبيت JDK: تأكد من أن لديك Java Development Kit (JDK) مثبتًا على نظامك. يمكنك تنزيله من [موقع Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. إعداد IDE: اختر بيئة تطوير متكاملة (IDE) مثل IntelliJ IDEA أو Eclipse أو NetBeans وقم بإعدادها على جهازك.

### تثبيت Aspose.Tasks for Java
1. تنزيل Aspose.Tasks for Java: انتقل إلى [صفحة التنزيل](https://releases.aspose.com/tasks/java/) واحصل على أحدث نسخة من Aspose.Tasks for Java.
2. دمج مع المشروع: أدمج مكتبة Aspose.Tasks for Java في مشروع Java الخاص بك عن طريق إضافتها كاعتماد.

## استيراد الحزم
للبدء، تحتاج إلى استيراد الحزم الضرورية من Aspose.Tasks for Java إلى مشروعك. هذه الخطوة تضمن حصولك على الوظائف المطلوبة.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import java.math.BigDecimal;
```

## الخطوة 1: إنشاء كائن Project
إنشاء **project object** هو الخطوة الأولى لأي تعديل على MS Project. يمثل الملف الكامل للمشروع في الذاكرة.

```java
Project project = new Project();
```

## الخطوة 2: إضافة مورد (add resource ms project)
الآن سنقوم **add resource MS Project** باستخدام مجموعة Resources. يمكن أن يكون اسم المورد أي شيء منطقي لجدولك.

```java
Resource rsc = project.getResources().add("Rsc");
```

## الخطوة 3: تعيين خصائص المورد (how to set rates)
هنا نقوم **set standard rate** وأيضًا نوضح كيفية تعيين معدل العمل الإضافي. تُخزن هذه المعدلات كقيم `BigDecimal` للحفاظ على الدقة.

```java
// Set standard rate for the resource
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(15));
// Set overtime rate for the resource
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(20));
```

## المشكلات الشائعة والحلول
| المشكلة | لماذا يحدث | الحل |
|---------|------------|------|
| `NullPointerException` عند استدعاء `set` | لم يتم إضافة المورد بشكل صحيح. | تأكد من أن `project.getResources().add()` يُعيد `Resource` غير فارغ (non‑null). |
| المعدلات تظهر كـ 0 في الملف المحفوظ | استخدام `int` بدلاً من `BigDecimal`. | استخدم دائمًا `BigDecimal.valueOf()` للقيم المالية. |
| لم يتم العثور على الترخيص | ملف الترخيص لم يتم تحميله قبل إنشاء `Project`. | حمّل الترخيص (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`) في بداية البرنامج. |

## الخلاصة
باتباع هذه الخطوات، تعلمت كيفية **create a project object**، **add a resource MS Project**، و**set standard rate** بالإضافة إلى خصائص أخرى للمورد. يتيح لك ذلك أتمتة حسابات التكلفة، إنشاء تقارير مخصصة، وإدارة موارد MS Project بالكامل من Java.

## الأسئلة المتكررة
### هل يمكن لـ Aspose.Tasks for Java التعامل مع ملفات MS Project المعقدة؟
نعم، Aspose.Tasks for Java قادر على التعامل مع مجموعة واسعة من صيغ ملفات MS Project، بما في ذلك الملفات المعقدة ذات التسلسلات الهرمية الواسعة للمهام.

### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Tasks for Java؟
نعم، يمكنك الوصول إلى نسخة تجريبية مجانية من Aspose.Tasks for Java من [هنا](https://releases.aspose.com/).

### أين يمكنني العثور على الدعم لـ Aspose.Tasks for Java؟
يمكنك طلب المساعدة والمشاركة في المناقشات المتعلقة بـ Aspose.Tasks for Java على [منتدى الدعم](https://forum.aspose.com/c/tasks/15).

### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Tasks for Java؟
يمكنك الحصول على ترخيص مؤقت من [صفحة الترخيص المؤقت](https://purchase.aspose.com/temporary-license/) لأغراض التقييم.

### أين يمكنني شراء نسخة مرخصة من Aspose.Tasks for Java؟
يمكنك شراء نسخة مرخصة من Aspose.Tasks for Java من [صفحة الشراء](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-18  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose