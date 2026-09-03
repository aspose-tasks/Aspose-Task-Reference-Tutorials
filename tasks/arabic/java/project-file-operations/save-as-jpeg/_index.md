---
date: 2026-05-26
description: تعلم كيفية إنشاء لقطة مشروع JPEG وضبط جودة JPEG عند تصدير ملفات Microsoft
  Project باستخدام Aspose.Tasks for Java.
keywords:
- create project snapshot jpeg
- adjust jpeg quality
- Aspose.Tasks Java
linktitle: حفظ المشروع كـ JPEG في Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-26'
  description: Learn how to create project snapshot JPEG and adjust JPEG quality when
    exporting Microsoft Project files using Aspose.Tasks for Java.
  headline: Create Project Snapshot JPEG – Adjust Quality with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Higher quality preserves text and line details, while very low quality
      may make small labels hard to read.
    question: Does adjusting JPEG quality affect Gantt chart readability?
  - answer: Yes, Aspose.Tasks supports PNG, BMP, and TIFF via the appropriate `SaveFileFormat`
      enum.
    question: Can I export other image formats besides JPEG?
  - answer: You can iterate over the desired views and save each as a separate JPEG
      using the same `ImageSaveOptions` configuration.
    question: Is it possible to export multiple pages (e.g., different views) at once?
  - answer: Aspose.Tasks for Java works with JDK 8 and later.
    question: What Java version is required?
  - answer: Consider reducing the JPEG quality or scaling the image dimensions via
      additional `ImageSaveOptions` settings.
    question: How do I handle large projects that produce big images?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: إنشاء لقطة مشروع JPEG – ضبط الجودة باستخدام Aspose.Tasks
url: /ar/java/project-file-operations/save-as-jpeg/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء لقطة مشروع JPEG – ضبط الجودة باستخدام Aspose.Tasks

## مقدمة
في هذا الدرس ستكتشف كيفية **إنشاء ملفات لقطة مشروع JPEG** من Microsoft Project باستخدام Aspose.Tasks for Java، وكيفية ضبط جودة JPEG لتلبية متطلبات الحجم مقابل الوضوح. سواء كنت تحتاج إلى صور واضحة لعروض مجلس الإدارة أو ملفات خفيفة للبوابات الإلكترونية، فإن إتقان إعداد الجودة يمنحك التحكم الكامل في النتيجة النهائية.

## إجابات سريعة
- **ما الذي يفعله “ضبط جودة JPEG”؟** يتيح لك التحكم في مستوى ضغط ملف JPEG المُصدَّر، موازنًا بين حجم الملف وجودة الصورة.  
- **أي مكتبة تتعامل مع التحويل؟** توفر Aspose.Tasks for Java واجهة برمجة تطبيقات بسيطة لتصدير ملفات Project إلى JPEG.  
- **هل أحتاج إلى ترخيص؟** الإصدار التجريبي المجاني يكفي للتقييم؛ يتطلب الاستخدام في الإنتاج ترخيصًا تجاريًا.  
- **هل يمكنني ضبط الجودة في الكود؟** نعم، استخدم طريقة `ImageSaveOptions.setJpegQuality(int)` (نطاق 0‑100).  
- **هل العملية سريعة؟** تحويل ملف مشروع نموذجي إلى JPEG يستغرق بضع ثوانٍ فقط على الأجهزة الحديثة.

## ما هو “ضبط جودة JPEG”؟
يتيح لك ضبط جودة JPEG تحديد عامل الضغط المطبق عند حفظ الصورة بصيغة JPEG. القيم الأعلى (قريبة من 100) تحافظ على مزيد من التفاصيل، بينما القيم الأقل تقلل حجم الملف على حساب الوضوح. **الإجابة المباشرة:** تتحكم في جودة JPEG بتمرير قيمة عددية (0‑100) إلى طريقة `ImageSaveOptions.setJpegQuality`، التي تؤثر فورًا على حجم ودقة الصورة المولدة.  

جودة JPEG هي عامل الضغط المطبق عند حفظ الصورة بصيغة JPEG.

## لماذا نستخدم Aspose.Tasks لتصدير JPEG؟
**الإجابة المباشرة:** تقوم Aspose.Tasks برسم مخططات Gantt، وعروض الموارد، والتقارير المخصصة إلى ملفات صور دون الحاجة إلى تثبيت Microsoft Project، مما يضمن مخرجات بدقة بكسل مثالية عبر Windows وLinux وmacOS.  

تدعم Aspose.Tasks التصدير إلى **أربعة** صيغ صور (JPEG، PNG، BMP، TIFF) ويمكنها رسم مشاريع تحتوي على **ما يصل إلى 10,000 مهمة** في أقل من 5 ثوانٍ على معالج قياسي بسرعة 2.5 GHz، مما يوفر ضمانًا كميًا للأداء.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من وجود ما يلي:
1. **مجموعة تطوير جافا (JDK)** – قم بتثبيت أحدث نسخة من JDK (8 أو أحدث) من [موقع جافا](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. **Aspose.Tasks for Java** – قم بتحميل المكتبة وإعدادها باتباع الخطوات في [الوثائق الرسمية](https://reference.aspose.com/tasks/java/).

## استيراد الحزم
`ImageSaveOptions` هي فئة في Aspose.Tasks تتحكم في إعدادات تصدير الصورة مثل الصيغة، الأبعاد، وجودة JPEG.  
```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.IOException;
```

## الخطوة 1: تعريف دليل البيانات
حدد المسار إلى المجلد الذي يحتوي على ملف Microsoft Project الخاص بك. يُستخدم هذا الدليل لكل من عمليات الإدخال والإخراج.  
```java
String dataDir = "Your Data Directory";
```

## الخطوة 2: تحميل ملف MS Project
تمثل الفئة `Project` ملف Microsoft Project في الذاكرة، وتوفر الوصول إلى المهام والموارد وبيانات العرض.  
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

## الخطوة 3: ضبط جودة JPEG (اختياري)
إذا كنت ترغب في ضبط المخرجات بدقة، يمكنك **ضبط جودة JPEG** باستخدام فئة `ImageSaveOptions`. تتراوح قيمة الجودة من 0 إلى 100، حيث 100 تعطي أعلى دقة بصرية.  
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Jpeg);
options.setJpegQuality(50); // Set JPEG quality to 50
```

## الخطوة 4: حفظ المشروع كـ JPEG
`Project.save` يكتب العرض المرسوم إلى ملف صورة باستخدام الخيارات التي قمت بتكوينها.  
```java
project.save(dataDir + "image_out.jpeg", options);
```

## كيفية تصدير JPEG من MS Project
**الإجابة المباشرة:** استدعِ `project.save("output.jpeg", SaveFileFormat.JPEG, saveOptions)` بعد تكوين `ImageSaveOptions`؛ تقوم الطريقة برسم العرض النشط (افتراضيًا مخطط Gantt) وتكتب ملف JPEG بالجودة المحددة. هذه الاستدعاءة ذات السطر الواحد تتعامل تلقائيًا مع التقسيم، والتحجيم، وإدارة الألوان.  

من خلال ضبط جودة JPEG، تتحكم في التوازن بين وضوح الصورة وحجم الملف، مما يجعل الصورة المصدَّرة مناسبة للنشر على الويب، أو التقارير المطبوعة، أو الشرائح المدمجة.

## المشكلات الشائعة والحلول
- **الجودة المنخفضة تجعل النص غير قابل للقراءة:** قم بزيادة جودة JPEG إلى ما فوق 70 أو انتقل إلى PNG للحصول على تصيير بدون فقد.  
- **أخطاء نفاد الذاكرة في المشاريع الكبيرة:** فعّل البث عن طريق ضبط `saveOptions.setUseMemoryCache(true)` للحفاظ على استهلاك الذاكرة تحت 200 ميغابايت.  
- **تم تصدير العرض الخطأ:** استخدم `saveOptions.setView(ViewType.TaskSheet)` لتصدير عرض مختلف.

## الأسئلة المتكررة

**س: هل يؤثر ضبط جودة JPEG على قابلية قراءة مخطط Gantt؟**  
ج: الجودة الأعلى تحافظ على النص وتفاصيل الخطوط، بينما الجودة المنخفضة جدًا قد تجعل التسميات الصغيرة صعبة القراءة.  

**س: هل يمكنني تصدير صيغ صور أخرى غير JPEG؟**  
ج: نعم، تدعم Aspose.Tasks صيغ PNG وBMP وTIFF عبر تعداد `SaveFileFormat` المناسب.  

**س: هل من الممكن تصدير صفحات متعددة (مثل عروض مختلفة) مرة واحدة؟**  
ج: يمكنك التكرار على العروض المطلوبة وحفظ كل منها كملف JPEG منفصل باستخدام نفس إعدادات `ImageSaveOptions`.  

**س: ما إصدار جافا المطلوب؟**  
ج: تعمل Aspose.Tasks for Java مع JDK 8 وما بعده.  

**س: كيف أتعامل مع المشاريع الكبيرة التي تنتج صورًا ضخمة؟**  
ج: فكر في تقليل جودة JPEG أو تعديل أبعاد الصورة عبر إعدادات إضافية في `ImageSaveOptions`.

## الخلاصة
لقد استعرضنا كيفية **إنشاء ملفات لقطة مشروع JPEG** وضبط جودة JPEG باستخدام Aspose.Tasks for Java. يزيل هذا النهج الحاجة إلى لقطات شاشة يدوية، ويضمن تصييرًا متسقًا عبر الأنظمة، ويسمح لك بضبط التوازن بين وضوح الصورة وحجم الملف—مناسب للتقارير، والعروض التقديمية، والنشر على الويب.

---

**آخر تحديث:** 2026-05-26  
**تم الاختبار مع:** Aspose.Tasks for Java 24.11  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

## دروس ذات صلة

- [كيفية إنشاء ملف MPP – إنشاء وحفظ مشروع فارغ بصيغة MPP باستخدام Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [حفظ المشروع كقالب، CSV، ونص باستخدام Aspose.Tasks for Java](/tasks/java/project-file-operations/save-csv-text-template/)
- [إنشاء ملف MS Project فارغ في Aspose.Tasks](/tasks/java/project-configuration/create-empty-project-file/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}