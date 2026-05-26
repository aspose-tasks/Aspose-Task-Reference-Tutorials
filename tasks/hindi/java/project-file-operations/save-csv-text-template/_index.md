---
date: 2026-05-26
description: Aspose.Tasks for Java का उपयोग करके MPP को CSV में निर्यात करना, प्रोजेक्ट
  को Template के रूप में सहेजना, और MPP को टेक्स्ट में बदलना सीखें।
keywords:
- export mpp to csv
- save project as template
- convert mpp to csv
linktitle: Aspose.Tasks Java के साथ MPP को CSV, टेक्स्ट और Template में निर्यात करें
schemas:
- author: Aspose
  dateModified: '2026-05-26'
  description: Learn how to export MPP to CSV, save project as template, and convert
    MPP to text using Aspose.Tasks for Java.
  headline: Export MPP to CSV, Text & Template with Aspose.Tasks Java
  type: TechArticle
- description: Learn how to export MPP to CSV, save project as template, and convert
    MPP to text using Aspose.Tasks for Java.
  name: Export MPP to CSV, Text & Template with Aspose.Tasks Java
  steps:
  - name: Save as CSV
    text: '`SaveFileFormat.CSV` tells Aspose.Tasks to output the project in CSV format.'
  - name: Save as Text
    text: '`SaveFileFormat.TEXT` instructs the library to generate a plain‑text representation
      of the project.'
  - name: Set Template Options
    text: Use `Project.save` with `SaveFileFormat.MPT` (or `SaveFileFormat.TEMPLATE`)
      to create a template file that strips dates and baselines.
  type: HowTo
- questions:
  - answer: Yes, it fully supports tasks, resources, assignments, baselines, and custom
      fields across all Project versions up to 2024.
    question: Can Aspose.Tasks for Java handle complex, multi‑phase projects?
  - answer: Absolutely – download a free trial from [here](https://releases.aspose.com/).
    question: Is a trial version available?
  - answer: The official support forum is at [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      where staff and community members answer questions.
    question: Where can I get help if I run into problems?
  - answer: Yes, purchase a temporary license at [here](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for short‑term evaluation?
  - answer: It is fully cross‑platform and works on Windows, macOS, and Linux with
      any Java 8+ runtime.
    question: Does Aspose.Tasks run on Linux and macOS?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks Java के साथ MPP को CSV, टेक्स्ट और Template में निर्यात करें
url: /hi/java/project-file-operations/save-csv-text-template/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java के साथ MPP को CSV, टेक्स्ट और टेम्प्लेट में निर्यात करें

## परिचय
इस ट्यूटोरियल में आप **MPP को CSV में निर्यात करने का तरीका**, पुन: उपयोग योग्य प्रोजेक्ट टेम्प्लेट बनाने, और Aspose.Tasks लाइब्रेरी फॉर जावा का उपयोग करके प्लेन‑टेक्स्ट एक्सट्रैक्ट जनरेट करना सीखेंगे। चाहे आप रिपोर्टिंग पाइपलाइन बना रहे हों, प्रोजेक्ट निर्माण को स्वचालित कर रहे हों, या अन्य सिस्टम्स के साथ एकीकरण कर रहे हों, ये चरण आपको एक कच्चे MPP फ़ाइल से आवश्यक आउटपुट तक जल्दी और बिना Microsoft Project स्थापित किए पहुँचाएंगे।

## त्वरित उत्तर
- **क्या मैं MPP को CSV में निर्यात कर सकता हूँ?** हाँ – `project.save("output.csv", SaveFileFormat.CSV)` को कॉल करें।  
- **मैं प्लेन टेक्स्ट में कैसे निर्यात करूँ?** `save` मेथड के साथ `SaveFileFormat.TEXT` का उपयोग करें।  
- **“save project as template” क्या करता है?** यह एक `.mpt` फ़ाइल बनाता है जो तिथियों और बेसलाइन को हटा देता है, केवल स्केलेटन छोड़ता है।  
- **क्या मुझे लाइसेंस चाहिए?** ट्रायल मूल्यांकन के लिए काम करता है; एक व्यावसायिक लाइसेंस मूल्यांकन सीमाओं को हटाता है।  
- **कौन सा Java संस्करण आवश्यक है?** Java 8 या उससे नया पूर्ण रूप से समर्थित है।

## “save project as template” क्या है?
एक प्रोजेक्ट को टेम्प्लेट (`.mpt`) के रूप में सहेजना संरचना, टास्क हायरार्की, और रिसोर्स असाइनमेंट को कैप्चर करता है जबकि वास्तविक प्रारंभ/समाप्ति तिथियों और बेसलाइन डेटा को हटा देता है। यह टेम्प्लेट कई नए प्रोजेक्ट्स में मानक प्रोजेक्ट लेआउट को पुनः उपयोग करने के लिए आदर्श बनाता है। यह सभी कस्टम फ़ील्ड्स, लागत दरें, और असाइनमेंट विवरण को बरकरार रखता है, जिससे टेम्प्लेट किसी भी नए प्रोजेक्ट पर लागू किया जा सकता है बिना आवश्यक कॉन्फ़िगरेशन खोए।

## Aspose.Tasks for Java का उपयोग क्यों करें?
Microsoft Project के बिना सीधे Java से MPP को CSV, टेक्स्ट, या टेम्प्लेट में निर्यात करें। Aspose.Tasks **20+ Microsoft Project संस्करणों** (2000‑2024) का समर्थन करता है और मेमोरी‑कुशल मोड में **500 MB** तक की फ़ाइलें प्रोसेस कर सकता है, जिससे यह सर्वर‑साइड ऑटोमेशन, CI पाइपलाइन, और क्रॉस‑प्लेटफ़ॉर्म यूटिलिटीज़ के लिए आदर्श है।

## पूर्वापेक्षाएँ
- Java Development Kit 8 या उससे ऊपर स्थापित होना चाहिए।  
- Aspose.Tasks for Java लाइब्रेरी को अपने प्रोजेक्ट में जोड़ें – [यहाँ](https://releases.aspose.com/tasks/java/) से डाउनलोड करें।  
- आप अन्य Aspose लाइब्रेरीज़ को भी [यहाँ](https://releases.aspose.com/) देख सकते हैं।  
- Java और Maven/Gradle प्रोजेक्ट कॉन्फ़िगरेशन का बुनियादी ज्ञान।

## पैकेज इम्पोर्ट करें
`Project` क्लास Aspose.Tasks का कोर ऑब्जेक्ट है जो मेमोरी में Microsoft Project फ़ाइल का प्रतिनिधित्व करता है। लाइब्रेरी को अपने बिल्ड फ़ाइल में जोड़ने के बाद, आवश्यक क्लासेज़ इम्पोर्ट करें:

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

## प्रोजेक्ट को CSV के रूप में सहेजें (MPP को CSV में निर्यात)
एक MPP फ़ाइल को CSV में निर्यात करने से आप टास्क डेटा को Excel, Power BI, या किसी भी एनालिटिक्स प्लेटफ़ॉर्म में फीड कर सकते हैं।

### चरण 1: प्रोजेक्ट लोड करें
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### चरण 2: CSV के रूप में सहेजें
`SaveFileFormat.CSV` Aspose.Tasks को प्रोजेक्ट को CSV फ़ॉर्मेट में आउटपुट करने के लिए बताता है।  
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```

## प्रोजेक्ट को टेक्स्ट के रूप में सहेजें (टेक्स्ट निर्यात कैसे करें)
एक प्लेन‑टेक्स्ट फ़ाइल टास्क, रिसोर्सेज़, और असाइनमेंट्स का त्वरित, मानव‑पठनीय डंप प्रदान करती है।

### चरण 1: प्रोजेक्ट लोड करें
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### चरण 2: टेक्स्ट के रूप में सहेजें
`SaveFileFormat.TEXT` लाइब्रेरी को प्रोजेक्ट का प्लेन‑टेक्स्ट प्रतिनिधित्व जनरेट करने के लिए निर्देश देता है।  
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```

## प्रोजेक्ट को टेम्प्लेट के रूप में सहेजें (जावा में प्रोजेक्ट टेम्प्लेट बनाएं)

### चरण 1: प्रोजेक्ट लोड करें
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### चरण 2: टेम्प्लेट विकल्प सेट करें
तिथियों और बेसलाइन को हटाने वाली टेम्प्लेट फ़ाइल बनाने के लिए `Project.save` को `SaveFileFormat.MPT` (या `SaveFileFormat.TEMPLATE`) के साथ उपयोग करें।  
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
- **फ़ाइल नहीं मिली:** `YourProject.mpp` का पाथ सत्यापित करें या पूर्ण पाथ का उपयोग करें।  
- **लाइसेंस अपवाद:** वैध लाइसेंस के बिना लाइब्रेरी मूल्यांकन मोड में चलती है और वॉटरमार्क जोड़ सकती है। अपना लाइसेंस जल्दी लागू करें (`License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`)।  
- **बड़ी प्रोजेक्ट्स:** 200 MB से बड़ी फ़ाइलों के लिए JVM हीप (`-Xmx2g`) बढ़ाएँ ताकि `OutOfMemoryError` से बचा जा सके।  
- **प्रदर्शन:** कई प्रोजेक्ट्स को कन्वर्ट करते समय, जहाँ संभव हो एक ही `Project` इंस्टेंस को पुन: उपयोग करें ताकि ऑब्जेक्ट‑क्रिएशन ओवरहेड कम हो।

## निष्कर्ष
हमने दिखाया है कि Aspose.Tasks for Java का उपयोग करके **MPP को CSV में निर्यात करें**, **MPP को टेक्स्ट में बदलें**, और **प्रोजेक्ट को टेम्प्लेट के रूप में सहेजें**। ये क्षमताएँ आपको रिपोर्टिंग को ऑटोमेट करने, मानकीकृत प्रोजेक्ट स्केलेटन बनाने, और प्रोजेक्ट डेटा को किसी भी डाउनस्ट्रीम सिस्टम में एकीकृत करने देती हैं—बिना Microsoft Project स्थापित किए।

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न:** Aspose.Tasks for Java जटिल, बहु‑फेज़ प्रोजेक्ट्स को संभाल सकता है?  
**उत्तर:** हाँ, यह सभी टास्क, रिसोर्सेज़, असाइनमेंट्स, बेसलाइन, और कस्टम फ़ील्ड्स को 2024 तक के सभी Project संस्करणों में पूरी तरह समर्थन करता है।

**प्रश्न:** क्या ट्रायल संस्करण उपलब्ध है?  
**उत्तर:** बिल्कुल – [यहाँ](https://releases.aspose.com/) से मुफ्त ट्रायल डाउनलोड करें।

**प्रश्न:** यदि मुझे समस्याएँ आती हैं तो मैं मदद कहाँ प्राप्त कर सकता हूँ?  
**उत्तर:** आधिकारिक सपोर्ट फ़ोरम [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) पर है जहाँ स्टाफ और समुदाय के सदस्य प्रश्नों के उत्तर देते हैं।

**प्रश्न:** क्या मैं अल्पकालिक मूल्यांकन के लिए अस्थायी लाइसेंस प्राप्त कर सकता हूँ?  
**उत्तर:** हाँ, आप [यहाँ](https://purchase.aspose.com/temporary-license/) से अस्थायी लाइसेंस खरीद सकते हैं।

**प्रश्न:** क्या Aspose.Tasks Linux और macOS पर चलता है?  
**उत्तर:** यह पूरी तरह से क्रॉस‑प्लेटफ़ॉर्म है और Windows, macOS, और Linux पर किसी भी Java 8+ रनटाइम के साथ काम करता है।

---

**अंतिम अपडेट:** 2026-05-26  
**परीक्षित संस्करण:** Aspose.Tasks for Java 24.12 (latest)  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [MPP फ़ाइल कैसे बनाएं – Aspose.Tasks के साथ MPP फ़ॉर्मेट में खाली प्रोजेक्ट बनाएं और सहेजें](/tasks/java/project-configuration/create-save-mpp/)
- [MPP फ़ाइल लोड करें Java - Aspose.Tasks के साथ प्रोजेक्ट प्रॉपर्टीज़ प्रबंधित करें](/tasks/java/project-management/default-properties/)
- [Aspose.Tasks for Java के साथ MPP को Excel में निर्यात कैसे करें](/tasks/java/project-file-operations/save-data-to-excel/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}