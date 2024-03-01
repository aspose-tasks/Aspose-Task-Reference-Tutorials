---
title: إدارة سمات مشروع MS بكفاءة باستخدام Aspose.Tasks
linktitle: التعامل مع سمات الموارد الموسعة في Aspose.Tasks
second_title: Aspose.Tasks جافا API
description: تعرف على كيفية التعامل مع سمات موارد Microsoft Project الموسعة بكفاءة باستخدام Aspose.Tasks لـ Java. خطوات سهلة ودليل شامل.
type: docs
weight: 11
url: /ar/java/resource-management/extended-resource-attributes/
---
## مقدمة
في هذا البرنامج التعليمي، سوف نتعمق في كيفية التعامل بفعالية مع سمات موارد Microsoft Project الموسعة باستخدام Aspose.Tasks لـ Java. Aspose.Tasks هي مكتبة قوية تمكن المطورين من التعامل مع ملفات Microsoft Project برمجياً، مما يوفر وظائف واسعة النطاق لإدارة المهام والموارد.
## المتطلبات الأساسية
قبل المتابعة، تأكد من توفر المتطلبات الأساسية التالية:
1. بيئة تطوير Java: قم بإعداد Java Development Kit (JDK) على نظامك.
2.  Aspose.Tasks لـ Java: قم بتنزيل وتثبيت Aspose.Tasks لمكتبة Java من[هنا](https://releases.aspose.com/tasks/java/).
3. بيئة التطوير المتكاملة (IDE): قم بتثبيت IDE مثل Eclipse أو IntelliJ IDEA لتطوير Java.

## حزم الاستيراد
ابدأ باستيراد الحزم الضرورية إلى مشروع Java الخاص بك. 
```java
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.SaveFileFormat;
import java.math.BigDecimal;
```
## الخطوة 1: تحديد دليل البيانات
قم بتعيين المسار إلى الدليل الذي توجد به بيانات مشروعك.
```java
String dataDir = "Your Data Directory";
```
## الخطوة 2: تحميل ملف المشروع
 إنشاء مثيل أ`Project` كائن عن طريق تحميل ملف Microsoft Project الخاص بك.
```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```
## الخطوة 3: تحديد السمة الموسعة
تحديد السمة الموسعة للمورد.
```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```
## الخطوة 4: إنشاء سمة موسعة وتعيين القيمة
قم بإنشاء السمة الموسعة وقم بتعيين قيمة رقمية لها.
```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```
## الخطوة 5: إضافة المورد والسمة الموسعة
إضافة مورد جديد إلى المشروع مع السمة الموسعة الخاصة به.
```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```
## الخطوة 6: حفظ المشروع
احفظ المشروع المعدل في ملف جديد.
```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```
## الخطوة 7: عرض النتيجة
اطبع رسالة تؤكد إتمام العملية.
```java
System.out.println("Process completed Successfully");
```
باتباع هذه الخطوات بدقة، يمكنك التعامل بسلاسة مع سمات موارد MS Project الموسعة باستخدام Aspose.Tasks لـ Java.

## خاتمة
في الختام، يوفر Aspose.Tasks for Java إمكانات قوية لإدارة ملفات Microsoft Project، بما في ذلك التعامل مع سمات الموارد الموسعة. من خلال الاستفادة من الوظائف التي تقدمها Aspose.Tasks، يمكن للمطورين معالجة بيانات المشروع بكفاءة لتلبية المتطلبات المختلفة.
## الأسئلة الشائعة
### هل يستطيع Aspose.Tasks التعامل مع هياكل المشروع المعقدة؟
نعم، يقدم Aspose.Tasks دعمًا شاملاً لهياكل المشاريع المعقدة، مما يسمح للمستخدمين بإدارة المهام والموارد والسمات بسلاسة.
### هل Aspose.Tasks متوافق مع أحدث إصدارات Microsoft Project؟
يتم تحديث Aspose.Tasks بانتظام لضمان التوافق مع أحدث إصدارات Microsoft Project، مما يوفر للمستخدمين حلاً موثوقًا لإدارة المشاريع.
### هل يدعم Aspose.Tasks التطوير عبر الأنظمة الأساسية؟
نعم، يمكن للمطورين الاستفادة من Aspose.Tasks لـ Java عبر منصات مختلفة، مما يجعله خيارًا متعدد الاستخدامات لتطبيقات إدارة المشاريع.
### هل يمكنني دمج Aspose.Tasks مع مكتبات Java الأخرى؟
بالتأكيد، يمكن دمج Aspose.Tasks بسلاسة مع مكتبات Java الأخرى لتحسين الوظائف وتبسيط عمليات التطوير.
### هل يتوفر الدعم الفني لمستخدمي Aspose.Tasks؟
نعم، يمكن للمستخدمين الوصول إلى الدعم الفني من خلال منتدى Aspose.Tasks، حيث يمكنهم طلب المساعدة والتفاعل مع المجتمع.