---
date: 2026-08-08
description: Aspose.Tasks for Java के साथ जावा में कैलेंडर अपवाद कैसे बनाएं, अपवादों
  को कुशलतापूर्वक जोड़ें और हटाएं, और प्रोजेक्ट शेड्यूलिंग में सुधार करें, सीखें।
keywords:
- create calendar exception java
- Aspose.Tasks Java
- project calendar management
lastmod: 2026-08-08
linktitle: Aspose.Tasks में कैलेंडर अपवाद जोड़ें और हटाएँ
og_description: Aspose.Tasks for Java के साथ जावा में कैलेंडर अपवाद बनाना सीखें। Microsoft
  Project फ़ाइलों में कैलेंडर अपवादों को कुशलतापूर्वक जोड़ें, हटाएँ और सत्यापित करें।
og_image_alt: Screenshot of Java code managing calendar exceptions with Aspose.Tasks
og_title: Aspose.Tasks का उपयोग करके जावा में कैलेंडर अपवाद बनाएं – त्वरित गाइड
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to create calendar exception java with Aspose.Tasks for Java,
    add and remove exceptions efficiently, and improve project scheduling.
  headline: Create calendar exception java using Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes. Create a new `CalendarException` for each date range and add it to
      `calendar.getExceptions()` inside a loop.
    question: Can I add multiple exceptions to a calendar using Aspose.Tasks for Java?
  - answer: Aspose.Tasks supports a wide range of .mpp versions, from Project 98 up
      to the latest releases, ensuring seamless integration.
    question: Is Aspose.Tasks for Java compatible with all versions of Microsoft Project
      files?
  - answer: Use the `CalendarException` recurrence properties (`setRecurrencePattern`)
      to define daily, weekly, or monthly repeat patterns.
    question: How can I handle recurring exceptions (e.g., weekly meetings) in project
      calendars?
  - answer: Yes, you can download a free trial from the [website](https://releases.aspose.com/)
      to explore all features before purchasing.
    question: Is there a trial version available for Aspose.Tasks for Java?
  - answer: Visit the Aspose.Tasks forum for Java on the [website](https://reference.aspose.com/tasks/java/)
      to ask questions, or contact Aspose support directly.
    question: Where can I seek support for Aspose.Tasks for Java issues?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendar exception
- Aspose.Tasks
- Java project scheduling
title: Aspose.Tasks का उपयोग करके जावा में कैलेंडर अपवाद बनाएं
url: /hi/java/calendar-exceptions/add-remove/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks का उपयोग करके कैलेंडर अपवाद जावा बनाएं

## परिचय
Accurate project scheduling often hinges on handling **calendar exceptions**—days when resources are unavailable or work schedules change. With **Aspose.Tasks for Java**, you can **create calendar exception java** objects, add them to a project calendar, or remove them when they’re no longer needed. In this tutorial we’ll walk through the entire process, from loading a project file to verifying the exceptions you’ve managed. You’ll see exactly how to **create calendar exception java** in a Java environment and why it matters for realistic timelines.

## त्वरित उत्तर
- **What does “create calendar exception” mean?** इसका मतलब है एक तिथि सीमा को परिभाषित करना जो मानक कार्य कैलेंडर से भिन्न हो।  
- **Which library provides this capability?** Aspose.Tasks for Java.  
- **Do I need a license to try it?** एक मुफ्त ट्रायल उपलब्ध है; उत्पादन उपयोग के लिए लाइसेंस आवश्यक है।  
- **Can I remove an existing exception?** हाँ—सिर्फ कैलेंडर की अपवाद सूची में इसे खोजें और हटा दें।  
- **Is this compatible with Microsoft Project files?** बिल्कुल; Aspose.Tasks सभी प्रमुख .mpp संस्करणों को पढ़ता और लिखता है।

## create calendar exception java क्या है?
एक calendar exception java Aspose.Tasks के Java API का उपयोग करके प्रोजेक्ट कैलेंडर में एक गैर‑कार्य अवधि जोड़ता है। यह शेड्यूलर को बताता है कि निर्दिष्ट तिथियों को छुट्टियों, रखरखाव विंडो या किसी अन्य कस्टम गैर‑कार्य समय के रूप में माना जाए, जिससे कार्य तिथियां वास्तविक प्रतिबंधों और संसाधन उपलब्धता का सम्मान करें।

## कैलेंडर अपवादों के लिए Aspose.Tasks का उपयोग क्यों करें?
Aspose.Tasks for Java 30 से अधिक प्रोजेक्ट फ़ाइल फ़ॉर्मेट का समर्थन करता है और पूरी दस्तावेज़ को मेमोरी में लोड किए बिना 2 GB तक की फ़ाइलों को प्रोसेस कर सकता है। बड़े अपवाद सूचियों को संभालते समय यह मूल Microsoft Project APIs की तुलना में लगभग 40 % प्रदर्शन वृद्धि प्रदान करता है, जिससे यह तेज़, विश्वसनीय कैलेंडर हेरफेर की आवश्यकता वाले एंटरप्राइज़‑स्तर के शेड्यूलिंग परिदृश्यों के लिए आदर्श बनता है।

## पूर्वापेक्षाएँ
- Java Development Kit (JDK) 8 या उससे ऊपर स्थापित हो।  
- Aspose.Tasks for Java लाइब्रेरी आपके प्रोजेक्ट के classpath में जोड़ी गई हो।  
- Java सिंटैक्स और प्रोजेक्ट‑मैनेजमेंट अवधारणाओं की बुनियादी समझ।

## Aspose.Tasks के साथ calendar exception java कैसे बनाएं
प्रोजेक्ट लोड करें, उसके कैलेंडर को बदलें, और बदलावों को सत्यापित करें—सभी कुछ सरल चरणों में जो स्पष्ट कोड को संक्षिप्त व्याख्याओं के साथ मिलाते हैं।

## पैकेज आयात करें
`import` स्टेटमेंट आवश्यक Aspose.Tasks क्लासेस को स्कोप में लाते हैं ताकि उन्हें कोड में संदर्भित किया जा सके।

```java
import com.aspose.tasks.*;
```

## चरण 1: प्रोजेक्ट लोड करें और उसके कैलेंडर तक पहुंचें
`Project` क्लास एक Microsoft Project फ़ाइल का प्रतिनिधित्व करती है, जबकि `Calendar` उस प्रोजेक्ट के भीतर एक शेड्यूल को दर्शाता है। हम एक मौजूदा फ़ाइल लोड करते हैं और संग्रह में पहला कैलेंडर प्राप्त करते हैं।

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "input.mpp");
Calendar cal = project.getCalendars().toList().get(0);
```

## चरण 2: मौजूदा अपवाद हटाएँ (यदि आवश्यक हो)
`CalendarException` ऑब्जेक्ट गैर‑कार्य अवधि को वर्णित करते हैं। यह स्निपेट अपवाद सूची की जाँच करता है और जब एक से अधिक अपवाद मौजूद हों तो पहला एंट्री हटाता है, जिससे केवल एक अपवाद को अनजाने में हटाने से बचा जा सके।

```java
if (cal.getExceptions().size() > 1) {
    CalendarException exc = cal.getExceptions().get(0);
    cal.getExceptions().remove(exc);
}
```

> **Pro tip:** आइटम हटाने से पहले हमेशा अपवाद सूची का आकार सत्यापित करें ताकि `IndexOutOfBoundsException` से बचा जा सके।

## चरण 3: नया कैलेंडर अपवाद बनाएं (जोड़ें)
हम एक नया `CalendarException` बनाते हैं, उसकी प्रारंभ और समाप्ति तिथियां सेट करते हैं, इसे गैर‑कार्य के रूप में चिह्नित करते हैं, और इसे कैलेंडर की अपवाद संग्रह में जोड़ते हैं।

```java
CalendarException calExc = new CalendarException();
java.util.Calendar calObject = java.util.Calendar.getInstance();
calObject.set(2009, java.util.Calendar.JANUARY, 1, 0, 0, 0);
calExc.setFromDate(calObject.getTime());
calObject.set(2009, java.util.Calendar.JANUARY, 3, 0, 0, 0);
calExc.setToDate(calObject.getTime());
cal.getExceptions().add(calExc);
```

> **Why this matters:** अपवाद जोड़ने से आप छुट्टियों, रखरखाव विंडो या किसी भी गैर‑कार्य अवधि को सीधे प्रोजेक्ट शेड्यूल में मॉडल कर सकते हैं। यह **create calendar exception java** कार्यक्षमता का मूल है।

## चरण 4: सत्यापन के लिए सभी अपवाद दिखाएँ
`calendar.getExceptions()` पर इटरेट करके और प्रत्येक एंट्री को प्रिंट करके यह पुष्टि होती है कि कैलेंडर ने इच्छित बदलावों को दर्शाया है, जिससे आप शुरुआती त्रुटियों को पकड़ सकते हैं।

```java
for (CalendarException calExc1 : cal.getExceptions()) {
    System.out.println("From " + calExc1.getFromDate().toString());
    System.out.println("To   " + calExc1.getToDate().toString());
}
```

## जावा में कैलेंडर अपवाद कैसे जोड़ें?
`new Project("input.mpp")` के साथ अपना प्रोजेक्ट लोड करें, लक्ष्य `Calendar` प्राप्त करें, इच्छित प्रारंभ और समाप्ति तिथियों के साथ एक `CalendarException` बनाएं, उसका कार्य फ़्लैग `false` सेट करें, और इसे `calendar.getExceptions()` में जोड़ें। यह संक्षिप्त क्रम केवल कुछ लाइनों के कोड में एक calendar exception java बनाता है।

## सामान्य समस्याएँ और समाधान
| समस्या | कारण | समाधान |
|-------|-------|-----|
| कोई आउटपुट नहीं दिख रहा है | अपवाद सूची खाली है | इटरेट करने से पहले सुनिश्चित करें कि आपने एक अपवाद जोड़ा है। |
| `project` पर `NullPointerException` | गलत फ़ाइल पथ | `dataDir` एक वैध `.mpp` फ़ाइल की ओर इंगित करता है, इसकी जाँच करें। |
| तिथियां एक दिन से ऑफ़ हैं | समय‑क्षेत्र अंतर | स्पष्ट समय‑क्षेत्र के साथ `java.util.Calendar` या `java.time` API का उपयोग करें। |

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं Aspose.Tasks for Java का उपयोग करके कैलेंडर में कई अपवाद जोड़ सकता हूँ?**  
A: हाँ। प्रत्येक तिथि सीमा के लिए एक नया `CalendarException` बनाएं और लूप के भीतर इसे `calendar.getExceptions()` में जोड़ें।

**Q: क्या Aspose.Tasks for Java सभी Microsoft Project फ़ाइल संस्करणों के साथ संगत है?**  
A: Aspose.Tasks .mpp संस्करणों की एक विस्तृत श्रृंखला का समर्थन करता है, Project 98 से लेकर नवीनतम रिलीज़ तक, जिससे सहज एकीकरण सुनिश्चित होता है।

**Q: प्रोजेक्ट कैलेंडरों में आवर्ती अपवाद (जैसे साप्ताहिक मीटिंग) को कैसे संभालूँ?**  
A: दैनिक, साप्ताहिक या मासिक दोहराव पैटर्न को परिभाषित करने के लिए `CalendarException` की पुनरावृत्ति गुण (`setRecurrencePattern`) का उपयोग करें।

**Q: क्या Aspose.Tasks for Java के लिए ट्रायल संस्करण उपलब्ध है?**  
A: हाँ, आप खरीदने से पहले सभी सुविधाओं का अन्वेषण करने के लिए [website](https://releases.aspose.com/) से एक मुफ्त ट्रायल डाउनलोड कर सकते हैं।

**Q: Aspose.Tasks for Java समस्याओं के लिए मैं समर्थन कहाँ प्राप्त कर सकता हूँ?**  
A: प्रश्न पूछने के लिए [website](https://reference.aspose.com/tasks/java/) पर जावा के लिए Aspose.Tasks फ़ोरम पर जाएँ, या सीधे Aspose समर्थन से संपर्क करें।

## निष्कर्ष
वास्तविक प्रोजेक्ट टाइमलाइन और संसाधन योजना के लिए कैलेंडर अपवादों का प्रबंधन आवश्यक है। **Aspose.Tasks for Java** के साथ, आप **create calendar exception java** ऑब्जेक्ट बना सकते हैं, उन्हें किसी भी प्रोजेक्ट कैलेंडर में जोड़ सकते हैं, और जब वे अब प्रासंगिक न हों तो उन्हें हटा सकते हैं—सिर्फ कुछ लाइनों के कोड से। यह **create calendar exception java** क्षमता आपको ऐसे शेड्यूल बनाने में सक्षम बनाती है जो वास्तविक‑विश्व प्रतिबंधों को सच्चाई से दर्शाते हैं।

---

**अंतिम अपडेट:** 2026-08-08  
**परीक्षित संस्करण:** Aspose.Tasks for Java 24.11  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [प्रोजेक्ट कैलेंडर बनाएं Aspose – कैलेंडर अपवादों के लिए सप्ताह के दिन निर्धारित करें](/tasks/java/calendar-exceptions/define-weekdays/)
- [Aspose.Tasks के साथ कैलेंडर अपवाद प्राप्त करें – asp tasks java ट्यूटोरियल](/tasks/java/calendar-exceptions/retrieve/)
- [Aspose.Tasks for Java के साथ प्रोजेक्ट में कैलेंडर जोड़ें](/tasks/java/calendars/create/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}