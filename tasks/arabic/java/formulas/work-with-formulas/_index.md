---
date: 2026-10-05
description: تعلم كيفية إنشاء مشروع اختبار وحساب عدد الأيام بين التواريخ باستخدام
  Aspose.Tasks for Java، إضافة حقل مخصص، ومعالجة ملفات MPP بكفاءة.
keywords:
- create test project
- calculate days between dates
- define extended attribute
- set deadline Aspose.Tasks
- manipulate mpp file
lastmod: 2026-10-05
linktitle: العمل مع الصيغ في Aspose.Tasks
og_description: إنشاء مشروع اختبار وحساب عدد الأيام بين التواريخ باستخدام Aspose.Tasks
  for Java. يوضح هذا الدليل كيفية إضافة حقل مخصص، وتحديد مواعيد نهائية للمهام، وحفظ
  المشروع كملف MPP.
og_image_alt: 'Aspose.Tasks Java tutorial: create test project and calculate date
  differences'
og_title: إنشاء مشروع اختبار وحساب عدد الأيام بين التواريخ
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to create test project and calculate days between dates using
    Aspose.Tasks for Java, add a custom field, and manipulate MPP files efficiently.
  headline: Create test project and calculate days between dates
  type: TechArticle
- description: Learn how to create test project and calculate days between dates using
    Aspose.Tasks for Java, add a custom field, and manipulate MPP files efficiently.
  name: Create test project and calculate days between dates
  steps:
  - name: Create a test project with a custom field
    text: We begin by **creating a test project** and adding a custom field that will
      later hold our formula result. > *Pro tip:* `CreateTestProjectWithCustomField()`
      is a helper method that builds a minimal schedule and registers an extended
      attribute ready for formula assignment.
  - name: Define an extended attribute (add custom field)
    text: Next, we **define an extended attribute** – essentially the custom field
      – and give it a friendly alias. This is where we **add custom field** logic.
      - **Alias** makes the field readable in Project. - **Formula** calculates the
      number of days between a task’s *Finish* date and its *Deadline* – the c
  - name: Set deadline for a task (add deadline task & set task deadline)
    text: Now we **add deadline task** data by setting the *Deadline* property on
      a specific task. - The `Calendar` instance defines the exact deadline moment.
      - `set(Tsk.DEADLINE, …)` **sets task deadline** for the chosen task.
  - name: Save the project (manipulate Microsoft Project file)
    text: Finally, we **manipulate Microsoft Project** by persisting the changes to
      an MPP file. You can open `SaveFile.mpp` in Microsoft Project to see the custom
      field, formula result, and deadline reflected in the schedule.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks provides APIs for .NET, Java, and other platforms, allowing
      you to manipulate Microsoft Project files in the language of your choice.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely. Download a fully functional trial from the [Aspose.Tasks download
      page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks?
  - answer: The official docs are hosted at [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).
    question: Where can I find detailed documentation for Aspose.Tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) to
      ask questions and share experiences with the community.
    question: How can I get support for Aspose.Tasks?
  - answer: A temporary license is available for short‑term testing; you can request
      one from the [temporary license request page](https://purchase.aspose.com/temporary-license/).
    question: Do I need a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project automation
- custom fields
- date calculations
title: إنشاء مشروع اختبار وحساب عدد الأيام بين التواريخ
url: /ar/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء مشروع اختبار وحساب عدد الأيام بين التواريخ

في هذا الدرس سوف **تنشئ مشروع اختبار** وتقوم **بحساب عدد الأيام بين التواريخ** عن طريق إضافة حقل مخصص، تعريف سمة موسعة، وتطبيق صيغة Microsoft Project عبر مكتبة Aspose.Tasks للغة Java. سواء كنت بحاجة إلى إنشاء جداول زمنية، حساب مواعيد نهائية، أو أتمتة التقارير، تتيح لك Aspose.Tasks تعديل بيانات Project برمجياً دون الحاجة لتثبيت سطح المكتب، وتدعم أكثر من 50 تنسيق إدخال وإخراج وتتعامل مع ملفات مئات الصفحات في وضع توفير الذاكرة.

## إجابات سريعة
- **ما الذي يغطيه الدرس؟** يوضح كيفية إنشاء مشروع اختبار، تعريف سمة موسعة، تعيين موعد نهائي لمهمة، واستخدام صيغة لحساب عدد الأيام بين التواريخ.  
- **ما المكتبة المطلوبة؟** Aspose.Tasks for Java (أحدث إصدار).  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تكفي للتطوير؛ يلزم الحصول على ترخيص تجاري للاستخدام في الإنتاج.  
- **ما بيئة التطوير المتكاملة التي يمكنني استخدامها؟** أي بيئة Java IDE (IntelliJ IDEA، Eclipse، VS Code) تدعم JDK 8+.  
- **كم يستغرق تنفيذ هذا الدرس؟** تقريباً 10‑15 دقيقة لنسخ الشيفرة وتشغيلها.

## ما هو “حساب عدد الأيام بين التواريخ” في Aspose.Tasks؟
في Aspose.Tasks، الصيغة هي سلسلة نصية يمكنها الإشارة إلى حقول المهمة وإجراء عمليات حسابية. الصيغة `[Deadline] - [Finish]` هي الصيغة التي يستخدمها Aspose.Tasks لإرجاع الفرق العددي بالأيام بين حقلين تاريخيين. يتم تخزين النتيجة كقيمة عددية تمثل عدد الأيام الكاملة، ويمكنك عرضها في حقل مخصص أو استخدامها في حسابات أخرى.

## لماذا تستخدم Aspose.Tasks لحساب عدد الأيام بين التواريخ؟
توفر Aspose.Tasks **تغطية كاملة لواجهة برمجة التطبيقات** لكل خاصية في Project، Task، وResource، وتعمل على Windows وLinux وmacOS، ولا **تتطلب تثبيت Microsoft Project أو Office**. يمكن للمحرك معالجة مشاريع تحتوي على **أكثر من 500 مهمة** في أقل من ثانية على خوادم عادية، مما يجعله مثالياً لأنابيب CI، حاويات Docker، ومعالجة الدُفعات ذات الحجم الكبير.

## كيفية تعيين الموعد النهائي لمهمة
`java.util.Calendar` هي فئة Java تمثل لحظة معينة في الزمن. يمكنك تعيين موعد نهائي عن طريق إسناد قيمة `java.util.Calendar` إلى الحقل `Tsk.DEADLINE` للمهمة. بعد إنشاء كائن Calendar، حدد السنة والشهر واليوم للموعد المطلوب، ثم استدعِ `task.set(Tsk.DEADLINE, calendar);`. يُخزن الموعد النهائي في ملف المشروع ويمكن استخدامه في صيغ مثل `[Deadline] - [Finish]`.

## كيفية تعريف السمة الموسعة
السمة الموسعة هي حقل مخصص يخزن نتيجة الصيغة الخاصة بك. تقوم بإنشائها مرة واحدة، تعطيها اسمًا وصفيًا، وتربط التعبير `[Deadline] - [Finish]` بحيث تحسب كل مهمة الفاصل الزمني تلقائيًا. أنشئها بإنشاء كائن `ExtendedAttribute`، ضبط Alias، إسناد الصيغة، وإضافتها إلى مجموعة المشروع.

## المتطلبات المسبقة
قبل البدء، تأكد من وجود ما يلي:

- **Java Development Kit (JDK) 8+** – حمّلها من موقع Oracle أو استخدم OpenJDK.  
- **Aspose.Tasks for Java** – احصل على أحدث ملف JAR من [صفحة تحميل Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/) وأضفه إلى مسار الفئات في مشروعك أو إلى تبعيات Maven/Gradle.

## استيراد الحزم
أولاً، استورد الفئات التي سنحتاجها:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## دليل خطوة بخطوة

### الخطوة 1: إنشاء مشروع اختبار مع حقل مخصص
نبدأ بـ **إنشاء مشروع اختبار** وإضافة حقل مخصص سيحمل لاحقًا نتيجة الصيغة.

```java
Project project = CreateTestProjectWithCustomField();
```

> *نصيحة احترافية:* `CreateTestProjectWithCustomField()` هي طريقة مساعدة تبني جدولًا زمنيًا بسيطًا وتسجيل سمة موسعة جاهزة لتعيين الصيغة.

### الخطوة 2: تعريف سمة موسعة (إضافة حقل مخصص)
بعد ذلك، **نعرّف سمة موسعة** – أي الحقل المخصص – ونعطيها اسمًا وصفيًا. هنا نضيف منطق الحقل المخصص.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** يجعل الحقل قابلًا للقراءة في Project.  
- **Formula** تحسب عدد الأيام بين تاريخ *Finish* للمهمة وتاريخ *Deadline* – جوهر **حساب عدد الأيام بين التواريخ**.

### الخطوة 3: تعيين الموعد النهائي لمهمة (إضافة مهمة موعد نهائي وتعيين موعد نهائي للمهمة)
الآن **نضيف بيانات مهمة الموعد النهائي** عن طريق ضبط خاصية *Deadline* لمهمة معينة.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- كائن `Calendar` يحدد لحظة الموعد النهائي بدقة.  
- `set(Tsk.DEADLINE, …)` **يضبط موعد نهائي للمهمة** للمهمة المختارة.

### الخطوة 4: حفظ المشروع (معالجة ملف Microsoft Project)
أخيرًا، **نقوم بمعالجة Microsoft Project** عن طريق حفظ التغييرات في ملف MPP.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

يمكنك فتح `SaveFile.mpp` في Microsoft Project لرؤية الحقل المخصص، نتيجة الصيغة، والموعد النهائي المنعكس في الجدول الزمني.

## المشكلات الشائعة والحلول
| المشكلة | الحل |
|-------|----------|
| **Formula not evaluating** | تأكد من أن سلسلة `Formula` للسمة تستخدم أسماء الحقول الصحيحة (مثل `[Deadline]`، `[Finish]`). |
| **Task not found** | تحقق من وجود معرف المهمة (`1` في المثال)؛ استخدم `project.getRootTask().getChildren().size()` للتصحيح. |
| **License exception** | طبّق ترخيص Aspose.Tasks صالح قبل استدعاء أي من طرق API (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Tasks مع لغات برمجة أخرى؟**  
ج: نعم، توفر Aspose.Tasks واجهات برمجة تطبيقات لـ .NET، Java، ومنصات أخرى، مما يتيح لك تعديل ملفات Microsoft Project باللغة التي تفضلها.

**س: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Tasks؟**  
ج: بالتأكيد. حمّل نسخة تجريبية كاملة الوظائف من [صفحة تحميل Aspose.Tasks](https://releases.aspose.com/).

**س: أين يمكنني العثور على وثائق مفصلة لـ Aspose.Tasks؟**  
ج: الوثائق الرسمية مستضافة على [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).

**س: كيف يمكنني الحصول على دعم لـ Aspose.Tasks؟**  
ج: زر [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15) لطرح الأسئلة ومشاركة التجارب مع المجتمع.

**س: هل أحتاج إلى ترخيص مؤقت للتقييم؟**  
ج: يتوفر ترخيص مؤقت للاختبار قصير‑المدى؛ يمكنك طلبه من [صفحة طلب الترخيص المؤقت](https://purchase.aspose.com/temporary-license/).

**آخر تحديث:** 2026-10-05  
**تم الاختبار مع:** Aspose.Tasks for Java 24.12 (أحدث إصدار وقت الكتابة)  
**المؤلف:** Aspose

## دروس ذات صلة

- [كيفية إنشاء ملف MPP – إنشاء وحفظ مشروع فارغ بتنسيق MPP باستخدام Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [تعيين تاريخ بدء المشروع في MS Project باستخدام Aspose.Tasks for Java](/tasks/java/project-properties/write-project-info/)
- [كيفية إنشاء سمة موسعة في Java مع Aspose.Tasks](/tasks/java/resource-management/extended-resource-attributes/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}