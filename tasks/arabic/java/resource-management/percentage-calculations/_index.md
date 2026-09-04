---
date: 2026-06-15
description: تعلم كيفية حساب نسبة الموارد في جافا باستخدام Aspose.Tasks، بما في ذلك
  كيفية الحصول على نسبة إكمال العمل للموارد في MS Project. دليل خطوة بخطوة مع أمثلة
  على الشيفرة.
keywords:
- calculate resource percentage java
- get percent work complete
- Aspose.Tasks resource percentage
- Java project management API
linktitle: إجراء حسابات النسبة للموارد في Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to calculate resource percentage java with Aspose.Tasks,
    including how to get percent work complete for MS Project resources. Step‑by‑step
    guide with code examples.
  headline: calculate resource percentage java with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: It’s the percentage of work a resource has completed relative to its total
      assigned work.
    question: What does “resource percentage” mean?
  - answer: '`Rsc.PERCENT_WORK_COMPLETE` via the `Resource` class.'
    question: Which API call returns this value?
  - answer: A temporary or full Aspose.Tasks license is required for production use.
    question: Do I need a license?
  - answer: Yes – the API works with Spring, Hibernate, and plain Java projects.
    question: Can I use this with other Java frameworks?
  - answer: Any recent version that supports the `Rsc` enumeration (e.g., 24.x).
    question: What version of Aspose.Tasks is needed?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: حساب نسبة الموارد في جافا باستخدام Aspose.Tasks
url: /ar/java/resource-management/percentage-calculations/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# حساب نسبة الموارد في جافا باستخدام Aspose.Tasks

## مقدمة
مرحبًا! في هذا الدرس ستتعلم **كيفية حساب نسبة الموارد في جافا** باستخدام مكتبة Aspose.Tasks للغة جافا. سنستعرض استخراج *نسبة إكمال العمل* لكل مورد في ملف Microsoft Project، نشرح لماذا هذا المقياس مهم، ونظهر لك الشيفرة الدقيقة التي تحتاجها. في النهاية، ستكون قادرًا على دمج حسابات نسبة الموارد في أي حل لإدارة المشاريع مبني على جافا.

## إجابات سريعة
- **ماذا يعني “نسبة الموارد”?** إنها نسبة العمل التي أكملها المورد مقارنةً بإجمالي العمل المخصص له.  
- **ما هي استدعاءة الـ API التي تُرجع هذه القيمة؟** `Rsc.PERCENT_WORK_COMPLETE` عبر فئة `Resource`.  
- **هل أحتاج إلى ترخيص؟** يلزم الحصول على ترخيص مؤقت أو كامل لـ Aspose.Tasks للاستخدام في بيئة الإنتاج.  
- **هل يمكنني استخدامه مع أطر جافا أخرى؟** نعم – يعمل الـ API مع Spring وHibernate ومشاريع جافا العادية.  
- **ما هو إصدار Aspose.Tasks المطلوب؟** أي إصدار حديث يدعم تعداد `Rsc` (مثل 24.x).

## ما هو حساب نسبة الموارد في جافا؟
يتضمن حساب نسبة الموارد في جافا فتح ملف Microsoft Project، قراءة العمل المخصص لكل مورد، وتحديد نسبة ذلك العمل الذي تم إنجازه بالفعل. يساعد هذا المقياس مديري المشاريع على تقييم التقدم، موازنة أعباء العمل، وتحديد التأخيرات المحتملة دون الحاجة إلى حسابات يدوية.

## لماذا الحصول على نسبة إكمال العمل؟
يمنح الحصول على نسبة إكمال العمل لكل مورد رؤية فورية لمقدار الجهد المخطط الذي تم إنجازه، مما يتيح لك اكتشاف المهام المتأخرة أو الموارد غير المستغلة بسرعة. يدعم هذا الفهم اتخاذ قرارات في الوقت المناسب وتقديم تقارير حالة أكثر دقة.

## المتطلبات المسبقة
### بيئة تطوير جافا
تأكد من تثبيت مجموعة تطوير جافا (JDK). يمكنك تنزيل JDK من [هنا](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### مكتبة Aspose.Tasks
قم بتنزيل وإضافة مكتبة Aspose.Tasks إلى مشروعك من [هنا](https://releases.aspose.com/tasks/java/) وتبع تعليمات التثبيت الموجودة في الوثائق [هنا](https://reference.aspose.com/tasks/java/).

## استيراد الحزم
فئة `Resource` تمثل موردًا في المشروع وتوفر الوصول إلى حقول مثل نسبة إكمال العمل.  
قبل أن نبدأ بالبرمجة، لنستورد الحزم الضرورية لهذه الدروس:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## كيف أقوم بإعداد مسار ملف المشروع؟
حدد موقع ملف Microsoft Project الخاص بك إما بمسار مطلق أو مسار نسبي إلى دليل العمل للتطبيق. يجب أن يشير نص المسار إلى ملف *.mpp* صالح حتى يتمكن Aspose.Tasks من العثور عليه وفتحه للمعالجة الإضافية.
```java
String dataDir = "Your Data Directory";
```
استبدل `"Your Data Directory"` بالمجلد الذي يحتوي على ملف Microsoft Project الخاص بك.

## كيف أقوم بتحميل المشروع؟
أنشئ نسخة جديدة من فئة `Project` باستخدام مسار الملف الذي حددته مسبقًا. فئة `Project` تمثل ملف Microsoft Project وتوفر الوصول إلى مهامه، موارده، وبيانات المشروع الأخرى، محملةً كل شيء في الذاكرة للتحليل.
```java
Project prj = new Project(dataDir + "Software Development.mpp");
```
هذا يحمل الملف **Software Development.mpp** من الدليل الذي حددته.

## كيف أقوم بالتكرار عبر الموارد؟
استخدم طريقة `project.getResources()` للحصول على مجموعة جميع الموارد المعرفة في المشروع المحمل. قم بالتكرار عبر هذه المجموعة باستخدام حلقة `for` قياسية في جافا أو بنية `for‑each` المحسنة، مما يتيح لك فحص كل كائن `Resource` على حدة واسترجاع حقوله المرتبطة.
```java
for (Resource res : prj.getResources()) {
```
نقوم بالتكرار عبر كل مورد معرف في المشروع.

## كيف أتحقق من اسم المورد وأحصل على نسبة إكمال العمل؟
أولاً تأكد من أن كائن `Resource` لديه اسم غير فارغ لتجنب معالجة الإدخالات النائبة. ثم استدعِ `res.get(Rsc.PERCENT_WORK_COMPLETE)` التي تُعيد قيمة مزدوجة تمثل نسبة العمل المكتمل لهذا المورد، تتراوح بين 0 إلى 100. يمكنك تنسيق هذه القيمة للعرض أو استخدامها في حسابات إضافية لتقييم صحة المشروع العامة.
```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.PERCENT_WORK_COMPLETE));
}
```
تضمن الشيفرة أولاً أن للمورد اسم ثم تطبع قيمة **نسبة إكمال العمل** لهذا المورد.

## المشكلات الشائعة والحلول
- **NullPointerException** – تأكد من صحة مسار ملف المشروع وأن الملف يُحمَّل دون أخطاء.  
- **Incorrect percentages** – تحقق من أن المورد لديه عمل مُعيَّن؛ وإلا ستكون النسبة `0`.  
- **License errors** – استخدم ترخيص Aspose.Tasks صالح أو ترخيص تقييم مؤقت لتجنب قيود وقت التشغيل.

## الأسئلة المتكررة (الأصلية)

### هل يمكنني استخدام Aspose.Tasks للغة جافا مع أطر جافا أخرى؟
نعم، Aspose.Tasks للغة جافا متوافق مع أطر جافا مختلفة مثل Spring وHibernate وغيرها.

### هل يدعم Aspose.Tasks جميع إصدارات ملفات Microsoft Project؟
يوفر Aspose.Tasks دعمًا لجميع إصدارات ملفات Microsoft Project، بما في ذلك MPP وMPT وXML وغيرها.

### هل يمكنني تعديل جداول المشروع باستخدام Aspose.Tasks؟
بالطبع، يقدم Aspose.Tasks ميزات شاملة لتعديل جداول المشروع، بما في ذلك المهام والموارد والتقويمات وغيرها.

### هل هناك منتدى مجتمع لدعم Aspose.Tasks؟
نعم، يمكنك العثور على المساعدة والتفاعل مع المستخدمين الآخرين في منتدى مجتمع Aspose.Tasks [هنا](https://forum.aspose.com/c/tasks/15).

### هل يقدم Aspose.Tasks تراخيص مؤقتة لأغراض التقييم؟
نعم، يمكنك الحصول على ترخيص مؤقت للتقييم من [هنا](https://purchase.aspose.com/temporary-license/).

## الأسئلة المتكررة الإضافية

**س:** كيف أُنسق الإخراج لإظهار النسب مع علامة %؟  
**ج:** استرجع القيمة الرقمية باستخدام `res.get(Rsc.PERCENT_WORK_COMPLETE)` وقم بتنسيقها باستخدام `String.format("%.2f%%", value)`.

**س:** هل يمكنني تصفية الموارد لإظهار فقط تلك التي تقل نسبتها عن 50 %؟  
**ج:** نعم، أضف شرط `if` يتحقق من `res.get(Rsc.PERCENT_WORK_COMPLETE) < 50` قبل الطباعة.

**س:** هل من الممكن كتابة النسب مرة أخرى إلى ملف المشروع؟  
**ج:** حقل `Rsc.PERCENT_WORK_COMPLETE` للقراءة فقط؛ ستحتاج إلى تعديل تعيينات المهام بدلاً من ذلك.

**س:** هل يعمل هذا مع ملفات Project Online (السحابة)؟  
**ج:** يجب أولاً تنزيل ملف .mpp محليًا؛ Aspose.Tasks يعمل مع تنسيق الملف، وليس مع الخدمة السحابية مباشرة.

## الفوائد الكمية لاستخدام Aspose.Tasks
يدعم Aspose.Tasks **أكثر من 30 تنسيق ملف** (MPP، MPT، XML، CSV، إلخ) ويمكنه معالجة مشاريع تحتوي على **حتى 10,000 مهمة** مع الحفاظ على استهلاك الذاكرة تحت 200 ميغابايت عبر تدفق البيانات. حقل **`Rsc.PERCENT_WORK_COMPLETE`** للقراءة فقط يتم حسابه في زمن O(n)، مما يضمن استرجاعًا سريعًا حتى للجداول الكبيرة.

## الخلاصة
في هذا الدليل أظهرنا **كيفية حساب نسبة الموارد في جافا** باستخدام Aspose.Tasks، مع التركيز على استرجاع *نسبة إكمال العمل* لكل مورد. باتباع الخطوات أعلاه، يمكنك دمج تحليلات نسبة الموارد الدقيقة في تطبيقات جافا الخاصة بك، مما يمنحك رؤية أفضل لصحة المشروع واستخدام الموارد.

---

**آخر تحديث:** 2026-06-15  
**تم الاختبار مع:** Aspose.Tasks للغة جافا 24.10  
**المؤلف:** Aspose

## دروس ذات صلة

- [إضافة مورد إلى المشروع باستخدام Aspose.Tasks للغة جافا](/tasks/java/resource-management/create-resources/)
- [إدارة تكاليف موارد MS Project باستخدام Aspose.Tasks للغة جافا](/tasks/java/resource-management/resource-cost/)
- [حسابات النسبة المكتملة للمهام في Aspose.Tasks](/tasks/java/task-properties/percentage-complete-calculations/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}