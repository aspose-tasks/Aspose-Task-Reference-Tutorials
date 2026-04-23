---
date: 2026-02-13
description: تعلم كيفية إنشاء نشاط جديد، وتعيين دليل البيانات، وحفظ المشروع كملف MPP
  في Aspose.Tasks Java. يغطي هذا الدليل خطوة بخطوة أيضًا تخصيص حقول الجدول.
linktitle: How to Create New Activity & Set Data Directory Aspose.Tasks
second_title: Aspose.Tasks Java API
title: كيفية إنشاء نشاط جديد وتعيين دليل البيانات Aspose.Tasks
url: /ar/java/project-configuration/configure-gantt-chart/
weight: 10
---

-left but we just output Arabic sentences.

Proceed.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية إنشاء نشاط جديد وتعيين دليل البيانات Aspose.Tasks

## مقدمة
في هذا البرنامج التعليمي، ستتعلم **كيفية تعيين دليل البيانات**، وكيف **إنشاء نشاط جديد**، وكيف **حفظ المشروع بصيغة MPP** مع تكوين عرض مخطط Gantt في مشاريع Aspose.Tasks باستخدام Java. Aspose.Tasks هي واجهة برمجة تطبيقات Java قوية تتيح لك معالجة ملفات Microsoft Project برمجياً. بنهاية هذا الدليل ستتمكن من **تخصيص حقول الجدول**، وضبط دليل البيانات، وعرض مشروعك exactement كما تحتاج.

## إجابات سريعة
- **ما هي الخطوة الأولى؟** تعيين مسار دليل البيانات حيث توجد ملفات المشروع الخاصة بك.  
- **ما المكتبة المطلوبة؟** Aspose.Tasks for Java (متاحة للتحميل من الموقع الرسمي).  
- **هل يمكنني إضافة سمات مخصصة؟** نعم – يمكنك تعريف سمات موسعة وعرضها في مخطط Gantt.  
- **هل أحتاج إلى ترخيص للاختبار؟** ترخيص مؤقت متاح لأغراض التقييم.  
- **أي بيئة تطوير متكاملة (IDE) هي الأنسب؟** أي IDE للـ Java (IntelliJ IDEA، Eclipse، NetBeans) سيعمل.

## ما هو “تعيين دليل البيانات” ولماذا هو مهم؟
تعيين دليل البيانات يخبر Aspose.Tasks أين يقرأ ويكتب ملفات المشروع. بدون مسار صحيح لا تستطيع الواجهة البرمجية العثور على ملفات `.mpp`، مما يؤدي إلى أخطاء FileNotFound. تعريف هذا الدليل في بداية الكود يجعل سير العمل باقيًا نظيفًا وقابلاً للتكرار.

## لماذا نخصص حقول الجدول في مخطط Gantt؟
حقول الجدول المخصصة تتيح لك إظهار معلومات إضافية—مثل السمات المخصصة، بيانات الموارد، أو ملاحظات خاصة بالمشروع—مباشرة في عرض الـ Gantt. هذا يجعل المخطط أكثر إفادة لأصحاب المصلحة ويقلل الحاجة للتنقل بين تقارير متعددة.

## كيف ننشئ نشاطًا جديدًا؟
إنشاء نشاط جديد (مهمة) هو أحد العمليات الأساسية عند بناء أو تحديث جدول زمني للمشروع. بإضافة المهام برمجياً يمكنك أتمتة إنشاء خطط مشروع معقدة، دمج البيانات من أنظمة أخرى، أو تطبيق تغييرات جماعية دون تحرير يدوي.

## المتطلبات المسبقة
قبل البدء، تأكد من أن لديك:

1. **مجموعة تطوير Java (JDK)** – أي نسخة حديثة (8+).  
2. **مكتبة Aspose.Tasks** – حمّلها من [هنا](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA، Eclipse، أو أي محرر يدعم Java تفضله.

## استيراد الحزم
أولاً، استورد مساحة أسماء Aspose.Tasks لتتمكن من العمل مع فئاتها:

```java
import com.aspose.tasks.*;
```

## دليل خطوة بخطوة

### الخطوة 1: إعداد دليل البيانات
عرّف المجلد الذي يحتوي على ملفات مشروعك. هذه هي خطوة **تعيين دليل البيانات** التي يركز عليها البرنامج التعليمي.

```java
String dataDir = "Your Data Directory";
```

استبدل `"Your Data Directory"` بالمسار المطلق للمجلد الذي يُخزن فيه `project.mpp`.

### الخطوة 2: تحميل ملف المشروع
أنشئ كائن `Project` بتحميل ملف Microsoft Project موجود.

```java
Project project = new Project(dataDir + "project.mpp");
```

### الخطوة 3: إضافة نشاط جديد
أدرج مهمة (نشاط) جديدة في جذر المشروع. هذا يوضح **كيفية إنشاء نشاط جديد** برمجياً.

```java
Task task = project.getRootTask().getChildren().add("New Activity");
```

### الخطوة 4: تعريف سمة مخصصة
أنشئ تعريف سمة مخصصة يمكنك لاحقاً ربطه بالمهام.

```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```

### الخطوة 5: إضافة السمة المخصصة إلى المهمة
عيّن السمة التي عرّفتها حديثاً إلى المهمة التي أنشأتها.

```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```

### الخطوة 6: تخصيص الجدول – **تخصيص حقول الجدول**
أضف السمة المخصصة كعمود في جدول مخطط Gantt، مع تحديد العرض، العنوان، والمحاذاة.

```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```

### الخطوة 7: حفظ المشروع
احفظ التغييرات في ملف جديد يمكن فتحه في Microsoft Project. هذه الخطوة **تحفظ المشروع بصيغة MPP**.

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|--------|------|
| **FileNotFoundException** عند تحميل المشروع | مسار **تعيين دليل البيانات** غير صحيح أو يفتقد الشرطة المائلة النهائية. | تحقق من أن `dataDir` يشير إلى المجلد الدقيق وأضف الفاصل المناسب (`/` أو `\\`). |
| السمة المخصصة غير مرئية في عرض Gantt | تم إضافة حقل الجدول في الفهرس الخطأ أو عرض العمود صغير جداً. | تأكد من أن `table.getTableFields().add(3, attrField);` يستخدم فهرساً صالحاً واضبط `setWidth` حسب الحاجة. |
| LicenseException عند الحفظ | لم يتم تطبيق ترخيص صالح للاستخدام الإنتاجي. | طبق ترخيصاً مؤقتاً أو دائماً قبل استدعاء `project.save()`. |

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Tasks مع لغات برمجة أخرى؟**  
ج: نعم، Aspose.Tasks متاح لعدة لغات برمجة تشمل .NET، Java، و C++.

**س: هل هناك نسخة تجريبية مجانية من Aspose.Tasks؟**  
ج: نعم، يمكنك تحميل نسخة تجريبية مجانية من [هنا](https://releases.aspose.com/).

**س: أين يمكنني الحصول على الدعم الخاص بـ Aspose.Tasks؟**  
ج: يمكنك العثور على الدعم وطرح الأسئلة في [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

**س: كيف يمكنني شراء ترخيص لـ Aspose.Tasks؟**  
ج: يمكنك شراء الترخيص من [هنا](https://purchase.aspose.com/buy).

**س: هل أحتاج إلى ترخيص مؤقت لأغراض الاختبار؟**  
ج: نعم، يمكنك الحصول على ترخيص مؤقت من [هنا](https://purchase.aspose.com/temporary-license/).

## الخاتمة
لقد تعلمت الآن **تعيين دليل البيانات**، **إنشاء نشاط جديد**، تعريف وإرفاق سمة مخصصة، و**حفظ المشروع بصيغة MPP** مع **تخصيص حقول الجدول** في عرض مخطط Gantt باستخدام Aspose.Tasks for Java. تمنحك هذه الخطوات تحكمًا كاملاً في طريقة عرض بيانات المشروع، مما يجعل مخططات Gantt أكثر إفادة وتخصيصًا لاحتياجات أصحاب المصلحة.

---

**آخر تحديث:** 2026-02-13  
**تم الاختبار مع:** Aspose.Tasks Java 24.12 (الأحدث)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}