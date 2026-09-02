---
date: 2026-04-24
description: जानें कि कैसे Aspose Tasks Java का उपयोग करके Primavera XML को MS Project
  में इम्पोर्ट किया जाए, जिससे सहज डेटा एक्सचेंज और बेहतर प्रोजेक्ट मैनेजमेंट संभव
  हो सके।
keywords:
- aspose tasks java
- import xml ms project
- java read project
- java project xml
linktitle: Aspose.Tasks में Primavera से प्रोजेक्ट पढ़ें
second_title: Aspose.Tasks Java API
title: aspose tasks java – Primavera XML को MS Project में पढ़ें
url: /hi/java/project-management/read-primavera/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java के साथ Primavera से MS Project पढ़ें

## परिचय
आज की तेज़ गति वाली प्रोजेक्ट‑मैनेजमेंट दुनिया में, आपको अक्सर Primavera P6 और Microsoft Project के बीच शेड्यूल को बिना किसी विवरण को खोए स्थानांतरित करने की आवश्यकता होती है। यह ट्यूटोरियल दिखाता है **Primavera XML** फ़ाइलों को कैसे पढ़ें और **aspose tasks java** का उपयोग करके उन्हें MS Project में इम्पोर्ट करें। गाइड के अंत तक आप Primavera‑विशिष्ट टास्क प्रॉपर्टीज़ को एक Java एप्लिकेशन में खींच सकेंगे, जिससे विश्लेषण, रिपोर्टिंग या आगे की ऑटोमेशन के लिए एक ही सत्य स्रोत मिल सके।

## त्वरित उत्तर
- **Aspose.Tasks for Java क्या करता है?** यह कई प्रोजेक्ट फ़ाइल फ़ॉर्मेट को पढ़ता और लिखता है, जिसमें Primavera XML और Microsoft Project (MPP) शामिल हैं।  
- **क्या मुझे लाइसेंस चाहिए?** मूल्यांकन के लिए एक मुफ्त ट्रायल काम करता है; उत्पादन उपयोग के लिए लाइसेंस आवश्यक है।  
- **कौन सा Java संस्करण समर्थित है?** Java 8 या उससे ऊपर की आवश्यकता है।  
- **क्या मैं Primavera XML के अलावा अन्य फ़ॉर्मेट इम्पोर्ट कर सकता हूँ?** हाँ, aspose tasks java MPP, XML और कई अन्य को भी सपोर्ट करता है।  
- **क्या यह तरीका बड़े एंटरप्राइज़ प्रोजेक्ट्स के लिए उपयुक्त है?** बिल्कुल—Aspose.Tasks उच्च‑प्रदर्शन, एंटरप्राइज़‑ग्रेड परिदृश्यों के लिए डिज़ाइन किया गया है।

## aspose tasks java – Primavera XML पढ़ना
Primavera XML पढ़ना का अर्थ है Oracle Primavera P6 से एक्सपोर्ट की गई XML को पार्स करना ताकि प्रोजेक्ट शेड्यूल डेटा—टास्क, अवधि, संसाधन, और Primavera‑विशिष्ट एट्रिब्यूट्स—प्राप्त किया जा सके, जिससे इसे Microsoft Project जैसे अन्य टूल्स द्वारा उपयोग किया जा सके।

## Primavera XML पढ़ने के लिए Aspose.Tasks for Java का उपयोग क्यों करें?
- **पूर्ण सटीकता:** सभी Primavera‑विशिष्ट प्रॉपर्टीज़ संरक्षित रहती हैं।  
- **कोई बाहरी निर्भरताएँ नहीं:** शुद्ध Java लाइब्रेरी, Primavera या MS Project इंस्टॉलेशन की आवश्यकता नहीं।  
- **स्केलेबल:** हजारों टास्क वाले बड़े प्रोजेक्ट्स को कुशलता से संभालता है।  
- **क्रॉस‑प्लेटफ़ॉर्म:** Windows, Linux और macOS पर काम करता है।

## पूर्वापेक्षाएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
1. **Java Development Kit (JDK)** – Java 8 या उससे नया स्थापित हो।  
2. **Aspose.Tasks for Java** – इसे [here](https://releases.aspose.com/tasks/java/) से डाउनलोड करें।  
3. एक Primavera XML फ़ाइल (उदा., `PrimaveraProject.xml`) जिसे आप पढ़ना चाहते हैं।

## Aspose.Tasks के साथ Java में प्रोजेक्ट फ़ाइल कैसे पढ़ें?
नीचे एक चरण‑दर‑चरण गाइड है जो आपको पूरी प्रक्रिया से गुजराता है।

### इम्पोर्ट पैकेज
```java
import com.aspose.tasks.PrimaveraReadOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeDelta;
```

### चरण 1: डेटा डायरेक्टरी सेट करें
```java
String dataDir = "Your Data Directory";
```
`"Your Data Directory"` को उस पूर्ण पथ से बदलें जहाँ आपका Primavera XML फ़ाइल स्थित है।

### चरण 2: Primavera XML से प्रोजेक्ट पढ़ें
```java
PrimaveraReadOptions options = new PrimaveraReadOptions();
options.setProjectUid(3883);
Project project = new Project(dataDir + "PrimaveraProject.xml", options);
```
`"PrimaveraProject.xml"` को अपने Primavera एक्सपोर्ट की वास्तविक फ़ाइलनाम से अपडेट करें।

### चरण 3: टास्क्स पर इटररेट करें और Primavera‑विशिष्ट प्रॉपर्टीज़ प्राप्त करें
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
यह लूप प्रत्येक टास्क के Primavera‑विशिष्ट विवरण प्रिंट करता है, जैसे Activity ID, WBS क्रम, अवधि प्रकार, लागत विवरण, आदि।

## सामान्य समस्याएँ और समाधान
- **फ़ाइल नहीं मिली त्रुटि:** सुनिश्चित करें कि `dataDir` पाथ सेपरेटर (`/` या `\\`) पर समाप्त होता है और XML फ़ाइलनाम सही है।  
- **Primavera प्रॉपर्टीज़ गायब:** सुनिश्चित करें कि XML सभी आवश्यक फ़ील्ड के साथ एक्सपोर्ट किया गया है; पुराने Primavera संस्करण कुछ एट्रिब्यूट्स को छोड़ सकते हैं।  
- **बड़ी फ़ाइलों पर प्रदर्शन:** दसियों हज़ार टास्क वाले प्रोजेक्ट्स के लिए JVM हीप साइज (`-Xmx2g` या अधिक) बढ़ाने पर विचार करें।

## अक्सर पूछे जाने वाले प्रश्न
### Q: क्या मैं Aspose.Tasks for Java का उपयोग करके टास्क्स की Primavera‑विशिष्ट प्रॉपर्टीज़ को संशोधित कर सकता हूँ?
A: हाँ, Aspose.Tasks for Java आवश्यकतानुसार टास्क्स की Primavera‑विशिष्ट प्रॉपर्टीज़ को संशोधित करने के लिए API प्रदान करता है।

### Q: क्या Aspose.Tasks for Java अन्य प्रोजेक्ट फ़ाइल फ़ॉर्मेट पढ़ने का समर्थन करता है?
A: हाँ, Aspose.Tasks for Java विभिन्न प्रोजेक्ट फ़ाइल फ़ॉर्मेट पढ़ने का समर्थन करता है, जिसमें MPP, XML, और Primavera XML शामिल हैं।

### Q: क्या Aspose.Tasks for Java एंटरप्राइज़‑स्तर के प्रोजेक्ट मैनेजमेंट एप्लिकेशन के लिए उपयुक्त है?
A: बिल्कुल, Aspose.Tasks for Java मजबूत फीचर्स और स्केलेबिलिटी प्रदान करता है, जिससे यह एंटरप्राइज़‑स्तर के प्रोजेक्ट मैनेजमेंट एप्लिकेशन के लिए उपयुक्त बनता है।

### Q: क्या मैं Aspose.Tasks for Java का उपयोग करके Primavera प्रोजेक्ट्स से रिसोर्स जानकारी निकाल सकता हूँ?
A: हाँ, Aspose.Tasks for Java आपको Primavera प्रोजेक्ट्स से टास्क विवरण के साथ रिसोर्स जानकारी निकालने की अनुमति देता है।

### Q: मैं Aspose.Tasks for Java के लिए अतिरिक्त समर्थन या दस्तावेज़ीकरण कहाँ पा सकता हूँ?
A: आप व्यापक दस्तावेज़ीकरण और समर्थन के लिए फ़ोरम [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/) पेज पर पा सकते हैं।

## निष्कर्ष
आपने अब **Primavera XML** फ़ाइलों को पढ़ना और **aspose tasks java** का उपयोग करके विस्तृत टास्क जानकारी को Java एप्लिकेशन में खींचना सीख लिया है। यह क्षमता Primavera और Microsoft Project के बीच अंतर को पाटती है, जिससे आपको प्लेटफ़ॉर्म्स के बीच पूर्ण दृश्यता मिलती है और समग्र प्रोजेक्ट‑मैनेजमेंट दक्षता बढ़ती है।

**अंतिम अपडेट:** 2026-04-24  
**परीक्षण किया गया:** Aspose.Tasks for Java 24.11  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}