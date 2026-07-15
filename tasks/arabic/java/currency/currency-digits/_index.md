---
date: 2026-02-10
description: تعلم كيفية الحصول على قيم العملات، قراءة ملف MS Project وتحويل ملف المشروع
  إلى Java باستخدام Aspose.Tasks. دليل خطوة بخطوة لاستخراج أرقام العملات.
linktitle: How to Get Currency from MS Project using Aspose.Tasks
second_title: Aspose.Tasks Java API
title: كيفية الحصول على العملة من MS Project باستخدام Aspose.Tasks
url: /ar/java/currency/currency-digits/
weight: 11
---

 with same markdown structure.

Let's assemble.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية الحصول على العملة من MS Project باستخدام Aspose.Tasks

## Introduction
إذا كنت تتساءل **كيف تحصل على معلومات العملة** من ملف Microsoft Project، فقد وصلت إلى المكان الصحيح. في هذا الدرس الشامل ستكتشف **كيفية التعامل مع قيم عملة ms project** باستخدام مكتبة Aspose.Tasks للغة Java. سواء كنت تبني أداة تقارير، أو أداة ترحيل، أو تحتاج ببساطة إلى قراءة إعدادات العملة من **ملف مشروع java**، فإن هذا الدليل يمر بك عبر كل خطوة—من تحميل ملف *.mpp* إلى استخراج أرقام العملة. في النهاية، ستكون مرتاحًا في التعامل مع بيانات عملة ms project في تطبيقاتك الخاصة.

## Quick Answers
- **ما المكتبة التي تقرأ ملفات MS Project؟** Aspose.Tasks for Java.  
- **كم عدد أسطر الكود للحصول على أرقام العملة؟** ثلاثة أسطر مختصرة فقط بعد تحميل المشروع.  
- **هل أحتاج إلى ترخيص للتطوير؟** النسخة التجريبية المجانية تعمل للاختبار؛ يلزم ترخيص تجاري للإنتاج.  
- **ما نسخة Java المدعومة؟** Java 8 أو أعلى (أي JDK يدعم Aspose.Tasks).  
- **هل يمكنني استرجاع خصائص مشروع أخرى؟** نعم – Aspose.Tasks تعرض مجموعة كاملة من حقول المشروع (مثل تاريخ البدء، أسعار التكلفة، إلخ).

## What is ms project currency?
`ms project currency` تشير إلى الدقة الرقمية (عدد المنازل العشرية) التي يستخدمها Microsoft Project عند عرض القيم المالية. يتم تخزينها في ملف المشروع كخاصية **CURRENCY_DIGITS** وتحدد ما إذا كانت القيم تظهر كأعداد صحيحة، أو منزل عشرية واحدة، أو منزلتين عشريتين، إلخ.

## Why use Aspose.Tasks for handling ms project currency?
- **لا يلزم تثبيت Microsoft Project** – العمل مباشرةً مع ملفات *.mpp* على أي منصة تدعم Java.  
- **أمان نوع قوي** – تُعيد الـ API قيمًا ذات نوع قوي، مما يقلل من أخطاء التحليل.  
- **محسّن للأداء** – تحميل المشاريع الكبيرة بسرعة واستخراج الحقول التي تحتاجها فقط.  
- **متعدد المنصات** – تشغيل على Windows أو Linux أو macOS دون تعديل.

## Prerequisites
قبل أن تبدأ، تأكد من توفر ما يلي:

1. **بيئة تطوير Java** – JDK 8 أو أحدث مثبتة ومُكوَّنة.  
2. **Aspose.Tasks for Java** – قم بتحميل أحدث ملف JAR من الموقع الرسمي: [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).  
3. **معرفة أساسية بـ Java** – يجب أن تكون مرتاحًا لإنشاء مشروع Java، وإضافة المكتبات الخارجية، وتشغيل طريقة `main`.

## Import Packages
أولاً، استورد الفئات التي سنحتاجها.  
```java
import java.io.IOException;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Step 1: Define Data Directory
حدد المجلد الذي يحتوي على **ملف مشروع java** الخاص بك (`*.mpp`).  
```java
String dataDir = "Your Data Directory";
```
استبدل `"Your Data Directory"` بالمسار المطلق أو النسبي حيث يوجد `project.mpp`.

## Step 2: Load the MPP File  
الآن سنرى **كيفية تحميل ملفات mpp** باستخدام Aspose.Tasks.  
```java
Project project = new Project(dataDir + "project.mpp");
```
تأكد من أن اسم الملف يطابق تمامًا؛ وإلا سيتم إلقاء استثناء `IOException`.

## Step 3: Retrieve Currency Digits  
مع تحميل المشروع، استخراج أرقام **عملة ms project** هو سطر واحد:  
```java
System.out.println(project.get(Prj.CURRENCY_DIGITS));
```
تُعيد الدالة قيمة `Integer` تمثل عدد المنازل العشرية (مثال، `2` للسنات). يتم طباعة القيمة إلى وحدة التحكم، لكن يمكنك أيضًا تخزينها في متغير لمعالجة إضافية.

## Common Issues & Tips
- **الملف غير موجود** – تحقق مرة أخرى من مسار `dataDir` وتأكد من صحة اسم الملف، بما في ذلك امتداد `.mpp`.  
- **إصدار ملف غير مدعوم** – Aspose.Tasks يدعم صيغ Project من 2000 إلى 2024؛ قد تحتاج الملفات الأقدم أو التالفة إلى تحويل.  
- **لم يتم تعيين الترخيص** – أثناء التطوير النسخة التجريبية تعمل، لكن للإنتاج يجب تطبيق ترخيص صالح لتجنب علامات مائية للتقييم.

## Frequently Asked Questions

**س: هل يمكن لـ Aspose.Tasks التعامل مع سمات مشروع أخرى غير أرقام العملة؟**  
**ج:** نعم، Aspose.Tasks تقدم مجموعة واسعة من الوظائف للتعامل مع جوانب مختلفة من ملفات المشروع، مثل المهام، والموارد، والحقول المخصصة.

**س: هل Aspose.Tasks مناسبة لتطبيقات على مستوى المؤسسات؟**  
**ج:** بالتأكيد، تم تصميم Aspose.Tasks لتلبية متطلبات المشاريع على مستوى المؤسسات، مع توفير أداء عالي وقابلية توسع.

**س: هل يدعم Aspose.Tasks التطوير متعدد المنصات؟**  
**ج:** نعم، يمكنك استخدام Aspose.Tasks للغة Java على أي منصة تدعم بيئة تشغيل Java (Windows، Linux، macOS).

**س: هل يمكنني تجربة Aspose.Tasks قبل الشراء؟**  
**ج:** نعم، يمكنك تحميل نسخة تجريبية مجانية من [هنا](https://releases.aspose.com/).

**س: أين يمكنني الحصول على الدعم لـ Aspose.Tasks؟**  
**ج:** يمكنك العثور على الدعم في [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

## Conclusion
أنت الآن تعرف **كيفية الحصول على أرقام العملة** من ملف MS Project باستخدام Aspose.Tasks للغة Java. العملية بسيطة: قم بتحميل المشروع، استدعِ `project.get(Prj.CURRENCY_DIGITS)`، واستخدم النتيجة في تطبيقك. لا تتردد في استكشاف خصائص مشروع أخرى بنفس النمط، ودمج هذه المنطق في حلول تقارير أو ترحيل أكبر.

---

**آخر تحديث:** 2026-02-10  
**تم الاختبار مع:** Aspose.Tasks for Java (latest at time of writing)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}