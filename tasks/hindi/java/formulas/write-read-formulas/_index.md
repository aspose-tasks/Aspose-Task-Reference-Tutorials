---
date: 2025-12-07
description: जानेँ कि Aspose.Tasks for Java का उपयोग करके प्रोजेक्ट फ़ाइल कैसे सहेजें,
  MS Project फ़ॉर्मूले लिखें और पढ़ें, और कस्टम फ़ील्ड फ़ॉर्मूले कैसे जोड़ें।
language: hi
linktitle: Save Project File & Write Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks के साथ प्रोजेक्ट फ़ाइल सहेजें और MS Project फ़ॉर्मूले लिखें
url: /java/formulas/write-read-formulas/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# प्रोजेक्ट फ़ाइल सहेजें और Aspose.Tasks के साथ MS Project फ़ॉर्मूले लिखें

## परिचय
प्रोजेक्ट मैनेजमेंट के क्षेत्र में, डेटा का प्रभावी प्रबंधन अत्यंत महत्वपूर्ण है। Aspose.Tasks for Java एक मजबूत समाधान है जो Microsoft Project फ़ाइलों से डेटा को हेरफेर करने और निकालने में सहायता करता है। इसकी एक शक्तिशाली सुविधा यह है कि यह MS Project फ़ॉर्मूले लिखने और पढ़ने की क्षमता प्रदान करता है। **आप यह भी सीखेंगे कि इन फ़ॉर्मूले को लागू करने के बाद *save project file* कैसे किया जाए**, जिससे आपके परिवर्तन भविष्य के विश्लेषण के लिए संरक्षित रहेंगे। यह ट्यूटोरियल आपको इस कार्यक्षमता का उपयोग करके आपके प्रोजेक्ट मैनेजमेंट कार्यों को बेहतर बनाने की प्रक्रिया में मार्गदर्शन करेगा।

## त्वरित उत्तर
- **“save project file” क्या करता है?** यह सभी इन‑मेमोरी परिवर्तन को डिस्क पर एक .mpp फ़ाइल में वापस लिखता है।  
- **क्या मैं कस्टम फ़ील्ड फ़ॉर्मूले जोड़ सकता हूँ?** हाँ – आप एक कस्टम फ़ील्ड बना सकते हैं और “double task cost” जैसे फ़ॉर्मूला असाइन कर सकते हैं।  
- **कोड चलाने के लिए क्या लाइसेंस चाहिए?** मूल्यांकन के लिए एक फ्री ट्रायल काम करता है; उत्पादन के लिए एक वाणिज्यिक लाइसेंस आवश्यक है।  
- **कौन सा IDE सबसे अच्छा है?** कोई भी Java IDE (IntelliJ IDEA, Eclipse, VS Code) सैंपल को कंपाइल कर देगा।  
- **क्या API नवीनतम MS Project संस्करण के साथ संगत है?** Aspose.Tasks सभी हालिया .mpp फ़ॉर्मैट्स को सपोर्ट करता है।

## Aspose.Tasks में “save project file” क्या है?
प्रोजेक्ट फ़ाइल को सहेजना मतलब `Project` ऑब्जेक्ट की वर्तमान स्थिति—टास्क, रिसोर्सेज, और किसी भी कस्टम फ़ॉर्मूले—को एक भौतिक Microsoft Project फ़ाइल (`.mpp`) में स्थायी रूप से लिखना। यह ऑपरेशन डेटा में बदलाव करने के बाद आवश्यक है, जैसे कि कस्टम फ़ील्ड जोड़ना या टास्क लागत बदलना।

## कस्टम फ़ील्ड जोड़ने और कस्टम फ़ील्ड फ़ॉर्मूला बनाने का कारण क्या है?
कस्टम फ़ील्ड जोड़ने से आप अतिरिक्त जानकारी के लिए एक लचीला कंटेनर प्राप्त करते हैं जो डिफ़ॉल्ट फ़ील्ड्स में नहीं होता। एक फ़ॉर्मूला—जैसे **double task cost**—संलग्न करके आप गणनाओं को स्वचालित करते हैं, मैन्युअल त्रुटियों को कम करते हैं, और अपने शेड्यूल डेटा को सुसंगत रखते हैं।

## पूर्वापेक्षाएँ
इस ट्यूटोरियल को शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यकताएँ हों:

1. **Java Development Kit (JDK)** – आपके मशीन पर Java 8 या उससे ऊपर स्थापित हो।  
2. **Aspose.Tasks for Java** – इसे [here](https://releases.aspose.com/tasks/java/) से डाउनलोड और इंस्टॉल करें।  
3. **Integrated Development Environment (IDE)** – Java विकास के लिए अपना पसंदीदा IDE चुनें (IntelliJ IDEA, Eclipse, VS Code, आदि)।  

## पैकेज इम्पोर्ट करना
शुरू करने के लिए, अपने Java प्रोजेक्ट में आवश्यक पैकेज इम्पोर्ट करें:

```java
import com.aspose.tasks.*;
import java.io.IOException;
import java.math.BigDecimal;
import java.util.Objects;
```

## चरण 1: डेटा डायरेक्टरी सेट अप करें
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```
उस फ़ोल्डर को परिभाषित करें जहाँ आपके MS Project फ़ाइलें स्थित हैं। यही वह जगह है जहाँ आप स्रोत फ़ाइल लोड करेंगे और बाद में **save project file** करेंगे।

## चरण 2: प्रोजेक्ट फ़ाइल लोड करें
```java
Project project = new Project(dataDir + "project.mpp");
```
मौजूदा Microsoft Project फ़ाइल को एक `Project` ऑब्जेक्ट में लोड करें ताकि आप उसकी सामग्री पढ़ या संशोधित कर सकें।

## चरण 3: कस्टम फ़ील्ड जोड़ें और कस्टम फ़ील्ड फ़ॉर्मूला बनाएं
```java
project.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(
        CustomFieldType.Text, ExtendedAttributeTask.Text1, "Custom");
attr.setAlias("Double Costs");
attr.setFormula("[Cost]*2");   // This formula doubles the task cost
project.getExtendedAttributes().add(attr);
```
इस चरण में हम **custom field** “Double Costs” जोड़ते हैं और **custom field formula** बनाते हैं जो टास्क के `[Cost]` को 2 से गुणा करता है, अर्थात **double task cost**। `setFormula` मेथड गणना को सीधे प्रोजेक्ट फ़ाइल में एम्बेड करता है।

## चरण 4: टास्क जोड़ें और लागत सेट करें
```java
Task task = project.getRootTask().getChildren().add("Task");
task.set(Tsk.COST, BigDecimal.valueOf(100));
```
एक नया टास्क बनाएं, फिर बेस लागत `100` असाइन करें। जब प्रोजेक्ट सहेजा जाएगा, कस्टम फ़ील्ड स्वचालित रूप से `200` दिखाएगा क्योंकि पहले परिभाषित फ़ॉर्मूला लागू हो गया है।

## चरण 5: प्रोजेक्ट फ़ाइल सहेजें
```java
project.save(dataDir + "saved.mpp", SaveFileFormat.Mpp);
```
आखिरकार, सभी संशोधनों के साथ **save project file** करें। `save` मेथड अपडेटेड प्रोजेक्ट, जिसमें नया कस्टम फ़ील्ड और उसकी गणना की गई मान शामिल हैं, को `saved.mpp` में लिखता है।

## सामान्य समस्याएँ और समाधान
| समस्या | कारण | समाधान |
|--------|-------|--------|
| **फ़ॉर्मूला लागू नहीं हुआ** | कस्टम फ़ील्ड को प्रोजेक्ट के `ExtendedAttributes` संग्रह में नहीं जोड़ा गया। | सुनिश्चित करें कि `project.getExtendedAttributes().add(attr);` को सहेजने से पहले निष्पादित किया गया है। |
| **फ़ाइल नहीं मिली** | `dataDir` पथ गलत है। | सत्यापित करें कि डायरेक्टरी स्ट्रिंग अंत में एक पाथ सेपरेटर (`/` या `\\`) रखती है। |
| **लागत 0 दिख रही है** | टास्क लागत सहेजने से पहले सेट नहीं की गई। | `project.save` से पहले `task.set(Tsk.COST, ...)` को कॉल करें। |

## अक्सर पूछे जाने वाले प्रश्न
**Q: क्या Aspose.Tasks सभी MS Project संस्करणों के साथ संगत है?**  
A: हाँ, Aspose.Tasks पुराने .mpp फ़ॉर्मैट्स से लेकर नवीनतम रिलीज़ तक के व्यापक MS Project संस्करणों को सपोर्ट करता है।

**Q: क्या मैं Aspose.Tasks को अपने मौजूदा Java प्रोजेक्ट में इंटीग्रेट कर सकता हूँ?**  
A: बिल्कुल। API को सहज इंटीग्रेशन के लिए डिज़ाइन किया गया है; बस Aspose.Tasks JAR को अपने प्रोजेक्ट की क्लासपाथ में जोड़ें।

**Q: क्या मैं बनाते हुए फ़ॉर्मूले के प्रकारों में कोई सीमा है?**  
A: लाइब्रेरी अधिकांश मूल MS Project फ़ॉर्मूला सिंटैक्स को सपोर्ट करती है, जिसमें अंकगणितीय, लॉजिकल, और बिल्ट‑इन फ़ंक्शन शामिल हैं। जटिल कस्टम फ़ंक्शन के लिए वर्कअराउंड की आवश्यकता हो सकती है।

**Q: क्या Aspose.Tasks मल्टी‑प्लेटफ़ॉर्म डिप्लॉयमेंट को सपोर्ट करता है?**  
A: हाँ, लाइब्रेरी किसी भी प्लेटफ़ॉर्म पर चलती है जो Java को सपोर्ट करता है, जिसमें Windows, Linux, और macOS शामिल हैं।

**Q: Aspose.Tasks के लिए तकनीकी समर्थन कैसे प्राप्त करूँ?**  
A: समुदाय सहायता के लिए [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) देखें, या यदि आपके पास वाणिज्यिक लाइसेंस है तो सपोर्ट टिकट खोलें।

## निष्कर्ष
इस ट्यूटोरियल में हमने **save project file**, **custom field जोड़ना**, और **custom field formula बनाना** जो **double task cost** करता है, Aspose.Tasks for Java का उपयोग करके कवर किया। इन चरणों का पालन करके आप गणनाओं को स्वचालित कर सकते हैं, अपने प्रोजेक्ट डेटा को समृद्ध बना सकते हैं, और सभी बदलावों को भविष्य की रिपोर्टिंग और विश्लेषण के लिए संरक्षित रख सकते हैं।

---

**अंतिम अपडेट:** 2025-12-07  
**परीक्षित संस्करण:** Aspose.Tasks for Java 24.12  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}