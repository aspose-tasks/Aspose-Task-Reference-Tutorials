---
date: 2026-08-08
description: Aspose.Tasks for Java का उपयोग करके MS Project कैलेंडर सेट करना, दैनिक
  कार्य घंटे निर्धारित करना, और सप्ताहांत के कार्य दिवस जोड़ना सीखें। कुछ ही कोड लाइनों
  में प्रोजेक्ट को XML के रूप में सहेजें।
keywords:
- set calendar ms project
- set daily working hours
- add weekend working days
- java create msproject file
- aspose.tasks calendar
lastmod: 2026-08-08
linktitle: MS Project कैलेंडर कैसे सेट करें और कार्यदिवस निर्धारित करें
og_description: Aspose.Tasks for Java का उपयोग करके MS Project कैलेंडर सेट करें, कार्यदिवस
  निर्धारित करें, और सप्ताहांत के कार्य दिवस जोड़ें। इस चरण‑दर‑चरण ट्यूटोरियल का पालन
  करें और XML के रूप में सहेजें।
og_image_alt: Screenshot of Java code configuring MS Project calendar with Aspose.Tasks
og_title: Aspose.Tasks के साथ MS Project कैलेंडर सेट करें – Java गाइड
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to set calendar ms project, set daily working hours, and
    add weekend working days using Aspose.Tasks for Java. Save the project as XML
    in just a few lines of code.
  headline: How to set calendar ms project and define weekdays
  type: TechArticle
- description: Learn how to set calendar ms project, set daily working hours, and
    add weekend working days using Aspose.Tasks for Java. Save the project as XML
    in just a few lines of code.
  name: How to set calendar ms project and define weekdays
  steps:
  - name: create a project instance
    text: Instantiate a `Project` object, which represents the MS Project file you
      will manipulate.
  - name: define a new calendar
    text: '`Calendar` represents a set of working times, exceptions, and holidays
      for a project.'
  - name: add standard working days (Monday‑Thursday)
    text: '`WeekDay` defines the working time for a specific day of the week.'
  - name: add weekend working days
    text: If your project runs on weekends, add Saturday and Sunday as regular working
      days. This demonstrates **add weekend working days**.
  - name: set a custom short working day (Friday)
    text: Configure Friday with a morning shift (9 am‑12 pm) and an afternoon shift
      (1 pm‑4 pm) to illustrate **set daily working hours** and a custom short workday.
  - name: save the project as XML
    text: '`SaveFileFormat` enumerates the supported file formats when saving a project,
      such as XML or MPP.'
  type: HowTo
- questions:
  - answer: Yes. Set the `DayWorking` property to `false` for any `WeekDay` you want
      to treat as a non‑working day.
    question: Can I define custom non‑working days using Aspose.Tasks for Java?
  - answer: Create `CalendarException` objects, specify the exception dates, and add
      them to `cal.getExceptions()`.
    question: How can I add holidays or company‑wide exceptions?
  - answer: Absolutely. Aspose.Tasks supports MPP, MPT, and XML formats across multiple
      Project versions.
    question: Is the library compatible with older MS Project versions?
  - answer: Load the project with `new Project("existing.mpp")`, retrieve the desired
      calendar, make changes, and save.
    question: Can I modify an existing calendar in an imported project?
  - answer: Yes, you can create and edit recurring tasks using the `RecurringTask`
      class.
    question: Does Aspose.Tasks handle recurring tasks as well?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- set calendar ms project
- aspose.tasks
- java project management
title: MS Project कैलेंडर कैसे सेट करें और कार्यदिवस निर्धारित करें
url: /hi/java/calendars/define-weekdays/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# कैसे सेट करें कैलेंडर एमएस प्रोजेक्ट और परिभाषित करें कार्यदिवस

इस ट्यूटोरियल में आप **कैसे सेट करें कैलेंडर एमएस प्रोजेक्ट** प्रोग्रामेटिकली सीखेंगे, कार्यदिवस परिभाषित करेंगे, और Aspose.Tasks लाइब्रेरी फॉर जावा का उपयोग करके कस्टम कार्य दिवस कॉन्फ़िगर करेंगे। चाहे आप एक शेड्यूलिंग इंजन बना रहे हों, ERP सिस्टम्स के साथ इंटीग्रेट कर रहे हों, या बस माइक्रोसॉफ्ट प्रोजेक्ट खोले बिना प्रोजेक्ट प्लान जेनरेट करना चाहते हों, नीचे दिए गए चरण आपको दिखाएंगे कि कैसे एक कैलेंडर बनाएं, दैनिक कार्य घंटे सेट करें, और कुछ कोड लाइनों में सप्ताहांत के कार्य दिवस जोड़ें।

## त्वरित उत्तर
- **कौन सी लाइब्रेरी आवश्यक है?** Aspose.Tasks for Java.  
- **क्या मैं सप्ताहांत के कार्य दिवस जोड़ सकता हूँ?** हाँ – बस शनिवार और रविवार को कार्य दिवस के रूप में चिह्नित करें।  
- **मैं प्रोजेक्ट को कैसे सहेजूँ?** `prj.save(..., SaveFileFormat.Xml)` कॉल करें।  
- **क्या लाइसेंस आवश्यक है?** मूल्यांकन के लिए एक मुफ्त ट्रायल काम करता है; उत्पादन उपयोग के लिए लाइसेंस आवश्यक है।  
- **कौन सा जावा संस्करण समर्थित है?** Java 8 या उससे ऊपर।

## सेट कैलेंडर एमएस प्रोजेक्ट क्या है?
MS Project में कैलेंडर सेट करने से यह निर्धारित होता है कि कौन से दिन कार्य दिवस माने जाएंगे, प्रत्येक दिन कितने कार्य घंटे होंगे, और छुट्टियों या कंपनी‑व्यापी शटडाउन जैसी विशेष अपवाद क्या हैं। यह जानकारी टास्क शेड्यूलिंग, रिसोर्स एलोकेशन, और समग्र प्रोजेक्ट टाइमलाइन को चलाती है, जिससे गणनाएँ संगठन के वास्तविक कार्य पैटर्न का सम्मान करती हैं।

## कैलेंडर हेरफेर के लिए Aspose.Tasks क्यों उपयोग करें?
Aspose.Tasks आपको Microsoft Project UI लॉन्च किए बिना कैलेंडर पर प्रोग्रामेटिक नियंत्रण देता है। यह किसी भी ऑपरेटिंग सिस्टम पर चलता है जो जावा को सपोर्ट करता है, 50 से अधिक इनपुट और आउटपुट फ़ॉर्मेट्स को सपोर्ट करता है, और पूरी फ़ाइल को मेमोरी में लोड किए बिना कई‑सौ पेज के प्रोजेक्ट को प्रोसेस कर सकता है, जिससे यह सर्वर‑साइड ऑटोमेशन के लिए आदर्श बनता है।

## पूर्वापेक्षाएँ
- **Java Development Kit (JDK) 8+** – [Oracle वेबसाइट](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) से डाउनलोड करें।  
- **Aspose.Tasks for Java** – नवीनतम JAR [Aspose.Tasks डाउनलोड पेज](https://releases.aspose.com/tasks/java/) से प्राप्त करें।  
- एक IDE या बिल्ड टूल (Maven/Gradle) ताकि Aspose.Tasks JAR को आपके classpath में जोड़ सकें।

## पैकेज आयात करें
प्रोजेक्ट्स, कैलेंडर, और कार्य‑समय ऑब्जेक्ट्स तक पहुँच प्रदान करने वाली क्लासेज़ को आयात करें।

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

## चरण‑दर‑चरण मार्गदर्शिका

### चरण 1: प्रोजेक्ट इंस्टेंस बनाएं
एक `Project` ऑब्जेक्ट इंस्टैंशिएट करें, जो उस MS Project फ़ाइल का प्रतिनिधित्व करता है जिसे आप बदलेंगे।

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```

### चरण 2: नया कैलेंडर परिभाषित करें
`Calendar` एक प्रोजेक्ट के लिए कार्य समय, अपवाद, और छुट्टियों का सेट दर्शाता है।

```java
Calendar cal = prj.getCalendars().add("Calendar1");
```

### चरण 3: मानक कार्य दिवस जोड़ें (सोमवार‑गुरुवार)
`WeekDay` सप्ताह के विशिष्ट दिन के लिए कार्य समय को परिभाषित करता है।

```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```

### चरण 4: सप्ताहांत के कार्य दिवस जोड़ें
यदि आपका प्रोजेक्ट सप्ताहांत में चलता है, तो शनिवार और रविवार को नियमित कार्य दिवस के रूप में जोड़ें। यह **सप्ताहांत के कार्य दिवस जोड़ें** को दर्शाता है।

```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```

### चरण 5: कस्टम छोटा कार्य दिवस सेट करें (शुक्रवार)
शुक्रवार को सुबह की शिफ्ट (9 am‑12 pm) और दोपहर की शिफ्ट (1 pm‑4 pm) के साथ कॉन्फ़िगर करें ताकि **दैनिक कार्य घंटे सेट करें** और एक कस्टम छोटा कार्य दिवस दिखाया जा सके।

```java
WeekDay myWeekDay = new WeekDay(DayType.Friday);
WorkingTime wt1 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 9, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 12, 0, 0).getTime()
);
WorkingTime wt2 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 13, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 16, 0, 0).getTime()
);
myWeekDay.getWorkingTimes().add(wt1);
myWeekDay.getWorkingTimes().add(wt2);
myWeekDay.setDayWorking(true);
cal.getWeekDays().add(myWeekDay);
```

### चरण 6: प्रोजेक्ट को XML के रूप में सहेजें
`SaveFileFormat` प्रोजेक्ट को सहेजते समय समर्थित फ़ाइल फ़ॉर्मेट्स को सूचीबद्ध करता है, जैसे XML या MPP।

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## सामान्य समस्याएँ और समाधान
| समस्या | समाधान |
|-------|----------|
| **कार्य समय लागू नहीं हुए** | सुनिश्चित करें कि प्रत्येक कस्टम `WeekDay` पर `setDayWorking(true)` कॉल किया गया है। |
| **सहेजते समय फ़ाइल नहीं मिली** | जाँचें कि `dataDir` मौजूद फ़ोल्डर की ओर इशारा कर रहा है और एप्लिकेशन के पास लिखने की अनुमति है। |
| **कार्य में कैलेंडर प्रतिबिंबित नहीं हो रहा है** | नए बनाए गए कैलेंडर को संसाधनों या कार्यों को `task.setCalendar(cal)` के माध्यम से असाइन करें। |

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं Aspose.Tasks for Java का उपयोग करके कस्टम गैर‑कार्य दिवस परिभाषित कर सकता हूँ?**  
A: हाँ। किसी भी `WeekDay` के लिए `DayWorking` प्रॉपर्टी को `false` सेट करें जिसे आप गैर‑कार्य दिवस मानना चाहते हैं।

**Q: मैं छुट्टियों या कंपनी‑व्यापी अपवाद कैसे जोड़ सकता हूँ?**  
A: `CalendarException` ऑब्जेक्ट बनाएं, अपवाद तिथियों को निर्दिष्ट करें, और उन्हें `cal.getExceptions()` में जोड़ें।

**Q: क्या लाइब्रेरी पुराने MS Project संस्करणों के साथ संगत है?**  
A: बिल्कुल। Aspose.Tasks कई प्रोजेक्ट संस्करणों में MPP, MPT, और XML फ़ॉर्मेट्स को सपोर्ट करता है।

**Q: क्या मैं आयातित प्रोजेक्ट में मौजूदा कैलेंडर को संशोधित कर सकता हूँ?**  
A: `new Project("existing.mpp")` के साथ प्रोजेक्ट लोड करें, इच्छित कैलेंडर प्राप्त करें, परिवर्तन करें, और सहेजें।

**Q: क्या Aspose.Tasks आवर्ती कार्यों को भी संभालता है?**  
A: हाँ, आप `RecurringTask` क्लास का उपयोग करके आवर्ती कार्य बना और संपादित कर सकते हैं।

## निष्कर्ष
अब आप **कैसे सेट करें कैलेंडर एमएस प्रोजेक्ट**, कार्यदिवस परिभाषित करना, सप्ताहांत के कार्य दिवस जोड़ना, और एक छोटा शुक्रवार शेड्यूल कॉन्फ़िगर करना जानते हैं—सब Aspose.Tasks for Java के साथ। परिणाम को XML के रूप में सहेजें और कैलेंडर लॉजिक को किसी भी जावा‑आधारित प्रोजेक्ट‑मैनेजमेंट समाधान में इंटीग्रेट करें।

---

**अंतिम अपडेट:** 2026-08-08  
**परीक्षण किया गया:** Aspose.Tasks for Java 24.11  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [Aspose.Tasks for Java के साथ प्रोजेक्ट में कैलेंडर जोड़ें](/tasks/java/calendars/create/)
- [Aspose.Tasks के साथ कार्य दिवस और कार्य घंटे निर्धारित करें](/tasks/java/calendars/working-hours/)
- [Aspose.Tasks के साथ कैलेंडर में छुट्टियां जोड़ें और MPP के रूप में सहेजें](/tasks/java/calendars/update-to-mpp/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}