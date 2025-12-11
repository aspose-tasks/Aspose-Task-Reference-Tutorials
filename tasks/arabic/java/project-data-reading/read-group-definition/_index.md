---
date: 2025-12-11
description: تعلم كيفية قراءة بيانات تعريف المجموعات من ملفات Microsoft Project باستخدام
  Aspose.Tasks للغة Java. اتبع دليلنا خطوة بخطوة.
linktitle: Read Group Definition Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: قراءة بيانات تعريف المجموعة في Aspose.Tasks
url: /ar/java/project-data-reading/read-group-definition/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# قراءة بيانات تعريف المجموعة في Aspose.Tasks

## المقدمة
Aspose.Tasks for Java هي مكتبة قوية تتيح للمطورين التعامل مع ملفات Microsoft Project بسهولة. في هذا الدرس، **ستتعلم كيفية قراءة بيانات تعريف المجموعة** من ملف مشروع خطوة بخطوة، حتى تتمكن من استخراج والعمل مع معلومات مجموعة المهام في تطبيقات Java الخاصة بك.

## إجابات سريعة
- **ماذا يعني “قراءة تعريف المجموعة”?** يشير إلى استخراج تعريف مجموعات المهام (الاسم، المعايير، التنسيق) من ملف Microsoft Project.  
- **أي مكتبة أحتاجها؟** Aspose.Tasks for Java.  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تعمل للتطوير؛ يلزم ترخيص تجاري للإنتاج.  
- **ما هي بيئات التطوير المتكاملة المدعومة؟** أي بيئة تطوير Java مثل IntelliJ IDEA أو Eclipse.  
- **كم عدد أسطر الكود المطلوبة؟** أقل من 30 سطرًا من كود Java لتحميل مشروع وعرض تفاصيل المجموعة.

## ما هي قراءة تعريف المجموعة؟
*تعريف المجموعة* في Microsoft Project يصف كيفية تجميع المهام معًا بناءً على معايير (مثل الحالة، الأولوية). قراءة هذا التعريف يتيح لك فحص منطق التجميع، الألوان، الخطوط، وترتيب الفرز المطبق في ملف المشروع برمجيًا.

## لماذا قراءة بيانات تعريف المجموعة؟
- **الأتمتة:** إنشاء تقارير مخصصة تعكس التجميع الذي تراه في Project.  
- **الهجرة:** نقل قواعد التجميع إلى مشروع آخر أو نظام إدارة مشاريع مختلف.  
- **التحقق:** التأكد من وجود المجموعات المتوقعة قبل تنفيذ التحديثات الجماعية.  
- **التخصيص:** تطبيق منطق أعمال إضافي بناءً على إعدادات الخط أو اللون للمجموعة.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من أن لديك ما يلي:

1. **Java Development Kit (JDK)** – أي نسخة حديثة (8 أو أحدث).  
2. **Aspose.Tasks for Java Library** – قم بتنزيله من [here](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA، Eclipse، أو أي محرر تفضله.  

## استيراد الحزم
أولاً، استورد حزمة Aspose.Tasks الأساسية:

```java
import com.aspose.tasks.*;
```

## دليل خطوة بخطوة

### الخطوة 1: إعداد دليل البيانات الخاص بك
حدد المجلد الذي يحتوي على ملف `.mpp` الذي تريد فحصه.

```java
String dataDir = "Your Data Directory";
```

استبدل `"Your Data Directory"` بالمسار المطلق لموقع ملف المشروع الخاص بك.

### الخطوة 2: تحميل ملف المشروع
أنشئ كائن `Project` بالإشارة إلى ملف `.mpp` الخاص بك.

```java
Project project = new Project(dataDir + "project.mpp");
```

### الخطوة 3: استرجاع عدد مجموعات المهام
اطبع العدد الإجمالي لمجموعات المهام المعرفة في المشروع.

```java
System.out.println("Task Groups Count: " + project.getTaskGroups().size());
```

### الخطوة 4: استرجاع معلومات مجموعة مهام محددة
احصل على مجموعة معينة (الفهرس 1 في هذا المثال) واعرض اسمها وعدد المعايير التي تحتويها.

```java
Group taskGroup = project.getTaskGroups().toList().get(1);
System.out.println("Percent Complete:" + taskGroup.getName());
System.out.println("Group Criteria count: " + taskGroup.getGroupCriteria().size());
```

### الخطوة 5: استرجاع معلومات معيار المجموعة
يمكن لكل مجموعة أن تحتوي على معيار واحد أو أكثر. المقتطف أدناه يستخرج تفاصيل مثل الحقل المستخدم للتجميع، وضع التجميع، لون الخلية، والنمط.

```java
GroupCriterion criterion = taskGroup.getGroupCriteria().toList().get(0);
System.out.println("Criterion Field: " + criterion.getField());
System.out.println("Criterion GroupOn: " + criterion.getGroupOn());
System.out.println("Criterion Cell Color: " + criterion.getCellColor());
System.out.println("Criterion Pattern: " + criterion.getPattern());
```

### الخطوة 6: التحقق من المجموعة الأم
أحيانًا يكون المعيار تابعًا لمجموعة أم. هذا الفحص يؤكد العلاقة.

```java
if (taskGroup == criterion.getParentGroup())
    System.out.println("Parent Group is equval to task Group.");
```

### الخطوة 7: استرجاع معلومات خط المعيار
يمكن لمعايير المجموعة أن تحتوي على تنسيق خط مخصص. الكود التالي يطبع عائلة الخط، الحجم، النمط، واتجاه الفرز.

```java
System.out.println("Font Family Name: " + criterion.getFont().getFontFamily());
System.out.println("Font Size: " + criterion.getFont().getSize());
System.out.println("Font Style: " + criterion.getFont().getStyle());
System.out.println("Ascending/Descending: " + criterion.getAscending());
```

## المشكلات الشائعة والحلول

| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **`NullPointerException` on `criterion.getParentGroup()`** | قد لا يكون للمعيار مجموعة أم. | أضف فحصًا للـ null قبل المقارنة. |
| **File not found** | `مسار dataDir` غير صحيح. | استخدم `Paths.get(dataDir, "project.mpp").toAbsolutePath()` للتحقق. |
| **License not set** | مكتبة Aspose تعمل في وضع التقييم وقد تقيد الإخراج. | سجّل ترخيصك باستخدام `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` |

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Tasks for Java لتعديل ملفات المشروع؟**  
ج: نعم، المكتبة توفر إمكانيات قراءة/كتابة كاملة لملفات Microsoft Project.

**س: هل Aspose.Tasks for Java متوافق مع جميع إصدارات ملفات Microsoft Project؟**  
ج: يدعم MPP، XML، وغيرها من تنسيقات Project الشائعة عبر إصدارات متعددة.

**س: كيف يمكنني التعامل مع الأخطاء أثناء العمل مع Aspose.Tasks for Java؟**  
ج: غلف عمليات الملفات بكتل `try‑catch` وتفحص `TasksException` للحصول على رسائل مفصلة.

**س: هل يوفر Aspose.Tasks for Java دعمًا لتصدير بيانات المشروع إلى تنسيقات أخرى؟**  
ج: بالتأكيد – يمكنك التصدير إلى PDF، XLSX، CSV، وأكثر باستخدام واجهات برمجة تطبيقات التصدير في المكتبة.

**س: أين يمكنني العثور على موارد إضافية ودعم لـ Aspose.Tasks for Java؟**  
ج: زر [توثيق Aspose.Tasks for Java](https://reference.aspose.com/tasks/java/) للحصول على مراجع API كاملة و[منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15) للحصول على مساعدة المجتمع.

## الخلاصة
في هذا الدرس استعرضنا كيفية **قراءة تعريف المجموعة** من ملف Microsoft Project باستخدام Aspose.Tasks for Java. باتباع الخطوات أعلاه يمكنك استخراج أسماء المجموعات، المعايير، التنسيق، وعلاقات المجموعة‑الأم، مما يمكنك من بناء تقارير مخصصة، نقل الإعدادات، أو أتمتة منطق التحقق في تطبيقات Java الخاصة بك.

---

**آخر تحديث:** 2025-12-11  
**تم الاختبار مع:** Aspose.Tasks for Java 24.12  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}