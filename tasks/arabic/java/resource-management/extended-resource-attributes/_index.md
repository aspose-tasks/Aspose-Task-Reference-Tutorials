---
date: 2026-01-13
description: تعلم كيفية إنشاء سمة مخصصة، تحميل ملف Microsoft Project، تعيين قيمة رقمية
  في Java، وحفظ المشروع كملف XML باستخدام Aspose.Tasks for Java.
linktitle: Handle Extended Resource Attributes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: كيفية إنشاء سمة مخصصة في MS Project باستخدام Aspose.Tasks
url: /ar/java/resource-management/extended-resource-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء سمة مخصصة في MS Project باستخدام Aspose.Tasks

## المقدمة
في هذا الدرس، **ستكتشف كيفية إنشاء سمة مخصصة** للموارد في ملف Microsoft Project باستخدام Aspose.Tasks for Java. سنستعرض تحميل ملف Microsoft Project، تعريف سمة رقمية جديدة، تعيين قيمة لها، وأخيرًا حفظ المشروع بصيغة XML. في النهاية، ستحصل على مثال عملي واضح يمكنك تكييفه مع حلول إدارة المشاريع الخاصة بك.

## إجابات سريعة
- **ماذا يعني “سمة مخصصة”؟**  
  حقل يحدده المستخدم لتخزين معلومات إضافية (مثل العمر، مستوى المهارة) للموارد أو المهام.  
- **أي مكتبة تتعامل مع ذلك؟**  
  Aspose.Tasks for Java توفر API سهل لإنشاء وإدارة السمات المخصصة.  
- **هل أحتاج إلى ترخيص؟**  
  ترخيص مؤقت مجاني يكفي للتقييم؛ الترخيص الكامل مطلوب للإنتاج.  
- **هل يمكنني تعيين قيم رقمية؟**  
  نعم – استخدم `setNumericValue` مع `BigDecimal` (مثلًا `30.5345`).  
- **كيف يتم حفظ المشروع؟**  
  يمكن حفظ الملف المعدل بصيغة XML باستخدام `SaveFileFormat.Xml`.

## ما هي السمة المخصصة؟
**السمة المخصصة** (وتُسمى أيضًا السمة الموسعة) هي عمود إضافي يمكنك إضافته إلى الموارد أو المهام في Microsoft Project. تتيح لك التقاط بيانات لا يغطيها الحقول المدمجة، مثل عمر الموظف، مستوى الشهادة، أو أي مقياس خاص بالأعمال.

## لماذا ننشئ سمة مخصصة في MS Project؟
- **تخصيص بيانات المشروع** لتلبية احتياجات مؤسستك.  
- **تمكين التقارير المتقدمة** عبر تخزين قيم يمكن الاستعلام عنها لاحقًا.  
- **الحفاظ على الاتساق** عبر مشاريع متعددة من خلال تطبيق تعريف السمة نفسه برمجيًا.

## المتطلبات المسبقة
قبل البدء، تأكد من وجود ما يلي:

1. **بيئة تطوير جافا** – JDK 8 أو أعلى مثبتة.  
2. **Aspose.Tasks for Java** – حمّل أحدث نسخة من [هنا](https://releases.aspose.com/tasks/java/).  
3. **IDE** – Eclipse أو IntelliJ IDEA أو أي بيئة تطوير تدعم جافا.  

## دليل خطوة بخطوة

### استيراد الحزم
أولاً، استورد فئات Aspose.Tasks التي ستحتاجها. هذه الفئات توفر الوظائف الأساسية للتعامل مع المشاريع والموارد والسمات الموسعة.

```java
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.SaveFileFormat;
import java.math.BigDecimal;
```

### الخطوة 1: تعريف دليل البيانات
حدد المجلد الذي يحتوي على ملف المشروع المصدر ومكان كتابة المخرجات.

```java
String dataDir = "Your Data Directory";
```

### الخطوة 2: تحميل ملف Microsoft Project
أنشئ كائن `Project` بتحميل الملف الموجود. هذه هي خطوة **تحميل ملف Microsoft Project** التي تمنحك الوصول الكامل إلى محتوياته.

```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```

### الخطوة 3: تعريف السمة المخصصة
سنعرّف سمة رقمية جديدة تسمى **Age**. يتحقق الـ API مما إذا كان التعريف موجودًا مسبقًا؛ إذا لم يكن كذلك، يتم إنشاؤه.

```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```

### الخطوة 4: تعيين قيمة رقمية في جافا
أنشئ نسخة من السمة لمورد محدد وعيّن قيمة رقمية باستخدام `setNumericValue`. هذا يوضح **set numeric value java** عمليًا.

```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```

### الخطوة 5: إضافة مورد وإرفاق السمة المخصصة
أضف موردًا جديدًا باسم **R1** وأرفق السمة المخصصة التي تم إنشاؤها مسبقًا به.

```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```

### الخطوة 6: حفظ المشروع بصيغة XML
أخيرًا، احفظ التغييرات بحفظ المشروع. هذه هي خطوة **save project as xml** التي تنتج تمثيل XML نظيف للملف المحدث.

```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```

### الخطوة 7: عرض النتيجة
اطبع رسالة تأكيد ودية لتعرف أن العملية انتهت دون أخطاء.

```java
System.out.println("Process completed Successfully");
```

باتباع هذه الخطوات، تكون قد **أنشأت سمة مخصصة**، حمّلت ملف Microsoft Project، عيّنت قيمة رقمية باستخدام جافا، وحفظت المشروع بصيغة XML.

## الأخطاء الشائعة والنصائح
- **تعارض معرف السمة:** تحقق دائمًا من `getById` قبل إنشاء تعريف جديد لتجنب تكرار المعرفات.  
- **معالجة الدقة:** `BigDecimal` يحافظ على الدقة العشرية؛ تجنّب استخدام `float` أو `double` للقيم الدقيقة.  
- **مسارات الملفات:** استخدم مسارات مطلقة أو اضبط دليل العمل في IDE لتفادي `FileNotFoundException`.  

## الأسئلة المتكررة

**س: هل يمكنني إنشاء سمات مخصصة للمهام بالإضافة إلى الموارد؟**  
ج: نعم – استخدم `ExtendedAttributeTask` بدلاً من `ExtendedAttributeResource` عند تعريف السمة.

**س: هل يمكن إضافة عدة سمات مخصصة مرة واحدة؟**  
ج: بالتأكيد. أنشئ كائنات `ExtendedAttributeDefinition` منفصلة لكل سمة وأرفقها بالموارد أو المهام المطلوبة.

**س: ما الصيغ التي يمكنني حفظ المشروع بها؟**  
ج: يدعم Aspose.Tasks الصيغ XML، MPP، والعديد من الصيغ الأخرى مثل PDF وHTML. في هذا المثال استخدمنا `SaveFileFormat.Xml`.

**س: هل أحتاج إلى ترخيص Aspose.Tasks لبناءات التطوير؟**  
ج: الترخيص المؤقت يكفي للتقييم. للانتشار في بيئات الإنتاج، يلزم الترخيص الكامل.

**س: كيف أسترجع قيم السمات المخصصة لاحقًا؟**  
ج: استخدم `resource.getExtendedAttributes()` للتنقل عبر السمات المرفقة واسترجاع قيمها عبر `getNumericValue()` أو `getTextValue()`.

## الخاتمة
إنشاء **سمة مخصصة** في Microsoft Project باستخدام Aspose.Tasks for Java سهل بمجرد فهم سير العمل: تحميل المشروع، تعريف السمة، تعيين قيمتها، إرفاقها بمورد، وحفظ الملف. يتيح لك هذا النهج توسيع نماذج بيانات المشروع برمجيًا، مما يوفّر تقارير أغنى وتكاملًا أقوى مع عمليات الأعمال الخاصة بك.

---

**آخر تحديث:** 2026-01-13  
**تم الاختبار مع:** Aspose.Tasks for Java 24.12  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}