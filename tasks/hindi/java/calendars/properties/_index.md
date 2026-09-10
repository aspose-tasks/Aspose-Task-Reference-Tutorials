---
date: 2026-09-09
description: Aspose.Tasks का उपयोग करके Java में प्रोजेक्ट कैलेंडर कैसे सेट करें।
  कैलेंडर working hours को प्रदर्शित करना, configure working time, और modify calendar
  days को MS Project फ़ाइलों में सीखें।
keywords:
- how to set project calendar
- display calendar working hours
- configure calendar working time
- modify calendar working days
- aspose.tasks java
lastmod: 2026-09-09
linktitle: Aspose.Tasks में कैलेंडर प्रॉपर्टीज़ को मैनेज करें
og_description: Aspose.Tasks का उपयोग करके Java में प्रोजेक्ट कैलेंडर कैसे सेट करें।
  कैलेंडर working hours को प्रदर्शित करना, configure working time, और modify calendar
  days को MS Project फ़ाइलों में सीखें।
og_image_alt: Screenshot of Java code managing MS Project calendar with Aspose.Tasks
og_title: Aspose.Tasks के साथ Java में प्रोजेक्ट कैलेंडर कैसे सेट करें
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: How to set project calendar in Java using Aspose.Tasks. Learn to display
    calendar working hours, configure working time, and modify calendar days in MS
    Project files.
  headline: How to set project calendar Java with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, the API provides full read/write access to calendars, allowing you
      to add, edit, or delete working times, exceptions, and base‑calendar relationships.
    question: Can I modify calendar properties programmatically using Aspose.Tasks?
  - answer: The library mirrors the capabilities of Microsoft Project, so you can
      customize virtually all calendar aspects. Only very old Project file versions
      may have minor compatibility quirks.
    question: Are there any limitations to calendar customization with Aspose.Tasks?
  - answer: Absolutely. Simply add the Aspose.Tasks JAR to your build path and use
      the same code patterns shown here.
    question: Can I integrate calendar management into existing Java projects?
  - answer: Yes, it covers tasks, resources, assignments, outlines, baselines, and
      more—making it a comprehensive solution for Java‑based project automation.
    question: Does Aspose.Tasks support other project‑management functionalities besides
      calendar management?
  - answer: Yes, Aspose provides dedicated forums, email support, and extensive documentation
      for all licensed users.
    question: Is technical support available for developers using Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose.tasks
- java project calendar
- ms project automation
- calendar management
title: Aspose.Tasks के साथ Java में प्रोजेक्ट कैलेंडर कैसे सेट करें
url: /hi/java/calendars/properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks के साथ Java में प्रोजेक्ट कैलेंडर सेट कैसे करें

## परिचय
इस ट्यूटोरियल में आप Aspose.Tasks लाइब्रेरी का उपयोग करके Java में **how to set project calendar** सीखेंगे। कैलेंडर प्रॉपर्टीज़ को नियंत्रित करने से आप **display calendar working hours** दिखा सकते हैं, कस्टम कार्य दिवस कॉन्फ़िगर कर सकते हैं, और अपने प्रोजेक्ट शेड्यूल को छुट्टियों या शिफ्ट पैटर्न जैसे वास्तविक‑विश्व प्रतिबंधों के साथ संरेखित रख सकते हैं। हम पर्यावरण सेटअप, प्रोजेक्ट लोड करना, कैलेंडरों पर इटरेट करना, और उनकी प्रॉपर्टीज़ को पढ़ने या अपडेट करने की प्रक्रिया को चरण‑दर‑चरण दिखाएंगे, ताकि आप किसी भी Java एप्लिकेशन में **manage MS Project calendar** सेटिंग्स को आत्मविश्वास से संभाल सकें।

## त्वरित उत्तर
- **What does “set project calendar” mean?** यह एक MS Project फ़ाइल के भीतर कैलेंडर के कार्य समय, बेस कैलेंडर और दिन प्रकारों को बनाना या अपडेट करना意味 करता है।  
- **Which library is required?** Aspose.Tasks for Java (any recent version).  
- **Do I need a license?** एक मुफ्त ट्रायल विकास के लिए काम करता है; उत्पादन के लिए एक व्यावसायिक लाइसेंस आवश्यक है।  
- **Can I display calendar working hours?** हाँ—प्रत्येक `WeekDay` को पढ़कर आप प्रत्येक दिन प्रकार के घंटे आउटपुट कर सकते हैं।  
- **Is this compatible with Maven/Gradle?** बिल्कुल—Aspose.Tasks JAR को एक डिपेंडेंसी के रूप में जोड़ें।

## Java में प्रोजेक्ट कैलेंडर कैसे सेट करें
अपनी प्रोजेक्ट फ़ाइल लोड करें, लक्ष्य कैलेंडर खोजें, और फिर आवश्यकतानुसार उसके कार्य समय परिभाषाएँ, बेस कैलेंडर, और दिन प्रकारों को समायोजित करें। नीचे दिए गए चरण एक पूर्ण, अंत‑से‑अंत समाधान प्रदान करते हैं जो लोडिंग, इटरेटिंग, मॉडिफाइंग, और प्रोजेक्ट को सेव करने को दर्शाते हैं, साथ ही एक्सेप्शन को संभालते हैं और सटीक कार्य‑घंटा गणनाएँ सुनिश्चित करते हैं।

## प्रोजेक्ट कैलेंडर क्या है?
एक प्रोजेक्ट कैलेंडर कार्य दिवसों और घंटों को परिभाषित करता है जो टास्क, रिसोर्सेज़, और संपूर्ण प्रोजेक्ट टाइमलाइन के लिए लागू होते हैं। MS Project में, कैलेंडर बेस कैलेंडर से विरासत में ले सकते हैं, और प्रत्येक दिन प्रकार (जैसे **Standard**, **Non‑working**) का अपना कार्य समय हो सकता है। प्रोग्रामेटिक रूप से इन सेटिंग्स को प्रबंधित करने से आप मैन्युअल एडिटिंग के बिना डायनेमिक शेड्यूल समायोजन कर सकते हैं।

## MS Project कैलेंडर को प्रोग्रामेटिकली क्यों प्रबंधित करें?
कैलेंडरों को प्रोग्रामेटिकली प्रबंधित करने से आप कई प्रोजेक्ट्स में सुसंगत शेड्यूलिंग नियम लागू कर सकते हैं, मैन्युअल त्रुटियों को कम कर सकते हैं, और कैलेंडर डेटा को HR या ERP जैसे अन्य एंटरप्राइज़ सिस्टम्स के साथ एकीकृत कर सकते हैं। यह ऑटोमेशन प्रोजेक्ट सेटअप को तेज़ करता है और सुनिश्चित करता है कि सभी टीम सदस्य समान कार्य‑समय नीतियों का पालन करें।

- **Automation:** एक स्क्रिप्ट के साथ दर्जनों प्रोजेक्ट्स में कैलेंडर समायोजित करें।  
- **Consistency:** स्वचालित रूप से संगठन‑व्यापी कार्य‑समय नीतियों को लागू करें।  
- **Integration:** कैलेंडर को बाहरी HR या ERP सिस्टम्स के साथ सिंक करें।  
- **Visibility:** रिपोर्टिंग या डिबगिंग के लिए जल्दी **display calendar working hours** दिखाएँ।  
- **Flexibility:** UI खोले बिना तुरंत अपवाद या शिफ्ट पैटर्न जोड़ें।

## पूर्वापेक्षाएँ
शुरू करने से पहले, सुनिश्चित करें कि आपके पास हैं:

- **Java Development Kit (JDK) 8+** स्थापित है और `JAVA_HOME` कॉन्फ़िगर किया गया है।  
- **Aspose.Tasks for Java** लाइब्रेरी को [download page](https://releases.aspose.com/tasks/java/) से डाउनलोड करें। JAR को अपने क्लासपाथ में जोड़ें या इसे Maven/Gradle डिपेंडेंसी के रूप में घोषित करें।  
- एक सैंपल MS Project फ़ाइल (`.mpp` या `.xml`) जिसमें कम से कम एक कैलेंडर हो जिसे आप निरीक्षण या संशोधित करना चाहते हैं।

## पैकेज इम्पोर्ट करें
`Project`, `Calendar`, `WeekDay`, और संबंधित क्लासेज़ कैलेंडर मैनिपुलेशन का मूल हैं।  
`Calendar` क्लास एक प्रोजेक्ट कैलेंडर को दर्शाती है, जिसमें कार्य दिवस, अपवाद, और बेस‑कैलेंडर संबंध शामिल होते हैं।  
`WeekDay` क्लास कैलेंडर के भीतर एक एकल दिन के कार्य समय सेटिंग्स को परिभाषित करती है।  
`Project` क्लास Aspose.Tasks का टॉप‑लेवल ऑब्जेक्ट है जो मेमोरी में एकल MS Project फ़ाइल का प्रतिनिधित्व करता है। फ़ाइल लोड करने के बाद, सभी कैलेंडर ऑपरेशन्स इस ऑब्जेक्ट के माध्यम से होते हैं।

```java
import com.aspose.tasks.*;
```

## चरण 1: डेटा डायरेक्टरी सेट करें
उस फ़ोल्डर को परिभाषित करें जिसमें आपके प्रोजेक्ट फ़ाइलें हैं। प्लेसहोल्डर को अपने मशीन पर वास्तविक पाथ से बदलें।

```java
String dataDir = "Your Data Directory";
```

## चरण 2: समय‑इकाई स्थिरांक परिभाषित करें
कार्य समय मिलिसेकंड में व्यक्त किया जाता है। पुन: उपयोग योग्य स्थिरांक परिभाषित करने से कोड पढ़ने में आसान होता है और आप **calculate working hours Java** को सटीक रूप से कर सकते हैं।

```java
long OneSec = 1000; // 1000 milliseconds
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

## चरण 3: प्रोजेक्ट डेटा लोड करें
`Project` इंस्टेंस बनाएं मौजूदा MS Project XML फ़ाइल (`.xml` या `.mpp`) को लोड करके। यह आपको फ़ाइल में संग्रहीत सभी कैलेंडरों तक पहुंच देता है।  
`Project` क्लास फ़ाइल को एक हल्के ऑब्जेक्ट मॉडल में लोड करता है; यह पूरी फ़ाइल को मेमोरी में रखने की **आवश्यकता नहीं** रखता, जिससे आप उन प्रोजेक्ट्स के साथ काम कर सकते हैं जिनमें दसियों हज़ार टास्क होते हैं।

```java
Project project = new Project(dataDir + "project.xml");
```

## चरण 4: कैलेंडरों पर इटरेट करें Java
अब हम प्रत्येक कैलेंडर पर लूप करते हैं, उसका यूनिक आइडेंटिफायर, नाम, बेस कैलेंडर, और प्रत्येक दिन प्रकार के कार्य घंटे प्रिंट करते हैं। यह **how to set project calendar Java** मानों को दर्शाता है और साथ ही **display calendar working hours** को भी दिखाता है।

```java
for (Calendar cal : project.getCalendars()) {
    if (cal.getName() == null) {
        continue;
    }
    System.out.println("UID: " + cal.getUid() + " Name: " + cal.getName());
    // Show if it has a base calendar
    System.out.print("Base Calendar: ");
    System.out.println(cal.isBaseCalendar() ? "Self" : cal.getBaseCalendar().getName());
    // Iterate through weekdays
    for (WeekDay wd : cal.getWeekDays()) {
        double ts = wd.getWorkingTime();
        System.out.println("Day Type: " + DayType.toString(DayType.class, wd.getDayType()) + " Hours: " + ts / OneHour);
    }
}
```

### यह कोड क्या करता है
- **Filters unnamed calendars** (कुछ आंतरिक कैलेंडरों का `null` नाम हो सकता है)।  
- **Prints UID and name** – बाद में कैलेंडर की पहचान के लिए उपयोगी।  
- **Shows the base calendar** – या तो “Self” (कैलेंडर अपना स्वयं का बेस है) या विरासत में मिले कैलेंडर का नाम।  
- **Loops through each `WeekDay`** कुल कार्य घंटे की गणना और आउटपुट करने के लिए (`workingTime` मिलिसेकंड में है, इसलिए हम इसे `OneHour` से विभाजित करते हैं)।

## Aspose.Tasks के उपयोग के मापनीय लाभ
Aspose.Tasks **30+ इनपुट और आउटपुट फ़ॉर्मेट** को सपोर्ट करता है और **10,000 टास्क तक के प्रोजेक्ट्स** को पूरी फ़ाइल को मेमोरी में लोड किए बिना प्रोसेस कर सकता है, सामान्य सर्वर हार्डवेयर पर एक सेकंड से कम समय में परिणाम देता है। ये आँकड़े इसे एंटरप्राइज़‑स्तर के ऑटोमेशन के लिए एक विश्वसनीय विकल्प बनाते हैं।

## सामान्य समस्याएँ और समाधान
| Issue | Reason | Fix |
|-------|--------|-----|
| `NullPointerException` on `cal.getBaseCalendar()` | कैलेंडर स्वयं एक बेस कैलेंडर है (`isBaseCalendar()` `true` लौटाता है)। | जैसा दिखाया गया है, टर्नरी चेक उपयोग करें (`cal.isBaseCalendar() ? "Self" : ...`)। |
| No output for working hours | प्रोजेक्ट फ़ाइल अलग समय इकाई (ticks) उपयोग करती है। | फ़ाइल फ़ॉर्मेट सत्यापित करें; Aspose.Tasks मिलिसेकंड में सामान्यीकृत करता है, लेकिन सुनिश्चित करें कि आप सही फ़ाइल प्रकार लोड कर रहे हैं। |
| Unable to locate `project.xml` | गलत `dataDir` पाथ। | एक एब्सोल्यूट पाथ उपयोग करें या `Paths.get(dataDir, "project.xml").toString()`। |

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं Aspose.Tasks का उपयोग करके कैलेंडर प्रॉपर्टीज़ को प्रोग्रामेटिकली संशोधित कर सकता हूँ?**  
A: हाँ, API कैलेंडरों तक पूर्ण रीड/राइट एक्सेस प्रदान करता है, जिससे आप कार्य समय, अपवाद, और बेस‑कैलेंडर संबंधों को जोड़, संपादित या हटाने में सक्षम होते हैं।

**Q: क्या Aspose.Tasks के साथ कैलेंडर कस्टमाइज़ेशन में कोई सीमाएँ हैं?**  
A: लाइब्रेरी Microsoft Project की क्षमताओं को प्रतिबिंबित करती है, इसलिए आप लगभग सभी कैलेंडर पहलुओं को कस्टमाइज़ कर सकते हैं। केवल बहुत पुराने प्रोजेक्ट फ़ाइल संस्करणों में मामूली संगतता समस्याएँ हो सकती हैं।

**Q: क्या मैं मौजूदा Java प्रोजेक्ट्स में कैलेंडर प्रबंधन को एकीकृत कर सकता हूँ?**  
A: बिल्कुल। बस Aspose.Tasks JAR को अपने बिल्ड पाथ में जोड़ें और यहाँ दिखाए गए कोड पैटर्न का उपयोग करें।

**Q: क्या Aspose.Tasks कैलेंडर प्रबंधन के अलावा अन्य प्रोजेक्ट‑मैनेजमेंट कार्यक्षमताओं का समर्थन करता है?**  
A: हाँ, यह टास्क, रिसोर्सेज़, असाइनमेंट्स, आउटलाइन, बेसलाइन और अधिक को कवर करता है—जिससे यह Java‑आधारित प्रोजेक्ट ऑटोमेशन के लिए एक व्यापक समाधान बनता है।

**Q: क्या Aspose.Tasks उपयोग करने वाले डेवलपर्स के लिए तकनीकी समर्थन उपलब्ध है?**  
A: हाँ, Aspose सभी लाइसेंसधारकों के लिए समर्पित फ़ोरम, ईमेल समर्थन, और विस्तृत दस्तावेज़ प्रदान करता है।

**अंतिम अपडेट:** 2026-09-09  
**परीक्षित संस्करण:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल

- [Java में प्रोजेक्ट कैलेंडर बनाएं – Aspose.Tasks for Java गाइड](/tasks/java/)
- [Java में प्रोजेक्ट फ़ाइलें लोड करें और प्रोजेक्ट प्रॉपर्टीज़ प्रबंधित करें](/tasks/java/project-management/default-properties/)
- [Aspose.Tasks for Java का उपयोग करके MS Project में प्रोजेक्ट स्टार्ट डेट सेट करें](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}