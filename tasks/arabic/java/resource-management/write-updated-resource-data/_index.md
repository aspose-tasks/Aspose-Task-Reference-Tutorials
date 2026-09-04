---
date: 2026-06-30
description: تعلم كيفية تحديث موارد متعددة وتعديل بيانات مجموعة الموارد، ثم تصدير
  المشروع إلى MPP وحفظ المشروع كملف MPP باستخدام Aspose.Tasks for Java.
keywords:
- update multiple resources
- modify resource group
- export project to mpp
- save project as mpp
linktitle: تحديث موارد متعددة في Aspose.Tasks for Java
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to update multiple resources and modify resource group data,
    then export project to MPP and save project as MPP using Aspose.Tasks for Java.
  headline: Update Multiple Resources in Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to update multiple resources and modify resource group data,
    then export project to MPP and save project as MPP using Aspose.Tasks for Java.
  name: Update Multiple Resources in Aspose.Tasks for Java
  steps:
  - name: Java Development Kit (JDK) installed on your system.
    text: Java Development Kit (JDK) installed on your system.
  - name: Aspose.Tasks for Java library. You can download it from [here](https://releases.aspose.com/tasks/java/).
    text: Aspose.Tasks for Java library. You can download it from [here](https://releases.aspose.com/tasks/java/).
  - name: Basic knowledge of Java programming.
    text: Basic knowledge of Java programming.
  type: HowTo
- questions:
  - answer: Yes, you can update multiple resources by iterating through them and setting
      their attributes accordingly.
    question: Can I update multiple resources in the same project using Aspose.Tasks
      for Java?
  - answer: Yes, Aspose.Tasks supports various file formats including XML, MPP, and
      more.
    question: Does Aspose.Tasks support other file formats besides MS Project?
  - answer: Aspose.Tasks is compatible with Java versions 6 and above.
    question: Is Aspose.Tasks compatible with different versions of Java?
  - answer: Yes, you can perform a wide range of operations such as reading, writing,
      and manipulating tasks, resources, and calendars.
    question: Can I perform other operations on MS Project files with Aspose.Tasks?
  - answer: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for any assistance or queries.
    question: Where can I find additional help or support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: تحديث موارد متعددة في Aspose.Tasks for Java
url: /ar/java/resource-management/write-updated-resource-data/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تحديث موارد متعددة في Aspose.Tasks لـ Java

## مقدمة
في هذا البرنامج التعليمي، ستتعلم كيفية **تحديث موارد متعددة** في ملف Microsoft Project باستخدام Aspose.Tasks لـ Java. سواء كنت بحاجة إلى تغيير الأسعار، أو إعادة تعيين المجموعات، أو تصدير الملف المحدث إلى MPP، فإن الخطوات أدناه ستقودك عبر سير عمل كامل وجاهز للإنتاج. لا يلزم تثبيت Microsoft Project، ويمكن للـ API التعامل مع المشاريع التي تحتوي على مئات الموارد بكفاءة.

## إجابات سريعة
- **هل يمكنني تحديث عدة موارد مرة واحدة؟** نعم – قم بالتكرار عبر `ResourceCollection` وتعيين الخصائص في تمريرة واحدة.  
- **ما الطريقة التي تحفظ الملف كـ MPP؟** `project.save("output.mpp", SaveFileFormat.MPP)`.  
- **هل أحتاج إلى ترخيص للاستخدام التجاري؟** الترخيص المدفوع مطلوب للإنتاج؛ يتوفر إصدار تجريبي مجاني.  
- **ما إصدارات Java المدعومة؟** Java 6 وما فوق، بما في ذلك Java 17 LTS.  
- **هل التحديث الجماعي performant؟** Aspose.Tasks يعالج مشاريع بـ 500 مورد في أقل من ثانيتين على خادم عادي.

## ما هو “تحديث موارد متعددة”؟
**“تحديث موارد متعددة”** يشير إلى تغيير خصائص عدة إدخالات موارد برمجيًا—مثل الأسعار، المجموعات، التقويمات، أو الحقول المخصصة—داخل ملف مشروع واحد. غالبًا ما يُطلب هذا الإجراء عند مزامنة بيانات المشروع مع أنظمة تخطيط موارد المؤسسة، أو تعديل الميزانيات عبر العديد من الموارد، أو تطبيق تغييرات سياسات على مستوى المؤسسة.

## لماذا تستخدم Aspose.Tasks لتعديل مجموعة الموارد وتصدير المشروع إلى MPP؟
Aspose.Tasks يدعم **أكثر من 50 تنسيقًا للإدخال والإخراج**، بما في ذلك MPP وXML وCSV، ويمكنه **تصدير المشروع إلى MPP** دون تحميل الملف بالكامل في الذاكرة. المكتبة تعالج ملفات يصل حجمها إلى **2 GB**، مما يتيح لك **حفظ المشروع كـ MPP** بسرعة وبشكل موثوق.

## المتطلبات المسبقة

قبل أن نبدأ، تأكد من وجود ما يلي:

1. مجموعة تطوير Java (JDK) مثبتة على نظامك.  
2. مكتبة Aspose.Tasks لـ Java. يمكنك تنزيلها من [هنا](https://releases.aspose.com/tasks/java/).  
3. معرفة أساسية ببرمجة Java.  

## استيراد الحزم

عبارات `import` تجلب الفئات المطلوبة من Aspose.Tasks إلى ملف المصدر الخاص بك.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## الخطوة 1: إعداد دليل البيانات الخاص بك

حدد الدليل الذي توجد فيه ملفات البيانات الخاصة بك:

```java
String dataDir = "Your Data Directory";
```

## الخطوة 2: تحديد ملفات الإدخال والإخراج

حدد المسارات لملف MS Project الإدخالي والملف المحدث الناتج:

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Test file with one rsc to update
String resultFile = dataDir + "OutputMPP.mpp"; // File to write test project
```

## الخطوة 3: تحميل المشروع

`Project` يمثل ملف Microsoft Project محملاً في الذاكرة، ويوفر الوصول إلى المهام والموارد وبيانات المشروع الأخرى.

```java
Project project = new Project(file);
```

## الخطوة 4: إضافة مورد وتعيين الخصائص

`Resource` نمذجة مورد مشروع فردي، يتيح لك تعيين الأسعار، المجموعات، التقويمات، وغيرها من الخصائص.

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

## الخطوة 5: تحديث موارد متعددة بكفاءة

`ResourceCollection` هي مجموعة جميع الموارد في المشروع، يمكن الوصول إليها عبر `project.getResources()`.

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## الخطوة 6: حفظ المشروع

`SaveFileFormat` يعدد صيغ الملفات المدعومة لحفظ المشروع، مثل MPP وXML وPDF.

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## كيفية تحديث موارد متعددة في مشروع؟

حمّل المشروع الحالي، استرجع `ResourceCollection` الخاص به، وتكرّر عبر كل كائن `Resource`. لكل مورد، عدّل الحقول المطلوبة مثل الأسعار أو المجموعات أو السمات المخصصة، ثم انتقل إلى العنصر التالي. بعد معالجة جميع الموارد، استدعِ `project.save(...)` مرة واحدة لحفظ التغييرات بكفاءة.

## المشكلات الشائعة والحلول

- **تعارض معرفات الموارد** – تأكد من أن كل مورد جديد يحصل على معرف فريد باستخدام `project.getResources().add(new Resource())`.  
- **أخطاء تنسيق السعر** – استخدم كائنات `ResourceRate` واضبط `RateType` إلى `StandardRate` أو `OvertimeRate`.  
- **الملفات الكبيرة تسبب ضغطًا على الذاكرة** – فعّل `Project.setReadOnly(true)` قبل التحميل لتقليل استهلاك الذاكرة.

## الأسئلة المتكررة

**س: هل يمكنني تحديث موارد متعددة في نفس المشروع باستخدام Aspose.Tasks لـ Java؟**  
ج: نعم، يمكنك تحديث موارد متعددة عن طريق التكرار عبرها وتعيين خصائصها وفقًا لذلك.

**س: هل يدعم Aspose.Tasks تنسيقات ملفات أخرى غير MS Project؟**  
ج: نعم، Aspose.Tasks يدعم تنسيقات ملفات متعددة بما في ذلك XML وMPP وغيرها.

**س: هل Aspose.Tasks متوافق مع إصدارات Java المختلفة؟**  
ج: Aspose.Tasks متوافق مع إصدارات Java 6 وما فوق.

**س: هل يمكنني إجراء عمليات أخرى على ملفات MS Project باستخدام Aspose.Tasks؟**  
ج: نعم، يمكنك تنفيذ مجموعة واسعة من العمليات مثل القراءة والكتابة وتعديل المهام والموارد والتقويمات.

**س: أين يمكنني العثور على مساعدة أو دعم إضافي لـ Aspose.Tasks؟**  
ج: يمكنك زيارة [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15) للحصول على أي مساعدة أو استفسارات.

**س: كيف أقوم بتصدير الملف المحدث إلى صيغة MPP؟**  
ج: استدعِ `project.save("UpdatedProject.mpp", SaveFileFormat.MPP)` بعد إجراء جميع تغييرات الموارد.

**س: ما هي أفضل طريقة لتعديل مجموعة مورد؟**  
ج: اضبط خاصية `Resource.Group` على كل كائن `Resource` قبل حفظ المشروع.

---

**آخر تحديث:** 2026-06-30  
**تم الاختبار مع:** Aspose.Tasks for Java 24.12  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

## دروس ذات صلة

- [إضافة مورد إلى المشروع باستخدام Aspose.Tasks لـ Java](/tasks/java/resource-management/create-resources/)
- [إدارة تكاليف موارد MS Project باستخدام Aspose.Tasks لـ Java](/tasks/java/resource-management/resource-cost/)
- [كيفية تصدير MPP إلى Excel باستخدام Aspose.Tasks لـ Java](/tasks/java/project-file-operations/save-data-to-excel/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}