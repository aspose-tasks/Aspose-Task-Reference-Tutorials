---
date: 2025-12-25
description: Aspose Tasks Java ट्यूटोरियल का अन्वेषण करें ताकि आप MS Project फ़ाइलों
  के प्रोजेक्ट संस्करण को निर्धारित करना सीख सकें। कोड उदाहरणों के साथ चरण‑दर‑चरण
  मार्गदर्शिका।
linktitle: Determine Project Version with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 'Aspose Tasks Java ट्यूटोरियल: MS प्रोजेक्ट संस्करण निर्धारित करें'
url: /hi/java/project-management/determine-version/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose Tasks Java ट्यूटोरियल: MS Project संस्करण निर्धारित करें

## परिचय
इस **aspose tasks java tutorial** में आप जानेंगे कि कैसे प्रोग्रामेटिक रूप से Aspose.Tasks लाइब्रेरी for Java का उपयोग करके Microsoft Project फ़ाइल का संस्करण पता किया जाए। फ़ाइल संस्करण को जानने से आप संगतता समस्याओं को संभाल सकते हैं, माइग्रेशन नीतियों को लागू कर सकते हैं, या बस यह लॉग कर सकते हैं कि किस Project रिलीज़ ने फ़ाइल बनाई। हम हर चरण को विस्तार से बताएँगे—पर्यावरण सेटअप से लेकर संस्करण और अंतिम‑सेव की तिथि प्रिंट करने तक—ताकि आप इस जांच को किसी भी Java एप्लिकेशन में आत्मविश्वास के साथ एकीकृत कर सकें।

## त्वरित उत्तर
- **इस ट्यूटोरियल में क्या कवर किया गया है?** Aspose.Tasks for Java के साथ MS Project फ़ाइल संस्करण निर्धारित करना।  
- **क्या मुझे Microsoft Project स्थापित करने की आवश्यकता है?** नहीं, Aspose.Tasks स्वतंत्र रूप से काम करता है।  
- **कौन से फ़ाइल फ़ॉर्मेट समर्थित हैं?** XML‑आधारित Project फ़ाइलें (MPP, XML, आदि)।  
- **इम्प्लीमेंटेशन में कितना समय लगता है?** बुनियादी जांच के लिए लगभग 5‑10 मिनट।  
- **क्या लाइसेंस आवश्यक है?** मूल्यांकन के लिए एक मुफ्त ट्रायल काम करता है; उत्पादन के लिए लाइसेंस आवश्यक है।

## Aspose Tasks Java ट्यूटोरियल क्या है?
एक **aspose tasks java tutorial** Java प्रोजेक्ट्स में Aspose.Tasks API के उपयोग के लिए व्यावहारिक मार्गदर्शन प्रदान करता है। यह आपको दिखाता है कि Microsoft Project डेटा को कैसे पढ़ें, संशोधित करें और विश्लेषण करें, बिना Microsoft Project की आवश्यकता के।

## प्रोजेक्ट संस्करण निर्धारित करने के लिए Aspose.Tasks क्यों उपयोग करें?
- **Microsoft Project पर कोई निर्भरता नहीं** – सर्वर‑साइड ऑटोमेशन के लिए उत्तम।  
- **सटीक संस्करण मेटाडेटा** – सटीक SAVE_VERSION और LAST_SAVED फ़ील्ड प्राप्त करें।  
- **क्रॉस‑प्लेटफ़ॉर्म** – किसी भी OS पर काम करता है जो Java को सपोर्ट करता है।  
- **उच्च प्रदर्शन** – बैच प्रोसेसिंग के लिए उपयुक्त हल्का पार्सिंग।

## पूर्वापेक्षाएँ
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

1. **Java Development Kit (JDK)** – कोई भी नवीनतम JDK (8 या उससे ऊपर)।  
2. **Aspose.Tasks for Java JAR** – इसे [वेबसाइट](https://releases.aspose.com/tasks/java/) से डाउनलोड करें और अपने प्रोजेक्ट की classpath में जोड़ें।  
3. **MS Project फ़ाइल** – एक XML‑आधारित Project फ़ाइल (जैसे `input.xml`) जिसे आप जांचना चाहते हैं।  

> **प्रो टिप:** पाथ हैंडलिंग को सरल बनाने के लिए Project फ़ाइल को एक समर्पित `data` फ़ोल्डर में रखें।

## पैकेज इम्पोर्ट करें
पहले, आवश्यक Aspose.Tasks क्लासेस इम्पोर्ट करें:

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## चरण 1: प्रोजेक्ट डायरेक्टरी सेट अप करें
उस फ़ोल्डर को परिभाषित करें जिसमें आपकी Project फ़ाइल मौजूद है।

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

`"Your Data Directory"` को उस पूर्ण या सापेक्ष पाथ से बदलें जहाँ `input.xml` स्थित है।

## चरण 2: प्रोजेक्ट लोड करें
XML फ़ाइल लोड करके एक `Project` इंस्टेंस बनाएं।

```java
Project project = new Project(dataDir + "input.xml");
```

यदि आपकी फ़ाइल का नाम अलग है, तो `"input.xml"` को उसी अनुसार समायोजित करें।

## चरण 3: प्रोजेक्ट संस्करण कैसे निर्धारित करें
संस्करण जानकारी और अंतिम सेव टाइमस्टैम्प प्राप्त करें।

```java
//Display project version property
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```

`Prj.SAVE_VERSION` प्रॉपर्टी दर्शाती है कि फ़ाइल को सहेजने के लिए कौन सा Microsoft Project संस्करण उपयोग किया गया था (उदाहरण के लिए, Project 2010 के लिए 12)। `Prj.LAST_SAVED` सबसे हालिया सेव ऑपरेशन की तिथि/समय लौटाता है।

## चरण 4: परिणाम प्रदर्शित करें
संस्करण जांच की सफल पूर्णता को संकेत दें।

```java
//Display result of conversion.
System.out.println("Process completed Successfully");
```

## सामान्य समस्याएँ और समाधान
| समस्या | कारण | समाधान |
|-------|--------|-----|
| `NullPointerException` on `project.get(...)` | फ़ाइल नहीं मिली या पाथ गलत है | `dataDir` और फ़ाइल नाम की जाँच करें; परीक्षण के लिए पूर्ण पाथ उपयोग करें। |
| अप्रत्याशित संस्करण संख्या (उदा., 0) | गैर‑Project XML फ़ाइल लोड करना | सुनिश्चित करें कि फ़ाइल एक वैध Microsoft Project फ़ाइल (MPP/XML) है। |
| लाइसेंस अपवाद | उत्पादन में वैध लाइसेंस के बिना ट्रायल का उपयोग करना | अपना Aspose.Tasks लाइसेंस लागू करें (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## अक्सर पूछे जाने वाले प्रश्न

### Q: क्या मैं Aspose.Tasks को अन्य प्रोग्रामिंग भाषाओं के साथ उपयोग कर सकता हूँ?
A: हाँ, Aspose.Tasks कई भाषाओं का समर्थन करता है जिसमें .NET, Java, और C++ शामिल हैं।

### Q: क्या Aspose.Tasks बड़े‑स्तर के प्रोजेक्ट्स के लिए उपयुक्त है?
A: बिल्कुल, Aspose.Tasks को किसी भी आकार के प्रोजेक्ट को आसानी से संभालने के लिए डिज़ाइन किया गया है।

### Q: क्या मैं Aspose.Tasks का उपयोग करके प्रोजेक्ट डेटा को कस्टमाइज़ कर सकता हूँ?
A: हाँ, आप Aspose.Tasks का उपयोग करके प्रोजेक्ट डेटा को हेरफेर कर सकते हैं, टास्क, रिसोर्सेज़ आदि को संशोधित कर सकते हैं।

### Q: क्या Aspose.Tasks को Microsoft Project इंस्टॉलेशन की आवश्यकता है?
A: नहीं, Aspose.Tasks स्वतंत्र रूप से काम करता है और Microsoft Project स्थापित करने की आवश्यकता नहीं है।

### Q: क्या Aspose.Tasks के लिए तकनीकी समर्थन उपलब्ध है?
A: हाँ, आप Aspose.Tasks फ़ोरम पर तकनीकी समर्थन प्राप्त कर सकते हैं [यहाँ](https://forum.aspose.com/c/tasks/15).

### अतिरिक्त प्रश्न‑उत्तर

**Q: अन्य प्रोजेक्ट प्रॉपर्टीज़ (जैसे, author, company) कैसे प्राप्त करें?**  
A: `project.get(Prj.AUTHOR)` या `project.get(Prj.COMPANY)` का उपयोग करें, जैसा कि संस्करण उदाहरण में किया गया था।

**Q: क्या मैं MPP फ़ाइल (बाइनरी फ़ॉर्मेट) का संस्करण जांच सकता हूँ?**  
A: हाँ, Aspose.Tasks सीधे `.mpp` फ़ाइलें लोड कर सकता है; वही `Prj.SAVE_VERSION` प्रॉपर्टी काम करती है।

**Q: क्या कोई तरीका है जिससे प्रोग्रामेटिक रूप से पुराने प्रोजेक्ट फ़ाइल को नए संस्करण में अपग्रेड किया जा सके?**  
A: पुरानी फ़ाइल लोड करें, फिर इसे `project.save("newfile.mpp", SaveFileFormat.MPP);` का उपयोग करके सहेजें — Aspose.Tasks डिफ़ॉल्ट रूप से इसे नवीनतम फ़ॉर्मेट में लिखता है।

## निष्कर्ष
आपने अब एक संक्षिप्त **aspose tasks java tutorial** पूरा कर लिया है जो Aspose.Tasks for Java का उपयोग करके MS Project फ़ाइलों का **प्रोजेक्ट संस्करण कैसे निर्धारित करें** दिखाता है। इस स्निपेट को बड़े ऑटोमेशन वर्कफ़्लो, रिपोर्टिंग टूल्स, या माइग्रेशन यूटिलिटीज़ में एकीकृत करें ताकि आप हमेशा उस प्रोजेक्ट संस्करण को जान सकें जिसके साथ आप काम कर रहे हैं।

---

**अंतिम अपडेट:** 2025-12-25  
**परीक्षित संस्करण:** Aspose.Tasks for Java 24.11  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}