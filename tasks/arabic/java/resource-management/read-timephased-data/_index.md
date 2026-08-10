---
date: 2026-06-15
description: تعلم كيفية استخراج البيانات الزمنية من موارد MS Project باستخدام Aspose.Tasks
  for Java. دليل خطوة بخطوة للحصول على resource by id.
keywords:
- get resource by id
- Aspose.Tasks timephased data
- Java MS Project API
linktitle: قراءة البيانات الزمنية للموارد في Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to extract timephased data from MS Project resources using
    Aspose.Tasks for Java. Step‑by‑step guide to get resource by id.
  headline: Read Timephased Data for Resources in Aspose.Tasks – get resource by id
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks supports MPP, XML, CSV, and several other formats, allowing
      you to read and write across different standards.
    question: Can Aspose.Tasks handle other types of project files apart from Microsoft
      Project?
  - answer: Absolutely. The library works with all major IDEs (IntelliJ IDEA, Eclipse,
      NetBeans) and build tools (Maven, Gradle).
    question: Is Aspose.Tasks compatible with different Java development environments?
  - answer: Yes, you can create, modify, and delete tasks, resources, assignments,
      and even custom fields through the API.
    question: Can I manipulate project data using Aspose.Tasks?
  - answer: It is. Enterprises rely on Aspose.Tasks for high‑volume processing, batch
      conversions, and server‑side reporting because it requires no Microsoft Project
      installation.
    question: Is Aspose.Tasks suitable for enterprise‑level projects?
  - answer: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for assistance from the community and support team.
    question: Where can I find support if I encounter issues while using Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: قراءة البيانات الزمنية للموارد في Aspose.Tasks – get resource by id
url: /ar/java/resource-management/read-timephased-data/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# قراءة البيانات الزمنية للموارد في Aspose.Tasks

## مقدمة
في هذا الدرس، ستتعلم **how to get resource by id** وتقرأ بياناته الزمنية باستخدام Aspose.Tasks for Java. سنستعرض كل خطوة — من إعداد مجلد المشروع إلى طباعة قيم العمل والتكلفة الزمنية — حتى تتمكن من استخراج معلومات جدولة قيمة من أي ملف Microsoft Project برمجياً. Aspose.Tasks for Java هي API شاملة تمكّن المطورين من إنشاء، قراءة، تعديل، وتحويل ملفات Microsoft Project دون الحاجة إلى تثبيت Microsoft Project، وتدعم مجموعة واسعة من ميزات وإصدارات إدارة المشاريع.

## إجابات سريعة
- **ماذا يفعل “get resource by id”؟** يقوم باسترجاع كائن `Resource` محدد من `Project` باستخدام المعرف الفريد الخاص به.  
- **أي مكتبة تتعامل مع البيانات الزمنية؟** توفر Aspose.Tasks for Java واجهة برمجة التطبيقات `Resource.getTimephasedData`.  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تعمل للتطوير؛ يلزم الحصول على ترخيص تجاري للإنتاج.  
- **هل يمكنني قراءة مشاريع كبيرة؟** نعم — يمكن لـ Aspose.Tasks معالجة ملفات تحتوي على ما يصل إلى 10,000 مهمة دون تحميل الملف بالكامل في الذاكرة.  
- **ما نسخة Java المطلوبة؟** Java 8 أو أعلى؛ المكتبة متوافقة مع جميع إصدارات JDK الرئيسية.  

## ما هو “get resource by id”؟
`get resource by id` هو استدعاء طريقة يجلب كائن `Resource` من `Project` محمَّل باستخدام المعرف الرقمي للموارد. يتيح هذا الإجراء وصولاً دقيقاً إلى خصائص المورد التفصيلية، مثل التعيينات، الجداول الزمنية، والحقول المخصصة، وهو أساسي لاستخراج بيانات العمل أو التكلفة الزمنية المرتبطة بذلك المورد المحدد.

## لماذا نستخدم Aspose.Tasks للبيانات الزمنية؟
يدعم Aspose.Tasks **أكثر من 50 تنسيق إدخال وإخراج** (MPP، XML، CSV، إلخ) ويمكنه استخراج قيم العمل والتكلفة الزمنية للموارد عبر جداول زمنية تمتد لعدة سنوات مع الحفاظ على استهلاك منخفض للذاكرة. تُعيد الواجهة البرمجية البيانات بفواصل زمنية قدرها 15 دقيقة افتراضيًا، مما يمنحك رؤى دقيقة للتقارير أو التحليلات المخصصة.

## المتطلبات المسبقة
1. Java Development Kit (JDK): تأكد من تثبيت JDK على نظامك. يمكنك تنزيله من [الموقع](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) واتباع تعليمات التثبيت.  
2. Aspose.Tasks for Java Library: قم بتنزيل مكتبة Aspose.Tasks for Java من [صفحة التحميل](https://releases.aspose.com/tasks/java/) واتبع تعليمات التثبيت الواردة في الوثائق.

## استيراد الحزم
الخطوة الأولى هي استيراد فئات Aspose.Tasks المطلوبة إلى ملف المصدر Java الخاص بك.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```

## الخطوة 1: إعداد دليل البيانات
أولاً، حدد الدليل الذي يقع فيه ملف MS Project الخاص بك. الحفاظ على مجلد البيانات منفصلًا عن شفرة المصدر يجعل المشروع أسهل في الصيانة.

```java
String dataDir = "Your Data Directory";
```

## الخطوة 2: قراءة ملف قالب MS Project
حدد اسم ملف قالب MS Project الخاص بك. يضمن استخدام قالب توحيد إعدادات الأعمدة عبر المشاريع المختلفة.

```java
String fileName = "ResourceTimephasedData.mpp";
```

## الخطوة 3: قراءة ملف الإدخال ككائن Project
فئة `Project` هي الكائن الأساسي في Aspose.Tasks الذي يمثل ملف Microsoft Project في الذاكرة. تحميل الملف يمنحك وصولًا برمجيًا إلى المهام والموارد والجداول الزمنية.

```java
Project project = new Project(dataDir + fileName);
```

## الخطوة 4: الحصول على المورد عبر المعرف
للحصول على مورد محدد، استدعِ طريقة `getResources().getById(id)`. هذه هي العملية الدقيقة المشار إليها بالكلمة المفتاحية الأساسية.

```java
Resource resource = project.getResources().getByUid(1);
```

## الخطوة 5: طباعة البيانات الزمنية لعمل المورد
بمجرد حصولك على كائن `Resource`، يمكنك استدعاء `resource.getTimephasedData(ResourceTimephasedDataType.Work)` للحصول على تخصيصات العمل عبر الزمن. تحتوي المجموعة المرجعة على كائنات `TimephasedData` التي تشمل تاريخ البدء، تاريخ الانتهاء، وكمية العمل لكل فاصل زمني.

```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```

## الخطوة 6: طباعة البيانات الزمنية لتكلفة المورد
وبالمثل، تُعيد `resource.getTimephasedData(ResourceTimephasedDataType.Cost)` معلومات التكلفة مقسمة حسب نفس الفواصل الزمنية. هذا مفيد لتقارير الميزانية وتتبع التكاليف.

```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## كيف تحصل على المورد عبر المعرف في سطر واحد؟
حمّل المشروع، ثم استدعِ `project.getResources().getById(5)` — استبدل **5** بمعرف المورد الفعلي الذي تحتاجه. تُعيد هذه الاستدعاءة الواحدة كائن `Resource`، وبعد ذلك يمكنك الاستعلام عن بياناته الزمنية أو تعييناته أو حقوله المخصصة. تعمل الطريقة في زمن O(1) لأن الموارد مفهرسة داخليًا.

## المشكلات الشائعة والحلول
- **Resource not found** – تأكد من وجود المعرف في ملف المشروع؛ تبدأ المعرفات من 1 وتكون فريدة لكل مورد.  
- **Empty timephased data** – تحقق من أن المورد لديه تعيينات عمل أو تكلفة؛ وإلا ستكون المجموعة فارغة.  
- **Large file performance** – استخدم `Project.setLoadOptions(LoadOptions.fromFile(...))` لتمكين التحميل الكسول للمشاريع التي يزيد حجمها عن 500 ميغابايت.  

## الأسئلة المتكررة
**س: هل يمكن لـ Aspose.Tasks التعامل مع أنواع أخرى من ملفات المشاريع بخلاف Microsoft Project؟**  
ج: نعم، يدعم Aspose.Tasks صيغ MPP، XML، CSV، والعديد من الصيغ الأخرى، مما يتيح لك القراءة والكتابة عبر معايير مختلفة.

**س: هل Aspose.Tasks متوافق مع بيئات تطوير Java المختلفة؟**  
ج: بالتأكيد. تعمل المكتبة مع جميع بيئات التطوير المتكاملة الرئيسية (IntelliJ IDEA، Eclipse، NetBeans) وأدوات البناء (Maven، Gradle).

**س: هل يمكنني تعديل بيانات المشروع باستخدام Aspose.Tasks؟**  
ج: نعم، يمكنك إنشاء، تعديل، وحذف المهام، الموارد، التعيينات، وحتى الحقول المخصصة عبر الواجهة البرمجية.

**س: هل Aspose.Tasks مناسب للمشاريع على مستوى المؤسسات؟**  
ج: نعم. تعتمد المؤسسات على Aspose.Tasks للمعالجة ذات الحجم الكبير، التحويلات الدفعية، والتقارير على الخادم لأنها لا تتطلب تثبيت Microsoft Project.

**س: أين يمكنني الحصول على الدعم إذا واجهت مشكلات أثناء استخدام Aspose.Tasks؟**  
ج: يمكنك زيارة [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15) للحصول على مساعدة من المجتمع وفريق الدعم.

## الخلاصة
في هذا الدرس، تعلمنا كيفية **get resource by id** وقراءة بيانات العمل والتكلفة الزمنية الخاصة به باستخدام Aspose.Tasks for Java. باتباع هذه الخطوات، يمكنك استخراج معلومات جدولة قيمة من ملفات المشروع الخاصة بك بفعالية ودمجها في تقارير مخصصة أو خطوط تحليلية.

---

**آخر تحديث:** 2026-06-15  
**تم الاختبار باستخدام:** Aspose.Tasks 24.11 for Java  
**المؤلف:** Aspose

## دروس ذات صلة
- [إضافة مورد إلى المشروع باستخدام Aspose.Tasks for Java](/tasks/java/resource-management/create-resources/)
- [إدارة تكاليف موارد MS Project باستخدام Aspose.Tasks for Java](/tasks/java/resource-management/resource-cost/)
- [قراءة أسابيع العمل Java من تقويم MS Project باستخدام Aspose.Tasks](/tasks/java/calendars/read-work-weeks/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}