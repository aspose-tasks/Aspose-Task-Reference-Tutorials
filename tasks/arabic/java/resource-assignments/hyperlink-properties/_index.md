---
date: 2026-06-05
description: تعلم كيفية تعيين خصائص hyperlink لتخصيصات الموارد في Aspose.Tasks لـ
  Java، مع توضيح **كيفية تعيين hyperlink** وتحسين التعاون.
keywords:
- how to set hyperlink
- validate hyperlink java
- Aspose.Tasks hyperlink
- resource assignment hyperlink
- Java project hyperlink
linktitle: إدارة خصائص hyperlink لتخصيصات الموارد في Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to set hyperlink properties for resource assignments in Aspose.Tasks
    for Java, showing exactly **how to set hyperlink** and improve collaboration.
  headline: How to Set Hyperlink Properties for Assignments in Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, you can repeat the assignment process for each URL, setting different
      `HYPERLINK_ADDRESS` values on the same `Asn` object.
    question: Can I add multiple hyperlinks to a single resource assignment?
  - answer: Aspose.Tasks focuses on data management; visual styling is handled by
      the client application that renders the project file.
    question: Is it possible to customize the appearance of hyperlinks in Aspose.Tasks?
  - answer: The library does not impose strict length limits, but keeping URLs under
      2,000 characters maintains compatibility with most browsers and tools.
    question: Are there any limitations on the length of hyperlinks in Aspose.Tasks?
  - answer: Yes, assign `null` or an empty string to the `HYPERLINK`, `HYPERLINK_ADDRESS`,
      and `HYPERLINK_SUB_ADDRESS` fields to clear them.
    question: Can I remove hyperlinks from resource assignments programmatically?
  - answer: The library stores hyperlink data but does not validate URLs automatically;
      you should implement custom validation logic in Java.
    question: Does Aspose.Tasks support hyperlink validation?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: كيفية تعيين خصائص hyperlink للتخصيصات في Aspose.Tasks
url: /ar/java/resource-assignments/hyperlink-properties/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تعيين خصائص الارتباط التشعبي للتعيينات في Aspose.Tasks

## مقدمة
في هذا الدليل ستكتشف **كيفية تعيين خصائص الارتباط التشعبي** على تعيينات الموارد باستخدام Aspose.Tasks for Java. بنهاية البرنامج التعليمي ستكون قادرًا على إرفاق عناوين URL قابلة للنقر، والتحقق من صحتها، والاستعلام عنها برمجيًا—مما يجعل ملفات المشروع مركزًا للمعلومات السياقية التي يمكن لفريقك الاعتماد عليها.

## إجابات سريعة
- **ما الذي يفعله “set hyperlink”?** يرفق عنوان URL قابل للنقر (وعنوان فرعي اختياري) إلى تعيين مورد، محولًا النص العادي إلى رابط تنقل مباشر.  
- **أي فئة تخزن بيانات الارتباط التشعبي؟** توفر الفئة `Asn` الحقول `HYPERLINK` و`HYPERLINK_ADDRESS` و`HYPERLINK_SUB_ADDRESS`.  
- **هل أحتاج إلى ترخيص لاستخدام هذه الميزة؟** يلزم وجود ترخيص Aspose.Tasks صالح للاستخدام في الإنتاج؛ النسخة التجريبية المجانية تعمل للاختبار.  
- **هل يمكنني التحقق من صحة الارتباط التشعبي في Java؟** نعم—استخدم `java.net.URL` أو Apache Commons Validator قبل تعيينه.  
- **هل هذا النهج متوافق مع أي مشروع Java؟** بالتأكيد؛ يعمل مع أي مشروع Java يتضمن مكتبة Aspose.Tasks.

## ما هو “كيفية تعيين الارتباط التشعبي” في Aspose.Tasks؟
**تعيين الارتباط التشعبي يعني ربط عنوان URL (وباختياري عنوان فرعي) بتعيين مورد بحيث يمكن لأصحاب المصلحة في المشروع الانتقال فورًا إلى صفحات الويب ذات الصلة أو المستندات أو أقسام المشروع الداخلية مباشرةً من عرض التعيين.** هذه القدرة تُسهل التواصل وتقلل الحاجة إلى جداول البيانات المرجعية الخارجية.

## لماذا إضافة ارتباط تشعبي إلى تعيينات المهام؟
إرفاق الروابط التشعبية إلى التعيينات **يحسن التعاون من خلال السماح لأعضاء الفريق بالنقر للوصول إلى المواصفات أو التصاميم أو تذاكر متعقّب المشكلات دون مغادرة ملف المشروع**. كما أنه يُركز المعلومات—كل عنوان URL ذي صلة يعيش داخل المشروع، مما يخلق مصدرًا موحدًا للحقائق وسجل تدقيق يمكن الاستعلام عنه أو تصديره للتقارير. الفائدة المكمّنة: يمكن لـ Aspose.Tasks التعامل مع مشاريع تحتوي على **حتى 10,000 مهمة و5,000 مورد مع الحفاظ على وصول دون ثانية إلى حقول الارتباط التشعبي**.

## المتطلبات المسبقة
- معرفة أساسية ببرمجة Java.  
- تثبيت Java Development Kit (JDK) الإصدار 8 أو أحدث.  
- إضافة مكتبة Aspose.Tasks for Java إلى مسار الفئات (classpath) في مشروعك.  
- بيئة تطوير متكاملة (IDE) مثل IntelliJ IDEA أو Eclipse لتحرير وتشغيل الكود.  
- (اختياري) ملف ترخيص Aspose.Tasks صالح لبُنى الإنتاج.

## استيراد الحزم
تقع الفئات `Project` و`Task` و`Resource` و`Asn` في مساحة الاسم `com.aspose.tasks`. استوردها قبل البدء في العمل مع الـ API.

الفئة `Project` هي الكائن الأعلى مستوى في Aspose.Tasks الذي يمثل ملف مشروع كامل في الذاكرة.  
الفئة `Task` تمثل عنصر عمل واحد داخل هيكل المشروع.  
الفئة `Resource` تُعرّف شخصًا أو معدًّا أو مادة يمكن تعيينها للمهام.  
الفئة `Asn` تمثل الرابط بين `Task` و`Resource` وتخزن خصائص على مستوى التعيين، بما في ذلك حقول الارتباط التشعبي.

## الخطوة 1: إنشاء كائن مشروع
حمّل أو أنشئ ملف مشروع جديد. هذا هو الحاوية لجميع الكائنات اللاحقة.

## الخطوة 2: إضافة مهمة إلى المشروع
أنشئ مهمة ستستقبل لاحقًا الارتباط التشعبي عبر تعيينها.

## الخطوة 3: إضافة مورد
عرّف موردًا (مثل مطور أو قطعة من المعدات) ستقوم بتعيينه للمهمة.

## الخطوة 4: إنشاء تعيين مورد
اربط المهمة بالمورد معًا، مما ينتج كائن `Asn` يحمل بيانات خاصة بالتعيين.

## الخطوة 5: تعيين خصائص الارتباط التشعبي
عيّن عنوان الارتباط التشعبي والعنوان الفرعي الاختياري لكائن `Asn`. يمكنك أيضًا تعيين نص العرض عبر الحقل `HYPERLINK`.

## الخطوة 6: طباعة خصائص الارتباط التشعبي
استرجع واعرض قيم الارتباط التشعبي المخزنة لتأكيد أن التعيين تم تكوينه بشكل صحيح.

## الخطوة 7: إكمال العملية
اعرض رسالة ودية تشير إلى أن إعداد الارتباط التشعبي اكتمل دون أخطاء.

## كيف يمكنني التحقق من صحة الارتباط التشعبي في Java؟
**تحقق من صحة عنوان URL قبل تعيينه بإنشاء كائن `java.net.URL`؛ إذا ألقى المُنشئ استثناء `MalformedURLException`، فإن السلسلة ليست عنوان URL مُشكلًا بشكل صحيح.** هذا الفحص البسيط يمنع أخطاء وقت التشغيل ويضمن أن الروابط القابلة للوصول فقط هي المخزنة في ملف المشروع.

## المشكلات الشائعة والحلول
- **تنسيق URL غير صالح:** تحقق من صحة URL باستخدام `java.net.URL` قبل تعيينه لتجنب أخطاء وقت التشغيل.  
- **قيمة الارتباط التشعبي فارغة:** تأكد من تعيين جميع الخصائص الثلاثة (`HYPERLINK`، `HYPERLINK_ADDRESS`، `HYPERLINK_SUB_ADDRESS`) إذا كنت تحتاجها؛ وإلا، عيّن القيم غير المستخدمة إلى `null` أو سلسلة فارغة.  
- **الترخيص غير موجود:** إذا تلقيت أخطاء ترخيص، تحقق من تحميل ملف ترخيص Aspose.Tasks بشكل صحيح قبل إنشاء كائن `Project`.

## الأسئلة المتكررة

**س: هل يمكنني إضافة روابط تشعبية متعددة إلى تعيين مورد واحد؟**  
ج: نعم، يمكنك تكرار عملية التعيين لكل عنوان URL، مع تعيين قيم `HYPERLINK_ADDRESS` مختلفة على نفس كائن `Asn`.

**س: هل يمكن تخصيص مظهر الروابط التشعبية في Aspose.Tasks؟**  
ج: يركز Aspose.Tasks على إدارة البيانات؛ يتم التعامل مع التنسيق البصري من قبل تطبيق العميل الذي يعرض ملف المشروع.

**س: هل هناك أي قيود على طول الروابط التشعبية في Aspose.Tasks؟**  
ج: لا تفرض المكتبة حدودًا صارمة للطول، لكن الحفاظ على عناوين URL أقل من 2,000 حرف يضمن التوافق مع معظم المتصفحات والأدوات.

**س: هل يمكنني إزالة الروابط التشعبية من تعيينات الموارد برمجيًا؟**  
ج: نعم، عيّن `null` أو سلسلة فارغة للحقول `HYPERLINK` و`HYPERLINK_ADDRESS` و`HYPERLINK_SUB_ADDRESS` لمسحها.

**س: هل يدعم Aspose.Tasks التحقق من صحة الروابط التشعبية؟**  
ج: تقوم المكتبة بتخزين بيانات الروابط التشعبية لكنها لا تتحقق من صحة عناوين URL تلقائيًا؛ يجب عليك تنفيذ منطق تحقق مخصص في Java.

**س: كيف يتناسب هذا مع استراتيجية الروابط التشعبية لمشروع Java أكبر؟**  
ج: يخلق تجميع عناوين URL داخل ملف المشروع خريطة روابط تشعبية قابلة للبحث “java project hyperlink map” يمكن تصديرها أو تدقيقها أو دمجها مع مولدات الوثائق.

## الخاتمة
باتباعك هذه الخطوات، أصبحت الآن تعرف **كيفية تعيين خصائص الارتباط التشعبي** لتعيينات الموارد في Aspose.Tasks for Java، وكيفية التحقق من صحة تلك العناوين، ولماذا تعزز هذه الممارسة التعاون وتتبع المعلومات. دمج النمط في خطوط أتمتة مشروعك الأكبر للحفاظ على ربط كل صاحب مصلحة بالمعلومات الصحيحة في الوقت المناسب.

---

**آخر تحديث:** 2026-06-05  
**تم الاختبار باستخدام:** Aspose.Tasks for Java 24.12  
**المؤلف:** Aspose

## دروس ذات صلة

- [إنشاء تعيينات موارد في Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [كيفية إضافة ملاحظات إلى تعيينات الموارد في Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)
- [إدارة ميزانية التعيين Java باستخدام Aspose.Tasks](/tasks/java/resource-assignments/assignment-budget/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

```java
Project prj = new Project();
```

```java
Task task = prj.getRootTask().getChildren().add("Task 1");
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```

```java
Resource resource = prj.getResources().add("Resource 1");
```

```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```

```java
assignment.set(Asn.HYPERLINK, "Click to visit our site");
assignment.set(Asn.HYPERLINK_ADDRESS, "https://products.aspose.com");
assignment.set(Asn.HYPERLINK_SUB_ADDRESS, "/total/net");
```

```java
System.out.println("Hyperlink: " + assignment.get(Asn.HYPERLINK));
System.out.println("Hyperlink Address: " + assignment.get(Asn.HYPERLINK_ADDRESS));
System.out.println("Hyperlink Sub Address: " + assignment.get(Asn.HYPERLINK_SUB_ADDRESS));
```

```java
System.out.println("Process completed Successfully");
```