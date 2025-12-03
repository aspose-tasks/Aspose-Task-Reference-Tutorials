---
date: 2025-12-03
description: Aspose.Tasks for Java का उपयोग करके कैलेंडर MS Project बनाना, प्रोजेक्ट
  को MPP में बदलना और प्रोजेक्ट को MPP के रूप में आसानी से सहेजना सीखें।
language: hi
linktitle: Update Calendar to MPP Format in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks के साथ कैलेंडर MS प्रोजेक्ट बनाएं और इसे MPP के रूप में सहेजें
url: /java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks के साथ कैलेंडर MS Project बनाएं और इसे MPP के रूप में सहेजें

## परिचय

आधुनिक प्रोजेक्ट मैनेजमेंट में आपको अक्सर **create calendar MS Project** फ़ाइलें बनानी पड़ती हैं और फिर उन्हें मूल MPP फ़ॉर्मेट में साझा करना होता है। चाहे आप कई स्रोतों से शेड्यूल को एकत्रित कर रहे हों या लेगेसी डेटा को माइग्रेट कर रहे हों, प्रोग्रामेटिक रूप से कैलेंडर जनरेट करना समय बचाता है और मैन्युअल त्रुटियों को समाप्त करता है। यह ट्यूटोरियल आपको MS Project में कैलेंडर बनाने, उसे कस्टमाइज़ करने, और अंत में **convert[ing] project to MPP** Aspose.Tasks Java API का उपयोग करके करने की पूरी प्रक्रिया दिखाता है।

## त्वरित उत्तर
- **इस ट्यूटोरियल में क्या कवर किया गया है?** Aspose.Tasks for Java के साथ MS Project में कैलेंडर बनाना और उसे MPP फ़ाइल के रूप में सहेजना।  
- **क्या मुझे लाइसेंस चाहिए?** विकास के लिए एक फ्री ट्रायल काम करता है; प्रोडक्शन के लिए एक कमर्शियल लाइसेंस आवश्यक है।  
- **कौन सा Java संस्करण आवश्यक है?** Java 8 या उससे ऊपर (JDK 8+).  
- **क्या मैं कैलेंडर को कस्टमाइज़ कर सकता हूँ?** हाँ – आप कार्य समय, अपवाद, और छुट्टियों को जोड़ सकते हैं।  
- **इम्प्लीमेंटेशन में कितना समय लगेगा?** बेसिक कैलेंडर के लिए लगभग 10‑15 मिनट।

## “create calendar MS Project” क्या है?

Creating a calendar MS Project का अर्थ है प्रोग्रामेटिक रूप से कार्य दिवस, घंटे, और अपवाद निर्धारित करना जो Microsoft Project फ़ाइल के भीतर टास्क शेड्यूलिंग को नियंत्रित करते हैं। Aspose.Tasks का उपयोग करके आप इन कैलेंडरों को बना, संशोधित, और बिना Microsoft Project UI खोले ही सहेज सकते हैं।

## इस कार्य के लिए Aspose.Tasks क्यों उपयोग करें?

- **Full .NET/Java compatibility** – वह किसी भी प्लेटफ़ॉर्म पर काम करता है जो Java को सपोर्ट करता है।  
- **No COM or Office installation needed** – सर्वर‑साइड ऑटोमेशन के लिए आदर्श।  
- **Rich API** – सभी कैलेंडर प्रॉपर्टीज़ को सपोर्ट करता है, जिसमें कस्टम वर्क वीक और छुट्टियाँ शामिल हैं।  
- **Direct MPP output** – आप **save project MPP** बिना किसी मध्यवर्ती रूपांतरण के कर सकते हैं।

## पूर्वापेक्षाएँ

1. **Java Development Kit (JDK) 8+** – सुनिश्चित करें कि `java -version` 1.8 या उससे नया दिखाता है।  
2. **Aspose.Tasks for Java** – नवीनतम JAR को [Aspose website](https://releases.aspose.com/tasks/java/) से डाउनलोड करें।  
3. **IDE** – IntelliJ IDEA, Eclipse, या कोई भी एडिटर जो आप पसंद करते हैं।  
4. **Basic Java knowledge** – क्लास, मेथड, और फ़ाइल I/O की बुनियादी समझ।

## चरण‑दर‑चरण गाइड

### चरण 1: आवश्यक पैकेज आयात करें

पहले, Aspose.Tasks क्लासेज़ और Java यूटिलिटीज़ को स्कोप में लाएँ।

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### डेटा डायरेक्टरी सेट अप करें

परिभाषित करें कि आपका इनपुट टेम्प्लेट और आउटपुट फ़ाइलें कहाँ स्थित होंगी। प्लेसहोल्डर को अपने मशीन पर वास्तविक पाथ से बदलें।

```java
String dataDir = "Your Data Directory";
```

### इनपुट और आउटपुट फ़ाइल नाम निर्धारित करें

हम एक मौजूदा MPP फ़ाइल (या एक खाली प्रोजेक्ट) लोड करेंगे और परिणाम को नई फ़ाइल में लिखेंगे।

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### प्रोजेक्ट लोड करें और नया कैलेंडर जोड़ें

स्रोत फ़ाइल से एक `Project` इंस्टेंस बनाएँ और **“Calendar 1”** नाम का कैलेंडर जोड़ें।

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### कैलेंडर को अनुकूलित करें (वैकल्पिक)

यदि आपको विशेष कार्य समय, छुट्टियाँ, या अपवाद चाहिए, तो अपनी हेल्पर मेथड को कॉल करें। इस उदाहरण में `GetTestCalendar` को प्लेसहोल्डर के रूप में उपयोग किया गया है।

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **Pro tip:** आप सीधे `cal1.getWeekDays()` को मैनिपुलेट करके सप्ताह के प्रत्येक दिन के कार्य घंटे सेट कर सकते हैं।

### कैलेंडर को प्रोजेक्ट को असाइन करें

प्रोजेक्ट को बताएँ कि सभी शेड्यूलिंग गणनाओं के लिए नया बनाया गया कैलेंडर उपयोग किया जाए।

```java
project.set(Prj.CALENDAR, cal1);
```

### प्रोजेक्ट को MPP के रूप में सहेजें

अब **convert project to MPP** `SaveFileFormat.Mpp` विकल्प के साथ सहेजकर करें।

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### सफल पूर्णता की पुष्टि करें

एक साधा कंसोल संदेश आपको बताता है कि प्रक्रिया बिना त्रुटियों के समाप्त हो गई।

```java
System.out.println("Process completed Successfully");
```

## सामान्य उपयोग केस

- **स्वचालित शेड्यूल जनरेशन** पुनरावर्ती प्रोजेक्ट्स (जैसे साप्ताहिक स्प्रिंट) के लिए।  
- **लेगेसी CSV या Excel कैलेंडर** को पूरी‑फ़ीचर वाले MS Project फ़ाइल में माइग्रेट करना।  
- **सर्वर‑साइड रिपोर्टिंग** जहाँ एक वेब सर्विस मांग पर MPP फ़ाइल लौटाती है।  

## समस्या निवारण और सामान्य बाधाएँ

| समस्या | कारण | समाधान |
|-------|-------|-----|
| `NullPointerException` on `project.save` | `dataDir` points to a non‑existent folder | सुनिश्चित करें कि डायरेक्टरी मौजूद है या प्रोग्रामिक रूप से इसे बनाएँ। |
| Calendar not applied to tasks | Tasks still reference the default calendar | `Prj.CALENDAR` सेट करने के बाद, यदि टास्क पहले ओवरराइड किए गए थे तो प्रत्येक टास्क के `Task.CALENDAR` को भी अपडेट करें। |
| Output file is 0 KB | Missing write permissions | JVM को उचित फ़ाइल सिस्टम अधिकारों के साथ चलाएँ या लिखने योग्य पाथ चुनें। |

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या Aspose.Tasks for Java विभिन्न संस्करणों के MS Project के साथ संगत है?**  
उत्तर: हाँ, Aspose.Tasks for Java MS Project के कई संस्करणों का समर्थन करता है, Project 2007 से लेकर नवीनतम रिलीज़ तक, जिससे सहज संगतता सुनिश्चित होती है।

**प्रश्न: क्या मैं कैलेंडर को विशिष्ट प्रोजेक्ट आवश्यकताओं के अनुसार कस्टमाइज़ कर सकता हूँ?**  
उत्तर: बिल्कुल। आप कार्य दिवस निर्धारित कर सकते हैं, कस्टम वर्क वीक सेट कर सकते हैं, छुट्टियों को जोड़ सकते हैं, और एक ही प्रोजेक्ट फ़ाइल में कई कैलेंडर भी बना सकते हैं।

**प्रश्न: क्या Aspose.Tasks for Java समस्या निवारण और सहायता के लिए समर्थन प्रदान करता है?**  
उत्तर: हाँ, आप Aspose.Tasks कम्युनिटी फ़ोरम से यहाँ मदद ले सकते हैं: [here](https://forum.aspose.com/c/tasks/15)।

**प्रश्न: क्या Aspose.Tasks for Java के लिए एक फ्री ट्रायल उपलब्ध है?**  
उत्तर: हाँ, एक पूरी तरह कार्यशील फ्री ट्रायल यहाँ उपलब्ध है: [here](https://releases.aspose.com/)।

**प्रश्न: मैं Aspose.Tasks for Java के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूँ?**  
उत्तर: अस्थायी लाइसेंस Aspose वेबसाइट से यहाँ अनुरोध किया जा सकता है: [here](https://purchase.aspose.com/temporary-license/)।

---

**अंतिम अपडेट:** 2025-12-03  
**परीक्षित संस्करण:** Aspose.Tasks for Java 24.12  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}