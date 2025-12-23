---
date: 2025-12-23
description: تعلم كيفية استخدام Aspose.Tasks Java لتحديث جدول المشروع، وتعيين يوم
  بدء الأسبوع، وتغيير عدد الأيام في الشهر، وتخصيص تقويم المشروع بكفاءة.
linktitle: Weekday Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: aspose tasks java – إدارة خصائص أيام الأسبوع
url: /ar/java/project-file-operations/weekday-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose tasks java – إدارة خصائص أيام الأسبوع

## المقدمة
Aspose.Tasks for Java (aspose tasks java) هي واجهة برمجة تطبيقات قوية تتيح لمطوري Java العمل مع ملفات Microsoft Project دون الحاجة إلى تثبيت Microsoft Project. في هذا الدليل ستتعلم كيفية **تحميل ملف MPP**، **تحديد يوم بدء الأسبوع**، **تغيير عدد الأيام في الشهر**، و**تخصيص تقويم المشروع** — جميعها خطوات أساسية لتحديث جدول المشروع. في النهاية، ستتمكن من تعديل خصائص أيام الأسبوع برمجياً وحفظ التغييرات بالتنسيق الذي تحتاجه.

## إجابات سريعة
- **ما هي الفئة الأساسية للتعامل مع المشاريع؟** `Project` من مكتبة Aspose.Tasks.  
- **كيف يمكنني تغيير يوم بدء الأسبوع؟** استخدم `project.set(Prj.WEEK_START_DAY, DayType.Monday)`.  
- **هل يمكنني تحميل ملف .mpp موجود؟** نعم — أنشئ كائن `Project` باستخدام مسار الملف.  
- **ما الطريقة التي تحفظ المشروع كملف XML؟** `project.save(path, SaveFileFormat.Xml)`.  
- **هل أحتاج إلى ترخيص للتطوير؟** النسخة التجريبية المجانية تكفي للتقييم؛ الترخيص مطلوب للإنتاج.

## المتطلبات المسبقة
قبل البدء، تأكد من توفر ما يلي:

- **Java Development Kit (JDK)** – أحدث نسخة مثبتة.  
- **Aspose.Tasks for Java library** – قم بتحميله [هنا](https://releases.aspose.com/tasks/java/).  
- **بيئة تطوير متكاملة (IDE)** مثل IntelliJ IDEA أو Eclipse أو NetBeans.  

## استيراد الحزم
لبدء العمل، استورد الفئات الأساسية من Aspose.Tasks:

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

الآن دعنا نستعرض كل خطوة من خطوات إدارة خصائص أيام الأسبوع.

## الخطوة 1: تحميل ملف MPP
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
*هنا نقوم **بتحميل ملف .mpp موجود** (`load mpp file`) حتى نتمكن من فحص وتعديل إعدادات تقويمه.*

## الخطوة 2: عرض خصائص أيام الأسبوع الحالية
```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```
يقوم هذا الكود بطباعة **يوم بدء الأسبوع** الحالي، **عدد الأيام في الشهر**، **الدقائق في اليوم**، و**الدقائق في الأسبوع** — العناصر الأساسية التي ستحتاج غالباً إلى **تخصيص تقويم المشروع**.

## الخطوة 3: تعيين خصائص أيام أسبوع جديدة
```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```
في هذه الخطوة نقوم **بتحديد يوم بدء الأسبوع** إلى الإثنين، **تغيير عدد الأيام في الشهر** إلى 24، وتعديل عدد الدقائق اليومية والأسبوعية. هذه الإعدادات شائعة عندما تحتاج إلى **تحديث جدول المشروع** ليتوافق مع تقويم عمل غير قياسي.

## الخطوة 4: حفظ المشروع المحدث
```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
يتم حفظ المشروع المعدل كملف XML، مما يسهل مشاركته أو استيراده إلى أدوات أخرى.

## الخطوة 5: تأكيد العملية
```java
System.out.println("Process completed Successfully");
```
رسالة بسيطة في وحدة التحكم تخبرك بأن سير العمل انتهى دون أخطاء.

## المشكلات الشائعة والنصائح
- **مسار ملف غير صحيح** – تحقق من أن `dataDir` ينتهي بشرطة مائلة أو استخدم `Paths.get(...)` للحصول على مسارات مستقلة عن النظام.  
- **الترخيص غير مُعين** – في بيئة الإنتاج، استدعِ `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` قبل إنشاء `Project`.  
- **يوم بدء أسبوع غير متوقع** – تأكد من استخدام قيمة `DayType` الصحيحة (مثال: `DayType.Sunday`).  

## الأسئلة المتكررة

**س: هل يمكن لـ Aspose.Tasks for Java التعامل مع هياكل مشاريع معقدة؟**  
ج: نعم، توفر Aspose.Tasks for Java دعماً شاملاً للتعامل مع هياكل مشاريع معقدة بسهولة.

**س: هل Aspose.Tasks for Java متوافق مع إصدارات مختلفة من ملفات Microsoft Project؟**  
ج: بالتأكيد، يدعم Aspose.Tasks for Java إصدارات متعددة من ملفات Microsoft Project، مما يضمن التوافق عبر المنصات.

**س: هل يمكنني دمج Aspose.Tasks for Java في تطبيقاتي الحالية المكتوبة بـ Java؟**  
ج: نعم، يقدم Aspose.Tasks for Java إمكانيات دمج سلسة، مما يسمح لك بتعزيز تطبيقات Java بميزات قوية لإدارة المشاريع.

**س: هل توفر Aspose.Tasks for Java وثائق ودعمًا؟**  
ج: نعم، يمكنك الوصول إلى وثائق شاملة ودعم المجتمع لـ Aspose.Tasks for Java عبر موقعهم على الويب [هنا](https://releases.aspose.com/).

**س: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Tasks for Java؟**  
ج: نعم، يمكنك تحميل نسخة تجريبية مجانية من Aspose.Tasks for Java من موقعهم [هنا](https://reference.aspose.com/tasks/java/) لاستكشاف الميزات قبل الشراء.

---

**آخر تحديث:** 2025-12-23  
**تم الاختبار مع:** Aspose.Tasks for Java 24.11  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}