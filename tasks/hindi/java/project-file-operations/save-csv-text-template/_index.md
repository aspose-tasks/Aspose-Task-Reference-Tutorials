---
date: 2025-12-21
description: Aspose.Tasks for Java का उपयोग करके प्रोजेक्ट को टेम्पलेट के रूप में
  सहेजना, MPP को CSV में निर्यात करना, और MPP को टेक्स्ट में बदलना सीखें।
linktitle: Save Project as Template, CSV, and Text with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java के साथ प्रोजेक्ट को टेम्पलेट, CSV और टेक्स्ट के रूप में
  सहेजें
url: /hi/java/project-file-operations/save-csv-text-template/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspise.Tasks के साथ प्रोजेक्ट को टेम्प्लेट, CSV, और टेक्स्ट के रूप में सहेजें

## परिचय
इस ट्यूटोरियल में आप **प्रोजेक्ट को टेम्प्लेट के रूप में कैसे सहेजें** और साथ ही Aspose.Tasks लाइब्रेरी फॉर जावा का उपयोग करके अपने Microsoft Project (MPP) फ़ाइलों को CSV और प्लेन‑टेक्स्ट फ़ॉर्मेट में कैसे एक्सपोर्ट करें, यह जानेंगे। चाहे आपको एक पुन: उपयोग योग्य प्रोजेक्ट टेम्प्लेट बनाना हो, एनालिटिक्स के लिए CSV रिपोर्ट जेनरेट करनी हो, या इंटीग्रेशन के लिए साधारण टेक्स्ट एक्सट्रैक्ट बनाना हो, ये स्टेप्स आपको प्रक्रिया को जल्दी और प्रभावी ढंग से पूरा करने में मदद करेंगे।

## त्वरित उत्तर
- **क्या मैं MPP को CSV में निर्यात कर सकता हूँ?** हाँ – `project.save(..., SaveFileFormat.CSV)` का उपयोग करें।  
- **टेक्स्ट को कैसे निर्यात करें?** `SaveFileFormat.TEXT` के साथ सहेजें।  
- **“save project as template” क्या करता है?** यह एक `.mpt` फ़ाइल बनाता है जो वास्तविक और बेसलाइन मानों को हटाकर पुन: उपयोग के लिए तैयार करता है।  
- **क्या मुझे लाइसेंस चाहिए?** ट्रायल उपलब्ध है; प्रोडक्शन के लिए एक कमर्शियल लाइसेंस आवश्यक है।  
- **कौन सा जावा संस्करण आवश्यक है?** Java 8+ समर्थित है।

## “save project as template” क्या है?
प्रोजेक्ट को टेम्प्लेट (`.mpt`) के रूप में सहेजना संरचना, टास्क हायरार्की और रिसोर्स असाइनमेंट्स को कैप्चर करता है, जबकि वास्तविक स्टार्ट/फ़िनिश डेट और बेसलाइन डेटा को हटा देता है। यह टेम्प्लेट कई नए प्रोजेक्ट्स में एक मानक लेआउट को पुन: उपयोग करने के लिए आदर्श बनाता है।

## क्यों उपयोग करें Aspose.Tasks फॉर जावा?
Aspose.Tasks आपको Microsoft Project फ़ाइलों को बिना Microsoft Project इंस्टॉल किए मैनीपुलेट करने देता है। यह **MPP को CSV में निर्यात**, **टेक्स्ट निर्यात**, और **MPP को CSV में बदलने** जैसी सुविधाएँ शुद्ध जावा कोड से प्रदान करता है, जो सर्वर‑साइड ऑटोमेशन, CI पाइपलाइन या डेस्कटॉप यूटिलिटीज़ के लिए एकदम उपयुक्त है।

## पूर्वापेक्षाएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास:

1. Java Development Kit (JDK) 8 या उससे ऊपर स्थापित हो।  
2. Aspose.Tasks फॉर जावा लाइब्रेरी आपके प्रोजेक्ट में जोड़ी गई हो। इसे [here](https://releases.aspose.com/tasks/java/) से डाउनलोड करें।  
3. जावा सिंटैक्स और Maven/Gradle प्रोजेक्ट सेटअप की बुनियादी समझ हो।

## पैकेज आयात करें
सबसे पहले, अपने जावा सोर्स फ़ाइल में आवश्यक क्लासेस को इम्पोर्ट करें:

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

## प्रोजेक्ट को CSV के रूप में सहेजें (MPP को CSV में निर्यात करें)
एक MPP फ़ाइल को CSV में निर्यात करना Excel या BI टूल्स में डेटा विश्लेषण के लिए उपयोगी होता है।

### चरण 1: प्रोजेक्ट लोड करें
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### चरण 2: CSV के रूप में सहेजें
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```

## प्रोजेक्ट को टेक्स्ट के रूप में सहेजें (टेक्स्ट निर्यात कैसे करें)
यदि आपको टास्क, रिसोर्स या असाइनमेंट्स का प्लेन‑टेक्स्ट प्रतिनिधित्व चाहिए, तो प्रोजेक्ट को टेक्स्ट फ़ाइल के रूप में सहेजें।

### चरण 1: प्रोजेक्ट लोड करें
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### चरण 2: टेक्स्ट के रूप में सहेजें
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```

## प्रोजेक्ट को टेम्प्लेट के रूप में सहेजें (प्रोजेक्ट टेम्प्लेट जावा बनाएं)
एक पुन: उपयोग योग्य टेम्प्लेट बनाना वास्तविक डेट और बेसलाइन को हटाकर एक साफ़ स्केलेटन प्रदान करता है, जिसे नए प्रोजेक्ट्स में उपयोग किया जा सकता है।

### चरण 1: प्रोजेक्ट लोड करें
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### चरण 2: टेम्प्लेट विकल्प सेट करें
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```

### चरण 3: टेम्प्लेट के रूप में सहेजें
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## सामान्य समस्याएँ और सुझाव
- **File Not Found:** सुनिश्चित करें कि `YourProject.mpp` का पाथ सही है या एक एब्सॉल्यूट पाथ उपयोग करें।  
- **License Exceptions:** वैध लाइसेंस न होने पर लाइब्रेरी इवैल्यूएशन मोड में चलती है और वॉटरमार्क जोड़ सकती है। कोड में जल्दी लाइसेंस लागू करें (`License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`)।  
- **Large Projects:** बहुत बड़े MPP फ़ाइलों के लिए JVM हीप साइज बढ़ाएँ (`-Xmx2g`) ताकि `OutOfMemoryError` से बचा जा सके।

## निष्कर्ष
हमने **प्रोजेक्ट को टेम्प्लेट के रूप में कैसे सहेजें**, साथ ही **MPP को CSV में निर्यात** और **MPP को टेक्स्ट में बदलना** Aspose.Tasks फॉर जावा का उपयोग करके कवर किया। ये क्षमताएँ आपको प्रोजेक्ट डेटा को ऑटोमेट करने, पुन: उपयोग योग्य टेम्प्लेट जेनरेट करने, और प्रोजेक्ट जानकारी को अन्य सिस्टम्स में इंटीग्रेट करने की अनुमति देती हैं—बिना Microsoft Project इंस्टॉल किए।

## अक्सर पूछे जाने वाले प्रश्न
### Q: क्या Aspose.Tasks फॉर जावा जटिल प्रोजेक्ट फ़ाइलों को संभाल सकता है?
A: बिल्कुल! Aspose.Tasks फॉर जावा विभिन्न जटिलता वाले प्रोजेक्ट्स को आसानी से हैंडल करता है और Microsoft Project फ़ाइल फ़ॉर्मेट्स के लिए व्यापक समर्थन प्रदान करता है।  
### Q: क्या Aspose.Tasks फॉर जावा के लिए एक ट्रायल संस्करण उपलब्ध है?
A: हाँ, आप Aspose.Tasks फॉर जावा का मुफ्त ट्रायल [here](https://releases.aspose.com/) से प्राप्त कर सकते हैं।  
### Q: मैं Aspose.Tasks फॉर जावा के लिए सपोर्ट कहाँ पा सकता हूँ?
A: आप किसी भी सहायता या प्रश्नों के लिए [Aspose.Tasks फ़ोरम](https://forum.aspose.com/c/tasks/15) पर जा सकते हैं।  
### Q: क्या मैं Aspose.Tasks फॉर जावा के लिए एक टेम्पररी लाइसेंस खरीद सकता हूँ?
A: हाँ, आप पूर्ण लाइब्रेरी की क्षमता का मूल्यांकन करने के लिए [here](https://purchase.aspose.com/temporary-license/) से एक टेम्पररी लाइसेंस खरीद सकते हैं।  
### Q: क्या Aspose.Tasks फॉर जावा विभिन्न ऑपरेटिंग सिस्टम्स के साथ संगत है?
A: हाँ, Aspose.Tasks फॉर जावा Windows, macOS, और Linux सहित विभिन्न ऑपरेटिंग सिस्टम्स के साथ संगत है।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}

---

**अंतिम अपडेट:** 2025-12-21  
**परीक्षित संस्करण:** Aspose.Tasks for Java 24.12 (latest)  
**लेखक:** Aspose