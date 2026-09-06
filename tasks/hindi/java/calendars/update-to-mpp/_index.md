---
date: 2026-08-13
description: Aspose.Tasks for Java का उपयोग करके MS Project फ़ाइल को MPP के रूप में
  सहेजने, calendar में छुट्टियों को जोड़ने और उसे project को असाइन करने का तरीका सीखें।
keywords:
- add holidays to calendar
- assign calendar to project
- create ms project calendar
- automate schedule generation
- convert project to mpp
lastmod: 2026-08-13
linktitle: Aspose.Tasks में calendar को MPP फ़ॉर्मेट में अपडेट करें
og_description: Aspose.Tasks for Java का उपयोग करके calendar में छुट्टियों को जोड़ें,
  उसे project को असाइन करें, और schedule को MPP में बदलें। चरण‑दर‑चरण automation सीखें।
og_image_alt: Guide showing Java code that adds holidays to a calendar and saves as
  MPP with Aspose.Tasks
og_title: Aspose.Tasks के साथ calendar में छुट्टियों को जोड़ें और MPP के रूप में सहेजें
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to add holidays to a calendar, assign the calendar to a project,
    and save the MS Project file as MPP using Aspose.Tasks for Java.
  headline: Add holidays to calendar and save as MPP with Aspose.Tasks
  type: TechArticle
- description: Learn how to add holidays to a calendar, assign the calendar to a project,
    and save the MS Project file as MPP using Aspose.Tasks for Java.
  name: Add holidays to calendar and save as MPP with Aspose.Tasks
  steps:
  - name: import required packages
    text: First, bring the Aspose.Tasks classes and Java utilities into scope.
  - name: set up the data directory
    text: Define where your input template and output files will live. Replace the
      placeholder with the actual path on your machine.
  - name: define input and output file names
    text: We’ll load an existing MPP file (or a blank project) and write the result
      to a new file.
  - name: load the project and add a new calendar
    text: '`Project` class represents an MS Project file in memory and provides access
      to its calendars, tasks, and resources. Create a `Project` instance from the
      source file and add a calendar named **“Calendar 1”**.'
  - name: customize the calendar (optional)
    text: '`Calendar` object defines working days, hours, and exceptions for a project
      schedule. If you need specific working times, holidays, or exceptions, call
      your own helper method. The sample uses `GetTestCalendar` as a placeholder.
      > **Pro tip:** You can directly manipulate `cal1.getWeekDays()` to set w'
  - name: assign the calendar to the project
    text: Tell the project to use the newly created calendar for all its scheduling
      calculations.
  - name: save the project as MPP
    text: '`SaveFileFormat` enumeration specifies the output format, with `Mpp` indicating
      native Microsoft Project format. Now **convert project to MPP** by saving it
      with the `SaveFileFormat.Mpp` option.'
  - name: confirm successful completion
    text: A simple console message lets you know the process finished without errors.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports all Microsoft Project file formats from Project
      2007 through Project 2024, covering more than 10 versions.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: Absolutely. You can define working days, set custom work weeks, add holidays,
      and even create multiple calendars within a single project file.
    question: Can I customize calendars according to specific project requirements?
  - answer: Yes, you can get help from the Aspose.Tasks community forum [Aspose.Tasks
      community forum](https://forum.aspose.com/c/tasks/15).
    question: Does Aspose.Tasks for Java offer support for troubleshooting and assistance?
  - answer: Yes, a fully functional free trial is available [Aspose.Tasks free trial](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: Temporary licenses can be requested via the Aspose website [Aspose temporary
      license request](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add holidays
- Aspose.Tasks
- Java project scheduling
title: Aspose.Tasks के साथ calendar में छुट्टियों को जोड़ें और MPP के रूप में सहेजें
url: /hi/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# कैलेंडर में छुट्टियां जोड़ें और Aspose.Tasks के साथ MPP के रूप में सहेजें

## परिचय

आधुनिक प्रोजेक्ट मैनेजमेंट में आपको अक्सर **कैलेंडर में छुट्टियां जोड़ने** की आवश्यकता होती है, एक **MS Project कैलेंडर** बनाना होता है, और फिर शेड्यूल को मूल MPP फ़ॉर्मेट में साझा करना होता है। चाहे आप कई स्रोतों से टाइमलाइन को एकीकृत कर रहे हों या लेगेसी डेटा को माइग्रेट कर रहे हों, प्रोग्रामेटिक रूप से कैलेंडर बनाना मैन्युअल त्रुटियों को समाप्त करता है और डिलीवरी को तेज़ करता है। यह ट्यूटोरियल आपको MS Project में कैलेंडर बनाने, उसे छुट्टियों के साथ कस्टमाइज़ करने, **प्रोजेक्ट को कैलेंडर असाइन करने**, और अंत में Aspose.Tasks Java API का उपयोग करके **प्रोजेक्ट को MPP में कनवर्ट करने** की पूरी प्रक्रिया दिखाता है।

## त्वरित उत्तर
- **इस ट्यूटोरियल में क्या कवर किया गया है?** कैलेंडर में छुट्टियां जोड़ना, उसे प्रोजेक्ट को असाइन करना, और Aspose.Tasks for Java के साथ परिणाम को MPP फ़ाइल के रूप में सहेजना।  
- **क्या मुझे लाइसेंस की आवश्यकता है?** विकास के लिए एक फ्री ट्रायल काम करता है; उत्पादन के लिए एक व्यावसायिक लाइसेंस आवश्यक है।  
- **कौन सा Java संस्करण आवश्यक है?** Java 8 या उससे ऊपर (JDK 8+).  
- **क्या मैं कैलेंडर को कस्टमाइज़ कर सकता हूँ?** हाँ – आप कार्य समय, अपवाद, और छुट्टियां जोड़ सकते हैं।  
- **इम्प्लीमेंटेशन में कितना समय लगेगा?** बेसिक कैलेंडर के लिए लगभग 10‑15 मिनट।

## “create calendar MS Project” क्या है?

कैलेंडर MS Project बनाना का अर्थ है कार्य दिवस, घंटे, और अपवादों को परिभाषित करना जो Microsoft Project फ़ाइल के भीतर टास्क शेड्यूलिंग को नियंत्रित करते हैं। Aspose.Tasks का उपयोग करके आप प्रोग्रामेटिक रूप से यह कैलेंडर बना सकते हैं, छुट्टियां सेट कर सकते हैं, और कोड से ही इसे प्रोजेक्ट में एम्बेड कर सकते हैं, बिना MS Project UI खोले।

## इस कार्य के लिए Aspose.Tasks क्यों उपयोग करें?

आपको Aspose.Tasks का उपयोग करना चाहिए क्योंकि यह पूरी Java संगतता प्रदान करता है, Microsoft Office की आवश्यकता नहीं होती, और कोड से सीधे मूल MPP फ़ाइलें जेनरेट और सहेज सकता है। लाइब्रेरी सभी कैलेंडर फीचर्स को सपोर्ट करती है, किसी भी सर्वर वातावरण में काम करती है, और 10,000 टास्क तक के प्रोजेक्ट को एक सेकंड से कम समय में प्रोसेस करती है।

## पूर्वापेक्षाएँ

1. **Java Development Kit (JDK) 8+** – सुनिश्चित करें कि `java -version` 1.8 या नया रिपोर्ट करता है।  
2. **Aspose.Tasks for Java** – नवीनतम JAR को [Aspose वेबसाइट](https://releases.aspose.com/tasks/java/) से डाउनलोड करें।  
3. **IDE** – IntelliJ IDEA, Eclipse, या कोई भी एडिटर जो आप पसंद करते हैं।  
4. **Basic Java knowledge** – क्लास, मेथड, और फ़ाइल I/O की परिचितता।

## कैलेंडर में छुट्टियां कैसे जोड़ें

कैलेंडर में छुट्टियां जोड़ने के लिए आप एक नया `Calendar` ऑब्जेक्ट बनाते हैं, उसकी `Exceptions` कलेक्शन प्राप्त करते हैं, और प्रत्येक छुट्टी तिथि के लिए `DateException` एंट्री जोड़ते हैं। `DateException` कैलेंडर में एकल गैर‑कार्य तिथि या रेंज को दर्शाता है। Aspose.Tasks तब इन तिथियों को गैर‑कार्य दिवस मानता है, जिससे टास्क निर्धारित छुट्टियों के अनुसार शेड्यूल होते हैं।

### चरण 1: आवश्यक पैकेज इम्पोर्ट करें

पहले, Aspose.Tasks क्लासेज़ और Java यूटिलिटीज़ को स्कोप में लाएँ।

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### चरण 2: डेटा डायरेक्टरी सेट अप करें

परिभाषित करें कि आपका इनपुट टेम्प्लेट और आउटपुट फ़ाइलें कहाँ स्थित होंगी। प्लेसहोल्डर को अपने मशीन पर वास्तविक पाथ से बदलें।

```java
String dataDir = "Your Data Directory";
```

### चरण 3: इनपुट और आउटपुट फ़ाइल नाम निर्धारित करें

हम एक मौजूदा MPP फ़ाइल (या एक खाली प्रोजेक्ट) लोड करेंगे और परिणाम को नई फ़ाइल में लिखेंगे।

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### चरण 4: प्रोजेक्ट लोड करें और नया कैलेंडर जोड़ें

`Project` क्लास मेमोरी में एक MS Project फ़ाइल का प्रतिनिधित्व करती है और इसके कैलेंडर, टास्क, तथा रिसोर्सेज़ तक पहुँच प्रदान करती है।

स्रोत फ़ाइल से एक `Project` इंस्टेंस बनाएँ और **“Calendar 1”** नाम का कैलेंडर जोड़ें।

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### चरण 5: कैलेंडर को कस्टमाइज़ करें (वैकल्पिक)

`Calendar` ऑब्जेक्ट प्रोजेक्ट शेड्यूल के लिए कार्य दिवस, घंटे, और अपवादों को परिभाषित करता है।

यदि आपको विशिष्ट कार्य समय, छुट्टियां, या अपवाद चाहिए, तो अपनी हेल्पर मेथड कॉल करें। इस उदाहरण में प्लेसहोल्डर के रूप में `GetTestCalendar` उपयोग किया गया है।

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **Pro tip:** आप सीधे `cal1.getWeekDays()` को मैनिपुलेट करके सप्ताह के प्रत्येक दिन के कार्य घंटे सेट कर सकते हैं, या `cal1.getExceptions()` का उपयोग करके **कैलेंडर में छुट्टियां जोड़ें**।

### चरण 6: कैलेंडर को प्रोजेक्ट को असाइन करें

प्रोजेक्ट को बताएँ कि सभी शेड्यूलिंग गणनाओं के लिए नया बनाया गया कैलेंडर उपयोग करे।

```java
project.set(Prj.CALENDAR, cal1);
```

### चरण 7: प्रोजेक्ट को MPP के रूप में सहेजें

`SaveFileFormat` एनेमरेशन आउटपुट फ़ॉर्मेट को निर्दिष्ट करता है, जहाँ `Mpp` मूल Microsoft Project फ़ॉर्मेट को दर्शाता है।

अब `SaveFileFormat.Mpp` विकल्प के साथ सहेजकर **प्रोजेक्ट को MPP में कनवर्ट** करें।

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### चरण 8: सफल पूर्णता की पुष्टि करें

एक सरल कंसोल संदेश आपको बताता है कि प्रक्रिया बिना त्रुटियों के समाप्त हो गई।

```java
System.out.println("Process completed Successfully");
```

## सामान्य उपयोग केस

- **स्वचालित शेड्यूल जेनरेशन** आवर्ती प्रोजेक्ट्स (जैसे साप्ताहिक स्प्रिंट) के लिए।  
- **लेगेसी CSV या Excel कैलेंडर** को पूर्ण‑फ़ीचर वाले MS Project फ़ाइल में माइग्रेट करना।  
- **सर्वर‑साइड रिपोर्टिंग** जहाँ वेब सर्विस मांग पर MPP फ़ाइल लौटाती है।  

## ट्रबलशूटिंग और सामान्य समस्याएँ

| समस्या | कारण | समाधान |
|-------|-------|-----|
| `project.save` पर `NullPointerException` | `dataDir` एक गैर‑मौजूद फ़ोल्डर की ओर इशारा करता है | डायरेक्टरी मौजूद है यह सुनिश्चित करें या प्रोग्रामेटिक रूप से बनाएं। |
| कैलेंडर टास्क्स पर लागू नहीं हुआ | टास्क अभी भी डिफ़ॉल्ट कैलेंडर को संदर्भित कर रहे हैं | `Prj.CALENDAR` सेट करने के बाद, यदि टास्क पहले ओवरराइड किए गए थे तो प्रत्येक टास्क के `Task.CALENDAR` को भी अपडेट करें। |
| आउटपुट फ़ाइल 0 KB है | लिखने की अनुमति नहीं है | उपयुक्त फ़ाइल सिस्टम अधिकारों के साथ JVM चलाएँ या लिखने योग्य पथ चुनें। |

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या Aspose.Tasks for Java विभिन्न संस्करणों के MS Project के साथ संगत है?**  
A: हाँ, Aspose.Tasks Project 2007 से लेकर Project 2024 तक सभी Microsoft Project फ़ाइल फ़ॉर्मेट्स को सपोर्ट करता है, जो 10 से अधिक संस्करणों को कवर करता है।

**Q: क्या मैं कैलेंडर को विशिष्ट प्रोजेक्ट आवश्यकताओं के अनुसार कस्टमाइज़ कर सकता हूँ?**  
A: बिल्कुल। आप कार्य दिवस निर्धारित कर सकते हैं, कस्टम वर्क वीक सेट कर सकते हैं, छुट्टियां जोड़ सकते हैं, और एक ही प्रोजेक्ट फ़ाइल में कई कैलेंडर भी बना सकते हैं।

**Q: क्या Aspose.Tasks for Java ट्रबलशूटिंग और सहायता के लिए समर्थन प्रदान करता है?**  
A: हाँ, आप Aspose.Tasks समुदाय फ़ोरम से मदद ले सकते हैं [Aspose.Tasks समुदाय फ़ोरम](https://forum.aspose.com/c/tasks/15)।

**Q: क्या Aspose.Tasks for Java के लिए एक फ्री ट्रायल उपलब्ध है?**  
A: हाँ, एक पूरी तरह कार्यात्मक फ्री ट्रायल उपलब्ध है [Aspose.Tasks फ्री ट्रायल](https://releases.aspose.com/)।

**Q: मैं Aspose.Tasks for Java के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूँ?**  
A: अस्थायी लाइसेंस Aspose वेबसाइट के माध्यम से अनुरोध किया जा सकता है [Aspose अस्थायी लाइसेंस अनुरोध](https://purchase.aspose.com/temporary-license/)।

**अंतिम अपडेट:** 2026-08-13  
**परीक्षित संस्करण:** Aspose.Tasks for Java 24.12  
**लेखक:** Aspose  

{{< blocks/products/products-backtop-button >}}

## संबंधित ट्यूटोरियल्स

- [Aspose.Tasks for Java के साथ प्रोजेक्ट में कैलेंडर जोड़ें](/tasks/java/calendars/create/)
- [MS Project कैलेंडर में सप्ताह के दिन कैसे परिभाषित करें – Aspose.Tasks Java](/tasks/java/calendars/)
- [Aspose.Tasks for Java के साथ कस्टम कैलेंडर अपवाद बनाएं](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}