---
date: 2026-09-20
description: Aspose.Tasks for Java का उपयोग करके currency symbol mpp निकालना और project
  properties अपडेट करना सीखें। कुछ ही कोड लाइनों में प्रतीक को बदलें और प्राप्त करें।
keywords:
- extract currency symbol mpp
- read project properties java
- retrieve currency symbol java
lastmod: 2026-09-20
linktitle: Aspose.Tasks for Java का उपयोग करके currency symbol mpp निकालें
og_description: Aspose.Tasks for Java का उपयोग करके currency symbol mpp निकालना और
  project properties अपडेट करना सीखें। तेज़, विश्वसनीय, और उत्पादन के लिए तैयार।
og_image_alt: 'Guide: extract currency symbol mpp using Aspose.Tasks Java'
og_title: Aspose.Tasks Java के साथ currency symbol mpp निकालने का तरीका
schemas:
- author: Aspose
  dateModified: '2026-09-20'
  description: Learn how to extract currency symbol mpp and update project properties
    using Aspose.Tasks for Java. Change and retrieve the symbol in just a few lines
    of code.
  headline: How to extract currency symbol mpp with Aspose.Tasks Java
  type: TechArticle
- description: Learn how to extract currency symbol mpp and update project properties
    using Aspose.Tasks for Java. Change and retrieve the symbol in just a few lines
    of code.
  name: How to extract currency symbol mpp with Aspose.Tasks Java
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or higher.'
    text: '**Java Development Kit (JDK)** – version 8 or higher.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the [Aspose.Tasks
      download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the [Aspose.Tasks
      download page](https://releases.aspose.com/tasks/java/).'
  - name: A valid **project.mpp** file placed in a folder you can reference from your
      code.
    text: A valid **project.mpp** file placed in a folder you can reference from your
      code.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks lets you edit tasks, resources, assignments, calendars,
      and many more project properties.
    question: Can I manipulate other project attributes besides currency symbols using
      Aspose.Tasks?
  - answer: Absolutely. It supports MPP, MPT, and XML formats from Project 98 up to
      the latest releases.
    question: Is Aspose.Tasks compatible with different versions of MS Project files?
  - answer: Comprehensive API docs, code examples, and a dedicated support forum are
      available on the Aspose.Tasks website.
    question: Does Aspose.Tasks offer documentation and support for developers?
  - answer: Yes – a fully functional free trial can be downloaded from the [Aspose
      website](https://purchase.aspose.com/buy).
    question: Can I try Aspose.Tasks before purchasing it?
  - answer: Temporary licenses are provided on the [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/)
      for evaluation purposes.
    question: How can I obtain a temporary license for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- extract currency symbol
- Aspose.Tasks
- Java project properties
- MPP handling
title: Aspose.Tasks Java के साथ currency symbol mpp निकालने का तरीका
url: /hi/java/currency/currency-symbols/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java का उपयोग करके mpp से मुद्रा प्रतीक निकालें

## परिचय
इस ट्यूटोरियल में आप **java project properties** के साथ काम करना सीखेंगे—विशेष रूप से **extract currency symbol mpp** को Microsoft Project (MPP) फ़ाइल से निकालना और Aspose.Tasks लाइब्रेरी का उपयोग करके **change currency symbol java** या **retrieve currency symbol java** करना। चाहे आप एक वित्तीय रिपोर्टिंग टूल बना रहे हों, Project डेटा को ERP सिस्टम में एकीकृत कर रहे हों, या बस अपने UI में सही मुद्रा प्रतीक दिखाना चाहते हों, इस छोटे लेकिन आवश्यक कार्य में निपुणता आपके Java एप्लिकेशन को अधिक मजबूत और उपयोगकर्ता‑मित्र बना देगी।

## त्वरित उत्तर
- **What does “extract currency symbol mpp” mean?** यह MPP (Microsoft Project) फ़ाइल में संग्रहीत मुद्रा प्रतीक को पढ़ने का अर्थ है।  
- **Which library handles this?** Aspose.Tasks for Java द्वारा प्रदान किए गए सरल API द्वारा यह कार्य संभाला जाता है।  
- **Do I need a license?** एक मुफ्त ट्रायल विकास के लिए काम करता है; उत्पादन के लिए एक वाणिज्यिक लाइसेंस आवश्यक है।  
- **How long does it take?** नीचे दिए गए कोड के साथ, आप एक मिनट से कम समय में प्रतीक प्राप्त कर सकते हैं।  
- **Can I also change the symbol?** हाँ – आप वही `Prj.CURRENCY_SYMBOL` प्रॉपर्टी का उपयोग करके नया मान सेट कर सकते हैं।

## “extract currency symbol mpp” क्या है?
MPP फ़ाइल से मुद्रा प्रतीक निकालना मतलब Microsoft Project द्वारा फ़ाइल हेडर में संग्रहीत एक‑अक्षर स्ट्रिंग को पढ़ना है, जो प्रोजेक्ट की मौद्रिक इकाई को दर्शाता है। यह ऑपरेशन आपको अपने एप्लिकेशन में सही प्रतीक (जैसे $, €, £) दिखाने की अनुमति देता है बिना किसी मान को हार्ड‑कोड किए।

## जावा प्रोजेक्ट प्रॉपर्टीज़ में मुद्रा प्रतीक को अपडेट क्यों करें?
मुद्रा प्रतीक को अपडेट करने से आप रिपोर्ट, इनवॉइस और डैशबोर्ड को तुरंत स्थानीयकृत कर सकते हैं। कई क्षेत्रों में प्रोजेक्ट चलाने वाले एंटरप्राइज़ एक ही कदम में प्रतीक बदल सकते हैं, जिससे पूरे प्रोजेक्ट फ़ाइल को डुप्लिकेट करने की आवश्यकता नहीं रहती। Aspose.Tasks प्रॉपर्टी को मेमोरी में संशोधित कर फ़ाइल को वापस सहेज सकता है, और 2,000 कार्यों तक वाले प्रोजेक्ट्स में भी प्रदर्शन पर कोई उल्लेखनीय प्रभाव नहीं डालता।

## पूर्वापेक्षाएँ
1. **Java Development Kit (JDK)** – संस्करण 8 या उससे ऊपर।  
2. **Aspose.Tasks for Java** – नवीनतम JAR [Aspose.Tasks download page](https://releases.aspose.com/tasks/java/) से डाउनलोड करें।  
3. एक वैध **project.mpp** फ़ाइल को ऐसे फ़ोल्डर में रखें जिसे आप अपने कोड से संदर्भित कर सकें।

## पैकेज आयात करें
सबसे पहले, उन क्लासों को आयात करें जिनकी हमें प्रोजेक्ट फ़ाइलों के साथ काम करने के लिए आवश्यकता होगी।

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## चरण 1: डेटा डायरेक्टरी निर्धारित करें
एप्लिकेशन को बताएं कि आपका *.mpp* फ़ाइल कहाँ स्थित है।

```java
String dataDir = "Your Data Directory";
```

> **Pro tip:** `System.getProperty("user.dir")` का उपयोग करके एक पूर्ण पथ बनाएं जो किसी भी मशीन पर काम करे।

## चरण 2: MS Project फ़ाइल लोड करें
`Project` Aspose.Tasks का शीर्ष‑स्तर ऑब्जेक्ट है जो मेमोरी में एकल Microsoft Project फ़ाइल का प्रतिनिधित्व करता है। इस ऑब्जेक्ट को बनाकर फ़ाइल संरचना लोड हो जाती है बिना Microsoft Project स्थापित किए।

```java
Project project = new Project(dataDir + "project.mpp");
```

## चरण 3: मुद्रा प्रतीक प्राप्त करें (और वैकल्पिक रूप से बदलें)
`Prj.CURRENCY_SYMBOL` वह प्रॉपर्टी कुंजी है जो मुद्रा प्रतीक संग्रहीत करती है। इसे पढ़ने से वर्तमान प्रतीक मिलता है; नया स्ट्रिंग असाइन करने से प्रोजेक्ट की मुद्रा परिभाषा अपडेट हो जाती है।

```java
// Retrieve the current currency symbol
System.out.println(project.get(Prj.CURRENCY_SYMBOL));

// Example of changing it (uncomment to use)
// project.set(Prj.CURRENCY_SYMBOL, "€");
// System.out.println("New symbol: " + project.get(Prj.CURRENCY_SYMBOL));
```

`System.out.println` कॉल प्रतीक (जैसे, `$`) को कंसोल पर प्रिंट करता है, जिससे यह पुष्टि होती है कि निष्कर्षण सफल रहा।

## सामान्य समस्याएँ और समाधान
| लक्षण | संभावित कारण | समाधान |
|---------|--------------|----------|
| `NullPointerException` on `project.get(...)` | गलत फ़ाइल पथ या फ़ाइल नहीं मिली | `dataDir` और फ़ाइल नाम की जाँच करें; डिबग करने के लिए `new File(dataDir).exists()` का उपयोग करें |
| अप्रत्याशित प्रतीक (जैसे, `?`) | प्रोजेक्ट गैर‑मानक लोकेल के साथ बनाया गया | सुनिश्चित करें कि स्रोत MPP फ़ाइल वास्तव में मुद्रा प्रतीक परिभाषित करती है; आप ऊपर दिखाए अनुसार प्रोग्रामेटिक रूप से एक सेट कर सकते हैं |
| लाइसेंस त्रुटि | वैध लाइसेंस फ़ाइल के बिना ट्रायल का उपयोग करना | `Project` ऑब्जेक्ट बनाने से पहले `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` के साथ अपना लाइसेंस लोड करें |

## अक्सर पूछे जाने वाले प्रश्न

**Q: Can I manipulate other project attributes besides currency symbols using Aspose.Tasks?**  
A: हाँ, Aspose.Tasks आपको टास्क, रिसोर्स, असाइनमेंट, कैलेंडर और कई अन्य प्रोजेक्ट प्रॉपर्टीज़ को संपादित करने की अनुमति देता है।

**Q: Is Aspose.Tasks compatible with different versions of MS Project files?**  
A: बिल्कुल। यह Project 98 से लेकर नवीनतम रिलीज़ तक के MPP, MPT और XML फ़ॉर्मेट को सपोर्ट करता है।

**Q: Does Aspose.Tasks offer documentation and support for developers?**  
A: व्यापक API दस्तावेज़, कोड उदाहरण, और एक समर्पित सपोर्ट फ़ोरम Aspose.Tasks वेबसाइट पर उपलब्ध हैं।

**Q: Can I try Aspose.Tasks before purchasing it?**  
A: हाँ – एक पूरी तरह कार्यात्मक मुफ्त ट्रायल [Aspose website](https://purchase.aspose.com/buy) से डाउनलोड किया जा सकता है।

**Q: How can I obtain a temporary license for Aspose.Tasks?**  
A: मूल्यांकन उद्देश्यों के लिए टेम्पररी लाइसेंस [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/) पर उपलब्ध हैं।

**अंतिम अपडेट:** 2026-09-20  
**परीक्षित संस्करण:** Aspose.Tasks for Java 24.12 (लेखन के समय नवीनतम)  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [Project Properties Java – Aspose.Tasks के साथ मेटाडेटा पढ़ें](/tasks/java/project-properties/)
- [Aspose.Tasks के साथ MS Project से मुद्रा कैसे प्राप्त करें](/tasks/java/currency/currency-codes/)
- [Aspose.Tasks for Java का उपयोग करके MS Project में प्रोजेक्ट प्रारंभ तिथि सेट करें](/tasks/java/project-properties/write-project-info/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}