---
title: استرداد استثناءات التقويم باستخدام Aspose.Tasks
linktitle: استرداد استثناءات التقويم باستخدام Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية استرداد استثناءات التقويم من MS Project باستخدام Aspose.Tasks لـ Java. البرنامج التعليمي خطوة بخطوة للتكامل السلس.
type: docs
weight: 13
url: /ar/java/calendar-exceptions/retrieve/
---
## مقدمة
في هذا البرنامج التعليمي، سوف نستكشف كيفية استرداد استثناءات التقويم من MS Project باستخدام مكتبة Aspose.Tasks لـ Java. Aspose.Tasks هي أداة قوية تسمح للمطورين بمعالجة ملفات Microsoft Project برمجياً. سنرشدك خلال العملية خطوة بخطوة، مع تقسيم كل مثال إلى خطوات متعددة لتسهيل الفهم.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
1. Java Development Kit (JDK): تأكد من تثبيت JDK على نظامك.
2.  Aspose.Tasks لـ Java: قم بتنزيل Aspose.Tasks لـ Java وتثبيته من[هنا](https://releases.aspose.com/tasks/java/).
3. بيئة التطوير المتكاملة (IDE): يمكنك استخدام أي بيئة تطوير متكاملة من اختيارك، مثل IntelliJ IDEA أو Eclipse.

## حزم الاستيراد
أولاً، تحتاج إلى استيراد الحزم اللازمة للعمل مع Aspose.Tasks:
```java
import com.aspose.tasks.*;
```
## الخطوة 1: إعداد دليل البيانات الخاص بك
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Data Directory";
```
 تأكد من الاستبدال`"Your Data Directory"` مع المسار إلى الدليل الخاص بك الذي يحتوي على ملف MS Project.
## الخطوة 2: تحميل ملف مشروع MS
```java
Project project = new Project(dataDir + "project.mpp");
```
 يقوم هذا الخط بتهيئة ملف جديد`Project` الكائن عن طريق تحميل ملف MS Project المحدد بواسطة المسار.
## الخطوة 3: استرداد استثناءات التقويم
```java
for (Calendar cal : project.getCalendars()) {
    for (CalendarException calExc : cal.getExceptions()) {
        System.out.println("From: " + calExc.getFromDate().toString());
        System.out.println("To: " + calExc.getToDate().toString());
    }
}
```
هنا، نقوم بالتكرار من خلال كل تقويم في المشروع ثم من خلال كل استثناء تقويم داخل هذا التقويم. نقوم بطباعة تاريخي البدء والانتهاء لكل استثناء.

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية استرداد استثناءات التقويم من MS Project باستخدام Aspose.Tasks لـ Java. باتباع هذه الخطوات البسيطة، يمكنك دمج هذه الوظيفة بسلاسة في تطبيقات Java الخاصة بك.
## أسئلة مكررة
### هل يستطيع Aspose.Tasks التعامل مع إصدارات مختلفة من ملفات MS Project؟
نعم، يدعم Aspose.Tasks إصدارات مختلفة من ملفات MS Project، بما في ذلك تنسيقات MPP وMPT وXML.
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Tasks؟
 نعم، يمكنك تنزيل نسخة تجريبية مجانية من Aspose.Tasks من[هنا](https://releases.aspose.com/).
### أين يمكنني العثور على وثائق Aspose.Tasks لـ Java؟
 يمكنك الرجوع إلى الوثائق[هنا](https://reference.aspose.com/tasks/java/).
### كيف يمكنني الحصول على الدعم لـ Aspose.Tasks؟
 يمكنك الحصول على الدعم من منتدى المجتمع[هنا](https://forum.aspose.com/c/tasks/15).
### هل هناك خيار للتراخيص المؤقتة لـ Aspose.Tasks؟
 نعم يمكنك الحصول على تراخيص مؤقتة من[هنا](https://purchase.aspose.com/temporary-license/).