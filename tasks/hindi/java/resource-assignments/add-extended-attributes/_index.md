---
date: 2026-01-05
description: Aspose.Tasks for Java का उपयोग करके प्रोजेक्ट की प्रारंभ तिथि सेट करना
  और MS Project XML को सहेजना सीखें। जावा डेवलपर्स के लिए चरण‑दर‑चरण गाइड।
linktitle: Add Extended Attributes to Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java के साथ प्रोजेक्ट की शुरूआती तिथि सेट करें
url: /hi/java/resource-assignments/add-extended-attributes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java के साथ प्रोजेक्ट स्टार्ट डेट सेट करें

## परिचय
इस ट्यूटोरियल में आप **प्रोजेक्ट स्टार्ट डेट सेट करने** के बारे में सीखेंगे Microsoft Project फ़ाइल में और फिर **MS Project XML को सेव** करेंगे Aspose.Tasks लाइब्रेरी for Java का उपयोग करके। चाहे आप रिपोर्टिंग पाइपलाइन को ऑटोमेट कर रहे हों या एक कस्टम प्रोजेक्ट‑मैनेजमेंट टूल बना रहे हों, इस कार्य में निपुणता आपके समय की बचत करेगी और मैन्युअल त्रुटियों को समाप्त करेगी।

## त्वरित उत्तर
- **स्टार्ट डेट सेट करने की मुख्य विधि क्या है?** Use `project.set(Prj.START_DATE, …)`.
- **फ़ाइल को एक्सपोर्ट करने के लिए कौन सा फ़ॉर्मेट उपयोग करना चाहिए?** Save it as XML with `SaveFileFormat.Xml`.
- **क्या इस ऑपरेशन के लिए लाइसेंस की आवश्यकता है?** A trial works, but a full license removes watermarks.
- **क्या टास्क बनाने के बाद स्टार्ट डेट बदल सकते हैं?** Yes, update the project property before adding tasks.
- **क्या यह सभी MS Project संस्करणों के साथ संगत है?** Aspose.Tasks supports XML, MPP, and more.

## “Set Project Start Date” क्या है?
प्रोजेक्ट स्टार्ट डेट सेट करने से बेसलाइन कैलेंडर निर्धारित होता है जिससे सभी टास्क शेड्यूलिंग गणनाएँ शुरू होती हैं। यह एक विश्वसनीय प्रोजेक्ट शेड्यूल को प्रोग्रामेटिकली बनाने का पहला कदम है।

## Aspose.Tasks for Java क्यों उपयोग करें?
Aspose.Tasks एक शुद्ध‑Java API प्रदान करता है जो किसी भी प्लेटफ़ॉर्म पर काम करता है बिना Microsoft Project इंस्टॉल किए। यह आपको प्रोजेक्ट डेटा को जल्दी से बनाना, संशोधित करना और एक्सपोर्ट करना देता है, जिससे यह सर्वर‑साइड ऑटोमेशन के लिए आदर्श बनता है।

## आवश्यकताएँ
1. **Java Development Kit (JDK)** – कोई भी नवीनतम JDK संस्करण।
2. **Aspose.Tasks for Java** – डाउनलोड करें [here](https://releases.aspose.com/tasks/java/) से।
3. **IDE** – IntelliJ IDEA, Eclipse, या आपका पसंदीदा Java IDE।

## पैकेज इम्पोर्ट करें
पहले, आवश्यक क्लासेस इम्पोर्ट करें:

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Value;
import java.io.IOException;
import java.math.BigDecimal;
```

### चरण 1: डेटा डायरेक्टरी सेट करें
परिभाषित करें कि उत्पन्न फ़ाइलें कहाँ संग्रहीत होंगी।

```java
String dataDir = "Your Data Directory";
```

### चरण 2: प्रोजेक्ट इंस्टेंस बनाएं
एक नया, खाली प्रोजेक्ट इंस्टैंसिएट करें।

```java
Project project = new Project();
```

### चरण 3: प्रोजेक्ट सूचना प्रॉपर्टीज़ सेट करें
यहाँ हम **प्रोजेक्ट स्टार्ट डेट सेट** करते हैं और संबंधित शेड्यूल प्रॉपर्टीज़।

```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

### चरण 4: MS Project XML सेव करें
कॉन्फ़िगर किए गए प्रोजेक्ट को XML फ़ाइल में एक्सपोर्ट करें।

```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## सामान्य समस्याएँ और समाधान
- **गलत डेट फ़ॉर्मेट:** सुनिश्चित करें कि आप `java.util.Calendar` का उपयोग करें और असाइन करने से पहले `getTime()` कॉल करें।
- **फ़ाइल सेव नहीं हुई:** सत्यापित करें कि `dataDir` एक मौजूदा, लिखने योग्य फ़ोल्डर की ओर इशारा करता है।
- **लाइसेंस चेतावनियाँ:** ट्रायल संस्करण वॉटरमार्क जोड़ता है; इन्हें हटाने के लिए वैध लाइसेंस लागू करें।

## अक्सर पूछे जाने वाले प्रश्न

### प्रश्न: क्या मैं Aspose.Tasks for Java का उपयोग करके MS Project फ़ाइलें पढ़ सकता हूँ?
**A:** हाँ, Aspose.Tasks for Java पढ़ने और लिखने दोनों के लिए मजबूत कार्यक्षमताएँ प्रदान करता है।

### प्रश्न: क्या Aspose.Tasks for Java विभिन्न MS Project संस्करणों के साथ संगत है?
**A:** बिल्कुल, Aspose.Tasks for Java विभिन्न MS Project फ़ॉर्मेट्स को सपोर्ट करता है, जिससे व्यापक संगतता सुनिश्चित होती है।

### प्रश्न: क्या Aspose.Tasks for Java के ट्रायल संस्करण में कोई सीमाएँ हैं?
**A:** ट्रायल संस्करण आपको लाइब्रेरी का अन्वेषण करने देता है लेकिन आउटपुट फ़ाइलों में वॉटरमार्क जोड़ता है।

### प्रश्न: मैं Aspose.Tasks for Java के लिए समर्थन कैसे प्राप्त कर सकता हूँ?
**A:** आप Aspose.Tasks कम्युनिटी फ़ोरम से सहायता ले सकते हैं [here](https://forum.aspose.com/c/tasks/15)।

### प्रश्न: क्या मैं Aspose.Tasks for Java के लिए एक अस्थायी लाइसेंस खरीद सकता हूँ?
**A:** हाँ, अल्पकालिक उपयोग के लिए अस्थायी लाइसेंस उपलब्ध हैं। एक प्राप्त करें [here](https://purchase.aspose.com/temporary-license/)।

### प्रश्न: क्या XML के रूप में सेव करने से कस्टम फ़ील्ड सुरक्षित रहते हैं?
**A:** हाँ, जब आप `SaveFileFormat.Xml` का उपयोग करके सेव करते हैं, तो सभी कस्टम एट्रिब्यूट्स और विस्तारित फ़ील्ड्स बरकरार रहते हैं।

### प्रश्न: क्या टास्क जोड़ने के बाद स्टार्ट डेट बदल सकता हूँ?
**A:** आप सेव करने से पहले कभी भी स्टार्ट डेट अपडेट कर सकते हैं; बस फिर से `project.set(Prj.START_DATE, …)` कॉल करें।

---

**अंतिम अपडेट:** 2026-01-05  
**परीक्षित संस्करण:** Aspose.Tasks for Java 24.12  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}