---
date: 2026-09-25
description: تعلم كيفية استرجاع رموز العملة من ملفات MS Project باستخدام Aspose.Tasks
  for Java – الطريقة السريعة للحصول على رمز العملة الذي يحتاجه مطورو Java.
keywords:
- retrieve currency code java
- Aspose.Tasks Java
- MS Project currency
- read MS Project file
lastmod: 2026-09-25
linktitle: إدارة رموز العملة في Aspose.Tasks
og_description: استرجاع رمز العملة java من ملفات MS Project باستخدام Aspose.Tasks.
  يوضح هذا الدليل كيفية قراءة المشروع، استخراج معرف العملة ISO، وتطبيقه في تطبيقات
  Java.
og_image_alt: Screenshot of Java code extracting currency code from an MS Project
  file using Aspose.Tasks
og_title: استرجاع رمز العملة java من MS Project
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to retrieve currency codes from MS Project files using Aspose.Tasks
    for Java – the quick way to get currency code Java developers need.
  headline: Retrieve currency code java from MS Project with Aspose.Tasks
  type: TechArticle
- description: Learn how to retrieve currency codes from MS Project files using Aspose.Tasks
    for Java – the quick way to get currency code Java developers need.
  name: Retrieve currency code java from MS Project with Aspose.Tasks
  steps:
  - name: set up data directory
    text: Define the folder that contains your *.mpp* file. Adjust the path to match
      your environment so the runtime can locate the project file.
  - name: load the project file
    text: The `Project` class is Aspose.Tasks' top‑level object that represents a
      single MS Project file in memory. Creating an instance reads the file and builds
      an in‑memory model you can query.
  - name: retrieve currency code
    text: The `Prj.CURRENCY_CODE` constant identifies the property that stores the
      ISO currency identifier. Calling `prj.get(Prj.CURRENCY_CODE)` returns the three‑letter
      code in a single operation. The output will be the three‑letter ISO currency
      code (e.g., `USD`, `EUR`, `GBP`) that the project is configured
  - name: how to retrieve currency code in Java (additional context)
    text: Load your project, call `prj.get(Prj.CURRENCY_CODE)`, and store the result
      in a `String`. You can then pass this value to any financial service, reporting
      engine, or UI component that requires a currency identifier.
  - name: (optional) use the currency code
    text: 'Typical downstream scenarios include: - **Report generation** – prepend
      the code to cost columns (`USD 1,200`). - **API integration** – send the ISO
      code to payment gateways that demand a currency parameter. - **Data consolidation**
      – group multiple projects by currency for portfolio‑level analysis.'
  type: HowTo
- questions:
  - answer: Yes, the API reads multi‑level task hierarchies, resource pools, custom
      fields, and calendars without limitation.
    question: Can Aspose.Tasks handle complex project structures?
  - answer: Absolutely. It supports MPP, XML, XER, and other formats from Project
      98 through the latest Office releases.
    question: Is Aspose.Tasks compatible with different versions of MS Project files?
  - answer: Comprehensive API reference, code examples, and dedicated technical support
      are available on the Aspose website.
    question: Does Aspose.Tasks provide documentation and support?
  - answer: A free trial is offered so you can evaluate all features, including currency
      code extraction.
    question: Can I try Aspose.Tasks before purchasing?
  - answer: Temporary licenses are available from the [website](https://purchase.aspose.com/temporary-license/).
    question: Where can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- retrieve currency
- Aspose.Tasks
- Java project automation
- MS Project
title: استرجاع رمز العملة java من MS Project باستخدام Aspose.Tasks
url: /ar/java/currency/currency-codes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# استرجاع رمز العملة java من MS Project باستخدام Aspose.Tasks

## مقدمة
في هذا الدرس ستتعلم **كيفية استرجاع رمز العملة java** من ملف MS Project باستخدام Aspose.Tasks Java API. سواء كنت بحاجة إلى إنشاء تقارير مالية متعددة العملات، أو دمج المشاريع عبر مناطق مختلفة، أو ببساطة عرض الرمز النقدي الصحيح في نظام لاحق، فإن الخطوات أدناه ستأخذك من إعداد البيئة إلى استدعاء سطر واحد يُعيد معرف العملة ISO. بنهاية الدليل ستكون قادرًا على تحميل أي تنسيق ملف Project مدعوم واستخراج رمز العملة المكوّن من ثلاثة أحرف مثل `USD`، `EUR`، أو `GBP`.

## إجابات سريعة
- **ما الذي تفعله API؟** تقرأ ملفات MS Project وتكشف عن خصائص مثل رمز العملة.  
- **ما اللغة المستخدمة؟** Java، عبر مكتبة Aspose.Tasks for Java.  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تعمل للتطوير؛ يتطلب الترخيص التجاري للإنتاج.  
- **هل يمكنني استرجاع الرمز في سطر واحد؟** نعم—`prj.get(Prj.CURRENCY_CODE)` يُعيد سلسلة رمز العملة فورًا.  
- **هل هو متوافق مع جميع إصدارات Project؟** Aspose.Tasks يدعم أكثر من 20 تنسيق إدخال، بما في ذلك MPP القديم، XML، وملفات XER.

## ما هو قراءة ملف MS Project؟
قراءة ملف MS Project تعني فتحه برمجيًا (مثل *.mpp* أو أي تنسيق مدعوم آخر مثل XML أو XER) والوصول إلى هياكله الداخلية. تشمل هذه الهياكل المهام، الموارد، التقويمات، جداول التكاليف والإعدادات المالية. من خلال تحليل الملف يمكنك استخراج المعلومات دون تشغيل Microsoft Project، مما يتيح تقارير آلية، وهجرة، وتكامل سير العمل.

## لماذا نستخدم Aspose.Tasks لقراءة ملفات msproject؟
توفر Aspose.Tasks حلاً نقيًا للـ Java يزيل الحاجة إلى التفاعل مع COM أو تثبيت Microsoft Project محليًا. تدعم أكثر من 20 تنسيق ملف، يمكنها التعامل مع مشاريع تحتوي على آلاف المهام مع استهلاك أقل من 100 ميغابايت من الذاكرة، وتقدم نموذج كائن غني. الوصول المباشر إلى الثوابت مثل `Prj.CURRENCY_CODE` يتيح لك استرجاع معلومات العملة فورًا وبشكل موثوق.

## المتطلبات المسبقة
قبل الغوص في الشيفرة، تأكد من وجود ما يلي:

### مجموعة تطوير Java (JDK) مثبتة
يتطلب JDK حديث (الإصدار 11 أو أحدث). قم بتنزيله من الموقع الرسمي لـ Oracle: [هنا](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### مكتبة Aspose.Tasks للـ Java
احصل على أحدث ملفات Aspose.Tasks للـ Java وأضفها إلى مسار الفئات (classpath) لمشروعك. الوثائق الكاملة وروابط التحميل متاحة [هنا](https://reference.aspose.com/tasks/java/).

## استيراد الحزم
فئة `Project` وثوابت `Prj` موجودة في مساحة الاسم `com.aspose.tasks`. استوردها في أعلى ملف مصدر Java الخاص بك:

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## دليل خطوة بخطوة

### الخطوة 1: إعداد دليل البيانات
حدد المجلد الذي يحتوي على ملف *.mpp* الخاص بك. عدل المسار ليتطابق مع بيئتك حتى يتمكن وقت التشغيل من العثور على ملف المشروع.

```java
String dataDir = "Your Data Directory";
```

### الخطوة 2: تحميل ملف المشروع
فئة `Project` هي الكائن الأعلى مستوى في Aspose.Tasks الذي يمثل ملف MS Project واحد في الذاكرة. إنشاء نسخة يقرأ الملف ويبني نموذجًا في الذاكرة يمكنك الاستعلام عنه.

```java
Project prj = new Project(dataDir + "project.mpp");
```

### الخطوة 3: استرجاع رمز العملة
الثابت `Prj.CURRENCY_CODE` يحدد الخاصية التي تخزن معرف العملة ISO. استدعاء `prj.get(Prj.CURRENCY_CODE)` يُعيد الرمز المكوّن من ثلاثة أحرف في عملية واحدة.

```java
System.out.println(prj.get(Prj.CURRENCY_CODE));
```
سيكون الناتج هو رمز العملة ISO المكوّن من ثلاثة أحرف (مثال: `USD`، `EUR`، `GBP`) الذي تم تكوين المشروع لاستخدامه.

### الخطوة 4: كيفية استرجاع رمز العملة في Java (سياق إضافي)
حمّل مشروعك، استدعِ `prj.get(Prj.CURRENCY_CODE)`، وخزن النتيجة في `String`. يمكنك بعد ذلك تمرير هذه القيمة إلى أي خدمة مالية، محرك تقارير، أو مكوّن واجهة مستخدم يتطلب معرف عملة.

### الخطوة 5: (اختياري) استخدام رمز العملة
السيناريوهات النموذجية تشمل:

- **إنشاء التقارير** – أضف الرمز قبل أعمدة التكلفة (`USD 1,200`).  
- **تكامل API** – أرسل رمز ISO إلى بوابات الدفع التي تتطلب معلمة العملة.  
- **تجميع البيانات** – جمع مشاريع متعددة حسب العملة لتحليل على مستوى الحافظة.

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|--------|-----|
| **إخراج فارغ** | ملف المشروع لا يحدد عملة (القيمة الافتراضية فارغة). | قم بتعيين العملة في Microsoft Project أو اضبطها عبر `prj.set(Prj.CURRENCY_CODE, "USD");` قبل القراءة. |
| **الملف غير موجود** | مسار `dataDir` غير صحيح. | تحقق من المسار وتأكد من أن اسم الملف يطابق تمامًا، بما في ذلك حساسية الأحرف. |
| **إصدار ملف غير مدعوم** | ملف *.mpp* قديم جدًا أو معطوب. | قم بالترقية إلى أحدث نسخة من Aspose.Tasks أو حوّل الملف إلى تنسيق أحدث في Microsoft Project أولاً. |

## الأسئلة المتكررة

**Q: هل يمكن لـ Aspose.Tasks التعامل مع هياكل مشروع معقدة؟**  
A: نعم، تقوم API بقراءة هياكل مهام متعددة المستويات، مجموعات الموارد، الحقول المخصصة، والتقويمات دون أي قيود.

**Q: هل Aspose.Tasks متوافق مع إصدارات مختلفة من ملفات MS Project؟**  
A: بالتأكيد. يدعم MPP، XML، XER، وغيرها من التنسيقات من Project 98 حتى أحدث إصدارات Office.

**Q: هل توفر Aspose.Tasks وثائق ودعم؟**  
A: مرجع API شامل، أمثلة على الشيفرة، ودعم فني مخصص متاح على موقع Aspose.

**Q: هل يمكنني تجربة Aspose.Tasks قبل الشراء؟**  
A: تتوفر نسخة تجريبية مجانية لتقييم جميع الميزات، بما في ذلك استخراج رمز العملة.

**Q: أين يمكنني الحصول على ترخيص مؤقت للتقييم؟**  
A: التراخيص المؤقتة متاحة من [الموقع](https://purchase.aspose.com/temporary-license/).

---

**آخر تحديث:** 2026-09-25  
**تم الاختبار مع:** Aspose.Tasks for Java (latest version)  
**المؤلف:** Aspose

## دروس ذات صلة

- [خصائص المشروع Java – قراءة البيانات الوصفية باستخدام Aspose.Tasks](/tasks/java/project-properties/)
- [كيفية قراءة معلومات المشروع من Microsoft Project باستخدام Aspose.Tasks للـ Java](/tasks/java/project-properties/read-project-info/)
- [استرجاع رموز المخطط التفصيلي لـ MS Project في Aspose.Tasks](/tasks/java/project-file-operations/retrieve-outline-codes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}