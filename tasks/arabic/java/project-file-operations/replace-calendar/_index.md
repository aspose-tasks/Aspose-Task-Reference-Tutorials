---
date: 2025-12-18
description: تعلم كيفية إضافة ملفات تقويم MS Project باستخدام Aspose.Tasks للغة Java.
  دليل خطوة‑بخطوة لاستبدال وتعديل وإزالة التقويمات في Microsoft Project.
linktitle: Replace Calendar in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: إضافة تقويم MS Project – استبدال التقويم في Aspose.Tasks
url: /ar/java/project-file-operations/replace-calendar/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة تقويم MS Project – استبدال التقويم في Aspose.Tasks

## مقدمة
في هذا البرنامج التعليمي، ستكتشف **كيفية إضافة تقويم MS Project** برمجيًا باستخدام Aspose.Tasks for Java. تخصيص تقويمات المشروع هو حاجة روتينية لمديري المشاريع، وتُسهل Aspose.Tasks استبدال أو تعديل أو إزالة التقويمات دون فتح Microsoft Project يدويًا. سنستعرض كل خطوة، نشرح لماذا كل إجراء مهم، ونقدم لك نصائح لتجنب المشكلات الشائعة.

## إجابات سريعة
- **ماذا يعني “add calendar MS Project”?**  
  يعني ذلك إنشاء كائن تقويم جديد في ملف Project وإدراجه في مجموعة تقويمات المشروع.  
- **ما المكتبة التي تتعامل مع ذلك؟**  
  توفر Aspose.Tasks for Java الفئات `Calendar` و `Project` اللازمة لتعامل مع التقويم.  
- **هل أحتاج إلى ترخيص؟**  
  يتوفر نسخة تجريبية مجانية، لكن الترخيص التجاري مطلوب للاستخدام في الإنتاج.  
- **هل يمكنني استبدال تقويم موجود؟**  
  نعم – يمكنك إزالة التقويم القديم وإضافة تقويم جديد في بضع أسطر من الشيفرة.  
- **هل هذا متوافق مع جميع إصدارات Project؟**  
  تدعم Aspose.Tasks إصدارات متعددة من Microsoft Project، لذا يعمل نفس الكود عبرها.

## المتطلبات المسبقة
قبل أن تبدأ، تأكد من وجود:

1. معرفة أساسية بـ Java.  
2. تثبيت JDK على جهازك.  
3. بيئة تطوير متكاملة (IDE) مثل IntelliJ IDEA أو Eclipse.  
4. مكتبة Aspose.Tasks for Java – قم بتنزيلها من [here](https://releases.aspose.com/tasks/java/).  
5. الوصول إلى وثائق Aspose.Tasks للرجوع إليها، المتاحة [here](https://reference.aspose.com/tasks/java/).

## استيراد الحزم
أولاً، استورد الفئات الضرورية التي تمنحك إمكانية الوصول إلى وظائف التقويم:

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
```

## دليل خطوة بخطوة

### الخطوة 1: إنشاء كائن `Project` جديد
كائن `Project` جديد يمنحك مجموعة تقويمات فارغة للعمل معها.

```java
Project project = new Project();
```

### الخطوة 2: إضافة تقويم نائب (اختياري)
إذا كنت تريد رؤية كيفية عمل الإزالة، أضف تقويمًا تجريبيًا باسم **“Cal 1”**.

```java
project.getCalendars().add("Cal 1");
```

### الخطوة 3: إنشاء التقويم الجديد الذي تريد الاحتفاظ به
هنا نقوم بإنشاء **“New Cal”** وإضافته إلى المشروع دفعة واحدة.

```java
Calendar newCal = project.getCalendars().add("New Cal");
```

### الخطوة 4: إزالة التقويم الموجود – “Cal 1”
لـ **إزالة التقويم من المشروع**، قم بالتكرار عكسيًا عبر المجموعة (التكرار العكسي يتجنب مشاكل إزاحة الفهارس) واحذف التقويم المطابق.

```java
CalendarCollection calColl = project.getCalendars();
for (int i = calColl.size() - 1; i >= 0; i--) {
    Calendar c = calColl.get(i);
    if (c.getName().equals("Cal 1")) {
        calColl.remove(i);
        break;
    }
}
```

### الخطوة 5: إضافة التقويم الجديد إلى المجموعة
الآن بعد أن تم حذف التقويم القديم، أدخل التقويم الجديد كالتقويم **Standard** (أو أي اسم تفضله).

```java
calColl.add("Standard", newCal);
```

### الخطوة 6: عرض النتيجة
رسالة بسيطة في وحدة التحكم تؤكد نجاح العملية.

```java
System.out.println("Process completed Successfully");
```

## لماذا استبدال تقويم؟
- **Standardization:** فرض أسبوع عمل أو جدول إجازات على مستوى الشركة.  
- **Project‑specific needs:** قد تتطلب المراحل المختلفة أوقات عمل متميزة.  
- **Automation:** التغييرات البرمجية تتيح لك تحديث العشرات من الملفات في ثوانٍ.

## المشكلات الشائعة والنصائح
- **IndexOutOfBoundsException:** يجب دائمًا التكرار من نهاية المجموعة عند إزالة العناصر.  
- **Duplicate names:** تسمح Aspose.Tasks بالتقويمات ذات الاسم نفسه، لكن قد يسبب ذلك ارتباكًا عند الاستعلام بالاسم. استخدم معرّفات فريدة.  
- **Saving the project:** بعد تعديل التقويم، لا تنسَ استدعاء `project.save("output.mpp");` (غير معروض للحفاظ على الكود الأصلي دون تغيير).

## الخلاصة
باتباع هذه الخطوات، الآن تعرف **كيفية إضافة تقويم MS Project**، استبدال تقويم موجود، وحتى إزالة تقويم من ملف مشروع باستخدام Aspose.Tasks for Java. يمنحك هذا النهج تحكمًا برمجيًا كاملاً في تقويمات المشروع، مما يوفر الوقت ويقلل الأخطاء اليدوية.

## الأسئلة الشائعة
### س: هل يمكنني استخدام Aspose.Tasks for Java لتعديل جوانب أخرى من ملفات المشروع؟
ج: نعم، توفر Aspose.Tasks وظائف متعددة لتعديل المهام والموارد وعناصر المشروع الأخرى.  

### س: هل Aspose.Tasks متوافق مع جميع إصدارات Microsoft Project؟
ج: تدعم Aspose.Tasks إصدارات متعددة من Microsoft Project، مما يضمن التوافق عبر بيئات مختلفة.  

### س: هل يمكنني أتمتة مهام إدارة المشروع باستخدام Aspose.Tasks؟
ج: بالتأكيد، تمكّن Aspose.Tasks المطورين من أتمتة مجموعة واسعة من مهام إدارة المشروع، مما يحسن الكفاءة والإنتاجية.  

### س: هل تتوفر نسخة تجريبية مجانية لـ Aspose.Tasks for Java؟
ج: نعم، يمكنك الوصول إلى نسخة تجريبية مجانية من Aspose.Tasks for Java من [here](https://releases.aspose.com/).  

### س: أين يمكنني طلب الدعم أو المساعدة بخصوص Aspose.Tasks؟
ج: يمكنك زيارة منتدى Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15) للحصول على الدعم والإرشاد من المجتمع.  

---

**آخر تحديث:** 2025-12-18  
**تم الاختبار باستخدام:** Aspose.Tasks for Java 24.10  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}