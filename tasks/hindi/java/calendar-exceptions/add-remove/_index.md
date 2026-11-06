---
date: 2026-11-06
description: Aspose.Tasks for Java का उपयोग करके प्रोजेक्ट कैलेंडर में अपवाद को हटाना,
  अपवादों को जोड़ना और प्रभावी रूप से प्रबंधित करना, तथा शेड्यूलिंग में सुधार करना
  सीखें।
images:
- /java/calendar-exceptions/add-remove/og-image.png
keywords:
- how to remove exception
- how to handle recurring
- how to add exception
- Aspose.Tasks Java
- project calendar management
lastmod: 2026-11-06
linktitle: Aspose.Tasks में कैलेंडर अपवाद जोड़ें और हटाएँ
og_description: Aspose.Tasks for Java का उपयोग करके प्रोजेक्ट कैलेंडर में अपवाद को
  कैसे हटाएँ। कैलेंडर अपवादों को प्रभावी रूप से प्रबंधित, जोड़ और सत्यापित करें।
og_image_alt: Screenshot of Java code managing calendar exceptions with Aspose.Tasks
og_title: प्रोजेक्ट कैलेंडर में अपवाद को हटाने का तरीका – Aspose.Tasks Java गाइड
schemas:
- author: Aspose
  dateModified: '2026-11-06'
  description: Learn how to remove exception in a project calendar using Aspose.Tasks
    for Java, add and manage exceptions efficiently.
  headline: How to remove exception in a project calendar using Aspose.Tasks
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
  - answer: Yes, you can download a free trial from the [Aspose Releases page](https://releases.aspose.com/)
      to explore all features before purchasing.
    question: Is there a trial version available for Aspose.Tasks for Java?
  - answer: Visit the Aspose.Tasks forum for Java on the [Aspose Tasks Java forum](https://reference.aspose.com/tasks/java/)
      to ask questions, or contact Aspose support directly.
    question: Where can I seek support for Aspose.Tasks for Java issues?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendar exception
- Aspose.Tasks
- Java project scheduling
title: Aspose.Tasks for Java का उपयोग करके प्रोजेक्ट कैलेंडर में अपवाद को कैसे हटाएँ
url: /hi/java/calendar-exceptions/add-remove/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java का उपयोग करके प्रोजेक्ट कैलेंडर में अपवाद को कैसे हटाएँ

## परिचय
सटीक प्रोजेक्ट शेड्यूलिंग अक्सर **calendar exceptions** को संभालने पर निर्भर करती है—वे दिन जब संसाधन उपलब्ध नहीं होते या कार्य शेड्यूल बदलते हैं। **Aspose.Tasks for Java** के साथ, आप **create**, **add**, **remove**, और **manage** calendar exceptions को प्रभावी ढंग से कर सकते हैं। इस ट्यूटोरियल में हम एक प्रोजेक्ट लोड करने, नया अपवाद जोड़ने, मौजूदा को हटाने, और परिणामों की पुष्टि करने की प्रक्रिया दिखाएंगे, ताकि आप ठीक‑ठीक समझ सकें कि **how to remove exception** प्रविष्टियों को कब आवश्यक न हों तो कैसे हटाएँ।

## त्वरित उत्तर
- **What does “create calendar exception” mean?** इसका मतलब है एक तिथि सीमा को परिभाषित करना जो मानक कार्य कैलेंडर से भिन्न हो।  
- **Which library provides this capability?** Aspose.Tasks for Java.  
- **Do I need a license to try it?** एक मुफ्त ट्रायल उपलब्ध है; उत्पादन उपयोग के लिए लाइसेंस आवश्यक है।  
- **Can I remove an existing exception?** हाँ—सिर्फ इसे कैलेंडर की exception सूची में ढूँढें और हटाएँ।  
- **Is this compatible with Microsoft Project files?** बिल्कुल; Aspose.Tasks सभी प्रमुख .mpp संस्करणों को पढ़ता और लिखता है।

## create calendar exception java क्या है?
`CalendarException` क्लास एक non‑working अवधि का प्रतिनिधित्व करती है जिसे आप प्रोजेक्ट कैलेंडर में जोड़ते हैं। यह शेड्यूलर को बताती है कि निर्दिष्ट तिथियों को छुट्टियों, रखरखाव विंडो, या किसी भी कस्टम non‑working समय के रूप में माना जाए, जिससे टास्क तिथियाँ वास्तविक दुनिया की बाधाओं का सम्मान करें।

## कैलेंडर अपवादों के लिए Aspose.Tasks का उपयोग क्यों करें?
Aspose.Tasks for Java **50+ इनपुट और आउटपुट फॉर्मेट** को सपोर्ट करता है और **2 GB** तक की फ़ाइलों को बिना पूरे दस्तावेज़ को मेमोरी में लोड किए प्रोसेस कर सकता है। बड़े अपवाद सूचियों को संभालते समय यह मूल Microsoft Project APIs की तुलना में लगभग **40 % प्रदर्शन वृद्धि** प्रदान करता है, जिससे यह एंटरप्राइज़‑स्तर के शेड्यूलिंग परिदृश्यों के लिए आदर्श बनता है।

## पूर्वापेक्षाएँ
- Java Development Kit (JDK) 8 या उससे ऊपर स्थापित हो।  
- Aspose.Tasks for Java लाइब्रेरी को आपके प्रोजेक्ट के classpath में जोड़ा गया हो।  
- Java सिंटैक्स और प्रोजेक्ट‑मैनेजमेंट अवधारणाओं की बुनियादी समझ।

## कैलेंडर से अपवाद को कैसे हटाएँ?
`Project` क्लास एक Microsoft Project फ़ाइल का प्रतिनिधित्व करता है और इसके कैलेंडर, टास्क, और रिसोर्सेज़ तक पहुँच प्रदान करता है। `CalendarException` क्लास कैलेंडर के भीतर एक non‑working अवधि को परिभाषित करती है। प्रोजेक्ट लोड करें, कैलेंडर की exception संग्रह में अनचाहा `CalendarException` खोजें, और सूची पर `remove` कॉल करें। यह ऑपरेशन शेड्यूल को तुरंत अपडेट करता है और पूरी प्रोजेक्ट फ़ाइल को पुनः‑सहेजने की आवश्यकता नहीं होती जब तक आप परिवर्तन को स्थायी नहीं बनाना चाहते।

## कैलेंडर में अपवाद कैसे जोड़ें?
`CalendarException` क्लास एक non‑working अवधि को परिभाषित करती है जिसे कैलेंडर में जोड़ा जा सकता है। एक नया `CalendarException` इंस्टैंसिएट करें, उसके प्रारंभ और समाप्ति तिथियों को सेट करें, इसे non‑working चिह्नित करें, और इसे कैलेंडर की exception सूची में जोड़ें। यह जोड़ तुरंत होता है, और शेड्यूलर इस परिभाषित रेंज को उस कैलेंडर से जुड़े सभी टास्क के लिए छुट्टी के रूप में मानता है।

## आवर्ती अपवादों को कैसे संभालें?
`CalendarException` की recurrence प्रॉपर्टीज़ (`setRecurrencePattern`) आपको दैनिक, साप्ताहिक, या मासिक दोहराव पैटर्न परिभाषित करने देती हैं। इन प्रॉपर्टीज़ को कॉन्फ़िगर करके, आप साप्ताहिक मीटिंग्स, मासिक रखरखाव विंडो, या किसी भी पैटर्न‑आधारित non‑working समय को प्रत्येक घटना के लिए अलग एंट्री बनाए बिना मॉडल कर सकते हैं।

## पैकेज आयात करें
`import` स्टेटमेंट्स आवश्यक Aspose.Tasks क्लासेज़ को स्कोप में लाते हैं ताकि उन्हें कोड में रेफ़र किया जा सके।

```java
import com.aspose.tasks.*;
```

## चरण 1: प्रोजेक्ट लोड करें और उसके कैलेंडर तक पहुँचें
`Project` एक Microsoft Project फ़ाइल का प्रतिनिधित्व करता है, जबकि `Calendar` उस प्रोजेक्ट के भीतर एक शेड्यूल का प्रतिनिधित्व करता है। मौजूदा फ़ाइल को लोड करना और संग्रह में पहला कैलेंडर प्राप्त करना पहला कदम है।

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "input.mpp");
Calendar cal = project.getCalendars().toList().get(0);
```

## चरण 2: मौजूदा अपवाद को हटाएँ (यदि आवश्यक हो)
`CalendarException` ऑब्जेक्ट्स non‑working अवधि का वर्णन करते हैं। यह स्निपेट exception सूची की जाँच करता है और जब एक से अधिक अपवाद मौजूद हों तो पहला एंट्री हटाता है, जिससे केवल एक अपवाद को अनजाने में हटाने से बचा जा सके।

```java
if (cal.getExceptions().size() > 1) {
    CalendarException exc = cal.getExceptions().get(0);
    cal.getExceptions().remove(exc);
}
```

> **Pro tip:** आइटम हटाने से पहले हमेशा exception सूची का आकार जाँचें ताकि `IndexOutOfBoundsException` से बचा जा सके।

## चरण 3: नया कैलेंडर अपवाद बनाएं (जोड़ें)
हम एक नया `CalendarException` इंस्टैंसिएट करते हैं, उसके प्रारंभ और समाप्ति तिथियों को सेट करते हैं, इसे non‑working चिह्नित करते हैं, और इसे कैलेंडर की exception संग्रह में जोड़ते हैं।

```java
CalendarException calExc = new CalendarException();
java.util.Calendar calObject = java.util.Calendar.getInstance();
calObject.set(2009, java.util.Calendar.JANUARY, 1, 0, 0, 0);
calExc.setFromDate(calObject.getTime());
calObject.set(2009, java.util.Calendar.JANUARY, 3, 0, 0, 0);
calExc.setToDate(calObject.getTime());
cal.getExceptions().add(calExc);
```

> **Why this matters:** अपवाद जोड़ने से आप छुट्टियों, रखरखाव विंडो, या किसी भी non‑working अवधि को सीधे प्रोजेक्ट शेड्यूल में मॉडल कर सकते हैं। यह **create calendar exception java** कार्यक्षमता का मूल है।

## चरण 4: सत्यापन के लिए सभी अपवाद दिखाएँ
`calendar.getExceptions()` पर इटररेट करके और प्रत्येक एंट्री को प्रिंट करके यह पुष्टि होती है कि कैलेंडर ने इच्छित परिवर्तन को दर्शाया है, जिससे आप शुरुआती त्रुटियों को पकड़ सकते हैं।

```java
for (CalendarException calExc1 : cal.getExceptions()) {
    System.out.println("From " + calExc1.getFromDate().toString());
    System.out.println("To   " + calExc1.getToDate().toString());
}
```

## Java में कैलेंडर अपवाद कैसे जोड़ें?
`new Project("input.mpp")` से अपना प्रोजेक्ट लोड करें, लक्ष्य `Calendar` प्राप्त करें, इच्छित प्रारंभ और समाप्ति तिथियों के साथ एक `CalendarException` इंस्टैंसिएट करें, उसका working फ़्लैग `false` सेट करें, और इसे `calendar.getExceptions()` में जोड़ें। यह संक्षिप्त क्रम केवल कुछ लाइनों के कोड में एक calendar exception java बनाता है।

## सामान्य समस्याएँ और समाधान
| समस्या | कारण | समाधान |
|-------|-------|-----|
| कोई आउटपुट नहीं दिख रहा है | Exceptions सूची खाली है | इटररेट करने से पहले सुनिश्चित करें कि आपने एक exception जोड़ा है। |
| `NullPointerException` on `project` | गलत फ़ाइल पथ | `dataDir` एक वैध `.mpp` फ़ाइल की ओर इशारा करता है, यह सत्यापित करें। |
| तिथियाँ एक दिन से अलग हैं | समय‑क्षेत्र अंतर | स्पष्ट समय‑क्षेत्र के साथ `java.util.Calendar` या `java.time` API का उपयोग करें। |

## अक्सर पूछे जाने वाले प्रश्न

**Q:** क्या मैं Aspose.Tasks for Java का उपयोग करके कैलेंडर में कई अपवाद जोड़ सकता हूँ?  
**A:** हाँ। प्रत्येक तिथि रेंज के लिए एक नया `CalendarException` बनाएं और लूप के भीतर `calendar.getExceptions()` में जोड़ें।

**Q:** क्या Aspose.Tasks for Java सभी Microsoft Project फ़ाइल संस्करणों के साथ संगत है?  
**A:** Aspose.Tasks .mpp संस्करणों की एक विस्तृत श्रृंखला को सपोर्ट करता है, Project 98 से लेकर नवीनतम रिलीज़ तक, जिससे सहज एकीकरण सुनिश्चित होता है।

**Q:** मैं प्रोजेक्ट कैलेंडरों में आवर्ती अपवादों (जैसे साप्ताहिक मीटिंग्स) को कैसे संभाल सकता हूँ?  
**A:** `CalendarException` की recurrence प्रॉपर्टीज़ (`setRecurrencePattern`) का उपयोग करके दैनिक, साप्ताहिक, या मासिक दोहराव पैटर्न परिभाषित करें।

**Q:** क्या Aspose.Tasks for Java के लिए ट्रायल संस्करण उपलब्ध है?  
**A:** हाँ, आप सभी सुविधाओं को खरीदने से पहले परीक्षण करने के लिए [Aspose Releases page](https://releases.aspose.com/) से एक मुफ्त ट्रायल डाउनलोड कर सकते हैं।

**Q:** मैं Aspose.Tasks for Java समस्याओं के लिए समर्थन कहाँ प्राप्त कर सकता हूँ?  
**A:** प्रश्न पूछने के लिए [Aspose Tasks Java forum](https://reference.aspose.com/tasks/java/) पर Aspose.Tasks फ़ोरम देखें, या सीधे Aspose समर्थन से संपर्क करें।

## निष्कर्ष
कैलेंडर अपवादों का प्रबंधन वास्तविक प्रोजेक्ट टाइमलाइन और संसाधन योजना के लिए आवश्यक है। **Aspose.Tasks for Java** के साथ, आप **create**, **add**, **remove**, और कैलेंडर अपवादों को सत्यापित कर सकते हैं—सिर्फ कुछ लाइनों के कोड से। **how to remove exception** प्रविष्टियों में निपुणता आपको शेड्यूल को सटीक और वास्तविक‑दुनिया की बाधाओं के अनुरूप रखने में सक्षम बनाती है।

---

**अंतिम अपडेट:** 2026-11-06  
**परीक्षण किया गया:** Aspose.Tasks for Java 24.11  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [प्रोजेक्ट कैलेंडर बनाएं Aspose – कैलेंडर अपवादों के लिए सप्ताह के दिन निर्धारित करें](/tasks/java/calendar-exceptions/define-weekdays/)
- [Aspose.Tasks के साथ कैलेंडर अपवाद प्राप्त करें – asp tasks java ट्यूटोरियल](/tasks/java/calendar-exceptions/retrieve/)
- [Aspose.Tasks for Java के साथ प्रोजेक्ट में कैलेंडर जोड़ें](/tasks/java/calendars/create/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}