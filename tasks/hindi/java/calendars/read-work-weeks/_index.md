---
date: 2026-02-05
description: Aspose.Tasks का उपयोग करके Microsoft Project कैलेंडर से Java में कार्यसप्ताह
  पढ़ना सीखें। पूर्ण कोड उदाहरणों के साथ चरण‑दर‑चरण मार्गदर्शिका का पालन करें।
linktitle: Read Work Weeks from Calendar with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: MS Project Calendar Aspose.Tasks से जावा में कार्यसप्ताह कैसे पढ़ें
url: /hi/java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to Read Workweeks Java from MS Project Calendar Aspose.Tasks

## Introduction
इस ट्यूटोरियल में आप **Java से Workweeks पढ़ना** सीखेंगे, जो Microsoft Project कैलेंडर से Aspose.Tasks लाइब्रेरी का उपयोग करके किया जाता है। चाहे आप रिपोर्टिंग टूल बना रहे हों, शेड्यूल सिंक्रनाइज़ कर रहे हों, या प्रोजेक्ट डेटा एक्सट्रैक्शन को ऑटोमेट कर रहे हों, प्रोग्रामेटिकली वर्क‑वीक डिफिनिशन तक पहुंचना मैन्युअल घंटों की बचत करता है। हम आवश्यक सेटअप को दिखाएंगे, वर्क‑वीक विवरण प्राप्त करने के लिए सटीक कोड प्रदान करेंगे, और प्रत्येक चरण को समझाएंगे ताकि आप इसे अपने प्रोजेक्ट्स में अनुकूलित कर सकें।

## Quick Answers
- **“read workweeks java” का क्या मतलब है?** यह Java कोड का उपयोग करके प्रोजेक्ट फ़ाइल से वर्क‑वीक डिफिनिशन निकालने को दर्शाता है।  
- **कौन सी लाइब्रेरी आवश्यक है?** Aspose.Tasks for Java (फ्री ट्रायल उपलब्ध)।  
- **क्या विकास के लिए लाइसेंस चाहिए?** टेस्टिंग के लिए ट्रायल चलती है; प्रोडक्शन के लिए कमर्शियल लाइसेंस आवश्यक है।  
- **कौन से फ़ाइल फ़ॉर्मेट सपोर्टेड हैं?** *.mpp* और Project XML फ़ाइलें दोनों संभाली जाती हैं।  
- **इम्प्लीमेंटेशन में कितना समय लगेगा?** लाइब्रेरी सेटअप हो जाने के बाद आमतौर पर 10 मिनट से कम।

## How to Read Workweeks Java from a Microsoft Project Calendar
Java में वर्क‑वीक पढ़ना Aspose.Tasks API का उपयोग करके Microsoft Project फ़ाइल के भीतर कैलेंडर ऑब्जेक्ट की `WorkWeekCollection` तक पहुंचना है। प्रत्येक `WorkWeek` में शुरू/समाप्ति तिथियां और दैनिक कार्य‑समय परिभाषाएँ होती हैं जो संसाधनों के शेड्यूल को निर्धारित करती हैं।

## Why read workweeks Java from a Microsoft Project calendar?
- **Automation:** शेड्यूल डेटा की मैन्युअल कॉपी‑पेस्ट को समाप्त करता है।  
- **Integration:** वर्क‑वीक जानकारी को ERP, HR, या कस्टम रिपोर्टिंग सिस्टम में फीड करता है।  
- **Consistency:** सुनिश्चित करता है कि सभी डाउनस्ट्रीम टूल्स प्रोजेक्ट फ़ाइल में परिभाषित एक ही कैलेंडर नियमों का पालन करें।

## Prerequisites
कोड में डुबने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

1. **Java Development Kit (JDK)** – संस्करण 8 या बाद का स्थापित हो।  
2. **Aspose.Tasks for Java** – आधिकारिक साइट से नवीनतम JAR डाउनलोड करें: [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
3. एक **सैंपल प्रोजेक्ट फ़ाइल** (`ReadWorkWeeksInformation.mpp`) जिसे आप किसी ज्ञात फ़ोल्डर में रखें।

## Import Packages
पहले, उन क्लासेज़ को इम्पोर्ट करें जिनकी हमें कैलेंडर और वर्क‑वीक के साथ इंटरैक्ट करने के लिए आवश्यकता होगी:

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```

## Step 1: Set Up Your Data Directory
`.mpp` फ़ाइल वाले फ़ोल्डर को परिभाषित करें। प्लेसहोल्डर को अपने मशीन पर वास्तविक पाथ से बदलें:

```java
String dataDir = "Your Data Directory";
```

## Step 2: Create a Project Instance and Access the Calendar
एक `Project` ऑब्जेक्ट बनाएं, इच्छित कैलेंडर को (UID द्वारा) चुनें, और उसकी `WorkWeekCollection` प्राप्त करें:

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **Pro tip:** यदि आपको कैलेंडर UID का पता नहीं है, तो आप `project.getCalendars()` के माध्यम से इटररेट कर सकते हैं और प्रत्येक कैलेंडर का नाम व UID प्रिंट कर सकते हैं।

## Step 3: Iterate Through Work Weeks
प्रत्येक `WorkWeek` पर लूप करें ताकि उसका नाम, शुरू/समाप्ति तिथि, और दैनिक कार्य समय दिखाया जा सके:

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

**आपको क्या दिखेगा:** कंसोल प्रत्येक वर्क‑वीक का लेबल (जैसे “Standard”), उसकी प्रभावी तिथि रेंज, और प्रत्येक दिन के सटीक कार्य घंटे प्रदर्शित करेगा।

## Common Issues and Solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| `NullPointerException` when accessing `calendar` | Wrong UID or calendar does not exist | Verify the UID with `project.getCalendars().size()` and list available calendars first. |
| No output for work weeks | The selected calendar has no custom work weeks (uses default) | Use the default calendar (`project.getDefaultCalendar()`) or create a work week programmatically. |
| Date format looks odd | `System.out.println` uses default `java.util.Date` format | Apply a `SimpleDateFormat` to format dates as needed. |

## Frequently Asked Questions

**Q: क्या मैं Aspose.Tasks for Java का उपयोग करके वर्क‑वीक जानकारी को संशोधित कर सकता हूँ?**  
A: हाँ। API `addWorkWeek()`, `removeWorkWeek()` और प्रॉपर्टी सेटर्स जैसे मेथड्स प्रदान करता है जिससे नाम, तिथियां और कार्य समय बदले जा सकते हैं।

**Q: क्या Aspose.Tasks विभिन्न संस्करणों की Microsoft Project फ़ाइलों के साथ संगत है?**  
A: बिल्कुल। यह Project 98 से लेकर नवीनतम संस्करणों तक के MPP फ़ाइलों और Project XML फ़ाइलों को सपोर्ट करता है।

**Q: क्या मैं Aspose.Tasks को अन्य Java फ्रेमवर्क्स के साथ इंटीग्रेट कर सकता हूँ?**  
A: हाँ। लाइब्रेरी शुद्ध Java है, इसलिए आप इसे Spring, Jakarta EE या किसी भी अन्य फ्रेमवर्क के साथ उपयोग कर सकते हैं।

**Q: क्या Aspose.Tasks के लिए ट्रायल संस्करण उपलब्ध है?**  
A: हाँ, आप आधिकारिक साइट से 30‑दिन का फ्री ट्रायल डाउनलोड कर सकते हैं: [Aspose.Tasks trial](https://releases.aspose.com/).

**Q: Aspose.Tasks के लिए सपोर्ट कहाँ मिल सकता है?**  
A: सबसे अच्छा स्थान Aspose कम्युनिटी फ़ोरम है: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Conclusion
आपने अब **Java से Workweeks पढ़ना** Aspose.Tasks का उपयोग करके पूरी तरह समझ लिया है। ऊपर दिए गए चरणों का पालन करके आप किसी भी MS Project कैलेंडर से प्रोग्रामेटिकली वर्क‑वीक डिफिनिशन निकाल सकते हैं, इस डेटा को अपने एप्लिकेशन में इंटीग्रेट कर सकते हैं, और शेड्यूल‑संबंधित वर्कफ़्लोज़ को ऑटोमेट कर सकते हैं। वर्क‑वीक बनाना या अपडेट करना भी आज़माएँ—Aspose.Tasks इसे सरल बनाता है।

---

**Last Updated:** 2026-02-05  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}