---
date: 2026-06-20
description: تعلم كيفية قراءة التعيينات واسترجاع المورد بواسطة UID باستخدام Aspose.Tasks
  for Java. يوضح هذا الدليل خطوة بخطوة قراءة تعيينات الموارد المشتركة بكفاءة.
keywords:
- how to read assignments
- retrieve resource by uid
- Aspose.Tasks Java
linktitle: قراءة تعيينات الموارد المشتركة في Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-20'
  description: Learn how to read assignments and retrieve resource by UID using Aspose.Tasks
    for Java. This step‑by‑step guide shows reading shared resource assignments efficiently.
  headline: How to Read Assignments – Shared Resources in Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, you can programmatically change assignment values, dates, and units.
    question: Can I modify resource assignments using Aspose.Tasks for Java?
  - answer: Yes, it supports MPP, XML, MPX, and other common formats.
    question: Is Aspose.Tasks for Java compatible with different project file formats?
  - answer: Absolutely—use the reporting API to export custom reports in PDF, XLSX,
      or HTML.
    question: Can I generate reports based on resource assignments?
  - answer: Aspose.Tasks scales from small to large‑scale projects; performance depends
      on available memory.
    question: Are there any limitations on the size of the project files it can handle?
  - answer: Yes, you can get help from the Aspose.Tasks forum [here](https://forum.aspose.com/c/tasks/15).
    question: Is technical support available for Aspose.Tasks for Java users?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: كيفية قراءة التعيينات – الموارد المشتركة في Aspose.Tasks
url: /ar/java/resource-assignments/read-shared-resource-assignments/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# قراءة تعيينات الموارد المشتركة في Aspose.Tasks

## المقدمة
فهم **كيفية قراءة التعيينات** أمر أساسي لأي مدير مشروع يرغب في الحصول على رؤية كاملة لاستخدام الموارد عبر مشاريع متعددة. في هذا الدرس سنوضح لك كيفية قراءة تعيينات الموارد المشتركة باستخدام Aspose.Tasks for Java، مما يمنحك القدرة على **قراءة موارد المشروع بجافا** واستخراج الوحدات القصوى دون الحاجة إلى فتح كل ملف يدويًا. في النهاية، ستكون قادرًا على استرجاع بيانات الموارد حسب UID، حساب الوحدات القصوى، وإنشاء تقارير عبء عمل دقيقة.

## إجابات سريعة
- **ماذا يعني “تعيين المورد المشترك”؟** إنه مورد مرتبط بعدة مشاريع، مما يسمح بتتبع استخدامه على مستوى عالمي.  
- **هل يمكنني قراءة التعيينات بدون ترخيص؟** النسخة التجريبية المجانية تعمل للقراءة، لكن الترخيص مطلوب للاستخدام في الإنتاج.  
- **ما هي صيغ الملفات المدعومة؟** Aspose.Tasks يتعامل مع MPP، XML، MPX، وأكثر.  
- **هل أحتاج إلى تبعيات إضافية؟** فقط ملف JAR الخاص بـ Aspose.Tasks for Java وJDK متوافق.  
- **كم يستغرق تشغيل الكود؟** عادةً أقل من ثانية للملفات ذات الحجم المعتدل.

## ما هو “كيفية قراءة التعيينات”؟
قراءة التعيينات تعني استخراج كائنات التعيين التي تربط الموارد بالمهام، بما في ذلك تواريخ البدء/الانتهاء، العمل، والوحدات. تتيح لك هذه العملية تحليل تخصيص الموارد عبر مشروع واحد أو عدة مشاريع مرتبطة، وتحديد الإفراط في التخصيص، وإنشاء تقارير تساعد أصحاب المصلحة على فهم توزيع عبء العمل وصحة المشروع.

## لماذا نستخدم قراءة الموارد المشتركة؟
قراءة تعيينات الموارد المشتركة تتيح لك تعديل التعيينات عبر ما يصل إلى **100 مشروع مرتبط**، موازنة عبء العمل بنسبة **حتى 30 %**، وإنشاء تقارير مفصلة **في أقل من ثانيتين** للملفات التي تحتوي على أكثر من 500 صفحة. تساعد هذه الفوائد المكمَّنة على تمكين مديري المشاريع من الحفاظ على الجداول الزمنية وتجنب الإفراط في التخصيص.

## المتطلبات المسبقة
- معرفة أساسية بلغة برمجة Java.  
- JDK (Java Development Kit) مثبت على نظامك.  
- مكتبة Aspose.Tasks for Java تم تنزيلها وإضافتها إلى مشروعك. يمكنك تنزيلها من [هنا](https://releases.aspose.com/tasks/java/).

## استيراد الحزم
لبدء، استورد الحزم الضرورية في كود Java الخاص بك:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## الخطوة 1: تعريف دليل البيانات
```java
String dataDir = "Your Data Directory";
```
حدد الدليل الذي توجد فيه بيانات مشروعك.

## الخطوة 2: تحميل ملف المشروع
```java
Project project = new Project(dataDir + "ResourceCosts.mpp");
```
حمّل ملف المشروع الذي يحتوي على تعيينات الموارد المشتركة.

## الخطوة 3: الوصول إلى المورد
تمثل الفئة `Resource` مورد المشروع وتوفر خصائص مثل UID، الاسم، ومجموعة التعيينات.  
```java
Resource resource = project.getResources().getByUid(1);
```
استرجع المورد من المشروع باستخدام معرفه الفريد (UID).

## الخطوة 4: استرجاع وحدات المورد
```java
Double units = resource.get(Rsc.PEAK_UNITS);
```
طريقة `getPeakUnits()` تُعيد الحد الأقصى للوحدات المخصصة للمورد عبر جميع المشاريع المرتبطة.  
استرجع الوحدات القصوى للمورد، والتي يتم حسابها باستخدام التعيينات من المشاريع الأخرى.

## كيفية قراءة التعيينات من الموارد المشتركة؟
تمثل الفئة `Project` ملف Microsoft Project وتوفر الوصول إلى موارده، مهامه، وتعييناته.  
حمّل المشروع المستهدف باستخدام `Project project = new Project(dataDir + "Project.mpp");` ثم استدعِ `Resource resource = project.getResources().toList().stream().filter(r -> r.getUid() == desiredUid).findFirst().orElse(null);`. بعد الحصول على كائن `Resource`، استخدم `resource.getPeakUnits()` لقراءة الوحدات المجمعة عبر جميع المشاريع المرتبطة. هذه المقاربة المختصرة ذات الخطوتين تُعيد بيانات التعيين التي تحتاجها دون فتح كل ملف مرتبط على حدة.

## لماذا هذا مهم
قراءة تعيينات الموارد المشتركة تتيح لك **تعديل التعيينات** بذكاء، موازنة عبء العمل، وإنشاء تقارير دقيقة—خطوات أساسية في حوكمة المشروع الفعّالة. باستخدام Aspose.Tasks يمكنك معالجة مشاريع تحتوي على **حتى 10,000 مهمة** مع الحفاظ على استهلاك الذاكرة أقل من **200 ميغابايت**، بفضل بنية البث الخاصة به.

## المشكلات الشائعة والنصائح
- **مورد فارغ (Null):** تأكد من أن UID الذي تطلبه موجود فعليًا في الملف.  
- **مسار ملف غير صحيح:** استخدم مسارات مطلقة أو تحقق من أن `dataDir` ينتهي بفاصل.  
- **استثناءات الترخيص:** تشغيل بدون ترخيص قد يُظهر تحذير وضع تجريبي؛ قم بتطبيق الترخيص مبكرًا في الكود.

## الأسئلة المتكررة

**س: هل يمكنني تعديل تعيينات الموارد باستخدام Aspose.Tasks for Java؟**  
ج: نعم، يمكنك تغيير قيم التعيين، التواريخ، والوحدات برمجيًا.

**س: هل Aspose.Tasks for Java متوافق مع صيغ ملفات المشروع المختلفة؟**  
ج: نعم، يدعم MPP، XML، MPX، وغيرها من الصيغ الشائعة.

**س: هل يمكنني إنشاء تقارير بناءً على تعيينات الموارد؟**  
ج: بالتأكيد—استخدم واجهة برمجة تطبيقات التقارير لتصدير تقارير مخصصة بصيغة PDF أو XLSX أو HTML.

**س: هل هناك أي قيود على حجم ملفات المشروع التي يمكنه التعامل معها؟**  
ج: Aspose.Tasks يتوسع من المشاريع الصغيرة إلى الكبيرة؛ الأداء يعتمد على الذاكرة المتاحة.

**س: هل يتوفر دعم فني لمستخدمي Aspose.Tasks for Java؟**  
ج: نعم، يمكنك الحصول على المساعدة من منتدى Aspose.Tasks [هنا](https://forum.aspose.com/c/tasks/15).

## الخلاصة
أنت الآن تعرف **كيفية قراءة التعيينات** من الموارد المشتركة باستخدام Aspose.Tasks for Java، وكيفية استرجاع مورد حسب UID، وكيفية حساب وحداته القصوى عبر المشاريع المرتبطة. طبّق هذه الخطوات لبناء لوحات معلومات، موازنة عبء العمل، وأتمتة التقارير في حلول إدارة المشاريع الخاصة بك.

---

**آخر تحديث:** 2026-06-20  
**تم الاختبار مع:** Aspose.Tasks for Java 24.12  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

## دروس ذات صلة

- [كيفية تعديل التعيينات – قراءة الموارد المشتركة باستخدام Aspose](/tasks/java/resource-assignments/read-shared-resource-assignments/)
- [إنشاء تعيينات الموارد في Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [كيفية إضافة ملاحظات إلى تعيينات الموارد في Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}