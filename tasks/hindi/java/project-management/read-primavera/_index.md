---
date: 2025-12-28
description: Aspose.Tasks for Java का उपयोग करके Primavera XML फ़ाइलों को MS Project
  में पढ़ना सीखें, जिससे सहज डेटा एक्सचेंज और बेहतर प्रोजेक्ट प्रबंधन संभव हो।
linktitle: Read Project from Primavera in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java के साथ Primavera XML को MS Project में कैसे पढ़ें
url: /hi/java/project-management/read-primavera/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Read MS Project from Primavera with Aspose.Tasks for Java

## Introduction
आधुनिक प्रोजेक्ट मैनेजमेंट में, टूल्स के बीच डेटा को बिना किसी विवरण के नुकसान के स्थानांतरित करना अत्यंत आवश्यक है। यह ट्यूटोरियल आपको **Primavera XML** फ़ाइलों को पढ़ने और उन्हें Aspose.Tasks for Java का उपयोग करके Microsoft Project में इम्पोर्ट करने का तरीका दिखाता है। अंत तक, आप Primavera‑विशिष्ट टास्क प्रॉपर्टीज़ निकाल सकेंगे, जिससे क्रॉस‑प्लेटफ़ॉर्म विश्लेषण सरल और प्रभावी बन जाएगा।

## Quick Answers
- **Aspose.Tasks for Java क्या करता है?** यह कई प्रोजेक्ट फ़ाइल फ़ॉर्मेट्स को पढ़ता और लिखता है, जिसमें Primavera XML और Microsoft Project (MPP) शामिल हैं।  
- **क्या मुझे लाइसेंस चाहिए?** मूल्यांकन के लिए एक मुफ्त ट्रायल काम करता है; उत्पादन उपयोग के लिए लाइसेंस आवश्यक है।  
- **कौन सा Java संस्करण समर्थित है?** Java 8 या उससे ऊपर का संस्करण आवश्यक है।  
- **क्या मैं Primavera XML के अलावा अन्य फ़ॉर्मेट पढ़ सकता हूँ?** हाँ, Aspose.Tasks MPP, XML और कई अन्य फ़ॉर्मेट्स को सपोर्ट करता है।  
- **क्या यह तरीका बड़े एंटरप्राइज़ प्रोजेक्ट्स के लिए उपयुक्त है?** बिल्कुल—Aspose.Tasks को हाई‑परफ़ॉर्मेंस, एंटरप्राइज़‑ग्रेड परिदृश्यों के लिए डिज़ाइन किया गया है।

## What is read primavera xml?
Primavera XML को पढ़ना का अर्थ है Oracle Primavera P6 से एक्सपोर्ट की गई XML फ़ाइल को पार्स करना, जिससे प्रोजेक्ट शेड्यूल डेटा—टास्क, अवधि, रिसोर्सेज़, और Primavera‑विशिष्ट एट्रिब्यूट्स—निकाले जा सकें और उन्हें Microsoft Project जैसे अन्य टूल्स द्वारा उपयोग किया जा सके।

## Why use Aspose.Tasks for Java to read primavera xml?
- **पूर्ण फ़िडेलिटी:** सभी Primavera‑विशिष्ट प्रॉपर्टीज़ संरक्षित रहती हैं।  
- **कोई बाहरी डिपेंडेंसी नहीं:** शुद्ध Java लाइब्रेरी, Primavera या MS Project की इंस्टॉलेशन की आवश्यकता नहीं।  
- **स्केलेबल:** हजारों टास्क वाले बड़े प्रोजेक्ट्स को भी कुशलता से संभालता है।  
- **क्रॉस‑प्लेटफ़ॉर्म:** Windows, Linux, और macOS पर काम करता है।

## Prerequisites
शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
1. **Java Development Kit (JDK)** – Java 8 या उससे नया स्थापित हो।  
2. **Aspose.Tasks for Java** – इसे [here](https://releases.aspose.com/tasks/java/) से डाउनलोड करें।  
3. एक Primavera XML फ़ाइल (उदाहरण के लिए `PrimaveraProject.xml`) जिसे आप पढ़ना चाहते हैं।

## How to read project file java with Aspose.Tasks?
नीचे चरण‑दर‑चरण गाइड दिया गया है जो पूरी प्रक्रिया को समझाता है।

### Import Packages
```java
import com.aspose.tasks.PrimaveraReadOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeDelta;
```

### Step 1: Set up Data Directory
```java
String dataDir = "Your Data Directory";
```
`"Your Data Directory"` को उस पूर्ण पाथ से बदलें जहाँ आपका Primavera XML फ़ाइल स्थित है।

### Step 2: Read Project from Primavera XML
```java
PrimaveraReadOptions options = new PrimaveraReadOptions();
options.setProjectUid(3883);
Project project = new Project(dataDir + "PrimaveraProject.xml", options);
```
`"PrimaveraProject.xml"` को अपने Primavera एक्सपोर्ट की वास्तविक फ़ाइलनाम से अपडेट करें।

### Step 3: Iterate Through Tasks and Retrieve Primavera‑Specific Properties
```java
for (Task task : project.enumerateAllChildTasks()) {
    System.out.println("Task '" + task.getName() + "'");
    
    if (task.isSummary()) {
        System.out.println("WBS Sequence number: " + task.getPrimaveraProperties().getSequenceNumber());
    } else {
        System.out.println("Task ActivityId: " + task.getPrimaveraProperties().getActivityId());
    }
    
    System.out.println("Activity Type: " + task.getPrimaveraProperties().getActivityType());
    System.out.println("Duration Type: " + task.getPrimaveraProperties().getDurationType());
    System.out.println("Percent Complete Type: " + task.getPrimaveraProperties().getPercentCompleteType());
    System.out.println("Original Duration: " + TimeDelta.fromMilliseconds(task.getDuration().getTimeSpan()).getTotalHours());
    System.out.println("At Complete Duration: " +
            (TimeDelta.fromMilliseconds(task.getActualDuration().getTimeSpan()).getTotalHours() + TimeDelta.fromMilliseconds(task.getRemainingDuration().getTimeSpan()).getTotalHours()));
    System.out.println("Duration % Complete: " + task.getPrimaveraProperties().getDurationPercentComplete());
    System.out.println("Physical % Complete: " + task.getPrimaveraProperties().getPhysicalPercentComplete());
    
    System.out.println("Task RemainingEarlyStart: " + task.getPrimaveraProperties().getRemainingEarlyStart());
    System.out.println("Task RemainingEarlyFinish: " + task.getPrimaveraProperties().getRemainingEarlyFinish());
    
    System.out.println("Actual costs:");
    System.out.println(task.getPrimaveraProperties().getActualExpenseCost() + ", "
                    + task.getPrimaveraProperties().getActualLaborCost() + ", "
                    + task.getPrimaveraProperties().getActualMaterialCost() + ", "
                    + task.getPrimaveraProperties().getActualNonlaborCost() + ", Total: "
                    + task.getPrimaveraProperties().getActualTotalCost());
    
    System.out.println("Labor Units:");
    System.out.println(task.getPrimaveraProperties().getActualLaborUnits() + ", " +
            task.getPrimaveraProperties().getActualNonLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingNonLaborUnits());
    
    System.out.println("Units % Complete: " + task.getPrimaveraProperties().getUnitsPercentComplete());
}
```
यह लूप प्रत्येक टास्क की Primavera‑विशिष्ट विवरणों को प्रिंट करता है, जैसे Activity ID, WBS सीक्वेंस, ड्यूरेशन टाइप्स, कॉस्ट ब्रेकडाउन आदि।

## Common Issues and Solutions
- **File not found error:** सुनिश्चित करें कि `dataDir` के अंत में पाथ सेपरेटर (`/` या `\\`) है और XML फ़ाइलनाम सही है।  
- **Missing Primavera properties:** जांचें कि XML को सभी आवश्यक फ़ील्ड्स के साथ एक्सपोर्ट किया गया था; पुराने Primavera संस्करण कुछ एट्रिब्यूट्स को छोड़ सकते हैं।  
- **Performance on large files:** बड़े प्रोजेक्ट्स (दसियों हजार टास्क) के लिए JVM हीप साइज (`-Xmx2g` या उससे अधिक) बढ़ाने पर विचार करें।

## Frequently Asked Questions
### Q: क्या मैं Aspose.Tasks for Java का उपयोग करके टास्क की Primavera‑विशिष्ट प्रॉपर्टीज़ को संशोधित कर सकता हूँ?
A: हाँ, Aspose.Tasks for Java आवश्यकतानुसार Primavera‑विशिष्ट प्रॉपर्टीज़ को बदलने के लिए API प्रदान करता है।

### Q: क्या Aspose.Tasks for Java अन्य प्रोजेक्ट फ़ाइल फ़ॉर्मेट्स को पढ़ने का समर्थन करता है?
A: हाँ, Aspose.Tasks for Java MPP, XML और Primavera XML सहित विभिन्न प्रोजेक्ट फ़ाइल फ़ॉर्मेट्स को पढ़ सकता है।

### Q: क्या Aspose.Tasks for Java एंटरप्राइज़‑लेवल प्रोजेक्ट मैनेजमेंट एप्लिकेशन्स के लिए उपयुक्त है?
A: बिल्कुल, Aspose.Tasks for Java मजबूत फीचर्स और स्केलेबिलिटी प्रदान करता है, जिससे यह एंटरप्राइज़‑लेवल प्रोजेक्ट मैनेजमेंट एप्लिकेशन्स के लिए उपयुक्त है।

### Q: क्या मैं Aspose.Tasks for Java का उपयोग करके Primavera प्रोजेक्ट्स से रिसोर्स जानकारी निकाल सकता हूँ?
A: हाँ, Aspose.Tasks for Java आपको Primavera प्रोजेक्ट्स से टास्क विवरणों के साथ रिसोर्स जानकारी भी निकालने की अनुमति देता है।

### Q: Aspose.Tasks for Java के लिए अतिरिक्त सपोर्ट या डॉक्यूमेंटेशन कहाँ मिल सकता है?
A: आप विस्तृत डॉक्यूमेंटेशन और सपोर्ट फ़ोरम [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/) पेज पर पा सकते हैं।

## Conclusion
अब आप **Primavera XML** फ़ाइलों को पढ़ना और Aspose.Tasks का उपयोग करके Java एप्लिकेशन में विस्तृत टास्क जानकारी निकालना सीख चुके हैं। यह क्षमता Primavera और Microsoft Project के बीच अंतर को पाटती है, जिससे आपको सभी प्लेटफ़ॉर्म पर पूर्ण दृश्यता मिलती है और कुल प्रोजेक्ट मैनेजमेंट दक्षता बढ़ती है।

---

**Last Updated:** 2025-12-28  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}