---
date: 2025-12-25
description: تعلم كيفية تصفية ملفات MPP باستخدام Aspose.Tasks للغة Java وتخصيص معايير
  الفلتر لتبسيط سير عمل إدارة المشاريع الخاص بك.
linktitle: How to Filter MPP Files Using Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: كيفية تصفية ملفات MPP باستخدام Aspose.Tasks للـ Java
url: /ar/java/project-management/filter-data/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تصفية ملفات MPP باستخدام Aspose.Tasks للـ Java

## المقدمة
إذا كنت تعمل مع ملفات Microsoft Project (.mpp) في تطبيق Java، فستحتاج غالبًا إلى **تصفية** المهام أو الموارد أو التعيينات للتركيز على البيانات التي تهمك حقًا. في هذا البرنامج التعليمي سنستعرض **كيفية تصفية ملفات mpp** برمجيًا باستخدام Aspose.Tasks للـ Java، ونوضح لك كيفية **تخصيص معايير التصفية** لتلبية احتياجات تقارير مشروعك الخاصة. في النهاية، ستحصل على مثال واضح خطوة بخطوة يمكنك إدراجه مباشرةً في قاعدة الشيفرة الخاصة بك.

## إجابات سريعة
- **ماذا يعني “filter mpp”؟** يشير إلى استخراج مجموعة فرعية من بيانات المشروع بناءً على شروط محددة.  
- **أي مكتبة تتعامل مع ذلك؟** Aspose.Tasks للـ Java توفر API غني لإنشاء وتطبيق الفلاتر.  
- **هل أحتاج إلى ترخيص؟** نسخة تجريبية مجانية تكفي للتطوير؛ الترخيص التجاري مطلوب للإنتاج.  
- **هل يمكنني تصفية المهام والموارد والتعيينات؟** نعم – لكل نوع كيان مجموعة فلاتر خاصة به.  
- **هل Java 8 أو أعلى مطلوب؟** Aspose.Tasks تدعم Java 8 والإصدارات الأحدث.

## ما هو “how to filter mpp” في Java؟
تصفية ملف MPP تعني استخدام API الخاص بـ Aspose.Tasks لتحديد معايير (مثل تاريخ بدء المهمة، التكلفة، أو الحقول المخصصة) ثم استرجاع العناصر التي تلبي تلك القواعد فقط. يساعدك ذلك على إنشاء تقارير مركزة، أتمتة فحص الحالة، أو دمج بيانات المشروع مع أنظمة أخرى.

## لماذا تخصيص معايير الفلترة؟
كل مشروع له أولوياته الخاصة. من خلال **تخصيص معايير الفلترة**، يمكنك عزل المهام عالية المخاطر، العناصر المتأخرة، أو الموارد التي تتجاوز الميزانية، مما يجعل لوحات معلومات المشروع أكثر فاعلية وشيفرتك أكثر قابلية لإعادة الاستخدام.

## المتطلبات المسبقة
قبل أن تبدأ، تأكد من وجود ما يلي:

1. **مجموعة تطوير Java (JDK)** – الإصدار 8 أو أحدث.  
2. **Aspose.Tasks للـ Java** – حمّله من [صفحة التحميل](https://releases.aspose.com/tasks/java/).  
3. **بيئة تطوير متكاملة (IDE)** – IntelliJ IDEA أو Eclipse أو NetBeans ستعمل بشكل جيد.  

## استيراد الحزم
ابدأ باستيراد الفئات اللازمة إلى مشروع Java الخاص بك:

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
أولاً، أنشئ كائن `Project` يشير إلى ملف MPP الذي تريد العمل معه.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "Project2003.mpp");
```

### الخطوة 2: استرجاع الفلتر
تخزن Aspose.Tasks الفلاتر المعرفة مسبقًا (مثل “All Tasks”، “Critical Tasks”). احصل على الفلتر الذي تحتاجه عبر الفهرس أو الاسم.

```java
Filter filter = project.getTaskFilters().toList().get(1);
```

> **نصيحة احترافية:** استخدم `project.getTaskFilters().getByName("My Custom Filter")` إذا كنت تفضّل الفلتر المسمّى.

### الخطوة 3: الوصول إلى معايير الفلتر
الآن بعد أن حصلت على كائن `Filter`، يمكنك فحص صفوف معاييره والعملية المنطقية (AND/OR) التي تجمع بينها.

```java
System.out.println(filter.getCriteria().getCriteriaRows().size());
System.out.println(filter.getCriteria().getOperation());
```

### الخطوة 4: استرجاع تفاصيل المعايير
كل صف معيار يحتوي على اختبار (مثل “Equals”، “GreaterThan”) والحقل الذي يُطبق عليه (مثل “Start”، “Cost”).

```java
FilterCriteria criteria1 = filter.getCriteria().getCriteriaRows().get(0);
System.out.println(criteria1.getTest());
System.out.println(criteria1.getField());
```

### الخطوة 5: التكرار عبر صفوف المعايير
يمكن أن تحتوي الفلاتر المعقدة على معايير متداخلة. هنا نستعرض مجموعة معايير من المستوى الثاني.

```java
FilterCriteria criteria2 = filter.getCriteria().getCriteriaRows().get(1);
System.out.println(criteria2.getOperation());
System.out.println(criteria2.getCriteriaRows().size());
```

### الخطوة 6: طباعة معلومات المعايير
أخيرًا، اعرض تفاصيل كل معيار متداخل لتتمكن من التحقق من منطق الفلتر.

```java
FilterCriteria criteria21 = criteria2.getCriteriaRows().get(0);
System.out.println(criteria21.getTest());
System.out.println(criteria21.getField());
FilterCriteria criteria22 = criteria2.getCriteriaRows().get(1);
System.out.println(criteria22.getTest());
System.out.println(criteria22.getField());
```

## المشكلات الشائعة والحلول
| المشكلة | الحل |
|-------|----------|
| **NullPointerException عند الوصول إلى الفلاتر** | تأكد من أن ملف المشروع يحتوي فعليًا على فلاتر مهام؛ يمكنك إضافة فلتر برمجيًا إذا لزم الأمر. |
| **أسماء الحقول غير صحيحة** | استخدم تعداد `ItemType` (مثل `ItemType.Task`) لتجنب الأخطاء الإملائية. |
| **الفلتر لا يُعيد أي نتائج** | تحقق من أن عوامل الاختبار والقيم تتطابق مع البيانات في ملف MPP الخاص بك. |

## الأسئلة المتكررة
### س: هل Aspose.Tasks للـ Java متوافق مع إصدارات مختلفة من ملفات Microsoft Project؟
ج: نعم، يدعم Aspose.Tasks للـ Java إصدارات متعددة من ملفات Microsoft Project، مما يضمن التوافق والمرونة في مهام إدارة المشاريع.

### س: هل يمكنني تخصيص معايير الفلترة بناءً على متطلبات مشروع محددة؟
ج: بالتأكيد! يتيح لك Aspose.Tasks للـ Java تعديل معايير الفلترة وفقًا لاحتياجات مشروعك الفريدة، مما يمكِّنك من معالجة البيانات المستهدفة وتحليلها.

### س: هل Aspose.Tasks للـ Java مناسب للمشاريع الصغيرة والكبيرة على حد سواء؟
ج: نعم، سواء كنت تدير مشروعًا صغيرًا أو تتعامل مع محافظ مشاريع واسعة، يوفر Aspose.Tasks للـ Java القابلية للتوسع والأداء اللازم لمختلف سيناريوهات إدارة المشاريع.

### س: هل يقدم Aspose.Tasks للـ Java وثائق شاملة وموارد دعم؟
ج: بالطبع! يمكنك الرجوع إلى [الوثائق](https://reference.aspose.com/tasks/java/) للحصول على أدلة مفصلة ومراجع API. بالإضافة إلى ذلك، يمكنك طلب المساعدة من منتديات مجتمع Aspose.Tasks لأي استفسارات أو مشكلات تواجهها.

### س: هل يمكنني تجربة وظائف Aspose.Tasks للـ Java قبل الشراء؟
ج: بالطبع! يمكنك الاستفادة من نسخة تجريبية مجانية من [الموقع الإلكتروني](https://releases.aspose.com/) لتجربة الميزات والقدرات الخاصة بـ Aspose.Tasks للـ Java مباشرة.

## أسئلة شائعة أخرى

**س: كيف أنشئ فلترًا جديدًا تمامًا برمجيًا؟**  
ج: استخدم `project.getTaskFilters().add(new Filter("My Filter"))` ثم عرّف مجموعة `FilterCriteria` الخاصة به.

**س: هل يمكنني تطبيق فلتر على الموارد بدلاً من المهام؟**  
ج: نعم – استخدم `project.getResourceFilters()` للعمل مع فلاتر الموارد.

**س: هل يمكن الجمع بين فلاتر متعددة باستخدام منطق OR؟**  
ج: يمكنك إنشاء `FilterCriteria` رئيسي مع تعيين `Operation` إلى `OR` وإضافة المعايير الفردية كأطفال.

**س: هل يدعم Aspose.Tasks التصفية على الحقول المخصصة؟**  
ج: بالتأكيد. تُعامل الحقول المخصصة كأي حقل آخر؛ يمكنك الإشارة إليها باستخدام قيمة تعداد `CustomField` الخاصة بها.

**س: ما هو تأثير الأداء لتصفية ملفات MPP الكبيرة؟**  
ج: تتم التصفية في الذاكرة وعادةً ما تكون سريعة، ولكن بالنسبة للمشروعات الضخمة جدًا يُنصح بتحميل الأقسام المطلوبة فقط باستخدام `ProjectReader`.

---

**آخر تحديث:** 2025-12-25  
**تم الاختبار مع:** Aspose.Tasks للـ Java 24.10  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}