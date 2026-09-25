---
date: 2026-09-25
description: Aspose.Tasks for Java का उपयोग करके MS Project फ़ाइलों से currency codes
  प्राप्त करना सीखें – वह तेज़ तरीका जिससे Java डेवलपर्स को आवश्यक currency code मिल
  सके।
keywords:
- retrieve currency code java
- Aspose.Tasks Java
- MS Project currency
- read MS Project file
lastmod: 2026-09-25
linktitle: Aspose.Tasks में Currency Codes प्रबंधित करें
og_description: Aspose.Tasks का उपयोग करके MS Project फ़ाइलों से जावा में currency
  code प्राप्त करें। यह गाइड दिखाता है कि प्रोजेक्ट को कैसे पढ़ें, ISO currency identifier
  निकालें, और इसे Java एप्लिकेशन्स में लागू करें।
og_image_alt: Screenshot of Java code extracting currency code from an MS Project
  file using Aspose.Tasks
og_title: MS Project से जावा में currency code प्राप्त करें
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to retrieve currency codes from MS Project files using Aspose.Tasks
    for Java – the quick way to get currency code Java developers need.
  headline: Retrieve currency code java from MS Project with Aspose.Tasks
  type: TechArticle
- description: Learn how to retrieve currency codes from MS Project files using Aspose.Tasks
    for Java – the quick way to get currency code Java developers need.
  name: Retrieve currency code java from MS Project with Aspose.Tasks
  steps:
  - name: set up data directory
    text: Define the folder that contains your *.mpp* file. Adjust the path to match
      your environment so the runtime can locate the project file.
  - name: load the project file
    text: The `Project` class is Aspose.Tasks' top‑level object that represents a
      single MS Project file in memory. Creating an instance reads the file and builds
      an in‑memory model you can query.
  - name: retrieve currency code
    text: The `Prj.CURRENCY_CODE` constant identifies the property that stores the
      ISO currency identifier. Calling `prj.get(Prj.CURRENCY_CODE)` returns the three‑letter
      code in a single operation. The output will be the three‑letter ISO currency
      code (e.g., `USD`, `EUR`, `GBP`) that the project is configured
  - name: how to retrieve currency code in Java (additional context)
    text: Load your project, call `prj.get(Prj.CURRENCY_CODE)`, and store the result
      in a `String`. You can then pass this value to any financial service, reporting
      engine, or UI component that requires a currency identifier.
  - name: (optional) use the currency code
    text: 'Typical downstream scenarios include: - **Report generation** – prepend
      the code to cost columns (`USD 1,200`). - **API integration** – send the ISO
      code to payment gateways that demand a currency parameter. - **Data consolidation**
      – group multiple projects by currency for portfolio‑level analysis.'
  type: HowTo
- questions:
  - answer: Yes, the API reads multi‑level task hierarchies, resource pools, custom
      fields, and calendars without limitation.
    question: Can Aspose.Tasks handle complex project structures?
  - answer: Absolutely. It supports MPP, XML, XER, and other formats from Project
      98 through the latest Office releases.
    question: Is Aspose.Tasks compatible with different versions of MS Project files?
  - answer: Comprehensive API reference, code examples, and dedicated technical support
      are available on the Aspose website.
    question: Does Aspose.Tasks provide documentation and support?
  - answer: A free trial is offered so you can evaluate all features, including currency
      code extraction.
    question: Can I try Aspose.Tasks before purchasing?
  - answer: Temporary licenses are available from the [website](https://purchase.aspose.com/temporary-license/).
    question: Where can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- retrieve currency
- Aspose.Tasks
- Java project automation
- MS Project
title: Aspose.Tasks के साथ MS Project से जावा में currency code प्राप्त करें
url: /hi/java/currency/currency-codes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Project से Aspose.Tasks के साथ जावा में मुद्रा कोड प्राप्त करें

## परिचय
इस ट्यूटोरियल में आप Aspose.Tasks जावा API का उपयोग करके MS Project फ़ाइल से **जावा में मुद्रा कोड कैसे प्राप्त करें** सीखेंगे। चाहे आपको बहु‑मुद्रा वित्तीय रिपोर्ट बनानी हों, विभिन्न क्षेत्रों में प्रोजेक्ट को समेकित करना हो, या केवल डाउनस्ट्रीम सिस्टम में सही मौद्रिक प्रतीक दिखाना हो, नीचे दिए गए चरण आपको पर्यावरण सेटअप से लेकर एकल‑लाइन कॉल तक ले जाएंगे जो ISO मुद्रा पहचानकर्ता लौटाता है। गाइड के अंत तक आप किसी भी समर्थित प्रोजेक्ट फ़ाइल फ़ॉर्मेट को लोड करने और `USD`, `EUR`, या `GBP` जैसे तीन‑अक्षर वाले मुद्रा कोड निकालने में सहज होंगे।

## त्वरित उत्तर
- **API क्या करता है?** यह MS Project फ़ाइलें पढ़ता है और मुद्रा कोड जैसी प्रॉपर्टीज़ को उजागर करता है।  
- **कौन सी भाषा उपयोग की गई है?** जावा, Aspose.Tasks for Java लाइब्रेरी के माध्यम से।  
- **क्या मुझे लाइसेंस चाहिए?** विकास के लिए एक मुफ्त ट्रायल काम करता है; उत्पादन के लिए एक व्यावसायिक लाइसेंस आवश्यक है।  
- **क्या मैं कोड एक पंक्ति में प्राप्त कर सकता हूँ?** हाँ—`prj.get(Prj.CURRENCY_CODE)` तुरंत मुद्रा कोड स्ट्रिंग लौटाता है।  
- **क्या यह सभी प्रोजेक्ट संस्करणों के साथ संगत है?** Aspose.Tasks 20 से अधिक इनपुट फ़ॉर्मेट का समर्थन करता है, जिसमें लेगेसी MPP, XML, और XER फ़ाइलें शामिल हैं।

## MS Project फ़ाइल पढ़ना क्या है?
MS Project फ़ाइल पढ़ना मतलब प्रोग्रामेटिक रूप से *.mpp* (या कोई अन्य समर्थित फ़ॉर्मेट जैसे XML या XER) खोलना और उसकी आंतरिक डेटा संरचनाओं तक पहुँच प्राप्त करना है। इन संरचनाओं में टास्क, रिसोर्सेज़, कैलेंडर, लागत तालिकाएँ और वित्तीय सेटिंग्स शामिल हैं। फ़ाइल को पार्स करके आप माइक्रोसॉफ्ट प्रोजेक्ट को लॉन्च किए बिना जानकारी निकाल सकते हैं, जिससे स्वचालित रिपोर्टिंग, माइग्रेशन और इंटीग्रेशन वर्कफ़्लो सक्षम होते हैं।

## MS Project फ़ाइलें पढ़ने के लिए Aspose.Tasks क्यों उपयोग करें?
Aspose.Tasks एक शुद्ध‑जावा समाधान प्रदान करता है जो COM इंटरऑप या स्थानीय Microsoft Project इंस्टॉलेशन की आवश्यकता को हटाता है। यह 20 से अधिक फ़ाइल फ़ॉर्मेट का समर्थन करता है, 100 MB से कम मेमोरी में हजारों टास्क वाले प्रोजेक्ट को संभाल सकता है, और एक समृद्ध ऑब्जेक्ट मॉडल प्रदान करता है। `Prj.CURRENCY_CODE` जैसे कॉन्स्टेंट्स तक सीधी पहुँच आपको मुद्रा जानकारी तुरंत और विश्वसनीय रूप से प्राप्त करने देती है।

## पूर्वापेक्षाएँ
कोड में डुबकी लगाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

### Java विकास किट (JDK) स्थापित है
एक नवीनतम JDK (11 या बाद का) आवश्यक है। इसे आधिकारिक Oracle साइट से डाउनलोड करें: [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### Aspose.Tasks for Java लाइब्रेरी
नवीनतम Aspose.Tasks for Java बाइनरी प्राप्त करें और उन्हें अपने प्रोजेक्ट की क्लासपाथ में जोड़ें। पूरी दस्तावेज़ीकरण और डाउनलोड लिंक उपलब्ध हैं [here](https://reference.aspose.com/tasks/java/).

## पैकेज आयात करें
`Project` क्लास और `Prj` कॉन्स्टेंट्स `com.aspose.tasks` नेमस्पेस में स्थित हैं। इन्हें अपने जावा स्रोत फ़ाइल के शीर्ष पर आयात करें:

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## चरण‑दर‑चरण मार्गदर्शिका

### चरण 1: डेटा डायरेक्टरी सेट करें
उस फ़ोल्डर को परिभाषित करें जिसमें आपका *.mpp* फ़ाइल है। पथ को अपने पर्यावरण के अनुसार समायोजित करें ताकि रनटाइम प्रोजेक्ट फ़ाइल को ढूँढ़ सके।

```java
String dataDir = "Your Data Directory";
```

### चरण 2: प्रोजेक्ट फ़ाइल लोड करें
`Project` क्लास Aspose.Tasks का शीर्ष‑स्तरीय ऑब्जेक्ट है जो मेमोरी में एकल MS Project फ़ाइल का प्रतिनिधित्व करता है। एक इंस्टेंस बनाना फ़ाइल को पढ़ता है और एक इन‑मेमोरी मॉडल बनाता है जिसे आप क्वेरी कर सकते हैं।

```java
Project prj = new Project(dataDir + "project.mpp");
```

### चरण 3: मुद्रा कोड प्राप्त करें
`Prj.CURRENCY_CODE` कॉन्स्टेंट उस प्रॉपर्टी को पहचानता है जो ISO मुद्रा पहचानकर्ता संग्रहीत करता है। `prj.get(Prj.CURRENCY_CODE)` को कॉल करने से एक ही ऑपरेशन में तीन‑अक्षर वाला कोड लौटता है।

```java
System.out.println(prj.get(Prj.CURRENCY_CODE));
```
आउटपुट वह तीन‑अक्षर वाला ISO मुद्रा कोड होगा (जैसे `USD`, `EUR`, `GBP`) जिसे प्रोजेक्ट उपयोग करने के लिए कॉन्फ़िगर किया गया है।

### चरण 4: जावा में मुद्रा कोड कैसे प्राप्त करें (अतिरिक्त संदर्भ)
अपने प्रोजेक्ट को लोड करें, `prj.get(Prj.CURRENCY_CODE)` को कॉल करें, और परिणाम को एक `String` में संग्रहीत करें। फिर आप इस मान को किसी भी वित्तीय सेवा, रिपोर्टिंग इंजन, या UI कंपोनेंट को पास कर सकते हैं जिसे मुद्रा पहचानकर्ता की आवश्यकता होती है।

### चरण 5: (वैकल्पिक) मुद्रा कोड का उपयोग करें
Typical downstream scenarios include:

- **Report generation** – कोड को लागत कॉलमों के पहले जोड़ें (`USD 1,200`).  
- **API integration** – ISO कोड को भुगतान गेटवे को भेजें जो मुद्रा पैरामीटर की मांग करते हैं।  
- **Data consolidation** – कई प्रोजेक्ट्स को मुद्रा के आधार पर समूहित करें ताकि पोर्टफ़ोलियो‑स्तर विश्लेषण हो सके।

## सामान्य समस्याएँ और समाधान

| समस्या | कारण | समाधान |
|-------|--------|-----|
| **शून्य आउटपुट** | प्रोजेक्ट फ़ाइल में मुद्रा परिभाषित नहीं है (डिफ़ॉल्ट खाली है)। | Microsoft Project में मुद्रा सेट करें या पढ़ने से पहले `prj.set(Prj.CURRENCY_CODE, "USD");` के माध्यम से असाइन करें। |
| **फ़ाइल नहीं मिली** | `dataDir` पथ गलत है। | पथ की जाँच करें और सुनिश्चित करें कि फ़ाइल नाम बिल्कुल मेल खाता है, केस सेंसिटिविटी सहित। |
| **असमर्थित फ़ाइल संस्करण** | बहुत पुरानी या भ्रष्ट *.mpp* फ़ाइल। | नवीनतम Aspose.Tasks संस्करण में अपग्रेड करें या पहले Microsoft Project में फ़ाइल को नए फ़ॉर्मेट में परिवर्तित करें। |

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या Aspose.Tasks जटिल प्रोजेक्ट संरचनाओं को संभाल सकता है?**  
A: हाँ, API मल्टी‑लेवल टास्क हायरार्की, रिसोर्स पूल, कस्टम फ़ील्ड, और कैलेंडर को बिना सीमा के पढ़ता है।

**Q: क्या Aspose.Tasks विभिन्न संस्करणों की MS Project फ़ाइलों के साथ संगत है?**  
A: बिल्कुल। यह MPP, XML, XER, और प्रोजेक्ट 98 से लेकर नवीनतम ऑफिस रिलीज़ तक के अन्य फ़ॉर्मेट का समर्थन करता है।

**Q: क्या Aspose.Tasks दस्तावेज़ीकरण और समर्थन प्रदान करता है?**  
A: व्यापक API रेफ़रेंस, कोड उदाहरण, और समर्पित तकनीकी समर्थन Aspose वेबसाइट पर उपलब्ध हैं।

**Q: क्या मैं खरीदने से पहले Aspose.Tasks आज़मा सकता हूँ?**  
A: एक मुफ्त ट्रायल उपलब्ध है जिससे आप सभी फीचर्स, जिसमें मुद्रा कोड निष्कर्षण भी शामिल है, का मूल्यांकन कर सकते हैं।

**Q: मूल्यांकन के लिए अस्थायी लाइसेंस कहाँ प्राप्त कर सकता हूँ?**  
A: अस्थायी लाइसेंस [website](https://purchase.aspose.com/temporary-license/) से उपलब्ध हैं।

---

**अंतिम अपडेट:** 2026-09-25  
**परीक्षण किया गया:** Aspose.Tasks for Java (latest version)  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [Project Properties Java – Aspose.Tasks के साथ मेटाडेटा पढ़ें](/tasks/java/project-properties/)
- [Microsoft Project से प्रोजेक्ट जानकारी पढ़ने के लिए Aspose.Tasks for Java](/tasks/java/project-properties/read-project-info/)
- [Aspose.Tasks में MS Project आउटलाइन कोड प्राप्त करें](/tasks/java/project-file-operations/retrieve-outline-codes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}