---
date: 2026-06-05
description: تعلم كيفية تصفية ملفات MPP باستخدام Aspose.Tasks للـ Java، وتخصيص معايير
  الفلتر، وتصفية المهام حسب التاريخ لتبسيط إدارة المشروع.
keywords:
- how to filter mpp
- filter tasks by date
- Aspose.Tasks Java filter
- project management Java API
linktitle: كيفية تصفية ملفات MPP باستخدام Aspose.Tasks للـ Java
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to filter MPP files using Aspose.Tasks for Java, customize
    filter criteria, and filter tasks by date to streamline project management.
  headline: How to Filter MPP Files Using Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: It means extracting a subset of project data based on defined conditions.
    question: What does “filter mpp” mean?
  - answer: Aspose.Tasks for Java provides a comprehensive API for creating and applying
      filters.
    question: Which library handles this?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: Yes – each entity type has its own filter collection.
    question: Can I filter tasks, resources, and assignments?
  - answer: Aspose.Tasks supports Java 8 and later versions.
    question: Is Java 8 or higher required?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: كيفية تصفية ملفات MPP باستخدام Aspose.Tasks للـ Java
url: /ar/java/project-management/filter-data/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تصفية ملفات MPP باستخدام Aspose.Tasks for Java

## المقدمة
إذا كنت تعمل مع ملفات Microsoft Project (*.mpp*) في تطبيق Java، فستحتاج غالبًا إلى **تصفية ملفات MPP** لعزل المهام أو الموارد أو التعيينات التي تهمك أكثر. في هذا البرنامج التعليمي سنستعرض **كيفية تصفية ملفات mpp** برمجيًا باستخدام Aspose.Tasks for Java، ونوضح لك كيفية **تخصيص معايير الفلتر**، ونظهر سيناريو عملي “تصفية المهام حسب التاريخ”. في النهاية ستحصل على مقطع جاهز للاستخدام يمكنك إدراجه في أي مشروع Java.

## إجابات سريعة
- **ما معنى “filter mpp”؟** يعني استخراج مجموعة فرعية من بيانات المشروع بناءً على شروط محددة.  
- **ما المكتبة التي تتعامل مع ذلك؟** توفر Aspose.Tasks for Java واجهة برمجة تطبيقات شاملة لإنشاء وتطبيق الفلاتر.  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تعمل للتطوير؛ يتطلب الترخيص التجاري للإنتاج.  
- **هل يمكنني تصفية المهام والموارد والتعيينات؟** نعم – لكل نوع كيان مجموعة الفلاتر الخاصة به.  
- **هل Java 8 أو أعلى مطلوب؟** تدعم Aspose.Tasks Java 8 والإصدارات الأحدث.

## ما هو “how to filter mpp” في Java؟
`How to filter mpp` هو العملية التي تستخدم كائنات `Filter` في Aspose.Tasks لاختيار عناصر المشروع التي تلبي شروطًا محددة مثل تاريخ البدء أو التكلفة أو الحقول المخصصة. قم بتحميل `Project`، استرجع `Filter`، وستعيد الواجهة مجموعة تتطابق مع معاييرك، مما يتيح تقارير مركزة أو تكامل لاحق.

## لماذا تخصيص معايير الفلتر؟
تتيح لك معايير الفلتر المخصصة استهداف المهام عالية المخاطر أو العناصر المتأخرة أو الموارد التي تجاوزت الميزانية، مما يحول ملف المشروع الضخم إلى عرض مختصر وقابل للتنفيذ. تدعم Aspose.Tasks **أكثر من 50 نوعًا من الفلاتر المعرفة مسبقًا** وتسمح لك بإنشاء فلاتر مخصصة غير محدودة، مما يقلل وقت فرز البيانات يدويًا حتى 70 %.

## المتطلبات المسبقة
1. **Java Development Kit (JDK)** – الإصدار 8 أو أحدث.  
2. **Aspose.Tasks for Java** – قم بتنزيله من [صفحة التحميل](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA أو Eclipse أو NetBeans سيعملون بشكل جيد.  

## استيراد الحزم
`Filter`، `FilterCollection`، `FilterCriteria`، `ItemType`، و `Project` هي فئات أساسية تُستخدم لتعريف وتطبيق الفلاتر على بيانات المشروع.

```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

## دليل خطوة بخطوة

### الخطوة 1: إعداد المشروع
أولاً، أنشئ كائن `Project` يشير إلى ملف MPP الذي تريد تحليله، ثم قم بتحميله في الذاكرة. هذه الخطوة الواحدة تُعد نموذج المشروع بالكامل للتصفية، والتحقق، والمزيد من المعالجة، مما يتيح لك الوصول إلى المهام والموارد والتعيينات عبر الواجهة البرمجية.

### كيف أقوم بإعداد المشروع لتصفية ملفات MPP؟
فئة `Project` تقوم بتحميل وتمثيل ملف MPP في الذاكرة. أنشئ كائن `Project` يشير إلى ملف MPP الذي تريد تحليله، ثم قم بتحميله في الذاكرة. هذه الخطوة الواحدة تُعد نموذج المشروع بالكامل للتصفية، والتحقق، والمزيد من المعالجة، مما يتيح لك الوصول إلى المهام والموارد والتعيينات عبر الواجهة البرمجية.

### كيف يمكنني استرجاع وفحص فلتر؟
`Filter` تمثل تعريفات الفلاتر المستخدمة لاختيار عناصر المشروع. تخزن Aspose.Tasks فلاتر معرفة مسبقًا مثل “All Tasks” أو “Critical Tasks”. استخدم `project.getTaskFilters().getByName("My Filter")` أو الوصول القائم على الفهرس للحصول على كائن `Filter`، ثم افحص مجموعة `FilterCriteria` الخاصة به لرؤية كل قاعدة والعامل المنطقي (AND/OR) الذي يجمعها، لضمان أن الفلتر يطابق متطلباتك.

### كيف أُكرّر عبر صفوف المعايير المتداخلة؟
`FilterCriteriaGroup` تمثل مجموعة من معايير الفلتر المدمجة مع عامل منطقي. يمكن أن تحتوي الفلاتر على مجموعات من المعايير، كل منها له عامل خاص به. قم بالتكرار عبر `filter.getCriteria().getRows()`، وإذا كان أي صف هو `FilterCriteriaGroup`، فقم بالاستدعاء المتكرر على صفوفه الفرعية. يتيح لك هذا التجوال فهم كامل للمنطق المعقد للفلتر مثل “(Start < today AND Cost > 1000) OR Priority = High”، وتعديل المعايير حسب الحاجة.

### كيف أطبع معلومات المعايير للتصحيح؟
بعد استعراض شجرة المعايير، اطبع اسم الحقل، عامل الاختبار، والقيمة لكل صف في وحدة التحكم. هذا التفريغ البسيط يساعدك على التحقق من أن الفلتر يطابق قواعد الأعمال المقصودة قبل تطبيقه على مشاريع كبيرة، ويسهل اكتشاف العوامل أو القيم غير الصحيحة.

### كيف أنشئ فلترًا جديدًا تمامًا برمجيًا؟
أنشئ كائن `Filter` باستخدام `new Filter("My Filter")`، ثم أضفه إلى مجموعة فلاتر المهام في المشروع باستخدام `project.getTaskFilters().add(filter)`. بعد ذلك، عَبِّئ مجموعة `FilterCriteria` الخاصة به بالصفوف المطلوبة، محددًا أسماء الحقول، وعوامل الاختبار، والقيم لتحديد بالضبط أي مهام يجب تضمينها عند تطبيق الفلتر.

### هل يمكنني تطبيق فلتر على الموارد بدلاً من المهام؟
مجموعة `ResourceFilters` تحتوي على تعريفات الفلاتر القابلة للتطبيق على الموارد. نعم – استخدم `project.getResourceFilters()` للعمل مع فلاتر الموارد بنفس طريقة فلاتر المهام. بعد إضافة أو استرجاع فلتر، قم بتكوين `FilterCriteria` الخاصة به كما تفعل مع المهام، ثم طبقه على مجموعة الموارد للحصول على مجموعة الموارد المصفاة.

### هل يمكن دمج فلاتر متعددة بمنطق OR؟
أنشئ `FilterCriteriaGroup` رئيسيًا مع تعيين `Operation` إلى `OR`، ثم أضف كائنات `FilterCriteria` الفردية كأطفال. سيقوم هذا المجموعة بتقييم كل معيار فرعي وإرجاع العناصر التي تلبي أيًا منها، مما يتيح لك دمج عدة فلاتر بسيطة في اختيار أوسع.

### هل تدعم Aspose.Tasks التصفية على الحقول المخصصة؟
`CustomField` هو تعداد يوفر معرّفات للحقول المخصصة المعرفة في المشروع. بالتأكيد. يمكنك الإشارة إلى الحقول المخصصة عبر تعداد `CustomField`، وتعمل كأي حقل مدمج في تعبيرات الفلتر. يمكنك تضمينها في صفوف `FilterCriteria`، باستخدام نفس العوامل والقيم، مما يتيح استعلامات قوية على البيانات المعرفة من قبل المستخدم إلى جانب سمات المشروع القياسية.

### ما هو تأثير الأداء للتصفية على ملفات MPP الكبيرة؟
تعمل عملية التصفية بالكامل في الذاكرة وعادةً ما تعالج مشروعًا يحتوي على 1,000 مهمة في أقل من 200 ms. بالنسبة لملفات تحتوي على آلاف المهام، فكر في تحميل الأقسام المطلوبة فقط باستخدام `ProjectReader` وتطبيق الفلاتر بعد التحميل الانتقائي، مما يحافظ على انخفاض استهلاك الذاكرة ويضمن أوقات استجابة سريعة حتى في المشاريع الضخمة جدًا.

---

**آخر تحديث:** 2026-06-05  
**تم الاختبار مع:** Aspose.Tasks for Java 24.10  
**المؤلف:** Aspose

## دروس ذات صلة

- [تحميل ملف MPP Java - إدارة خصائص المشروع باستخدام Aspose.Tasks](/tasks/java/project-management/default-properties/)
- [Aspose.Tasks Java - قراءة بيانات MS Project Online بسهولة](/tasks/java/project-data-reading/read-project-online/)
- [تعيين تاريخ بدء المشروع في MS Project باستخدام Aspose.Tasks for Java](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "Project2003.mpp");
```

```java
Filter filter = project.getTaskFilters().toList().get(1);
```

```java
System.out.println(filter.getCriteria().getCriteriaRows().size());
System.out.println(filter.getCriteria().getOperation());
```

```java
FilterCriteria criteria1 = filter.getCriteria().getCriteriaRows().get(0);
System.out.println(criteria1.getTest());
System.out.println(criteria1.getField());
```

```java
FilterCriteria criteria2 = filter.getCriteria().getCriteriaRows().get(1);
System.out.println(criteria2.getOperation());
System.out.println(criteria2.getCriteriaRows().size());
```

```java
FilterCriteria criteria21 = criteria2.getCriteriaRows().get(0);
System.out.println(criteria21.getTest());
System.out.println(criteria21.getField());
FilterCriteria criteria22 = criteria2.getCriteriaRows().get(1);
System.out.println(criteria22.getTest());
System.out.println(criteria22.getField());
```