---
date: 2026-02-13
description: जावा में एक प्रोजेक्ट ऑब्जेक्ट बनाकर, विस्तारित गुण जोड़कर, और Aspose.Tasks
  के साथ मूल्यांकन फ़ंक्शन का उपयोग करके प्रोजेक्ट रिपोर्ट कैसे जेनरेट करें, सीखें।
linktitle: Support Evaluation Functions in Aspose.Tasks Formulas
second_title: Aspose.Tasks Java API
title: प्रोजेक्ट रिपोर्ट जनरेट करें – जावा में प्रोजेक्ट ऑब्जेक्ट बनाएं
url: /hi/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks फ़ॉर्मूले में समर्थन मूल्यांकन फ़ंक्शन

## परिचय
Aspose.Tasks for Java आपको **generate project report** करने देता है, Java में एक **project object** बनाकर और Microsoft Project फ़ंक्शन को सीधे आपके कोड के भीतर मूल्यांकन करके। इन फ़ॉर्मूलों को एम्बेड करके, आप जटिल गणनाएँ चला सकते हैं, कस्टम रिपोर्ट बना सकते हैं, और अपने विकास वातावरण को छोड़े बिना प्रोजेक्ट विश्लेषण को स्वचालित कर सकते हैं। इस ट्यूटोरियल में हम एक प्रोजेक्ट ऑब्जेक्ट बनाने, एक विस्तारित एट्रिब्यूट जोड़ने, और मूल्यांकन फ़ंक्शन का उपयोग करके **add custom field task** डेटा जोड़ने की प्रक्रिया बताएँगे।

## त्वरित उत्तर
- **“create project object java” का क्या अर्थ है?** यह एक इन‑मेमोरी `Project` इंस्टेंस बनाता है जिसे आप प्रोग्रामेटिकली हेरफेर कर सकते हैं।  
- **कौन सी लाइब्रेरी आवश्यक है?** Aspose.Tasks for Java (आधिकारिक साइट से डाउनलोड करें)।  
- **क्या मुझे लाइसेंस चाहिए?** उत्पादन उपयोग के लिए एक अस्थायी या पूर्ण Aspose.Tasks लाइसेंस आवश्यक है; एक मुफ्त ट्रायल उपलब्ध है।  
- **क्या मैं कस्टम फ़ील्ड्स का उपयोग कर सकता हूँ?** हां – आप टास्क में **add extended attribute** कर सकते हैं और उन्हें कस्टम फ़ील्ड्स के रूप में उपयोग कर सकते हैं।  
- **क्या यह सभी प्रोजेक्ट फ़ाइल फ़ॉर्मेट्स के साथ संगत है?** Aspose.Tasks MPP, MPT, और XML फ़ॉर्मेट्स को सपोर्ट करता है।

## पूर्वापेक्षाएँ
शुरू करने से पहले, सुनिश्चित करें कि आपके पास है:

1. **Java Development Environment** – JDK 8+ और IntelliJ IDEA या Eclipse जैसे IDE।  
2. **Aspose.Tasks for Java Library** – लाइब्रेरी को डाउनलोड करके शामिल करें [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/) से।

## पैकेज इम्पोर्ट करें
अपने Java क्लास में Aspose.Tasks नेमस्पेस जोड़ें ताकि आप प्रोजेक्ट्स, टास्क, और विस्तारित एट्रिब्यूट्स के साथ काम कर सकें:

```java
import com.aspose.tasks.*;
```

## प्रोजेक्ट रिपोर्ट जनरेट करें – Create Project Object Java
एक नया `Project` ऑब्जेक्ट इंस्टैंसिएट करें। यह सभी टास्क, रिसोर्सेज, और कस्टम डेटा के कंटेनर के रूप में काम करेगा जिसे आप परिभाषित करेंगे।

```java
Project project = new Project();
```

ऊपर की पंक्ति **creates project object java** करता है जो खाली शुरू होती है और कस्टमाइज़ेशन के लिए तैयार है।

## विस्तारित एट्रिब्यूट कैसे जोड़ें
एक विस्तारित एट्रिब्यूट परिभाषित करें जो प्रत्येक टास्क के लिए कस्टम संख्यात्मक डेटा (जैसे, साइन मान) संग्रहीत करेगा।

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

यहां हम `Number` प्रकार का **add extended attribute** “Sine” नाम से जोड़ते हैं और इसे टास्क के साथ संबद्ध करते हैं।

## विस्तारित एट्रिब्यूट को प्रोजेक्ट में जोड़ें
एट्रिब्यूट परिभाषा को प्रोजेक्ट में रजिस्टर करें ताकि प्रत्येक टास्क इसे रेफ़र कर सके।

```java
project.getExtendedAttributes().add(attr);
```

## एक नया टास्क बनाएं
प्रोजेक्ट के रूट टास्क के तहत “Task” नाम का एक सरल टास्क जोड़ें।

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## विस्तारित एट्रिब्यूट को टास्क के साथ जोड़ें
पहले परिभाषित विस्तारित एट्रिब्यूट को नए बनाए गए टास्क से लिंक करें।

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

अब टास्क में एक कस्टम “Sine” फ़ील्ड है जिसे आप फ़ॉर्मूले या गणनाओं में उपयोग कर सकते हैं। यही तरीका है जिससे आप प्रोग्रामेटिकली **add custom field task** डेटा जोड़ते हैं।

## मूल्यांकन फ़ंक्शन का उपयोग क्यों करें?
Aspose.Tasks फ़ॉर्मूले में MS Project फ़ंक्शन एम्बेड करने से आप सक्षम होते हैं:

- बाहरी टूल्स के बिना ऑन‑द‑फ्लाई गणनाएँ (जैसे, `Sin([Start])`) करना।  
- सभी प्रोजेक्ट लॉजिक को एक ही, मेंटेनेबल कोडबेस में रखें।  
- डायनामिक रिपोर्ट जनरेट करें जो रियल‑टाइम डेटा बदलाव को दर्शाती हैं, जिससे आप **generate project report** स्वचालित रूप से कर सकें।

## सामान्य समस्याएँ और समाधान
| समस्या | समाधान |
|-------|----------|
| **Formula returns `NaN`** | जाँचें कि कस्टम फ़ील्ड प्रकार अपेक्षित संख्यात्मक प्रकार से मेल खाता है। |
| **Extended attribute not visible** | सुनिश्चित करें कि एट्रिब्यूट परिभाषा प्रोजेक्ट में टास्क बनाने **से पहले** जोड़ी गई है। |
| **License exception** | एक अस्थायी या पूर्ण **Aspose.Tasks लाइसेंस** स्थापित करें; ट्रायल मोड कुछ फीचर्स को सीमित कर सकता है। |
| **Missing temporary license** | Aspose वेबसाइट से एक **temporary Aspose license** प्राप्त करें। |

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या Aspose.Tasks for Java जटिल MS Project फ़ॉर्मूले संभाल सकता है?**  
A: हां, Aspose.Tasks for Java कई प्रकार के MS Project फ़ंक्शन के मूल्यांकन को सपोर्ट करता है, जिससे Java एप्लिकेशन्स में जटिल गणनाएँ संभव होती हैं।

**Q: क्या Aspose.Tasks for Java विभिन्न संस्करणों के Microsoft Project फ़ाइलों के साथ संगत है?**  
A: हां, Aspose.Tasks for Java विभिन्न संस्करणों के Microsoft Project फ़ाइलों को सपोर्ट करता है, जिसमें MPP, MPT, और XML फ़ॉर्मेट शामिल हैं।

**Q: क्या मैं Aspose.Tasks for Java को खरीदने से पहले आज़मा सकता हूँ?**  
A: हां, आप वेबसाइट से Aspose.Tasks for Java का मुफ्त ट्रायल संस्करण डाउनलोड कर सकते हैं [here](https://purchase.aspose.com/buy).

**Q: मैं Aspose.Tasks for Java के लिए समर्थन कैसे प्राप्त कर सकता हूँ?**  
A: आप Aspose.Tasks कम्युनिटी फ़ोरम से समर्थन प्राप्त कर सकते हैं [here](https://forum.aspose.com/c/tasks/15).

**Q: क्या Aspose.Tasks for Java के लिए एक अस्थायी लाइसेंस उपलब्ध है?**  
A: हां, आप परीक्षण उद्देश्यों के लिए Aspose वेबसाइट से अस्थायी लाइसेंस प्राप्त कर सकते हैं [here](https://purchase.aspose.com/temporary-license/).

## निष्कर्ष
इन चरणों का पालन करके आपने सीखा कि कैसे **create project object**, **add extended attribute**, और मूल्यांकन फ़ंक्शन का उपयोग करके **generate project report** स्वचालित रूप से किया जाता है। अब आप इस आधार को विस्तारित करके अधिक समृद्ध प्रोजेक्ट एनालिटिक्स, कस्टम डैशबोर्ड, या स्वचालित शेड्यूलिंग टूल बना सकते हैं—सब कुछ Aspose.Tasks for Java द्वारा संचालित।

---

**अंतिम अपडेट:** 2026-02-13  
**परीक्षण किया गया:** Aspose.Tasks for Java 24.10  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}