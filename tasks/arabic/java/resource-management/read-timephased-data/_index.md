---
date: 2026-01-20
description: تعلم كيفية الحصول على المورد بواسطة المعرف واستخراج البيانات الزمنية
  من موارد MS Project باستخدام Aspose.Tasks للغة Java.
linktitle: Get resource by id and read timephased data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: الحصول على المورد بواسطة المعرف وقراءة البيانات الزمنية في Aspose.Tasks
url: /ar/java/resource-management/read-timephased-data/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# الحصول على المورد حسب المعرف وقراءة البيانات الزمنية في Aspose.Tasks

## المقدمة
في هذا الدرس، سنرشدك إلى **كيفية الحصول على المورد حسب المعرف** وقراءة البيانات الزمنية لموارد MS Project باستخدام Aspose.Tasks for Java. سواء كنت بحاجة إلى تحليل أعباء العمل للمورد أو توزيع التكاليف، فإن استخراج هذه المعلومات برمجياً يوفر ساعات لا تُحصى من العمل اليدوي.

## إجابات سريعة
- **ما هو الصنف الأساسي لتحميل مشروع؟** `Project` من `com.asposeحتاج إلىخيص تجريبي مجاني يعمل للاختبار؛ الترخيص الكامل مطلوب للإنتاج.
- **ما نسخة Java المدعومة؟** Aspose.Tasks for Java يدعم JDKاء طريقة يسترجع كائن `Resource` من `Project` باستخدام المعرف الفريد للمورد (UID). يتم تعيين هذا الـ UID من قبل Microsoft Project عند إنشاء المورد ويظل ثابتاً طوال دورة حياة المشروع.

## لماذا قراءة البيانات الزمنية؟
البيانات الزمنية تقسم عمل أو تكلفة المورد إلى فواصل زمنية منفصلة (يوميًا، أسبوعيًا، شهريًا). هذه الدقة تمكنك من:
- إنشاء تقارير مخصصة عن استغلال الموارد.
- تحديد الإفراط في تخصيص الموارد مبكرًا.
- تغذية البيانات في أدوات التنبؤ أو الميزانية.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من توفر المتطلبات التالية:

1. **Java Development Kit (JDK)** – قم بتثبيت JDK 8 أو أحدث. يمكنك تنزيله من [الموقع](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) واتبع تعليمات التثبيت.  
2. **Aspose.Tasks for Java Library** – قم بتنزيل مكتبة Aspose.Tasks for Java من [صفحة التحميل](https://releases.aspose.com/tasks/java/) واتبع تعليمات التثبيت الواردة في الوثائق.  

## استيراد الحزم
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```

## الخطوة 1: إعداد دليل البيانات
أولاً، حدد الدليل الذي يقع فيه ملف MS Project الخاص بك.

```java
String dataDir = "Your Data Directory";
```

## الخطوة 2: قراءة ملف قالب MS Project
حدد اسم ملف قالب MS Project الخاص بك.

```java
String fileName = "ResourceTimephasedData.mpp";
```

## الخطوة 3: تحميل المشروع (java read project resources)
اقرأ ملف الإدخال باستخدام Aspose.Tasks وحمّله ككائن `Project`.

```java
Project project = new Project(dataDir + fileName);
```

## الخطوة 4: **Get resource by id**
استرجع المورد المطلوب من المشروع باستخدام معرفه الفريد (ID). في هذا المثال نقوم بجلب المورد الذي UID = 1.

```java
Resource resource = project.getResources().getByUid(1);
```

## الخطوة 5: طباعة البيانات الزمنية لعمل المورد
اطبع البيانات الزمنية لعمل المورد.

```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```

## الخطوة 6: طباعة البيانات الزمنية لتكلفة المورد
اطبع البيانات الزمنية لتكلفة المورد.

```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|---|---|---|
| **NullPointerException عند استدعاء `resource.getTimephasedData`** | قد يكون تاريخ بدء أو انتهاء المشروع مفقودًا. | تأكد من أن ملف المشروع يحتوي على تواريخ بدء/إنهاء صالحة أو قدم تواريخ صريحة. |
| **UID غير صحيح** | قد تكون الموارد في الملف لها UIDs مختلفة عما هو متوقع. | استخدم `project.getResources().toList()` لسرد الـ UIDs المتاحة قبل الجلب. |
| **الترخيص مفقود** | تقوم Aspose.Tasks بإلقاء استثناء إذا لم يتم تحميل ترخيص صالح في نسخة الإنتاج. | حمّل ملف الترخيص الخاص بك عبر `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` |

## الأسئلة المتكررة
### هل يمكن لـ Aspose.Tasks التعامل مع أنواع أخرى من ملفات المشروع غير Microsoft Project؟
نعم، يدعم Aspose.Tasks صيغ ملفات متعددة، بما في ذلك MPP و XML و CSV.

### هل Aspose.Tasks متوافق مع بيئات تطوير Java المختلفة؟
نعم، Aspose.Tasks متوافق مع جميع بيئات تطوير Java الرئيسية والإطارات.

### هل يمكنني تعديل بيانات المشروع باستخدام Aspose.Tasks؟
بالطبع، يوفر Aspose.Tasks واجهات برمجة تطبيقات واسعة لإنشاء وتعديل وتحليل بيانات المشروع.

### هل Aspose.Tasks مناسب للمشاريع على مستوى المؤسسات؟
نعم، يُستخدم Aspose.Tasks على نطاق واسع في بيئات المؤسسات بفضل موثوقيته وقابليته للتوسع.

### أين يمكنني العثور على الدعم إذا واجهت مشاكل أثناء استخدام Aspose.Tasks؟
يمكنك زيارة [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15) للحصول على مساعدة من المجتمع وفريق الدعم.

## الأسئلة المتداولة

**Q: كيف يمكنني استخراج بيانات المشروع لعدة موارد في آن واحد؟**  
A: قم بالتكرار عبر `project.getResources()` واستدعِ `getTimephasedData` لكل مورد داخل الحلقة.

**Q: هل هناك طريقة لتغيير الفاصل الزمني (مثلاً من يومي إلى أسبوعي)؟**  
A: نعم، مرّر `TimephasedDataType` مثل `TimephasedDataType.ResourceWork` مع مجموعة `TimephasedData` التي يمكنك تجميعها يدويًا.

**Q: هل يمكنني تصدير البيانات الزمنية إلى CSV؟**  
A: بعد استرجاع البيانات، اكتبها إلى ملف CSV باستخدام I/O القياسي في Java (`FileWriter`/`BufferedWriter`).

**Q: هل يدعم Aspose.Tasks قراءة ملفات المشروع التي تم إنشاؤها بإصدارات MS Project الأحدث؟**  
A: يتم تحديث المكتبة بانتظام لدعم أحدث صيغ MPP؛ استخدم دائمًا أحدث نسخة من Aspose.Tasks.

**Q: ما هي اعتبارات الأداء للمشاريع الكبيرة؟**  
A: حمّل المشروع مرة واحدة، أعد استخدام كائن `Project`، وتجنب الاستدعاءات المتكررة لـ `getTimephasedData` لنفس الفاصل الزمني.

---

**آخر تحديث:** 2026-01-20  
**تم الاختبار مع:** Aspose.Tasks for Java 24.11  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}