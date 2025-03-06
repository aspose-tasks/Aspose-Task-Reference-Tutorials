---
title: طباعة الصفحات لفصل الصورة في Aspose.Tasks
linktitle: طباعة الصفحات لفصل الصورة في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية طباعة الصفحات لفصل الصور في Aspose.Tasks لـ Java. قم بتحسين تصور المشروع باستخدام هذا الدليل التفصيلي.
type: docs
weight: 22
url: /ar/java/project-management/print-pages/
---
## مقدمة
في هذا البرنامج التعليمي، سنرشدك خلال عملية طباعة الصفحات لفصل الصور باستخدام Aspose.Tasks لـ Java. يمكن أن تكون هذه الوظيفة مفيدة بشكل خاص عندما تحتاج إلى تصور تخطيطات المشروع أو المهام الهامة بشكل منفصل.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
1.  Java Development Kit (JDK): تأكد من تثبيت JDK على نظامك. يمكنك تنزيله من[هنا](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
   
2.  Aspose.Tasks لمكتبة Java: قم بتنزيل مكتبة Aspose.Tasks لـ Java وتضمينها في مشروعك. يمكنك الحصول عليه من[هنا](https://releases.aspose.com/tasks/java/).

## حزم الاستيراد
تأكد من استيراد الحزم الضرورية في بداية ملف Java الخاص بك:
```java
import com.aspose.tasks.Gridline;
import com.aspose.tasks.GridlineType;
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.LinePattern;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.awt.*;
import java.util.ArrayList;
```
## الخطوة 1: تحميل بيانات المشروع
أولاً، قم بتحميل بيانات المشروع من ملف MPP الخاص بك:
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "CustomerFeedback.mpp");
```
## الخطوة 2: ضبط خيارات حفظ الصورة
حدد خيارات حفظ الصورة، بما في ذلك تاريخ البدء وتاريخ الانتهاء والمهام الهامة ووسيلة الإيضاح وخطوط الشبكة:
```java
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFileFormat.Png);
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.setTime(project.get(Prj.START_DATE));
cal.add(java.util.Calendar.DATE, -3);
saveOptions.setStartDate(cal.getTime());
saveOptions.setEndDate(project.get(Prj.FINISH_DATE));
saveOptions.setMarkCriticalTasks(true);
saveOptions.setLegendOnEachPage(false);
```
## الخطوة 3: تخصيص خطوط الشبكة
تخصيص خطوط الشبكة للصورة، وتحديد النوع واللون والنمط:
```java
saveOptions.setGridlines(new ArrayList<Gridline>());
Gridline gridline = new Gridline();
gridline.setGridlineType(GridlineType.GanttRow);
gridline.setColor(Color.BLUE);
gridline.setPattern(LinePattern.Dashed);
saveOptions.getGridlines().add(gridline);
```
## الخطوة 4: حفظ الصور
احفظ تخطيط المشروع كصور، كملف واحد وملفات منفصلة:
```java
project.save(dataDir + "CustomerFeedback.png", saveOptions);
saveOptions.setRenderToSinglePage(false);
project.save(dataDir + "CustomerFeedback_.png", saveOptions);
```

## خاتمة
في هذا البرنامج التعليمي، أوضحنا كيفية طباعة الصفحات لفصل الصور باستخدام Aspose.Tasks لـ Java. باتباع الخطوات الموضحة أعلاه، يمكنك تصور تخطيطات المشروع والمهام الهامة بكفاءة وفقًا لمتطلباتك.
## الأسئلة الشائعة
### س: هل يمكنني تخصيص تنسيق الصورة عند حفظ تخطيطات المشروع؟
 ج: نعم، يدعم Aspose.Tasks for Java تنسيقات صور متنوعة مثل PNG، وJPEG، وBMP، وما إلى ذلك. ويمكنك تحديد التنسيق المطلوب في`ImageSaveOptions` فصل.
### س: هل Aspose.Tasks for Java متوافق مع بيئات تطوير Java المختلفة؟
ج: نعم، Aspose.Tasks for Java متوافق مع معظم بيئات تطوير Java، بما في ذلك Eclipse وIntelliJ IDEA وNetBeans.
### س: هل يمكنني دمج Aspose.Tasks for Java في مشروع Maven أو Gradle الخاص بي؟
ج: نعم، يمكنك بسهولة دمج Aspose.Tasks for Java في مشروع Maven أو Gradle الخاص بك عن طريق إضافة التبعية المناسبة في ملفك`pom.xml` أو`build.gradle` ملف.
### س: هل يدعم Aspose.Tasks for Java تصدير بيانات المشروع إلى تنسيقات أخرى إلى جانب الصور؟
ج: نعم، يدعم Aspose.Tasks for Java تصدير بيانات المشروع إلى تنسيقات مختلفة مثل PDF وHTML وXLSX وما إلى ذلك، مما يوفر المرونة في تصور البيانات وإعداد التقارير.
### س: هل يتوفر أي دعم مجتمعي لـ Aspose.Tasks لـ Java؟
 ج: نعم، يمكنك العثور على دعم المجتمع وطرح الأسئلة والتفاعل مع المستخدمين الآخرين على الموقع[Aspose.منتدى المهام](https://forum.aspose.com/c/tasks/15).