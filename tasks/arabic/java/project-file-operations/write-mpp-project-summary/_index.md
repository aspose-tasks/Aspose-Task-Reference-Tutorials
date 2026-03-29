---
date: 2026-03-29
description: تعلم كيفية تعيين الكلمات المفتاحية وتعيين تاريخ الإنشاء في مشروع MPP
  باستخدام Aspose.Tasks للغة Java. دليل خطوة بخطوة مع أمثلة على الشيفرة.
linktitle: Write MPP Project Summary in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: كيفية تعيين الكلمات المفتاحية في ملخص مشروع MPP باستخدام Aspose.Tasks
url: /ar/java/project-file-operations/write-mpp-project-summary/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تعيين الكلمات المفتاحية في ملخص مشروع MPP باستخدام Aspose.Tasks

## مقدمة
في هذا الدرس ستكتشف **كيفية تعيين الكلمات المفتاحية** ومعلومات ملخص أخرى لملف مشروع MPP باستخدام Aspose.Tasks for Java. سواء كنت بحاجة إلى تضمين تفاصيل المؤلف، أرقام المراجعة، أو تاريخ إنشاء مخصص، يوجهك هذا الدليل خلال الخطوات الدقيقة، مع كود جاهز للتنفيذ. في النهاية ستتمكن من تعيين الكلمات المفتاحية، تعيين تاريخ الإنشاء java، واسترجاع البيانات من الملف.

## إجابات سريعة
- **ما المكتبة المستخدمة؟** Aspose.Tasks for Java  
- **الغرض الأساسي؟** تعيين الكلمات المفتاحية، معلومات المؤلف، وتاريخ الإنشاء في ملف MPP  
- **كم عدد خطوات الكود؟** ثلاث كتل كود بسيطة (تهيئة، حفظ، قراءة)  
- **هل أحتاج إلى ترخيص؟** نسخة تجريبية مجانية تكفي للتطوير؛ يلزم ترخيص تجاري للإنتاج  
- **إصدار Java المدعوم؟** Java 8 وما فوق  

## ما هو “كيفية تعيين الكلمات المفتاحية” في ملف MPP؟
الكلمات المفتاحية هي حقول بيانات وصفية مخزنة داخل ملف Microsoft Project (MPP). تساعد في تصنيف المشاريع، تمكين البحث السريع، وتوفير معلومات سياقية للأدوات اللاحقة. تقوم Aspose.Tasks بالكشف عن الخاصية `Prj.KEYWORDS`، مما يجعل كتابة أو تحديث هذه القيمة برمجياً أمراً بسيطاً.

## لماذا تستخدم Aspose.Tasks for Java لتعيين الكلمات المفتاحية وتاريخ الإنشاء؟
- **توافق كامل مع .MPP** – يعمل مع جميع صيغ Project من 2007 إلى 2023.  
- **لا حاجة لتثبيت COM أو Office** – جافا صافية، مثالية لبيئات الخادم.  
- **API غني** – بالإضافة إلى الكلمات المفتاحية يمكنك تعيين المؤلف، المراجعة، التعليقات، والتواريخ في استدعاء واحد.  
- **محسن للأداء** – قراءة/كتابة سريعة حتى لملفات المشاريع الكبيرة.  

## المتطلبات المسبقة
1. **مجموعة تطوير جافا (JDK)** – تم تثبيت JDK 8 أو أحدث.  
2. **Aspose.Tasks for Java** – حمّل أحدث ملف JAR من [here](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA، Eclipse، NetBeans، أو أي محرر تفضله.

## استيراد الحزم
أولاً، استورد الفئات التي ستحتاجها. هذه الاستيرادات تمنحك الوصول إلى كائن `Project`، تعداد `Prj` لحقول الملخص، وتعداد `SaveFileFormat` للحفظ.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```

## الخطوة 1: إعداد المشروع وتعريف معلومات الملخص
أنشئ مثيلاً من `Project`، ثم استخدم طريقة `set` لكتابة البيانات الوصفية المطلوبة. لاحظ كيف نقوم **بتعيين الكلمات المفتاحية** و**بتعيين تاريخ الإنشاء java** باستخدام كائن `Calendar`.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Initialize a new Project object with the path to your project file
Project project = new Project(dataDir + "project.mpp");
// Set summary information about the project
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");          // <-- set keywords
project.set(Prj.COMMENTS, "Comments");

// Set creation date of the project (set creation date java)
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());

// Set last printed date of the project
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```

## الخطوة 2: حفظ معلومات ملخص المشروع
بعد ملء الحقول، احفظ التغييرات. هنا نقوم بحفظ المشروع كملف XML لتسهيل الفحص، لكن يمكنك أيضًا حفظه مرة أخرى كملف MPP.

```java
// Save the Project back in MPP format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Display a success message
System.out.println("Process completed Successfully");
```

## الخطوة 3: قراءة معلومات ملخص المشروع
للتحقق من كتابة البيانات الوصفية بشكل صحيح، أعد تحميل الملف واقرأ كل خاصية مرة أخرى. تُظهر هذه الخطوة أن **كيفية تعيين الكلمات المفتاحية** تعمل فعليًا من البداية إلى النهاية.

```java
// Reading Project Summary Information
project = new Project(dataDir + "MppAspose.xml");
// Print author of the project
System.out.println("Author: " + project.get(Prj.AUTHOR));
// Print last author of the project
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// Print revision number of the project
System.out.println("Revision: " + project.get(Prj.REVISION));
// Print keywords of the project
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print comments of the project
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// Print creation date of the project
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// Print last printed date of the project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```

## المشكلات الشائعة والحلول
| المشكلة | سبب حدوثها | الحل |
|-------|----------------|-----|
| **NullPointerException on `project.get(Prj.CREATION_DATE)`** | لم يتم تعيين التقويم قبل الحفظ. | تأكد من استدعاء `project.set(Prj.CREATION_DATE, cal.getTime())` قبل `save()`. |
| **Keywords not appearing in Microsoft Project UI** | تم حفظ الملف كـ XML وفتح مباشرة في Project. | احفظه مرة أخرى كـ MPP (`SaveFileFormat.MPP`) أو افتح XML عبر *Import* في Project. |
| **Date values shifted by timezone** | كائن Java `Date` يتضمن معلومات المنطقة الزمنية. | استخدم `Calendar.setTimeZone(TimeZone.getTimeZone("UTC"))` إذا كنت بحاجة إلى تواريخ UTC. |

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Tasks for Java مع مكتبات جافا أخرى؟**  
**ج:** نعم، يمكن دمج Aspose.Tasks for Java بسلاسة مع مكتبات جافا أخرى لتعزيز قدرات إدارة المشاريع الخاصة بك.

**س: هل تتوفر نسخة تجريبية من Aspose.Tasks for Java؟**  
**ج:** نعم، يمكنك تحميل نسخة تجريبية مجانية من [here](https://releases.aspose.com/).

**س: ما مدى تكرار تحديث Aspose.Tasks for Java؟**  
**ج:** يتم تحديث Aspose.Tasks for Java بانتظام لضمان التوافق مع أحدث إصدارات Java وملفات Microsoft Project.

**س: هل يمكنني تخصيص معلومات ملخص المشروع أكثر؟**  
**ج:** بالتأكيد، يوفر Aspose.Tasks for Java خيارات واسعة لتخصيص معلومات ملخص المشروع وفقًا لمتطلباتك الخاصة.

**س: أين يمكنني الحصول على دعم لـ Aspose.Tasks for Java؟**  
**ج:** يمكنك الحصول على الدعم من منتدى مجتمع Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

**آخر تحديث:** 2026-03-29  
**تم الاختبار مع:** Aspose.Tasks for Java 24.11 (latest at time of writing)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}