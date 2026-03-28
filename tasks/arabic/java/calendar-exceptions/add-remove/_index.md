---
date: 2026-01-28
description: تعلم كيفية إنشاء استثناء تقويم باستخدام Aspose.Tasks للغة Java، وإضافة
  وإزالة استثناءات التقويم بكفاءة، وتحسين جدولة المشروع.
linktitle: Add and Remove Calendar Exceptions in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: إنشاء استثناء تقويم Aspose للـ Java
url: /ar/java/calendar-exceptions/add-remove/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء استثناء تقويم Aspose للـ Java

## المقدمة
غالبًا ما يعتمد جدولة المشاريع الدقيقة على التعامل مع **استثناءات التقويم** — الأيام التي تكون فيها الموارد غير متاحة أو تتغير جداول العمل. باستخدام **Aspose.Tasks for Java**، يمكنك **إنشاء استثناء تقويم** كائنات، إضافتها إلى تقويم المشروع، أو إزالتها عندما لا تكون بحاجة إليها بعد الآن. في هذا البرنامج التعليمي سنستعرض العملية بالكامل، من تحميل ملف المشروع إلى التحقق من الاستثناءات التي أدرتها. يوضح لك هذا الدليل بالضبط كيفية **إنشاء استثناء تقويم aspose** في بيئة Java.

### إجابات سريعة
- **ما معنى “create calendar exception”?** يعني تعريف نطاق تاريخ يختلف عن التقويم العملي القياسي.  
- **أي مكتبة توفر هذه القدرة؟** Aspose.Tasks for Java.  
- **هل أحتاج إلى ترخيص لتجربتها؟** تتوفر نسخة تجريبية مجانية؛ يلزم الترخيص للاستخدام في الإنتاج.  
- **هل يمكنني إزالة استثناء موجود؟** نعم — فقط ابحث عنه في قائمة استثناءات التقويم واحذفها.  
- **هل هذا متوافق مع ملفات Microsoft Project؟** بالتأكيد؛ Aspose.Tasks يقرأ ويكتب جميع إصدارات .mpp الرئيسية.

#### المتطلبات المسبقة
- مجموعة تطوير جافا (JDK) مثبتة.  
- مكتبة Aspose.Tasks للـ Java مضافة إلى مسار الفئات (classpath) في مشروعك.  
- فهم أساسي للغة Java ومصطلحات إدارة المشاريع.

## كيفية إنشاء استثناء تقويم Aspose باستخدام Java
فيما يلي دليل خطوة بخطوة يشرح هدف كل مقتطف شفرة قبل تشغيله. اتبع هذه الأقسام بالترتيب لضمان معالجة استثناءات التقويم الخاصة بك بشكل صحيح.

## استيراد الحزم
أولاً، استورد الفئات الأساسية من Aspose.Tasks التي تمكّن من معالجة التقويم.

```java
import com.aspose.tasks.*;
```

## الخطوة 1: تحميل المشروع والوصول إلى تقويمه
نبدأ بتحميل ملف Microsoft Project موجود (`input.mpp`) والحصول على أول تقويم في المجموعة. يمكنك تعديل الفهرس إذا كنت بحاجة إلى تقويم مختلف.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "input.mpp");
Calendar cal = project.getCalendars().toList().get(0);
```

## الخطوة 2: إزالة استثناء موجود (إذا لزم الأمر)
أحيانًا يحتوي التقويم بالفعل على استثناءات تريد مسحها. يتحقق المقتطف أدناه من قائمة الاستثناءات ويزيل الإدخال الأول عندما يكون هناك أكثر من استثناء واحد.

```java
if (cal.getExceptions().size() > 1) {
    CalendarException exc = cal.getExceptions().get(0);
    cal.getExceptions().remove(exc);
}
```

> **نصيحة احترافية:** تحقق دائمًا من حجم قائمة الاستثناءات قبل إزالة العناصر لتجنب `IndexOutOfBoundsException`.

## الخطوة 3: إنشاء (إضافة) استثناء تقويم جديد
الآن نقوم **بإنشاء استثناء تقويم** كائنات. في هذا المثال نحدد استثناء يمتد من 1 إلى 3 يناير 2009. عدّل التواريخ لتتناسب مع جدول مشروعك الخاص.

```java
CalendarException calExc = new CalendarException();
java.util.Calendar calObject = java.util.Calendar.getInstance();
calObject.set(2009, java.util.Calendar.JANUARY, 1, 0, 0, 0);
calExc.setFromDate(calObject.getTime());
calObject.set(2009, java.util.Calendar.JANUARY, 3, 0, 0, 0);
calExc.setToDate(calObject.getTime());
cal.getExceptions().add(calExc);
```

> **لماذا هذا مهم:** إضافة الاستثناءات تتيح لك نمذجة العطلات، فترات الصيانة، أو أي فترات غير عمل مباشرة في جدول المشروع. هذا هو جوهر وظيفة **create calendar exception aspose**.

## الخطوة 4: عرض جميع الاستثناءات للتحقق
بعد إضافة (أو إزالة) الاستثناءات، من الممارسات الجيدة طباعتها. يساعدك ذلك على التأكد من أن التقويم يعكس التغييرات المقصودة.

```java
for (CalendarException calExc1 : cal.getExceptions()) {
    System.out.println("From " + calExc1.getFromDate().toString());
    System.out.println("To   " + calExc1.getToDate().toString());
}
```

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|-------|-----|
| لا يظهر أي إخراج | قائمة الاستثناءات فارغة | تأكد من أنك أضفت استثناءً قبل التكرار. |
| `NullPointerException` على `project` | مسار ملف غير صحيح | تحقق من أن `dataDir` يشير إلى ملف `.mpp` صالح. |
| التواريخ متأخرة بيوم واحد | اختلافات المنطقة الزمنية | استخدم `java.util.Calendar` مع تحديد صريح للمنطقة الزمنية أو واجهة `java.time` API. |

## الأسئلة المتكررة

**س: هل يمكنني إضافة استثناءات متعددة إلى تقويم باستخدام Aspose.Tasks للـ Java؟**  
ج: نعم. فقط أنشئ `CalendarException` جديد لكل نطاق تاريخ وأضفه إلى `cal.getExceptions()` داخل حلقة.

**س: هل Aspose.Tasks للـ Java متوافق مع جميع إصدارات ملفات Microsoft Project؟**  
ج: يدعم Aspose.Tasks مجموعة واسعة من إصدارات .mpp، من Project 98 حتى أحدث الإصدارات، مما يضمن تكاملًا سلسًا.

**س: كيف يمكنني التعامل مع الاستثناءات المتكررة (مثل الاجتماعات الأسبوعية) في تقاويم المشروع؟**  
ج: استخدم خصائص التكرار في `CalendarException` (`setRecurrencePattern`) لتحديد أنماط معقدة مثل التكرار اليومي أو الأسبوعي أو الشهري.

**س: هل تتوفر نسخة تجريبية من Aspose.Tasks للـ Java؟**  
ج: نعم، يمكنك تنزيل نسخة تجريبية مجانية من [الموقع](https://releases.aspose.com/) لاستكشاف جميع الميزات قبل الشراء.

**س: أين يمكنني طلب الدعم لأي مشكلات أو استفسارات تتعلق بـ Aspose.Tasks للـ Java؟**  
ج: زر منتدى Aspose.Tasks للـ Java على [الموقع](https://reference.aspose.com/tasks/java/) لطرح الأسئلة، أو اتصل بدعم Aspose مباشرة.

## الخاتمة
إدارة استثناءات التقويم أمر أساسي لجداول زمنية واقعية للمشاريع وتخطيط الموارد. باستخدام **Aspose.Tasks للـ Java**، يمكنك **إنشاء استثناء تقويم** كائنات، إضافتها إلى أي تقويم مشروع، وإزالتها عندما لم تعد ذات صلة—كل ذلك ببضع أسطر من الشيفرة. هذه القدرة على **إنشاء استثناء تقويم aspose** تمكّنك من بناء جداول تعكس القيود الواقعية.

---

**آخر تحديث:** 2026-01-28  
**تم الاختبار مع:** Aspose.Tasks للـ Java 24.11  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}