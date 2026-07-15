---
date: 2026-02-10
description: تعلم كيفية استخراج وتحديث خصائص مشروع جافا مثل رمز العملة باستخدام Aspose.Tasks
  للغة جافا. غيّر عملة المشروع واسترجع رمز العملة بسهولة.
linktitle: Extract currency symbol mpp using Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: خصائص مشروع جافا – استخراج رمز العملة من ملف MPP باستخدام Aspose.Tasks للغة
  جافا
url: /ar/java/currency/currency-symbols/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# استخراج رمز العملة من ملف mpp باستخدام Aspose.Tasks للـ Java

## المقدمة
في هذا الدرس ستتعلم كيفية العمل مع **java project properties**—وبشكل خاص كيفية استخراج رمز العملة من ملف Microsoft Project (MPP) وكيفية **change currency symbol java** أو **retrieve currency symbol java** باستخدام مكتبة Aspose.Tasks. سواءً كنت تبني أداة تقارير، أو تدمج بيانات Project في نظام مالي، أو تحتاج ببساطة إلى عرض رمز العملة الصحيح في واجهة المستخدم الخاصة بك، فإن إتقان هذه المهمة الصغيرة ولكن الأساسية سيجعل تطبيقات Java الخاصة بك أكثر قوة وسهولة في الاستخدام.

## إجابات سريعة
- **ماذا يعني “extract currency symbol mpp”؟** يعني قراءة رمز العملة المخزن في ملف MPP (Microsoft Project).  
- **أي مكتبة تتعامل مع ذلك؟** Aspose.Tasks للـ Java توفر واجهة برمجة تطبيقات بسيطة لهذا الغرض.  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تكفي للتطوير؛ الترخيص التجاري مطلوب للإنتاج.  
- **كم من الوقت يستغرق؟** باستخدام الشيفرة أدناه يمكنك الحصول على الرمز في أقل من دقيقة.  
- **هل يمكنني أيضًا تغيير الرمز؟** نعم – يمكنك تعيين قيمة جديدة باستخدام الخاصية نفسها `Prj.CURRENCY_SYMBOL`.

## ما هو “extract currency symbol mpp”؟
يخزن Microsoft Project رمز العملة (مثل $, €, £) في رأس ملف المشروع. عملية **extract currency symbol mpp** تقوم بقراءة تلك القيمة لتتمكن من عرضها أو معالجتها برمجيًا.

## لماذا تحديث رمز العملة في خصائص مشروع Java؟
غالبًا ما تمتد المشاريع عبر مناطق جغرافية متعددة. القدرة على **change project currency** أو **update currency symbol** أثناء التشغيل تتيح لك تعديل التقارير والفواتير أو لوحات التحكم لتتناسب مع السوق المحلي دون الحاجة إلى إعادة إنشاء ملف المشروع بالكامل. هذه المرونة جزء أساسي من إدارة **java project properties** بفعالية.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من وجود ما يلي:

1. **Java Development Kit (JDK)** – الإصدار 8 أو أعلى.  
2. **Aspose.Tasks للـ Java** – حمّل أحدث ملف JAR من [صفحة تحميل Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
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

## الخطوة 3: استرجاع (وتغيير اختياري) رمز العملة
الآن نقوم بـ **retrieve currency symbol java** بقراءة الخاصية `Prj.CURRENCY_SYMBOL`. يمكنك أيضًا **change currency symbol java** (أو **change project currency**) عن طريق تعيين سلسلة جديدة لنفس الخاصية.

```java
// Retrieve the current currency symbol
System.out.println(project.get(Prj.CURRENCY_SYMBOL));

// Example of changing it (uncomment to use)
// project.set(Prj.CURRENCY_SYMBOL, "€");
// System.out.println("New symbol: " + project.get(Prj.CURRENCY_SYMBOL));
```

ستطبع الدالة `System.out.println` الرمز (مثلاً `$`) إلى وحدة التحكم، مؤكدًا أن عملية الاستخراج نجحت.

## المشكلات الشائعة وكيفية حلها
| Symptom | Likely Cause | Solution |
|---------|--------------|----------|
| `NullPointerException` on `project.get(...)` | مسار الملف غير صحيح أو الملف غير موجود | تحقق من `dataDir` واسم الملف؛ استخدم `new File(dataDir).exists()` للتصحيح |
| Unexpected symbol (e.g., `?`) | تم إنشاء المشروع بإعدادات إقليمية غير قياسية | تأكد من أن ملف MPP المصدر يحدد رمز عملة؛ يمكنك تعيين واحد برمجيًا كما هو موضح أعلاه |
| License error | استخدام النسخة التجريبية بدون ملف ترخيص صالح | حمّل الترخيص باستخدام `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` قبل إنشاء كائن `Project` |

## الأسئلة المتكررة

**س: هل يمكنني تعديل سمات مشروع أخرى غير رموز العملة باستخدام Aspose.Tasks؟**  
ج: نعم، تتيح لك Aspose.Tasks تحرير المهام، والموارد، والتعيينات، والتقويمات، والعديد من خصائص المشروع الأخرى.

**س: هل Aspose.Tasks متوافق مع إصدارات مختلفة من ملفات MS Project؟**  
ج: بالتأكيد. يدعم صيغ MPP، MPT، وXML من Project 98 حتى أحدث الإصدارات.

**س: هل توفر Aspose.Tasks وثائق ودعم للمطورين؟**  
ج: تتوفر وثائق API شاملة، أمثلة شيفرة، ومنتدى دعم مخصص على موقع Aspose.Tasks.

**س: هل يمكنني تجربة Aspose.Tasks قبل شرائه؟**  
ج: نعم – يمكن تنزيل نسخة تجريبية كاملة الوظائف من [موقع Aspose](https://purchase.aspose.com/buy).

**س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Tasks؟**  
ج: تُقدم تراخيص مؤقتة على [صفحة الترخيص المؤقت لـ Aspose](https://purchase.aspose.com/temporary-license/) لأغراض التقييم.

---

**آخر تحديث:** 2026-02-10  
**تم الاختبار مع:** Aspose.Tasks للـ Java 24.12 (أحدث نسخة وقت الكتابة)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}