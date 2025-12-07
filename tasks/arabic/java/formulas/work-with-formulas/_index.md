---
date: 2025-12-07
description: تعرّف على كيفية **إنشاء مشروع اختبار** و **إضافة حقل مخصص** أثناء التعامل
  مع ملفات Microsoft Project باستخدام Aspose.Tasks للغة Java.
language: ar
linktitle: Work with Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: إنشاء مشروع اختبار واستخدام الصيغ مع Aspose.Tasks لجافا
url: /java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء مشروع اختبار واستخدام الصيغ مع Aspose.Tasks للـ Java

## المقدمة
في هذا البرنامج التعليمي ستقوم **بإنشاء ملفات مشروع اختبار**، وإضافة حقل مخصص، والعمل مع صيغ MS Project باستخدام مكتبة Aspose.Tasks للـ Java. تجعل Aspose.Tasks من السهل **معالجة بيانات Microsoft Project** برمجياً—سواء كنت بحاجة إلى إنشاء جداول زمنية، حساب تواريخ، أو أتمتة التقارير. بنهاية الدليل ستحصل على مثال قابل للتنفيذ يعرّف سمة موسّعة، يحدد موعد نهائي لمهمة، ويحفظ المشروع كملف MPP.

## إجابات سريعة
- **ماذا يغطي البرنامج التعليمي؟** إنشاء مشروع اختبار، إضافة حقل مخصص، تعريف سمة موسّعة، وتحديد موعد نهائي للمهمة باستخدام صيغة.  
- **ما المكتبة المطلوبة؟** Aspose.Tasks للـ Java (الإصدار الأحدث).  
- **هل أحتاج إلى ترخيص؟** نسخة تجريبية مجانية تكفي للتطوير؛ الترخيص مطلوب للإنتاج.  
- **ما بيئة التطوير المتكاملة التي يمكنني استخدامها؟** أي بيئة Java IDE (IntelliJ IDEA، Eclipse، VS Code) تدعم JDK 8+.  
- **كم يستغرق التنفيذ؟** حوالي 10‑15 دقيقة لنسخ الكود وتشغيله.

## ما هو “مشروع الاختبار” في Aspose.Tasks؟
**مشروع الاختبار** هو ملف Microsoft Project خفيف الوزن يتم إنشاؤه برمجياً لعرض أو التحقق من الوظائف. يحتوي على مجموعة قليلة من المهام والموارد والحقول المخصصة التي يمكنك تعديلها دون التأثير على بيانات مشروع حقيقي.

## لماذا نستخدم Aspose.Tasks لمعالجة Microsoft Project؟
- **تغطية كاملة للـ API** – الوصول إلى كل خاصية في Project، Task، وResource.  
- **لا حاجة لتثبيت Office** – يعمل على الخوادم، خطوط CI، وحاويات Docker.  
- **متعدد المنصات** – يعمل على Windows، Linux، وmacOS بنفس كود Java.  
- **محرك صيغ قوي** – حساب التواريخ، المدد، والحقول المخصصة مباشرة داخل ملف المشروع.

## المتطلبات المسبقة
قبل البدء، تأكد من وجود ما يلي:

- **مجموعة تطوير Java (JDK) 8+** – حمّلها من موقع Oracle أو استخدم OpenJDK.  
- **Aspose.Tasks للـ Java** – احصل على أحدث ملف JAR من [صفحة تنزيل Aspose.Tasks للـ Java](https://releases.aspose.com/tasks/java/) وأضفه إلى مسار الفئة في مشروعك أو إلى تبعيات Maven/Gradle.

## استيراد الحزم
أولاً، استورد الفئات التي سنحتاجها:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## دليل خطوة بخطوة

### الخطوة 1: إنشاء مشروع اختبار مع حقل مخصص
نبدأ بـ **إنشاء مشروع اختبار** وإضافة حقل مخصص سيحمل لاحقاً نتيجة الصيغة.

```java
Project project = CreateTestProjectWithCustomField();
```

> *نصيحة محترف:* `CreateTestProjectWithCustomField()` هي طريقة مساعدة تُنشئ جدولاً زمنياً بسيطاً وتُسجّل سمة موسّعة جاهزة لتعيين الصيغة.

### الخطوة 2: تعريف سمة موسّعة (إضافة حقل مخصص)
بعد ذلك، **نعرّف السمة الموسّعة** – أي الحقل المخصص – ونمنحه اسمًا مستعارًا واضحًا. هنا يتم تنفيذ منطق **إضافة الحقل المخصص**.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **الاسم المستعار** يجعل الحقل مقروءًا في Project.  
- **الصيغة** تحسب عدد الأيام بين تاريخ *Finish* للمهمة وتاريخ *Deadline* الخاص بها.

### الخطوة 3: تحديد موعد نهائي لمهمة (إضافة مهمة موعد نهائي وتعيين الموعد النهائي)
الآن نضيف بيانات **مهمة الموعد النهائي** عن طريق تعيين خاصية *Deadline* لمهمة معينة.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- كائن `Calendar` يحدد لحظة الموعد النهائي بدقة.  
- `set(Tsk.DEADLINE, …)` **يحدد موعد نهائي للمهمة** المختارة.

### الخطوة 4: حفظ المشروع (معالجة ملف Microsoft Project)
أخيرًا، **نُعالج Microsoft Project** عن طريق حفظ التغييرات في ملف MPP.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

يمكنك فتح `SaveFile.mpp` في Microsoft Project لرؤية الحقل المخصص، نتيجة الصيغة، والموعد النهائي المعكوس في الجدول الزمني.

## المشكلات الشائعة والحلول
| المشكلة | الحل |
|-------|----------|
| **الصيغة لا تُحسب** | تأكد من أن سلسلة `Formula` للصفة تستخدم أسماء الحقول الصحيحة (مثل `[Deadline]`، `[Finish]`). |
| **المهمة غير موجودة** | تحقق من أن معرف المهمة (`1` في المثال) موجود؛ استخدم `project.getRootTask().getChildren().size()` للتصحيح. |
| **استثناء الترخيص** | طبّق ترخيص Aspose.Tasks صالح قبل استدعاء أي طريقة API (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Tasks مع لغات برمجة أخرى؟**  
ج: نعم، توفر Aspose.Tasks واجهات برمجة تطبيقات لـ .NET، Java، ومنصات أخرى، مما يتيح لك **معالجة ملفات Microsoft Project** باللغة التي تختارها.

**س: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Tasks؟**  
ج: بالتأكيد. حمّل نسخة تجريبية كاملة الوظائف من [صفحة تنزيل Aspose.Tasks](https://releases.aspose.com/).

**س: أين يمكنني العثور على وثائق مفصلة لـ Aspose.Tasks؟**  
ج: الوثائق الرسمية مستضافة على [مرجع Aspose.Tasks Java API](https://reference.aspose.com/tasks/java/).

**س: كيف يمكنني الحصول على دعم لـ Aspose.Tasks؟**  
ج: زر [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15) لطرح الأسئلة ومشاركة التجارب مع المجتمع.

**س: هل أحتاج إلى ترخيص مؤقت للتقييم؟**  
ج: ترخيص مؤقت متاح للاختبار قصير الأمد؛ يمكنك طلبه [من هنا](https://purchase.aspose.com/temporary-license/).

---

**آخر تحديث:** 2025-12-07  
**تم الاختبار مع:** Aspose.Tasks للـ Java 24.12 (أحدث إصدار وقت الكتابة)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}