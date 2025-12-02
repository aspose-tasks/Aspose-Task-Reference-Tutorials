---
date: 2025-12-02
description: जानेँ कि कैसे कैलेंडर सेट करें, MS Project में कार्यदिवस निर्धारित करें
  और Aspose.Tasks for Java का उपयोग करके कस्टम कार्य दिवस सेट करें। कुछ ही कोड लाइनों
  के साथ प्रोजेक्ट को XML के रूप में सहेजें।
language: hi
linktitle: How to Set Calendar and Define Weekdays in MS Project with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks के साथ MS Project में कैलेंडर सेट करने और सप्ताह के दिनों को परिभाषित
  करने का तरीका
url: /java/calendars/define-weekdays/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Project में कैलेंडर सेट करने और कार्यदिवस निर्धारित करने का तरीका Aspose.Tasks के साथ

## परिचय
इस ट्यूटोरियल में आप **कैलेंडर सेट करने** की सेटिंग्स को प्रोग्रामेटिकली कैसे सेट करें और Aspose.Tasks लाइब्रेरी फॉर जावा का उपयोग करके Microsoft Project फ़ाइल में कार्यदिवस कैसे परिभाषित करें, यह जानेंगे। चाहे आपको एक मानक कार्य सप्ताह बनाना हो, सप्ताहांत के कार्य दिवस जोड़ने हों, या शॉर्ट फ्राइडे शेड्यूल कॉन्फ़िगर करना हो, यह गाइड प्रोजेक्ट निर्माण से लेकर फ़ाइल को XML के रूप में सेव करने तक के हर चरण को समझाता है।

## त्वरित उत्तर
- **कौन सी लाइब्रेरी चाहिए?** Aspose.Tasks for Java  
- **क्या मैं सप्ताहांत के कार्य दिवस जोड़ सकता हूँ?** हाँ – बस शनिवार और रविवार को कार्य दिवस के रूप में जोड़ें।  
- **प्रोजेक्ट को कैसे सेव करें?** `prj.save(..., SaveFileFormat.Xml)` का उपयोग करें।  
- **क्या लाइसेंस चाहिए?** मूल्यांकन के लिए एक फ्री ट्रायल चल सकता है; उत्पादन के लिए लाइसेंस आवश्यक है।  
- **कौन सा जावा संस्करण आवश्यक है?** Java 8 या उससे ऊपर।

## MS Project के संदर्भ में “कैलेंडर सेट करने” का क्या मतलब है?
MS Project में कैलेंडर सेट करने का अर्थ है यह निर्धारित करना कि कौन से दिन कार्य दिवस हैं, दैनिक कार्य घंटे क्या हैं, और छुट्टियों जैसी अपवाद क्या हैं। यह कैलेंडर टास्क शेड्यूलिंग, रिसोर्स अलोकेशन और समग्र प्रोजेक्ट टाइमलाइन को नियंत्रित करता है।

## कैलेंडर मैनिपुलेशन के लिए Aspose.Tasks क्यों उपयोग करें?
- **पूर्ण नियंत्रण** – UI खोले बिना प्रोग्रामेटिकली कैलेंडर बनाना, संशोधित करना या हटाना।  
- **क्रॉस‑प्लेटफ़ॉर्म** – वह सभी OS पर काम करता है जो जावा को सपोर्ट करते हैं।  
- **सभी फ़ाइल फ़ॉर्मेट सपोर्ट** – MPP, MPT, और XML, इसलिए आप *प्रोजेक्ट को XML के रूप में सेव* कर सकते हैं जिससे अन्य सिस्टम के साथ आसान इंटीग्रेशन हो।  
- **कोई COM डिपेंडेंसी नहीं** – Microsoft Project Interop लाइब्रेरी के विपरीत।

## पूर्वापेक्षाएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

1. **Java Development Kit (JDK) 8+** – इसे [Oracle वेबसाइट](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) से डाउनलोड करें।  
2. **Aspose.Tasks for Java** – नवीनतम JAR को [Aspose.Tasks डाउनलोड पेज](https://releases.aspose.com/tasks/java/) से प्राप्त करें।  
3. एक IDE या बिल्ड टूल (Maven/Gradle) ताकि आप Aspose.Tasks JAR को अपने प्रोजेक्ट की classpath में जोड़ सकें।

## पैकेज इम्पोर्ट करें
सबसे पहले, उन क्लासेज़ को इम्पोर्ट करें जिनकी आपको आवश्यकता होगी। ये इम्पोर्ट्स आपको प्रोजेक्ट, कैलेंडर, और कार्य‑समय ऑब्जेक्ट्स तक पहुंच प्रदान करेंगे।

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

## चरण‑दर‑चरण गाइड

### चरण 1: प्रोजेक्ट इंस्टेंस बनाएं
एक नया `Project` ऑब्जेक्ट बनाएं। यह ऑब्जेक्ट उस MS Project फ़ाइल का प्रतिनिधित्व करता है जिसे आप संपादित करेंगे।

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```

### चरण 2: नया कैलेंडर परिभाषित करें
प्रोजेक्ट में एक नया कैलेंडर जोड़ें। जब आपके पास कई कैलेंडर हों तो स्पष्ट नाम देना उपयोगी रहता है।

```java
Calendar cal = prj.getCalendars().add("Calendar1");
```

### चरण 3: मानक कार्य दिवस जोड़ें (सोमवार‑गुरुवार)
बिल्ट‑इन हेल्पर `WeekDay.createDefaultWorkingDay` का उपयोग करके कोर कार्य सप्ताह के लिए डिफ़ॉल्ट 9 am‑5 pm शेड्यूल सेट करें।

```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```

### चरण 4: सप्ताहांत के कार्य दिवस जोड़ें
यदि आपका प्रोजेक्ट सप्ताहांत में चलता है, तो बस शनिवार और रविवार को नियमित कार्य दिवस के रूप में जोड़ें। यह **सप्ताहांत के कार्य दिवस जोड़ने** का प्रदर्शन करता है।

```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```

### चरण 5: कस्टम शॉर्ट कार्य दिवस सेट करें (शुक्रवार)
यहाँ हम **शुक्रवार के लिए कस्टम कार्य दिवस** सेट करते हैं: एक सुबह की शिफ्ट (9 am‑12 pm) और एक दोपहर की शिफ्ट (1 pm‑4 pm)।

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

### चरण 6: प्रोजेक्ट को XML के रूप में सेव करें
अंत में, परिवर्तन को स्थायी बनाएं। `SaveFileFormat.Xml` विकल्प आपको **प्रोजेक्ट को XML के रूप में सेव** करने देता है, जो अन्य टूल्स के साथ इंटीग्रेशन के लिए उपयोगी है।

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## सामान्य समस्याएँ और समाधान
| समस्या | समाधान |
|-------|----------|
| **वर्किंग टाइम लागू नहीं हो रहा** | सुनिश्चित करें कि कस्टम `WeekDay` पर `setDayWorking(true)` कॉल किया गया है। |
| **सेव करते समय फ़ाइल नहीं मिली** | जांचें कि `dataDir` किसी मौजूदा फ़ोल्डर की ओर इशारा कर रहा है और आपके एप्लिकेशन के पास लिखने की अनुमति है। |
| **कैलेंडर टास्क में परिलक्षित नहीं हो रहा** | नए बनाए गए कैलेंडर को रिसोर्स या टास्क को `task.setCalendar(cal)` के माध्यम से असाइन करें। |

## अक्सर पूछे जाने वाले प्रश्न

**प्र: क्या मैं Aspose.Tasks for Java का उपयोग करके कस्टम नॉन‑वर्किंग दिन परिभाषित कर सकता हूँ?**  
उ: हाँ। किसी भी `WeekDay` के लिए `DayWorking` प्रॉपर्टी को `false` सेट करें जिसे आप नॉन‑वर्किंग दिन बनाना चाहते हैं।

**प्र: मैं छुट्टियों या कंपनी‑व्यापी अपवाद कैसे जोड़ सकता हूँ?**  
उ: `CalendarException` ऑब्जेक्ट बनाएं, अपवाद तिथियों को निर्दिष्ट करें, और उन्हें `cal.getExceptions()` में जोड़ें।

**प्र: क्या लाइब्रेरी पुराने MS Project संस्करणों के साथ संगत है?**  
उ: बिल्कुल। Aspose.Tasks कई प्रोजेक्ट संस्करणों में MPP, MPT, और XML फ़ॉर्मेट्स को सपोर्ट करता है।

**प्र: क्या मैं इम्पोर्ट किए गए प्रोजेक्ट में मौजूदा कैलेंडर को संशोधित कर सकता हूँ?**  
उ: प्रोजेक्ट को `new Project("existing.mpp")` से लोड करें, इच्छित कैलेंडर प्राप्त करें, बदलाव करें, और फिर सेव करें।

**प्र: क्या Aspose.Tasks आवर्ती टास्क को भी संभालता है?**  
उ: हाँ, आप `RecurringTask` क्लास का उपयोग करके आवर्ती टास्क बना और संपादित कर सकते हैं।

## निष्कर्ष
अब आप **कैलेंडर सेट करने** की सेटिंग्स, **MS Project में कार्यदिवस परिभाषित करने**, सप्ताहांत के कार्य दिवस जोड़ने, और शॉर्ट फ्राइडे शेड्यूल बनाने के बारे में जानते हैं—सभी Aspose.Tasks for Java के साथ। परिणाम को XML के रूप में सेव करें और कैलेंडर लॉजिक को किसी भी जावा‑आधारित प्रोजेक्ट मैनेजमेंट समाधान में इंटीग्रेट करें।

---

**अंतिम अपडेट:** 2025-12-02  
**टेस्टेड विथ:** Aspose.Tasks for Java 24.11  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}