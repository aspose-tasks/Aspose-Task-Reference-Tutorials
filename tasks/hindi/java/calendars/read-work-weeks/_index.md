---
date: 2025-12-03
description: Aspose.Tasks का उपयोग करके Microsoft Project कैलेंडर से कार्य‑सप्ताह
  Java को पढ़ना सीखें। पूर्ण कोड उदाहरणों के साथ चरण‑दर‑चरण मार्गदर्शिका का पालन करें।
linktitle: Read Work Weeks from Calendar with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: MS प्रोजेक्ट कैलेंडर Aspose.Tasks से जावा में कार्य सप्ताह पढ़ें
url: /hi/java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS प्रोजेक्ट कैलेंडर Aspose.Tasks से वर्क वीक जावा पढ़ें

## परिचय
इस ट्यूटोरियल में आप **वर्क वीक जावा पढ़ेंगे** Microsoft Project कैलेंडर से Aspose.Tasks लाइब्रेरी का उपयोग करके। चाहे आप रिपोर्टिंग टूल बना रहे हों, शेड्यूल सिंक्रनाइज़ कर रहे हों, या प्रोजेक्ट डेटा एक्सट्रैक्शन को ऑटोमेट कर रहे हों, प्रोग्रामेटिक रूप से वर्क‑वीक परिभाषाओं तक पहुंचना अनगिनत मैन्युअल घंटे बचाता है। हम आवश्यक सेटअप दिखाएंगे, वर्क‑वीक विवरण प्राप्त करने के लिए सटीक कोड प्रदान करेंगे, और प्रत्येक चरण को समझाएंगे ताकि आप इस समाधान को अपने प्रोजेक्ट्स में अनुकूलित कर सकें।

## त्वरित उत्तर
- **“read work weeks java” का क्या अर्थ है?** यह Java कोड का उपयोग करके प्रोजेक्ट फ़ाइल से वर्क‑वीक परिभाषाएँ निकालने को दर्शाता है।  
- **कौन सी लाइब्रेरी आवश्यक है?** Aspose.Tasks for Java (फ्री ट्रायल उपलब्ध)।  
- **क्या विकास के लिए लाइसेंस चाहिए?** टेस्टिंग के लिए ट्रायल चलती है; प्रोडक्शन के लिए कमर्शियल लाइसेंस आवश्यक है।  
- **कौन से फ़ाइल फ़ॉर्मेट समर्थित हैं?** *.mpp* और Project XML फ़ाइलें दोनों संभाली जाती हैं।  
- **इम्प्लीमेंटेशन में कितना समय लगेगा?** लाइब्रेरी सेटअप हो जाने पर आमतौर पर 10 मिनट से कम।

## “read work weeks java” क्या है?
Java में वर्क वीक पढ़ना Aspose.Tasks API का उपयोग करके Microsoft Project फ़ाइल के भीतर कैलेंडर ऑब्जेक्ट की `WorkWeekCollection` तक पहुंचना है। प्रत्येक `WorkWeek` में शुरू/समाप्ति तिथियाँ और दैनिक कार्य‑समय परिभाषाएँ होती हैं जो संसाधनों की शेड्यूलिंग को निर्धारित करती हैं।

## Microsoft Project कैलेंडर से वर्क वीक जावा पढ़ने के कारण
- **ऑटोमेशन:** शेड्यूल डेटा की मैन्युअल कॉपी‑पेस्ट को समाप्त करें।  
- **इंटीग्रेशन:** वर्क‑वीक जानकारी को ERP, HR, या कस्टम रिपोर्टिंग सिस्टम में फ़ीड करें।  
- **कंसिस्टेंसी:** सुनिश्चित करें कि सभी डाउनस्ट्रीम टूल्स प्रोजेक्ट फ़ाइल में परिभाषित समान कैलेंडर नियमों का पालन करें।

## पूर्वापेक्षाएँ
कोड में जाने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित हों:

1. **Java Development Kit (JDK)** – संस्करण 8 या बाद का स्थापित हो।  
2. **Aspose.Tasks for Java** – आधिकारिक साइट से नवीनतम JAR डाउनलोड करें: [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
3. एक **सैंपल प्रोजेक्ट फ़ाइल** (`ReadWorkWeeksInformation.mpp`) जिसे आप किसी ज्ञात फ़ोल्डर में रखें।

## पैकेज इम्पोर्ट करें
कैलेंडर और वर्क वीक के साथ इंटरैक्ट करने के लिए आवश्यक क्लासेज़ को इम्पोर्ट करें:

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```

## चरण 1: डेटा डायरेक्टरी सेट करें
`.mpp` फ़ाइल वाले फ़ोल्डर को परिभाषित करें। प्लेसहोल्डर को अपने मशीन पर वास्तविक पाथ से बदलें:

```java
String dataDir = "Your Data Directory";
```

## चरण 2: प्रोजेक्ट इंस्टेंस बनाएं और कैलेंडर एक्सेस करें
`Project` ऑब्जेक्ट को इंस्टैंशिएट करें, इच्छित कैलेंडर (UID द्वारा) चुनें, और उसकी `WorkWeekCollection` प्राप्त करें:

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **प्रो टिप:** यदि आपको कैलेंडर UID का पता नहीं है, तो `project.getCalendars()` पर इटररेट करके प्रत्येक कैलेंडर का नाम और UID प्रिंट कर सकते हैं।

## चरण 3: वर्क वीक पर इटररेट करें
प्रत्येक `WorkWeek` को लूप करके उसका नाम, शुरू/समाप्ति तिथि, और दैनिक कार्य समय प्रदर्शित करें:

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

**आपको जो दिखेगा:** कंसोल प्रत्येक वर्क‑वीक का लेबल (जैसे “Standard”), उसकी प्रभावी तिथि रेंज, और प्रत्येक दिन के सटीक कार्य घंटे दिखाएगा।

## सामान्य समस्याएँ और समाधान
| समस्या | कारण | समाधान |
|-------|--------|-----|
| `NullPointerException` जब `calendar` एक्सेस किया जाता है | गलत UID या कैलेंडर मौजूद नहीं है | `project.getCalendars().size()` से UID सत्यापित करें और उपलब्ध कैलेंडर सूचीबद्ध करें। |
| वर्क वीक के लिए कोई आउटपुट नहीं | चयनित कैलेंडर में कस्टम वर्क वीक नहीं हैं (डिफ़ॉल्ट उपयोग करता है) | डिफ़ॉल्ट कैलेंडर (`project.getDefaultCalendar()`) उपयोग करें या प्रोग्रामेटिक रूप से वर्क वीक बनाएं। |
| डेट फ़ॉर्मेट अजीब दिख रहा है | `System.out.println` डिफ़ॉल्ट `java.util.Date` फ़ॉर्मेट उपयोग करता है | आवश्यकतानुसार `SimpleDateFormat` लागू करके तिथियों को फ़ॉर्मेट करें। |

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या मैं Aspose.Tasks for Java का उपयोग करके वर्क वीक जानकारी को संशोधित कर सकता हूँ?**  
उत्तर: हाँ। API `addWorkWeek()`, `removeWorkWeek()` और प्रॉपर्टी सेटर्स जैसे मेथड्स प्रदान करता है जिससे नाम, तिथियाँ और कार्य समय बदले जा सकते हैं।

**प्रश्न: क्या Aspose.Tasks विभिन्न संस्करणों की Microsoft Project फ़ाइलों के साथ संगत है?**  
उत्तर: बिल्कुल। यह Project 98 से लेकर नवीनतम संस्करणों तक के MPP फ़ाइलों और Project XML फ़ाइलों को सपोर्ट करता है।

**प्रश्न: क्या मैं Aspose.Tasks को अन्य Java फ्रेमवर्क्स के साथ इंटीग्रेट कर सकता हूँ?**  
उत्तर: हाँ। लाइब्रेरी शुद्ध Java है, इसलिए इसे Spring, Jakarta EE या किसी भी अन्य फ्रेमवर्क के साथ उपयोग किया जा सकता है।

**प्रश्न: क्या Aspose.Tasks का ट्रायल संस्करण उपलब्ध है?**  
उत्तर: हाँ, आप आधिकारिक साइट से 30‑दिन का फ्री ट्रायल डाउनलोड कर सकते हैं: [Aspose.Tasks trial](https://releases.aspose.com/).

**प्रश्न: Aspose.Tasks के लिए सपोर्ट कहाँ मिल सकता है?**  
उत्तर: Aspose कम्युनिटी फ़ोरम सबसे अच्छा स्थान है: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## निष्कर्ष
आपने अब **वर्क वीक जावा पढ़ना** Aspose.Tasks के साथ महारत हासिल कर ली है। ऊपर बताए गए चरणों का पालन करके आप किसी भी MS Project कैलेंडर से प्रोग्रामेटिक रूप से वर्क‑वीक परिभाषाएँ निकाल सकते हैं, इस डेटा को अपने एप्लिकेशन में इंटीग्रेट कर सकते हैं, और शेड्यूल‑संबंधी वर्कफ़्लो को ऑटोमेट कर सकते हैं। वर्क वीक बनाना या अपडेट करना आज़माएँ—Aspose.Tasks इसे सरल बनाता है।

---

**अंतिम अपडेट:** 2025-12-03  
**टेस्टेड विथ:** Aspose.Tasks for Java 24.12 (लेखन समय पर नवीनतम)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}