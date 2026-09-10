---
date: 2026-09-09
description: Aspose.Tasks Java प्रोजेक्ट्स में मुद्रा प्रतीक कैसे बदलें, मुद्रा कोड
  सेट करें, प्रतीकों को समायोजित करें, और Microsoft Project फ़ाइलों के लिए कस्टम फ़ॉर्मेट
  लागू करें, सीखें।
keywords:
- how to change currency symbol
- Aspose.Tasks currency code
- Java project currency
- Microsoft Project formatting
lastmod: 2026-09-09
linktitle: Aspose.Tasks प्रोजेक्ट्स में मुद्रा गुण सेट करें
og_description: Java का उपयोग करके Aspose.Tasks में मुद्रा प्रतीक कैसे बदलें। चरण‑दर‑चरण
  निर्देश, आवश्यकताएँ, और प्रोजेक्ट लागत फ़ॉर्मेट को कस्टमाइज़ करने के टिप्स जानें।
og_image_alt: Screenshot of Aspose.Tasks Java code setting currency symbol
og_title: Aspose.Tasks में मुद्रा प्रतीक कैसे बदलें – Java गाइड
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to change currency symbol in Aspose.Tasks Java projects,
    set currency codes, adjust symbols, and apply custom formats for Microsoft Project
    files.
  headline: How to change currency symbol in Aspose.Tasks projects – Java guide
  type: TechArticle
- description: Learn how to change currency symbol in Aspose.Tasks Java projects,
    set currency codes, adjust symbols, and apply custom formats for Microsoft Project
    files.
  name: How to change currency symbol in Aspose.Tasks projects – Java guide
  steps:
  - name: Define the data directory
    text: Choose a folder that holds your source files and where the output will be
      written. Make sure the directory exists and your Java process has write permission.
  - name: Create a new project instance
    text: '`Project` class is Aspose.Tasks'' top‑level object that represents a single
      Project file in memory. Instantiating it creates a blank project ready for configuration.'
  - name: Set currency properties
    text: Here you configure the currency code, number of decimal digits, the symbol
      itself, and the symbol’s position. - **Currency code** – a three‑letter ISO
      4217 code such as `AUD` or `USD`. - **Decimal digits** – typically 2 for most
      currencies. - **Currency symbol** – the character or string displayed w
  - name: Save the updated project
    text: Write the project back to disk using the desired format. The XML format
      is human‑readable, while `SaveFileFormat.MPP` preserves full compatibility with
      Microsoft Project.
  - name: Confirm success
    text: Print a short message or log entry so you know the operation completed without
      errors. This is especially useful in automated pipelines.
  type: HowTo
- questions:
  - answer: Yes, you can assign different currency settings to individual resources
      or tasks by modifying their respective cost fields after the project‑level currency
      is defined.
    question: Can I set multiple currencies in a single project using Aspose.Tasks?
  - answer: Absolutely. The library supports MPP files from Project 2000 up to the
      latest releases, as well as XML and other interchange formats.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes, you can define custom symbols, decimal digits, and positioning to
      meet any regional requirement, and these settings are persisted in the saved
      file.
    question: Does Aspose.Tasks provide support for custom currency formats?
  - answer: Certainly. The API is pure Java, so it works seamlessly with Spring, Hibernate,
      Maven, Gradle, and other ecosystems.
    question: Can I integrate Aspose.Tasks with other Java frameworks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community assistance, or consult the official documentation for detailed API
      references.
    question: Where can I find additional help or examples?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- currency symbol
- Aspose.Tasks
- Java API
- Microsoft Project
- project cost formatting
title: Aspose.Tasks प्रोजेक्ट्स में मुद्रा प्रतीक कैसे बदलें – Java गाइड
url: /hi/java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में मुद्रा प्रतीक कैसे बदलें – Java गाइड

## परिचय
इस ट्यूटोरियल में आप Aspose.Tasks Java API का उपयोग करके Microsoft Project फ़ाइल के लिए **मुद्रा प्रतीक कैसे बदलें** सीखेंगे। चाहे आप विदेशी क्लाइंट के लिए रिपोर्ट तैयार कर रहे हों, कई क्षेत्रों में बजट को एकीकृत कर रहे हों, या बस अपनी कंपनी के लेखा मानकों से मेल खाने की आवश्यकता हो, मुद्रा प्रतीक को समायोजित करने से प्रत्येक लागत‑संबंधित फ़ील्ड सही मौद्रिक चिह्न प्रदर्शित करता है। यह गाइड विकास पर्यावरण सेटअप से लेकर नई या मौजूदा प्रोजेक्ट फ़ाइल में परिवर्तन को सहेजने तक के हर चरण को दर्शाता है।

## त्वरित उत्तर
- **कौनसी लाइब्रेरी आवश्यक है?** Aspose.Tasks for Java.  
- **क्या मैं मुद्रा प्रतीक बदल सकता हूँ?** हाँ – `Prj.CURRENCY_SYMBOL` सेट करें और `CurrencySymbolPositionType` चुनें।  
- **कौनसे फ़ाइल फ़ॉर्मेट समर्थित हैं?** `XML`, `MPP`, और `SaveFileFormat` के माध्यम से कई अन्य फ़ॉर्मेट।  
- **क्या विकास के लिए लाइसेंस चाहिए?** टेस्टिंग के लिए एक फ्री ट्रायल काम करता है; प्रोडक्शन के लिए लाइसेंस आवश्यक है।  
- **इम्प्लीमेंटेशन में कितना समय लगेगा?** बेसिक सेटअप के लिए लगभग 5‑10 मिनट।

## Aspose.Tasks में Java का उपयोग करके मुद्रा प्रतीक कैसे बदलें?
लक्षित प्रोजेक्ट को लोड करें (या नया बनाएं), इच्छित मुद्रा गुण सेट करें, और फ़ाइल सहेजें। पूरी प्रक्रिया तीन API कॉल्स में होती है: `Project` ऑब्जेक्ट बनाना या लोड करना, मुद्रा कोड, प्रतीक और स्थिति असाइन करना, फिर `project.save` को कॉल करना। यह तरीका नए प्रोजेक्ट और मौजूदा फ़ाइल दोनों के लिए काम करता है, बिना Microsoft Project को इंस्टॉल किए।

## मुद्रा बदलने के लिए Aspose.Tasks क्यों उपयोग करें?
Aspose.Tasks **30+ मुद्रा‑संबंधित प्रॉपर्टीज़ के लिए पूर्ण API कवरेज** प्रदान करता है, जिससे आप कोड, प्रतीक, दशमलव अंक, और पोजिशनिंग एक ही जगह पर परिभाषित कर सकते हैं। यह लाइब्रेरी सामान्य सर्वर हार्डवेयर पर एक सेकंड से कम समय में सैकड़ों पृष्ठों वाली प्रोजेक्ट फ़ाइलों को प्रोसेस करती है, और यह Windows, Linux, और macOS पर अतिरिक्त निर्भरताओं के बिना काम करती है।

## पूर्वापेक्षाएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास है:

1. **Java Development Kit (JDK) 8 या उससे ऊपर** – API को कम से कम JDK 8 चाहिए।  
2. **Aspose.Tasks for Java** – नवीनतम JAR [Aspose.Tasks download page](https://releases.aspose.com/tasks/java/) से डाउनलोड करें।  
3. **एक IDE** – Eclipse, IntelliJ IDEA, या कोई भी एडिटर जो Java सपोर्ट करता हो।  
4. **एक लिखने योग्य फ़ोल्डर** – जहाँ जेनरेटेड प्रोजेक्ट फ़ाइल सहेजी जाएगी।

## पैकेज इम्पोर्ट करें
निम्नलिखित क्लासेज़ आपको प्रोजेक्ट प्रॉपर्टीज़, फ़ाइल हैंडलिंग, और मुद्रा सेटिंग्स तक पहुँच देती हैं।  

`Project` – मेमोरी में Microsoft Project फ़ाइल का प्रतिनिधित्व करता है।  
`Prj` – सभी प्रोजेक्ट‑लेवल प्रॉपर्टीज़ के कॉन्स्टैंट्स रखता है, जिसमें मुद्रा फ़ील्ड शामिल हैं।  
`CurrencySymbolPositionType` – मुद्रा प्रतीक की संभावित स्थितियों (राशि से पहले या बाद) को एनेमरेट करता है।  

कोड द्वारा प्रोजेक्ट को मैनीपुलेट करने से पहले ये इम्पोर्ट्स आवश्यक हैं।

## स्टेप‑बाय‑स्टेप गाइड

### चरण 1: डेटा डायरेक्टरी निर्धारित करें
एक फ़ोल्डर चुनें जिसमें आपके स्रोत फ़ाइलें हों और जहाँ आउटपुट लिखा जाएगा। सुनिश्चित करें कि डायरेक्टरी मौजूद है और आपका Java प्रोसेस लिखने की अनुमति रखता है।

### चरण 2: नया प्रोजेक्ट इंस्टेंस बनाएं
`Project` क्लास Aspose.Tasks का टॉप‑लेवल ऑब्जेक्ट है जो मेमोरी में एक सिंगल प्रोजेक्ट फ़ाइल का प्रतिनिधित्व करता है। इसे इंस्टैंशिएट करने से एक खाली प्रोजेक्ट बनता है जो कॉन्फ़िगरेशन के लिए तैयार है।

### चरण 3: मुद्रा प्रॉपर्टीज़ सेट करें
यहाँ आप मुद्रा कोड, दशमलव अंकों की संख्या, स्वयं प्रतीक, और प्रतीक की स्थिति कॉन्फ़िगर करते हैं।  

- **Currency code** – `AUD` या `USD` जैसे तीन‑अक्षर ISO 4217 कोड।  
- **Decimal digits** – अधिकांश मुद्राओं के लिए सामान्यतः 2।  
- **Currency symbol** – राशि के साथ दिखने वाला कैरेक्टर या स्ट्रिंग, जैसे `$` या `€`।  
- **Symbol position** – `CurrencySymbolPositionType.Before` प्रतीक को संख्या से पहले रखता है; `After` इसे बाद में रखता है।

ये सेटिंग्स प्रोजेक्ट में प्रत्येक लागत‑संबंधित फ़ील्ड (रिसोर्स रेट्स, टास्क बजट आदि) को प्रभावित करती हैं।  

> **Pro tip:** यदि आपको मौजूदा फ़ाइल के लिए मुद्रा बदलनी है, तो ऊपर दिए सेटिंग्स को लागू करने से पहले `new Project("file.mpp")` से लोड करें।

### चरण 4: अपडेटेड प्रोजेक्ट सहेजें
इच्छित फ़ॉर्मेट का उपयोग करके प्रोजेक्ट को डिस्क पर वापस लिखें। XML फ़ॉर्मेट मानव‑पठनीय है, जबकि `SaveFileFormat.MPP` Microsoft Project के साथ पूर्ण संगतता बनाए रखता है।

### चरण 5: सफलता की पुष्टि करें
एक छोटा संदेश या लॉग एंट्री प्रिंट करें ताकि आपको पता चले कि ऑपरेशन बिना त्रुटियों के पूरा हुआ। यह ऑटोमेटेड पाइपलाइन में विशेष रूप से उपयोगी है।

## सामान्य समस्याएँ और समाधान
| समस्या | कारण | समाधान |
|-------|--------|-----|
| **`project.save` पर `NullPointerException`** | `dataDir` वैध पाथ नहीं है या लिखने की अनुमति नहीं है। | सुनिश्चित करें कि डायरेक्टरी मौजूद है और आपका Java प्रोसेस लिखने की अनुमति रखता है। |
| **मुद्रा प्रतीक नहीं दिख रहा** | आपके लोकेल के लिए प्रतीक की स्थिति गलत सेट है। | यदि प्रतीक राशि से पहले होना चाहिए तो `CurrencySymbolPositionType.Before` का उपयोग करें। |
| **प्रोजेक्ट फ़ाइल MS Project में नहीं खुलती** | असंगत सेटिंग्स के साथ पुराने फ़ॉर्मेट में सहेजने के कारण। | नवीनतम MS Project संस्करणों के साथ पूर्ण संगतता के लिए `SaveFileFormat.MPP` का उपयोग करके सहेजें। |

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं Aspose.Tasks का उपयोग करके एक ही प्रोजेक्ट में कई मुद्राएँ सेट कर सकता हूँ?**  
A: हाँ, आप प्रोजेक्ट‑लेवल मुद्रा निर्धारित करने के बाद व्यक्तिगत रिसोर्स या टास्क के संबंधित लागत फ़ील्ड को संशोधित करके अलग-अलग मुद्रा सेटिंग्स असाइन कर सकते हैं।

**Q: क्या Aspose.Tasks विभिन्न संस्करणों की Microsoft Project फ़ाइलों के साथ संगत है?**  
A: बिल्कुल। लाइब्रेरी Project 2000 से लेकर नवीनतम रिलीज़ तक के MPP फ़ाइलों, साथ ही XML और अन्य इंटरचेंज फ़ॉर्मेट्स को सपोर्ट करती है।

**Q: क्या Aspose.Tasks कस्टम मुद्रा फ़ॉर्मेट्स के लिए समर्थन प्रदान करता है?**  
A: हाँ, आप किसी भी क्षेत्रीय आवश्यकता को पूरा करने के लिए कस्टम प्रतीक, दशमलव अंक, और पोजिशनिंग परिभाषित कर सकते हैं, और ये सेटिंग्स सहेजी गई फ़ाइल में संरक्षित रहती हैं।

**Q: क्या मैं Aspose.Tasks को अन्य Java फ्रेमवर्क्स के साथ इंटीग्रेट कर सकता हूँ?**  
A: निश्चित रूप से। API शुद्ध Java है, इसलिए यह Spring, Hibernate, Maven, Gradle और अन्य इकोसिस्टम्स के साथ सहजता से काम करता है।

**Q: अतिरिक्त मदद या उदाहरण कहाँ मिल सकते हैं?**  
A: समुदाय सहायता के लिए [Aspose.Tasks फ़ोरम](https://forum.aspose.com/c/tasks/15) पर जाएँ, या विस्तृत API रेफ़रेंसेज़ के लिए आधिकारिक दस्तावेज़ देखें।

## निष्कर्ष
अब आप Java का उपयोग करके Aspose.Tasks प्रोजेक्ट्स में **मुद्रा प्रतीक कैसे बदलें** जानते हैं, मुद्रा कोड सेट करना, दशमलव अंकों को समायोजित करना, और कस्टम प्रतीक लागू करना। ये क्षमताएँ आपको स्थानीयकृत लागत रिपोर्ट बनाने, प्रोजेक्ट बजट को क्षेत्रीय लेखा मानकों के साथ संरेखित करने, और वैश्विक टीमों में Microsoft Project फ़ाइलों को सुसंगत रखने में मदद करती हैं।

---

**अंतिम अपडेट:** 2026-09-09  
**परीक्षित संस्करण:** Aspose.Tasks for Java 24.11  
**लेखक:** Aspose  








```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

```java
String dataDir = "Your Data Directory";
```

```java
Project project = new Project();
```

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

```java
System.out.println("Process completed Successfully");
```

## संबंधित ट्यूटोरियल

- [java प्रोजेक्ट प्रॉपर्टीज – Aspose.Tasks for Java का उपयोग करके MPP से मुद्रा प्रतीक निकालें](/tasks/java/currency/currency-symbols/)
- [Aspose.Tasks प्रोजेक्ट्स के साथ Java में मुद्रा प्रॉपर्टीज़ पढ़ें](/tasks/java/currency-properties/read-properties/)
- [Aspose.Tasks के साथ Java में मुद्रा कोड प्रबंधित करें](/tasks/java/currency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}