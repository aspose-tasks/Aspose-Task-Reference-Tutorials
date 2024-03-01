---
title: تحديد أيام الأسبوع لاستثناءات التقويم باستخدام Aspose.Tasks
linktitle: تحديد أيام الأسبوع لاستثناءات التقويم باستخدام Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية تحديد أيام الأسبوع لاستثناءات التقويم في مشاريع Java باستخدام Aspose.Tasks لجدولة دقيقة للمشروع.
type: docs
weight: 11
url: /ar/java/calendar-exceptions/define-weekdays/
---
### مقدمة
في إدارة المشاريع، يعد تحديد الاستثناءات للتقويمات أمرًا بالغ الأهمية لتمثيل أيام العمل أو العطلات غير القياسية بدقة ضمن الجدول الزمني للمشروع. يوفر Aspose.Tasks for Java وظائف قوية لإدارة التقويمات بكفاءة، بما في ذلك تحديد الاستثناءات مثل العطلات أو أيام العمل الخاصة. في هذا البرنامج التعليمي، سنتعمق في كيفية تحديد أيام الأسبوع لاستثناءات التقويم باستخدام Aspose.Tasks لـ Java.
### المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من إعداد المتطلبات الأساسية التالية:
1. Java Development Kit (JDK): تأكد من تثبيت JDK على نظامك.
2.  Aspose.Tasks لـ Java: قم بتنزيل Aspose.Tasks لـ Java وتثبيته من[رابط التحميل](https://releases.aspose.com/tasks/java/).
3. بيئة التطوير المتكاملة (IDE): اختر IDE المفضل لديك لتطوير Java.

## حزم الاستيراد
للبدء، قم باستيراد الحزم اللازمة لـ Aspose.Tasks في مشروع Java الخاص بك:
```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;

```

## الخطوة 1: تحديد دليل البيانات
قم بإعداد المسار إلى دليل البيانات الخاص بك حيث سيتم تخزين ملفات المشروع.
```java
String dataDir = "Your Data Directory";
```
## الخطوة 2: إنشاء مثيل المشروع
قم بتهيئة مثيل جديد لفئة Project لبدء العمل مع بيانات المشروع.
```java
Project project = new Project();
```
## الخطوة 3: تحديد التقويم
قم بإنشاء كائن تقويم لتحديد التقويم الذي ستتم إضافة الاستثناءات إليه.
```java
Calendar cal = project.getCalendars().add("Calendar1");
```
## الخطوة 4: تحديد استثناء أيام الأسبوع
حدد استثناءً لأيام الأسبوع، مثل أيام العطل، ضمن التقويم.
```java
CalendarException except = new CalendarException();
except.setEnteredByOccurrences(false);
except.setFromDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 24, 0, 0, 0).getTime());
except.setToDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 31, 23, 59, 0).getTime());
except.setType(CalendarExceptionType.Daily);
except.setDayWorking(false);
cal.getExceptions().add(except);
```
## الخطوة 5: احفظ المشروع
احفظ ملف المشروع مع استثناءات التقويم المحددة.
```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## خاتمة
باتباع هذه الخطوات، يمكنك تحديد أيام الأسبوع بشكل فعال لاستثناءات التقويم في مشروعك باستخدام Aspose.Tasks for Java. إدارة الاستثناءات مثل العطلات أو أيام العمل الخاصة تضمن جدولة دقيقة وتمثيل الجداول الزمنية للمشروع.
## الأسئلة الشائعة
### س: هل يمكنني تحديد استثناءات متعددة لأيام الأسبوع المختلفة ضمن نفس التقويم؟
ج: نعم، يمكنك تحديد استثناءات متعددة لأيام الأسبوع المختلفة ضمن تقويم واحد باستخدام Aspose.Tasks لـ Java.
### س: هل Aspose.Tasks لـ Java متوافق مع بيئة Java IDEs المختلفة؟
ج: Aspose.Tasks for Java متوافق مع Java IDEs الشائعة مثل IntelliJ IDEA وEclipse وNetBeans.
### س: هل يمكنني تخصيص أنواع الاستثناءات بخلاف الاستثناءات اليومية؟
ج: بالتأكيد، يوفر Aspose.Tasks لـ Java المرونة في تحديد الاستثناءات بناءً على معايير مختلفة، ولا يقتصر على الاستثناءات اليومية.
### س: كيف يمكنني التعامل مع الاستثناءات ديناميكيًا بناءً على متطلبات المشروع؟
ج: يمكنك التعامل مع الاستثناءات برمجيًا استنادًا إلى متطلبات المشروع الديناميكية باستخدام واجهة برمجة التطبيقات الشاملة التي توفرها Aspose.Tasks لـ Java.
### س: هل هناك إصدار تجريبي متاح لـ Aspose.Tasks لـ Java؟
 ج: نعم، يمكنك الاستفادة من الإصدار التجريبي المجاني من Aspose.Tasks لـ Java من[موقع إلكتروني](https://releases.aspose.com/).
