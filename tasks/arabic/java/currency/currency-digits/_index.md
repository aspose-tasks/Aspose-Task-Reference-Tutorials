---
date: 2025-12-05
description: تعلم كيفية التعامل مع أرقام عملة MS Project بفعالية باستخدام Aspose.Tasks
  للغة Java. دليل خطوة بخطوة يغطي معالجة ملفات مشروع Java وكيفية تحميل ملفات MPP.
linktitle: Handle ms project currency Digits with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: معالجة أرقام عملة مشروع MS باستخدام Aspose.Tasks
url: /ar/java/currency/currency-digits/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# معالجة أرقام عملة MS Project باستخدام Aspose.Tasks

## المقدمة
في هذا الدرس الشامل ستكتشف **كيفية التعامل مع قيم عملة ms project** باستخدام مكتبة Aspose.Tasks للغة Java. سواءً كنت تبني أداة تقارير، أو أداة ترحيل، أو ببساطة تحتاج إلى قراءة إعدادات العملة من **ملف مشروع java**، فإن هذا الدليل سيرشدك خلال كل خطوة — من تحميل ملف *.mpp* إلى استخراج أرقام العملة. في النهاية، ستكون مرتاحًا في معالجة بيانات عملة ms project في تطبيقاتك الخاصة.

## إجابات سريعة
- **ما المكتبة التي تقرأ ملفات MS Project؟** Aspose.Tasks for Java.  
- **كم عدد أسطر الكود للحصول على أرقام العملة؟** فقط ثلاث أسطر مختصرة بعد تحميل المشروع.  
- **هل أحتاج إلى ترخيص للتطوير؟** النسخة التجريبية المجانية تعمل للاختبار؛ الترخيص التجاري مطلوب للإنتاج.  
- **ما نسخة Java المدعومة؟** Java 8 أو أعلى (أي JDK يدعم Aspose.Tasks).  
- **هل يمكنني استرجاع خصائص مشروع أخرى؟** نعم – Aspose.Tasks يتيح مجموعة كاملة من حقول المشروع (مثل تاريخ البدء، معدلات التكلفة، إلخ).

## ما هي عملة ms project؟
`ms project currency` تشير إلى الدقة الرقمية (عدد المنازل العشرية) التي يستخدمها Microsoft Project عند عرض القيم المالية. يتم تخزينها في ملف المشروع كخاصية **CURRENCY_DIGITS** وتحدد ما إذا كانت القيم تظهر كأعداد صحيحة، أو منزل عشرية واحدة، أو منزلتين عشريتين، إلخ.

## لماذا نستخدم Aspose.Tasks لمعالجة عملة ms project؟
- **لا حاجة لتثبيت Microsoft Project** – العمل مباشرةً مع ملفات *.mpp* على أي منصة تدعم Java.  
- **أمان نوع قوي** – تُعيد API قيمًا ذات نوع قوي، مما يقلل من أخطاء التحليل.  
- **محسّن للأداء** – تحميل المشاريع الكبيرة بسرعة واستخراج الحقول المطلوبة فقط.  
- **متعدد المنصات** – تشغيل على Windows أو Linux أو macOS دون تعديل.

## المتطلبات المسبقة
قبل البدء، تأكد من أن لديك ما يلي:

1. **بيئة تطوير Java** – JDK 8 أو أحدث مثبت ومُكوَّن.  
2. **Aspose.Tasks للـ Java** – قم بتحميل أحدث ملف JAR من الموقع الرسمي: [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).  
3. **معرفة أساسية بـ Java** – يجب أن تكون مرتاحًا لإنشاء مشروع Java، وإضافة مكتبات خارجية، وتشغيل دالة `main`.

## استيراد الحزم
First, import the classes we’ll need.  
```java
import java.io.IOException;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## الخطوة 1: تعريف دليل البيانات
حدد المجلد الذي يحتوي على **ملف مشروع java** (`*.mpp`).  
```java
String dataDir = "Your Data Directory";
```
استبدل `"Your Data Directory"` بالمسار المطلق أو النسبي حيث يوجد `project.mpp`.

## الخطوة 2: تحميل ملف MPP  
الآن سنرى **كيفية تحميل ملفات mpp** باستخدام Aspose.Tasks.  
```java
Project project = new Project(dataDir + "project.mpp");
```
تأكد من أن اسم الملف يطابق تمامًا؛ وإلا سيتم رمي استثناء `IOException`.

## الخطوة 3: استرجاع أرقام العملة  
مع تحميل المشروع، استخراج أرقام **عملة ms project** هو سطر واحد:  
```java
System.out.println(project.get(Prj.CURRENCY_DIGITS));
```
تُعيد الدالة قيمة `Integer` تمثل عدد المنازل العشرية (مثال، `2` للسنات). يتم طباعة القيمة إلى وحدة التحكم، ولكن يمكنك أيضًا تخزينها في متغير لمزيد من المعالجة.

## مشكلات شائعة ونصائح
- **الملف غير موجود** – تحقق مرة أخرى من مسار `dataDir` وتأكد من صحة اسم الملف، بما في ذلك امتداد `.mpp`.  
- **إصدار ملف غير مدعوم** – Aspose.Tasks يدعم صيغ Project 2000‑2024؛ قد تحتاج الملفات الأقدم أو التالفة إلى تحويل.  
- **لم يتم تعيين الترخيص** – أثناء التطوير النسخة التجريبية تعمل، لكن للإنتاج يجب تطبيق ترخيص صالح لتجنب علامات مائية للتقييم.

## الأسئلة المتكررة

**س: هل يمكن لـ Aspose.Tasks التعامل مع خصائص مشروع أخرى غير أرقام العملة؟**  
**ج:** نعم، Aspose.Tasks يقدم مجموعة واسعة من الوظائف للتعامل مع جوانب مختلفة من ملفات المشروع، مثل المهام والموارد والحقول المخصصة.

**س: هل Aspose.Tasks مناسب لتطبيقات على مستوى المؤسسات؟**  
**ج:** بالتأكيد، تم تصميم Aspose.Tasks لتلبية متطلبات المشاريع على مستوى المؤسسات، مع توفير أداء عالي وقابلية توسع.

**س: هل يدعم Aspose.Tasks التطوير متعدد المنصات؟**  
**ج:** نعم، يمكنك استخدام Aspose.Tasks للـ Java على أي منصة تدعم بيئة تشغيل Java (Windows، Linux، macOS).

**س: هل يمكنني تجربة Aspose.Tasks قبل الشراء؟**  
**ج:** نعم، يمكنك تحميل نسخة تجريبية مجانية من [هنا](https://releases.aspose.com/).

**س: أين يمكنني الحصول على دعم لـ Aspose.Tasks؟**  
**ج:** يمكنك العثور على الدعم في [منتدى Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

---

**آخر تحديث:** 2025-12-05  
**تم الاختبار مع:** Aspose.Tasks for Java 24.11 (latest at time of writing)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}