---
date: 2025-12-25
description: استكشف هذا البرنامج التعليمي لـ Aspose Tasks Java لتتعلم كيفية تحديد
  إصدار المشروع لملفات MS Project. دليل خطوة بخطوة مع أمثلة على الشيفرة.
linktitle: Determine Project Version with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 'دورة Aspose Tasks Java: تحديد إصدار MS Project'
url: /ar/java/project-management/determine-version/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# دورة Aspose Tasks Java: تحديد إصدار MS Project

## المقدمة
في هذه **دورة aspose tasks java** ستكتشف كيفية العثور برمجيًا على إصدار ملف Microsoft Project باستخدام مكتبة Aspose.Tasks للغة Java. معرفة إصدار الملف تساعدك على معالجة مشكلات التوافق، فرض سياسات الترحيل، أو ببساطة تسجيل أي إصدار من Project أنشأ الملف. سنستعرض كل خطوة — من إعداد البيئة إلى طباعة الإصدار وتاريخ الحفظ الأخير — حتى تتمكن من دمج هذا الفحص في أي تطبيق Java بثقة.

## إجابات سريعة
- **ما الذي تغطيه هذه الدورة؟** تحديد إصدار ملف MS Project باستخدام Aspose.Tasks للغة Java.  
- **هل أحتاج إلى تثبيت Microsoft Project؟** لا، Aspose.Tasks يعمل بشكل مستقل.  
- **ما صيغ الملفات المدعومة؟** ملفات Project القائمة على XML (MPP، XML، إلخ).  
- **كم يستغرق تنفيذ الفحص؟** حوالي 5‑10 دقائق لفحص أساسي.  
- **هل يلزم الحصول على ترخيص؟** نسخة تجريبية مجانية تكفي للتقييم؛ الترخيص مطلوب للإنتاج.

## ما هي دورة Aspose Tasks Java؟
توفر **دورة aspose tasks java** إرشادات عملية لاستخدام واجهة Aspose.Tasks API في مشاريع Java. تُظهر لك كيفية قراءة وتعديل وتحليل بيانات Microsoft Project دون الحاجة إلى برنامج Microsoft Project نفسه.

## لماذا نستخدم Aspose.Tasks لتحديد إصدار المشروع؟
- **بدون اعتماد على Microsoft Project** – مثالي لأتمتة الخوادم.  
- **بيانات إصدار دقيقة** – استرجاع الحقول SAVE_VERSION و LAST_SAVED بدقة.  
- **متعدد المنصات** – يعمل على أي نظام تشغيل يدعم Java.  
- **أداء عالي** – تحليل خفيف الوزن مناسب للمعالجة الدفعية.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من وجود ما يلي:

1. **مجموعة تطوير جافا (JDK)** – أي نسخة حديثة (8 أو أعلى).  
2. **ملف JAR الخاص بـ Aspose.Tasks للغة Java** – حمّله من [الموقع](https://releasespose.com/tasks/java/) وأضفه إلى مسار الفئة (classpath) في مشروعك.  
3. **ملف MS Project** – ملف Project قائم على XML (مثال: `input.xml`) تريد فحصه.  

> **نصيحة احترافية:** احتفظ بملف Project في مجلد `data` مخصص لتبسيط التعامل مع المسارات.

## استيراد الحزم
أولاً، استورد الفئات الأساسية من Aspose.Tasks:

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## الخطوة 1: إعداد دليل المشروع
حدد المجلد الذي يحتوي على ملف Project الخاص بك.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

استبدل `"Your Data Directory"` بالمسار المطلق أو النسبي حيث يقع `input.xml`.

## الخطوة 2: تحميل المشروع
أنشئ كائن `Project` بتحميل ملف XML.

```java
Project project = new Project(dataDir + "input.xml");
```

إذا كان لملفك اسم مختلف، عدّل `"input.xml"` وفقًا لذلك.

## الخطوة 3: كيفية تحديد إصدار المشروع
استرجع معلومات الإصدار والطابع الزمني لآخر حفظ.

```java
//Display project version property
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```

خاصية `Prj.SAVE_VERSION` تشير إلى إصدار Microsoft Project الذي تم حفظ الملف به (مثال: 12 لإصدار Project 2010). خاصية `Prj.LAST_SAVED` تُعيد تاريخ/وقت آخر عملية حفظ.

## الخطوة 4: عرض النتيجة
أظهر إكمال الفحص بنجاح.

```java
//Display result of conversion.
System.out.println("Process completed Successfully");
```

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|---------|--------|------|
| `NullPointerException` على `project.get(...)` | الملف غير موجود أو المسار غير صحيح | تحقق من `dataDir` واسم الملف؛ استخدم مسارًا مطلقًا للاختبار. |
| رقم إصدار غير متوقع (مثال: 0) | تحميل ملف XML غير مشروع كـ Project | تأكد من أن الملف ملف Microsoft Project صالح (MPP/XML). |
| استثناء الترخيص | استخدام النسخة التجريبية دون ترخيص صالح في بيئة الإنتاج | طبق ترخيص Aspose.Tasks الخاص بك (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## الأسئلة المتكررة

### س: هل يمكنني استخدام Aspose.Tasks مع لغات برمجة أخرى؟
ج: نعم، يدعم Aspose.Tasks عدة لغات بما فيها .NET، Java، و C++.

### س: هل Aspose.Tasks مناسب للمشاريع الضخمة؟
ج: بالتأكيد، صُمم Aspose.Tasks للتعامل مع مشاريع بأي حجم بسهولة.

### س: هل يمكنني تخصيص بيانات المشروع باستخدام Aspose.Tasks؟
ج: نعم، يمكنك تعديل بيانات المشروع، تعديل المهام، الموارد، وأكثر باستخدام Aspose.Tasks.

### س: هل يتطلب Aspose.Tasks تثبيت Microsoft Project؟
ج: لا، يعمل Aspose.Tasks بشكل مستقل ولا يحتاج إلى تثبيت Microsoft Project.

### س: هل يتوفر دعم فني لـ Aspose.Tasks؟
ج: نعم، يمكنك الحصول على الدعم الفني من منتدى Aspose.Tasks عبر [هنا](https://forum.aspose.com/c/tasks/15).

### أسئلة وإجابات إضافية

**س: كيف أسترجع خصائص أخرى للمشروع (مثل المؤلف، الشركة)؟**  
ج: استخدم `project.get(Prj.AUTHOR)` أو `project.get(Prj.COMPANY)` بنفس طريقة مثال الإصدار.

**س: هل يمكنني فحص إصدار ملف MPP (صيغة ثنائية)؟**  
ج: نعم، يمكن لـ Aspose.Tasks تحميل ملفات `.mpp` مباشرة؛ خاصية `Prj.SAVE_VERSION` تعمل بنفس الطريقة.

**س: هل هناك طريقة لترقية ملف مشروع قديم برمجيًا إلى إصدار أحدث؟**  
ج: حمّل الملف القديم، ثم احفظه باستخدام `project.save("newfile.mpp", SaveFileFormat.MPP);` – يقوم Aspose.Tasks بكتابته بأحدث صيغة بشكل افتراضي.

## الخاتمة
لقد أكملت الآن **دورة aspose tasks java** المختصرة التي توضح **كيفية تحديد إصدار المشروع** لملفات MS Project باستخدام Aspose.Tasks للغة Java. دمج هذا المقتطف في سير عمل أتمتة أكبر، أدوات تقارير، أو أدوات ترحيل لضمان معرفتك الدائمة بالإصدار الدقيق للمشروع الذي تتعامل معه.

---

**آخر تحديث:** 2025-12-25  
**تم الاختبار مع:** Aspose.Tasks للغة Java 24.11  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}