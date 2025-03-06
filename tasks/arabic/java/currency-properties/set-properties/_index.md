---
title: قم بتعيين خصائص العملة في مشاريع Aspose.Tasks
linktitle: قم بتعيين خصائص العملة في مشاريع Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية تعيين خصائص العملة في مشاريع Aspose.Tasks باستخدام Java. التعامل مع ملفات Microsoft Project دون عناء.
weight: 11
url: /ar/java/currency-properties/set-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# قم بتعيين خصائص العملة في مشاريع Aspose.Tasks

## مقدمة
في هذا البرنامج التعليمي، سوف نستكشف كيفية تعيين خصائص العملة في مشاريع Aspose.Tasks باستخدام Java. Aspose.Tasks هي مكتبة Java قوية تسمح للمطورين بمعالجة ملفات Microsoft Project برمجياً.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
1. Java Development Kit (JDK): تأكد من تثبيت JDK على نظامك.
2.  Aspose.Tasks لمكتبة Java: قم بتنزيل وتثبيت Aspose.Tasks لمكتبة Java من[رابط التحميل](https://releases.aspose.com/tasks/java/).
3. بيئة التطوير المتكاملة (IDE): اختر IDE المفضل لديك مثل Eclipse أو IntelliJ IDEA.
## حزم الاستيراد
أولاً، لنستورد الحزم اللازمة للعمل مع Aspose.Tasks في Java.
```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```
## الخطوة 1: قم بتعيين دليل البيانات
قم بتعيين دليل البيانات حيث توجد ملفات مشروعك.
```java
String dataDir = "Your Data Directory";
```
## الخطوة 2: إنشاء مثيل المشروع
قم بإنشاء مثيل مشروع جديد باستخدام Aspose.Tasks.
```java
Project project = new Project();
```
## الخطوة 3: تعيين خصائص العملة
الآن، لنقم بتعيين خصائص العملة للمشروع.
```java
project.set(Prj.CURRENCY_CODE, "AUD");
project.set(Prj.CURRENCY_DIGITS, 2);
project.set(Prj.CURRENCY_SYMBOL, "$");
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After);
```
## الخطوة 4: احفظ المشروع
احفظ المشروع بخصائص العملة المحدثة.
```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```
## الخطوة 5: عرض رسالة الإكمال
عرض رسالة تشير إلى إتمام العملية بنجاح.
```java
System.out.println("Process completed Successfully");
```
تهانينا! لقد قمت بتعيين خصائص العملة بنجاح في مشروع Aspose.Tasks باستخدام Java.
## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية استخدام Aspose.Tasks لـ Java لتعيين خصائص العملة في ملفات المشروع. باستخدام Aspose.Tasks، يمكن للمطورين معالجة بيانات المشروع بكفاءة، مما يجعلها أداة قيمة لتطبيقات إدارة المشروع.
## الأسئلة الشائعة
### هل يمكنني تعيين عملات متعددة في مشروع واحد باستخدام Aspose.Tasks؟
نعم، يتيح لك Aspose.Tasks التعامل مع عملات متعددة ضمن ملف مشروع واحد.
### هل Aspose.Tasks متوافق مع الإصدارات المختلفة من ملفات Microsoft Project؟
نعم، يدعم Aspose.Tasks إصدارات مختلفة من ملفات Microsoft Project، مما يضمن التوافق عبر بيئات مختلفة.
### هل يوفر Aspose.Tasks الدعم لتنسيقات العملة المخصصة؟
بالتأكيد، يوفر Aspose.Tasks المرونة في تحديد تنسيقات العملة المخصصة لتلبية متطلبات المشروع المحددة.
### هل يمكنني دمج Aspose.Tasks مع مكتبات أو أطر عمل Java الأخرى؟
نعم، يمكن دمج Aspose.Tasks بسلاسة مع مكتبات وأطر عمل Java الأخرى، مما يعزز وظائفها وتعدد استخداماتها.
### أين يمكنني العثور على دعم أو مساعدة إضافية لـ Aspose.Tasks؟
 للحصول على دعم إضافي، يمكنك زيارة[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15)، حيث يمكنك العثور على موارد مفيدة والتفاعل مع المجتمع.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
