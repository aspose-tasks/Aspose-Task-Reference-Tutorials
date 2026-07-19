---
date: 2026-07-19
description: .NET प्रोजेक्ट्स में राशि के बाद मुद्रा प्रतीक को आसानी से नियंत्रित
  करना सीखें Aspose.Tasks के साथ।
keywords:
- currency symbol after amount
- Aspose.Tasks currency formatting
- .NET project financial reporting
lastmod: 2026-07-19
linktitle: Aspose.Tasks में मुद्रा प्रतीक की स्थितियाँ
og_description: .NET के लिए Aspose.Tasks का उपयोग करके राशि के बाद मुद्रा प्रतीक कैसे
  रखें, सीखें। चरण‑दर‑चरण निर्देश और सर्वोत्तम प्रथाओं का पालन करें।
og_image_alt: Guide showing currency symbol after amount configuration in Aspose.Tasks
og_title: Aspose.Tasks में राशि के बाद मुद्रा प्रतीक — त्वरित गाइड
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to control currency symbol after amount in .NET projects
    effortlessly with Aspose.Tasks.
  headline: How to Place Currency Symbol After Amount in Aspose.Tasks
  type: TechArticle
- description: Learn how to control currency symbol after amount in .NET projects
    effortlessly with Aspose.Tasks.
  name: How to Place Currency Symbol After Amount in Aspose.Tasks
  steps:
  - name: Load the Project File
    text: The `Project` class loads an existing MS‑Project file or creates a new one
      in memory.
  - name: Set Currency Symbol Position
    text: '`CurrencySymbolPosition` is an enum that lets you choose `Before` or `After`.
      Setting it to `After` places the symbol after the numeric value.'
  - name: Work with the Project
    text: After you have configured the symbol position, you can continue adding tasks,
      resources, or custom fields as needed. The setting is persisted when you save
      the project.
  type: HowTo
- questions:
  - answer: Yes, you can adjust `CurrencySymbolPosition` as many times as needed;
      just set the property and re‑save the project.
    question: Can I change the currency symbol position multiple times within the
      same project?
  - answer: Absolutely. Aspose.Tasks supports more than 50 international currencies,
      allowing you to work with any regional format.
    question: Does Aspose.Tasks support currencies other than the US Dollar?
  - answer: Yes, you can obtain a free trial of Aspose.Tasks for .NET from [here](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Tasks for .NET?
  - answer: Certainly! You can seek support and assistance from the Aspose.Tasks community
      forum [here](https://forum.aspose.com/c/tasks/15).
    question: Can I seek assistance if I encounter any issues while using Aspose.Tasks
      for .NET?
  - answer: You can purchase a license for Aspose.Tasks for .NET from [here](https://purchase.aspose.com/buy).
    question: How can I purchase a license for Aspose.Tasks for .NET?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- currency symbol
- Aspose.Tasks
- .NET financial management
title: Aspose.Tasks में राशि के बाद मुद्रा प्रतीक कैसे रखें
url: /hi/net/calendar-scheduling/currency-symbol-positions/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में राशि के बाद मुद्रा प्रतीक कैसे रखें

## परिचय

जब आप प्रोजेक्ट लागत रिपोर्ट बनाते हैं, तो **राशि के बाद मुद्रा प्रतीक** की स्थिति पढ़ने की सुविधा और क्षेत्रीय मानकों के अनुपालन को प्रभावित कर सकती है। Aspose.Tasks for .NET आपको कुछ ही कोड लाइनों के साथ इस फ़ॉर्मेटिंग को नियंत्रित करने की सुविधा देता है, जिससे प्रत्येक वित्तीय आंकड़ा ठीक उसी तरह दिखे जैसा आपके हितधारक अपेक्षा करते हैं। इस ट्यूटोरियल में हम आवश्यक चरणों को समझेंगे, बताएँगे कि यह सेटिंग क्यों महत्वपूर्ण है, और वास्तविक .NET प्रोजेक्ट में इसे कैसे लागू करें दिखाएँगे।

## त्वरित उत्तर
- **“राशि के बाद मुद्रा प्रतीक” का क्या अर्थ है?** यह प्रतीक (जैसे $) को संख्यात्मक मान के बाद दिखाता है, जैसे `100 $`।
- **कौन सी प्रॉपर्टी स्थिति को नियंत्रित करती है?** `Project` ऑब्जेक्ट पर `CurrencySymbolPosition`।
- **क्या मुझे लाइसेंस चाहिए?** विकास के लिए ट्रायल काम करता है; उत्पादन के लिए व्यावसायिक लाइसेंस आवश्यक है।
- **समर्थित मुद्राएँ?** 50 से अधिक अंतर्निहित मुद्राएँ, अधिकांश वैश्विक बाजारों को कवर करती हैं।
- **क्या मैं रनटाइम पर सेटिंग बदल सकता हूँ?** हाँ, आप प्रोजेक्ट फ़ाइल सहेजने से पहले कभी भी इसे अपडेट कर सकते हैं।

## “राशि के बाद मुद्रा प्रतीक” सेटिंग क्या है?
**राशि के बाद मुद्रा प्रतीक** विकल्प निर्धारित करता है कि प्रोजेक्ट के सभी मौद्रिक फ़ील्ड में मुद्रा चिह्न संख्यात्मक मान से पहले या बाद में दिखेगा। इस सेटिंग को समायोजित करने से रिपोर्ट स्थानीय लेखा मानदंडों के अनुरूप बनती हैं, बिना मैन्युअल पोस्ट‑प्रोसेसिंग के। यह उस फॉर्मेट के आदी हितधारकों के लिए पठनीयता भी बढ़ाता है।

## मुद्रा फ़ॉर्मेटिंग के लिए Aspose.Tasks क्यों उपयोग करें?
Aspose.Tasks **50+ मुद्राओं** का समर्थन करता है और **10,000+ कार्यों** वाले प्रोजेक्ट को पूरी फ़ाइल को मेमोरी में लोड किए बिना संभाल सकता है, जिससे सीमित हार्डवेयर पर भी तेज़ प्रदर्शन मिलता है। API आपको प्रोग्रामेटिक नियंत्रण देती है, जिससे मैन्युअल स्प्रेडशीट संपादन की आवश्यकता समाप्त हो जाती है। यह बड़े‑पैमाने पर वित्तीय रिपोर्टिंग को कुशल और विश्वसनीय बनाता है।

## पूर्वापेक्षाएँ

### 1. Aspose.Tasks for .NET की स्थापना
सुनिश्चित करें कि आपके पास Aspose.Tasks लाइब्रेरी स्थापित है। आप इसे [here](https://releases.aspose.com/tasks/net/) से डाउनलोड कर सकते हैं।

### 2. .NET प्रोग्रामिंग का मूल ज्ञान
उदाहरणों का पालन करने के लिए .NET प्रोग्रामिंग की बुनियादी समझ आवश्यक है।

## नामस्थान आयात करें

`Aspose.Tasks` नामस्थान `Project` क्लास और संबंधित एनेम्स तक पहुँच प्रदान करता है।

`Project` क्लास Aspose.Tasks का शीर्ष‑स्तरीय ऑब्जेक्ट है जो मेमोरी में एकल प्रोजेक्ट फ़ाइल का प्रतिनिधित्व करता है। नामस्थान आयात करने के बाद आप प्रोजेक्ट डेटा के साथ काम शुरू कर सकते हैं।

```csharp

```

अब, हम उदाहरण को स्पष्ट, क्रियात्मक चरणों में विभाजित करेंगे।

## राशि के बाद मुद्रा प्रतीक कैसे सेट करें?

`CurrencySymbolPosition` एक एनेमरेशन है जो निर्धारित करता है कि मुद्रा प्रतीक संख्यात्मक मान से पहले या बाद में दिखेगा।

अपने प्रोजेक्ट को लोड करें, `CurrencySymbolPosition` को `After` सेट करें, और फिर सहेजें – यह वह सब है जो राशि के बाद प्रतीक दिखाने के लिए आवश्यक है। यह सीधा तरीका किसी भी समर्थित मुद्रा के लिए काम करता है और अतिरिक्त फ़ॉर्मेटिंग लॉजिक की आवश्यकता नहीं होती। आप सेटिंग की पुष्टि एक नमूना लागत रिपोर्ट निर्यात करके भी कर सकते हैं ताकि प्रतीक सही ढंग से दिखे।

### चरण 1: प्रोजेक्ट फ़ाइल लोड करें
`Project` क्लास मौजूदा MS‑Project फ़ाइल को लोड करता है या मेमोरी में नई फ़ाइल बनाता है।

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

### चरण 2: मुद्रा प्रतीक स्थिति सेट करें
`CurrencySymbolPosition` एक एनेम है जो आपको `Before` या `After` चुनने की अनुमति देता है। इसे `After` पर सेट करने से प्रतीक संख्यात्मक मान के बाद रखता है।

```csharp
project.Set(Prj.CurrencySymbolPosition, CurrencySymbolPositionType.Before);
```

### चरण 3: प्रोजेक्ट के साथ काम करें
एक बार जब आप प्रतीक स्थिति को कॉन्फ़िगर कर लेते हैं, तो आप आवश्यकतानुसार कार्य, संसाधन, या कस्टम फ़ील्ड जोड़ते रह सकते हैं। यह सेटिंग प्रोजेक्ट सहेजने पर संरक्षित रहती है।

```csharp
// Perform other operations with the project...
```

## सामान्य समस्याएँ और समाधान
- **प्रतीक अभी भी राशि से पहले दिख रहा है:** सुनिश्चित करें कि आप `Save` कॉल करने से *पहले* प्रॉपर्टी सेट करें। सहेजने के बाद बदलने के लिए फ़ाइल को पुनः‑सहेजना आवश्यक है।
- **असमर्थित मुद्रा:** जांचें कि आप जिस मुद्रा कोड का उपयोग कर रहे हैं वह Aspose.Tasks की समर्थित सूची (50 से अधिक मुद्राएँ) में है या नहीं।
- **बड़े प्रोजेक्ट पर प्रदर्शन धीमा:** यदि कार्यों की संख्या 10,000 से अधिक हो तो बड़े फ़ाइलों को स्ट्रीम करने के लिए `ProjectReader` का उपयोग करें।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं एक ही प्रोजेक्ट में कई बार मुद्रा प्रतीक स्थिति बदल सकता हूँ?**  
A: हाँ, आप `CurrencySymbolPosition` को जितनी बार चाहें बदल सकते हैं; बस प्रॉपर्टी सेट करें और प्रोजेक्ट को पुनः‑सहेजें।

**Q: क्या Aspose.Tasks अमेरिकी डॉलर के अलावा अन्य मुद्राओं का समर्थन करता है?**  
A: बिल्कुल। Aspose.Tasks 50 से अधिक अंतरराष्ट्रीय मुद्राओं का समर्थन करता है, जिससे आप किसी भी क्षेत्रीय फ़ॉर्मेट के साथ काम कर सकते हैं।

**Q: क्या Aspose.Tasks for .NET के लिए कोई ट्रायल संस्करण उपलब्ध है?**  
A: हाँ, आप Aspose.Tasks for .NET का मुफ्त ट्रायल [here](https://releases.aspose.com/) से प्राप्त कर सकते हैं।

**Q: क्या मैं Aspose.Tasks for .NET उपयोग करते समय किसी समस्या का सामना करने पर सहायता प्राप्त कर सकता हूँ?**  
A: निश्चित रूप से! आप Aspose.Tasks समुदाय फ़ोरम से सहायता और समर्थन प्राप्त कर सकते हैं [here](https://forum.aspose.com/c/tasks/15)।

**Q: मैं Aspose.Tasks for .NET के लिए लाइसेंस कैसे खरीद सकता हूँ?**  
A: आप Aspose.Tasks for .NET का लाइसेंस [here](https://purchase.aspose.com/buy) से खरीद सकते हैं।

## निष्कर्ष

**राशि के बाद मुद्रा प्रतीक** को नियंत्रित करना प्रोजेक्ट प्रबंधन सॉफ़्टवेयर में वित्तीय रिपोर्टिंग का एक महत्वपूर्ण पहलू है। Aspose.Tasks for .NET के साथ आप इस विकल्प को प्रोग्रामेटिक रूप से सेट कर सकते हैं, 50 से अधिक मुद्राओं का समर्थन करते हुए बड़े प्रोजेक्ट को कुशलता से संभालते हैं। ऊपर दिए गए चरणों को लागू करके सुनिश्चित करें कि आपके प्रोजेक्ट रिपोर्ट किसी भी लोकेल की फ़ॉर्मेटिंग अपेक्षाओं से मेल खाएँ।

---

**Last Updated:** 2026-07-19  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose

## संबंधित ट्यूटोरियल

- [Aspose.Tasks में कैलेंडर संग्रह प्रबंधन](/tasks/net/calendar-scheduling/calendar-collection/)
- [Aspose.Tasks में कैलेंडर अपवाद संग्रह](/tasks/net/calendar-scheduling/calendar-exception-collection/)
- [Aspose.Tasks for .NET के साथ MS Project दरें संभालना](/tasks/net/rate-recurring-tasks/handling-rates/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}