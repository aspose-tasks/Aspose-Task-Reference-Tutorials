---
date: 2026-01-02
description: تعلم كيفية حساب النسبة المئوية لتعيينات الموارد في مشاريع جافا باستخدام
  Aspose.Tasks، مما يبسط إدارة مشاريع جافا ويحسن استغلال الموارد.
linktitle: How to Calculate Percentage for Resources with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: كيفية حساب النسبة المئوية للموارد باستخدام Aspose.Tasks
url: /ar/java/resource-assignments/calculate-percentages/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية حساب النسبة المئوية للموارد باستخدام Aspose.Tasks

## المقدمة
إن حساب **كيفية حساب النسبة المئوية** للعمل المكتمل لكل تعيين مورد بدقة هو جزء أساسي من **إدارة مشاريع جافا** الفعّالة. سواء كنت تتعقب **نسبة إكمال المشروع** أو تراقب **نسبة استخدام الموارد**، فإن Aspose.Tasks for Java يوفّر لك طريقة برمجية نظيفة لاستخراج تلك الأرقام مباشرةً من ملفات .mpp الخاصة بك. في هذا البرنامج التعليمي سنستعرض **دليل تعيين الموارد** خطوة بخطوة بسيط يمكنك دمجه في أي مشروع جافا.

## إجابات سريعة
- **ما الذي تمثله النسبة المئوية؟** تُظهر نسبة العمل المكتمل لتعيين مورد معين.  
- **أي فئة توفر القيمة؟** `ResourceAssignment` مع الحقل `Asn.PERCENT_WORK_COMPLETE`.  
- **هل أحتاج إلى ترخيص لتشغيل الكود؟** النسخة التجريبية المجانية تكفي للتطوير؛ يلزم ترخيص تجاري للإنتاج.  
- **هل يمكنني استخدام هذا مع بيئات تطوير جافا الأخرى؟** نعم—IntelliJ IDEA، Eclipse، NetBeans، أو أي بيئة تطوير متوافقة مع جافا.  
- **هل الـ API آمن للاستخدام المتعدد الخيوط؟** قراءة قيم التعيين آمنة؛ تعديل بيانات المشروع يجب أن يتم بشكل متزامن.

## المتطلبات المسبقة
قبل الغوص في الكود، تأكد من إعداد ما يلي:

### بيئة تطوير جافا
تأكد من تثبيت مجموعة تطوير جافا (JDK) على نظامك. يمكنك تنزيلها من [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### مكتبة Aspose.Tasks لجافا
قم بتنزيل وتثبيت مكتبة Aspose.Tasks لجافا. يمكنك العثور على رابط التنزيل [here](https://releases.aspose.com/tasks/java/).

### بيئة التطوير المتكاملة (IDE)
اختر بيئة تطوير حسب تفضيلك مثل IntelliJ IDEA أو Eclipse أو NetBeans للبرمجة. 

## استيراد الحزم
للبدء، استورد الحزم الضرورية في كود جافا الخاص بك:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
```

## الخطوة 1: إعداد دليل البيانات الخاص بك
تأكد من وجود دليل مخصص حيث توجد بيانات مشروعك. ستستخدم هذا الدليل للوصول إلى ملفات المشروع.
```java
String dataDir = "Your Data Directory";
```

## الخطوة 2: تحميل ملف المشروع
أنشئ كائن `Project` وحمّل ملف المشروع باستخدام دليل البيانات المحدد.
```java
Project project = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```

## الخطوة 3: التكرار عبر تعيينات الموارد
تجول عبر جميع تعيينات الموارد في المشروع للوصول إلى تفاصيل كل تعيين.
```java
for (ResourceAssignment ra : project.getResourceAssignments()) {
    // Perform operations on each resource assignment
}
```

## الخطوة 4: حساب نسبة إكمال العمل
استرجع نسبة إكمال العمل لكل تعيين مورد باستخدام Aspose.Tasks.
```java
for (ResourceAssignment ra : project.getResourceAssignments()) {
    System.out.println(ra.get(Asn.PERCENT_WORK_COMPLETE).toString());
}
```

## لماذا هذا مهم
معرفة **نسبة استخدام الموارد** تساعدك على:
- اكتشاف الإفراط في تخصيص الموارد قبل أن يصبح عنق زجاجة.  
- إنشاء تقارير حالة دقيقة لأصحاب المصلحة.  
- أتمتة لوحات المعلومات التي تعرض **نسبة إكمال المشروع** في الوقت الفعلي.

## المشكلات الشائعة والنصائح
- **القيم الفارغة:** قد لا تحتوي بعض التعيينات على نسبة مئوية محددة؛ تحقق دائمًا من `null` قبل استدعاء `toString()`.  
- **البيانات الزمنية المرحلية:** الـ API يعيد النسبة العامة؛ إذا كنت تحتاج قيمًا يومية، استكشف مجموعة `TimephasedData`.  
- **الأداء:** بالنسبة لملفات .mpp الكبيرة جدًا، استخدم حلقة `for` كما هو موضح بدلاً من استخدام الـ streams للحفاظ على استهلاك الذاكرة منخفضًا.  

## الأسئلة المتكررة
### س: هل يمكن لـ Aspose.Tasks التعامل مع هياكل مشاريع معقدة؟
نعم، يدعم Aspose.Tasks التعامل مع هياكل مشاريع معقدة بسهولة، مما يتيح لك إدارة المشاريع بأي حجم.

### س: هل Aspose.Tasks مناسب لإدارة المشاريع على مستوى المؤسسات؟
بالطبع، يقدم Aspose.Tasks ميزات قوية مخصصة لإدارة المشاريع على مستوى المؤسسات، بما في ذلك تخصيص الموارد، والجدولة، وإعداد التقارير.

### س: هل يمكنني دمج Aspose.Tasks مع مكتبات جافا أخرى؟
بالتأكيد، يمكن دمج Aspose.Tasks بسلاسة مع مكتبات جافا الأخرى لتعزيز قدرات إدارة مشروعك.

### س: هل يقدم Aspose.Tasks دعمًا للعملاء؟
نعم، يقدم Aspose.Tasks دعمًا مخصصًا للعملاء عبر منتداهم. يمكنك العثور على المساعدة [here](https://forum.aspose.com/c/tasks/15).

### س: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Tasks؟
نعم، يمكنك استكشاف Aspose.Tasks من خلال نسخة تجريبية مجانية متاحة [here](https://releases.aspose.com/).

---

**آخر تحديث:** 2026-01-02  
**تم الاختبار باستخدام:** Aspose.Tasks for Java 24.11 (latest release)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}