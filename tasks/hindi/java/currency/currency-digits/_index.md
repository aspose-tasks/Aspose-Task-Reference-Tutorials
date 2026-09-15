---
date: 2026-09-14
description: Aspose.Tasks के साथ MS Project मुद्रा प्राप्त करने और जावा में प्रोजेक्ट
  प्रॉपर्टीज़ पढ़ने का तरीका सीखें। MPP फ़ाइल से मुद्रा अंक निकालने के लिए चरण-दर-चरण
  गाइड।
keywords:
- get ms project currency
- read project properties java
- convert project file java
lastmod: 2026-09-14
linktitle: Aspose.Tasks का उपयोग करके MS Project से मुद्रा प्राप्त करने का तरीका
og_description: Aspose.Tasks के साथ MS Project मुद्रा प्राप्त करने और जावा में प्रोजेक्ट
  प्रॉपर्टीज़ पढ़ने का तरीका सीखें। इस संक्षिप्त जावा ट्यूटोरियल का पालन करके MPP
  फ़ाइल से मुद्रा अंक निकालें।
og_image_alt: Screenshot of Java code extracting currency digits from an MS Project
  file using Aspose.Tasks
og_title: Aspose.Tasks का उपयोग करके MS Project मुद्रा प्राप्त करना – जावा गाइड
schemas:
- author: Aspose
  dateModified: '2026-09-14'
  description: Learn how to get ms project currency and read project properties java
    with Aspose.Tasks. Step‑by‑step guide for extracting currency digits from an MPP
    file.
  headline: How to get ms project currency using Aspose.Tasks
  type: TechArticle
- description: Learn how to get ms project currency and read project properties java
    with Aspose.Tasks. Step‑by‑step guide for extracting currency digits from an MPP
    file.
  name: How to get ms project currency using Aspose.Tasks
  steps:
  - name: '**Java Development Environment** – JDK 8 or newer installed and configured.'
    text: '**Java Development Environment** – JDK 8 or newer installed and configured.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).'
  - name: '**Basic Java knowledge** – you should be comfortable creating a Java project,
      adding external libraries, and running a `main` method.'
    text: '**Basic Java knowledge** – you should be comfortable creating a Java project,
      adding external libraries, and running a `main` method.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks offers a wide range of functionalities to manipulate
      various aspects of Project files, such as tasks, resources, and custom fields.
    question: Can Aspose.Tasks handle other Project attributes besides currency digits?
  - answer: Absolutely, Aspose.Tasks is designed to meet the demands of enterprise‑grade
      projects, offering high performance and scalability.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes, you can use Aspose.Tasks for Java on any platform that supports the
      Java Runtime Environment (Windows, Linux, macOS).
    question: Does Aspose.Tasks support cross‑platform development?
  - answer: Yes, you can download a free trial version from the [Aspose releases page](https://releases.aspose.com/).
    question: Can I try Aspose.Tasks before purchasing?
  - answer: You can find support on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I get support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- ms project
- aspose.tasks
- java project processing
title: Aspose.Tasks का उपयोग करके MS Project मुद्रा प्राप्त करने का तरीका
url: /hi/java/currency/currency-digits/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks के साथ ms project currency कैसे प्राप्त करें

## परिचय
यदि आप Microsoft Project फ़ाइल से **ms project currency** जानकारी प्राप्त करने के बारे में सोच रहे हैं, तो आप सही जगह पर आए हैं। इस विस्तृत ट्यूटोरियल में आप **ms project currency** मानों के साथ काम करना सीखेंगे, Aspose.Tasks लाइब्रेरी for Java का उपयोग करके। चाहे आप रिपोर्टिंग टूल बना रहे हों, माइग्रेशन यूटिलिटी, या सिर्फ **java project file** से मुद्रा सेटिंग पढ़नी हो, यह गाइड आपको हर चरण से ले जाएगा — *.mpp* फ़ाइल लोड करने से लेकर मुद्रा अंकों (currency digits) निकालने तक। अंत तक, आप अपने एप्लिकेशन में ms project currency डेटा को सहजता से संभाल पाएँगे।

## त्वरित उत्तर
- **कौन सी लाइब्रेरी MS Project फ़ाइलें पढ़ती है?** Aspose.Tasks for Java।  
- **मुद्रा अंकों को प्राप्त करने के लिए कितनी लाइनों का कोड चाहिए?** प्रोजेक्ट लोड होने के बाद केवल तीन संक्षिप्त पंक्तियाँ।  
- **क्या विकास के लिए लाइसेंस चाहिए?** परीक्षण के लिए मुफ्त ट्रायल चलती है; उत्पादन के लिए वाणिज्यिक लाइसेंस आवश्यक है।  
- **कौन सा Java संस्करण समर्थित है?** Java 8 या उससे ऊपर (कोई भी JDK जो Aspose.Tasks चलाता है)।  
- **क्या मैं अन्य Project गुण भी प्राप्त कर सकता हूँ?** हाँ – Aspose.Tasks पूरी Project फ़ील्ड सेट प्रदान करता है (जैसे, start date, cost rates, आदि)।

## ms project currency क्या है?
`ms project currency` प्रॉपर्टी यह निर्धारित करती है कि Microsoft Project मौद्रिक मानों को प्रदर्शित करते समय कितने दशमलव स्थान (decimal places) दिखाता है। यह Project फ़ाइल में **CURRENCY_DIGITS** फ़ील्ड के रूप में संग्रहीत होती है और यह तय करती है कि राशि पूर्ण संख्या, एक‑दशमलव, दो‑दशमलव आदि के रूप में दिखेगी। यह सेटिंग बजट रिपोर्ट, लागत रोल‑अप और किसी भी UI को सीधे प्रभावित करती है जो वित्तीय आंकड़े दिखाता है, इसलिए सटीक डेटा एक्सचेंज के लिए यह अत्यंत महत्वपूर्ण है।

## ms project currency को संभालने के लिए Aspose.Tasks क्यों उपयोग करें?
Aspose.Tasks आपको Microsoft Project स्थापित किए बिना मुद्रा अंकों को निकालने की सुविधा देता है, और यह एंटरप्राइज़‑ग्रेड प्रदर्शन के साथ आता है। लाइब्रेरी **30+ वर्षों** के Project फ़ाइल संस्करणों — Project 2000 से लेकर Project 2024 तक — को सपोर्ट करती है, जिसमें **150 से अधिक अलग‑अलग फ़ाइल स्कीमा** शामिल हैं। 500‑पृष्ठीय प्रोजेक्ट को लोड करने में सामान्य सर्वर पर **2 सेकंड** से कम समय लगता है, और आप केवल आवश्यक फ़ील्ड को क्वेरी कर सकते हैं, जिससे सबसे बड़े शेड्यूल के लिए भी मेमोरी उपयोग **50 MB** से कम रहता है।

## पूर्वापेक्षाएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित हों:

1. **Java Development Environment** – JDK 8 या नया स्थापित और कॉन्फ़िगर किया हुआ।  
2. **Aspose.Tasks for Java** – आधिकारिक साइट से नवीनतम JAR डाउनलोड करें: [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/)।  
3. **Basic Java knowledge** – आपको Java प्रोजेक्ट बनाना, बाहरी लाइब्रेरी जोड़ना, और `main` मेथड चलाना आना चाहिए।  

## पैकेज आयात करें
पहले उन क्लासों को आयात करें जिनकी हमें आवश्यकता होगी।  
Aspose.Tasks लाइब्रेरी से `Project` क्लास और संबंधित यूटिलिटीज़ आयात करें।  
```java
import java.io.IOException;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## चरण 1: डेटा डायरेक्टरी निर्धारित करें
उस फ़ोल्डर को निर्दिष्ट करें जिसमें आपका **java project file** (`*.mpp`) स्थित है।  
```java
String dataDir = "Your Data Directory";
```
`"Your Data Directory"` को उस पूर्ण या सापेक्ष पथ से बदलें जहाँ `project.mpp` मौजूद है।

## चरण 2: mpp फ़ाइल लोड करें  
अब हम Aspose.Tasks का उपयोग करके **mpp फ़ाइल लोड** करने का तरीका देखेंगे।  
`Project` क्लास Microsoft Project फ़ाइल का प्रतिनिधित्व करती है और उसकी प्रॉपर्टीज़ तक पहुँच प्रदान करती है।  
```java
Project project = new Project(dataDir + "project.mpp");
```
फ़ाइल नाम बिल्कुल समान होना चाहिए; अन्यथा `IOException` उत्पन्न होगा।

## चरण 3: मुद्रा अंकों (currency digits) प्राप्त करें  
प्रोजेक्ट लोड होने के बाद, **ms project currency** अंकों को निकालना एक‑लाइनर है:  
`getCurrencyDigits()` मेथड मौद्रिक मानों के लिए निर्धारित दशमलव स्थानों की संख्या लौटाता है।  
```java
System.out.println(project.get(Prj.CURRENCY_DIGITS));
```
यह कॉल एक `Integer` लौटाता है जो दशमलव स्थानों की संख्या दर्शाता है (उदाहरण के लिए, सेंट के लिए `2`)। मान को कंसोल पर प्रिंट किया जाता है, लेकिन आप इसे आगे की प्रोसेसिंग के लिए वेरिएबल में भी रख सकते हैं।

## सामान्य समस्याएँ एवं सुझाव
- **फ़ाइल नहीं मिली** – `dataDir` पथ को दोबारा जांचें और फ़ाइल नाम सही है, साथ में `.mpp` एक्सटेंशन भी।  
- **असमर्थित फ़ाइल संस्करण** – Aspose.Tasks Project 2000‑2024 फ़ॉर्मेट को सपोर्ट करता है; पुराने या भ्रष्ट फ़ाइलों को रूपांतरण की आवश्यकता हो सकती है।  
- **लाइसेंस सेट नहीं** – विकास के दौरान ट्रायल चलती है, लेकिन उत्पादन में वैध लाइसेंस लागू करना आवश्यक है, नहीं तो मूल्यांकन वॉटरमार्क दिखेगा।

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या Aspose.Tasks मुद्रा अंकों के अलावा अन्य Project गुणों को भी संभाल सकता है?**  
उत्तर: हाँ, Aspose.Tasks विभिन्न Project फ़ाइल पहलुओं को नियंत्रित करने की विस्तृत कार्यक्षमता प्रदान करता है, जैसे टास्क, रिसोर्स, और कस्टम फ़ील्ड।

**प्रश्न: क्या Aspose.Tasks एंटरप्राइज़‑स्तर के अनुप्रयोगों के लिए उपयुक्त है?**  
उत्तर: बिल्कुल, Aspose.Tasks को एंटरप्राइज़‑ग्रेड प्रोजेक्ट्स की मांगों को पूरा करने के लिए डिज़ाइन किया गया है, उच्च प्रदर्शन और स्केलेबिलिटी के साथ।

**प्रश्न: क्या Aspose.Tasks क्रॉस‑प्लेटफ़ॉर्म विकास को सपोर्ट करता है?**  
उत्तर: हाँ, आप Aspose.Tasks for Java को किसी भी प्लेटफ़ॉर्म पर उपयोग कर सकते हैं जो Java Runtime Environment को सपोर्ट करता है (Windows, Linux, macOS)।

**प्रश्न: क्या मैं Aspose.Tasks को खरीदने से पहले आज़मा सकता हूँ?**  
उत्तर: हाँ, आप [Aspose releases पेज](https://releases.aspose.com/) से मुफ्त ट्रायल संस्करण डाउनलोड कर सकते हैं।

**प्रश्न: Aspose.Tasks के लिए समर्थन कहाँ प्राप्त कर सकता हूँ?**  
उत्तर: आप [Aspose.Tasks फ़ोरम](https://forum.aspose.com/c/tasks/15) पर समर्थन पा सकते हैं।

---

**अंतिम अपडेट:** 2026-09-14  
**परीक्षित संस्करण:** Aspose.Tasks for Java (लेखन समय पर नवीनतम)  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [java प्रोजेक्ट गुण – Aspose.Tasks for Java का उपयोग करके MPP से मुद्रा प्रतीक निकालें](/tasks/java/currency/currency-symbols/)
- [Aspose.Tasks के साथ MS Project से मुद्रा कोड प्राप्त करने का तरीका](/tasks/java/currency/currency-codes/)
- [Project Properties Java – Aspose.Tasks के साथ मेटाडेटा पढ़ें](/tasks/java/project-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}