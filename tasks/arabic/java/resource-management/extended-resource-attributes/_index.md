---
date: 2026-06-10
description: تعلم كيفية إنشاء سمة موسعة في Java، تحميل ملف Microsoft Project، تعيين
  القيم الرقمية، وحفظ المشروع كملف XML باستخدام Aspose.Tasks for Java.
keywords:
- create extended attribute java
- custom attribute Aspose.Tasks
- Java project management
linktitle: معالجة سمات الموارد الموسعة في Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to create extended attribute in Java, load a Microsoft Project
    file, set numeric values, and save the project as XML using Aspose.Tasks for Java.
  headline: How to create extended attribute in Java with Aspose.Tasks
  type: TechArticle
- description: Learn how to create extended attribute in Java, load a Microsoft Project
    file, set numeric values, and save the project as XML using Aspose.Tasks for Java.
  name: How to create extended attribute in Java with Aspose.Tasks
  steps:
  - name: Define Data Directory
    text: '`Paths` is a utility class that provides methods to obtain a file system
      path in a platform‑independent way.'
  - name: Load Microsoft Project File
    text: '`Project` represents a Microsoft Project file in memory, allowing read
      and write access to its contents.'
  - name: Define the Custom Attribute
    text: '`ExtendedAttributeDefinition` defines the schema of a new custom field
      that can be attached to resources or tasks.'
  - name: Set Numeric Value in Java
    text: '`ExtendedAttributeResource` holds the value of a custom attribute for a
      specific resource instance.'
  - name: Add Resource and Attach the Custom Attribute
    text: '`Resource` models a project resource such as a person, equipment, or material.'
  - name: Save Project as XML
    text: '`SaveFileFormat` enumerates the supported output formats for saving a project,
      including XML.'
  - name: Display Result
    text: '`System.out.println` prints a line of text to the standard console output.'
  type: HowTo
- questions:
  - answer: Yes – use `ExtendedAttributeTask` instead of `ExtendedAttributeResource`
      when defining the attribute schema.
    question: Can I create custom attributes for tasks as well as resources?
  - answer: Absolutely. Create separate `ExtendedAttributeDefinition` objects for
      each attribute and attach them to the desired resources or tasks.
    question: Is it possible to add multiple custom attributes at once?
  - answer: Aspose.Tasks supports XML, MPP, PDF, HTML, and more than 30 additional
      formats. In this example we used `SaveFileFormat.Xml`.
    question: What formats can I save the project in?
  - answer: A temporary evaluation license is sufficient for testing. For any production
      deployment, a full commercial license is required.
    question: Do I need a license for development builds?
  - answer: Call `resource.getExtendedAttributes()` and iterate over the collection;
      retrieve the stored value with `getNumericValue()` or `getTextValue()`.
    question: How do I read back the custom attribute values later?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: كيفية إنشاء سمة موسعة في Java باستخدام Aspose.Tasks
url: /ar/java/resource-management/extended-resource-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء سمة موسعة في Java باستخدام Aspose.Tasks

## مقدمة
في هذا الدليل العملي ستقوم **بإنشاء سمة موسعة في Java** لملف Microsoft Project باستخدام Aspose.Tasks. سنستعرض تحميل مشروع موجود، تعريف سمة رقمية جديدة، تعيين قيمة لمورد، وأخيرًا حفظ التغييرات كملف XML. في النهاية ستحصل على نمط كود قابل لإعادة الاستخدام يمكن دمجه في أي حل لإدارة المشاريع مبني على Java.

## إجابات سريعة
- **ما هي السمة الموسعة؟**  
  حقل يحدده المستخدم (مثل العمر، مستوى المهارة) يخزن بيانات إضافية للموارد أو المهام.  
- **أي API ينشئها؟**  
  توفر Aspose.Tasks for Java الفئة `ExtendedAttributeDefinition` لتعريف وإدارة السمات المخصصة.  
- **هل أحتاج إلى ترخيص؟**  
  ترخيص تجريبي مؤقت يكفي للتطوير؛ يلزم ترخيص كامل للنشر في بيئة الإنتاج.  
- **هل يمكنني تخزين أرقام؟**  
  نعم – استخدم `setNumericValue(BigDecimal)` لتعيين قيم عشرية دقيقة.  
- **كيف أحفظ التغييرات؟**  
  استدعِ `project.save("output.xml", SaveFileFormat.Xml)` لكتابة المشروع المحدث بصيغة XML.

## ما هي السمة المخصصة؟
**السمة المخصصة** (المعروفة أيضًا باسم السمة الموسعة) هي عمود إضافي يمكنك إضافته إلى الموارد أو المهام في Microsoft Project. تتيح لك جمع بيانات لا تغطيها الحقول المدمجة، مثل عمر الموظف، مستوى الشهادة، أو أي مقياس خاص بالأعمال.

## لماذا إنشاء سمة موسعة في Java؟
إنشاء سمة موسعة في Java يتيح لك إثراء بيانات المشروع برمجيًا، مما يضمن التناسق عبر الملفات ويسمح بالتقارير الآلية. من خلال تعريف السمة مرة واحدة، يمكنك تطبيقها على أي عدد من الموارد أو المهام دون إدخال يدوي، مما يوفر الوقت ويقلل الأخطاء.

- **تخصيص البيانات لمؤسستك** – احفظ أي مقياس يهمك دون حلول يدوية في Excel.  
- **تمكين تقارير أغنى** – استعلم عن الحقل المخصص لاحقًا للوحة التحكم أو التحليل.  
- **الحفاظ على التناسق** – طبق التعريف نفسه برمجيًا عبر العشرات من المشاريع، مما يلغي الأخطاء البشرية.  
- **اختبار الأداء** – تقوم Aspose.Tasks بمعالجة المشاريع التي تصل إلى 10,000 مهمة و5,000 مورد دون تحميل الملف بالكامل في الذاكرة، وفقًا لمقاييس المنتج.

## المتطلبات المسبقة
1. **Java Development Kit** – JDK 8 أو أحدث مثبت.  
2. **Aspose.Tasks for Java** – قم بتنزيل أحدث إصدار من [here](https://releases.aspose.com/tasks/java/).  
3. **IDE** – Eclipse أو IntelliJ IDEA أو أي بيئة تطوير متوافقة مع Java.  

## كيفية إنشاء سمة موسعة في Java؟
حمّل مشروعك، عرّف السمة، أرفقها بمورد، واحفظ الملف – كل ذلك في بضع خطوات بسيطة. الأقسام التالية تقسم كل خطوة إلى شرح مختصر يليه العنصر النائب حيث يُوضع الكود الفعلي.

### دليل خطوة بخطوة

#### استيراد الحزم
`Project`، `ExtendedAttributeDefinition`، `ExtendedAttributeResource`، والفئات ذات الصلة تقع في مساحة الأسماء `com.aspose.tasks`. استوردها في أعلى ملف Java الخاص بك.

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

#### الخطوة 1: تعريف دليل البيانات
`Paths` هي فئة مساعدة توفر طرقًا للحصول على مسار نظام الملفات بطريقة مستقلة عن المنصة.

```java
String dataDir = "Your Data Directory";
```

#### الخطوة 2: تحميل ملف Microsoft Project
`Project` تمثل ملف Microsoft Project في الذاكرة، مما يسمح بالقراءة والكتابة على محتوياته.

```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```

#### الخطوة 3: تعريف السمة المخصصة
`ExtendedAttributeDefinition` يحدد مخطط حقل مخصص جديد يمكن إرفاقه بالموارد أو المهام.

```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```

#### الخطوة 4: تعيين قيمة رقمية في Java
`ExtendedAttributeResource` يحمل قيمة السمة المخصصة لمثيل مورد محدد.

```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```

#### الخطوة 5: إضافة مورد وإرفاق السمة المخصصة
`Resource` نمذج مورد المشروع مثل شخص أو معدات أو مادة.

```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```

#### الخطوة 6: حفظ المشروع بصيغة XML
`SaveFileFormat` يعدد صيغ الإخراج المدعومة لحفظ المشروع، بما في ذلك XML.

```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```

#### الخطوة 7: عرض النتيجة
`System.out.println` يطبع سطرًا من النص إلى مخرجات وحدة التحكم القياسية.

```java
System.out.println("Process completed Successfully");
```

## المشكلات الشائعة والنصائح
- **تعارض معرف السمة:** استدعِ دائمًا `project.getExtendedAttributes().getById(id)` قبل إنشاء تعريف جديد لتجنب تكرار المعرفات.  
- **معالجة الدقة:** فضلًا استخدم `BigDecimal` بدلاً من `float`/`double` للقيم العددية الدقيقة؛ هذا يمنع أخطاء التقريب في التقارير.  
- **موثوقية مسار الملف:** استخدم `Paths.get(...).toAbsolutePath()` أو اضبط دليل العمل في IDE لتجنب `FileNotFoundException`.  

## الأسئلة المتكررة

**س: هل يمكنني إنشاء سمات مخصصة للمهام وكذلك للموارد؟**  
ج: نعم – استخدم `ExtendedAttributeTask` بدلاً من `ExtendedAttributeResource` عند تعريف مخطط السمة.

**س: هل يمكن إضافة عدة سمات مخصصة مرة واحدة؟**  
ج: بالتأكيد. أنشئ كائنات `ExtendedAttributeDefinition` منفصلة لكل سمة وأرفقها بالموارد أو المهام المطلوبة.

**س: ما الصيغ التي يمكنني حفظ المشروع بها؟**  
ج: تدعم Aspose.Tasks صيغ XML، MPP، PDF، HTML، وأكثر من 30 صيغة إضافية. في هذا المثال استخدمنا `SaveFileFormat.Xml`.

**س: هل أحتاج إلى ترخيص لإصدارات التطوير؟**  
ج: الترخيص التجريبي المؤقت يكفي للاختبار. لأي نشر إنتاجي، يلزم ترخيص تجاري كامل.

**س: كيف يمكنني قراءة قيم السمة المخصصة لاحقًا؟**  
ج: استدعِ `resource.getExtendedAttributes()` وتكرّر عبر المجموعة؛ استرجع القيمة المخزنة باستخدام `getNumericValue()` أو `getTextValue()`.

---

**آخر تحديث:** 2026-06-10  
**تم الاختبار مع:** Aspose.Tasks for Java 24.12  
**المؤلف:** Aspose

## دروس ذات صلة

- [كيفية إنشاء الموارد – إدارة الموارد باستخدام Aspose.Tasks for Java](/tasks/java/resource-management/)
- [إنشاء حقل مخصص Aspose - التعامل مع السمات الموسعة](/tasks/java/project-management/extended-attributes/)
- [كيفية إنشاء مشروع – تعيين سمات مهام جديدة باستخدام Aspose.Tasks](/tasks/java/project-file-operations/set-attributes-new-tasks/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}