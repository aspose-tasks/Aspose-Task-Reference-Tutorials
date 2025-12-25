---
date: 2025-12-25
description: Aspose.Tasks for Java का उपयोग करके वित्तीय वर्ष गुणों को प्रबंधित करना
  और MPP फ़ाइलों को कुशलतापूर्वक लोड करना सीखें। उदाहरणों के साथ चरण‑दर‑चरण मार्गदर्शिका।
linktitle: Manage Fiscal Year Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks में वित्तीय वर्ष की विशेषताओं को प्रबंधित करें
url: /hi/java/project-management/fiscal-year-properties/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में वित्तीय वर्ष गुणों का प्रबंधन

## Introduction
Aspose.Tasks एक शक्तिशाली Java लाइब्रेरी है जो डेवलपर्स को **वित्तीय वर्ष** सेटिंग्स प्रबंधित करने, MPP फ़ाइलें लोड करने, और कुछ ही कोड लाइनों के साथ प्रोजेक्ट डेटा को XML में परिवर्तित करने में सक्षम बनाती है। इस ट्यूटोरियल में आप देखेंगे कि कैसे वित्तीय वर्ष गुण सेट करें, वित्तीय वर्ष जानकारी प्रदर्शित करें, और परिणाम सहेजें—साथ ही आपका कोड साफ़ और रखरखाव योग्य बना रहे।

## Quick Answers
- **Aspose.Tasks में “वित्तीय वर्ष प्रबंधित करना” क्या मतलब है?** यह आपको प्रोजेक्ट के लिए वित्तीय वर्ष की प्रारंभिक माह निर्धारित करने और वित्तीय वर्ष क्रमांकन सक्षम करने की अनुमति देता है।  
- **वित्तीय वर्ष की प्रारंभिक माह कैसे सेट करें?** `Prj.FY_START_DATE` प्रॉपर्टी को `Month` enum मान (जैसे `Month.JULY`) के साथ उपयोग करें।  
- **क्या मैं MPP फ़ाइल लोड कर सकता हूँ?** हाँ, बस *.mpp* फ़ाइल के पथ के साथ एक `Project` इंस्टेंस बनाएँ।  
- **MPP को XML में कैसे परिवर्तित करें?** इच्छित गुण सेट करने के बाद `project.save(..., SaveFileFormat.Xml)` कॉल करें।  
- **क्या मुझे लाइसेंस चाहिए?** एक मुफ्त ट्रायल उपलब्ध है; उत्पादन उपयोग के लिए व्यावसायिक लाइसेंस आवश्यक है।

## What is “manage fiscal year” in project files?
प्रोजेक्ट फ़ाइलों में “वित्तीय वर्ष प्रबंधित करना” का अर्थ है वह कैलेंडर कॉन्फ़िगर करना जिसे आपका प्रोजेक्ट वित्तीय रिपोर्टिंग के लिए अनुसरण करता है। इसमें वित्तीय वर्ष की प्रारंभिक माह सेट करना और वैकल्पिक रूप से वित्तीय वर्ष क्रमांकन सक्षम करना शामिल है, जो रिपोर्टों में तिथियों की गणना और प्रदर्शन को प्रभावित करता है।

## Why use Aspose.Tasks for fiscal year handling?
- **Microsoft Project की आवश्यकता नहीं** – Java में सीधे प्रोजेक्ट फ़ाइलों के साथ काम करें।  
- **पूर्ण नियंत्रण** – प्रोग्रामेटिक रूप से वित्तीय वर्ष की शुरुआत सेट करें, क्रमांकन सक्षम करें, और फ़ॉर्मेट बदलें।  
- **मज़बूत API** – बड़े MPP फ़ाइलों को विश्वसनीय रूप से संभालता है और सहज XML निर्यात प्रदान करता है।

## Prerequisites
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
1. आपके सिस्टम पर Java Development Kit (JDK) स्थापित हो।  
2. Aspose.Tasks for Java JAR – इसे [here](https://releases.aspose.com/tasks/java/) से डाउनलोड करें और अपने प्रोजेक्ट की classpath में जोड़ें।

## Import Packages
शुरू करने के लिए, अपने Java स्रोत फ़ाइल में आवश्यक क्लासेस इम्पोर्ट करें:
```java
import com.aspose.tasks.*;
```

## How to load an MPP file and display fiscal year information
एक MPP फ़ाइल लोड करने और वित्तीय वर्ष जानकारी प्रदर्शित करने का तरीका

नीचे हम प्रक्रिया को स्पष्ट, क्रमांकित चरणों में विभाजित करते हैं।

### Step 1: Load Project File
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
यहाँ हम निर्दिष्ट डायरेक्टरी से **एक MPP फ़ाइल लोड** (`project.mpp`) करते हैं। यह किसी भी वित्तीय‑वर्ष‑संबंधित कार्य का पहला कदम है।

### Step 2: Display Fiscal Year Properties
```java
//Display fiscal year properties
System.out.println("Fiscal Year Start Date : " + project.get(Prj.FY_START_DATE));
System.out.println("Fiscal Year Numbering : " + project.get(Prj.FISCAL_YEAR_START));
```
`Prj.FY_START_DATE` और `Prj.FISCAL_YEAR_START` प्रॉपर्टी आपको **वित्तीय वर्ष** विवरण दिखाने देती हैं, जिससे “वर्तमान वित्तीय कॉन्फ़िगरेशन क्या है?” प्रश्न का उत्तर मिलता है।

### Step 3: Set Fiscal Year Start and Enable Numbering
```java
//Create a project instance
Project prj = new Project();
//Set fiscal year properties
prj.set(Prj.FY_START_DATE, Month.JULY);
prj.set(Prj.FISCAL_YEAR_START, new NullableBool(true));
//Save the project as XML project file
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
इस चरण में हम वित्तीय सेटिंग्स सेट करने का तरीका दिखाते हैं:
- `Month.JULY` वित्तीय वर्ष की प्रारंभिक माह को परिभाषित करता है।  
- `NullableBool(true)` वित्तीय वर्ष क्रमांकन को सक्रिय करता है।  
- अंत में, प्रोजेक्ट को `SaveFileFormat.Xml` का उपयोग करके **MPP से XML में परिवर्तित** किया जाता है।

### Step 4: Confirm the Operation
```java
//Display result of conversion.
System.out.println("Process completed Successfully");
```
एक सरल कंसोल संदेश पुष्टि करता है कि वित्तीय वर्ष कॉन्फ़िगर हो गया है और फ़ाइल सहेजी गई है।

## Common Issues and Solutions
| समस्या | समाधान |
|-------|----------|
| **गलत माह मान** | सुनिश्चित करें कि आप `Month` enum का उपयोग करें (जैसे, `Month.JANUARY`)। |
| **फ़ाइल नहीं मिली** | `dataDir` सही फ़ोल्डर की ओर इशारा करता है और फ़ाइल नाम मेल खाता है, यह सत्यापित करें। |
| **सेविंग विफल** | लक्षित डायरेक्टरी पर लिखने की अनुमति जांचें और सुनिश्चित करें कि `SaveFileFormat` समर्थित है। |

## Frequently Asked Questions

**Q: क्या मैं Aspose.Tasks for Java का उपयोग करके अन्य प्रोजेक्ट गुणों को बदल सकता हूँ?**  
A: हां, Aspose.Tasks वित्तीय वर्ष सेटिंग्स के अलावा विभिन्न प्रोजेक्ट गुणों को प्रबंधित करने के लिए व्यापक कार्यक्षमता प्रदान करता है।

**Q: क्या Aspose.Tasks for Java विभिन्न प्रोजेक्ट फ़ाइल फ़ॉर्मेट्स के साथ संगत है?**  
A: हां, यह MPP, XML और अन्य सहित कई फ़ॉर्मेट्स को सपोर्ट करता है।

**Q: यदि मैं Aspose.Tasks for Java का उपयोग करते समय कोई समस्या का सामना करता हूं तो समर्थन कैसे प्राप्त कर सकता हूं?**  
A: आप Aspose.Tasks समुदाय से [forum](https://forum.aspose.com/c/tasks/15) पर सहायता ले सकते हैं या सीधे उनके सपोर्ट टीम से संपर्क कर सकते हैं।

**Q: क्या Aspose.Tasks एक मुफ्त ट्रायल संस्करण प्रदान करता है?**  
A: हां, आप [here](https://releases.aspose.com/) से Aspose.Tasks का मुफ्त ट्रायल संस्करण प्राप्त कर सकते हैं।

**Q: मैं Aspose.Tasks for Java के लिए लाइसेंस कहाँ खरीद सकता हूं?**  
A: आप लाइसेंस [here](https://purchase.aspose.com/buy) से खरीद सकते हैं।

## Conclusion
Java के लिए Aspose.Tasks में वित्तीय वर्ष गुणों का प्रबंधन सरल है। ऊपर दिए गए चरणों का पालन करके आप **वित्तीय वर्ष प्रबंधित** कर सकते हैं, **MPP फ़ाइलें लोड** कर सकते हैं, **वित्तीय वर्ष** विवरण दिखा सकते हैं, और **MPP को XML में परिवर्तित** कर सकते हैं। इन तकनीकों का उपयोग करके अपने प्रोजेक्ट शेड्यूल को अपने संगठन के वित्तीय कैलेंडर के साथ संरेखित रखें।

---

**Last Updated:** 2025-12-25  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}