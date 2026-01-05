---
date: 2026-01-05
description: تعلم كيفية تعيين تاريخ بدء المشروع وحفظ ملف XML الخاص بـ MS Project باستخدام
  Aspose.Tasks للغة Java. دليل خطوة بخطوة لمطوري Java.
linktitle: Add Extended Attributes to Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: تعيين تاريخ بدء المشروع باستخدام Aspose.Tasks للغة Java
url: /ar/java/resource-assignments/add-extended-attributes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تعيين تاريخ بدء المشروع باستخدام Aspose.Tasks للغة Java

## مقدمة
في هذا البرنامج التعليمي ستتعلم **كيفية تعيين تاريخ بدء المشروع** في ملف Microsoft Project ثم **حفظ ملف XML الخاص بـ MS Project** باستخدام مكتبة Aspose.Tasks للغة Java. سواءً كنت تقوم بأتمتة خط أنابيب التقارير أو بناء أداة إدارة مشاريع مخصصة، فإن إتقان هذه المهمة سيوفر لك الوقت ويقضي على الأخطاء اليدوية.

## إجابات سريعة
- **ما هي الطريقة الأساسية لتعيين تاريخ البدء؟** استخدم `project.set(Prj.START_DATE, …)`.
- **أي تنسيق يجب أن أستخدمه لتصدير الملف؟** احفظه كـ XML باستخدام `SaveFileFormat.Xml`.
- **هل أحتاج إلى ترخيص لهذه العملية؟** النسخة التجريبية تعمل، لكن الترخيص الكامل يزيل العلامات المائية.
- **هل يمكنني تغيير تاريخ البدء بعد إنشاء المهام؟** نعم، قم بتحديث خاصية المشروع قبل إضافة المهام.
- **هل هذا متوافق مع جميع إصدارات MS Project؟** Aspose.Tasks يدعم XML و MPP والمزيد.

## ما هو “تعيين تاريخ بدء المشروع”؟
تعيين تاريخ بدء المشروع يحدد التقويم الأساسي الذي تبدأ منه جميع حسابات جدولة المهام. إنها الخطوة الأولى في بناء جدول مشروع موثوق برمجيًا.

## لماذا نستخدم Aspose.Tasks للغة Java؟
Aspose.Tasks توفر واجهة برمجة تطبيقات pure‑Java تعمل على أي منصة دون الحاجة إلى تثبيت Microsoft Project. تتيح لك إنشاء وتعديل وتصدير بيانات المشروع بسرعة، مما يجعلها مثالية لأتمتة الخادم.

## المتطلبات المسبقة
1. **Java Development Kit (JDK)** – أي نسخة حديثة من JDK.
2. **Aspose.Tasks للغة Java** – تحميل من [here](https://releases.aspose.com/tasks/java/).
3. **IDE** – IntelliJ IDEA أو Eclipse أو بيئة التطوير المتكاملة المفضلة لديك.

## استيراد الحزم
First, import the necessary classes:

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Value;
import java.io.IOException;
import java.math.BigDecimal;
```

### الخطوة 1: إعداد دليل البيانات
Define where the generated files will be stored.

```java
String dataDir = "Your Data Directory";
```

### الخطوة 2: إنشاء كائن مشروع
Instantiate a new, empty project.

```java
Project project = new Project();
```

### الخطوة 3: تعيين خصائص معلومات المشروع
Here we **set the project start date** and related schedule properties.

```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

### الخطوة 4: حفظ ملف XML الخاص بـ MS Project
Export the configured project to an XML file.

```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## المشكلات الشائعة والحلول
- **تنسيق التاريخ غير صحيح:** تأكد من استخدام `java.util.Calendar` واستدعاء `getTime()` قبل التعيين.
- **الملف غير محفوظ:** تحقق من أن `dataDir` يشير إلى مجلد موجود ويمكن الكتابة فيه.
- **تحذيرات الترخيص:** النسخة التجريبية تضيف علامات مائية؛ قم بتطبيق ترخيص صالح لإزالتها.

## Frequently Asked Questions

### س: هل يمكنني استخدام Aspose.Tasks للغة Java لقراءة ملفات MS Project؟  
**ج:** نعم، Aspose.Tasks للغة Java توفر وظائف قوية للقراءة والكتابة لملفات MS Project.

### س: هل Aspose.Tasks للغة Java متوافق مع إصدارات مختلفة من MS Project؟  
**ج:** بالتأكيد، Aspose.Tasks للغة Java يدعم صيغ MS Project المتنوعة، مما يضمن توافقًا واسعًا.

### س: هل هناك أي قيود على النسخة التجريبية من Aspose.Tasks للغة Java؟  
**ج:** النسخة التجريبية تسمح لك باستكشاف المكتبة لكنها تضيف علامات مائية إلى ملفات الإخراج.

### س: كيف يمكنني الحصول على دعم لـ Aspose.Tasks للغة Java؟  
**ج:** يمكنك طلب المساعدة من منتدى مجتمع Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

### س: هل يمكنني شراء ترخيص مؤقت لـ Aspose.Tasks للغة Java؟  
**ج:** نعم، الترخيصات المؤقتة متاحة للاستخدام قصير الأمد. احصل على واحدة من [here](https://purchase.aspose.com/temporary-license/).

### س: هل حفظ الملف كـ XML يحافظ على الحقول المخصصة؟  
**ج:** نعم، عند الحفظ باستخدام `SaveFileFormat.Xml`، يتم الاحتفاظ بجميع السمات المخصصة والحقول الموسعة.

### س: هل يمكنني تغيير تاريخ البدء بعد إضافة المهام؟  
**ج:** يمكنك تحديث تاريخ البدء في أي وقت قبل الحفظ؛ فقط استدعِ `project.set(Prj.START_DATE, …)` مرة أخرى.

---

**آخر تحديث:** 2026-01-05  
**تم الاختبار باستخدام:** Aspose.Tasks for Java 24.12  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}