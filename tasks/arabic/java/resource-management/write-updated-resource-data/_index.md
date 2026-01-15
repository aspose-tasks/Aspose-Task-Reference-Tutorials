---
date: 2026-01-15
description: تعلم كيفية إضافة مورد إلى المشروع، وتحديث بيانات المورد، وحفظ المشروع
  بصيغة MPP باستخدام Aspose.Tasks للغة Java.
linktitle: Add Resource to Project Using Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: إضافة مورد إلى المشروع باستخدام Aspose.Tasks لجافا
url: /ar/java/resource-management/write-updated-resource-data/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة مورد إلى المشروع باستخدام Aspose.Tasks للـ Java

## مقدمة
في هذا الدرس العملي ستكتشف **كيفية إضافة مورد إلى المشروع** برمجياً باستخدام Aspose.Tasks Java API. سنستعرض تحميل ملف MS Project XML موجود، إدراج مورد جديد، تحديث خصائصه، وأخيراً **حفظ المشروع كملف MPP**. في النهاية ستحصل على نمط واضح وقابل للتكرار يمكنك دمجه في أي أداة تقارير أو أتمتة مبنية على Java.

## إجابات سريعة
- **ماذا يعني “إضافة مورد إلى المشروع”؟** ينشئ إدخال مورد جديد (أشخاص، معدات، مواد) داخل ملف Microsoft Project.  
- **أي مكتبة تتعامل مع هذا؟** Aspose.Tasks للـ Java – لا حاجة لتثبيت Microsoft Project.  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تكفي للتطوير؛ يلزم ترخيص تجاري للإنتاج.  
- **هل يمكنني تحويل XML إلى MPP؟** نعم – قم بتحميل ملف XML و**احفظ المشروع كملف MPP** باستخدام `project.save(...)`.  
- **ما نسخة Java المطلوبة؟** Java 6 أو أحدث (يوصى بـ Java 8 أو أعلى).

## ما هو “إضافة مورد إلى المشروع”؟
إضافة مورد إلى مشروع يعني إدراج صف جديد في جدول الموارد (Resources) بملف MS Project. هذا الصف يخزن تفاصيل مثل الاسم، معدلات التكلفة، المجموعة، والحقول المخصصة التي يمكن للمهام الإشارة إليها لاحقاً.

## لماذا نستخدم Aspose.Tasks للـ Java؟
- **لا يعتمد على Microsoft Project** – يعمل على أي نظام تشغيل أو خادم CI.  
- **دقة كاملة** – يحتفظ بجميع ميزات Project الأصلية عند التحويل بين الصيغ.  
- **API غني** – يتيح لك قراءة، كتابة، وتعديل المهام، الموارد، التقويمات، وأكثر.

## المتطلبات المسبقة
قبل البدء، تأكد من وجود:

1. مجموعة تطوير Java (JDK) الإصدار 8 أو أحدث مثبتة.  
2. مكتبة Aspose.Tasks للـ Java – قم بتنزيلها من [هنا](https://releases.aspose.com/tasks/java/).  
3. إلمام أساسي بصياغة Java وإعداد مشروع Maven/Gradle.

## استيراد الحزم
أضف الفئات المطلوبة من Aspose.Tasks إلى ملف المصدر Java الخاص بك:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## الخطوة 1: إعداد دليل البيانات الخاص بك
حدد موقع ملفات XML المصدر وملفات MPP الناتجة:

```java
String dataDir = "Your Data Directory";
```

## الخطوة 2: تحديد ملفات الإدخال والإخراج
حدد ملف XML الذي تريد تحويله (**تحويل XML إلى MPP**) وملف MPP الهدف الذي سيحتوي على المورد الجديد:

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Test file with one rsc to update
String resultFile = dataDir + "OutputMPP.mpp"; // File to write test project
```

## الخطوة 3: تحميل المشروع
أنشئ كائن `Project` من مصدر XML:

```java
Project project = new Project(file);
```

## الخطوة 4: إضافة مورد وتعيين الخصائص
هنا حيث **نضيف موردًا إلى المشروع** ونقوم بتكوين معدلاته ومجموعته:

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

*نصيحة احترافية:* يمكنك تكرار استدعاء `add` داخل حلقة لت **تحديث موارد متعددة** في تشغيل واحد.

## الخطوة 5: حفظ المشروع
أخيرًا، **احفظ المشروع كملف MPP** لتثبيت التغييرات:

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## الخلاصة
لقد تعلمت الآن **كيفية إضافة مورد إلى المشروع**، تحديث خصائصه، و**حفظ المشروع كملف MPP** باستخدام Aspose.Tasks للـ Java. هذا النهج مثالي لأنابيب التقارير الآلية، استيراد الموارد بالجملة، أو أي سيناريو تحتاج فيه إلى تعديل ملفات MS Project دون الحاجة إلى التطبيق المكتبي.

## الأسئلة المتكررة

**س1: هل يمكنني تحديث موارد متعددة في نفس المشروع باستخدام Aspose.Tasks للـ Java؟**  
ج: نعم، يمكنك التكرار على `project.getResources()` أو استدعاء `add` بشكل متكرر، مع ضبط حقول كل مورد حسب الحاجة.

**س2: هل يدعم Aspose.Tasks صيغ ملفات أخرى غير MS Project؟**  
ج: بالطبع – XML، MPP، MPX، Primavera، والمزيد كلها مدعومة.

**س3: هل Aspose.Tasks متوافق مع إصدارات Java المختلفة؟**  
ج: المكتبة تعمل مع Java 6 وما فوق؛ يوصى بشدة باستخدام Java 8 أو أحدث لأفضل أداء.

**س4: هل يمكنني تنفيذ عمليات أخرى على ملفات MS Project باستخدام Aspose.Tasks؟**  
ج: نعم، يمكنك قراءة/كتابة المهام، التقويمات، التعيينات، الحقول المخصصة، وحتى إنشاء تقارير.

**س5: أين يمكنني العثور على مساعدة أو دعم إضافي لـ Aspose.Tasks؟**  
ج: زر [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15) للحصول على مساعدة المجتمع والدعم الرسمي.

---

**آخر تحديث:** 2026-01-15  
**تم الاختبار مع:** Aspose.Tasks للـ Java 24.11  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}