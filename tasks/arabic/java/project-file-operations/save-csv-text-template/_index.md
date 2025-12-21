---
date: 2025-12-21
description: تعلم كيفية حفظ المشروع كقالب، وتصدير ملف MPP إلى CSV، وتحويل ملف MPP
  إلى نص باستخدام Aspose.Tasks للغة Java.
linktitle: Save Project as Template, CSV, and Text with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: حفظ المشروع كقالب، CSV، ونص باستخدام Aspose.Tasks لجافا
url: /ar/java/project-file-operations/save-csv-text-template/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# حفظ المشروع كقالب، CSV، ونص باستخدام Aspose.Tasks

## المقدمة
في هذا البرنامج التعليمي، ستكتشف **كيفية حفظ المشروع كقالب** وكذلك كيفية تصدير ملفات Microsoft Project (MPP) إلى صيغ CSV ونص عادي باستخدام مكتبة Aspose.Tasks للغة Java. سواء كنت بحاجة إلى إنشاء قالب مشروع قابل لإعادة الاستخدام، أو توليد تقارير CSV للتحليل، أو استخراج نص بسيط للتكامل، فإن هذه الخطوات ستوجهك خلال العملية بسرعة وكفاءة.

## إجابات سريعة
- **هل يمكنني تصدير MPP إلى CSV؟** نعم – استخدم `project.save(..., SaveFileFormat.CSV)`.  
- **كيف يمكن تصدير النص؟** احفظ باستخدام `SaveFileFormat.TEXT`.  
- **ماذا يفعل “حفظ المشروع كقالب”؟** ينشئ ملف `.mpt` يزيل القيم الفعلية وبيانات الخط الأساسي، جاهز لإعادة الاستخدام.  
- **هل أحتاج إلى ترخيص؟** يتوفر إصدار تجريبي؛ الترخيص التجاري مطلوب للإنتاج.  
- **ما نسخة Java المطلوبة؟** تدعم Java 8+.

## ما هو “حفظ المشروع كقالب”؟
حفظ المشروع كقالب (`.mpt`) يلتقط الهيكل، تسلسل المهام، وتعيينات الموارد مع إزالة تواريخ البدء/الانتهاء الفعلية وبيانات الخط الأساسي. يجعل هذا القالب مثالياً لإعادة استخدام تخطيط مشروع قياسي عبر مشاريع جديدة متعددة.

## لماذا نستخدم Aspose.Tasks للغة Java؟
تتيح لك Aspose.Tasks معالجة ملفات Microsoft Project دون الحاجة لتثبيت Microsoft Project نفسه. تدعم **كيفية تصدير MPP**، **كيفية تصدير النص**، و**تحويل MPP إلى CSV**، كل ذلك من خلال شفرة Java صافية، مما يجعلها مثالية لأتمتة الخوادم، خطوط CI، أو الأدوات المكتبية.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من وجود ما يلي:

1. مجموعة تطوير Java (JDK) 8 أو أعلى مثبتة.  
2. مكتبة Aspose.Tasks للغة Java مضافة إلى مشروعك. حمّلها من [هنا](https://releases.aspose.com/tasks/java/).  
3. إلمام أساسي بصياغة Java وإعداد مشروع Maven/Gradle.

## استيراد الحزم
أولاً، استورد الفئات المطلوبة في ملف مصدر Java الخاص بك:

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

## حفظ المشروع كـ CSV (تصدير MPP إلى CSV)
تصدير ملف MPP إلى CSV مفيد لتحليل البيانات في Excel أو أدوات BI.

### الخطوة 1: تحميل المشروع
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### الخطوة 2: حفظ كـ CSV
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```

## حفظ المشروع كنص (كيفية تصدير النص)
إذا كنت بحاجة إلى تمثيل نصي بسيط للمهام أو الموارد أو التعيينات، احفظ المشروع كملف نصي.

### الخطوة 1: تحميل المشروع
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### الخطوة 2: حفظ كنص
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```

## حفظ المشروع كقالب (إنشاء قالب مشروع Java)
إنشاء قالب قابل لإعادة الاستخدام يزيل التواريخ الفعلية والخطوط الأساسية، تاركاً هيكلًا نظيفًا للمشاريع الجديدة.

### الخطوة 1: تحميل المشروع
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### الخطوة 2: ضبط خيارات القالب
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```

### الخطوة 3: حفظ كقالب
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## المشكلات الشائعة والنصائح
- **الملف غير موجود:** تأكد من صحة المسار إلى `YourProject.mpp` أو استخدم مسارًا مطلقًا.  
- **استثناءات الترخيص:** بدون ترخيص صالح، تعمل المكتبة في وضع التقييم وقد تضيف علامات مائية. قم بتطبيق الترخيص مبكرًا في الشفرة (`License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`).  
- **المشاريع الكبيرة:** بالنسبة لملفات MPP الكبيرة جدًا، فكر في زيادة حجم heap للـ JVM (`-Xmx2g`) لتجنب `OutOfMemoryError`.

## الخاتمة
لقد غطينا **كيفية حفظ المشروع كقالب**، بالإضافة إلى **تصدير MPP إلى CSV** و**تحويل MPP إلى نص** باستخدام Aspose.Tasks للغة Java. تتيح لك هذه القدرات أتمتة معالجة بيانات المشروع، إنشاء قوالب قابلة لإعادة الاستخدام، وتكامل معلومات المشروع مع أنظمة أخرى—كل ذلك دون الحاجة لتثبيت Microsoft Project.

## الأسئلة المتكررة
### س: هل يمكن لـ Aspose.Tasks للغة Java التعامل مع ملفات مشروع معقدة؟
ج: بالتأكيد! يمكن لـ Aspose.Tasks للغة Java التعامل مع مشاريع ذات تعقيد مختلف بسهولة، مع توفير دعم شامل لصيغ ملفات Microsoft Project.  
### س: هل هناك نسخة تجريبية متاحة لـ Aspose.Tasks للغة Java؟
ج: نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Tasks للغة Java من [هنا](https://releases.aspose.com/).  
### س: أين يمكنني العثور على الدعم لـ Aspose.Tasks للغة Java؟
ج: يمكنك زيارة [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15) للحصول على أي مساعدة أو استفسارات بخصوص Aspose.Tasks للغة Java.  
### س: هل يمكنني شراء ترخيص مؤقت لـ Aspose.Tasks للغة Java؟
ج: نعم، يمكنك شراء ترخيص مؤقت من [هنا](https://purchase.aspose.com/temporary-license/)، مما يتيح لك تقييم كامل إمكانات المكتبة.  
### س: هل Aspose.Tasks للغة Java متوافق مع أنظمة تشغيل مختلفة؟
ج: نعم، Aspose.Tasks للغة Java متوافق مع أنظمة تشغيل متعددة، بما في ذلك Windows و macOS و Linux.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}

---

**آخر تحديث:** 2025-12-21  
**تم الاختبار مع:** Aspose.Tasks للغة Java 24.12 (الأحدث)  
**المؤلف:** Aspose  

---