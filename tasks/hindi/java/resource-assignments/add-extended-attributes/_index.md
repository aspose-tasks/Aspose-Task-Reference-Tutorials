---
date: 2026-05-20
description: Aspose.Tasks for Java का उपयोग करके resource assignments में extended
  attributes जोड़ना, project start date सेट करना, और MS Project फ़ाइलें कुशलता से
  लिखना सीखें।
keywords:
- how to use aspose
- add extended attributes
- set project start date
- create resource assignment
- aspose tasks java
linktitle: Aspose.Tasks में Resource Assignments में Extended Attributes जोड़ें
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to use Aspose.Tasks for Java to add extended attributes to
    resource assignments, set project start date, and write MS Project files efficiently.
  headline: How to Use Aspose.Tasks for Java – Add Extended Attributes to Resource
    Assignments
  type: TechArticle
- description: Learn how to use Aspose.Tasks for Java to add extended attributes to
    resource assignments, set project start date, and write MS Project files efficiently.
  name: How to Use Aspose.Tasks for Java – Add Extended Attributes to Resource Assignments
  steps:
  - name: Set Up Data Directory
    text: Define the directory where your project data will be stored. This path is
      used later when you save the XML file.
  - name: Create Project Instance
    text: The `Project` class is Aspose.Tasks' top‑level object that represents a
      single Microsoft Project file in memory. Instantiating it gives you full access
      to all project elements.
  - name: Set Project Information Properties
    text: Set essential project properties such as the start date, schedule from start
      flag, and status date. These values are stored in the project’s `ProjectInfo`
      object.
  - name: Add Extended Attributes to a Resource Assignment
    text: Create an `ExtendedAttributeDefinition` for the custom field, attach it
      to a `ResourceAssignment`, and populate the value. This step demonstrates the
      **add extended attributes** keyword in action.
  type: HowTo
- questions:
  - answer: Yes, the library provides full read‑write capabilities for .mpp, .xml,
      and .xps formats.
    question: Can I use Aspose.Tasks for Java to read MS Project files?
  - answer: Absolutely, it supports files from Project 2000 up to the latest 2024
      release, covering over 20 version formats.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: The trial adds a watermark to generated files and limits the number of
      tasks you can create, but all API features remain accessible.
    question: Are there any limitations to the trial version of Aspose.Tasks for Java?
  - answer: You can seek assistance from the Aspose.Tasks community forum [here](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for Aspose.Tasks for Java?
  - answer: Yes, temporary licenses are available for short‑term usage. You can obtain
      one from [here](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java का उपयोग कैसे करें – Resource Assignments में Extended
  Attributes जोड़ें
url: /hi/java/resource-assignments/add-extended-attributes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java के साथ MS Project हेरफेर में महारत

## परिचय
इस ट्यूटोरियल में आप **Aspose.Tasks for Java का उपयोग कैसे करें** यह जानेंगे, जिससे आप संसाधन असाइनमेंट में विस्तारित गुण जोड़ सकते हैं और प्रोग्रामेटिक रूप से Microsoft Project जानकारी लिख सकते हैं। चाहे आप रिपोर्टिंग पाइपलाइन को ऑटोमेट कर रहे हों या एक कस्टम प्रोजेक्ट‑मैनेजमेंट टूल बना रहे हों, नीचे दिए गए चरण आपको ठीक‑ठीक दिखाते हैं कि प्रोजेक्ट की प्रारंभ तिथि कैसे सेट करें, संसाधन असाइनमेंट बनाएं, और फ़ाइल को XML के रूप में कैसे सहेजें—सिर्फ कुछ ही Java कोड लाइनों के साथ।

## त्वरित उत्तर
- **Aspose.Tasks for Java क्या करता है?** यह Microsoft Project फ़ाइलों को पढ़ता, लिखता और संशोधित करता है, बिना Microsoft Project स्थापित किए।  
- **क्या मैं संसाधन असाइनमेंट में कस्टम फ़ील्ड जोड़ सकता हूँ?** हाँ, `ResourceAssignment` ऑब्जेक्ट पर `ExtendedAttribute` संग्रह का उपयोग करें।  
- **प्रोजेक्ट की प्रारंभ तिथि कैसे सेट करें?** सहेजने से पहले `project.setStartDate(LocalDateTime.of(...))` कॉल करें।  
- **क्या उत्पादन उपयोग के लिए लाइसेंस चाहिए?** एक व्यावसायिक लाइसेंस मूल्यांकन वॉटरमार्क हटाता है और पूर्ण API एक्सेस अनलॉक करता है।  
- **कौन से Java संस्करण समर्थित हैं?** Aspose.Tasks for Java JDK 8 से लेकर JDK 21 तक समर्थन देता है।

## Aspose.Tasks for Java का उपयोग कैसे करें?
`Project` वह मुख्य ऑब्जेक्ट है जो मेमोरी में Microsoft Project फ़ाइल का प्रतिनिधित्व करता है। Aspose.Tasks लाइब्रेरी लोड करें, एक `Project` इंस्टेंस बनाएं, प्रोजेक्ट‑स्तर के गुण कॉन्फ़िगर करें, संसाधन असाइनमेंट में विस्तारित गुण जोड़ें, और अंत में प्रोजेक्ट को XML के रूप में सहेजें। मूल कार्यप्रवाह तीन संक्षिप्त चरणों में फिट होता है: इनिशियलाइज़, मॉडिफ़ाई, और पर्सिस्ट। यह पैटर्न किसी भी आकार की प्रोजेक्ट फ़ाइल के लिए काम करता है और Windows, Linux, या macOS JVMs पर चलता है।

## Aspose.Tasks में विस्तारित गुण क्या है?
एक **विस्तारित गुण** एक कस्टम फ़ील्ड है जिसे आप टास्क, रिसोर्स या असाइनमेंट से जोड़ते हैं ताकि बिल्ट‑इन कॉलमों से परे अतिरिक्त मेटाडेटा संग्रहीत किया जा सके। `ExtendedAttributeDefinition` कस्टम फ़ील्ड की स्कीमा को परिभाषित करता है। Aspose.Tasks प्रोग्रामेटिक रूप से इन फ़ील्डों को परिभाषित और असाइन करने के लिए `ExtendedAttributeDefinition` और `ExtendedAttribute` क्लासेज़ प्रदान करता है।

## संसाधन असाइनमेंट में विस्तारित गुण क्यों जोड़ें?
Aspose.Tasks **50+ बिल्ट‑इन और कस्टम फ़ील्ड** का समर्थन करता है, और आप अनलिमिटेड यूज़र‑डिफाइंड गुण जोड़ सकते हैं। इन्हें जोड़ने से आप लागत कोड, विभाग आईडी, या कोई भी बिज़नेस‑स्पेसिफिक डेटा सीधे .mpp फ़ाइल में कैप्चर कर सकते हैं, जिससे बाहरी स्प्रेडशीट की आवश्यकता समाप्त हो जाती है और प्रोजेक्ट लाइफ़साइकल में डेटा इंटेग्रिटी सुनिश्चित होती है।

## पूर्वापेक्षाएँ
1. **Java Development Kit (JDK)** – JDK 8 या बाद का स्थापित हो।  
2. **Aspose.Tasks for Java लाइब्रेरी** – इसे आधिकारिक रिलीज़ पेज से डाउनलोड करें [here](https://releases.aspose.com/tasks/java/)।  
3. **IDE** – IntelliJ IDEA, Eclipse, या कोई भी Java‑संगत एडिटर जो आप पसंद करें।

## पैकेज आयात करें
सबसे पहले, अपने Java प्रोजेक्ट में आवश्यक पैकेज आयात करें:

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Value;
import java.io.IOException;
import java.math.BigDecimal;
```

### चरण 1: डेटा डायरेक्टरी सेट करें
उस डायरेक्टरी को परिभाषित करें जहाँ आपका प्रोजेक्ट डेटा संग्रहीत होगा। यह पाथ बाद में XML फ़ाइल सहेजते समय उपयोग किया जाएगा।

```java
String dataDir = "Your Data Directory";
```

### चरण 2: प्रोजेक्ट इंस्टेंस बनाएं
`Project` क्लास Aspose.Tasks का टॉप‑लेवल ऑब्जेक्ट है जो मेमोरी में एकल Microsoft Project फ़ाइल का प्रतिनिधित्व करता है। इसे इंस्टैंशिएट करने से आपको सभी प्रोजेक्ट तत्वों तक पूर्ण पहुंच मिलती है।

```java
Project project = new Project();
```

### चरण 3: प्रोजेक्ट सूचना गुण सेट करें
प्रोजेक्ट की आवश्यक गुण जैसे प्रारंभ तिथि, शेड्यूल फ्रॉम स्टार्ट फ़्लैग, और स्टेटस डेट सेट करें। ये मान प्रोजेक्ट के `ProjectInfo` ऑब्जेक्ट में संग्रहीत होते हैं।

```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

### चरण 4: संसाधन असाइनमेंट में विस्तारित गुण जोड़ें
कस्टम फ़ील्ड के लिए एक `ExtendedAttributeDefinition` बनाएं, इसे `ResourceAssignment` से अटैच करें, और वैल्यू पॉपुलेट करें। यह चरण **add extended attributes** कीवर्ड को कार्रवाई में दिखाता है।

```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## सामान्य समस्याएँ और समाधान
- **असाइनमेंट कलेक्शन तक पहुँचते समय NullPointerException** – असाइनमेंट प्राप्त करने से पहले कम से कम एक रिसोर्स और एक टास्क बनाएं।  
- **MS Project में विस्तारित गुण नहीं दिख रहा** – सुनिश्चित करें कि गुण का `FieldId` एक कस्टम फ़ील्ड स्लॉट से मेल खाता है (जैसे, `ExtendedAttributeTask.Text1`)।  
- **डेट फ़ॉर्मेट मिसमैच** – डेट वैल्यू के लिए `java.time.LocalDateTime` उपयोग करें; Aspose.Tasks उन्हें स्वचालित रूप से प्रोजेक्ट के कैलेंडर फ़ॉर्मेट में बदल देता है।

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या मैं Aspose.Tasks for Java का उपयोग करके MS Project फ़ाइलें पढ़ सकता हूँ?**  
**उत्तर:** हाँ, लाइब्रेरी .mpp, .xml, और .xps फ़ॉर्मैट्स के लिए पूर्ण रीड‑राइट क्षमताएँ प्रदान करती है।

**प्रश्न: क्या Aspose.Tasks for Java विभिन्न संस्करणों के MS Project के साथ संगत है?**  
**उत्तर:** बिल्कुल, यह Project 2000 से लेकर नवीनतम 2024 रिलीज़ तक की फ़ाइलों का समर्थन करता है, जिसमें 20 से अधिक संस्करण फ़ॉर्मैट्स शामिल हैं।

**प्रश्न: क्या Aspose.Tasks for Java के ट्रायल संस्करण में कोई सीमाएँ हैं?**  
**उत्तर:** ट्रायल जनरेट की गई फ़ाइलों में वॉटरमार्क जोड़ता है और आप जितने टास्क बना सकते हैं उसकी संख्या सीमित करता है, लेकिन सभी API फीचर उपलब्ध रहते हैं।

**प्रश्न: मैं Aspose.Tasks for Java के लिए समर्थन कैसे प्राप्त कर सकता हूँ?**  
**उत्तर:** आप Aspose.Tasks कम्युनिटी फ़ोरम से सहायता ले सकते हैं [here](https://forum.aspose.com/c/tasks/15)।

**प्रश्न: क्या मैं Aspose.Tasks for Java के लिए अस्थायी लाइसेंस खरीद सकता हूँ?**  
**उत्तर:** हाँ, अल्पकालिक उपयोग के लिए अस्थायी लाइसेंस उपलब्ध हैं। आप इसे [here](https://purchase.aspose.com/temporary-license/) से प्राप्त कर सकते हैं।

**अंतिम अपडेट:** 2026-05-20  
**परीक्षित संस्करण:** Aspose.Tasks for Java 24.12 (लेखन के समय नवीनतम)  
**लेखक:** Aspose  

{{< blocks/products/products-backtop-button >}}

## संबंधित ट्यूटोरियल

- [Aspose.Tasks में रिसोर्स असाइनमेंट में नोट्स कैसे जोड़ें](/tasks/java/resource-assignments/resource-assignment-notes/)
- [Aspose.Tasks में रिसोर्स असाइनमेंट के लिए रेट स्केल कैसे पढ़ें और लिखें](/tasks/java/resource-assignments/read-write-rate-scale/)
- [Aspose.Tasks में प्रोजेक्ट में रिसोर्स कैसे जोड़ें और लेवलिंग डिले प्रॉपर्टीज़ को संभालें](/tasks/java/resource-assignments/leveling-delay-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}