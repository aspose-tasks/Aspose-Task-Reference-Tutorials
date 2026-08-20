---
date: 2026-08-13
description: Aspose.Tasks for Java का उपयोग करके MS Project कैलेंडर से workweeks पढ़ना
  सीखें। कोड उदाहरण और troubleshooting tips के साथ step‑by‑step guide का पालन करें।
keywords:
- how to read workweeks
- Aspose.Tasks Java
- MS Project calendar
lastmod: 2026-08-13
linktitle: Aspose.Tasks के साथ कैलेंडर से Work Weeks पढ़ें
og_description: Aspose.Tasks for Java का उपयोग करके MS Project कैलेंडर से workweeks
  पढ़ने का तरीका। setup steps, code snippets, और troubleshooting tips के साथ concise
  tutorial का पालन करें।
og_image_alt: 'Tutorial: read workweeks from MS Project calendar using Aspose.Tasks
  Java API'
og_title: Aspose.Tasks के साथ MS कैलेंडर से workweeks पढ़ने का तरीका
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to read workweeks from an MS Project calendar using Aspose.Tasks
    for Java. Follow the step‑by‑step guide with code examples and troubleshooting
    tips.
  headline: How to read workweeks from MS calendar with Aspose.Tasks
  type: TechArticle
- description: Learn how to read workweeks from an MS Project calendar using Aspose.Tasks
    for Java. Follow the step‑by‑step guide with code examples and troubleshooting
    tips.
  name: How to read workweeks from MS calendar with Aspose.Tasks
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or later installed.'
    text: '**Java Development Kit (JDK)** – version 8 or later installed.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).'
  - name: A **sample Project file** (`ReadWorkWeeksInformation.mpp`) placed in a known
      folder on your machine.
    text: A **sample Project file** (`ReadWorkWeeksInformation.mpp`) placed in a known
      folder on your machine.
  type: HowTo
- questions:
  - answer: Yes. The API provides `addWorkWeek()`, `removeWorkWeek()`, and property
      setters to change names, dates, and working times.
    question: Can I modify the work weeks information using Aspose.Tasks for Java?
  - answer: Absolutely. It supports MPP files from Project 98 up to the latest releases,
      as well as Project XML files.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes. The library is pure Java, so you can use it alongside Spring, Jakarta
      EE, or any other framework.
    question: Can I integrate Aspose.Tasks with other Java frameworks?
  - answer: 'Yes, you can download a free 30‑day trial from the official site: [Aspose.Tasks
      trial](https://releases.aspose.com/).'
    question: Is there a trial version available for Aspose.Tasks?
  - answer: 'The Aspose community forum is the best place: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).'
    question: Where can I find support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- read workweeks
- Aspose.Tasks
- Java project scheduling
- MS Project
- calendar API
title: Aspose.Tasks के साथ MS कैलेंडर से workweeks पढ़ने का तरीका
url: /hi/java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS कैलेंडर से Aspose.Tasks के साथ कार्य सप्ताह पढ़ने का तरीका

## परिचय
इस ट्यूटोरियल में आप **कार्य सप्ताह पढ़ना सीखेंगे** Microsoft Project कैलेंडर से Aspose.Tasks लाइब्रेरी for Java का उपयोग करके। चाहे आप एक रिपोर्टिंग डैशबोर्ड बना रहे हों, ERP सिस्टम के साथ शेड्यूल समन्वय कर रहे हों, या विश्लेषण के लिए डेटा निष्कर्षण को स्वचालित कर रहे हों, कार्य‑सप्ताह परिभाषाओं तक प्रोग्रामेटिक पहुंच अनगिनत मैन्युअल घंटे बचाती है। Aspose.Tasks **50+ इनपुट और आउटपुट फॉर्मेट** का समर्थन करता है और कई‑सौ पृष्ठों वाली प्रोजेक्ट फ़ाइलों को पूरी फ़ाइल को मेमोरी में लोड किए बिना प्रोसेस कर सकता है, जिससे आपको लचीलापन और प्रदर्शन दोनों मिलते हैं।

## त्वरित उत्तर
- **“कार्य सप्ताह पढ़ना” का क्या अर्थ है?** यह एक प्रोजेक्ट फ़ाइल से कार्य‑सप्ताह परिभाषाएँ (तिथियाँ और दैनिक कार्य‑समय नियम) को Java कोड के माध्यम से निकालने को दर्शाता है।  
- **कौन सी लाइब्रेरी आवश्यक है?** Aspose.Tasks for Java (नि:शुल्क ट्रायल उपलब्ध)।  
- **क्या विकास के लिए लाइसेंस चाहिए?** ट्रायल परीक्षण के लिए काम करता है; उत्पादन परिनियोजन के लिए व्यावसायिक लाइसेंस आवश्यक है।  
- **कौन से फ़ाइल फॉर्मेट समर्थित हैं?** *.mpp* और Project XML फ़ाइलें दोनों संभाली जाती हैं, साथ ही आयात/निर्यात के लिए 50+ अन्य फॉर्मेट।  
- **इम्प्लीमेंटेशन में कितना समय लगेगा?** लाइब्रेरी सेट अप होने के बाद आमतौर पर 10 मिनट से कम।

## MS प्रोजेक्ट में कार्य सप्ताह क्या है?
एक कार्य सप्ताह वह कैलेंडर नियम परिभाषित करता है जो यह निर्धारित करता है कि संसाधन किसी विशिष्ट अवधि में कब उपलब्ध हैं। इसमें एक प्रारंभ तिथि, एक समाप्ति तिथि, और दैनिक कार्य‑समय अंतराल (जैसे, सुबह 9 से शाम 5) शामिल होते हैं। MS प्रोजेक्ट में, प्रत्येक कैलेंडर कई कार्य सप्ताह रख सकता है, जिससे आप छुट्टियों, शिफ्ट पैटर्न, या मौसमी शेड्यूल को मॉडल कर सकते हैं।

## Aspose.Tasks कैलेंडर से कार्य सप्ताह कैसे पढ़ता है?
Aspose.Tasks `Calendar` ऑब्जेक्ट की `WorkWeekCollection` को उजागर करता है। एक `Project` इंस्टेंस बनाकर, इच्छित कैलेंडर (UID या नाम द्वारा) चुनकर, और उसकी `WorkWeekCollection` पर इटरेट करके, आप प्रत्येक कार्य‑सप्ताह का लेबल, प्रभावी तिथि रेंज, और विस्तृत दैनिक कार्य‑समय स्लॉट प्राप्त कर सकते हैं। API सभी तिथि‑समय रूपांतरणों को संभालती है और प्रोजेक्ट की टाइम‑ज़ोन सेटिंग्स का स्वचालित सम्मान करती है।

## Java में Microsoft Project कैलेंडर से कार्य सप्ताह क्यों पढ़ें?
कार्य सप्ताह को प्रोग्रामेटिक रूप से पढ़ना मैन्युअल कॉपी‑पेस्ट को समाप्त करता है, सुनिश्चित करता है कि डाउनस्ट्रीम सिस्टम (ERP, HR, रिपोर्टिंग) बिल्कुल वही शेड्यूल नियम उपयोग करें, और कई प्रोजेक्ट्स में स्थिरता की गारंटी देता है। स्वचालन मानव त्रुटियों को कम करता है और इंटीग्रेशन पाइपलाइन को तेज़ करता है, विशेष रूप से जब आपको हर रात दर्जनों प्रोजेक्ट फ़ाइलों को प्रोसेस करना हो।

## पूर्वापेक्षाएँ
कोड में डुबकी लगाने से पहले सुनिश्चित करें कि आपके पास हैं:

1. **Java Development Kit (JDK)** – संस्करण 8 या बाद का स्थापित हो।  
2. **Aspose.Tasks for Java** – आधिकारिक साइट से नवीनतम JAR डाउनलोड करें: [Aspose.Tasks for Java डाउनलोड](https://releases.aspose.com/tasks/java/).  
3. एक **सैंपल प्रोजेक्ट फ़ाइल** (`ReadWorkWeeksInformation.mpp`) जिसे आपके मशीन पर किसी ज्ञात फ़ोल्डर में रखें।

## पैकेज आयात करें
पहले, उन क्लासों को आयात करें जिनकी हमें कैलेंडर और कार्य सप्ताह के साथ इंटरैक्ट करने की आवश्यकता होगी:

`Project` Microsoft Project फ़ाइल को दर्शाता है, `Calendar` उसके कैलेंडर प्रदान करता है, `WorkWeek` एक कार्य‑सप्ताह को परिभाषित करता है, और `WeekDay` एक दिन को दर्शाता है।

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```

## चरण 1: अपना डेटा डायरेक्टरी सेट करें
`.mpp` फ़ाइल वाले फ़ोल्डर को परिभाषित करें। प्लेसहोल्डर को अपने मशीन पर वास्तविक पथ से बदलें:

```java
String dataDir = "Your Data Directory";
```

## चरण 2: एक Project इंस्टेंस बनाएं और कैलेंडर तक पहुंचें
`Project` क्लास Microsoft Project फ़ाइल का प्रतिनिधित्व करती है और कैलेंडर, टास्क, रिसोर्स आदि डेटा स्ट्रक्चर तक पहुंच प्रदान करती है।  
एक `Project` ऑब्जेक्ट इंस्टैंशिएट करें, इच्छित कैलेंडर (UID द्वारा) चुनें, और उसकी `WorkWeekCollection` प्राप्त करें:

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **Pro tip:** यदि आप कैलेंडर UID के बारे में निश्चित नहीं हैं, तो `project.getCalendars()` पर इटरेट करके प्रत्येक कैलेंडर का नाम और UID पहले प्रिंट करें।

## चरण 3: कार्य सप्ताहों पर पुनरावृति करें
`WorkWeek` क्लास एक कार्य‑सप्ताह परिभाषा को समेटे हुए है, जिसमें प्रारंभ/समाप्ति तिथियाँ और दैनिक कार्य‑समय सेटिंग्स शामिल हैं।  
प्रत्येक `WorkWeek` पर लूप करें ताकि उसका नाम, प्रारंभ/समाप्ति तिथियाँ, और दैनिक कार्य‑समय प्रदर्शित हो सकें:

```java
for (WorkWeek workWeek : collection) {
    // Display work week name, from and to dates
    System.out.println(workWeek.getName());
    System.out.println(workWeek.getFromDate());
    System.out.println(workWeek.getToDate());
    // Access week days and working times
    WeekDayCollection weekDays = workWeek.getWeekDays();
    for (WeekDay day : weekDays) {
        WorkingTimeCollection workingTimes = day.getWorkingTimes();
        // Further process working times if needed
    }
}
```

**आपको जो दिखेगा:** कंसोल प्रत्येक कार्य‑सप्ताह का लेबल (जैसे, “Standard”), उसकी प्रभावी तिथि रेंज, और आप प्रत्येक दिन के सटीक कार्य‑घंटों को देख पाएंगे।

## सामान्य समस्याएँ और समाधान
| समस्या | कारण | समाधान |
|-------|--------|-----|
| `NullPointerException` जब `calendar` तक पहुंच रहे हों | गलत UID या कैलेंडर मौजूद नहीं है | `project.getCalendars().size()` से UID सत्यापित करें और पहले उपलब्ध कैलेंडर सूचीबद्ध करें। |
| कार्य सप्ताहों के लिए कोई आउटपुट नहीं | चयनित कैलेंडर में कोई कस्टम कार्य सप्ताह नहीं है (डिफ़ॉल्ट उपयोग करता है) | डिफ़ॉल्ट कैलेंडर (`project.getDefaultCalendar()`) का उपयोग करें या प्रोग्रामेटिक रूप से एक कार्य सप्ताह बनाएं। |
| तिथि फ़ॉर्मेट अजीब दिख रहा है | `System.out.println` डिफ़ॉल्ट `java.util.Date` फ़ॉर्मेट उपयोग करता है | आवश्यकतानुसार तिथियों को फ़ॉर्मेट करने के लिए `SimpleDateFormat` लागू करें। |

## अक्सर पूछे जाने वाले प्रश्न
**प्रश्न: क्या मैं Aspose.Tasks for Java का उपयोग करके कार्य सप्ताह की जानकारी संशोधित कर सकता हूँ?**  
उत्तर: हाँ। API `addWorkWeek()`, `removeWorkWeek()` और प्रॉपर्टी सेटर्स प्रदान करता है जिससे नाम, तिथियाँ और कार्य‑समय बदल सकते हैं।

**प्रश्न: क्या Aspose.Tasks विभिन्न संस्करणों की Microsoft Project फ़ाइलों के साथ संगत है?**  
उत्तर: बिल्कुल। यह Project 98 से लेकर नवीनतम रिलीज़ तक के MPP फ़ाइलों, साथ ही Project XML फ़ाइलों को सपोर्ट करता है।

**प्रश्न: क्या मैं Aspose.Tasks को अन्य Java फ्रेमवर्क के साथ एकीकृत कर सकता हूँ?**  
उत्तर: हाँ। लाइब्रेरी शुद्ध Java है, इसलिए आप इसे Spring, Jakarta EE या किसी भी अन्य फ्रेमवर्क के साथ उपयोग कर सकते हैं।

**प्रश्न: क्या Aspose.Tasks के लिए ट्रायल संस्करण उपलब्ध है?**  
उत्तर: हाँ, आप आधिकारिक साइट से 30‑दिन का मुफ्त ट्रायल डाउनलोड कर सकते हैं: [Aspose.Tasks ट्रायल](https://releases.aspose.com/).

**प्रश्न: Aspose.Tasks के लिए समर्थन कहाँ मिल सकता है?**  
उत्तर: Aspose कम्युनिटी फ़ोरम सबसे अच्छा स्थान है: [Aspose.Tasks फ़ोरम](https://forum.aspose.com/c/tasks/15)।

---

**अंतिम अद्यतन:** 2026-08-13  
**परीक्षण किया गया:** Aspose.Tasks for Java 24.12 (लेखन समय पर नवीनतम)  
**लेखक:** Aspose  

{{< blocks/products/products-backtop-button >}}

## संबंधित ट्यूटोरियल

- [Aspose.Tasks for Java के साथ प्रोजेक्ट में कैलेंडर जोड़ें](/tasks/java/calendars/create/)
- [Aspose.Tasks के साथ कैलेंडर अपवाद प्राप्त करें – asp tasks java ट्यूटोरियल](/tasks/java/calendar-exceptions/retrieve/)
- [MS Project में कैलेंडर सेट करने और सप्ताह के दिन निर्धारित करने का तरीका Aspose.Tasks के साथ](/tasks/java/calendars/define-weekdays/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}