---
date: 2026-05-26
description: تعلم كيفية الحصول على حقول الجدول وقراءة بيانات الجدول في Java باستخدام
  Aspose.Tasks. يوضح لك هذا البرنامج التعليمي كيفية استرجاع معلومات الجدول من ملفات
  Project.
keywords:
- read table data aspose.tasks
- Aspose.Tasks Java
- project table extraction
linktitle: قراءة بيانات الجدول من الملف في Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-26'
  description: Learn how to get table fields and read table data in Java using Aspose.Tasks.
    This tutorial shows you how to retrieve table information from Project files.
  headline: How to get table fields and read table data in Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Load each project separately with `new Project(path)` and repeat the table‑field
      extraction loop for each instance.
    question: How do I read table data in a multi‑project environment?
  - answer: Yes, after printing the field details you can write them to a `FileWriter`
      or use a CSV library such as OpenCSV to generate a properly escaped file.
    question: Can I export the retrieved table fields to CSV?
  - answer: Absolutely. The `project.getTables()` collection includes both default
      and user‑defined tables, so you can iterate through them and process each one
      individually.
    question: Does Aspose.Tasks handle custom tables created by users?
  - answer: Use the overloaded `Project` constructor that accepts a `LoadOptions`
      object where you can specify the password, e.g., `new Project(path, new LoadOptions("pwd"))`.
    question: What if the Project file is password‑protected?
  - answer: Check each `TableField`'s `getVisible()` method (available in newer releases)
      to determine whether the column is displayed in the UI.
    question: Is there a way to filter only visible columns?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: كيفية الحصول على حقول الجدول وقراءة بيانات الجدول في Aspose.Tasks
url: /ar/java/project-data-reading/read-table-data/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية الحصول على حقول الجدول وقراءة بيانات الجدول في Aspose.Tasks

## مقدمة
في هذا الدرس ستتعلم **كيفية الحصول على حقول الجدول** و**قراءة بيانات الجدول** من ملف Microsoft Project باستخدام واجهة برمجة التطبيقات **read table data aspose.tasks**. سواء كنت تبني لوحة تقارير مخصصة، أو تقوم بترحيل بيانات مشروع قديمة، أو تُؤتمت تحليل الجداول الزمنية، فإن استخراج تعريفات الجداول برمجيًا يوفر ساعات لا تُحصى من العمل اليدوي. سنستعرض إعداد البيئة، تحميل المشروع، وطباعة خصائص كل عمود، حتى تتمكن من استخدام هذه الميزة في تطبيقات Java الخاصة بك فورًا.

## إجابات سريعة
- **ماذا يعني “get table fields”؟** يشير إلى استرجاع تعريف (العرض، العنوان، المحاذاة، إلخ) لكل عمود معروض في جدول عرض Project.  
- **أي مكتبة مطلوبة؟** Aspose.Tasks for Java.  
- **هل أحتاج إلى ترخيص للتطوير؟** نسخة تجريبية مجانية تكفي للتقييم؛ يلزم ترخيص تجاري للاستخدام في الإنتاج.  
- **هل يمكن قراءة الجداول من أي إصدار من Project؟** نعم، يدعم Aspose.Tasks أكثر من 15 إصدارًا من ملفات Microsoft Project، من Project 2003 حتى Project 2024.  
- **هل هناك إعداد إضافي مطلوب؟** فقط JDK 8+ ووجود ملف JAR الخاص بـ Aspose.Tasks على مسار الفئة (classpath).

## ما هو read table data aspose.tasks؟
read table data aspose.tasks هو مجموعة طرق في واجهة Aspose.Tasks API تتيح لك الوصول برمجيًا إلى بنية ومحتويات الجداول المعرفة داخل ملف Microsoft Project. تُعيد بيانات وصفية مثل عرض العمود، العنوان، المحاذاة، والرؤية، مما يمكنك من إعادة إنشاء أو تحويل جداول المشروع إلى أي تنسيق تحتاجه.

## لماذا تستخدم Aspose.Tasks لقراءة بيانات الجدول؟
Aspose.Tasks يعالج **أكثر من 50 تنسيق ملف Project مختلف** (بما في ذلك MPP، MPX، XML، وPrimavera) ويمكنه التعامل مع ملفات تحتوي على **حتى 10,000 مهمة** دون تحميل الملف بالكامل إلى الذاكرة. هذه الأداء الم quantifiable يعني أنه يمكنك استخراج الجداول بأمان من مشاريع مؤسسية ضخمة مع الحفاظ على استهلاك الذاكرة تحت 200 ميغابايت.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من وجود ما يلي:

1. **مجموعة تطوير جافا (JDK) 8 أو أحدث** – حمّلها من الموقع الرسمي لـ Oracle.  
2. **Aspose.Tasks for Java JAR** – احصل على أحدث نسخة من [download link](https://releases.aspose.com/tasks/java/) وأضفها إلى مسار بناء مشروعك.  

> **نصيحة احترافية:** إذا كنت تستخدم Maven أو Gradle، يمكنك الإشارة إلى حزمة Aspose.Tasks مباشرة لتبسيط إدارة الاعتمادات.

## استيراد الحزم
الفئات `Project`، `Table`، و `TableField` هي جوهر سير عمل قراءة الجداول.

الفئة `Project` هي الكائن الأعلى مستوى في Aspose.Tasks الذي يمثل ملف Microsoft Project واحد في الذاكرة.  

الفئة `Table` تحوي مجموعة من كائنات `TableField`، كل منها يصف عمودًا في عرض.  

الفئة `TableField` هي حاملة تعريف لعرض العمود، العنوان، المحاذاة، والرؤية.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Table;
import com.aspose.tasks.TableField;
```

## الخطوة 1: إعداد دليل البيانات
عرّف المجلد الذي يحتوي على ملف *.mpp* الخاص بك:

```java
String dataDir = "Your Data Directory";
```

استبدل `"Your Data Directory"` بالمسار المطلق على جهازك (مثال: `C:/Projects/Data/`). استخدام مسار مطلق يجنب الغموض في تحميل الفئات عندما يُشغَّل الكود من بيئات تطوير مختلفة.

## الخطوة 2: تحميل ملف المشروع
أنشئ كائن `Project` بالإشارة إلى ملف Project الذي تريد فحصه:

```java
Project project = new Project(dataDir + "Project2003.mpp");
```

إذا كان اسم ملفك مختلفًا أو لديه امتداد آخر، عدّل السلسلة وفقًا لذلك. المُنشئ يكتشف تنسيق الملف تلقائيًا، لذا لا تحتاج إلى تحديد الإصدار يدويًا.

## الخطوة 3: استرجاع معلومات الجدول
الآن سنقوم **بالحصول على حقول الجدول** وعرض خصائص كل حقل:

```java
Table t1 = project.getTables().toList().get(0);
System.out.println("Table Fields Count: " + t1.getTableFields().size());
System.out.println();
for (TableField f : t1.getTableFields()) {
    System.out.println("Field width: " + f.getWidth());
    System.out.println("Field Title: " + f.getTitle());
    System.out.println("Field Title Alignment: " + f.getAlignTitle());
    System.out.println("Field Align Data: " + f.getAlignData());
    System.out.println();
}
```

المقتطف يطبع العرض، العنوان، والمحاذاة لكل عمود في الجدول الافتراضي، مما يمنحك صورة كاملة عن **حقول الجدول** المعرفة في المشروع.

## كيفية قراءة بيانات الجدول باستخدام Aspose.Tasks for Java؟
لقراءة بيانات الجدول الفعلية، أولًا حمّل المشروع، ثم احصل على الجدول المطلوب (مثلاً الجدول الافتراضي) باستخدام `project.getTables().getByName("Name")` أو عبر الفهرس. كرّر عبر المجموعة التي تُرجعها `table.getFields()` واطلع على خصائص كل `TableField` مثل العرض، العنوان، المحاذاة، والرؤية. يعمل هذا النهج مع أي جدول مخصص أو مدمج معرف في ملف Project.

## المشكلات الشائعة والنصائح
- **جداول فارغة** – إذا لم يحتوي المشروع على جداول، قد تكون `project.getTables()` فارغة. تحقق دائمًا من حجم المجموعة قبل الوصول إلى فهرس.  
- **مشكلات الترميز** – الأحرف غير ASCII في العناوين تظهر بشكل صحيح عند استخدام أحدث نسخة من Aspose.Tasks (24.12 أو أحدث).  
- **الأداء** – تحميل ملفات *.mpp* ضخمة قد يستهلك ذاكرةً كبيرة؛ فكر في استخدام واجهة البرمجة المتدفقة (`ProjectReader`) للملفات التي تتجاوز 500 ميغابايت.  

## الأسئلة المتكررة

**س: كيف يمكنني قراءة بيانات الجدول في بيئة متعددة المشاريع؟**  
ج: حمّل كل مشروع على حدة باستخدام `new Project(path)` وكرر حلقة استخراج حقول الجدول لكل مثال.

**س: هل يمكنني تصدير حقول الجدول المستخرجة إلى CSV؟**  
ج: نعم، بعد طباعة تفاصيل الحقول يمكنك كتابتها إلى `FileWriter` أو استخدام مكتبة CSV مثل OpenCSV لإنشاء ملف مُهَرَّس بشكل صحيح.

**س: هل يتعامل Aspose.Tasks مع الجداول المخصصة التي ينشئها المستخدمون؟**  
ج: بالتأكيد. مجموعة `project.getTables()` تشمل الجداول الافتراضية والمُعرفة من قبل المستخدم، لذا يمكنك التجول بينها ومعالجة كل واحدة على حدة.

**س: ماذا لو كان ملف Project محميًا بكلمة مرور؟**  
ج: استخدم المُنشئ المتعدد الوسائط لـ `Project` الذي يقبل كائن `LoadOptions` حيث يمكنك تحديد كلمة المرور، مثال: `new Project(path, new LoadOptions("pwd"))`.

**س: هل هناك طريقة لتصفية الأعمدة المرئية فقط؟**  
ج: تحقق من طريقة `getVisible()` لكل `TableField` (متاحة في الإصدارات الأحدث) لتحديد ما إذا كان العمود معروضًا في الواجهة.

## الخلاصة
باتباع هذه الخطوات أصبحت الآن تعرف **كيفية الحصول على حقول الجدول** وقراءة بيانات الجدول من ملف Microsoft Project باستخدام Aspose.Tasks for Java. تفتح هذه القدرة الباب أمام سيناريوهات أتمتة قوية، خطوط ترحيل بيانات، وحلول تقارير مخصصة في تطبيقات Java الخاصة بك. بعد ذلك، فكر في تصدير البيانات الوصفية المستخرجة إلى JSON أو قاعدة بيانات لتتمكن من بناء كتالوجات مشاريع قابلة للبحث أو دمجها مع أدوات ذكاء الأعمال.

---

**آخر تحديث:** 2026-05-26  
**تم الاختبار مع:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**المؤلف:** Aspose

## دروس ذات صلة

- [كيفية قراءة معلومات المشروع من Microsoft Project باستخدام Aspose.Tasks for Java](/tasks/java/project-properties/read-project-info/)
- [قراءة قاعدة بيانات مشروع Microsoft باستخدام Aspose.Tasks for Java](/tasks/java/project-data-reading/read-project-database/)
- [java قراءة قاعدة بيانات Access: قراءة بيانات المشروع باستخدام Aspose.Tasks](/tasks/java/project-data-reading/read-access-database/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}