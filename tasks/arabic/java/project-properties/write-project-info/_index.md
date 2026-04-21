---
date: 2025-12-31
description: تعلم كيفية تعيين تاريخ بدء المشروع، كتابة معلومات المشروع، وحفظ المشروع
  كملف XML باستخدام Aspose.Tasks للغة Java.
linktitle: Write Project Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: تعيين تاريخ بدء المشروع في MS Project باستخدام Aspose.Tasks للـ Java
url: /ar/java/project-properties/write-project-info/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تعيين تاريخ بدء المشروع في MS Project باستخدام Aspose.Tasks للغة Java

## المقدمة
في هذا البرنامج التعليمي، ستكتشف كيفية **تعيين تاريخ بدء المشروع** وكتابة معلومات إضافية في MS Project باستخدام Aspose.Tasks للغة Java. سواءً كنت تقوم بأتمتة جداول المشاريع، أو إنشاء تقارير، أو دمج بيانات Project في نظام أكبر، فإن التحكم في تاريخ البدء برمجياً يمنحك تحكمًا دقيقًا في الجداول الزمنية. سنستعرض كل خطوة—من إعداد البيئة إلى حفظ المشروع المحدث كملف XML—حتى تتمكن من تطبيق هذه التقنيات فورًا.

## إجابات سريعة
- **ما هو الصنف الأساسي للتعامل مع مشروع؟** `Project` من مكتبة Aspose.Tasks.  
- **كيف يمكنني تعيين تاريخ بدء المشروع؟** استخدم `project.set(Prj.START_DATE, <date>)`.  
- **هل يمكنني أيضًا تعيين تاريخ الحالة؟** نعم، باستخدام `project.set(Prj.STATUS_DATE, <date>)`.  
- **أي صيغة يجب أن أستخدمها لتصدير المشروع؟** احفظه كملف XML باستخدام `SaveFileFormat.Xml`.  
- **هل أحتاج إلى ترخيص للاستخدام في الإنتاج؟** يتطلب تشغيل كامل الوظائف ترخيص صالح لـ Aspose.Tasks.

## ما هو **set project start date**؟
تعيين تاريخ بدء المشروع يحدد اليوم التقويمي الذي تبدأ منه جميع المهام المجدولة. إنه نقطة الارتكاز لحسابات مثل مدد المهام، والاعتمادات، والمسارات الحرجة. من خلال تعيين هذا التاريخ برمجياً، تضمن الاتساق عبر ملفات المشروع المتعددة وتقلل من أخطاء الإدخال اليدوي.

## لماذا نستخدم Aspose.Tasks للغة Java لكتابة معلومات المشروع؟
- **تغطية كاملة للـ API:** قراءة، تعديل، وكتابة كل خاصية في Project دون الحاجة إلى تثبيت Microsoft Project.  
- **متعدد المنصات:** يعمل على Windows وLinux وmacOS.  
- **جاهز للأتمتة:** مثالي للمعالجة الدفعية، خطوط CI، أو الخدمات الخلفية التي تُنشئ جداول المشاريع تلقائيًا.  

## المتطلبات المسبقة
قبل البدء، تأكد من وجود ما يلي:

1. **مجموعة تطوير جافا (JDK)** – أي نسخة حديثة (يفضل 8 أو أعلى).  
2. **مكتبة Aspose.Tasks للغة Java** – حمّلها من [هنا](https://releases.aspose.com/tasks/java/).  
3. **بيئة تطوير متكاملة (IDE)** – IntelliJ IDEA، Eclipse، أو أي محرر جافا تفضله.  

## استيراد الحزم
أولاً، استورد الحزم الضرورية في مشروع جافا الخاص بك:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## الخطوة 1: إعداد دليل البيانات
حدد الدليل الذي سيُخزن فيه بيانات المشروع.
```java
String dataDir = "Your Data Directory";
```

## الخطوة 2: إنشاء كائن المشروع
تهيئة كائن مشروع جديد.
```java
Project project = new Project();
```

## الخطوة 3: تعيين خصائص معلومات المشروع
هنا نقوم بتعيين **تاريخ بدء المشروع**، والجدولة من البداية، وتاريخ الحالة—مُغطين الكلمات المفتاحية الأساسية *write project information* و *how to set status*.
```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

## الخطوة 4: حفظ المشروع كملف XML
أخيرًا، احفظ ملف المشروع المحدث. هذا يوضح الكلمة المفتاحية الثانوية **save project as xml**.
```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|---------|-------|------|
| **Incorrect start date** | Calendar month is zero‑based in Java. | Use `Calendar.JULY` (or add 1 to month index) as shown. |
| **File not saved** | `dataDir` does not exist or lacks write permission. | Create the directory beforehand or choose a writable path. |
| **License warning** | Running without a license adds a watermark. | Apply a valid Aspose.Tasks license before creating the `Project` object. |

## الأسئلة المتكررة
### س: هل يمكنني استخدام Aspose.Tasks للغة Java لقراءة ملفات MS Project؟
ج: نعم، توفر Aspose.Tasks للغة Java وظائف قوية لقراءة وكتابة ملفات MS Project.  
### س: هل Aspose.Tasks للغة Java متوافق مع إصدارات مختلفة من MS Project؟
ج: بالتأكيد، تدعم Aspose.Tasks للغة Java إصدارات متعددة من MS Project، مما يضمن التوافق عبر صيغ الملفات المختلفة.  
### س: هل هناك أي قيود على نسخة التجربة من Aspose.Tasks للغة Java؟
ج: نسخة التجربة تسمح لك باستكشاف قدرات المكتبة، لكنها تفرض بعض القيود مثل العلامات المائية على الملفات الناتجة.  
### س: كيف يمكنني الحصول على دعم لـ Aspose.Tasks للغة Java؟
ج: يمكنك طلب المساعدة من منتدى مجتمع Aspose.Tasks [هنا](https://forum.aspose.com/c/tasks/15).  
### س: هل يمكنني شراء ترخيص مؤقت لـ Aspose.Tasks للغة Java؟
ج: نعم، تتوفر تراخيص مؤقتة للاستخدام قصير الأمد. يمكنك الحصول عليها من [هنا](https://purchase.aspose.com/temporary-license/).

## الخاتمة
لقد تعلمت الآن كيفية **تعيين تاريخ بدء المشروع**، كتابة معلومات المشروع الأساسية، و**حفظ المشروع كملف XML** باستخدام Aspose.Tasks للغة Java. هذه الأساسيات تمكنك من أتمتة سير عمل إدارة المشاريع، إنشاء جداول زمنية متسقة، ودمج بيانات MS Project في تطبيقات جافا الخاصة بك.

---

**آخر تحديث:** 2025-12-31  
**تم الاختبار مع:** Aspose.Tasks للغة Java 24.12  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}