---
date: 2025-12-31
description: Aspose.Tasks for Java का उपयोग करके प्रोजेक्ट की प्रारंभ तिथि सेट करना,
  प्रोजेक्ट जानकारी लिखना, और प्रोजेक्ट को XML के रूप में सहेजना सीखें।
linktitle: Write Project Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java का उपयोग करके MS Project में प्रोजेक्ट की प्रारंभ तिथि
  सेट करें
url: /hi/java/project-properties/write-project-info/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java का उपयोग करके MS Project में प्रोजेक्ट शुरू होने की तिथि सेट करें

## परिचय
इस ट्यूटोरियल में, आप **प्रोजेक्ट शुरू होने की तिथि सेट करें** और Aspose.Tasks for Java के साथ अतिरिक्त MS Project जानकारी लिखना सीखेंगे। चाहे आप प्रोजेक्ट शेड्यूल को ऑटोमेट कर रहे हों, रिपोर्ट जनरेट कर रहे हों, या प्रोजेक्ट डेटा को बड़े सिस्टम में इंटीग्रेट कर रहे हों, प्रोग्रामेटिक रूप से शुरू तिथि को नियंत्रित करने से आपके टाइमलाइन पर सटीक नियंत्रण मिलता है। हम प्रत्येक चरण को समझेंगे—पर्यावरण सेटअप से लेकर अपडेटेड प्रोजेक्ट को XML फ़ाइल के रूप में सेव करने तक—ताकि आप तुरंत इन तकनीकों को लागू कर सकें।

## त्वरित उत्तर
- **प्रोजेक्ट को संशोधित करने के लिए मुख्य क्लास कौन सी है?** `Project` from the Aspose.Tasks library.  
- **मैं प्रोजेक्ट शुरू होने की तिथि कैसे सेट करूँ?** Use `project.set(Prj.START_DATE, <date>)`.  
- **क्या मैं स्टेटस डेट भी सेट कर सकता हूँ?** Yes, with `project.set(Prj.STATUS_DATE, <date>)`.  
- **प्रोजेक्ट को निर्यात करने के लिए मुझे कौन सा फ़ॉर्मेट उपयोग करना चाहिए?** Save as XML with `SaveFileFormat.Xml`.  
- **उत्पादन उपयोग के लिए क्या मुझे लाइसेंस चाहिए?** A valid Aspose.Tasks license is required for full functionality.

## क्या है **प्रोजेक्ट शुरू होने की तिथि सेट करना**?
**प्रोजेक्ट शुरू होने की तिथि सेट करना** वह कैलेंडर दिन निर्धारित करता है जिससे सभी निर्धारित कार्य शुरू होते हैं। यह टास्क ड्यूरेशन, डिपेंडेंसीज़, और क्रिटिकल पाथ जैसी गणनाओं का एंकर पॉइंट है। इस तिथि को प्रोग्रामेटिक रूप से सेट करके आप कई प्रोजेक्ट फ़ाइलों में स्थिरता सुनिश्चित करते हैं और मैन्युअल एंट्री त्रुटियों से बचते हैं।

## प्रोजेक्ट जानकारी लिखने के लिए Aspose.Tasks for Java का उपयोग क्यों करें?
- **पूर्ण API कवरेज:** Microsoft Project स्थापित किए बिना प्रत्येक प्रोजेक्ट प्रॉपर्टी को पढ़ें, संशोधित करें और लिखें।  
- **क्रॉस‑प्लेटफ़ॉर्म:** Windows, Linux और macOS पर काम करता है।  
- **ऑटोमेशन‑रेडी:** बैच प्रोसेसिंग, CI पाइपलाइन या बैक‑एंड सर्विसेज़ के लिए आदर्श है जो तुरंत प्रोजेक्ट शेड्यूल बनाते हैं।

## पूर्वापेक्षाएँ
1. **Java Development Kit (JDK)** – कोई भी नवीनतम संस्करण (8+ अनुशंसित)।  
2. **Aspose.Tasks for Java लाइब्रेरी** – इसे [यहाँ](https://releases.aspose.com/tasks/java/) से डाउनलोड करें।  
3. **एक IDE** – IntelliJ IDEA, Eclipse, या आपका पसंदीदा Java एडिटर।

## पैकेज इम्पोर्ट करें
सबसे पहले, अपने Java प्रोजेक्ट में आवश्यक पैकेज इम्पोर्ट करें:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## चरण 1: डेटा डायरेक्टरी सेट करें
उस डायरेक्टरी को परिभाषित करें जहाँ आपका प्रोजेक्ट डेटा संग्रहीत होगा।
```java
String dataDir = "Your Data Directory";
```

## चरण 2: प्रोजेक्ट इंस्टेंस बनाएं
एक नया प्रोजेक्ट इंस्टेंस इनिशियलाइज़ करें।
```java
Project project = new Project();
```

## चरण 3: प्रोजेक्ट जानकारी प्रॉपर्टीज़ सेट करें
यहाँ हम **project start date** सेट करते हैं, शुरू से शेड्यूल और स्टेटस डेट—मुख्य और द्वितीयक कीवर्ड *write project information* और *how to set status* को कवर करते हुए।
```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

## चरण 4: प्रोजेक्ट को XML के रूप में सहेजें
अंत में, अपडेटेड प्रोजेक्ट फ़ाइल को सहेजें। यह द्वितीयक कीवर्ड **save project as xml** को दर्शाता है।
```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## सामान्य समस्याएँ और समाधान
| समस्या | कारण | समाधान |
|-------|--------|-----|
| **गलत शुरू तिथि** | Java में कैलेंडर महीना शून्य‑आधारित होता है। | `Calendar.JULY` का उपयोग करें (या महीने के इंडेक्स में 1 जोड़ें) जैसा दिखाया गया है। |
| **फ़ाइल सहेजी नहीं गई** | `dataDir` मौजूद नहीं है या लिखने की अनुमति नहीं है। | डायरेक्टरी को पहले से बनाएं या लिखने योग्य पाथ चुनें। |
| **लाइसेंस चेतावनी** | बिना लाइसेंस के चलाने पर वॉटरमार्क जुड़ता है। | `Project` ऑब्जेक्ट बनाने से पहले वैध Aspose.Tasks लाइसेंस लागू करें। |

## अक्सर पूछे जाने वाले प्रश्न
### Q: क्या मैं Aspose.Tasks for Java का उपयोग करके MS Project फ़ाइलें पढ़ सकता हूँ?
A: हाँ, Aspose.Tasks for Java MS Project फ़ाइलों को पढ़ने और लिखने दोनों के लिए मजबूत कार्यक्षमताएँ प्रदान करता है।  
### Q: क्या Aspose.Tasks for Java विभिन्न संस्करणों के MS Project के साथ संगत है?
A: बिल्कुल, Aspose.Tasks for Java विभिन्न संस्करणों के MS Project को सपोर्ट करता है, जिससे विभिन्न फ़ाइल फ़ॉर्मेट्स के साथ संगतता सुनिश्चित होती है।  
### Q: ट्रायल संस्करण में कोई सीमाएँ हैं क्या?
A: ट्रायल संस्करण लाइब्रेरी की क्षमताओं को एक्सप्लोर करने देता है, लेकिन आउटपुट फ़ाइलों पर वॉटरमार्क जैसे कुछ प्रतिबंध होते हैं।  
### Q: Aspose.Tasks for Java के लिए सपोर्ट कैसे प्राप्त करूँ?
A: आप Aspose.Tasks कम्युनिटी फ़ोरम से सहायता ले सकते हैं [here](https://forum.aspose.com/c/tasks/15)।  
### Q: क्या मैं Aspose.Tasks for Java के लिए अस्थायी लाइसेंस खरीद सकता हूँ?
A: हाँ, अस्थायी लाइसेंस छोटे‑समय उपयोग के लिए उपलब्ध हैं। आप इसे [here](https://purchase.aspose.com/temporary-license/) से प्राप्त कर सकते हैं।

## निष्कर्ष
आपने अब सीख लिया है कि **set project start date**, आवश्यक प्रोजेक्ट जानकारी लिखें, और Aspose.Tasks for Java का उपयोग करके **save project as XML** कैसे करें। ये बिल्डिंग ब्लॉक्स आपको प्रोजेक्ट‑मैनेजमेंट वर्कफ़्लो को ऑटोमेट करने, सुसंगत शेड्यूल बनाने, और MS Project डेटा को अपने Java एप्लिकेशन में इंटीग्रेट करने में सक्षम बनाते हैं।

---

**अंतिम अपडेट:** 2025-12-31  
**परीक्षण किया गया:** Aspose.Tasks for Java 24.12  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}