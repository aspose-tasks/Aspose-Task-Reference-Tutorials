---
date: 2026-09-14
description: Java में Aspose.Tasks का उपयोग करके मुद्रा स्वरूप कैसे बदलें और मुद्रा
  गुण पढ़ें, सीखें। मुद्रा कोड निकालें, मुद्रा प्रतीक प्राप्त करें, और MS Project
  फ़ाइलों में प्रोजेक्ट मुद्रा को अपडेट करें।
keywords:
- change currency format
- retrieve currency symbol
- update project currency
- extract currency code java
lastmod: 2026-09-14
linktitle: मुद्रा स्वरूप कैसे बदलें
og_description: Java में Aspose.Tasks का उपयोग करके मुद्रा स्वरूप कैसे बदलें और मुद्रा
  गुण पढ़ें, सीखें। मुद्रा कोड निकालने और प्रोजेक्ट मुद्रा को अपडेट करने के लिए चरण‑दर‑चरण
  मार्गदर्शिका।
og_image_alt: Tutorial showing how to change currency format in Aspose.Tasks for Java
og_title: Java में Aspose.Tasks के साथ मुद्रा स्वरूप कैसे बदलें
schemas:
- author: Aspose
  dateModified: '2026-09-14'
  description: Learn how to change currency format and read currency properties in
    Java using Aspose.Tasks. Extract currency code, retrieve currency symbol, and
    update project currency in MS Project files.
  headline: How to change currency format in Java with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes. Use `Project.setCurrencyCode()` and related methods, then save the
      project again.
    question: Can I change the currency after the project is already saved?
  - answer: The numeric values remain unchanged; only the display format (symbol,
      decimal separator) is updated. You must recalculate costs if you need conversion
      between currencies.
    question: Does changing the currency affect existing cost values?
  - answer: Aspose.Tasks supports any ISO‑4217 currency code, so you’re effectively
      unlimited.
    question: Are there any limits on the number of currencies I can define?
  - answer: The library falls back to the default currency (USD) and logs a warning;
      you can override this by setting the desired currency manually.
    question: What happens if I open a project with an unsupported currency code?
  - answer: Absolutely. The same API works for both *.mpp* and *.xml* formats.
    question: Is it possible to read/write currency properties in a Project XML file?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- change currency format
- Aspose.Tasks
- Java project management
- currency handling
title: Java में Aspose.Tasks के साथ मुद्रा स्वरूप कैसे बदलें
url: /hi/java/currency-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks के साथ Java में मुद्रा गुण पढ़ें

## परिचय
इस ट्यूटोरियल में आप सीखेंगे कि कैसे **मुद्रा स्वरूप बदलें** और Aspose.Tasks का उपयोग करने वाले Java प्रोजेक्ट्स में मुद्रा गुण पढ़ें। सटीक वित्तीय डेटा बहुराष्ट्रीय टीमों के लिए आवश्यक है, और इन APIs में महारत हासिल करने से आप ISO‑4217 कोड निकाल सकते हैं, मुद्रा प्रतीक प्राप्त कर सकते हैं, और प्रोजेक्ट की मौद्रिक सेटिंग्स को मैन्युअल स्प्रेडशीट संपादन के बिना अपडेट कर सकते हैं।

## त्वरित उत्तर
- **“read currency” का क्या अर्थ है?** यह प्रोजेक्ट फ़ाइल के भीतर संग्रहीत मुद्रा कोड, प्रतीक, और संख्या‑स्वरूप सेटिंग्स को निकालने का अर्थ है।  
- **मुद्रा सेटिंग्स को क्यों समायोजित करें?** लागत रिपोर्टों को क्षेत्रीय मानकों के साथ संरेखित करने और रूपांतरण त्रुटियों से बचने के लिए।  
- **क्या मुझे लाइसेंस की आवश्यकता है?** हां – उत्पादन के लिए एक वैध Aspose.Tasks for Java लाइसेंस आवश्यक है; मूल्यांकन के लिए एक मुफ्त ट्रायल काम करता है।  
- **कौन से Project संस्करण समर्थित हैं?** दोनों *.mpp* (Project 2007‑2024) और *.xml* फ़ॉर्मेट पूरी तरह से समर्थित हैं, जो 20 से अधिक वर्षों के फ़ाइल संस्करणों को कवर करते हैं।  
- **क्या कोई अतिरिक्त सेटअप आवश्यक है?** सिर्फ Aspose.Tasks for Java JAR को अपने क्लासपाथ में जोड़ें और संबंधित क्लासेस को इम्पोर्ट करें।  

## Aspose.Tasks प्रोजेक्ट्स में Java में मुद्रा गुण पढ़ें
प्रोजेक्ट मैनेजमेंट के गतिशील क्षेत्र में, मुद्रा विवरण निकालना सटीक लागत विश्लेषण के लिए आवश्यक है। हमारा समर्पित गाइड **[Aspose.Tasks प्रोजेक्ट्स में मुद्रा गुण पढ़ना](./read-properties/)** आपको हर चरण के माध्यम से ले जाता है—प्रोजेक्ट फ़ाइल खोलने से लेकर मुद्रा कोड, प्रतीक, और स्वरूप प्राप्त करने तक। ट्यूटोरियल का पालन करके आप सक्षम होंगे:

* पूरे प्रोजेक्ट में उपयोग किया गया मुद्रा कोड (जैसे USD, EUR) प्राप्त करें।  
* मुद्रा प्रतीक और संख्या‑स्वरूप सेटिंग्स तक पहुंचें।  
* इस जानकारी का उपयोग करके स्थानीयकृत लागत रिपोर्ट बनाएं या वित्तीय डैशबोर्ड में फ़ीड करें।  

मुद्रा को पढ़ने की समझ सुनिश्चित करती है कि आप प्रोजेक्ट बजट का ऑडिट कर सकें, विभिन्न क्षेत्रों में लागत की तुलना कर सकें, और लेखा मानकों के साथ अनुपालन बनाए रख सकें।

## Aspose.Tasks के साथ Java में मुद्रा कोड निकालना कैसे
`Project.getCurrencyCode()` मेथड प्रोजेक्ट की मौद्रिक इकाई के लिए तीन-अक्षरीय ISO‑4217 पहचानकर्ता लौटाता है।

**Direct answer:** `project.getCurrencyCode()` को कॉल करके मुद्रा कोड प्राप्त करें जैसे **USD** या **EUR**; आप फिर इस मान को संग्रहित, लॉग, या बाहरी वित्तीय सेवाओं को रूपांतरण के लिए पास कर सकते हैं। यह एक‑लाइन कॉल आपको एक विश्वसनीय, मानकों‑आधारित पहचानकर्ता देता है जो सभी समर्थित Project संस्करणों में काम करता है।  
यह मेथड ERP सिस्टम्स के साथ प्रोजेक्ट डेटा को सिंक्रनाइज़ करने का तेज़ तरीका प्रदान करता है, जो एक मानकीकृत कोड की अपेक्षा करते हैं।

## Aspose.Tasks के साथ Java में मुद्रा स्वरूप समायोजित करना कैसे
मौद्रिक मानों के दृश्य प्रतिनिधित्व को बदलना तीन सरल प्रॉपर्टीज़ के माध्यम से किया जाता है।

`project.setCurrencySymbol(String)` मौद्रिक मानों के लिए प्रदर्शित मुद्रा प्रतीक सेट करता है।  
`project.setCurrencyDecimalSeparator(char)` पूर्णांक भाग और भिन्न भाग को अलग करने के लिए उपयोग किए जाने वाले अक्षर को परिभाषित करता है।  
`project.setCurrencyThousandsSeparator(char)` हजारों के समूहों को अलग करने के लिए उपयोग किए जाने वाले अक्षर को परिभाषित करता है।  

**Direct answer:** क्रमशः प्रतीक, दशमलव विभाजक, और हजार विभाजक को परिभाषित करने के लिए `project.setCurrencySymbol("€")`, `project.setCurrencyDecimalSeparator(",")`, और `project.setCurrencyThousandsSeparator(".")` का उपयोग करें—यह एक ही बार में मुद्रा स्वरूप को पूरी तरह बदल देता है। इन सेटिंग्स को समायोजित करने से यह सुनिश्चित होता है कि प्रत्येक हितधारक संख्याओं को परिचित शैली में देखे, जिससे गलतफहमी कम हो।

* `project.setCurrencySymbol("€")` – दृश्य प्रतीक सेट करता है।  
* `project.setCurrencyDecimalSeparator(",")` – दशमलव विभाजक को परिभाषित करता है।  
* `project.setCurrencyThousandsSeparator(".")` – हजार विभाजक को परिभाषित करता है।  

## Aspose.Tasks प्रोजेक्ट्स में मुद्रा गुण सेट करना कैसे
जब कोई प्रोजेक्ट नए बाजार में जाता है या क्लाइंट अलग मौद्रिक स्वरूप का अनुरोध करता है, तो आपको प्रोग्रामेटिक रूप से मुद्रा अपडेट करनी होगी।

`project.setCurrencyCode(String)` प्रोजेक्ट के लिए ISO‑4217 मुद्रा कोड निर्धारित करता है।

**Direct answer:** `project.setCurrencyCode("GBP")` को `project.setCurrencySymbol("£")` और उपयुक्त विभाजकों के साथ बुलाएँ, फिर प्रोजेक्ट को सहेजें; लाइब्रेरी सभी डिस्प्ले सेटिंग्स को अपडेट करती है जबकि मौजूदा लागत डेटा को संरक्षित रखती है। यह तरीका आपको आपके शेड्यूल की वित्तीय प्रस्तुति पर पूर्ण नियंत्रण देता है।

हमारा चरण‑दर‑चरण गाइड **[Aspose.Tasks प्रोजेक्ट्स में मुद्रा गुण सेट करना](./set-properties/)** बताता है कि कैसे:

* पूरे प्रोजेक्ट के लिए नया मुद्रा कोड और प्रतीक निर्धारित करें।  
* स्थानीय मानकों से मेल खाने के लिए संख्या स्वरूप (दशमलव स्थान, हजार विभाजक) को समायोजित करें।  
* अपडेटेड प्रोजेक्ट फ़ाइल को बिना किसी मौजूदा डेटा को खोए सहेजें।  

मुद्रा सेट करने में महारत हासिल करके आप तुरंत USD, GBP, JPY, या किसी भी समर्थित मुद्रा के बीच स्विच कर सकते हैं।

## Aspose.Tasks में मुद्रा हैंडलिंग में महारत क्यों हासिल करें?
सही मुद्रा हैंडलिंग महंगी गलतफहमियों को समाप्त करती है और वैश्विक सहयोग को सरल बनाती है।

**Direct answer:** मुद्रा हैंडलिंग में महारत हासिल करने से आप प्रत्येक टीम के मूल स्वरूप में लागत प्रस्तुत कर सकते हैं, सटीक रिपोर्टिंग सुनिश्चित कर सकते हैं, क्षेत्रीय लेखा मानकों का पालन कर सकते हैं, और स्वचालित वित्तीय वर्कफ़्लो सक्षम कर सकते हैं—प्रोजेक्ट प्रति मैन्युअल री‑फ़ॉर्मेटिंग में घंटों की बचत।

* **वैश्विक सहयोग:** विभिन्न देशों की टीमें अपनी मूल स्वरूप में लागत देख सकती हैं।  
* **सटीक रिपोर्टिंग:** बजट को प्रभावित करने वाली राउंडिंग या रूपांतरण त्रुटियों को रोकें।  
* **अनुपालन:** क्षेत्रीय लेखा मानकों और क्लाइंट विशिष्टताओं के साथ संरेखित रहें।  
* **ऑटोमेशन:** प्रोजेक्ट जनरेशन के दौरान प्रोग्रामेटिक रूप से मुद्रा सेटिंग्स लागू करके मैन्युअल संपादन को कम करें।  

## वास्तविक‑दुनिया उपयोग मामलों
* **बहु‑राष्ट्रीय प्रोजेक्ट्स:** यूरोप और उत्तर अमेरिका में साइट्स प्रबंधित करने वाली एक निर्माण फर्म को दोनों EUR और USD में बजट प्रस्तुत करने की आवश्यकता होती है।  
* **वित्तीय ऑडिट:** ऑडिटर्स को प्रत्येक लागत प्रविष्टि के लिए मुद्रा संदर्भ का स्पष्ट दृश्य चाहिए।  
* **डायनामिक प्राइसिंग मॉडल:** SaaS प्रदाता ग्राहक की स्थानीय मुद्रा के आधार पर सब्सक्रिप्शन लागत को समायोजित करते हैं।  

## सामान्य कठिनाइयाँ और सुझाव
* **Pitfall:** कोड बदलने के बाद मुद्रा प्रतीक को अपडेट करना भूल जाना।  
  **Tip:** कोड और प्रतीक दोनों को साथ में सेट करें ताकि डिस्प्ले में असंगति न हो।  
* **Pitfall:** कोड चलाने वाली मशीन के डिफ़ॉल्ट लोकेल पर निर्भर रहना।  
  **Tip:** अपने Aspose.Tasks कोड में वांछित मुद्रा स्वरूप को स्पष्ट रूप से निर्दिष्ट करें ताकि विभिन्न वातावरणों में स्थिरता बनी रहे।  

## मुद्रा गुण ट्यूटोरियल्स
### [Aspose.Tasks प्रोजेक्ट्स में मुद्रा गुण पढ़ें](./read-properties/)
Aspose.Tasks for Java का उपयोग करके MS Project फ़ाइलों से मुद्रा जानकारी निकालना सीखें। चरण‑दर‑चरण गाइड प्रदान किया गया है।

### [Aspose.Tasks प्रोजेक्ट्स में मुद्रा गुण सेट करें](./set-properties/)
Java का उपयोग करके Aspose.Tasks प्रोजेक्ट्स में मुद्रा गुण सेट करना सीखें। Microsoft Project फ़ाइलों को आसानी से संभालें।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं प्रोजेक्ट सहेजे जाने के बाद मुद्रा बदल सकता हूँ?**  
A: हाँ। `Project.setCurrencyCode()` और संबंधित मेथड्स का उपयोग करें, फिर प्रोजेक्ट को फिर से सहेजें।

**Q: क्या मुद्रा बदलने से मौजूदा लागत मान प्रभावित होते हैं?**  
A: संख्यात्मक मान अपरिवर्तित रहते हैं; केवल डिस्प्ले स्वरूप (प्रतीक, दशमलव विभाजक) अपडेट होता है। यदि आपको मुद्राओं के बीच रूपांतरण चाहिए तो आपको लागतों की पुनः गणना करनी होगी।

**Q: क्या मैं कितनी भी मुद्रा परिभाषित कर सकता हूँ, इसमें कोई सीमा है?**  
A: Aspose.Tasks किसी भी ISO‑4217 मुद्रा कोड का समर्थन करता है, इसलिए आप प्रभावी रूप से असीमित हैं।

**Q: यदि मैं किसी असमर्थित मुद्रा कोड वाले प्रोजेक्ट को खोलता हूँ तो क्या होता है?**  
A: लाइब्रेरी डिफ़ॉल्ट मुद्रा (USD) पर वापस आती है और एक चेतावनी लॉग करती है; आप इसे मैन्युअल रूप से वांछित मुद्रा सेट करके ओवरराइड कर सकते हैं।

**Q: क्या Project XML फ़ाइल में मुद्रा गुण पढ़ना/लिखना संभव है?**  
A: बिल्कुल। वही API दोनों *.mpp* और *.xml* फ़ॉर्मेट्स के लिए काम करता है।

**अंतिम अपडेट:** 2026-09-14  
**परीक्षित संस्करण:** Aspose.Tasks for Java 24.12  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल्स

- [java प्रोजेक्ट प्रॉपर्टीज – Aspose.Tasks for Java का उपयोग करके MPP से मुद्रा प्रतीक निकालें](/tasks/java/currency/currency-symbols/)
- [Aspose.Tasks के साथ MS Project से मुद्रा कैसे प्राप्त करें](/tasks/java/currency/currency-codes/)
- [प्रोजेक्ट प्रॉपर्टीज Java – Aspose.Tasks के साथ मेटाडेटा पढ़ें](/tasks/java/project-properties/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}