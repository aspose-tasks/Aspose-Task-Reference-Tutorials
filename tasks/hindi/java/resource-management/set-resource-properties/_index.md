---
date: 2026-01-18
description: जानेँ कि Aspose.Tasks for Java का उपयोग करके MS Project में मानक दर और
  अन्य संसाधन गुण कैसे सेट करें, जिसमें संसाधन को MS Project में जोड़ना और संसाधनों
  का प्रभावी प्रबंधन कैसे किया जाए, शामिल है।
linktitle: Set Resource Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks में संसाधनों के लिए मानक दर कैसे सेट करें
url: /hi/java/resource-management/set-resource-properties/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में रिसोर्स के लिए स्टैंडर्ड रेट सेट करें

## परिचय
यदि आप Java एप्लिकेशन बना रहे हैं जिन्हें Microsoft Project फ़ाइलों के साथ इंटरैक्ट करना है, तो **रिसोर्स के लिए स्टैंडर्ड रेट सेट करना** सबसे आम कार्यों में से एक है। इस ट्यूटोरियल में आप सीखेंगे कि **स्टैंडर्ड रेट** और अन्य रिसोर्स प्रॉपर्टीज़ को Aspose.Tasks for Java का उपयोग करके कैसे सेट किया जाता है। गाइड के अंत तक आप एक प्रोजेक्ट ऑब्जेक्ट बना पाएँगे, MS Project फ़ाइल में रिसोर्स जोड़ पाएँगे, और आत्मविश्वास के साथ MS Project रिसोर्सेज़ को मैनेज कर पाएँगे।

## त्वरित उत्तर
- **प्रोजेक्ट फ़ाइल के साथ काम करने के लिए मुख्य क्लास कौन सी है?** `Project`
- **नया रिसोर्स जोड़ने की मेथड कौन सी है?** `project.getResources().add()`
- **स्टैंडर्ड रेट कैसे सेट करते हैं?** `rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(...))`
- **क्या प्रोडक्शन के लिए लाइसेंस चाहिए?** हाँ, एक वैध Aspose.Tasks लाइसेंस आवश्यक है।
- **कौन सा Java संस्करण समर्थित है?** Java 8+ (नवीनतम JDK की सलाह दी जाती है)।

## “set standard rate” क्या है?
*set standard rate* ऑपरेशन रिसोर्स को एक डिफ़ॉल्ट प्रति घंटे लागत असाइन करता है। प्रोजेक्ट मैनेजर्स इस मान का उपयोग लेबर कॉस्ट की गणना, लागत रिपोर्ट जनरेट करने, और बजट का पूर्वानुमान लगाने के लिए करते हैं।

## Aspose.Tasks के साथ रेट सेट क्यों करें?
- **Microsoft Project इंस्टॉलेशन की आवश्यकता नहीं** – फ़ाइलों को सीधे Java से मैनीपुलेट करें।
- **पूर्ण फ़िडेलिटी** – ओवरटाइम और कॉस्ट रेट सहित सभी रिसोर्स फ़ील्ड संरक्षित रहते हैं।
- **क्रॉस‑प्लेटफ़ॉर्म** – Windows, Linux, और macOS पर काम करता है।
- **ऑटोमेशन‑फ्रेंडली** – बैच प्रोसेसिंग या CI पाइपलाइन के साथ इंटीग्रेशन के लिए आदर्श।

## पूर्वापेक्षाएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

### Java डेवलपमेंट एनवायरनमेंट सेटअप
1. JDK इंस्टॉल करें: सुनिश्चित करें कि आपके सिस्टम पर Java Development Kit (JDK) इंस्टॉल है। आप इसे [Oracle वेबसाइट](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) से डाउनलोड कर सकते हैं।
2. IDE सेटअप: IntelliJ IDEA, Eclipse, या NetBeans जैसे किसी Integrated Development Environment (IDE) को चुनें और अपने मशीन पर सेटअप करें।

### Aspose.Tasks for Java इंस्टॉलेशन
1. Aspose.Tasks for Java डाउनलोड करें: [download page](https://releases.aspose.com/tasks/java/) पर जाएँ और Aspose.Tasks for Java का नवीनतम संस्करण प्राप्त करें।
2. प्रोजेक्ट में इंटीग्रेट करें: Aspose.Tasks for Java लाइब्रेरी को अपने Java प्रोजेक्ट में डिपेंडेंसी के रूप में जोड़ें।

## पैकेज इम्पोर्ट करें
शुरू करने के लिए, आपको Aspose.Tasks for Java से आवश्यक पैकेज अपने प्रोजेक्ट में इम्पोर्ट करने होंगे। यह स्टेप सुनिश्चित करता है कि आपको आवश्यक फ़ंक्शनैलिटी तक पहुँच है।

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import java.math.BigDecimal;
```

## चरण 1: प्रोजेक्ट ऑब्जेक्ट बनाएं
एक **प्रोजेक्ट ऑब्जेक्ट** बनाना किसी भी MS Project मैनीपुलेशन का पहला कदम है। यह पूरी प्रोजेक्ट फ़ाइल को मेमोरी में प्रतिनिधित्व करता है।

```java
Project project = new Project();
```

## चरण 2: रिसोर्स जोड़ें (add resource ms project)
अब हम **रिसोर्स MS Project** को Resources कलेक्शन का उपयोग करके जोड़ेंगे। रिसोर्स का नाम आपके शेड्यूल के अनुसार कोई भी समझदारीपूर्ण नाम हो सकता है।

```java
Resource rsc = project.getResources().add("Rsc");
```

## चरण 3: रिसोर्स प्रॉपर्टीज़ सेट करें (how to set rates)
यहाँ हम **स्टैंडर्ड रेट** सेट करेंगे और साथ ही ओवरटाइम रेट कैसे सेट किया जाता है, यह भी दिखाएंगे। ये रेट `BigDecimal` वैल्यू के रूप में स्टोर होते हैं ताकि प्रिसीजन बना रहे।

```java
// Set standard rate for the resource
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(15));
// Set overtime rate for the resource
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(20));
```

## सामान्य समस्याएँ और समाधान
| समस्या | क्यों होता है | समाधान |
|-------|----------------|-----|
| `NullPointerException` जब `set` कॉल किया जाता है | रिसोर्स सही तरीके से नहीं जोड़ा गया था। | सुनिश्चित करें कि `project.getResources().add()` एक non‑null `Resource` रिटर्न करता है। |
| सेव्ड फ़ाइल में रेट 0 दिख रहा है | `int` के बजाय `BigDecimal` का उपयोग नहीं किया गया। | मौद्रिक मानों के लिए हमेशा `BigDecimal.valueOf()` का उपयोग करें। |
| लाइसेंस नहीं मिला | प्रोजेक्ट बनाने से पहले लाइसेंस फ़ाइल लोड नहीं हुई। | लाइसेंस लोड करें (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`) प्रोग्राम की शुरुआत में। |

## निष्कर्ष
इन चरणों का पालन करके आपने सीखा कि **प्रोजेक्ट ऑब्जेक्ट कैसे बनाते हैं**, **रिसोर्स MS Project कैसे जोड़ते हैं**, और **स्टैंडर्ड रेट** सहित अन्य रिसोर्स प्रॉपर्टीज़ कैसे सेट करते हैं। यह आपको लागत गणना को ऑटोमेट करने, कस्टम रिपोर्ट जनरेट करने, और Java से पूरी तरह MS Project रिसोर्सेज़ को मैनेज करने की शक्ति देता है।

## अक्सर पूछे जाने वाले प्रश्न
### क्या Aspose.Tasks for Java जटिल MS Project फ़ाइलों को संभाल सकता है?
हाँ, Aspose.Tasks for Java विभिन्न MS Project फ़ाइल फ़ॉर्मैट्स को संभालने में सक्षम है, जिसमें विस्तृत टास्क हायरार्की वाली जटिल फ़ाइलें भी शामिल हैं।
### क्या Aspose.Tasks for Java के लिए कोई फ्री ट्रायल उपलब्ध है?
हाँ, आप [यहाँ](https://releases.aspose.com/) से Aspose.Tasks for Java का फ्री ट्रायल एक्सेस कर सकते हैं।
### Aspose.Tasks for Java के लिए सपोर्ट कहाँ मिल सकता है?
आप [support forum](https://forum.aspose.com/c/tasks/15) पर Aspose.Tasks for Java से संबंधित सहायता और चर्चा में भाग ले सकते हैं।
### Aspose.Tasks for Java के लिए अस्थायी लाइसेंस कैसे प्राप्त करें?
आप मूल्यांकन उद्देश्यों के लिए [temporary license page](https://purchase.aspose.com/temporary-license/) से अस्थायी लाइसेंस प्राप्त कर सकते हैं।
### Aspose.Tasks for Java का लाइसेंस्ड वर्ज़न कहाँ खरीदें?
आप [purchase page](https://purchase.aspose.com/buy) से Aspose.Tasks for Java का लाइसेंस्ड वर्ज़न खरीद सकते हैं।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-18  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose