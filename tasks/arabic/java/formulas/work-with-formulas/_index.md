---
date: 2026-02-13
description: تعلم كيفية حساب عدد الأيام بين التواريخ، وإنشاء مشروع اختبار، وإضافة
  حقل مخصص أثناء التعامل مع ملفات Microsoft Project باستخدام Aspose.Tasks للغة Java.
linktitle: Work with Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: احسب الأيام بين التواريخ باستخدام Aspose.Tasks لجافا
url: /ar/java/formulas/work-with-formulas/
weight: 11
---

.

Now produce final output.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# احسب عدد الأيام بين التواريخ باستخدام Aspose.Tasks للـ Java

## المقدمة
في هذا الدرس ستقوم **بحساب عدد الأيام بين التواريخ** عن طريق إنشاء مشروع اختبار، إضافة حقل مخصص، واستخدام صيغ Microsoft Project عبر مكتبة Aspose.Tasks للـ Java. سواء كنت بحاجة إلى إنشاء جداول زمنية، حساب المواعيد النهائية، أو أتمتة التقارير، تتيح لك Aspose.Tasks تعديل بيانات Project برمجياً دون الحاجة إلى تثبيت سطح المكتب. في نهاية الدليل ستحصل على مثال قابل للتنفيذ يعرّف سمة موسعة، يحدد موعداً نهائياً لمهمة، ويحفظ المشروع كملف MPP.

## إجابات سريعة
- **ما الذي يغطيه الدرس؟** إنشاء مشروع اختبار، إضافة حقل مخصص، تعريف سمة موسعة، وتعيين موعد نهائي للمهمة باستخدام صيغة لحساب عدد الأيام بين التواريخ.  
- **ما هي المكتبة المطلوبة؟** Aspose.Tasks للـ Java (أحدث نسخة).  
- **هل أحتاج إلى ترخيص؟** نسخة تجريبية مجانية تكفي للتطوير؛ الترخيص مطلوب للإنتاج.  
- **ما هو بيئة التطوير المتكاملة التي يمكنني استخدامها؟** أي بيئة Java IDE (IntelliJ IDEA، Eclipse، VS Code) تدعم JDK 8+.  
- **كم من الوقت تستغرق عملية التنفيذ؟** حوالي 10‑15 دقيقة لنسخ الكود وتشغيله.

## ما هو “calculate days between dates” في Aspose.Tasks؟
حساب عدد الأيام بين التواريخ يعني استخدام صيغة Project تطرح حقل تاريخ (مثل **Finish**) من حقل آخر (مثل **Deadline**) وتعيد الفرق العددي بالأيام. هذا مفيد لتتبع انزلاق الجدول، قياس وقت العازلة، أو إنشاء تقارير مخصصة.

## لماذا تستخدم Aspose.Tasks لحساب عدد الأيام بين التواريخ؟
- **تغطية كاملة للـ API** – الوصول إلى كل خصائص Project، Task، وResource.  
- **لا حاجة لتثبيت Office** – يعمل على الخوادم، خطوط CI، وحاويات Docker.  
- **متعدد المنصات** – يعمل على Windows، Linux، وmacOS باستخدام نفس كود Java.  
- **محرك صيغ قوي** – يتيح لك تعريف حسابات مثل `[Deadline] - [Finish]` مباشرة داخل ملف المشروع.

## كيفية تعيين موعد نهائي لمهمة
تعيين الموعد النهائي هو الخطوة الأولى قبل أن تتمكن من حساب الفاصل الزمني. يُخزن الموعد النهائي في الحقل `Tsk.DEADLINE` للمهمة ويمكن تعيينه باستخدام كائن `java.util.Calendar`.

## كيفية تعريف السمة الموسعة
السمة الموسعة هي الحقل المخصص الذي سيحمل نتيجة الصيغة الخاصة بك. تُعرّفها مرة واحدة، تعطيها اسمًا مستعارًا للقراءة، ثم تُرفق صيغة تقوم بطرح التاريخ.

## المتطلبات المسبقة
قبل البدء، تأكد من وجود ما يلي:

- **Java Development Kit (JDK) 8+** – حمّله من موقع Oracle أو استخدم OpenJDK.  
- **Aspose.Tasks للـ Java** – احصل على أحدث ملف JAR من [صفحة تنزيل Aspose.Tasks للـ Java](https://releases.aspose.com/tasks/java/) وأضفه إلى مسار الفئة في مشروعك أو إلى تبعيات Maven/Gradle.

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

> *نصيحة احترافية:* `CreateTestProjectWithCustomField()` هي طريقة مساعدة تُنشئ جدولًا زمنيًا بسيطًا وتُسجل سمة موسعة جاهزة لتعيين الصيغة.

### الخطوة 2: تعريف سمة موسعة (إضافة حقل مخصص)
بعد ذلك، **نعرّف سمة موسعة** – أي الحقل المخصص – ونمنحه اسمًا مستعارًا سهل القراءة. هنا نضيف منطق **إضافة الحقل المخصص**.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** يجعل الحقل قابلاً للقراءة في Project.  
- **Formula** تحسب عدد الأيام بين تاريخ *Finish* وتاريخ *Deadline* – جوهر *calculate days between dates*.

### الخطوة 3: تعيين موعد نهائي لمهمة (إضافة مهمة موعد نهائي وتعيين موعد نهائي للمهمة)
الآن **نضيف بيانات مهمة الموعد النهائي** عن طريق تعيين خاصية *Deadline* لمهمة معينة.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- كائن `Calendar` يحدد لحظة الموعد النهائي الدقيقة.  
- `set(Tsk.DEADLINE, …)` **يحدد موعد نهائي للمهمة** للمهمة المختارة.

### الخطوة 4: حفظ المشروع (معالجة ملف Microsoft Project)
أخيرًا، **نُعالج Microsoft Project** عن طريق حفظ التغييرات إلى ملف MPP.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

يمكنك فتح `SaveFile.mpp` في Microsoft Project لرؤية الحقل المخصص، نتيجة الصيغة، والموعد النهائي المنعكس في الجدول الزمني.

## المشكلات الشائعة والحلول
| المشكلة | الحل |
|-------|----------|
| **Formula not evaluating** | تأكد من أن سلسلة `Formula` للسمة تستخدم أسماء الحقول الصحيحة (مثل `[Deadline]`، `[Finish]`). |
| **Task not found** | تحقق من وجود معرف المهمة (`1` في المثال)؛ استخدم `project.getRootTask().getChildren().size()` للتصحيح. |
| **License exception** | طبق ترخيص Aspose.Tasks صالح قبل استدعاء أي من طرق الـ API (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Tasks مع لغات برمجة أخرى؟**  
ج: نعم، توفر Aspose.Tasks واجهات برمجة تطبيقات لـ .NET، Java، ومنصات أخرى، مما يتيح لك **معالجة ملفات Microsoft Project** باللغة التي تختارها.

**س: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Tasks؟**  
ج: بالتأكيد. حمّل نسخة تجريبية كاملة الوظائف من [صفحة تنزيل Aspose.Tasks](https://releases.aspose.com/).

**س: أين يمكنني العثور على الوثائق التفصيلية لـ Aspose.Tasks؟**  
ج: الوثائق الرسمية مستضافة على [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).

**س: كيف يمكنني الحصول على دعم لـ Aspose.Tasks؟**  
ج: زر [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15) لطرح الأسئلة ومشاركة التجارب مع المجتمع.

**س: هل أحتاج إلى ترخيص مؤقت للتقييم؟**  
ج: ترخيص مؤقت متاح للاختبار قصير‑المدى؛ يمكنك طلبه [من هنا](https://purchase.aspose.com/temporary-license/).

---

**آخر تحديث:** 2026-02-13  
**تم الاختبار مع:** Aspose.Tasks للـ Java 24.12 (أحدث نسخة وقت الكتابة)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}