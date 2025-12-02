---
date: 2025-12-02
description: تعلم كيفية إضافة تقويم إلى المشروع، وكيفية إنشاء تقويم MS Project، وحفظ
  المشروع كملف XML باستخدام Aspose.Tasks للغة Java.
language: ar
linktitle: Add Calendar to Project using Aspose.Tasks
second_title: Aspose.Tasks Java API
title: إضافة تقويم إلى المشروع باستخدام Aspose.Tasks للـ Java
url: /java/calendars/create/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة تقويم إلى المشروع باستخدام Aspose.Tasks للغة Java

## المقدمة
في سير عمل إدارة المشاريع الحديثة، القدرة على **add calendar to project** برمجياً يمكن أن توفر ساعات من التعديل اليدوي. توفر Aspose.Tasks للغة Java للمطورين واجهة برمجة تطبيقات نظيفة وآمنة من حيث النوع للتعامل مع ملفات Microsoft Project دون الحاجة لفتح العميل المكتبي. في هذا البرنامج التعليمي ستتعلم **how to add calendar**, **how to create MS Project calendar**, و **save project as XML**—كل ذلك ببضع أسطر من كود Java.

## إجابات سريعة
- **What does “add calendar to project” mean?**  
  يعني ذلك إدراج تعريف جديد لوقت العمل (تقويم) في ملف Microsoft Project عبر الكود.  
- **Which library handles this?**  
  توفر Aspose.Tasks للغة Java الفئة `Calendar` وحاوية `Project` لإدارة التقويمات.  
- **Do I need a license?**  
  ترخيص تقييم مؤقت يكفي للاختبار؛ يلزم الحصول على ترخيص كامل للاستخدام في بيئة الإنتاج.  
- **Can I save the file as XML?**  
  نعم—استخدم `SaveFileFormat.Xml` لتصدير المشروع كملف XML.  
- **What are the prerequisites?**  
  Java JDK 8+ وملف JAR الخاص بـ Aspose.Tasks للغة Java في مسار الـ classpath الخاص بك.

## ما هو “add calendar to project”؟
إضافة تقويم إلى مشروع تُنشئ جدولاً مخصصاً يحدد أيام العمل، العطلات، وساعات العمل اليومية. يمكن بعد ذلك تعيين هذا التقويم للمهام أو الموارد أو للمشروع بأكمله، مما يضمن أن حسابات مثل تواريخ البدء والمدة تحترم وقت العمل المحدد.

## لماذا تستخدم Aspose.Tasks للغة Java لإضافة تقويم إلى المشروع؟
- **تحكم كامل** – لا حاجة لواجهة مستخدم؛ يمكن أتمتة إنشاء تقويمات جماعية عبر العديد من المشاريع.  
- **توافق عبر الإصدارات** – يعمل مع ملفات Project 2007، 2010، 2013، 2016، والإصدارات الأحدث.  
- **بدون تثبيت Microsoft Project** – يمكن تشغيله على أي خادم أو خط أنابيب CI.  
- **مرونة التصدير** – احفظ كملف XML، MPP، أو أي تنسيق مدعوم آخر.

## المتطلبات المسبقة
- **Java Development Kit (JDK) 8 أو أحدث** مثبت ومُعد.  
- مكتبة **Aspose.Tasks للغة Java** – حمّلها من [الموقع الرسمي](https://releases.aspose.com/tasks/java/) وأضف ملف JAR إلى مسار الـ classpath الخاص بمشروعك.  
- بيئة تطوير متكاملة (IDE) أو أداة بناء (Maven/Gradle) حسب اختيارك.

## دليل خطوة بخطوة

### الخطوة 1: استيراد حزمة Aspose.Tasks المطلوبة
أولاً، استورد فئات Aspose.Tasks إلى النطاق لتتمكن من العمل مع المشاريع والتقويمات.

```java
import com.aspose.tasks.*;
```

### الخطوة 2: تعيين مسار دليل البيانات
حدد المكان الذي سيُكتب فيه ملف المشروع المُنشأ. استبدل العنصر النائب بمسار مطلق أو نسبي على جهازك.

```java
String dataDir = "Your Data Directory";
```

### الخطوة 3: إنشاء كائن Project جديد
أنشئ كائن `Project` – يمثل ملف Microsoft Project فارغ يمكنك ملؤه.

```java
Project prj = new Project();
```

### الخطوة 4: تعريف التقويمات التي تريد إضافتها
استخدم الطريقة `Calendars.add(String name)` لإنشاء إدخالات تقويم جديدة. في هذا المثال نضيف ثلاثة تقويمات، لكن يمكنك إضافة أي عدد تحتاجه وتكوين أوقات العمل لاحقاً.

```java
Calendar cal1 = prj.getCalendars().add("no info");
Calendar cal2 = prj.getCalendars().add("no name");
Calendar cal3 = prj.getCalendars().add("cal3");
```

> **نصيحة احترافية:** بعد إضافة تقويم، يمكنك تخصيص أيام العمل باستخدام `cal1.getWeekDays().add(...)` وتحديد ساعات العمل اليومية عبر `cal1.getBaseCalendar().setWorkingTime(...)`.

### الخطوة 5: حفظ المشروع (حفظ المشروع كملف XML)
احفظ المشروع، بما في ذلك التقويمات المضافة حديثاً، إلى ملف XML. هذا التنسيق سهل الفحص ومتوافق مع العديد من الأدوات.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### الخطوة 6: عرض رسالة إكمال
أخبر المستخدم أن العملية انتهت بنجاح.

```java
System.out.println("Process completed Successfully");
```

باتباع هذه الخطوات الست المختصرة، تكون قد نجحت في **add calendar to project** وحفظ النتيجة كملف XML.

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|--------|-----|
| **`NullPointerException` on `prj.getCalendars()`** | كائن Project لم يتم تهيئته بشكل صحيح. | تأكد من استدعاء `new Project()` قبل الوصول إلى التقويمات. |
| **File not found when saving** | `dataDir` يشير إلى مجلد غير موجود. | أنشئ المجلد أولاً أو استخدم مسارًا مطلقًا. |
| **Calendar name appears as “no info”** | تم استخدام أسماء بديلة في العينة. | استبدلها بأسماء ذات معنى تعكس الجدول الزمني (مثال: “US Holiday Calendar”). |
| **Saved XML cannot be opened in MS Project** | استخدام نسخة قديمة من Aspose.Tasks. | حدّث إلى أحدث إصدار من Aspose.Tasks للغة Java. |

## الأسئلة المتكررة

**س: هل يمكن لـ Aspose.Tasks التعامل مع تقويمات معقدة تحتوي على استثناءات متعددة؟**  
ج: نعم – بعد إضافة تقويم يمكنك تعريف الاستثناءات، ساعات العمل، وأيام عدم العمل باستخدام فئتي `WeekDay` و `Exception`.

**س: هل من الممكن تعيين التقويم الجديد لمهام محددة؟**  
ج: بالتأكيد. استرجع مهمة عبر `prj.getRootTask().getChildren().add("Task Name")` ثم عيّن `task.set(Tsk.CALENDAR, cal3);`.

**س: هل تدعم المكتبة الحفظ بتنسيقات أخرى مثل MPP؟**  
ج: نعم. استبدل `SaveFileFormat.Xml` بـ `SaveFileFormat.Mpp` أو `SaveFileFormat.P6` حسب الحاجة.

**س: هل أحتاج إلى ترخيص لبناءات التطوير؟**  
ج: ترخيص تقييم مؤقت يكفي للاختبار؛ يلزم الحصول على ترخيص كامل للنشر في بيئات الإنتاج.

**س: أين يمكنني الحصول على مساعدة إذا واجهت مشاكل؟**  
ج: منتدى مجتمع Aspose.Tasks هو مصدر ممتاز: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## الخلاصة
باستخدام Aspose.Tasks للغة Java، يمكنك برمجياً **add calendar to project**، تخصيص قواعد الجدولة، و **save project as XML** ببضع أسطر من الكود. هذه الأتمتة تقلل الجهد اليدوي، تُزيل الأخطاء البشرية، وتُمكّن من معالجة دفعات كبيرة من مشاريع المحفظة.

---

**آخر تحديث:** 2025-12-02  
**تم الاختبار مع:** Aspose.Tasks للغة Java 24.12 (أحدث نسخة وقت كتابة هذا الدليل)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}