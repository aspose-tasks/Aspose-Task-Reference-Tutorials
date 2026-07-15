---
date: 2026-02-10
description: Aspose.Tasks for Java का उपयोग करके MS Project फ़ाइलों से मुद्रा कोड
  कैसे प्राप्त करें, यह सीखें – जावा डेवलपर्स के लिए आवश्यक मुद्रा कोड को जल्दी से
  प्राप्त करने का तरीका।
linktitle: Manage Currency Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks के साथ MS Project से मुद्रा कैसे प्राप्त करें
url: /hi/java/currency/currency-codes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Project से मुद्रा प्राप्त करने का तरीका Aspise.Tasks के साथ

## Introduction
Welcome! इस ट्यूटोरियल में आप **मुद्रा प्राप्त करने का तरीका** MS Project फ़ाइल से Aspose.Tasks Java API का उपयोग करके सीखेंगे। चाहे आप बहु‑मुद्रा वित्तीय रिपोर्ट बना रहे हों, विभिन्न क्षेत्रों से प्रोजेक्ट को एकीकृत कर रहे हों, या केवल डाउनस्ट्रीम प्रोसेसिंग के लिए सही मौद्रिक प्रतीकों की आवश्यकता हो, यह गाइड आपको हर चरण से ले जाएगा—पर्यावरण सेटअप से लेकर प्रोग्रामेटिक रूप से मुद्रा कोड निकालने तक। अंत तक, आप MS Project फ़ाइलें पढ़ने और **get currency code java** कॉल का उपयोग करके ISO मुद्रा पहचानकर्ता प्राप्त करने में सहज हो जाएंगे।

## Quick Answers
- **API क्या करता है?** यह MS Project फ़ाइलें पढ़ता है और मुद्रा कोड जैसी प्रॉपर्टीज़ को एक्सपोज़ करता है।  
- **कौन सी भाषा उपयोग की गई है?** Java, Aspose.Tasks for Java लाइब्रेरी के माध्यम से।  
- **क्या लाइसेंस की जरूरत है?** विकास के लिए एक फ्री ट्रायल काम करता है; उत्पादन के लिए एक कमर्शियल लाइसेंस आवश्यक है।  
- **क्या कोड एक लाइन में प्राप्त किया जा सकता है?** हाँ—`prj.get(Prj.CURRENCY_CODE)` मुद्रा कोड स्ट्रिंग लौटाता है।  
- **क्या यह सभी Project संस्करणों के साथ संगत है?** Aspose.Tasks पुराने (MPP) और नए (XML, XER) दोनों फ़ॉर्मैट्स को सपोर्ट करता है।

## What is **read ms project file**?
MS Project फ़ाइल पढ़ना मतलब प्रोग्रामेटिक रूप से *.mpp* (या अन्य समर्थित) प्रोजेक्ट दस्तावेज़ को खोलना और उसकी डेटा संरचनाओं—टास्क, रिसोर्स, कैलेंडर, और वित्तीय सेटिंग्स—तक पहुंचना, बिना Microsoft Project के मैन्युअल इंटरैक्शन के।

## Why use Aspose.Tasks to **read msproject** files?
- **Full format support** – Project 98 से लेकर नवीनतम Office रिलीज़ तक की फ़ाइलों के साथ काम करता है।  
- **No COM or Office installation needed** – शुद्ध Java, सर्वर‑साइड ऑटोमेशन के लिए परफेक्ट।  
- **Rich API** – `Prj.CURRENCY_CODE` जैसी प्रॉपर्टीज़ तक सीधे पहुंच देता है, जिससे आप **how to retrieve currency** जानकारी तुरंत प्राप्त कर सकते हैं।  
- **Performance** – हल्का पार्सिंग, कई प्रोजेक्ट्स की बैच प्रोसेसिंग के लिए आदर्श।

## Prerequisites
कोड में डुबकी लगाने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

### Java Development Kit (JDK) Installed
सुनिश्चित करें कि आपके मशीन पर एक हालिया JDK उपलब्ध है। आप नवीनतम JDK संस्करण [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) से डाउनलोड और इंस्टॉल कर सकते हैं।

### Aspose.Tasks for Java Library
Aspose.Tasks for Java लाइब्रेरी डाउनलोड और सेट अप करें। विस्तृत दस्तावेज़ीकरण और नवीनतम बाइनरीज़ [here](https://reference.aspose.com/tasks/java/) पर उपलब्ध हैं।

## Import Packages
शुरू करने के लिए, अपने Java प्रोजेक्ट में आवश्यक पैकेज इम्पोर्ट करें:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Step‑by‑step guide

### Step 1: Set Up Data Directory
उस फ़ोल्डर को परिभाषित करें जिसमें आपकी *.mpp* फ़ाइल है। अपने पर्यावरण के अनुसार पाथ को समायोजित करें।
```java
String dataDir = "Your Data Directory";
```

### Step 2: Load the Project File
MS Project फ़ाइल को लोड करके एक `Project` इंस्टेंस बनाएं। यही वह बिंदु है जहाँ आप **read msproject** डेटा को मेमोरी में लाते हैं।
```java
Project prj = new Project(dataDir + "project.mpp");
```

### Step 3: Retrieve Currency Code
अब प्रोजेक्ट लोड हो चुका है, आप एक ही कॉल के साथ **how to retrieve currency** जानकारी प्राप्त कर सकते हैं। यह **get currency code java** उपयोग का प्रदर्शन है।
```java
System.out.println(prj.get(Prj.CURRENCY_CODE));
```
आउटपुट तीन‑अक्षरीय ISO मुद्रा कोड होगा (उदा., `USD`, `EUR`, `GBP`) जिसे प्रोजेक्ट ने उपयोग के लिए कॉन्फ़िगर किया है।

### Step 4: How to Retrieve Currency Code in Java (Additional Context)
यदि आपको बाद में उपयोग के लिए मान संग्रहीत करना है, तो बस इसे एक वैरिएबल में असाइन कर दें:

*No extra code block is required* – बस `prj.get(Prj.CURRENCY_CODE)` द्वारा लौटाए गए स्ट्रिंग को रखें और इसे किसी भी फ़ाइनेंशियल सर्विस, रिपोर्टिंग इंजन, या UI कंपोनेंट को पास कर दें।

### Step 5: (Optional) Use the Currency Code
आप प्राप्त कोड को अन्यत्र लागू करना चाह सकते हैं—जैसे कस्टम रिपोर्ट में लागत मानों को फ़ॉर्मेट करना या इसे फ़ाइनेंशियल API को पास करना। सामान्य परिदृश्य शामिल हैं:

- **Report generation** – लागत कॉलम में कोड प्रीफ़िक्स करें (`USD 1,200`)।  
- **API integration** – भुगतान गेटवे को ISO कोड भेजें जो मुद्रा पहचानकर्ता की आवश्यकता रखते हैं।  
- **Data consolidation** – पोर्टफ़ोलियो विश्लेषण के लिए कई प्रोजेक्ट्स को मुद्रा के आधार पर समूहित करें।

## Common Issues and Solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| **Null output** | प्रोजेक्ट फ़ाइल में मुद्रा परिभाषित नहीं है (डिफ़ॉल्ट खाली)। | Microsoft Project में मुद्रा सेट करें या पढ़ने से पहले `prj.set(Prj.CURRENCY_CODE, "USD");` द्वारा असाइन करें। |
| **File not found** | `dataDir` पाथ गलत है। | पाथ की जाँच करें और सुनिश्चित करें कि फ़ाइल नाम बिल्कुल सही है, केस सेंसिटिविटी सहित। |
| **Unsupported file version** | बहुत पुरानी या करप्ट *.mpp* फ़ाइल। | नवीनतम Aspose.Tasks संस्करण का उपयोग करें या पहले Microsoft Project में फ़ाइल को नए फ़ॉर्मैट में कनवर्ट करें। |

## Frequently Asked Questions

**Q: क्या Aspose.Tasks जटिल प्रोजेक्ट संरचनाओं को संभाल सकता है?**  
A: हाँ, API मल्टी‑लेवल टास्क हायरार्की, रिसोर्स पूल, और कस्टम फ़ील्ड्स को बिना समस्या के पढ़ और मैनीपुलेट कर सकता है।

**Q: क्या Aspose.Tasks विभिन्न संस्करणों की MS Project फ़ाइलों के साथ संगत है?**  
A: बिल्कुल। यह MPP, XML, XER, और कई Microsoft Project रिलीज़ के अन्य फ़ॉर्मैट्स को सपोर्ट करता है।

**Q: क्या Aspose.Tasks दस्तावेज़ीकरण और सपोर्ट प्रदान करता है?**  
A: व्यापक दस्तावेज़ीकरण, कोड उदाहरण, और समर्पित सपोर्ट Aspose वेबसाइट पर उपलब्ध हैं।

**Q: क्या मैं Aspose.Tasks को खरीदने से पहले ट्राय कर सकता हूँ?**  
A: एक फ्री ट्रायल उपलब्ध है जिससे आप सभी फीचर्स, जिसमें मुद्रा कोड पढ़ना भी शामिल है, का मूल्यांकन कर सकते हैं।

**Q: Aspose.Tasks के लिए टेम्पररी लाइसेंस कहाँ मिल सकते हैं?**  
A: टेम्पररी लाइसेंस [website](https://purchase.aspose.com/temporary-license/) से शॉर्ट‑टर्म इवैल्यूएशन के लिए प्राप्त किए जा सकते हैं।

---

**Last Updated:** 2026-02-10  
**Tested With:** Aspose.Tasks for Java (latest version)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}