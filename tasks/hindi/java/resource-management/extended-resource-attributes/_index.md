---
date: 2026-01-13
description: Aspose.Tasks for Java के साथ कस्टम एट्रिब्यूट बनाना, Microsoft Project
  फ़ाइल लोड करना, संख्यात्मक मान सेट करना, और प्रोजेक्ट को XML के रूप में सहेजना सीखें।
linktitle: Handle Extended Resource Attributes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks का उपयोग करके MS Project में कस्टम एट्रिब्यूट कैसे बनाएं
url: /hi/java/resource-management/extended-resource-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks का उपयोग करके MS Project में कस्टम एट्रिब्यूट कैसे बनाएं

## Introduction
इस ट्यूटोरियल में, **आप सीखेंगे कि Microsoft Project फ़ाइल में संसाधनों के लिए कस्टम एट्रिब्यूट कैसे बनाएं** Aspose.Tasks for Java का उपयोग करके। हम Microsoft Project फ़ाइल को लोड करने, एक नया संख्यात्मक एट्रिब्यूट परिभाषित करने, मान असाइन करने, और अंत में प्रोजेक्ट को XML के रूप में सहेजने की प्रक्रिया को चरण‑दर‑चरण देखेंगे। अंत तक, आपके पास एक स्पष्ट, व्यावहारिक उदाहरण होगा जिसे आप अपने प्रोजेक्ट‑मैनेजमेंट समाधान में अनुकूलित कर सकते हैं।

## Quick Answers
- **कस्टम एट्रिब्यूट** का क्या मतलब है?  
  एक उपयोगकर्ता‑परिभाषित फ़ील्ड जो संसाधन या टास्क के लिए अतिरिक्त जानकारी (जैसे, आयु, कौशल स्तर) संग्रहीत करता है।  
- **यह कौन सी लाइब्रेरी संभालती है?**  
  Aspose.Tasks for Java एक फ्लुएंट API प्रदान करता है जिससे आप कस्टम एट्रिब्यूट बना और प्रबंधित कर सकते हैं।  
- **क्या मुझे लाइसेंस चाहिए?**  
  मूल्यांकन के लिए एक मुफ्त अस्थायी लाइसेंस काम करता है; उत्पादन के लिए पूर्ण लाइसेंस आवश्यक है।  
- **क्या मैं संख्यात्मक मान सेट कर सकता हूँ?**  
  हां – `setNumericValue` को `BigDecimal` (जैसे, `30.5345`) के साथ उपयोग करें।  
- **प्रोजेक्ट कैसे सहेजा जाता है?**  
  परिवर्तित फ़ाइल को `SaveFileFormat.Xml` का उपयोग करके XML के रूप में सहेजा जा सकता है।

## What is a Custom Attribute?
एक **कस्टम एट्रिब्यूट** (जिसे एक्सटेंडेड एट्रिब्यूट भी कहा जाता है) वह अतिरिक्त कॉलम है जिसे आप Microsoft Project में संसाधनों या टास्क के लिए जोड़ सकते हैं। यह आपको उन डेटा को कैप्चर करने की अनुमति देता है जो बिल्ट‑इन फ़ील्ड्स में नहीं होते, जैसे कर्मचारी की आयु, प्रमाणन स्तर, या कोई भी व्यवसाय‑विशिष्ट मीट्रिक।

## Why Create a Custom Attribute in MS Project?
- **अपने संगठन की जरूरतों के अनुसार प्रोजेक्ट डेटा को अनुकूलित करें।**  
- **उन्नत रिपोर्टिंग सक्षम करें** उन मानों को संग्रहीत करके जिन्हें बाद में क्वेरी किया जा सकता है।  
- **कई प्रोजेक्ट्स में स्थिरता बनाए रखें** समान एट्रिब्यूट परिभाषा को प्रोग्रामेटिक रूप से लागू करके।

## Prerequisites
शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

1. **Java Development Environment** – JDK 8 या उससे ऊपर स्थापित हो।  
2. **Aspose.Tasks for Java** – नवीनतम संस्करण [यहाँ](https://releases.aspose.com/tasks/java/) से डाउनलोड करें।  
3. **IDE** – Eclipse, IntelliJ IDEA, या कोई भी Java‑compatible IDE।

## Step‑by‑Step Guide

### Import Packages
पहले, उन Aspose.Tasks क्लासेज़ को इम्पोर्ट करें जिनकी आपको आवश्यकता होगी। ये प्रोजेक्ट, रिसोर्स और एक्सटेंडेड एट्रिब्यूट को संभालने की मुख्य कार्यक्षमता प्रदान करते हैं।

```java
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.SaveFileFormat;
import java.math.BigDecimal;
```

### Step 1: Define Data Directory
उस फ़ोल्डर को सेट करें जहाँ आपका स्रोत प्रोजेक्ट फ़ाइल स्थित है और जहाँ आउटपुट लिखा जाएगा।

```java
String dataDir = "Your Data Directory";
```

### Step 2: Load Microsoft Project File
एक `Project` इंस्टेंस बनाकर मौजूदा फ़ाइल को लोड करें। यह **Microsoft प्रोजेक्ट फ़ाइल लोड** करने का चरण है जो आपको उसकी सामग्री तक पूर्ण पहुंच देता है।

```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```

### Step 3: Define the Custom Attribute
हम एक नया संख्यात्मक एट्रिब्यूट **Age** परिभाषित करेंगे। API जांचता है कि परिभाषा पहले से मौजूद है या नहीं; यदि नहीं, तो यह नई बनाता है।

```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```

### Step 4: Set Numeric Value in Java
किसी विशिष्ट रिसोर्स के लिए एट्रिब्यूट का एक इंस्टेंस बनाएं और `setNumericValue` का उपयोग करके संख्यात्मक मान असाइन करें। यह **set numeric value java** को क्रियान्वित करने का उदाहरण है।

```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```

### Step 5: Add Resource and Attach the Custom Attribute
एक नया रिसोर्स **R1** जोड़ें और पहले बनाए गए कस्टम एट्रिब्यूट को उससे संलग्न करें।

```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```

### Step 6: Save Project as XML
अंत में, परिवर्तन को सहेजने के लिए प्रोजेक्ट को सेव करें। यह **save project as xml** चरण है, जो अपडेटेड फ़ाइल का साफ़ XML प्रतिनिधित्व उत्पन्न करता है।

```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```

### Step 7: Display Result
एक मित्रवत पुष्टि संदेश प्रिंट करें ताकि आपको पता चले कि प्रक्रिया बिना त्रुटियों के पूरी हो गई।

```java
System.out.println("Process completed Successfully");
```

इन चरणों का पालन करके, आपने सफलतापूर्वक **कस्टम एट्रिब्यूट बनाया**, Microsoft Project फ़ाइल लोड की, Java का उपयोग करके संख्यात्मक मान सेट किया, और प्रोजेक्ट को XML के रूप में सहेजा।

## Common Pitfalls & Tips
- **एट्रिब्यूट ID टकराव:** नया परिभाषा बनाने से पहले हमेशा `getById` से जाँचें ताकि डुप्लिकेट IDs न बनें।  
- **प्रिसीजन हैंडलिंग:** `BigDecimal` दशमलव प्रिसीजन को बरकरार रखता है; सटीक मानों के लिए `float` या `double` का उपयोग न करें।  
- **फ़ाइल पाथ्स:** `FileNotFoundException` से बचने के लिए पूर्ण पाथ्स का उपयोग करें या अपने IDE की वर्किंग डायरेक्टरी को कॉन्फ़िगर करें।  

## Frequently Asked Questions

**Q: क्या मैं टास्क के लिए भी कस्टम एट्रिब्यूट बना सकता हूँ?**  
A: हां – एट्रिब्यूट परिभाषित करते समय `ExtendedAttributeTask` का उपयोग करें, `ExtendedAttributeResource` के बजाय।

**Q: क्या एक साथ कई कस्टम एट्रिब्यूट जोड़ना संभव है?**  
A: बिल्कुल। प्रत्येक एट्रिब्यूट के लिए अलग `ExtendedAttributeDefinition` ऑब्जेक्ट बनाएं और उन्हें इच्छित रिसोर्स या टास्क से संलग्न करें।

**Q: मैं प्रोजेक्ट को किन फ़ॉर्मैट्स में सहेज सकता हूँ?**  
A: Aspose.Tasks XML, MPP, तथा PDF, HTML जैसे कई अन्य फ़ॉर्मैट्स को सपोर्ट करता है। इस उदाहरण में हमने `SaveFileFormat.Xml` का उपयोग किया।

**Q: विकास बिल्ड्स के लिए क्या मुझे Aspose.Tasks का लाइसेंस चाहिए?**  
A: मूल्यांकन के लिए एक अस्थायी लाइसेंस पर्याप्त है। उत्पादन परिनियोजन के लिए पूर्ण लाइसेंस आवश्यक है।

**Q: बाद में कस्टम एट्रिब्यूट मान कैसे पढ़ूँ?**  
A: `resource.getExtendedAttributes()` का उपयोग करके संलग्न एट्रिब्यूट्स पर इटरेट करें और `getNumericValue()` या `getTextValue()` से उनके मान प्राप्त करें।

## Conclusion
Aspose.Tasks for Java के साथ Microsoft Project में **कस्टम एट्रिब्यूट** बनाना सीधा है जब आप वर्कफ़्लो समझते हैं: प्रोजेक्ट लोड करें, एट्रिब्यूट परिभाषित करें, उसका मान सेट करें, उसे रिसोर्स से संलग्न करें, और फ़ाइल सहेजें। यह दृष्टिकोण आपको प्रोजेक्ट डेटा मॉडल को प्रोग्रामेटिक रूप से विस्तारित करने की शक्ति देता है, जिससे रिपोर्टिंग अधिक समृद्ध होती है और आपके व्यवसाय प्रक्रियाओं के साथ एकीकरण कड़ा होता है।

---

**Last Updated:** 2026-01-13  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}