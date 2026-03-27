---
date: 2025-12-25
description: تعلم كيفية إدارة خصائص السنة المالية وتحميل ملفات MPP بكفاءة باستخدام
  Aspose.Tasks للغة Java. دليل خطوة بخطوة مع أمثلة.
linktitle: Manage Fiscal Year Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: إدارة خصائص السنة المالية في Aspose.Tasks
url: /ar/java/project-management/fiscal-year-properties/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إدارة خصائص السنة المالية في Aspose.Tasks

## المقدمة
Aspose.Tasks هي مكتبة Java قوية تمكّن المطورين من **إدارة إعدادات السنة المالية**، تحميل ملفات MPP، وتحويل بيانات المشروع إلى XML ببضع أسطر من الشيفرة فقط. في هذا البرنامج التعليمي ستتعرف على كيفية ضبط خصائص السنة المالية، عرض معلومات السنة المالية، وحفظ النتيجة — كل ذلك مع الحفاظ على نظافة وصيانة الكود.

## إجابات سريعة
- **ماذا يعني “إدارة السنة المالية” في Aspose.Tasks؟** يتيح لك تعريف شهر بدء السنة المالية وتفعيل ترقيم السنة المالية للمشروع.  
- **كيف يمكن ضبط شهر بدء السنة المالية؟** استخدم الخاصية `Prj.FY_START_DATE` مع قيمة من تعداد `Month` (مثال: `Month.JULY`).  
- **هل يمكنني تحميل ملف MPP؟** نعم، ببساطة أنشئ كائن `Project` مع مسار ملف *.mpp*.  
- **كيف أحول MPP إلى XML؟** استدعِ `project.save(..., SaveFileFormat.Xml)` بعد ضبط الخصائص المطلوبة.  
- **هل أحتاج إلى ترخيص؟** يتوفر إصدار تجريبي مجاني؛ يلزم الحصول على ترخيص تجاري للاستخدام في الإنتاج.

## ما معنى “إدارة السنة المالية” في ملفات المشروع؟
إدارة السنة المالية تعني تكوين التقويم الذي يتبعه مشروعك للتقارير المالية. يشمل ذلك ضبط شهر بدء السنة المالية وتفعيل ترقيم السنة المالية اختياريًا، مما يؤثر على كيفية حساب التواريخ وعرضها في التقارير.

## لماذا نستخدم Aspose.Tasks لمعالجة السنة المالية؟
- **لا حاجة إلى Microsoft Project** – اعمل مباشرةً مع ملفات المشروع في Java.  
- **تحكم كامل** – اضبط بدء السنة المالية، فعّل الترقيم، وحوّل الصيغ برمجيًا.  
- **API قوي** – معالجة موثوقة لملفات MPP الكبيرة وتصدير XML سلس.

## المتطلبات السابقة
قبل أن نبدأ، تأكد من وجود ما يلي:
1. مجموعة تطوير Java (JDK) مثبتة على نظامك.  
2. ملف JAR الخاص بـ Aspose.Tasks for Java – حمّله من [here](https://releases.aspose.com/tasks/java/) وأضفه إلى مسار الفئة (classpath) في مشروعك.

## استيراد الحزم
لبدء العمل، استورد الفئات الضرورية في ملف Java المصدر:
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
هنا نقوم **بتحميل ملف MPP** (`project.mpp`) من الدليل المحدد. هذه هي الخطوة الأولى في أي تعديل يتعلق بالسنة المالية.

### الخطوة 2: عرض خصائص السنة المالية
```java
//Display fiscal year properties
System.out.println("Fiscal Year Start Date : " + project.get(Prj.FY_START_DATE));
System.out.println("Fiscal Year Numbering : " + project.get(Prj.FISCAL_YEAR_START));
```
تتيح لك الخصائص `Prj.FY_START_DATE` و `Prj.FISCAL_YEAR_START` **عرض تفاصيل السنة المالية**، والإجابة على سؤال “ما هو تكوين السنة المالية الحالي؟”.

### الخطوة 3: ضبط بدء السنة المالية وتفعيل الترقيم
```java
//Create a project instance
Project prj = new Project();
//Set fiscal year properties
prj.set(Prj.FY_START_DATE, Month.JULY);
prj.set(Prj.FISCAL_YEAR_START, new NullableBool(true));
//Save the project as XML project file
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
في هذه الخطوة نوضح **كيفية ضبط إعدادات السنة المالية**:
- `Month.JULY` يحدد شهر بدء السنة المالية.  
- `NullableBool(true)` يفعّل ترقيم السنة المالية.  
- أخيرًا، يتم **تحويل المشروع من MPP إلى XML** باستخدام `SaveFileFormat.Xml`.

### الخطوة 4: تأكيد العملية
```java
//Display result of conversion.
System.out.println("Process completed Successfully");
```
رسالة بسيطة في وحدة التحكم تؤكد أن السنة المالية تم تكوينها وتم حفظ الملف.

## المشكلات الشائعة والحلول
| المشكلة | الحل |
|-------|----------|
| **قيمة شهر غير صحيحة** | تأكد من استخدام تعداد `Month` (مثال: `Month.JANUARY`). |
| **الملف غير موجود** | تحقق من أن `dataDir` يشير إلى المجلد الصحيح وأن اسم الملف مطابق. |
| **فشل الحفظ** | افحص أذونات الكتابة على الدليل الهدف وتأكد من أن `SaveFileFormat` مدعوم. |

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Tasks for Java لتعديل خصائص مشروع أخرى؟**  
ج: نعم، توفر Aspose.Tasks وظائف شاملة لإدارة خصائص مشروع متعددة بخلاف إعدادات السنة المالية.

**س: هل Aspose.Tasks for Java متوافق مع صيغ ملفات مشروع مختلفة؟**  
ج: نعم، يدعم مجموعة واسعة من الصيغ بما فيها MPP، XML، وغيرها.

**س: كيف يمكنني الحصول على الدعم إذا واجهت أي مشكلات أثناء استخدام Aspose.Tasks for Java؟**  
ج: يمكنك طلب المساعدة من مجتمع Aspose.Tasks عبر [forum](https://forum.aspose.com/c/tasks/15) أو التواصل مباشرةً مع فريق الدعم.

**س: هل تقدم Aspose.Tasks نسخة تجريبية مجانية؟**  
ج: نعم، يمكنك الوصول إلى النسخة التجريبية المجانية من Aspose.Tasks من [here](https://releases.aspose.com/).

**س: أين يمكنني شراء ترخيص لـ Aspose.Tasks for Java؟**  
ج: يمكنك شراء ترخيص Aspose.Tasks for Java من [here](https://purchase.aspose.com/buy).

## الخاتمة
إدارة خصائص السنة المالية في Aspose.Tasks for Java أمر بسيط. باتباع الخطوات أعلاه يمكنك **إدارة السنة المالية**، **تحميل ملفات MPP**، **عرض تفاصيل السنة المالية**، و**تحويل MPP إلى XML** بثقة. استخدم هذه التقنيات لضمان توافق جداول مشروعك مع التقويم المالي لمنظمتك.

---

**آخر تحديث:** 2025-12-25  
**تم الاختبار مع:** Aspose.Tasks for Java 24.12 (أحدث نسخة وقت الكتابة)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}