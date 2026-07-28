---
date: 2026-01-28
description: تعلم كيفية إنشاء تقويم المشروع باستخدام Aspose، وتحديد أيام الأسبوع لاستثناءات
  التقويم، وإدارة جدول أيام غير العمل باستخدام Aspose.Tasks للغة Java.
linktitle: Create Project Calendar Aspose – Define Weekdays for Calendar Exceptions
second_title: Aspose.Tasks Java API
title: إنشاء تقويم المشروع Aspose – تحديد أيام الأسبوع لاستثناءات التقويم
url: /ar/java/calendar-exceptions/define-weekdays/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء تقويم مشروع Aspose – تعريف أيام الأسبوع لاستثناءات التقويم

### المقدمة
عندما تحتاج إلى **create project calendar aspose**، يجب أن تكون قادرًا على نمذجة أيام العمل غير القياسية مثل العطلات، والنوبات الخاصة، أو الإغلاقات المؤقتة. توفر لك Aspose.Tasks for Java تحكمًا كاملاً في تعريفات التقويم، مما يتيح لك إضافة استثناءات تعكس الجداول الزمنية الواقعية. في هذا البرنامج التعليمي سنستعرض الخطوات الدقيقة لتعريف أيام الأسبوع لاستثناءات التقويم، بحيث تظل جداول مشروعك دقيقة وموثوقة. في النهاية ستلاحظ أيضًا كيف يتناسب ذلك مع استراتيجية **non‑working days schedule** الأوسع لأي مشروع مؤسسي.

## إجابات سريعة
- **What does “create project calendar aspose” mean?**  
  يشير إلى استخدام Aspose.Tasks لإنشاء كائن تقويم مخصص يتحكم في جدولة المهام.
- **Do I need a license to run the sample?**  
  إصدار تجريبي مجاني يكفي للتطوير؛ يتطلب الترخيص التجاري للإنتاج.
- **Which IDEs are supported?**  
  IntelliJ IDEA، Eclipse، NetBeans، أو أي بيئة تطوير تدعم Java 8+.
- **Can I add multiple exceptions to the same calendar?**  
  نعم – يمكنك إضافة عدد غير محدود من كائنات `CalendarException` حسب الحاجة.
- **What file formats can I save the project to?**  
  XML، MPP، والعديد من الصيغ الأخرى التي تدعمها Aspose.Tasks.

## ما هو تقويم المشروع في Aspose.Tasks؟
يحدد **تقويم المشروع** أيام وساعات العمل للمشروع. يؤثر على تواريخ بدء/انتهاء المهام، وتخصيص الموارد، وحسابات الجدول الزمني العامة. من خلال تخصيص تقويم، تضمن أن الجدول الزمني يحترم القيود الواقعية مثل عطلات الشركة أو سياسات العمل في عطلات نهاية الأسبوع.

## لماذا تعريف أيام الأسبوع لاستثناءات التقويم؟
- **Accurate timelines:** المهام لن تُجدول في الأيام التي تم وضع علامة غير عمل عليها.
- **Resource planning:** يتم تخصيص الموارد فقط في أيام العمل الصالحة.
- **Compliance:** يطابق جداول المشروع سياسات المنظمة أو العطلات القانونية.

## جدول أيام غير العمل مع استثناءات التقويم
عند الحفاظ على **non‑working days schedule**، عادةً ما يكون لديك قائمة رئيسية بالعطلات، وفترات الصيانة، أو فترات الحظر الأخرى. إضافة تلك التواريخ ككائنات `CalendarException` يضمن أن كل حساب—سواء كان تحليل المسار الحرج أو تسوية الموارد—يحترم تلك القيود تلقائيًا. هذه الطريقة تلغي التعديلات اليدوية للتواريخ وتقلل من خطر انحراف الجدول.

## المتطلبات المسبقة
1. **Java Development Kit (JDK)** – الإصدار 8 أو أحدث.  
2. **Aspose.Tasks for Java** – تحميل من صفحة [Aspose.Tasks Java download page](https://releases.aspose.com/tasks/java/).  
3. **An IDE** – IntelliJ IDEA، Eclipse، NetBeans، أو أي محرر متوافق مع Java.

## كيفية إنشاء تقويم مشروع aspose – تعريف أيام الأسبوع لاستثناءات التقويم
### دليل خطوة بخطوة

### الخطوة 1: استيراد الحزم المطلوبة
نحتاج إلى الفئات الأساسية في Aspose.Tasks و`GregorianCalendar` في Java لمعالجة التواريخ.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

### الخطوة 2: تحديد دليل البيانات
حدد المكان الذي سيتم حفظ ملف المشروع المُنشأ فيه.

```java
String dataDir = "Your Data Directory";
```

### الخطوة 3: إنشاء نسخة من المشروع
إنشاء كائن `Project` جديد – هذا هو الحاوية لجميع بيانات المشروع، بما في ذلك التقويمات.

```java
Project project = new Project();
```

### الخطوة 4: تعريف تقويم
إضافة تقويم مخصص إلى المشروع. سيحتوي هذا التقويم على استثناءاتنا.

```java
Calendar cal = project.getCalendars().add("Calendar1");
```

### الخطوة 5: تعريف استثناء أيام الأسبوع
إنشاء `CalendarException` يحدد نطاقًا من الأيام (مثلاً الأسبوع الأخير من ديسمبر) كغير عمل.  
المثال يحدد الاستثناء من **24 Dec 2009** إلى **31 Dec 2009**، ويعطل العمل لتلك الأيام، ويعامل الاستثناء كنوع يومي.

```java
CalendarException except = new CalendarException();
except.setEnteredByOccurrences(false);
except.setFromDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 24, 0, 0, 0).getTime());
except.setToDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 31, 23, 59, 0).getTime());
except.setType(CalendarExceptionType.Daily);
except.setDayWorking(false);
cal.getExceptions().add(except);
```

### الخطوة 6: حفظ المشروع
حفظ المشروع، بما في ذلك التقويم المخصص واستثنائه، إلى ملف XML.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## المشكلات الشائعة والحلول
| المشكلة | الحل |
|-------|----------|
| **Exception dates not applied** | تأكد من ضبط `setEnteredByOccurrences(false)` والقيم الصحيحة لـ `FromDate/ToDate`. |
| **Saved file is empty** | تحقق من أن `dataDir` يشير إلى مجلد قابل للكتابة وأن اسم الملف ينتهي بـ `.xml`. |
| **Calendar not reflected in task scheduling** | قم بتعيين التقويم للمهام أو الموارد باستخدام `task.setCalendar(cal)` أو `resource.setCalendar(cal)`. |

## الأسئلة المتكررة

**Q: هل يمكنني تعريف استثناءات متعددة لأيام أسبوع مختلفة داخل نفس التقويم؟**  
A: نعم. أضف كائنات `CalendarException` إضافية إلى `cal.getExceptions()` لكل فترة أو قاعدة مميزة.

**Q: هل Aspose.Tasks for Java متوافق مع بيئات تطوير Java المختلفة؟**  
A: بالطبع. المكتبة تعمل مع IntelliJ IDEA، Eclipse، NetBeans، وأي بيئة تطوير تدعم مشاريع Java القياسية.

**Q: هل يمكنني تخصيص أنواع استثناء غير الاستثناءات اليومية؟**  
A: نعم. استخدم `CalendarExceptionType.Weekly` أو `Monthly` أو `Yearly` لتلبية احتياجات الجدولة الخاصة بك.

**Q: كيف يمكنني معالجة الاستثناءات بشكل ديناميكي بناءً على متطلبات المشروع؟**  
A: قم بإنشاء كائنات الاستثناء برمجيًا—مثلاً، قراءة تواريخ العطلات من قاعدة بيانات أو ملف إعدادات وإنشاء مثيلات `CalendarException` داخل حلقة.

**Q: هل هناك نسخة تجريبية متاحة لـ Aspose.Tasks for Java؟**  
A: نعم، يمكنك تنزيل نسخة تجريبية مجانية من [صفحة تحميل Aspose.Tasks Java](https://releases.aspose.com/tasks/java/).

## الخلاصة
باتباع هذه الخطوات، أصبحت الآن تعرف كيفية **create project calendar aspose** وتعريف استثناءات أيام الأسبوع التي تعكس بدقة العطلات أو فترات غير العمل الخاصة. تكوين التقويم بشكل صحيح أمر أساسي للجداول الزمنية الواقعية، وتخصيص الموارد، ونجاح المشروع بشكل عام. استكشف المزيد عن طريق إرفاق التقويم المخصص بالمهام أو الموارد وتجربة أنواع استثناء أخرى لبناء **non‑working days schedule** شاملة لأي مشروع.

---

**آخر تحديث:** 2026-01-28  
**تم الاختبار مع:** Aspose.Tasks for Java 24.11  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}