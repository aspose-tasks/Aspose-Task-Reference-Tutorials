---
date: 2026-02-23
description: Aspose.Tasks for Java का उपयोग करके प्रोजेक्ट की प्रारंभ तिथि सेट करना,
  कार्य की अवधि निर्धारित करना और प्रोजेक्ट को MPP के रूप में सहेजना सीखें। पैरेंट
  और चाइल्ड टास्क को प्रभावी ढंग से प्रबंधित करें।
linktitle: Set Project Start Date and Manage Parent and Child Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks में प्रोजेक्ट की प्रारंभ तिथि निर्धारित करें और पैरेंट तथा चाइल्ड
  कार्यों का प्रबंधन करें
url: /hi/java/task-properties/parent-child-tasks/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में प्रोजेक्ट की शुरूआती तिथि सेट करें और पैरेंट व चाइल्ड टास्क प्रबंधित करें

## Introduction
प्रभावी टास्क संगठन सफल प्रोजेक्ट मैनेजमेंट की रीढ़ है, और **प्रोजेक्ट की शुरूआती तिथि सेट करना** सही ढंग से एक सुव्यवस्थित शेड्यूल की ओर पहला कदम है। इस ट्यूटोरियल में आप देखेंगे कि कैसे **प्रोजेक्ट की शुरूआती तिथि सेट करें**, टास्क की अवधि कॉन्फ़िगर करें, और Aspose.Tasks for Java का उपयोग करके पैरेंट‑चाइल्ड संबंधों का प्रबंधन करें। अंत तक, आप **प्रोजेक्ट को MPP के रूप में सहेजने**, टास्क पूर्णता प्रतिशत अपडेट करने, और वास्तविक दुनिया के किसी भी परिदृश्य के अनुसार टास्क प्रॉपर्टीज़ को कस्टमाइज़ करने के लिए तैयार होंगे।

## Quick Answers
- **मैं प्रोजेक्ट की शुरूआती तिथि कैसे सेट करूँ?** `Project` ऑब्जेक्ट को इनिशियलाइज़ करने के बाद `proj.set(Prj.START_DATE, startDate);` का उपयोग करें।  
- **क्या मैं पैरेंट टास्क के अंतर्गत चाइल्ड टास्क जोड़ सकता हूँ?** हाँ – `parentTask.getChildren().add("Child Task")` कॉल करें।  
- **Aspose.Tasks फाइल किस फॉर्मेट में सहेजता है?** `SaveFileFormat.Mpp` का उपयोग करके **प्रोजेक्ट को MPP के रूप में सहेजें**।  
- **मैं टास्क पूर्णता कैसे अपडेट करूँ?** टास्क ऑब्जेक्ट पर `Tsk.PERCENT_COMPLETE` सेट करें।  
- **मैं अस्थायी लाइसेंस कहाँ प्राप्त कर सकता हूँ?** FAQs में लिंक किए गए अस्थायी‑लाइसेंस पेज पर जाएँ।

## Prerequisites
ट्यूटोरियल शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित प्री‑रिक्विज़िट्स मौजूद हैं:
- जावा प्रोग्रामिंग की बुनियादी समझ।  
- Aspose.Tasks for Java लाइब्रेरी इंस्टॉल हो। आप इसे [यहाँ](https://releases.aspose.com/tasks/java/) से डाउनलोड कर सकते हैं।  
- आपके सिस्टम पर जावा इंटीग्रेटेड डेवलपमेंट एनवायरनमेंट (IDE) सेट अप हो।

## Import Packages
शुरू करने के लिए, आवश्यक पैकेजेज़ को अपने जावा प्रोजेक्ट में इम्पोर्ट करें। ये पैकेजेज़ Aspose.Tasks for Java की कार्यक्षमताओं के साथ सहज इंटीग्रेशन को सक्षम बनाते हैं।
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.io.IOException;
import java.util.Date;
import java.util.List;
```

## Step 1: Set Project Start Date
प्रोजेक्ट की शुरूआती तिथि और अन्य संबंधित पैरामीटर सेट करके शुरू करें।
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project proj = new Project(dataDir + "Blank2010.mpp");
proj.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
// Additional code for package imports can be added here
double oneDay = 8d * 60d * 60d * 10000000d;
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, 9, 13, 8, 0, 0);
Date startDate = cal.getTime();
proj.set(Prj.START_DATE, startDate);
```

## Step 2: Add Parent Task (Task 1)
"Task 1" नामक एक पैरेंट टास्क बनाएँ और उसकी प्रॉपर्टीज़ कॉन्फ़िगर करें, जिसमें **set task duration** भी शामिल है।
```java
Task task1 = proj.getRootTask().getChildren().add("Task 1");
cal.set(2014, 9, 13, 8, 0, 0);
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, proj.getDuration(29, TimeUnitType.Day));
```

## Step 3: Add Parent Task (Task 2) with Child Tasks
अब, "Task 2" नामक एक और पैरेंट टास्क जोड़ें और चाइल्ड टास्क (Task 3 और Task 4) शामिल करें।
```java
Task task2 = proj.getRootTask().getChildren().add("Task 2");
// Add child tasks to Task 2
Task task3 = task2.getChildren().add("Task 3");
Task task4 = task2.getChildren().add("Task 4");
// Additional configuration for Task 3 and Task 4 can be added here
```

## Step 4: Configure Child Tasks
Task 3 और Task 4 के लिए शुरूआती तिथियाँ, अवधि, और कॉन्स्ट्रेंट्स निर्दिष्ट करें।
```java
// Configure Task 3
cal.set(2014, 9, 15, 8, 0, 0);
task3.set(Tsk.START, cal.getTime());
task3.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task3.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task3.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
// Configure Task 4
cal.set(2014, 9, 17, 8, 0, 0);
task4.set(Tsk.START, cal.getTime());
task4.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task4.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task4.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
```

## Step 5: Update Task Completion Percentage
Task 3 और Task 4 के लिए पूर्णता प्रतिशत समायोजित करें – यही **टास्क पूर्णता अपडेट** करने का तरीका है।
```java
task3.set(Tsk.PERCENT_COMPLETE, 50);
task4.set(Tsk.PERCENT_COMPLETE, 70);
```

## Step 6: Save the Project
अंत में, लागू किए गए बदलावों के साथ **प्रोजेक्ट को MPP के रूप में सहेजें**।
```java
proj.save(dataDir + "ProjectJava.mpp", SaveFileFormat.Mpp);
```

यह चरण‑दर‑चरण गाइड दिखाता है कि कैसे Aspose.Tasks for Java का उपयोग करके पैरेंट और चाइल्ड टास्क को प्रभावी रूप से प्रबंधित किया जाए। अपने प्रोजेक्ट की आवश्यकताओं के अनुसार विभिन्न कॉन्फ़िगरेशन के साथ प्रयोग करें।

## Why Customize Task Properties?
स्टार्ट डेट, ड्यूरेशन, कॉन्स्ट्रेंट्स, और पूर्णता प्रतिशत जैसी टास्क प्रॉपर्टीज़ को कस्टमाइज़ करने से आपको शेड्यूल व्यवहार पर सूक्ष्म नियंत्रण मिलता है। चाहे आपको टास्क को रिसोर्स उपलब्धता के साथ संरेखित करना हो या बिज़नेस नियम लागू करने हों, Aspose.Tasks आपको प्रोग्रामेटिकली **टास्क प्रॉपर्टीज़ कस्टमाइज़** करने की सुविधा देता है।

## Common Issues and Solutions
| Issue | Solution |
|-------|----------|
| **Start date not applied** | सुनिश्चित करें कि आप `proj.set(Prj.START_DATE, …)` **Project** ऑब्जेक्ट बनाते समय और टास्क जोड़ने से पहले कॉल कर रहे हैं। |
| **Child tasks inherit wrong constraints** | प्रत्येक चाइल्ड की `ConstraintType` और `ConstraintDate` को स्पष्ट रूप से सेट करें, जैसा कि Step 4 में दिखाया गया है। |
| **Saved file cannot be opened in MS Project** | जाँचें कि आप नवीनतम Aspose.Tasks संस्करण का उपयोग कर रहे हैं और `SaveFileFormat.Mpp` के साथ सहेजें। |
| **Percentage not reflecting in UI** | `Tsk.PERCENT_COMPLETE` सेट करने के बाद, यदि आपको पुनः गणना की तिथियों की आवश्यकता है तो `proj.calculateTaskSchedule()` कॉल करें। |

## FAQs
### क्या Aspose.Tasks for Java विभिन्न प्रोजेक्ट फाइल फॉर्मेट्स के साथ संगत है?
हाँ, Aspose.Tasks for Java विभिन्न प्रोजेक्ट फाइल फॉर्मेट्स, जैसे MPP और XML, को सपोर्ट करता है।

### क्या मैं इस ट्यूटोरियल में कवर किए गए से आगे टास्क प्रॉपर्टीज़ को कस्टमाइज़ कर सकता हूँ?
बिल्कुल! Aspose.Tasks for Java टास्क प्रॉपर्टीज़ के लिए विस्तृत कस्टमाइज़ेशन विकल्प प्रदान करता है।

### क्या Aspose.Tasks के लिए कोई कम्युनिटी फोरम है जहाँ मैं सहायता ले सकूँ?
हाँ, आप कम्युनिटी सपोर्ट के लिए [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) पर जा सकते हैं।

### मैं Aspose.Tasks for Java के लिए अस्थायी लाइसेंस कैसे प्राप्त करूँ?
आप अस्थायी लाइसेंस [यहाँ](https://purchase.aspose.com/temporary-license/) से प्राप्त कर सकते हैं।

### Aspose.Tasks for Java की व्यापक डॉक्यूमेंटेशन कहाँ मिल सकती है?
डॉक्यूमेंटेशन उपलब्ध है [यहाँ](https://reference.aspose.com/tasks/java/)।

**Additional Q&A**

**Q: मैं प्रोग्रामेटिकली अस्थायी लाइसेंस कैसे प्राप्त करूँ?**  
A: अस्थायी लाइसेंस फ़ाइल को इस प्रकार लोड करें: `License license = new License(); license.setLicense("Aspose.Tasks.lic");`।

**Q: क्या मैं डिफ़ॉल्ट टास्क ड्यूरेशन यूनिट बदल सकता हूँ?**  
A: हाँ – `proj.getDuration(value, TimeUnitType.YourChoice)` में `TimeUnitType` आर्ग्यूमेंट को संशोधित करें।

**Q: `SaveFileFormat.Mpp` उपयोग करने के लिए Aspose.Tasks का कौन सा संस्करण आवश्यक है?**  
A: सभी हालिया संस्करण (2022‑2026) MPP के रूप में सहेजने का समर्थन करते हैं; किसी भी ब्रेकिंग चेंज के लिए रिलीज़ नोट्स देखें।

---

**Last Updated:** 2026-02-23  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}