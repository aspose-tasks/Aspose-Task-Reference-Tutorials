---
date: 2026-02-10
description: Aspose.Tasks for Java का उपयोग करके जावा प्रोजेक्ट प्रॉपर्टीज़ जैसे मुद्रा
  प्रतीक को निकालना और अपडेट करना सीखें। प्रोजेक्ट की मुद्रा बदलें और आसानी से मुद्रा
  प्रतीक प्राप्त करें।
linktitle: Extract currency symbol mpp using Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: जावा प्रोजेक्ट प्रॉपर्टीज़ – Aspose.Tasks for Java का उपयोग करके MPP से मुद्रा
  प्रतीक निकालें
url: /hi/java/currency/currency-symbols/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java का उपयोग करके MPP से मुद्रा प्रतीक निकालें

## परिचय
इस ट्यूटोरियल में आप **java project properties** के साथ काम करना सीखेंगे—विशेष रूप से Microsoft Project (MPP) फ़ाइल से मुद्रा प्रतीक निकालना और Aspose.Tasks लाइब्रेरी का उपयोग करके **change currency symbol java** या **retrieve currency symbol java** करना। चाहे आप रिपोर्टिंग टूल बना रहे हों, Project डेटा को वित्तीय सिस्टम में एकीकृत कर रहे हों, या बस UI में सही मुद्रा प्रतीक दिखाना चाहते हों, इस छोटे लेकिन आवश्यक कार्य में महारत हासिल करने से आपके Java एप्लिकेशन अधिक मजबूत और उपयोगकर्ता‑मित्र बनेंगे।

## त्वरित उत्तर
- **“extract currency symbol mpp” का क्या अर्थ है?** इसका मतलब है MPP (Microsoft Project) फ़ाइल में संग्रहीत मुद्रा प्रतीक को पढ़ना।  
- **कौन सी लाइब्रेरी इसे संभालती है?** Aspose.Tasks for Java इस काम के लिए सरल API प्रदान करती है।  
- **क्या लाइसेंस की आवश्यकता है?** विकास के लिए मुफ्त ट्रायल काम करता है; उत्पादन के लिए व्यावसायिक लाइसेंस आवश्यक है।  
- **इसमें कितना समय लगेगा?** नीचे दिया गया कोड उपयोग करके आप एक मिनट से भी कम समय में प्रतीक प्राप्त कर सकते हैं।  
- **क्या मैं प्रतीक भी बदल सकता हूँ?** हाँ – आप उसी `Prj.CURRENCY_SYMBOL` प्रॉपर्टी का उपयोग करके नया मान सेट कर सकते हैं।

## “extract currency symbol mpp” क्या है?
Microsoft Project प्रोजेक्ट फ़ाइल हेडर में मुद्रा प्रतीक (जैसे $, €, £) संग्रहीत करता है। **extract currency symbol mpp** ऑपरेशन उस मान को पढ़ता है ताकि आप इसे प्रोग्रामेटिक रूप से प्रदर्शित या संशोधित कर सकें।

## java project properties में मुद्रा प्रतीक को अपडेट क्यों करें?
प्रोजेक्ट अक्सर कई क्षेत्रों में फैले होते हैं। रन‑टाइम पर **change project currency** या **update currency symbol** करने से आप रिपोर्ट, इनवॉइस या डैशबोर्ड को स्थानीय बाजार के अनुसार अनुकूलित कर सकते हैं, बिना पूरी प्रोजेक्ट फ़ाइल को फिर से बनाने की आवश्यकता के। यह लचीलापन java project properties को प्रभावी ढंग से प्रबंधित करने का मुख्य हिस्सा है।

## पूर्वापेक्षाएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित हों:

1. **Java Development Kit (JDK)** – संस्करण 8 या उससे ऊपर।  
2. **Aspose.Tasks for Java** – नवीनतम JAR [Aspose.Tasks डाउनलोड पृष्ठ](https://releases.aspose.com/tasks/java/) से डाउनलोड करें।  
3. एक वैध **project.mpp** फ़ाइल जिसे आप अपने कोड से संदर्भित कर सकें।

## पैकेज आयात करें
पहले, उन क्लासों को आयात करें जिनकी हमें Project फ़ाइलों के साथ काम करने के लिए आवश्यकता होगी।

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## चरण 1: डेटा डायरेक्टरी निर्धारित करें
ऐप्लिकेशन को बताएं कि आपका *.mpp* फ़ाइल कहाँ स्थित है।

```java
String dataDir = "Your Data Directory";
```

> **Pro tip:** किसी भी मशीन पर काम करने के लिए `System.getProperty("user.dir")` का उपयोग करके एक पूर्ण पाथ बनाएं।

## चरण 2: MS Project फ़ाइल लोड करें
एक `Project` ऑब्जेक्ट बनाएं जो मेमोरी में MPP फ़ाइल का प्रतिनिधित्व करता है।

```java
Project project = new Project(dataDir + "project.mpp");
```

## चरण 3: मुद्रा प्रतीक प्राप्त करें (और वैकल्पिक रूप से बदलें)
अब हम `Prj.CURRENCY_SYMBOL` प्रॉपर्टी पढ़कर **retrieve currency symbol java** करते हैं। आप उसी प्रॉपर्टी को नया स्ट्रिंग असाइन करके **change currency symbol java** (या **change project currency**) भी कर सकते हैं।

```java
// Retrieve the current currency symbol
System.out.println(project.get(Prj.CURRENCY_SYMBOL));

// Example of changing it (uncomment to use)
// project.set(Prj.CURRENCY_SYMBOL, "€");
// System.out.println("New symbol: " + project.get(Prj.CURRENCY_SYMBOL));
```

`System.out.println` कॉल प्रतीक (जैसे `$`) को कंसोल में प्रिंट करता है, जिससे यह पुष्टि होती है कि निष्कर्षण सफल रहा।

## सामान्य समस्याएँ एवं समाधान
| लक्षण | संभावित कारण | समाधान |
|---------|--------------|----------|
| `project.get(...)` पर `NullPointerException` | गलत फ़ाइल पाथ या फ़ाइल नहीं मिली | `dataDir` और फ़ाइल नाम की जाँच करें; डिबग करने के लिए `new File(dataDir).exists()` का उपयोग करें |
| अप्रत्याशित प्रतीक (जैसे `?`) | प्रोजेक्ट गैर‑मानक लोकेल के साथ बनाया गया | सुनिश्चित करें कि स्रोत MPP फ़ाइल वास्तव में मुद्रा प्रतीक निर्धारित करती है; आप ऊपर दिखाए अनुसार प्रोग्रामेटिक रूप से सेट कर सकते हैं |
| लाइसेंस त्रुटि | वैध लाइसेंस फ़ाइल के बिना ट्रायल उपयोग | `Project` ऑब्जेक्ट बनाने से पहले `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` के साथ अपना लाइसेंस लोड करें |

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या मैं Aspose.Tasks का उपयोग करके मुद्रा प्रतीकों के अलावा अन्य प्रोजेक्ट एट्रिब्यूट्स को भी बदल सकता हूँ?**  
उत्तर: हाँ, Aspose.Tasks आपको टास्क, रिसोर्स, असाइनमेंट, कैलेंडर और कई अन्य प्रोजेक्ट प्रॉपर्टीज़ को संपादित करने की सुविधा देता है।

**प्रश्न: क्या Aspose.Tasks विभिन्न संस्करणों की MS Project फ़ाइलों के साथ संगत है?**  
उत्तर: बिल्कुल। यह Project 98 से लेकर नवीनतम रिलीज़ तक के MPP, MPT और XML फ़ॉर्मैट्स को सपोर्ट करता है।

**प्रश्न: क्या Aspose.Tasks डेवलपर्स के लिए दस्तावेज़ीकरण और समर्थन प्रदान करता है?**  
उत्तर: व्यापक API डॉक्यूमेंटेशन, कोड उदाहरण, और एक समर्पित सपोर्ट फ़ोरम Aspose.Tasks वेबसाइट पर उपलब्ध हैं।

**प्रश्न: क्या मैं Aspose.Tasks को खरीदने से पहले आज़मा सकता हूँ?**  
उत्तर: हाँ – एक पूरी तरह कार्यात्मक मुफ्त ट्रायल [Aspose वेबसाइट](https://purchase.aspose.com/buy) से डाउनलोड किया जा सकता है।

**प्रश्न: मैं Aspose.Tasks के लिए अस्थायी लाइसेंस कैसे प्राप्त करूँ?**  
उत्तर: मूल्यांकन उद्देश्यों के लिए अस्थायी लाइसेंस [Aspose अस्थायी‑लाइसेंस पृष्ठ](https://purchase.aspose.com/temporary-license/) पर उपलब्ध है।

---

**अंतिम अपडेट:** 2026-02-10  
**परीक्षित संस्करण:** Aspose.Tasks for Java 24.12 (लेखन समय पर नवीनतम)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}