---
date: 2025-12-20
description: Aspose.Tasks for Java का उपयोग करके प्रोग्रामेटिकली MS Project आउटलाइन
  कोड्स को प्राप्त करना सीखें। अपनी प्रोजेक्ट मैनेजमेंट क्षमताओं को बढ़ाएँ।
linktitle: Retrieve Outline Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks में MS प्रोजेक्ट आउटलाइन कोड प्राप्त करें
url: /hi/java/project-file-operations/retrieve-outline-codes/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks के साथ MS Project Outline Codes प्राप्त करें

## परिचय
इस ट्यूटोरियल में, आप **Aspose.Tasks for Java** का उपयोग करके **MS Project Outline Codes को कैसे प्राप्त करें** सीखेंगे। MS Project में Outline Codes आपको कार्यों, संसाधनों और असाइनमेंट्स को वर्गीकृत करने का एक शक्तिशाली तरीका प्रदान करते हैं, और इन्हें प्रोग्रामेटिकली एक्सेस करने से आप कस्टम रिपोर्टिंग, ऑटोमेशन या इंटीग्रेशन समाधान बना सकते हैं। हम एक पूर्ण, चरण‑दर‑चरण उदाहरण के माध्यम से चलेंगे जिसे आप अपने प्रोजेक्ट में कॉपी कर सकते हैं।

## त्वरित उत्तर
- **कोड क्या करता है?** यह एक Project फ़ाइल को लोड करता है और प्रत्येक Outline Code परिभाषा, उसके मास्क और उसके मानों को प्रिंट करता है।  
- **कौन सी लाइब्रेरी आवश्यक है?** Aspose.Tasks for Java (कोई भी नवीनतम संस्करण)।  
- **क्या लाइसेंस चाहिए?** विकास के लिए ट्रायल चलती है; प्रोडक्शन के लिए पूर्ण लाइसेंस आवश्यक है।  
- **कौन सा Java संस्करण समर्थित है?** Java 8 या उससे ऊपर।  
- **क्या कोड प्राप्त करने के बाद उन्हें संशोधित कर सकता हूँ?** हाँ – वही API आपको Outline Codes को जोड़ने, संपादित करने या हटाने की अनुमति देती है।

## MS Project Outline Codes क्या हैं?
Outline Codes कस्टम फ़ील्ड होते हैं जो प्रोजेक्ट मैनेजर्स को डिफ़ॉल्ट हायरार्की से परे कार्यों को समूहित और फ़िल्टर करने की सुविधा देते हैं। ये सरल संख्यात्मक मान, स्ट्रिंग्स, या यहाँ तक कि एंटरप्राइज़‑व्यापी कस्टम कोड हो सकते हैं जो संगठन स्तर पर परिभाषित होते हैं। इन कोड्स को पढ़कर आप डैशबोर्ड चला सकते हैं, डेटा एक्सपोर्ट कर सकते हैं, या स्वचालित रूप से नामकरण नियम लागू कर सकते हैं।

## Aspose.Tasks के साथ MS Project Outline Codes क्यों प्राप्त करें?
- **ऑटोमेशन:** मैन्युअल एक्सपोर्ट के बिना रिपोर्ट बनाएं या वर्कफ़्लो ट्रिगर करें।  
- **इंटीग्रेशन:** Outline Codes को ERP, PPM या BI टूल्स के साथ सिंक करें।  
- **कस्टमाइज़ेशन:** कोड मानों के आधार पर बिज़नेस नियम लागू करें (जैसे, लागत आवंटन)।  
- **क्रॉस‑प्लेटफ़ॉर्म:** Windows, Linux और macOS पर काम करता है, Microsoft Project UI से स्वतंत्र।

## पूर्वापेक्षाएँ
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ सेट हैं:

### 1. Java विकास पर्यावरण
सुनिश्चित करें कि आपके सिस्टम पर Java Development Kit (JDK) स्थापित है। आप Oracle की वेबसाइट से JDK डाउनलोड और इंस्टॉल कर सकते हैं।

### 2. Aspose.Tasks लाइब्रेरी
Aspose.Tasks लाइब्रेरी को अपने Java प्रोजेक्ट में डाउनलोड और शामिल करें। आप लाइब्रेरी को [Aspose.Tasks for Java Download Page](https://releases.aspose.com/tasks/java/) से डाउनलोड कर सकते हैं।

## पैकेज आयात करें
पहले, अपने Java कोड में Aspose.Tasks से आवश्यक पैकेज आयात करें:
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```

अब हम प्रदान किए गए उदाहरण कोड को कई चरणों में विभाजित करते हैं:

## चरण 1: प्रोजेक्ट लोड करें
```java
String projectName = "ProjectFile.mpp";
Project project = new Project(projectName);
```
इस चरण में, हम प्रदान किए गए फ़ाइल नाम का उपयोग करके Microsoft Project फ़ाइल को एक `Project` ऑब्जेक्ट में लोड करते हैं।

## चरण 2: Outline Codes प्राप्त करें
```java
for (OutlineCodeDefinition ocd : project.getOutlineCodes()) {
```
हम प्रोजेक्ट में प्रत्येक Outline Code परिभाषा के माध्यम से इटररेट करते हैं।

## चरण 3: Outline Code गुणों तक पहुँचें
```java
System.out.println("Alias = " + ocd.getAlias());
System.out.println("Field Id = " + ocd.getFieldId());
System.out.println("Field Name = " + ocd.getFieldName());
```
हम Outline Code परिभाषा के विभिन्न गुणों जैसे Alias, Field ID, और Field Name को प्राप्त और प्रिंट करते हैं।

## चरण 4: एंटरप्राइज़ कस्टम कोड जांचें
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
हम जांचते हैं कि Outline Code एंटरप्राइज़ कस्टम कोड है या नहीं और परिणाम के अनुसार प्रिंट करते हैं।

## चरण 5: Outline Code मास्क दिखाएँ
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
हम Outline Code से जुड़े प्रत्येक मास्क के स्तर और मास्क मान को इटररेट करके प्रिंट करते हैं।

## चरण 6: Outline Code मान दिखाएँ
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
हम प्रत्येक Outline Code मान के विवरण, Value ID, Value और Type को इटररेट करके प्रिंट करते हैं।

## सामान्य समस्याएँ और समाधान
| समस्या | कारण | समाधान |
|-------|--------|-----|
| **कोई आउटपुट नहीं** | प्रोजेक्ट फ़ाइल पाथ गलत | सुनिश्चित करें `projectName` एक वैध `.mpp` फ़ाइल की ओर इशारा करता है। |
| **Null मान** | फ़ाइल में Outline Code परिभाषित नहीं है | सुनिश्चित करें प्रोजेक्ट फ़ाइल में वास्तव में Outline Codes मौजूद हैं (MS Project UI में जाँचें)। |
| **LicenseException** | उचित सक्रियण के बिना ट्रायल उपयोग | अस्थायी या पूर्ण लाइसेंस लागू करें: `License license = new License(); license.setLicense("Aspose.Tasks.lic");` |

## अक्सर पूछे जाने वाले प्रश्न

**प्र: क्या मैं Aspose.Tasks for Java का उपयोग करके प्रोजेक्ट फ़ाइल में Outline Codes को संशोधित कर सकता हूँ?**  
उ: हाँ, Aspose.Tasks for Java प्रोग्रामेटिकली Outline Codes को संशोधित करने के लिए API प्रदान करता है। आप वही `Project` ऑब्जेक्ट का उपयोग करके परिभाषाएँ जोड़, संपादित या हटाए सकते हैं।

**प्र: क्या Aspose.Tasks for Java का ट्रायल संस्करण उपलब्ध है?**  
उ: हाँ, आप Aspose.Tasks for Java का मुफ्त ट्रायल संस्करण [Aspose.Tasks वेबसाइट](https://releases.aspose.com/) से डाउनलोड कर सकते हैं।

**प्र: Aspose.Tasks for Java के लिए तकनीकी समर्थन कैसे प्राप्त करूँ?**  
उ: आप [Aspose.Tasks फ़ोरम](https://forum.aspose.com/c/tasks/15) पर जाकर अपने प्रश्न पोस्ट कर सकते हैं।

**प्र: क्या मैं Aspose.Tasks for Java के लिए अस्थायी लाइसेंस खरीद सकता हूँ?**  
उ: हाँ, आप [purchase page](https://purchase.aspose.com/temporary-license/) से Aspose.Tasks for Java के लिए अस्थायी लाइसेंस खरीद सकते हैं।

**प्र: Aspose.Tasks for Java की पूरी दस्तावेज़ीकरण कहाँ मिल सकती है?**  
उ: विस्तृत जानकारी के लिए आप [documentation](https://reference.aspose.com/tasks/java/) देख सकते हैं।

## निष्कर्ष
इस ट्यूटोरियल में हमने Aspose.Tasks for Java का उपयोग करके **MS Project Outline Codes को प्राप्त करना** सीखा। प्रदान किए गए चरणों का पालन करके आप अपने Java एप्लिकेशन में Outline Codes को प्रभावी रूप से एक्सेस और मैनीपुलेट कर सकते हैं, जिससे कस्टम रिपोर्टिंग, ऑटोमेशन और अन्य एंटरप्राइज़ सिस्टम्स के साथ इंटीग्रेशन जैसी उन्नत प्रोजेक्ट मैनेजमेंट क्षमताएँ सक्षम होती हैं।

---

**अंतिम अपडेट:** 2025-12-20  
**परीक्षित संस्करण:** Aspose.Tasks for Java 24.12 (लेखन समय पर नवीनतम)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}