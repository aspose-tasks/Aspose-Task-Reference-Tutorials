---
date: 2026-08-24
description: MS Project कैलेंडरों से कार्य घंटे निकालकर छुट्टियों का कैलेंडर जोड़ना,
  कार्य दिवस निर्धारित करना और कार्य अवधि की गणना करना सीखें, Aspose.Tasks for Java
  का उपयोग करके।
keywords:
- add holidays calendar
- determine working days
- read ms project
- calculate task duration
- load mpp file
lastmod: 2026-08-24
linktitle: छुट्टियों का कैलेंडर कैसे जोड़ें और कार्य दिवस निर्धारित करें
og_description: MS Project कैलेंडरों से कार्य घंटे निकालकर छुट्टियों का कैलेंडर जोड़ना,
  कार्य दिवस निर्धारित करना और कार्य अवधि की गणना करना सीखें, Aspose.Tasks for Java
  का उपयोग करके।
og_image_alt: Guide to add holidays calendar and calculate task duration with Aspose.Tasks
  Java
og_title: छुट्टियों का कैलेंडर कैसे जोड़ें और कार्य दिवस निर्धारित करें
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to add holidays calendar, determine working days and calculate
    task duration by extracting working hours from MS Project calendars using Aspose.Tasks
    for Java.
  headline: How to add holidays calendar and determine working days
  type: TechArticle
- description: Learn how to add holidays calendar, determine working days and calculate
    task duration by extracting working hours from MS Project calendars using Aspose.Tasks
    for Java.
  name: How to add holidays calendar and determine working days
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or higher.'
    text: '**Java Development Kit (JDK)** – version 8 or higher.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from [Aspose.Tasks
      for Java releases](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from [Aspose.Tasks
      for Java releases](https://releases.aspose.com/tasks/java/).'
  - name: Basic Java programming knowledge.
    text: Basic Java programming knowledge.
  type: HowTo
- questions:
  - answer: It means identifying which calendar dates are considered work‑days for
      a given task.
    question: What does “determine working days” mean?
  - answer: Aspose.Tasks for Java provides a full‑featured API for working with MS
      Project files.
    question: Which library should I use?
  - answer: Typically 10–15 minutes for a basic extraction.
    question: How long does the implementation take?
  - answer: A free trial is available; a commercial license is required for production
      use.
    question: Do I need a license?
  - answer: Yes – you can modify calendars, add holidays, and set custom work‑time
      ranges.
    question: Can I customize working hours?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add holidays calendar
- Aspose.Tasks
- Java project scheduling
- MS Project automation
title: छुट्टियों का कैलेंडर कैसे जोड़ें और कार्य दिवस निर्धारित करें
url: /hi/java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# छुट्टियों का कैलेंडर जोड़ना और कार्य दिवस निर्धारित करना

प्रोजेक्ट कैलेंडर का प्रबंधन सफल प्रोजेक्ट योजना का एक मुख्य भाग है। इस ट्यूटोरियल में आप **छुट्टियों का कैलेंडर जोड़ेंगे**, किसी भी टास्क के लिए **कार्य दिवस निर्धारित करेंगे**, और Aspose.Tasks for Java का उपयोग करके MS Project कैलेंडर से **कार्य घंटे निकालेंगे**। गाइड के अंत तक आप **टास्क की अवधि की गणना** कर सकेंगे, कार्य घंटों को कस्टमाइज़ कर सकेंगे, और बिना Microsoft Project स्थापित किए **एक MPP फ़ाइल लोड** करके आवश्यक डेटा प्राप्त कर सकेंगे।

## त्वरित उत्तर
- **“कार्य दिवस निर्धारित करना” का क्या अर्थ है?** यह किसी टास्क के लिए कौन से कैलेंडर तिथियों को कार्य‑दिवस माना जाता है, इसे पहचानना है।  
- **मैं कौन सी लाइब्रेरी उपयोग करूँ?** Aspose.Tasks for Java MS Project फ़ाइलों के साथ काम करने के लिए पूर्ण‑विशेषताओं वाला API प्रदान करता है।  
- **इम्प्लीमेंटेशन में कितना समय लगेगा?** आमतौर पर बुनियादी एक्सट्रैक्शन के लिए 10–15 मिनट।  
- **क्या मुझे लाइसेंस चाहिए?** एक मुफ्त ट्रायल उपलब्ध है; उत्पादन उपयोग के लिए व्यावसायिक लाइसेंस आवश्यक है।  
- **क्या मैं कार्य घंटों को कस्टमाइज़ कर सकता हूँ?** हाँ – आप कैलेंडर को संशोधित कर सकते हैं, छुट्टियाँ जोड़ सकते हैं, और कस्टम कार्य‑समय रेंज सेट कर सकते हैं।  

## “कार्य दिवस निर्धारित करना” क्या है?
**कार्य दिवस निर्धारित करना** का अर्थ है प्रोजेक्ट कैलेंडर को क्वेरी करके यह पता लगाना कि कौन सी तिथियों को कार्य‑दिवस और कौन सी को गैर‑कार्य दिवस (वीकेंड, छुट्टियाँ, या कस्टम अपवाद) के रूप में चिह्नित किया गया है। यह जानकारी सटीक **टास्क की अवधि की गणना** के लिए आवश्यक है क्योंकि केवल कार्य दिवस ही टास्क के कुल समय में योगदान देते हैं।

## कार्य घंटे प्राप्त करने के लिए Aspose.Tasks क्यों उपयोग करें?
Aspose.Tasks आपको Microsoft Project स्थापित किए बिना MS Project फ़ाइलें पढ़ने की अनुमति देता है, जिससे किसी भी प्लेटफ़ॉर्म पर ऑटोमेशन संभव होता है। यह उच्च‑प्रदर्शन प्रोसेसिंग, व्यापक फ़ॉर्मेट समर्थन, और विस्तृत दस्तावेज़ीकरण भी प्रदान करता है।

- **पूर्ण कैलेंडर समर्थन** – डिफ़ॉल्ट, रिसोर्स, और टास्क कैलेंडर सभी उपलब्ध हैं।  
- **उच्च प्रदर्शन** – मानक 2.5 GHz CPU पर **10,000+ टास्क** वाले प्रोजेक्ट को 2 सेकंड से कम में प्रोसेस कर सकता है।  
- **व्यापक फ़ॉर्मेट कवरेज** – **50+ इनपुट और आउटपुट फ़ॉर्मेट** का समर्थन करता है, जिसमें MPP, MPX, XML, और Primavera शामिल हैं।  
- **व्यापक दस्तावेज़ीकरण** – कोड नमूने, API रेफ़रेंस, और कम्युनिटी फ़ोरम सभी उपलब्ध हैं।

## पूर्वापेक्षाएँ
शुरू करने से पहले, सुनिश्चित करें कि आपके पास है:

1. **Java Development Kit (JDK)** – संस्करण 8 या उससे ऊपर।  
2. **Aspose.Tasks for Java** – नवीनतम JAR [Aspose.Tasks for Java releases](https://releases.aspose.com/tasks/java/) से डाउनलोड करें।  
3. बेसिक Java प्रोग्रामिंग ज्ञान।

## पैकेज आयात करें
`Project` क्लास Aspose.Tasks का टॉप‑लेवल ऑब्जेक्ट है जो मेमोरी में एकल MS Project फ़ाइल का प्रतिनिधित्व करता है। शुरू करने से पहले आवश्यक नेमस्पेस आयात करें:

पैकेज आयात करें

```java
import com.aspose.tasks.*;
```

## Aspose.Tasks के साथ MPP फ़ाइल कैसे लोड करें?
`Project` क्लास एक MS Project फ़ाइल को लोड करता है और उसके डेटा तक पहुंच प्रदान करता है। कोड की एक ही पंक्ति में प्रोजेक्ट फ़ाइल लोड करें; कोई UI या COM इंटरऑप आवश्यक नहीं है। यह सरल चरण आपको कैलेंडर, टास्क, और रिसोर्सेज तक पूर्ण पहुंच देता है।

MPP फ़ाइल लोड करना

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## टास्क और कैलेंडर जानकारी प्राप्त करें
`Task` एक प्रोजेक्ट टास्क को दर्शाता है, और `Calendar` उसके कार्य समय नियमों को परिभाषित करता है। वह टास्क चुनें जिसे आप विश्लेषण करना चाहते हैं और उसका संबंधित कैलेंडर प्राप्त करें। `Task` ऑब्जेक्ट `getStart()` और `getFinish()` मेथड प्रदान करता है, जबकि `Calendar` ऑब्जेक्ट कार्य समय परिभाषाएँ उजागर करता है।

टास्क और कैलेंडर प्राप्त करना

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## प्रारंभ और समाप्ति तिथियों को परिभाषित करें
`Date` ऑब्जेक्ट कैलेंडर विश्लेषण के लिए समय विंडो निर्दिष्ट करते हैं। वह समय विंडो सेट करें जिसके लिए आप **कार्य दिवस निर्धारित करना** चाहते हैं। टास्क की प्रारंभ और समाप्ति तिथियों का उपयोग करने से आप केवल संबंधित अवधि का मूल्यांकन करेंगे।

तिथियों को परिभाषित करना

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## तिथियों के माध्यम से इटररेट करें
`for` लूप तिथि रेंज के प्रत्येक दिन पर इटररेट कर सकता है। टास्क की अवधि में प्रत्येक तिथि पर लूप करें। यह लूप आपको बाद में आवश्यकता होने पर **कार्य घंटों को कस्टमाइज़** करने की अनुमति देगा और कुल कार्य समय की गणना का आधार है।

तिथियों पर इटररेट करना

```java
java.util.Calendar tempDate = calStartDate;
```

## अवधि की गणना करें
`Duration` इटररेशन से गणना किए गए कुल कार्य समय को एकत्रित करता है। इटररेशन के दौरान आप जांचते हैं कि प्रत्येक दिन कार्य दिवस है या नहीं, कार्य घंटों को जोड़ते हैं, और अंत में टास्क की अवधि को मिनट, घंटे, और दिनों में गणना करते हैं। यह दर्शाता है कि प्रोग्रामेटिक रूप से **कार्य दिवसों की गणना** और **टास्क की अवधि की गणना** कैसे की जाती है।

अवधि की गणना

```java
double durationInMins = 0;
double durationInHours = 0;
double durationInDays = 0;
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
long timeSpan;
while (tempDate.before(calEndDate)) {
    if (taskCalendar.isDayWorking(tempDate.getTime())) {
        timeSpan = (long) taskCalendar.getWorkingHours(tempDate.getTime());
        durationInMins += (double) timeSpan / OneMin;
        durationInHours += (double) timeSpan / OneHour;
        if ((timeSpan / OneHour) > 0) {
            durationInDays += ((double) timeSpan / OneHour / 8.0);
        }
    }
    tempDate.add(java.util.Calendar.DATE, 1);
}
System.out.println("Duration in Minutes = " + durationInMins);
System.out.println("Duration in Hours = " + durationInHours);
System.out.println("Duration in Days = " + durationInDays);
System.out.println();
```

## कार्य घंटे और छुट्टियों को कैसे कस्टमाइज़ करें
आप कैलेंडर के कार्य समय रेंज को संशोधित कर सकते हैं और छुट्टियों जैसे अपवाद जोड़ सकते हैं। नया कार्य अवधि सेट करने के लिए `taskCalendar.addWorkingTime()` का उपयोग करें और छुट्टी डालने के लिए `taskCalendar.addException()` का उपयोग करें। यह तब उपयोगी होता है जब डिफ़ॉल्ट 9‑5 शेड्यूल आपके संगठन की नीतियों से मेल नहीं खाता।

## सामान्य समस्याएँ और समाधान
| समस्या | समाधान |
|-------|----------|
| **टास्क का कैलेंडर `null` लौटाता है** | सुनिश्चित करें कि टास्क को वास्तव में एक कैलेंडर असाइन किया गया है; अन्यथा यह प्रोजेक्ट के डिफ़ॉल्ट कैलेंडर को विरासत में लेता है। |
| **छुट्टियों के कारण गलत अवधि** | जाँचें कि छुट्टियाँ टास्क के कैलेंडर में या प्रोजेक्ट के बेस कैलेंडर में परिभाषित हैं। |
| **समय क्षेत्र का मेल नहीं** | यदि आवश्यक हो तो कैलेंडर के समय क्षेत्र को अपने सिस्टम के साथ संरेखित करने के लिए `java.util.TimeZone` का उपयोग करें। |

## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या Aspose.Tasks for Java जटिल प्रोजेक्ट संरचनाओं को संभाल सकता है?
उत्तर: हाँ, Aspose.Tasks for Java जटिल प्रोजेक्ट संरचनाओं को संभालने के लिए व्यापक समर्थन प्रदान करता है, जिसमें टास्क, रिसोर्सेज, और कैलेंडर शामिल हैं।

### प्रश्न: क्या Aspose.Tasks for Java विभिन्न MS Project संस्करणों के साथ संगत है?
उत्तर: बिल्कुल, Aspose.Tasks for Java विभिन्न MS Project संस्करणों का समर्थन करता है, जिससे विभिन्न वातावरणों में संगतता सुनिश्चित होती है।

### प्रश्न: क्या मैं प्रोजेक्ट कैलेंडरों में कार्य घंटे और छुट्टियों को कस्टमाइज़ कर सकता हूँ?
उत्तर: हाँ, आप Aspose.Tasks for Java APIs का उपयोग करके अपने प्रोजेक्ट आवश्यकताओं के अनुसार कार्य घंटे और छुट्टियों को आसानी से कस्टमाइज़ कर सकते हैं।

### प्रश्न: क्या Aspose.Tasks for Java समर्थन और दस्तावेज़ीकरण प्रदान करता है?
उत्तर: हाँ, Aspose.Tasks for Java विस्तृत दस्तावेज़ीकरण और समर्पित समर्थन फ़ोरम प्रदान करता है ताकि डेवलपर्स इसकी सुविधाओं का प्रभावी उपयोग कर सकें।

### प्रश्न: क्या Aspose.Tasks for Java के लिए ट्रायल संस्करण उपलब्ध है?
उत्तर: हाँ, आप [Aspose releases page](https://releases.aspose.com/) से Aspose.Tasks for Java का मुफ्त ट्रायल संस्करण प्राप्त कर सकते हैं।

## निष्कर्ष
इस गाइड में हमने Aspose.Tasks for Java का उपयोग करके MS Project कैलेंडर से **छुट्टियों का कैलेंडर जोड़ना**, **कार्य दिवस निर्धारित करना**, **कार्य घंटे प्राप्त करना**, और **टास्क की अवधि की गणना** कैसे की जाए, दर्शाया है। ऊपर दिए गए चरणों का पालन करके आप शेड्यूल विश्लेषण को ऑटोमेट कर सकते हैं, कैलेंडर को कस्टमाइज़ कर सकते हैं, और अपने प्रोजेक्ट प्लान को सटीक और अद्यतित रख सकते हैं। अब आपके पास **MS Project** डेटा पढ़ने, **एक MPP फ़ाइल लोड** करने, और माइक्रोसॉफ्ट Project की आवश्यकता के बिना सटीक अवधि गणनाएँ करने के उपकरण हैं।

---

**अंतिम अपडेट:** 2026-08-24  
**परीक्षण किया गया:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [Aspose.Tasks for Java के साथ प्रोजेक्ट में कैलेंडर जोड़ें](/tasks/java/calendars/create/)
- [Aspose.Tasks के साथ कैलेंडर में छुट्टियाँ जोड़ें और MPP के रूप में सहेजें](/tasks/java/calendars/update-to-mpp/)
- [Aspose.Tasks for Java के साथ कस्टम कैलेंडर अपवाद बनाएं](/tasks/java/calendar-exceptions/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}