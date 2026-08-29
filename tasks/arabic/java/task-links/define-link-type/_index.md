---
date: 2026-08-29
description: تعلم كيفية تعيين Link Types وإدارة Task Dependencies باستخدام Aspose.Tasks
  for Java في دليل خطوة بخطوة.
keywords:
- how to set link
- Aspose.Tasks link types
- Java task dependencies
lastmod: 2026-08-29
linktitle: كيفية تعيين Link Types في Aspose.Tasks for Java
og_description: تعلم كيفية تعيين Link Types وإدارة Task Dependencies باستخدام Aspose.Tasks
  for Java. دليل خطوة بخطوة للمطورين.
og_image_alt: Screenshot of Aspose.Tasks Java code setting task link types
og_title: كيفية تعيين Link Types في Aspose.Tasks for Java
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to set link types and manage task dependencies with Aspose.Tasks
    for Java in a step‑by‑step tutorial.
  headline: How to Set Link Types in Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates with standard Java SE, Java EE, and Android
      development kits without additional dependencies.
    question: Is Aspose.Tasks compatible with different Java environments?
  - answer: Absolutely. The `TaskLinkType` enum provides four standard types, and
      you can combine them with lag values to model complex schedules.
    question: Can I customize link types based on my project requirements?
  - answer: Refer to the [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/)
      for in‑depth guidance, API reference, and code samples.
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Visit the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to acquire a temporary license for testing purposes.
    question: How can I obtain a temporary license for Aspose.Tasks?
  - answer: Join the Aspose.Tasks community on the [support forum](https://forum.aspose.com/c/tasks/15)
      for assistance and discussions.
    question: Where can I get support for Aspose.Tasks‑related queries?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project management
- task link
title: كيفية تعيين Link Types في Aspose.Tasks for Java
url: /ar/java/task-links/define-link-type/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تعيين أنواع الروابط في Aspose.Tasks لـ Java

## مقدمة
إذا كنت تتساءل **كيفية تعيين الرابط** بين المهام أثناء *إدارة تبعيات المهام* في مشروع، فقد وصلت إلى المكان الصحيح. في هذا البرنامج التعليمي سنستعرض إنشاء مشروع جديد، إضافة مهام، وتحديد نوع الرابط (Start‑to‑Start، Finish‑to‑Start، إلخ) باستخدام Aspose.Tasks للغة Java. في النهاية ستشعر بالثقة في تخصيص علاقات المهام لتتناسب مع احتياجات الجدولة الواقعية وسترى كيف يتعامل API مع خطط واسعة النطاق تصل إلى 10,000 مهمة.

## إجابات سريعة
- **ما هو الصنف الذي يمثل التبعية؟** `TaskLink` هو الكائن الأساسي الذي يُنمذج رابطًا بين مهمتين.  
- **أي تعداد يحدد نوع العلاقة؟** `TaskLinkType` (مثال: `StartToStart`، `FinishToStart`).  
- **هل يمكنني قراءة أنواع الروابط الموجودة؟** نعم – قم بالتكرار عبر `Project.getTaskLinks()` واستدعِ `getLinkType()`.  
- **هل أحتاج إلى ترخيص لهذا الكود؟** الترخيص المؤقت يعمل للاختبار؛ الترخيص الكامل مطلوب للإنتاج.  
- **هل هذا متوافق مع Java 8+؟** بالتأكيد – يدعم Aspose.Tasks Java 8 حتى Java 21، ويغطي 13 إصدارًا رئيسيًا.

## ما هو رابط المهمة؟
**رابط المهمة** يُنمذج تبعية بين مهمتين في جدول المشروع.  
يمكنك إنشاء أو تعديل أو حذف `TaskLink` لتعكس علاقات السلف‑اللاحق، مما يتيح للجدول الزمني حساب تواريخ البدء والانتهاء تلقائيًا.

## لماذا نستخدم أنواع روابط Aspose.Tasks؟
يدعم Aspose.Tasks **أكثر من 30 صيغة إدخال وإخراج** ويمكنه معالجة المشاريع التي تحتوي على **حتى 10,000 مهمة** دون تحميل الملف بالكامل إلى الذاكرة. تضمن هذه القدرة المكمّنة الأداء السريع حتى للخطط على مستوى المؤسسات، وتحافظ المكتبة على جميع ميزات Microsoft Project مثل الحقول المخصصة وتعيينات الموارد.

## المتطلبات المسبقة
- **بيئة تطوير Java** – JDK 8 أو أحدث مثبت ومُكوَّن.  
- **مكتبة Aspose.Tasks** – قم بتنزيل أحدث JAR من [download link](https://releases.aspose.com/tasks/java/).  
- **دليل المستندات** – أنشئ مجلدًا على جهازك حيث ستحفظ ملفات المشروع النموذجية.

## استيراد الحزم
نبدأ باستيراد الفئات الأساسية من Aspose.Tasks. هذا يجهز بيئة التطوير المتكاملة (IDE) للتعرف على استدعاءات API التي سنستخدمها لاحقًا.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkCollection;
import com.aspose.tasks.TaskLinkType;
```

## كيفية تعيين أنواع الروابط في Aspose.Tasks للغة Java؟
حمّل نسخة جديدة من كائن `Project`، أضف مهمتين، ثم أنشئ `TaskLink` بالنوع المطلوب `TaskLinkType`. يتيح لك هذا النمط المكوّن من خطوتين تعريف أي من الأنواع الأربعة القياسية للتبعيات في استدعاء واحد. `Project` يمثل ملف المشروع بالكامل وجدوله. `Task` هو عنصر عمل فردي داخل المشروع. `TaskLink` يربط مهمة سلفية بمهمة لاحقة. `TaskLinkType` هو تعداد يحدد العلاقة (Start‑to‑Start، Finish‑to‑Start، إلخ).

### الخطوة 1: تعيين نوع الرابط
`TaskLink` يمثل تبعية بين مهمتين، بينما `TaskLinkType` يُعدد أنواع العلاقات الممكنة مثل `StartToStart`. في هذه الخطوة ننشئ مشروعًا جديدًا، نضيف مهمتين، ونربطهما باستخدام علاقة **Start‑to‑Start**.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";

Project project = new Project();
Task pred = project.getRootTask().getChildren().add("Task 1");
Task succ = project.getRootTask().getChildren().add("Task 2");
TaskLink link = project.getTaskLinks().add(pred, succ);
link.setLinkType(TaskLinkType.StartToStart);
```

> **نصيحة احترافية:** يمكنك استبدال `StartToStart` بـ `FinishToStart` أو `StartToFinish` أو `FinishToFinish` حسب التبعية التي تحتاج إلى **إدارة تبعيات المهام**.

### الخطوة 2: الحصول على نوع الرابط
`Project.getTaskLinks()` يُعيد مجموعة من جميع كائنات `TaskLink` في الجدول. من خلال تكرار هذه المجموعة يمكنك قراءة `TaskLinkType` لكل رابط والتحقق من أن العلاقة الصحيحة تم حفظها.

```java
Project project = new Project(dataDir + "project.xml");
TaskLinkCollection allLinks = project.getTaskLinks();
for (TaskLink tskLink : allLinks) {
    System.out.println(tskLink.getLinkType());
}
```

ستظهر وحدة التحكم قيمًا مثل `StartToStart`، `FinishToStart`، إلخ، لتؤكد نوع الرابط الذي قمت بتعيينه مسبقًا.

## المشكلات الشائعة والحلول
- **NullPointerException عند إضافة الروابط** – تأكد من إضافة كل من المهمات السلفية واللاحقة إلى المشروع قبل إنشاء `TaskLink`.  
- **نوع الرابط غير صحيح بعد الحفظ** – احرص دائمًا على استدعاء `project.save("output.mpp")` (أو أي صيغة مدعومة أخرى) بعد تعيين نوع الرابط لحفظ التغييرات.  
- **الترخيص غير موجود** – ضع ملف ترخيص Aspose.Tasks في مسار الفئة (classpath) الخاص بالمشروع وحمّله باستخدام `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`.

## الأسئلة المتكررة

**س: هل Aspose.Tasks متوافق مع بيئات Java المختلفة؟**  
ج: نعم، يدمج Aspose.Tasks مع Java SE القياسي، Java EE، ومجموعات تطوير Android دون تبعيات إضافية.

**س: هل يمكنني تخصيص أنواع الروابط بناءً على متطلبات مشروعي؟**  
ج: بالتأكيد. يوفر تعداد `TaskLinkType` أربعة أنواع قياسية، ويمكنك دمجها مع قيم التأخير (lag) لنمذجة جداول زمنية معقدة.

**س: أين يمكنني العثور على وثائق مفصلة لـ Aspose.Tasks للغة Java؟**  
ج: راجع [توثيق Aspose.Tasks للغة Java](https://reference.aspose.com/tasks/java/) للحصول على إرشادات متعمقة، مرجع API، وعينات من الكود.

**س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Tasks؟**  
ج: زر [صفحة الترخيص المؤقت](https://purchase.aspose.com/temporary-license/) للحصول على ترخيص مؤقت لأغراض الاختبار.

**س: أين يمكنني الحصول على دعم لاستفسارات متعلقة بـ Aspose.Tasks؟**  
ج: انضم إلى مجتمع Aspose.Tasks على [منتدى الدعم](https://forum.aspose.com/c/tasks/15) للحصول على المساعدة والنقاشات.

**س: هل يمكنني تغيير نوع الرابط بعد حفظ المشروع؟**  
ج: نعم. حمّل المشروع، استرجع `TaskLink`، استدعِ `setLinkType()` بالقيمة الجديدة من التعداد، واحفظ المشروع مرة أخرى.

**س: هل يدعم Aspose.Tasks قراءة ملفات Microsoft Project (MPP)؟**  
ج: نعم. استخدم `new Project("file.mpp")` لتحميل ملفات MPP والعمل مع روابط المهام كما في مثال XML أعلاه.

---

**آخر تحديث:** 2026-08-29  
**تم الاختبار مع:** Aspose.Tasks للغة Java 24.12  
**المؤلف:** Aspose

## دروس ذات صلة

- [إنشاء رابط مهمة عبر مشروع في Aspose.Tasks](/tasks/java/task-links/create-cross-project-task-link/)
- [تعيين تاريخ بدء المشروع وإدارة المهام الأصلية والفرعية في Aspose.Tasks](/tasks/java/task-properties/parent-child-tasks/)
- [تحميل ملف MPP في Java - إدارة خصائص المشروع مع Aspose.Tasks](/tasks/java/project-management/default-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}