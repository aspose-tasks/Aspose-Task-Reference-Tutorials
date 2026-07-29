---
date: 2026-07-29
description: Aspose.Tasks for Java के साथ project calendar बनाकर गैर-कार्य दिवस निर्धारित
  करने का तरीका सीखें, weekday exceptions निर्धारित करें और holiday schedules प्रबंधित
  करें।
keywords:
- schedule non working days
- how to define weekdays
- set non working days
- java calendar exceptions
lastmod: 2026-07-29
linktitle: गैर-कार्य दिवस निर्धारित करें – Create Project Calendar Aspose
og_description: Aspose.Tasks for Java का उपयोग करके गैर-कार्य दिवस निर्धारित करें।
  weekdays को परिभाषित करना, calendar exceptions जोड़ना, और holiday schedules को प्रभावी
  ढंग से प्रबंधित करना सीखें।
og_image_alt: 'Developer guide: schedule non working days with Aspose.Tasks Java'
og_title: गैर-कार्य दिवस निर्धारित करें – Create Project Calendar Aspose
schemas:
- author: Aspose
  dateModified: '2026-07-29'
  description: Learn how to schedule non working days by creating a project calendar
    with Aspose.Tasks for Java, defining weekday exceptions and managing holiday schedules.
  headline: Schedule Non Working Days – Create Project Calendar Aspose
  type: TechArticle
- description: Learn how to schedule non working days by creating a project calendar
    with Aspose.Tasks for Java, defining weekday exceptions and managing holiday schedules.
  name: Schedule Non Working Days – Create Project Calendar Aspose
  steps:
  - name: Import Required Packages
    text: We need the core Aspose.Tasks classes and Java’s `GregorianCalendar` for
      date handling.
  - name: Define the Data Directory
    text: Specify where the generated project file will be saved.
  - name: Create a Project Instance
    text: '`Project` is the main object that holds all project data, including tasks,
      resources, and calendars.'
  - name: Define a Calendar
    text: '`Calendar` represents a schedule of working and non‑working times within
      a project.'
  - name: Define Weekdays Exception
    text: '`CalendarException` represents a period that is marked as non‑working in
      a calendar.'
  - name: Save the Project
    text: Persist the project, including the custom calendar and its exception, to
      an XML file.
  type: HowTo
- questions:
  - answer: Yes. Add additional `CalendarException` objects to `cal.getExceptions()`
      for each distinct period or rule.
    question: Can I define multiple exceptions for different weekdays within the same
      calendar?
  - answer: Absolutely. The library works with IntelliJ IDEA, Eclipse, NetBeans, and
      any IDE that supports standard Java projects.
    question: Is Aspose.Tasks for Java compatible with different Java IDEs?
  - answer: Yes. Use `CalendarExceptionType.Weekly`, `Monthly`, or `Yearly` to suit
      your scheduling needs.
    question: Can I customize exception types other than daily exceptions?
  - answer: Build the exception objects programmatically—e.g., read holiday dates
      from a database or configuration file and create `CalendarException` instances
      in a loop.
    question: How can I handle exceptions dynamically based on project requirements?
  - answer: Yes, you can download a free trial from the [Aspose.Tasks Java download
      page](https://releases.aspose.com/tasks/java/).
    question: Is there a trial version available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- schedule non working days
- Aspose.Tasks
- Java calendar exceptions
- project calendar
- non-working days
title: गैर-कार्य दिवस निर्धारित करें – Create Project Calendar Aspose
url: /hi/java/calendar-exceptions/define-weekdays/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# गैर-कार्य दिवस निर्धारित करें – Aspose के साथ प्रोजेक्ट कैलेंडर बनाएं

### परिचय
जब आपको किसी प्रोजेक्ट के लिए **गैर-कार्य दिवस निर्धारित** करने की आवश्यकता होती है, तो आपको छुट्टियों, विशेष शिफ्टों या अस्थायी बंदों को सीधे प्रोजेक्ट योजना में मॉडल करने में सक्षम होना चाहिए। Aspose.Tasks for Java कैलेंडर परिभाषाओं पर पूर्ण नियंत्रण प्रदान करता है, जिससे आप वास्तविक‑विश्व शेड्यूल को प्रतिबिंबित करने वाले अपवाद जोड़ सकते हैं। इस ट्यूटोरियल में हम कैलेंडर अपवादों के लिए weekdays को परिभाषित करने के सटीक चरणों से गुजरेंगे, ताकि आपके प्रोजेक्ट टाइमलाइन सटीक और विश्वसनीय रहें। अंत तक आप देखेंगे कि यह किसी भी एंटरप्राइज़ प्रोजेक्ट के लिए व्यापक **गैर-कार्य दिवस शेड्यूल** रणनीति में कैसे फिट बैठता है।

## त्वरित उत्तर
- **“गैर-कार्य दिवस निर्धारित” क्या मतलब है?**  
  इसका अर्थ है Aspose.Tasks का उपयोग करके एक कैलेंडर बनाना जो विशिष्ट तिथियों को गैर‑कार्य के रूप में चिह्नित करता है, जिससे कार्य तिथियों पर स्वचालित रूप से प्रभाव पड़ता है।  
- **क्या मुझे सैंपल चलाने के लिए लाइसेंस चाहिए?**  
  एक मुफ्त ट्रायल विकास के लिए काम करता है; उत्पादन के लिए एक व्यावसायिक लाइसेंस आवश्यक है।  
- **कौन से IDE समर्थित हैं?**  
  IntelliJ IDEA, Eclipse, NetBeans, या कोई भी IDE जो Java 8+ का समर्थन करता है।  
- **क्या मैं एक ही कैलेंडर में कई अपवाद जोड़ सकता हूँ?**  
  हाँ – आप आवश्यकता अनुसार जितने भी `CalendarException` ऑब्जेक्ट्स चाहें, जोड़ सकते हैं।  
- **मैं प्रोजेक्ट को किन फ़ाइल फ़ॉर्मेट में सहेज सकता हूँ?**  
  XML, MPP, और Aspose.Tasks द्वारा समर्थित कई अन्य फ़ॉर्मेट।  

## Aspose.Tasks में प्रोजेक्ट कैलेंडर क्या है?
**प्रोजेक्ट कैलेंडर** Aspose.Tasks का शीर्ष‑स्तरीय ऑब्जेक्ट है जो प्रोजेक्ट के कार्य दिवस और घंटे निर्धारित करता है। यह सीधे कार्य की शुरूआत/समाप्ति तिथियों, संसाधन आवंटन, और समग्र शेड्यूल गणनाओं को प्रभावित करता है। कैलेंडर को कस्टमाइज़ करके, आप सुनिश्चित करते हैं कि शेड्यूल वास्तविक‑विश्व प्रतिबंधों जैसे कंपनी की छुट्टियों या सप्ताहांत कार्य नीतियों का सम्मान करे।

## कैलेंडर अपवादों के लिए weekdays को क्यों परिभाषित करें?
weekday अपवादों को परिभाषित करने से यह सुनिश्चित होता है कि प्रोजेक्ट इंजन उन दिनों को गैर‑कार्य के रूप में मानता है, जिससे कार्यों को स्वचालित रूप से उन पर शेड्यूल होने से रोका जाता है और टाइमलाइन को वास्तविक‑विश्व प्रतिबंधों जैसे छुट्टियों, रखरखाव विंडो, या संगठन में विशेष शिफ्ट पैटर्न के साथ संरेखित रखा जाता है।

- **सटीक टाइमलाइन:** कार्य छुट्टियों या ब्लैकआउट अवधि में नहीं रखे जाएंगे।  
- **संसाधन योजना:** संसाधनों को केवल वैध कार्य दिवसों पर ही आवंटित किया जाता है, जिससे ओवरऑलोकेशन रोका जाता है।  
- **अनुपालन:** शेड्यूल स्वचालित रूप से संगठनात्मक नीतियों या कानूनी छुट्टी कैलेंडरों का पालन करते हैं।  

## कैलेंडर अपवादों के साथ गैर‑कार्य दिवस शेड्यूल
जब आप एक **गैर‑कार्य दिवस शेड्यूल** बनाए रखते हैं, तो आमतौर पर आपके पास छुट्टियों, रखरखाव विंडो या अन्य ब्लैकआउट अवधि की एक मास्टर सूची होती है। उन तिथियों को `CalendarException` ऑब्जेक्ट्स के रूप में जोड़ने से यह सुनिश्चित होता है कि हर गणना—चाहे वह क्रिटिकल‑पाथ विश्लेषण हो या संसाधन लेवलिंग—स्वचालित रूप से उन प्रतिबंधों का सम्मान करे। यह तरीका मैन्युअल तिथि समायोजन को समाप्त करता है और शेड्यूल ड्रिफ्ट के जोखिम को कम करता है।

## पूर्वापेक्षाएँ
1. **Java Development Kit (JDK)** – संस्करण 8 या बाद का।  
2. **Aspose.Tasks for Java** – आधिकारिक [Aspose.Tasks Java download page](https://releases.aspose.com/tasks/java/) से डाउनलोड करें।  
3. **एक IDE** – IntelliJ IDEA, Eclipse, NetBeans, या कोई भी Java‑compatible एडिटर।  

## कैलेंडर अपवादों का उपयोग करके गैर‑कार्य दिवस कैसे निर्धारित करें
अपना प्रोजेक्ट लोड करें, एक कस्टम कैलेंडर बनाएं, और `CalendarException` ऑब्जेक्ट्स जोड़ें जो इच्छित weekdays को गैर‑कार्य के रूप में चिह्नित करते हैं। यह पूरी प्रक्रिया कुछ सरल चरणों में पूरी की जा सकती है, और परिणामी कैलेंडर स्वचालित रूप से सभी कार्य शेड्यूलिंग लॉजिक को प्रभावित करेगा।

### चरण‑दर‑चरण मार्गदर्शिका

### चरण 1: आवश्यक पैकेज आयात करें
हमें कोर Aspose.Tasks क्लासेस और जावा के `GregorianCalendar` की आवश्यकता है तिथि संभालने के लिए।

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

### चरण 2: डेटा डायरेक्टरी निर्धारित करें
निर्दिष्ट करें कि उत्पन्न प्रोजेक्ट फ़ाइल कहाँ सहेजी जाएगी।

```java
String dataDir = "Your Data Directory";
```

### चरण 3: प्रोजेक्ट इंस्टेंस बनाएं
`Project` मुख्य ऑब्जेक्ट है जो सभी प्रोजेक्ट डेटा रखता है, जिसमें कार्य, संसाधन, और कैलेंडर शामिल हैं।

```java
Project project = new Project();
```

### चरण 4: कैलेंडर परिभाषित करें
`Calendar` प्रोजेक्ट के भीतर कार्य और गैर‑कार्य समय की शेड्यूल को दर्शाता है।

```java
Calendar cal = project.getCalendars().add("Calendar1");
```

### चरण 5: weekdays अपवाद परिभाषित करें
`CalendarException` एक अवधि को दर्शाता है जिसे कैलेंडर में गैर‑कार्य के रूप में चिह्नित किया गया है।

```java
CalendarException except = new CalendarException();
except.setEnteredByOccurrences(false);
except.setFromDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 24, 0, 0, 0).getTime());
except.setToDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 31, 23, 59, 0).getTime());
except.setType(CalendarExceptionType.Daily);
except.setDayWorking(false);
cal.getExceptions().add(except);
```

### चरण 6: प्रोजेक्ट सहेजें
कस्टम कैलेंडर और उसके अपवाद सहित प्रोजेक्ट को XML फ़ाइल में सहेजें।

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## सामान्य समस्याएँ और समाधान
| समस्या | समाधान |
|-------|----------|
| **अपवाद तिथियां लागू नहीं हुईं** | `setEnteredByOccurrences(false)` और सही `FromDate/ToDate` मान सुनिश्चित करें। |
| **सहेजी गई फ़ाइल खाली है** | `dataDir` एक लिखने योग्य फ़ोल्डर की ओर इशारा करता है और फ़ाइलनाम `.xml` पर समाप्त होता है, यह सत्यापित करें। |
| **कैलेंडर कार्य शेड्यूलिंग में प्रतिबिंबित नहीं है** | `task.setCalendar(cal)` या `resource.setCalendar(cal)` का उपयोग करके कैलेंडर को कार्यों या संसाधनों को असाइन करें। |

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं एक ही कैलेंडर में विभिन्न weekdays के लिए कई अपवाद परिभाषित कर सकता हूँ?**  
A: हाँ। प्रत्येक अलग अवधि या नियम के लिए `cal.getExceptions()` में अतिरिक्त `CalendarException` ऑब्जेक्ट्स जोड़ें।

**Q: क्या Aspose.Tasks for Java विभिन्न Java IDEs के साथ संगत है?**  
A: बिल्कुल। लाइब्रेरी IntelliJ IDEA, Eclipse, NetBeans, और किसी भी IDE के साथ काम करती है जो मानक Java प्रोजेक्ट्स को समर्थन देती है।

**Q: क्या मैं दैनिक अपवादों के अलावा अन्य अपवाद प्रकार कस्टमाइज़ कर सकता हूँ?**  
A: हाँ। अपनी शेड्यूलिंग आवश्यकताओं के अनुसार `CalendarExceptionType.Weekly`, `Monthly`, या `Yearly` का उपयोग करें।

**Q: मैं प्रोजेक्ट आवश्यकताओं के आधार पर अपवादों को गतिशील रूप से कैसे संभाल सकता हूँ?**  
A: अपवाद ऑब्जेक्ट्स को प्रोग्रामेटिकली बनाएं—उदाहरण के लिए, डेटाबेस या कॉन्फ़िगरेशन फ़ाइल से छुट्टी तिथियां पढ़ें और लूप में `CalendarException` इंस्टेंस बनाएं।

**Q: क्या Aspose.Tasks for Java के लिए कोई ट्रायल संस्करण उपलब्ध है?**  
A: हाँ, आप मुफ्त ट्रायल को [Aspose.Tasks Java download page](https://releases.aspose.com/tasks/java/) से डाउनलोड कर सकते हैं।

## निष्कर्ष
इन चरणों का पालन करके आप अब जानते हैं कि कैसे **गैर-कार्य दिवस निर्धारित** किए जाएँ, एक प्रोजेक्ट कैलेंडर बनाकर और weekdays अपवादों को परिभाषित करके जो छुट्टियों या विशेष गैर‑कार्य अवधि को सटीक रूप से दर्शाते हैं। उचित कैलेंडर कॉन्फ़िगरेशन वास्तविक शेड्यूल, संसाधन आवंटन, और समग्र प्रोजेक्ट सफलता के लिए आवश्यक है। कस्टम कैलेंडर को कार्यों या संसाधनों से जोड़कर और अन्य अपवाद प्रकारों के साथ प्रयोग करके किसी भी प्रोजेक्ट के लिए एक व्यापक **गैर‑कार्य दिवस शेड्यूल** बनाएं।

---

**अंतिम अपडेट:** 2026-07-29  
**परीक्षण किया गया:** Aspose.Tasks for Java 24.11  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [Aspose.Tasks for Java के साथ प्रोजेक्ट में कैलेंडर जोड़ें](/tasks/java/calendars/create/)
- [Aspose for Java में कैलेंडर अपवाद बनाएं](/tasks/java/calendar-exceptions/add-remove/)
- [Aspose.Tasks के साथ MS Project में कैलेंडर सेट करना और weekdays परिभाषित करना](/tasks/java/calendars/define-weekdays/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}