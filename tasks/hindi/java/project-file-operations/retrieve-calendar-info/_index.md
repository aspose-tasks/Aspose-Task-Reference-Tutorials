---
date: 2026-03-27
description: Aspose और Aspose.Tasks का उपयोग करके जावा के माध्यम से Microsoft Project
  फ़ाइलों से प्रोजेक्ट कैलेंडर विवरण निकालना सीखें। कोड उदाहरणों के साथ चरण‑दर‑चरण
  मार्गदर्शिका।
linktitle: Retrieve Calendar Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks का उपयोग करके MS Project कैलेंडर जानकारी प्राप्त करने का तरीका
url: /hi/java/project-file-operations/retrieve-calendar-info/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks का उपयोग करके MS Project कैलेंडर जानकारी प्राप्त करने का तरीका

## परिचय
इस ट्यूटोरियल में, **आप जानेंगे कि Aspose.Tasks** का उपयोग करके Microsoft Project फ़ाइलों से प्रोग्रामेटिकली कैलेंडर जानकारी कैसे प्राप्त की जाती है। कार्य दिवस, घंटे, और अपवाद जैसी कैलेंडर डेटा तक पहुंचना आवश्यक है जब आपको **प्रोजेक्ट कैलेंडर** विवरण रिपोर्टिंग, इंटीग्रेशन, या कस्टम शेड्यूलिंग लॉजिक के लिए निकालना हो। आइए प्रक्रिया को चरण‑दर‑चरण देखें, और आप देखेंगे कि **Aspose** का उपयोग करके *.mpp* फ़ाइल से यह डेटा कैसे निकाला जाता है।

## त्वरित उत्तर
- **इस ट्यूटोरियल में कौन सी लाइब्रेरी उपयोग की गई है?** Aspose.Tasks for Java.  
- **कौन सा मुख्य कीवर्ड कवर किया गया है?** *how to use aspose*.  
- **आप क्या निकाल सकते हैं?** प्रोजेक्ट कैलेंडर, जिसमें कार्य दिवस और घंटे शामिल हैं।  
- **क्या मुझे लाइसेंस चाहिए?** एक फ्री ट्रायल उपलब्ध है; प्रोडक्शन के लिए लाइसेंस आवश्यक है।  
- **कौन सा Java संस्करण समर्थित है?** Java 8 या उससे ऊपर।

## Aspose.Tasks क्या है और इसे क्यों उपयोग करें?
Aspose.Tasks एक शक्तिशाली Java API है जो डेवलपर्स को Microsoft Project फ़ाइलों को पढ़ने, लिखने और संशोधित करने की अनुमति देता है, बिना Microsoft Project के। Aspose.Tasks का उपयोग करके आप **कैसे कैलेंडर निकालें** जानकारी, शेड्यूल गणनाओं को स्वचालित करें, और प्रोजेक्ट डेटा को अन्य एंटरप्राइज़ सिस्टम्स के साथ इंटीग्रेट करें—सभी शुद्ध Java कोड से।

## प्रोजेक्ट कैलेंडर जानकारी क्यों निकालें?
प्रोजेक्ट कैलेंडर कार्य तिथियों, संसाधन आवंटनों, और कुल टाइमलाइन गणनाओं को नियंत्रित करता है। इस डेटा को निकालकर आप:
- वास्तविक कार्य शेड्यूल को दर्शाने वाली कस्टम रिपोर्टें जनरेट कर सकते हैं।  
- Microsoft Project टाइमलाइन को बाहरी सिस्टम्स (ERP, BI, आदि) के साथ सिंक्रनाइज़ कर सकते हैं।  
- प्रोग्रामेटिकली कैलेंडर सेटिंग्स बदलकर what‑if विश्लेषण कर सकते हैं।  
- **MS Project कैलेंडर** डेटा को अन्य प्लानिंग टूल्स में माइग्रेट कर सकते हैं।

## आवश्यकताएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास है:

- Java प्रोग्रामिंग का बेसिक ज्ञान।  
- आपके सिस्टम पर Java Development Kit (JDK) स्थापित हो।  
- Aspose.Tasks for Java लाइब्रेरी। आप इसे [here](https://releases.aspose.com/tasks/java/) से डाउनलोड कर सकते हैं।

## पैकेज इम्पोर्ट करें
सबसे पहले, आवश्यक Aspose.Tasks क्लासेज़ को अपने Java प्रोजेक्ट में इम्पोर्ट करें।

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```

## चरण 1: डेटा डायरेक्टरी सेट करें
उस फ़ोल्डर को परिभाषित करें जिसमें आपका *.mpp* फ़ाइल स्थित है।

```java
String dataDir = "Your Data Directory";
```

`"Your Data Directory"` को उस फ़ोल्डर के एब्सोल्यूट पाथ से बदलें जहाँ **project.mpp** मौजूद है।

## चरण 2: टाइम यूनिट्स परिभाषित करें
ऐसे कॉन्स्टैंट्स बनाएं जो आंतरिक टाइम प्रतिनिधित्व को मानव‑पठनीय घंटों में बदलने में मदद करेंगे।

```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

ये मान माइक्रोसेकंड में व्यक्त होते हैं, जो Aspose.Tasks आंतरिक रूप से टाइम स्टोर करता है।

## चरण 3: प्रोजेक्ट इंस्टेंस बनाएं
Microsoft Project फ़ाइल को एक `Project` ऑब्जेक्ट में लोड करें।

```java
Project project = new Project(dataDir + "project.mpp");
```

`Project` कंस्ट्रक्टर *.mpp* फ़ाइल को पार्स करता है और सभी प्रोजेक्ट डेटा, जिसमें कैलेंडर भी शामिल हैं, API के माध्यम से उपलब्ध कराता है।

## चरण 4: कैलेंडर जानकारी प्राप्त करें
प्रोजेक्ट में परिभाषित कैलेंडरों का संग्रह प्राप्त करें।

```java
CalendarCollection alCals = project.getCalendars();
```

एक प्रोजेक्ट में कई कैलेंडर (स्टैंडर्ड, रिसोर्स, और कस्टम) हो सकते हैं। यह संग्रह आपको प्रत्येक कैलेंडर तक पहुंच प्रदान करता है।

## चरण 5: कैलेंडरों पर इटररेट करें
हर कैलेंडर को लूप करें, उसका UID, नाम, और कार्य दिवसों के साथ संबंधित घंटे दिखाएँ।

```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        // Calendar Information
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        // Iterate Through WeekDays
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); // Time in milliseconds
            double time = ts / (OneHour); // Convert to hours
            if (wd.getDayWorking()) {
                // Display Working Days and Hours
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```

इंटीर लूप प्रत्येक `WeekDay` ऑब्जेक्ट की जाँच करता है। यदि दिन को कार्य दिवस के रूप में चिह्नित किया गया है, तो यह दिन का प्रकार (Monday, Tuesday, …) और गणना किए गए कार्य घंटे प्रिंट करता है।

## चरण 6: पूर्णता संदेश दिखाएँ
संकलन प्रक्रिया समाप्त होने का संकेत दें।

```java
System.out.println("Process completed Successfully");
```

## सामान्य समस्याएँ और समाधान
| समस्या | क्यों होती है | समाधान |
|-------|----------------|-----|
| **कोई कैलेंडर नहीं मिला** | प्रोजेक्ट फ़ाइल में कोई कस्टम कैलेंडर नहीं हो सकता। | जांचें कि *.mpp* वास्तव में कैलेंडर परिभाषित करता है या नहीं, या इसे Microsoft Project में खोलकर पुष्टि करें। |
| **गलत कार्य घंटे** | टाइम कन्वर्ज़न कॉन्स्टैंट्स विभिन्न Project संस्करण के लिए असंगत हैं। | यदि आप नए Aspose.Tasks संस्करण का उपयोग कर रहे हैं जो आंतरिक टाइम यूनिट बदलता है, तो `OneSec`, `OneMin`, `OneHour` को समायोजित करें। |
| **`NullPointerException` on `cal.getName()`** | कुछ कैलेंडर ऑब्जेक्ट null हो सकते हैं। | प्रॉपर्टीज़ एक्सेस करने से पहले null‑चेक जोड़ें (जैसा कि पहले दिखाया गया है)। |

## अक्सर पूछे जाने वाले प्रश्न

**प्र: क्या मैं Aspose.Tasks को अन्य प्रोग्रामिंग भाषाओं के साथ उपयोग कर सकता हूँ?**  
उ: हाँ, Aspose.Tasks कई प्लेटफ़ॉर्म और प्रोग्रामिंग भाषाओं को सपोर्ट करता है, जिसमें .NET, C++, Python, और Java शामिल हैं।

**प्र: क्या Aspose.Tasks के लिए फ्री ट्रायल उपलब्ध है?**  
उ: हाँ, आप एक फ्री ट्रायल संस्करण [here](https://releases.aspose.com/) से डाउनलोड कर सकते हैं।

**प्र: मैं Aspose.Tasks के लिए सपोर्ट कैसे प्राप्त करूँ?**  
उ: आप Aspose.Tasks कम्युनिटी फ़ोरम से सपोर्ट ले सकते हैं [here](https://forum.aspose.com/c/tasks/15)।

**प्र: क्या मैं Aspose.Tasks के लिए टेम्पररी लाइसेंस खरीद सकता हूँ?**  
उ: हाँ, टेम्पररी लाइसेंस [here](https://purchase.aspose.com/temporary-license/) से खरीदा जा सकता है।

**प्र: Aspose.Tasks की विस्तृत डॉक्यूमेंटेशन कहाँ मिल सकती है?**  
उ: आप डॉक्यूमेंटेशन [here](https://reference.aspose.com/tasks/java/) में देख सकते हैं।

## निष्कर्ष
इन चरणों का पालन करके, **आप अब जानते हैं कि Aspose.Tasks का उपयोग करके Java में MS Project फ़ाइल से प्रोजेक्ट कैलेंडर** जानकारी कैसे निकाली जाए। आप इस लॉजिक को बड़े एप्लिकेशन में इंटीग्रेट कर सकते हैं, रिपोर्टिंग को स्वचालित कर सकते हैं, या शेड्यूल को अन्य एंटरप्राइज़ सिस्टम्स के साथ सिंक्रनाइज़ कर सकते हैं। याद रखें, **how to use aspose** में महारत हासिल करने से आप कई उन्नत प्रोजेक्ट‑मैनेजमेंट ऑटोमेशन परिदृश्यों के द्वार खोलते हैं।

---

**अंतिम अपडेट:** 2026-03-27  
**टेस्टेड विथ:** Aspose.Tasks for Java 24.12 (लेखन के समय नवीनतम)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}