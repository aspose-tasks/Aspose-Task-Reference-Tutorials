---
date: 2025-12-07
description: تعرّف على كيفية حفظ ملف المشروع، كتابة وقراءة صيغ MS Project، وإضافة
  صيغ الحقول المخصصة باستخدام Aspose.Tasks للغة Java.
linktitle: Save Project File & Write Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: حفظ ملف المشروع وكتابة صيغ MS Project باستخدام Aspose.Tasks
url: /ar/java/formulas/write-read-formulas/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# حفظ ملف المشروع وكتابة صيغ MS Project باستخدام Aspose.Tasks

## المقدمة
في مجال إدارة المشاريع، يعتبر التعامل الفعال مع البيانات أمرًا حيويًا. Aspose.Tasks for Java هو حل قوي يسهّل تعديل واستخراج البيانات من ملفات Microsoft Project. إحدى الميزات القوية التي يقدمها هي القدرة على كتابة وقراءة صيغ MS Project. **سوف تتعلم أيضًا كيفية *حفظ ملف المشروع* بعد تطبيق تلك الصيغ**، مما يضمن بقاء تغييراتك محفوظة للتحليل المستقبلي. سيوجهك هذا البرنامج التعليمي خلال عملية الاستفادة من هذه الوظيفة لتعزيز مهام إدارة المشروع الخاصة بك.

## إجابات سريعة
- **ماذا يفعل “حفظ ملف المشروع”؟** يكتب جميع التغييرات الموجودة في الذاكرة إلى ملف .mpp على القرص.  
- **هل يمكنني إضافة صيغ حقول مخصصة؟** نعم – يمكنك إنشاء حقل مخصص وتعيين صيغة مثل “مضاعفة تكلفة المهمة”.  
- **هل أحتاج إلى ترخيص لتشغيل الكود؟** النسخة التجريبية المجانية تكفي للتقييم؛ الترخيص التجاري مطلوب للإنتاج.  
- **أي بيئة تطوير متكاملة (IDE) هي الأنسب؟** أي بيئة Java (IntelliJ IDEA، Eclipse، VS Code) ستتمكن من تجميع العينة.  
- **هل API متوافق مع أحدث نسخة من MS Project؟** Aspose.Tasks يدعم جميع تنسيقات .mpp الحديثة.

## ما هو “حفظ ملف المشروع” في Aspose.Tasks؟
حفظ ملف المشروع يعني تثبيت الحالة الحالية لكائن `Project`—بما في ذلك المهام والموارد وأي صيغ مخصصة—في ملف Microsoft Project فعلي (`.mpp`). هذه العملية ضرورية بعد تعديل البيانات، مثل إضافة حقل مخصص أو تغيير تكاليف المهمة.

## لماذا نضيف حقلًا مخصصًا وننشئ صيغة حقل مخصص؟
إضافة حقل مخصص يمنحك حاوية مرنة لمعلومات إضافية لا تغطيها الحقول الافتراضية. من خلال إرفاق صيغة—مثل تلك التي **مضاعفة تكلفة المهمة**—تُؤتمت الحسابات، وتقل الأخطاء اليدوية، وتبقى بيانات الجدول متسقة.

## المتطلبات المسبقة
قبل الغوص في هذا البرنامج التعليمي، تأكد من توفر المتطلبات التالية:

1. **مجموعة تطوير جافا (JDK)** – Java 8 أو أعلى مثبتة على جهازك.  
2. **Aspose.Tasks for Java** – قم بتنزيله وتثبيته من [هنا](https://releases.aspose.com/tasks/java/).  
3. **بيئة تطوير متكاملة (IDE)** – اختر البيئة المفضلة لتطوير Java (IntelliJ IDEA، Eclipse، VS Code، إلخ).  

## استيراد الحزم
لبدء العمل، استورد الحزم اللازمة إلى مشروع Java الخاص بك:

```java
import com.aspose.tasks.*;
import java.io.IOException;
import java.math.BigDecimal;
import java.util.Objects;
```

## الخطوة 1: إعداد دليل البيانات
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```
حدد المجلد الذي توجد فيه ملفات MS Project. هذا هو المكان الذي ستحمّل منه الملف المصدر ولاحقًا **تحفظ ملف المشروع**.

## الخطوة 2: تحميل ملف المشروع
```java
Project project = new Project(dataDir + "project.mpp");
```
حمّل ملف Microsoft Project الموجود إلى كائن `Project` لتتمكن من قراءة محتوياته أو تعديلها.

## الخطوة 3: إضافة حقل مخصص وإنشاء صيغة حقل مخصص
```java
project.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(
        CustomFieldType.Text, ExtendedAttributeTask.Text1, "Custom");
attr.setAlias("Double Costs");
attr.setFormula("[Cost]*2");   // This formula doubles the task cost
project.getExtendedAttributes().add(attr);
```
في هذه الخطوة **نضيف حقلًا مخصصًا** باسم “Double Costs” **وننشئ صيغة حقل مخصص** تضرب `[Cost]` للمهمة في 2، وبالتالي **مضاعفة تكلفة المهمة**. طريقة `setFormula` تدمج الحساب مباشرةً في ملف المشروع.

## الخطوة 4: إضافة مهمة وتحديد التكلفة
```java
Task task = project.getRootTask().getChildren().add("Task");
task.set(Tsk.COST, BigDecimal.valueOf(100));
```
أنشئ مهمة جديدة، ثم عيّن تكلفة أساسية قدرها `100`. عند حفظ المشروع، سيظهر الحقل المخصص تلقائيًا القيمة `200` بفضل الصيغة المعرفة مسبقًا.

## الخطوة 5: حفظ ملف المشروع
```java
project.save(dataDir + "saved.mpp", SaveFileFormat.Mpp);
```
أخيرًا، **احفظ ملف** مع جميع التعديلات. طريقة `save` تكتب المشروع المحدث، بما في ذلك الحقل المخصص الجديد والقيم المحسوبة، إلى `saved.mpp`.

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|--------|-----|
| **الصيغة غير مطبقة** | لم يُضاف الحقل المخصص إلى مجموعة `ExtendedAttributes` للمشروع. | تأكد من تنفيذ `project.getExtendedAttributes().add(attr);` قبل الحفظ. |
| **الملف غير موجود** | مسار `dataDir` غير صحيح. | تحقق من أن سلسلة الدليل تنتهي بفاصل مسار (`/` أو `\\`). |
| **التكلفة تظهر كصفر** | لم تُحدد تكلفة المهمة قبل الحفظ. | استدعِ `task.set(Tsk.COST, ...)` قبل `project.save`. |

## الأسئلة المتكررة
**س: هل Aspose.Tasks متوافق مع جميع إصدارات MS Project؟**  
ج: نعم، يدعم Aspose.Tasks مجموعة واسعة من إصدارات MS Project، من تنسيقات .mpp القديمة إلى الإصدارات الأحدث.

**س: هل يمكنني دمج Aspose.Tasks في مشروع Java الحالي؟**  
ج: بالطبع. تم تصميم API لتكامل سلس؛ ما عليك سوى إضافة ملف JAR الخاص بـ Aspose.Tasks إلى مسار الفئة (classpath) لمشروعك.

**س: هل هناك أي قيود على أنواع الصيغ التي يمكنني إنشاؤها؟**  
ج: المكتبة تدعم معظم صيغ MS Project الأصلية، بما في ذلك العمليات الحسابية، المنطقية، والدوال المدمجة. قد تتطلب الدوال المخصصة المعقدة حلولًا بديلة.

**س: هل يدعم Aspose.Tasks النشر عبر منصات متعددة؟**  
ج: نعم، تعمل المكتبة على أي منصة تدعم Java، بما في ذلك Windows وLinux وmacOS.

**س: كيف يمكنني الحصول على الدعم الفني لـ Aspose.Tasks؟**  
ج: زر [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15) للحصول على مساعدة المجتمع، أو افتح تذكرة دعم إذا كان لديك ترخيص تجاري.

## الخاتمة
في هذا البرنامج التعليمي غطينا كيفية **حفظ ملف المشروع**، **إضافة حقل مخصص**، و**إنشاء صيغة حقل مخصص** تقوم **بمضاعفة تكلفة المهمة** باستخدام Aspose.Tasks for Java. باتباع هذه الخطوات يمكنك أتمتة الحسابات، إغناء بيانات مشروعك، وضمان بقاء جميع التغييرات محفوظة للتقارير والتحليل المستقبلي.

---

**آخر تحديث:** 2025-12-07  
**تم الاختبار مع:** Aspose.Tasks for Java 24.12  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}