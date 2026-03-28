---
date: 2026-01-28
description: Aspose.Tasks for Java का उपयोग करके कैलेंडर अपवाद कैसे बनाएं, कैलेंडर
  अपवादों को कुशलतापूर्वक जोड़ें और हटाएं, और प्रोजेक्ट शेड्यूलिंग में सुधार करें,
  यह सीखें।
linktitle: Add and Remove Calendar Exceptions in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose for Java में कैलेंडर अपवाद बनाएं
url: /hi/java/calendar-exceptions/add-remove/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा के लिए Aspose कैलेंडर एक्सेप्शन बनाएं

## परिचय
सटीक प्रोजेक्ट शेड्यूलिंग अक्सर **कैलेंडर एक्सेप्शन** को संभालने पर निर्भर करती है—ऐसे दिन जब संसाधन उपलब्ध नहीं होते या कार्य शेड्यूल बदलते हैं। **Aspose.Tasks for Java** के साथ, आप **create calendar exception** ऑब्जेक्ट बना सकते हैं, उन्हें प्रोजेक्ट कैलेंडर में जोड़ सकते हैं, या जब उनकी अब आवश्यकता न हो तो उन्हें हटा सकते हैं। इस ट्यूटोरियल में हम पूरी प्रक्रिया को चरण‑दर‑चरण देखेंगे, प्रोजेक्ट फ़ाइल लोड करने से लेकर आप द्वारा प्रबंधित एक्सेप्शन की पुष्टि तक। यह गाइड आपको दिखाता है कि जावा वातावरण में **create calendar exception aspose** कैसे किया जाता है।

### त्वरित उत्तर
- **“create calendar exception” का क्या अर्थ है?** इसका मतलब है एक तिथि सीमा को परिभाषित करना जो मानक कार्य कैलेंडर से अलग हो।  
- **कौन सी लाइब्रेरी यह क्षमता प्रदान करती है?** Aspose.Tasks for Java।  
- **क्या इसे आज़माने के लिए लाइसेंस चाहिए?** एक मुफ्त ट्रायल उपलब्ध है; प्रोडक्शन उपयोग के लिए लाइसेंस आवश्यक है।  
- **क्या मैं मौजूदा एक्सेप्शन को हटा सकता हूँ?** हाँ—कैलेंडर की एक्सेप्शन सूची में उसे ढूँढ़ें और हटाएँ।  
- **क्या यह Microsoft Project फ़ाइलों के साथ संगत है?** बिल्कुल; Aspose.Tasks सभी प्रमुख .mpp संस्करणों को पढ़ता और लिखता है।

#### पूर्वापेक्षाएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास हैं:

- स्थापित Java Development Kit (JDK)।  
- आपके प्रोजेक्ट के क्लासपाथ में Aspose.Tasks for Java लाइब्रेरी।  
- Java और प्रोजेक्ट‑मैनेजमेंट शब्दावली की बुनियादी समझ।

## How to create calendar exception Aspose with Java
नीचे एक चरण‑दर‑चरण walkthrough दिया गया है जो प्रत्येक कोड स्निपेट के उद्देश्य को चलाने से पहले समझाता है। इन सेक्शन को क्रम में फॉलो करें ताकि आपके कैलेंडर एक्सेप्शन सही ढंग से संभाले जा सकें।

## Import Packages
पहले, मुख्य Aspose.Tasks क्लासेज़ को इम्पोर्ट करें जो कैलेंडर मैनिपुलेशन को सक्षम करती हैं।

```java
import com.aspose.tasks.*;
```

## Step 1: Load the Project and Access Its Calendar
हम एक मौजूदा Microsoft Project फ़ाइल (`input.mpp`) लोड करते हैं और कलेक्शन में पहला कैलेंडर प्राप्त करते हैं। यदि आपको कोई अलग कैलेंडर चाहिए तो इंडेक्स को बदल सकते हैं।

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "input.mpp");
Calendar cal = project.getCalendars().toList().get(0);
```

## Step 2: Remove an Existing Exception (If Needed)
कभी‑कभी कैलेंडर में पहले से मौजूद एक्सेप्शन होते हैं जिन्हें आप साफ़ करना चाहते हैं। नीचे दिया गया स्निपेट एक्सेप्शन सूची की जाँच करता है और यदि एक से अधिक एक्सेप्शन हैं तो पहला एंट्री हटाता है।

```java
if (cal.getExceptions().size() > 1) {
    CalendarException exc = cal.getExceptions().get(0);
    cal.getExceptions().remove(exc);
}
```

> **Pro tip:** आइटम हटाने से पहले हमेशा एक्सेप्शन सूची के आकार की जाँच करें ताकि `IndexOutOfBoundsException` से बचा जा सके।

## Step 3: Create (Add) a New Calendar Exception
अब हम **create calendar exception** ऑब्जेक्ट बनाते हैं। इस उदाहरण में हम 1‑3 जनवरी, 2009 की अवधि को परिभाषित करते हैं। अपनी प्रोजेक्ट टाइमलाइन के अनुसार तिथियों को समायोजित करें।

```java
CalendarException calExc = new CalendarException();
java.util.Calendar calObject = java.util.Calendar.getInstance();
calObject.set(2009, java.util.Calendar.JANUARY, 1, 0, 0, 0);
calExc.setFromDate(calObject.getTime());
calObject.set(2009, java.util.Calendar.JANUARY, 3, 0, 0, 0);
calExc.setToDate(calObject.getTime());
cal.getExceptions().add(calExc);
```

> **Why this matters:** एक्सेप्शन जोड़ने से आप छुट्टियों, मेंटेनेंस विंडो, या किसी भी गैर‑कार्य अवधि को सीधे प्रोजेक्ट शेड्यूल में मॉडल कर सकते हैं। यह **create calendar exception aspose** कार्यक्षमता का मूल है।

## Step 4: Display All Exceptions for Verification
एक्सेप्शन जोड़ने (या हटाने) के बाद, उन्हें प्रिंट करना एक अच्छा अभ्यास है। यह आपको यह पुष्टि करने में मदद करता है कि कैलेंडर ने इच्छित बदलावों को सही ढंग से दर्शाया है।

```java
for (CalendarException calExc1 : cal.getExceptions()) {
    System.out.println("From " + calExc1.getFromDate().toString());
    System.out.println("To   " + calExc1.getToDate().toString());
}
```

## Common Issues & Solutions
| Issue | Cause | Fix |
|-------|-------|-----|
| कोई आउटपुट नहीं दिख रहा | एक्सेप्शन सूची खाली है | इटररेट करने से पहले सुनिश्चित करें कि आपने एक्सेप्शन जोड़ा है। |
| `project` पर `NullPointerException` | फ़ाइल पाथ गलत है | `dataDir` को वैध `.mpp` फ़ाइल की ओर इंगित करने के लिए जाँचें। |
| तिथियाँ एक दिन आगे/पीछे | टाइम‑ज़ोन अंतर | स्पष्ट टाइम ज़ोन के साथ `java.util.Calendar` या `java.time` API का उपयोग करें। |

## Frequently Asked Questions

**Q: क्या मैं Aspose.Tasks for Java का उपयोग करके कैलेंडर में कई एक्सेप्शन जोड़ सकता हूँ?**  
A: हाँ। प्रत्येक तिथि सीमा के लिए नया `CalendarException` बनाएँ और लूप के भीतर `cal.getExceptions()` में जोड़ें।

**Q: क्या Aspose.Tasks for Java सभी संस्करणों की Microsoft Project फ़ाइलों के साथ संगत है?**  
A: Aspose.Tasks व्यापक .mpp संस्करणों को सपोर्ट करता है, Project 98 से लेकर नवीनतम रिलीज़ तक, जिससे सहज इंटीग्रेशन सुनिश्चित होता है।

**Q: प्रोजेक्ट कैलेंडर में आवर्ती एक्सेप्शन (जैसे साप्ताहिक मीटिंग) को कैसे संभालूँ?**  
A: `CalendarException` की recurrence प्रॉपर्टीज़ (`setRecurrencePattern`) का उपयोग करके दैनिक, साप्ताहिक या मासिक दोहराव जैसे जटिल पैटर्न परिभाषित करें।

**Q: क्या Aspose.Tasks for Java का ट्रायल संस्करण उपलब्ध है?**  
A: हाँ, आप सभी फीचर्स को आज़माने के लिए [website](https://releases.aspose.com/) से मुफ्त ट्रायल डाउनलोड कर सकते हैं।

**Q: Aspose.Tasks for Java से संबंधित किसी भी समस्या या प्रश्न के लिए मैं कहाँ सहायता प्राप्त कर सकता हूँ?**  
A: प्रश्न पूछने के लिए Aspose.Tasks फ़ोरम for Java पर जाएँ [website](https://reference.aspose.com/tasks/java/) या सीधे Aspose सपोर्ट से संपर्क करें।

## निष्कर्ष
कैलेंडर एक्सेप्शन का प्रबंधन वास्तविक प्रोजेक्ट टाइमलाइन और संसाधन योजना के लिए आवश्यक है। **Aspose.Tasks for Java** के साथ, आप **create calendar exception** ऑब्जेक्ट बना सकते हैं, उन्हें किसी भी प्रोजेक्ट कैलेंडर में जोड़ सकते हैं, और जब उनकी आवश्यकता न रहे तो उन्हें हटा सकते हैं—सिर्फ कुछ लाइनों के कोड से। यह **create calendar exception aspose** क्षमता आपको ऐसे शेड्यूल बनाने में सक्षम बनाती है जो वास्तविक‑विश्व प्रतिबंधों को सही ढंग से दर्शाते हैं।

---

**Last Updated:** 2026-01-28  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}