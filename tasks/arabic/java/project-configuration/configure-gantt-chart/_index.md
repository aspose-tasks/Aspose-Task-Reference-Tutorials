---
date: 2025-12-09
description: تعلم كيفية تعيين دليل البيانات وتكوين عرض مخطط جانت في Aspose.Tasks باستخدام
  Java. يوضح هذا الدليل أيضًا كيفية تخصيص حقول الجدول وتكوين مشاريع مخطط جانت في Java
  خطوة بخطوة.
linktitle: Set Data Directory for Gantt Chart View in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: تعيين دليل البيانات لعرض مخطط جانت في Aspose.Tasks
url: /ar/java/project-configuration/configure-gantt-chart/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تعيين دليل البيانات لعرض مخطط جانت في Aspose.Tasks

## المقدمة
في هذا البرنامج التعليمي، ستتعلم **كيفية تعيين دليل البيانات** وتكوين عرض مخطط جانت لمشروع MS في مشاريع Aspose.Tasks باستخدام Java. Aspose.Tasks هي واجهة برمجة تطبيقات Java قوية تتيح لك التعامل مع ملفات Microsoft Project برمجياً. بحلول نهاية هذا الدليل، ستكون قادرًا على **تخصيص حقول الجدول**، وضبط دليل البيانات، وتصور مشروعك بالضبط كما تحتاج.

## الإجابات السريعة
- **ما هي الخطوة الأولى؟** تعيين مسار دليل البيانات حيث توجد ملفات مشروعك.  
- **ما المكتبة المطلوبة؟** Aspose.Tasks for Java (قابلة للتنزيل من الموقع الرسمي).  
- **هل يمكنني إضافة سمات مخصصة؟** نعم – يمكنك تعريف سمات موسعة وعرضها في مخطط جانت.  
- **هل أحتاج إلى ترخيص للاختبار؟** ترخيص مؤقت متاح لأغراض التقييم.  
- **ما هو بيئة التطوير المتكاملة (IDE) الأنسب؟** أي بيئة تطوير Java (IntelliJ IDEA، Eclipse، NetBeans) ستعمل.

## ما هو “تعيين دليل البيانات” ولماذا هو مهم؟
تعيين دليل البيانات يخبر Aspose.Tasks أين يقرأ ويكتب ملفات المشروع. بدون مسار صحيح لا يمكن للواجهة البرمجية تحديد موقع ملفات `.mpp` الخاصة بك، مما يؤدي إلى أخطاء FileNotFound. تعريف هذا الدليل في بداية الكود يجعل سير العمل المتبقي نظيفًا وقابلاً للتكرار.

## لماذا تخصيص حقول الجدول في مخطط جانت؟
تسمح لك حقول الجدول المخصصة بإظهار معلومات إضافية—مثل السمات المخصصة، بيانات الموارد، أو ملاحظات خاصة بالمشروع—مباشرةً في عرض جانت. هذا يجعل المخطط أكثر إفادة لأصحاب المصلحة ويقلل الحاجة للتبديل بين تقارير متعددة.

## المتطلبات المسبقة
قبل أن تبدأ، تأكد من أن لديك:

1. **Java Development Kit (JDK)** – أي نسخة حديثة (8+).  
2. **Aspose.Tasks Library** – قم بتنزيلها من [here](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA، Eclipse، أو أي محرر متوافق مع Java تفضله.

## استيراد الحزم
أولاً، استورد مساحة الأسماء Aspose.Tasks حتى تتمكن من العمل مع فئاتها:

```java
import com.aspose.tasks.*;
```

## دليل خطوة بخطوة

### الخطوة 1: إعداد دليل البيانات
حدد المجلد الذي يحتوي على ملفات مشروعك. هذه هي خطوة **تعيين دليل البيانات** التي يركز عليها البرنامج التعليمي.

```java
String dataDir = "Your Data Directory";
```

استبدل `"Your Data Directory"` بالمسار المطلق للمجلد الذي يتم فيه تخزين `project.mpp`.

### الخطوة 2: تحميل ملف المشروع
أنشئ كائن `Project` بتحميل ملف Microsoft Project موجود.

```java
Project project = new Project(dataDir + "project.mpp");
```

### الخطوة 3: إضافة نشاط جديد
أدرج مهمة جديدة (نشاط) في جذر المشروع.

```java
Task task = project.getRootTask().getChildren().add("New Activity");
```

### الخطوة 4: تعريف سمة مخصصة
أنشئ تعريف سمة مخصصة يمكنك لاحقًا إرفاقها بالمهام.

```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```

### الخطوة 5: إضافة سمة مخصصة إلى المهمة
قم بتعيين السمة التي تم تعريفها حديثًا إلى المهمة التي أنشأتها.

```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```

### الخطوة 6: تخصيص الجدول – **customize table fields**
أضف السمة المخصصة كعمود في جدول مخطط جانت، مع تحديد العرض والعنوان والمحاذاة.

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
احفظ التغييرات في ملف جديد يمكن فتحه في Microsoft Project.

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## المشكلات الشائعة والحلول
| المشكلة | سبب حدوثها | الحل |
|---------|------------|------|
| **FileNotFoundException** عند تحميل المشروع | مسار **تعيين دليل البيانات** غير صحيح أو يفتقد إلى الشرطة المائلة النهائية. | تحقق من أن `dataDir` يشير إلى المجلد الدقيق وتضمن الفاصل المناسب للملفات (`/` أو `\\`). |
| السمة المخصصة غير مرئية في عرض جانت | تم إضافة حقل الجدول في الفهرس الخاطئ أو عرض العمود صغير جدًا. | تأكد من أن `table.getTableFields().add(3, attrField);` يستخدم فهرسًا صالحًا واضبط `setWidth` حسب الحاجة. |
| LicenseException عند الحفظ | لم يتم تطبيق ترخيص صالح للاستخدام في الإنتاج. | طبق ترخيصًا مؤقتًا أو دائمًا قبل استدعاء `project.save()`. |

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Tasks مع لغات برمجة أخرى؟**  
**ج:** نعم، Aspose.Tasks متاحة لعدة لغات برمجة بما في ذلك .NET و Java و C++.

**س: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Tasks؟**  
**ج:** نعم، يمكنك تنزيل نسخة تجريبية مجانية من [here](https://releases.aspose.com/).

**س: أين يمكنني العثور على الدعم لـ Aspose.Tasks؟**  
**ج:** يمكنك العثور على الدعم وطرح الأسئلة في [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

**س: كيف يمكنني شراء ترخيص لـ Aspose.Tasks؟**  
**ج:** يمكنك شراء ترخيص من [here](https://purchase.aspose.com/buy).

**س: هل أحتاج إلى ترخيص مؤقت لأغراض الاختبار؟**  
**ج:** نعم، يمكنك الحصول على ترخيص مؤقت من [here](https://purchase.aspose.com/temporary-license/).

## الخلاصة
لقد تعلمت الآن كيفية **تعيين دليل البيانات**، إضافة نشاط جديد، تعريف وإرفاق سمة مخصصة، و**تخصيص حقول الجدول** في عرض مخطط جانت باستخدام Aspose.Tasks للـ Java. تمنحك هذه الخطوات سيطرة كاملة على طريقة عرض بيانات المشروع، مما يجعل مخططات جانت أكثر إفادة ومصممة لتلبية احتياجات أصحاب المصلحة.

---

**آخر تحديث:** 2025-12-09  
**تم الاختبار مع:** Aspose.Tasks Java 24.12 (latest)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}