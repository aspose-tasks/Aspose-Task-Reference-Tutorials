---
date: 2026-09-30
description: تعلم كيفية إنشاء سمة موسعة للمهمة باستخدام Aspose.Tasks for Java، المكتبة
  الرائدة لإدارة المشاريع بلغة java لإضافة حقول مخصصة للمهمة.
keywords:
- create task extended attribute
- java project management library
- add custom task field
lastmod: 2026-09-30
linktitle: كيفية إنشاء سمة موسعة للمهمة باستخدام Aspose.Tasks Java
og_description: تعلم كيفية إنشاء سمة موسعة للمهمة باستخدام Aspose.Tasks for Java،
  المكتبة الرائدة لإدارة المشاريع بلغة java لإضافة حقول مخصصة للمهمة.
og_image_alt: 'Developer guide: create task extended attribute in Aspose.Tasks Java'
og_title: كيفية إنشاء سمة موسعة للمهمة باستخدام Aspose.Tasks Java
schemas:
- author: Aspose
  dateModified: '2026-09-30'
  description: Learn how to create task extended attribute using Aspose.Tasks for
    Java, the leading java project management library for adding custom task fields.
  headline: How to create task extended attribute with Aspose.Tasks Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java integrates smoothly with any Java ecosystem,
      including Spring, Hibernate, and Apache POI.
    question: Can I use Aspose.Tasks for Java with other Java libraries?
  - answer: Absolutely. The library is engineered to handle multi‑thousand‑task projects
      and supports streaming to keep memory usage low.
    question: Is Aspose.Tasks for Java suitable for large‑scale project management
      applications?
  - answer: Yes, you need a valid commercial license. You can review the details on
      the [Aspose.Tasks website](https://purchase.aspose.com/buy).
    question: Are there any licensing considerations for using Aspose.Tasks for Java
      in a commercial project?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community help, or open a support ticket through your Aspose account.
    question: How can I get support or assistance with Aspose.Tasks for Java?
  - answer: Yes, you can access a free trial version on the [Aspose.Tasks free trial](https://releases.aspose.com/)
      page.
    question: Can I try Aspose.Tasks for Java before purchasing?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose.tasks
- java project management
- extended attributes
- task customization
title: كيفية إنشاء سمة موسعة للمهمة باستخدام Aspose.Tasks Java
url: /ar/java/task-properties/add-extended-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء سمة موسعة للمهمة باستخدام Aspose.Tasks Java

## مقدمة
في هذا البرنامج التعليمي ستتعلم كيفية **إنشاء سمة موسعة للمهمة** في ملف Microsoft Project باستخدام Aspose.Tasks for Java. يتيح إضافة الحقول المخصصة لك التقاط بيانات خاصة بالمشروع غير مغطاة بالأعمدة المدمجة، مما يمنحك تحكمًا أكثر دقة في التقارير وتخطيط الموارد. في نهاية الدليل ستكون قادرًا على إضافة سمات نصية عادية، وسمات مدعومة بالبحث، وسمات مدة إلى أي مهمة.

## إجابات سريعة
- **ماذا يعني “السمة الموسعة”؟** إنها حقل مخصص تقوم بتعريفه وإرفاقه بالمهام أو الموارد أو التعيينات.  
- **أي مكتبة تضيف هذه القدرة؟** Aspose.Tasks for Java، مكتبة إدارة مشاريع جافا.  
- **هل أحتاج إلى ترخيص لتجربتها؟** نعم – نسخة تجريبية مجانية لمدة 30 يومًا متاحة من موقع Aspose.  
- **هل يمكنني إضافة قيم بحث؟** بالطبع؛ يمكنك توفير قائمة بالقيم المسموح بها للحقول النصية أو حقول المدة.  
- **هل API متوافق مع Java 8 وما بعده؟** نعم، يدعم Java 8+ ويعمل على جميع أنظمة التشغيل الرئيسية.  

## ما هي السمة الموسعة للمهمة؟
السمة الموسعة للمهمة هي عمود معرف من قبل المستخدم يخزن معلومات إضافية لكل مهمة في ملف Project. تتصرف كحقل مدمج ولكن يمكنها احتواء أي نوع من البيانات التي تحتاجها، مثل النص، الأرقام، التواريخ، أو الفترات الزمنية.

## لماذا تستخدم Aspose.Tasks for Java؟
يدعم Aspose.Tasks **أكثر من 50 تنسيق ملف** ويمكنه معالجة المشاريع التي تحتوي على **أكثر من 10,000 مهمة** دون الحاجة إلى تثبيت Microsoft Project. تعمل المكتبة بالكامل دون اتصال بالإنترنت، مما يضمن خصوصية البيانات وأداءً حتميًا لحلول على مستوى المؤسسات.

## المتطلبات المسبقة
قبل أن تبدأ، تأكد من أن لديك:

- معرفة أساسية ببرمجة Java.  
- مكتبة Aspose.Tasks for Java مثبتة. يمكنك تنزيلها من [الموقع الإلكتروني](https://releases.aspose.com/tasks/java/).  
- بيئة تطوير Java (IntelliJ IDEA أو Eclipse أو VS Code) مُعدة على جهازك.

## استيراد الحزم
تُتيح لك عبارات `import` الوصول إلى الفئات الأساسية التي ستحتاجها، مثل `Project` و `ExtendedAttributeDefinition` و `ExtendedAttribute`.  

`Project` تمثل ملف Microsoft Project وتوفر طرقًا لقراءةه وتعديله وحفظه.  
`ExtendedAttributeDefinition` تُعرّف حقلًا مخصصًا يمكن إرفاقه بالمهام أو الموارد أو التعيينات.  
`ExtendedAttribute` هو مثال على تعريف يحمل القيمة الفعلية لكيان معين.

## كيف تضيف سمة موسعة نصية عادية إلى مهمة؟
لإضافة سمة موسعة نصية عادية، تقوم أولاً بتحميل المشروع، ثم إنشاء تعريف من النوع Text، وإضافته إلى مجموعة المشروع، وإنشاء مهمة، وإنشاء السمة من التعريف، وتعيين قيمتها النصية، وإرفاقها بالمهمة، وأخيرًا حفظ المشروع.

### 1. تحديد مسار دليل المستند
حدد مكان وجود ملفات المصدر والإخراج الخاصة بك.

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

### 2. إنشاء مشروع جديد
أنشئ كائن `Project`، مع إمكانية تحميل ملف .mpp موجود.

```java
String dataDir = "Your Document Directory";
```

### 3. إنشاء تعريف سمة موسعة من النوع Text1
عرّف الحقل المخصص كعمود نصي عادي باسم “Text1”.

```java
Project project = new Project(dataDir + "project.mpp");
```

### 4. إضافة التعريف إلى مجموعة السمات الموسعة للمشروع
سجّل التعريف الجديد حتى يتعرف المشروع عليه.

```java
ExtendedAttributeDefinition taskExtendedAttributeText1Definition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Task City Name");
```

### 5. إضافة مهمة إلى المشروع
أنشئ مهمة ستستقبل الحقل المخصص.

```java
project.getExtendedAttributes().add(taskExtendedAttributeText1Definition);
```

### 6. إنشاء سمة موسعة من تعريف السمة
أنشئ مثالًا يمكنك ربطه بمهمة محددة.

```java
Task task = project.getRootTask().getChildren().add("Task 1");
```

### 7. تعيين قيمة للسمة الموسعة المُنشأة
حدد النص الفعلي الذي تريد تخزينه، مثل “Design Review”.

```java
ExtendedAttribute taskExtendedAttributeText1 = taskExtendedAttributeText1Definition.createExtendedAttribute();
```

### 8. إضافة السمة الموسعة إلى المهمة
أرفق مثال السمة إلى مجموعة `ExtendedAttributes` الخاصة بالمهمة.

```java
taskExtendedAttributeText1.setTextValue("London");
```

### 9. حفظ المشروع
اكتب المشروع المحدث مرة أخرى إلى القرص بالتنسيق المطلوب.

```java
task.getExtendedAttributes().add(taskExtendedAttributeText1);
```

## كيف تضيف سمة نصية مع خيار بحث؟
عند إضافة سمة نصية مع بحث، تتبع نفس الخطوات كما في السمة النصية العادية، ولكن قبل إضافة التعريف تقوم بملء مجموعة `LookupValues` الخاصة به بالسلاسل المسموح بها. تظهر هذه القيم كقائمة منسدلة في Microsoft Project، مما يضمن اتساق البيانات.

## كيف تضيف سمة مدة مع خيار بحث؟
لإضافة سمة مدة مع بحث، استبدل النوع `Text1` بـ `Duration2` عند إنشاء التعريف، ثم املأ مجموعة `LookupValues` بسلاسل المدة مثل “1 day”، “2 days”، إلخ. بعد إضافة التعريف إلى المشروع، أنشئ مثال السمة، حدد قيمة مدة، أرفقه بمهمة، واحفظ الملف.

## المشكلات الشائعة واستكشاف الأخطاء
- **قيمة البحث لا تظهر** – تأكد من إضافة كل إدخال بحث إلى مجموعة `LookupValues` *قبل* استدعاء `project.getExtendedAttributes().add(definition)`.  
- **قيمة السمة غير محفوظة** – تحقق من أنك تضيف مثال `ExtendedAttribute` إلى المهمة *بعد* تعيين قيمتها.  
- **حجم الملف يزداد بشكل غير متوقع** – عند العمل على مشاريع ضخمة جدًا، فكر في استدعاء `project.setSaveOptions(new ProjectSaveOptions())` لتمكين الحفظ التدريجي.  

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Tasks for Java مع مكتبات Java أخرى؟**  
ج: نعم، يتكامل Aspose.Tasks for Java بسلاسة مع أي بيئة Java، بما في ذلك Spring و Hibernate و Apache POI.

**س: هل Aspose.Tasks for Java مناسب لتطبيقات إدارة المشاريع على نطاق واسع؟**  
ج: بالتأكيد. تم تصميم المكتبة للتعامل مع مشاريع تحتوي على آلاف المهام وتدعم البث لتقليل استهلاك الذاكرة.

**س: هل هناك أي اعتبارات ترخيص لاستخدام Aspose.Tasks for Java في مشروع تجاري؟**  
ج: نعم، تحتاج إلى ترخيص تجاري صالح. يمكنك مراجعة التفاصيل على [موقع Aspose.Tasks](https://purchase.aspose.com/buy).

**س: كيف يمكنني الحصول على الدعم أو المساعدة بخصوص Aspose.Tasks for Java؟**  
ج: زر [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15) للحصول على مساعدة المجتمع، أو افتح تذكرة دعم عبر حساب Aspose الخاص بك.

**س: هل يمكنني تجربة Aspose.Tasks for Java قبل الشراء؟**  
ج: نعم، يمكنك الوصول إلى نسخة تجريبية مجانية عبر صفحة [تجربة Aspose.Tasks المجانية](https://releases.aspose.com/).

**آخر تحديث:** 2026-09-30  
**تم الاختبار مع:** Aspose.Tasks for Java 24.10  
**المؤلف:** Aspose  

```java
project.save(dataDir + "PlainTextExtendedAttribute_out.mpp", SaveFileFormat.Mpp);
```

## دروس ذات صلة

- [الأعمدة المخصصة والسمات الموسعة في إدارة مشاريع Java](/tasks/java/project-management/extended-attributes/)
- [قراءة السمات الموسعة للمهام باستخدام Aspose.Tasks for Java](/tasks/java/task-properties/extended-task-attributes/)
- [كيفية إنشاء مشروع aspose.tasks – تعيين سمات مهام جديدة](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}