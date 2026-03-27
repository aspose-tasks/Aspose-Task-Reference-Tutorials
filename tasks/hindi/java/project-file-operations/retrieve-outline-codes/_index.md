---
date: 2026-03-27
description: Aspose.Tasks for Java का उपयोग करके प्रोग्रामेटिकली MS Project आउटलाइन
  कोड्स को कैसे प्राप्त करें, सीखें। अपनी प्रोजेक्ट मैनेजमेंट क्षमताओं को बढ़ाएँ।
linktitle: Retrieve Outline Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks में MS प्रोजेक्ट आउटलाइन कोड प्राप्त करें
url: /hi/java/project-file-operations/retrieve-outline-codes/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में MS Project Outline Codes प्राप्त करें

## Introduction
इस ट्यूटोरियल में, आप Aspose.Tasks for Java का उपयोग करके **ms project outline codes को कैसे प्राप्त करें** की खोज करेंगे। MS Project में Outline codes आपको कार्यों, संसाधनों और असाइनमेंट्स को वर्गीकृत करने का एक शक्तिशाली तरीका प्रदान करते हैं, और इन्हें प्रोग्रामेटिकली एक्सेस करने से आप कस्टम रिपोर्टिंग, ऑटोमेशन, या इंटीग्रेशन समाधान बना सकते हैं। हम एक पूर्ण, चरण‑दर‑चरण उदाहरण के माध्यम से चलेंगे जिसे आप अपने प्रोजेक्ट में कॉपी कर सकते हैं।

## Quick Answers
- **कोड क्या करता है?** यह एक Project फ़ाइल लोड करता है और प्रत्येक outline code परिभाषा, उसके मास्क और उसके मान प्रिंट करता है।  
- **कौन सी लाइब्रेरी आवश्यक है?** Aspose.Tasks for Java (कोई भी नवीनतम संस्करण)।  
- **क्या मुझे लाइसेंस चाहिए?** विकास के लिए ट्रायल काम करता है; उत्पादन के लिए पूर्ण लाइसेंस आवश्यक है।  
- **कौन सा Java संस्करण समर्थित है?** Java 8 या उससे ऊपर।  
- **क्या मैं कोड्स को प्राप्त करने के बाद संशोधित कर सकता हूँ?** हाँ – वही API आपको outline codes को जोड़ने, संपादित करने या हटाने की अनुमति देती है।

## What are ms project outline codes?
Outline codes कस्टम फ़ील्ड्स हैं जो प्रोजेक्ट मैनेजर्स को डिफ़ॉल्ट हायरार्की से आगे कार्यों को समूहित और फ़िल्टर करने की अनुमति देते हैं। ये सरल संख्यात्मक मान, स्ट्रिंग्स, या यहाँ तक कि संगठन स्तर पर परिभाषित एंटरप्राइज़‑वाइड कस्टम कोड्स हो सकते हैं। इन कोड्स को पढ़कर, आप डैशबोर्ड चला सकते हैं, डेटा निर्यात कर सकते हैं, या स्वचालित रूप से नामकरण नियम लागू कर सकते हैं।

## Why retrieve ms project outline codes with Aspose.Tasks?
- **Automation:** रिपोर्ट जनरेट करें या वर्कफ़्लो ट्रिगर करें बिना मैन्युअल एक्सपोर्ट के।  
- **Integration:** outline codes को ERP, PPM, या BI टूल्स के साथ सिंक करें।  
- **Customization:** कोड मानों (जैसे, लागत आवंटन) के आधार पर बिज़नेस नियम लागू करें।  
- **Cross‑platform:** Windows, Linux, और macOS पर काम करता है, Microsoft Project UI से स्वतंत्र।

## How to read MPP files for outline codes?
MPP (Microsoft Project) फ़ाइल को पढ़ना outline codes निकालने की पहली कदम है। Aspose.Tasks फ़ाइल फ़ॉर्मेट को एब्स्ट्रैक्ट करता है, इसलिए आपको बाइनरी स्ट्रक्चर को स्वयं पार्स करने की जरूरत नहीं है। `Project` क्लास भारी काम संभालती है, जिससे आप वास्तव में जिस डेटा की आवश्यकता है उस पर ध्यान केंद्रित कर सकते हैं।

## Custom fields in MS Project
Outline codes MS Project में **कस्टम फ़ील्ड्स** का एक प्रकार हैं। जबकि मानक फ़ील्ड्स तिथियों, अवधि और संसाधनों को कवर करते हैं, कस्टम फ़ील्ड्स आपको संगठन‑विशिष्ट जानकारी संग्रहीत करने की अनुमति देते हैं। Aspose.Tasks के माध्यम से इन्हें एक्सेस करने से आपको प्रोग्रामेटिक रूप से वही लचीलापन मिलता है।

## Prerequisites
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यकताएँ सेट हैं:

### 1. Java Development Environment
सुनिश्चित करें कि आपके सिस्टम पर Java Development Kit (JDK) स्थापित है। आप Oracle वेबसाइट से JDK डाउनलोड और इंस्टॉल कर सकते हैं।

### 2. Aspose.Tasks Library
Aspose.Tasks लाइब्रेरी को अपने Java प्रोजेक्ट में डाउनलोड और शामिल करें। आप लाइब्रेरी को [Aspose.Tasks for Java Download Page](https://releases.aspose.com/tasks/java/) से डाउनलोड कर सकते हैं।

## Import Packages
सबसे पहले, अपने Java कोड में Aspose.Tasks से आवश्यक पैकेज इम्पोर्ट करें:
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```

अब चलिए प्रदान किए गए उदाहरण कोड को कई चरणों में विभाजित करते हैं:

## Step 1: Load the Project
```java
String projectName = "ProjectFile.mpp";
Project project = new Project(projectName);
```
इस चरण में, हम प्रदान किए गए फ़ाइल नाम का उपयोग करके Microsoft Project फ़ाइल को एक `Project` ऑब्जेक्ट में लोड करते हैं।

## Step 2: Retrieve Outline Codes
```java
for (OutlineCodeDefinition ocd : project.getOutlineCodes()) {
```
हम प्रोजेक्ट में प्रत्येक outline code परिभाषा के माध्यम से इटररेट करते हैं।

## Step 3: Access Outline Code Properties
```java
System.out.println("Alias = " + ocd.getAlias());
System.out.println("Field Id = " + ocd.getFieldId());
System.out.println("Field Name = " + ocd.getFieldName());
```
हम outline code परिभाषा की विभिन्न प्रॉपर्टीज़ जैसे Alias, Field ID, और Field Name को प्राप्त करके प्रिंट करते हैं।

## Step 4: Check Enterprise Custom Code
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
हम जांचते हैं कि outline code एंटरप्राइज़ कस्टम कोड है या नहीं और परिणाम को उसी अनुसार प्रिंट करते हैं।

## Step 5: Display Outline Code Masks
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
हम outline code से जुड़े प्रत्येक मास्क के माध्यम से इटररेट करते हैं और उसका लेवल तथा मास्क वैल्यू प्रिंट करते हैं।

## Step 6: Display Outline Code Values
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
हम प्रत्येक outline code वैल्यू के माध्यम से इटररेट करते हैं और उसका विवरण, value ID, value, और type प्रिंट करते हैं।

## Common Issues and Solutions
| समस्या | कारण | समाधान |
|-------|--------|-----|
| **कोई आउटपुट नहीं** | प्रोजेक्ट फ़ाइल पाथ गलत है | सुनिश्चित करें कि `projectName` एक वैध `.mpp` फ़ाइल की ओर इशारा करता है। |
| **नल मान** | फ़ाइल में outline code परिभाषित नहीं है | सुनिश्चित करें कि प्रोजेक्ट फ़ाइल वास्तव में outline codes शामिल करती है (MS Project UI में जांचें)। |
| **LicenseException** | उचित सक्रियता के बिना ट्रायल उपयोग करना | `License license = new License(); license.setLicense("Aspose.Tasks.lic");` के माध्यम से एक अस्थायी या पूर्ण लाइसेंस लागू करें। |

## Frequently Asked Questions

**Q: क्या मैं Aspose.Tasks for Java का उपयोग करके प्रोजेक्ट फ़ाइल में outline codes को संशोधित कर सकता हूँ?**  
A: हाँ, Aspose.Tasks for Java प्रोग्रामेटिकली outline codes को संशोधित करने के लिए API प्रदान करता है। आप वही `Project` ऑब्जेक्ट का उपयोग करके परिभाषाएँ जोड़, संपादित या हटाएँ सकते हैं।

**Q: क्या Aspose.Tasks for Java के लिए ट्रायल संस्करण उपलब्ध है?**  
A: हाँ, आप Aspose.Tasks for Java का मुफ्त ट्रायल संस्करण [Aspose.Tasks वेबसाइट](https://releases.aspose.com/) से डाउनलोड कर सकते हैं।

**Q: मैं Aspose.Tasks for Java के लिए तकनीकी समर्थन कैसे प्राप्त कर सकता हूँ?**  
A: आप [Aspose.Tasks फोरम](https://forum.aspose.com/c/tasks/15) पर जाकर और वहाँ अपने प्रश्न पोस्ट करके तकनीकी समर्थन प्राप्त कर सकते हैं।

**Q: क्या मैं Aspose.Tasks for Java के लिए अस्थायी लाइसेंस खरीद सकता हूँ?**  
A: हाँ, आप [खरीद पेज](https://purchase.aspose.com/temporary-license/) से Aspose.Tasks for Java के लिए अस्थायी लाइसेंस खरीद सकते हैं।

**Q: मैं Aspose.Tasks for Java की पूरी दस्तावेज़ीकरण कहाँ पा सकता हूँ?**  
A: आप Aspose.Tasks for Java के उपयोग के विस्तृत जानकारी के लिए [दस्तावेज़ीकरण](https://reference.aspose.com/tasks/java/) देख सकते हैं।

## Conclusion
इस ट्यूटोरियल में, हमने Aspose.Tasks for Java का उपयोग करके **ms project outline codes** को प्राप्त करना सीखा। प्रदान किए गए चरणों का पालन करके, आप अपने Java एप्लिकेशन में outline codes को प्रभावी रूप से एक्सेस और मैनिपुलेट कर सकते हैं, जिससे कस्टम रिपोर्टिंग, ऑटोमेशन, और अन्य एंटरप्राइज़ सिस्टम्स के साथ इंटीग्रेशन जैसी उन्नत प्रोजेक्ट मैनेजमेंट क्षमताएँ सक्षम होती हैं।

---

**अंतिम अपडेट:** 2026-03-27  
**परीक्षित संस्करण:** Aspose.Tasks for Java (latest)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}