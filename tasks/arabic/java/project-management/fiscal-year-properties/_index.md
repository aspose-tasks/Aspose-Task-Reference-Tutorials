---
date: 2026-04-01
description: تعلم كيفية حفظ XML، وتعيين السنة المالية، وتحويل MPP إلى XML باستخدام
  Aspose.Tasks للغة Java. دليل خطوة بخطوة مع أمثلة على الشيفرة.
keywords:
- how to save xml
- how to set fiscal
- convert mpp to xml
linktitle: كيفية حفظ XML وإدارة السنة المالية في Aspose.Tasks
second_title: Aspose.Tasks Java API
title: كيفية حفظ XML وإدارة السنة المالية في Aspose.Tasks
url: /ar/java/project-management/fiscal-year-properties/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية حفظ XML وإدارة السنة المالية في Aspose.Tasks

## المقدمة
إذا كنت بحاجة إلى **how to save xml** الملفات التي تم إنشاؤها من بيانات Microsoft Project، فإن Aspose.Tasks for Java يوفر لك طريقة نظيفة وخالية من الترخيص للقيام بذلك. في هذا البرنامج التعليمي سنستعرض تحميل ملف MPP، وعرض معلومات السنة المالية، وتعيين خصائص السنة المالية، وأخيرًا **how to save xml** الناتج. ستشاهد أيضًا كيفية **how to set fiscal** التفاصيل وكيفية **how to convert mpp** الملفات دون الحاجة إلى فتح Microsoft Project.

## إجابات سريعة
- **ما معنى “manage fiscal year” في Aspose.Tasks؟** يتيح لك تحديد شهر بدء السنة المالية وتمكين ترقيم السنة المالية للمشروع.  
- **كيف يتم تعيين شهر بدء السنة المالية؟** استخدم الخاصية `Prj.FY_START_DATE` مع قيمة تعداد `Month` (مثال: `Month.JULY`).  
- **هل يمكنني تحميل ملف MPP؟** نعم، ببساطة أنشئ كائن `Project` مع المسار إلى ملف *.mpp*.  
- **كيف يتم تحويل MPP إلى XML؟** استدعِ `project.save(..., SaveFileFormat.Xml)` بعد تعيين أي خصائص مرغوبة.  
- **هل أحتاج إلى ترخيص؟** يتوفر إصدار تجريبي مجاني؛ ويتطلب الاستخدام الإنتاجي ترخيصًا تجاريًا.  

## ما معنى “إدارة السنة المالية” في ملفات المشروع؟
إدارة السنة المالية تعني تكوين التقويم الذي يتبعه مشروعك للتقارير المالية. ويتضمن ذلك تعيين شهر بدء السنة المالية وتمكين ترقيم السنة المالية اختياريًا، مما يؤثر على كيفية حساب التواريخ وعرضها في التقارير.

## لماذا نستخدم Aspose.Tasks لمعالجة السنة المالية؟
- **لا حاجة إلى Microsoft Project** – العمل مع ملفات المشروع مباشرةً في Java.  
- **تحكم كامل** – تعيين بدء السنة المالية، تمكين الترقيم، وتحويل الصيغ برمجيًا.  
- **API قوي** – معالجة موثوقة لملفات MPP الكبيرة وتصدير XML بسلاسة.  

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من وجود ما يلي:
1. مجموعة تطوير جافا (JDK) مثبتة على نظامك.  
2. ملف JAR الخاص بـ Aspose.Tasks for Java – قم بتنزيله من [here](https://releases.aspose.com/tasks/java/) وأضفه إلى مسار الفئة (classpath) الخاص بمشروعك.

## استيراد الحزم
للبدء، استورد الفئات الضرورية في ملف مصدر Java الخاص بك:
```java
import com.aspose.tasks.*;
```

## كيفية تحميل ملف MPP وعرض معلومات السنة المالية
فيما يلي نقسم العملية إلى خطوات واضحة مرقمة.

### الخطوة 1: تحميل ملف المشروع
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
هنا نقوم **بتحميل ملف MPP** (`project.mpp`) من الدليل المحدد. هذه هي الخطوة الأولى في أي معالجة متعلقة بالسنة المالية.

### الخطوة 2: عرض خصائص السنة المالية
```java
//Display fiscal year properties
System.out.println("Fiscal Year Start Date : " + project.get(Prj.FY_START_DATE));
System.out.println("Fiscal Year Numbering : " + project.get(Prj.FISCAL_YEAR_START));
```
تتيح لك الخصائص `Prj.FY_START_DATE` و `Prj.FISCAL_YEAR_START` **عرض تفاصيل السنة المالية**، مُجابةً على سؤال “ما هو تكوين السنة المالية الحالي؟”.

### الخطوة 3: تعيين بداية السنة المالية وتمكين الترقيم
```java
//Create a project instance
Project prj = new Project();
//Set fiscal year properties
prj.set(Prj.FY_START_DATE, Month.JULY);
prj.set(Prj.FISCAL_YEAR_START, new NullableBool(true));
//Save the project as XML project file
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
في هذه الخطوة نقوم **how to set fiscal** الإعدادات:
- `Month.JULY` يحدد شهر بدء السنة المالية.  
- `NullableBool(true)` يُفعّل ترقيم السنة المالية.  
- أخيرًا، يتم **converted MPP to XML** للمشروع باستخدام `SaveFileFormat.Xml`.

### الخطوة 4: تأكيد العملية
```java
//Display result of conversion.
System.out.println("Process completed Successfully");
```
رسالة بسيطة في وحدة التحكم تؤكد أن السنة المالية تم تكوينها وتم حفظ الملف.

## لماذا هذا مهم
حفظ المشروع كملف XML يمنحك تمثيلًا نصيًا محمولًا يمكن تحليله بسهولة، وإدارته عبر نظام التحكم في الإصدارات، أو دمجه مع أنظمة أخرى. عندما تكون إعدادات السنة المالية صحيحة، فإن التقارير المالية ولوحات المعلومات اللاحقة ستتطابق مع فترات المحاسبة في مؤسستك.

## حالات الاستخدام الشائعة
- **التقارير المالية** – مواءمة جداول المشروع مع تقويم مالي قبل التصدير إلى أدوات ذكاء الأعمال.  
- **ترحيل البيانات** – تحويل ملفات *.mpp* القديمة إلى XML للاستيراد إلى منصات إدارة المشاريع السحابية.  
- **التدقيق الآلي** – التحقق برمجيًا من أن كل مشروع يستخدم شهر بدء السنة المالية الصحيح.

## نصائح استكشاف الأخطاء الشائعة ومشكلات متكررة
| المشكلة | الحل |
|-------|----------|
| **قيمة شهر غير صحيحة** | تأكد من استخدام تعداد `Month` (مثال: `Month.JANUARY`). |
| **الملف غير موجود** | تحقق من أن `dataDir` يشير إلى المجلد الصحيح وأن اسم الملف مطابق. |
| **فشل الحفظ** | تحقق من أذونات الكتابة على الدليل الهدف وأن `SaveFileFormat` مدعوم. |
| **السنة المالية غير معكوسة في XML** | بعد الحفظ، افتح ملف XML وتأكد من أن عقد `<FiscalYearStart>` و `<FiscalYearNumbering>` تحتوي على القيم المتوقعة. |

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Tasks for Java لتعديل خصائص مشروع أخرى؟**  
ج: نعم، يوفر Aspose.Tasks وظائف شاملة لإدارة مختلف خصائص المشروع بخلاف إعدادات السنة المالية.

**س: هل Aspose.Tasks for Java متوافق مع صيغ ملفات مشروع مختلفة؟**  
ج: نعم، يدعم مجموعة واسعة من الصيغ بما في ذلك MPP و XML وغيرها.

**س: كيف يمكنني الحصول على الدعم إذا واجهت أي مشكلات أثناء استخدام Aspose.Tasks for Java؟**  
ج: يمكنك طلب المساعدة من مجتمع Aspose.Tasks على [forum](https://forum.aspose.com/c/tasks/15) أو التواصل مباشرةً مع فريق الدعم الخاص بهم.

**س: هل يقدم Aspose.Tasks نسخة تجريبية مجانية؟**  
ج: نعم، يمكنك الوصول إلى النسخة التجريبية المجانية من Aspose.Tasks من خلال [here](https://releases.aspose.com/).

**س: أين يمكنني شراء ترخيص لـ Aspose.Tasks for Java؟**  
ج: يمكنك شراء ترخيص لـ Aspose.Tasks for Java من خلال [here](https://purchase.aspose.com/buy).

## الخلاصة
إدارة خصائص السنة المالية في Aspose.Tasks for Java أمر بسيط. باتباع الخطوات المذكورة أعلاه يمكنك **how to save xml**، **load mpp file**، **display fiscal year**، **set fiscal year**، و **convert mpp to xml** بثقة. استخدم هذه التقنيات للحفاظ على جداول مشروعك متوافقة مع التقويم المالي لمؤسستك وإنشاء تمثيلات XML محمولة للمعالجة اللاحقة.

---

**آخر تحديث:** 2026-04-01  
**تم الاختبار باستخدام:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}