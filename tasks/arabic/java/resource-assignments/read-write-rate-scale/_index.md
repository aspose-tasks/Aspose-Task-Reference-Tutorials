---
date: 2026-01-10
description: تعلم كيفية قراءة مقياس السعر وإدارة تعيينات الموارد في Aspose.Tasks للغة
  Java. تعريف المورد المادي، كيفية ضبط المقياس، وتعيين الموارد للمهمة.
linktitle: Read and Write Rate Scale for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: كيفية قراءة مقياس المعدل وكتابة مقياس المعدل لتعيينات الموارد في Aspose.Tasks
url: /ar/java/resource-assignments/read-write-rate-scale/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية قراءة مقياس المعدل وكتابة مقياس المعدل لتعيينات الموارد في Aspose.Tasks

في هذا البرنامج التعليمي ستكتشف **كيفية قراءة معدل** إعدادات المقياس وتعديلها لتعيينات الموارد باستخدام Aspose.Tasks for Java. سواءً كنت تبني أداة جدولة، أو أداة تقارير، أو تحتاج ببساطة إلى أتمتة تحديثات المشروع، فإن إتقان تعديل مقياس المعدل يمنحك تحكمًا دقيقًا في الموارد المادية والعملية.

## إجابات سريعة
- **ما هو الصنف الأساسي لمعالجة المعدل؟** `ResourceAssignment` مع الخاصية `Asn.RATE_SCALE`.  
- **أي تعداد يحدد خيارات المقياس؟** `RateScaleType` (Day, Week, Month, إلخ).  
- **هل أحتاج إلى ترخيص لتشغيل العينة؟** ترخيص تجريبي مجاني يعمل للاختبار؛ يلزم ترخيص تجاري للإنتاج.  
- **هل يمكنني تغيير المقياس بعد الحفظ؟** نعم – أعد تحميل المشروع وعدل `Asn.RATE_SCALE` كما هو موضح.  
- **ما هي بيئات التطوير المتكاملة المدعومة؟** أي بيئة تطوير Java (IntelliJ IDEA، Eclipse، NetBeans) يمكنها تجميع الشيفرة.

## ما هو مقياس المعدل؟
مقياس المعدل يحدد وحدة الوقت (يوم، أسبوع، شهر، إلخ) التي يُطبق عليها معدل تكلفة المورد. تعديل المقياس يتيح لك نمذجة استهلاك المواد أو الجهد العمالي بدقة.

## لماذا قراءة وكتابة مقياس المعدل؟
قراءة المقياس الحالي تساعدك على تدقيق الجداول الزمنية القائمة، بينما كتابة مقياس جديد يتيح لك مواءمة الموارد مع سياسات الفوترة أو الاستهلاك في المشروع. هذا مفيد بشكل خاص عند **تحديد تكلفة المورد المادي** أو عندما تحتاج إلى **تعيين المقياس** لتقويمات العمل غير القياسية.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من توفر المتطلبات التالية:
1. **بيئة تطوير Java** – JDK 8 أو أعلى مثبت.  
2. **مكتبة Aspose.Tasks for Java** – قم بتحميل وتثبيت المكتبة من [here](https://releases.aspose.com/tasks/java/).

## استيراد الحزم
أولاً، استورد الفئات الضرورية من Aspose.Tasks.

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.RateScaleType;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import java.io.IOException;
```

## الخطوة 1: إعداد مشروع Java الخاص بك
أنشئ مشروع Maven أو Gradle وأضف ملف JAR الخاص بـ Aspose.Tasks إلى مسار الفئة (classpath). هذه الخطوة تضمن أن المترجم يستطيع العثور على الفئات المستوردة.

## الخطوة 2: تحميل ملف المشروع
حمّل ملف Microsoft Project الموجود الذي تريد العمل عليه.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```

## الخطوة 3: إضافة مهمة
أنشئ مهمة جديدة ستستقبل لاحقًا تعيينات الموارد.

```java
Task task = project.getRootTask().getChildren().add("t1");
```

## الخطوة 4: تعريف الموارد
هنا نقوم **بتعريف مورد مادي** ومورد عمل عادي. لاحظ استخدام `ResourceType.Material` للمورد من النوع المادي.

```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```

## الخطوة 5: تعيين الموارد إلى المهمة
الآن نقوم **بتعيين الموارد إلى المهمة** ونحدد **كيفية تعيين المقياس** باستخدام `RateScaleType.Week`. هذا يوضح كل من قراءة وكتابة مقياس المعدل.

```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```

## الخطوة 6: حفظ المشروع
احفظ التغييرات في ملف جديد حتى نتمكن لاحقًا من التحقق من مقياس المعدل المخزن.

```java
project.save("output.mpp", SaveFileFormat.Mpp);
```

## الخطوة 7: استرجاع تعيينات الموارد
أعد تحميل المشروع المحفوظ و**اقرأ مقياس المعدل** للتأكد من أنه تم كتابته بشكل صحيح.

```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## الأخطاء الشائعة والنصائح
- **عدم تطابق UID** – عند استرجاع التعيينات بواسطة UID، تأكد من أن قيم UID تتطابق مع تلك التي تم تعيينها أثناء الإنشاء.  
- **نوع المورد غير الصحيح** – استخدام `ResourceType.Material` لمورد عمل سيتسبب في سلوك غير متوقع لحسابات المعدل.  
- **صيغة الحفظ** – احفظ دائمًا باستخدام `SaveFileFormat.Mpp` (أو أي صيغة مدعومة أخرى) للحفاظ على الحقول المخصصة مثل مقياس المعدل.

## الخلاصة
إدارة وفحص مقياس المعدل لتعيينات الموارد في Aspose.Tasks for Java أمر بسيط بمجرد معرفتك بالفئات والخصائص ذات الصلة. باتباع هذا الدليل يمكنك **قراءة معلومات المعدل**، **تعريف كائنات المورد المادي**، **تعيين المقياس**، و**تعيين الموارد إلى المهمة** بثقة.

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Tasks for Java مع أي بيئة تطوير Java؟**  
ج: نعم، Aspose.Tasks for Java متوافق مع جميع بيئات تطوير Java الرئيسية، بما في ذلك IntelliJ IDEA، Eclipse، وNetBeans.

**س: هل يدعم Aspose.Tasks صيغ ملفات أخرى غير MPP؟**  
ج: نعم، يدعم Aspose.Tasks صيغ ملفات متعددة، بما في ذلك MPP، XML، وHTML.

**س: هل Aspose.Tasks مناسب لإدارة المشاريع على مستوى المؤسسات؟**  
ج: بالتأكيد، يقدم Aspose.Tasks ميزات شاملة لإدارة المشاريع بأي حجم، مما يجعله مناسبًا لإدارة المشاريع على مستوى المؤسسات.

**س: هل يمكنني تخصيص تعيينات الموارد أكثر من مجرد مقياس المعدل؟**  
ج: نعم، يوفر Aspose.Tasks إمكانيات واسعة لتخصيص تعيينات الموارد، بما في ذلك تعديل التكلفة والعمل والمدة.

**س: هل هناك منتدى مجتمع لدعم Aspose.Tasks؟**  
ج: نعم، يمكنك العثور على الدعم والتفاعل مع المستخدمين الآخرين في منتدى Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

---

**آخر تحديث:** 2026-01-10  
**تم الاختبار مع:** Aspose.Tasks for Java 24.12 (أحدث نسخة وقت الكتابة)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}