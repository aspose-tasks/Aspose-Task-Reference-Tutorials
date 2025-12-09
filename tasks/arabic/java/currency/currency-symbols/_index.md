---
date: 2025-12-05
description: تعلم كيفية استخراج رمز العملة من ملفات MPP وتغيير رمز العملة في Java
  باستخدام Aspose.Tasks for Java. استرجع رمز العملة في Java بسرعة لإدارة المشاريع.
linktitle: Extract currency symbol mpp using Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: استخراج رمز العملة من ملف MPP باستخدام Aspose.Tasks للـ Java
url: /ar/java/currency/currency-symbols/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# استخراج رمز العملة mpp باستخدام Aspose.Tasks للـ Java

## المقدمة
في هذا البرنامج التعليمي ستقوم **باستخراج رمز العملة mpp** من ملف Microsoft Project وتكتشف كيفية **تغيير رمز العملة java** أو **استرجاع رمز العملة java** باستخدام مكتبة Aspose.Tasks. سواءً كنت تبني أداة تقارير، أو تدمج بيانات Project في نظام مالي، أو تحتاج ببساطة إلى عرض رمز العملة الصحيح في واجهة المستخدم الخاصة بك، فإن إتقان هذه المهمة الصغيرة ولكن الأساسية سيجعل تطبيقات Java الخاصة بك أكثر قوة وسهولة في الاستخدام.

## الإجابات السريعة
- **ماذا يعني “استخراج رمز العملة mpp”؟** يعني قراءة رمز العملة المخزن في ملف MPP (Microsoft Project).  
- **أي مكتبة تتعامل مع ذلك؟** Aspose.Tasks للـ Java توفر واجهة برمجة تطبيقات بسيطة لهذا الغرض.  
- **هل أحتاج إلى ترخيص؟** نسخة التجربة المجانية تكفي للتطوير؛ يلزم ترخيص تجاري للإنتاج.  
- **كم من الوقت يستغرق؟** باستخدام الشيفرة أدناه، يمكنك الحصول على الرمز في أقل من دقيقة.  
- **هل يمكنني أيضًا تغيير الرمز؟** نعم – يمكنك تعيين قيمة جديدة باستخدام خاصية `Prj.CURRENCY_SYMBOL` نفسها.

## ما هو “استخراج رمز العملة mpp”؟
يقوم Microsoft Project بتخزين رمز العملة (مثل $, €, £) في رأس ملف المشروع. عملية **استخراج رمز العملة mpp** تقرأ تلك القيمة لتتمكن من عرضها أو معالجتها برمجيًا.

## لماذا نغير رمز العملة java؟
غالبًا ما تمتد المشاريع عبر مناطق متعددة. القدرة على **تغيير رمز العملة java** في وقت التشغيل تتيح لك تعديل التقارير، الفواتير، أو لوحات التحكم لتتناسب مع السوق المحلي دون الحاجة إلى إعادة إنشاء ملف المشروع بالكامل.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من وجود ما يلي:

1. **مجموعة تطوير Java (JDK)** – الإصدار 8 أو أعلى.  
2. **Aspose.Tasks للـ Java** – حمّل أحدث ملف JAR من [صفحة تنزيل Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
3. ملف **project.mpp** صالح موجود في مجلد يمكنك الإشارة إليه من الشيفرة.

## استيراد الحزم
أولاً، استورد الفئات التي سنحتاجها للعمل مع ملفات Project.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## الخطوة 1: تعريف دليل البيانات
أخبر التطبيق بمكان وجود ملف *.mpp* الخاص بك.

```java
String dataDir = "Your Data Directory";
```

> **نصيحة احترافية:** استخدم `System.getProperty("user.dir")` لإنشاء مسار مطلق يعمل على أي جهاز.

## الخطوة 2: تحميل ملف MS Project
أنشئ كائن `Project` يمثل ملف MPP في الذاكرة.

```java
Project project = new Project(dataDir + "project.mpp");
```

## الخطوة 3: استرجاع (واختياريًا تغيير) رمز العملة
الآن نقوم **باسترجاع رمز العملة java** بقراءة خاصية `Prj.CURRENCY_SYMBOL`. يمكنك أيضًا **تغيير رمز العملة java** عن طريق تعيين سلسلة جديدة لنفس الخاصية.

```java
// Retrieve the current currency symbol
System.out.println(project.get(Prj.CURRENCY_SYMBOL));

// Example of changing it (uncomment to use)
// project.set(Prj.CURRENCY_SYMBOL, "€");
// System.out.println("New symbol: " + project.get(Prj.CURRENCY_SYMBOL));
```

ستطبع جملة `System.out.println` الرمز (مثلاً `$`) على وحدة التحكم، مما يؤكد نجاح عملية الاستخراج.

## المشكلات الشائعة وكيفية حلها
| العرض | السبب المحتمل | الحل |
|---------|--------------|----------|
| `NullPointerException` عند `project.get(...)` | مسار ملف غير صحيح أو الملف غير موجود | تحقق من `dataDir` واسم الملف؛ استخدم `new File(dataDir).exists()` للتصحيح |
| رمز غير متوقع (مثلاً `?`) | تم إنشاء المشروع ب locale غير قياسي | تأكد من أن ملف MPP المصدر يحدد رمز عملة؛ يمكنك تعيين واحد برمجيًا كما هو موضح أعلاه |
| خطأ الترخيص | استخدام النسخة التجريبية دون ملف ترخيص صالح | حمّل الترخيص باستخدام `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` قبل إنشاء كائن `Project` |

## الأسئلة المتكررة

**س: هل يمكنني تعديل سمات مشروع أخرى غير رموز العملة باستخدام Aspose.Tasks؟**  
ج: نعم، تتيح لك Aspose.Tasks تحرير المهام، الموارد، التخصيصات، التقويمات، والعديد من خصائص المشروع الأخرى.

**س: هل Aspose.Tasks متوافقة مع إصدارات مختلفة من ملفات MS Project؟**  
ج: بالتأكيد. تدعم صيغ MPP، MPT، وXML من Project 98 حتى أحدث الإصدارات.

**س: هل توفر Aspose.Tasks وثائق ودعم للمطورين؟**  
ج: وثائق API شاملة، أمثلة شيفرة، ومنتدى دعم مخصص متوفر على موقع Aspose.Tasks.

**س: هل يمكن تجربة Aspose.Tasks قبل شرائها؟**  
ج: نعم – يمكن تنزيل نسخة تجريبية كاملة الوظائف من [موقع Aspose](https://purchase.aspose.com/buy).

**س: كيف يمكن الحصول على ترخيص مؤقت لـ Aspose.Tasks؟**  
ج: تُقدَّم تراخيص مؤقتة على [صفحة الترخيص المؤقت لـ Aspose](https://purchase.aspose.com/temporary-license/) لأغراض التقييم.

---

**آخر تحديث:** 2025-12-05  
**تم الاختبار مع:** Aspose.Tasks للـ Java 24.12 (أحدث نسخة وقت كتابة هذا الدليل)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}