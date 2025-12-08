---
date: 2025-12-05
description: Aspose.Tasks for Java का उपयोग करके MS Project कैलेंडरों से कार्य घंटे
  निकालकर कार्य दिवस निर्धारित करने और कार्य अवधि की गणना करना सीखें।
language: hi
linktitle: Determine Working Days & Working Hours with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks के साथ कार्य दिवस और कार्य घंटे निर्धारित करें
url: /java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks के साथ कार्य दिवस और कार्य घंटे निर्धारित करें

## परिचय
प्रोजेक्ट कैलेंडर का प्रबंधन सफल प्रोजेक्ट योजना का एक मुख्य हिस्सा है। इस ट्यूटोरियल में आप Aspose.Tasks for Java का उपयोग करके किसी भी टास्क के लिए **कार्य दिवस निर्धारित** करेंगे और MS Project कैलेंडर से **कार्य घंटे निकालेंगे**। गाइड के अंत तक आप **टास्क की अवधि की गणना**, कार्य घंटों को कस्टमाइज़, और आवश्यक डेटा प्राप्त करने के लिए **MPP फ़ाइल लोड** करने में सक्षम होंगे।

## त्वरित उत्तर
- **“कार्य दिवस निर्धारित” का क्या अर्थ है?** यह किसी टास्क के लिए कौन से कैलेंडर तिथियों को कार्य‑दिवस माना जाता है, इसे पहचानना है।  
- **मैं कौन सी लाइब्रेरी उपयोग करूँ?** Aspose.Tasks for Java MS Project फ़ाइलों के साथ काम करने के लिए पूर्ण‑विशेषताओं वाला API प्रदान करता है।  
- **इम्प्लीमेंटेशन में कितना समय लगता है?** आधारभूत एक्सट्रैक्शन के लिए सामान्यतः 10–15 मिनट।  
- **क्या मुझे लाइसेंस चाहिए?** एक मुफ्त ट्रायल उपलब्ध है; प्रोडक्शन उपयोग के लिए व्यावसायिक लाइसेंस आवश्यक है।  
- **क्या मैं कार्य घंटों को कस्टमाइज़ कर सकता हूँ?** हाँ – आप कैलेंडर संशोधित कर सकते हैं, छुट्टियाँ जोड़ सकते हैं, और कस्टम कार्य‑समय रेंज सेट कर सकते हैं।

## “कार्य दिवस निर्धारित” क्या है?
जब कोई टास्क शेड्यूल किया जाता है, तो प्रोजेक्ट कैलेंडर यह निर्धारित करता है कि कौन से दिन कार्य दिवस हैं और कौन से गैर‑कार्य (सप्ताहांत, छुट्टियाँ) हैं। कार्य दिवस निर्धारित करने का अर्थ है उस कैलेंडर को क्वेरी करके यह जानना कि कार्य कब हो सकता है, जो सटीक **टास्क अवधि की गणना** के लिए आवश्यक है।

## कार्य घंटे प्राप्त करने के लिए Aspose.Tasks क्यों उपयोग करें?
- **Microsoft Project की आवश्यकता नहीं** – किसी भी प्लेटफ़ॉर्म पर .MPP फ़ाइलों के साथ काम करें।  
- **पूर्ण कैलेंडर समर्थन** – डिफ़ॉल्ट, रिसोर्स, और टास्क कैलेंडर शामिल हैं।  
- **उच्च प्रदर्शन** – बड़े प्रोजेक्ट्स को तेज़ी से प्रोसेस करें।  
- **व्यापक दस्तावेज़ीकरण** – उदाहरण और API रेफ़रेंस आसानी से उपलब्ध हैं।

## पूर्वापेक्षाएँ
शुरू करने से पहले, सुनिश्चित करें कि आपके पास है:

1. **Java Development Kit (JDK)** – संस्करण 8 या उससे ऊपर।  
2. **Aspose.Tasks for Java** – नवीनतम JAR [यहाँ](https://releases.aspose.com/tasks/java/) से डाउनलोड करें।  
3. बेसिक Java प्रोग्रामिंग ज्ञान।

## पैकेज इम्पोर्ट करें
सबसे पहले, कोर Aspose.Tasks नेमस्पेस इम्पोर्ट करें:

```java
import com.aspose.tasks.*;
```

## चरण 1: MPP फ़ाइल लोड करें
अपनी प्रोजेक्ट फ़ाइल लोड करें (**load mpp file** चरण) ताकि आप उसके कैलेंडरों के साथ काम कर सकें:

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## चरण 2: टास्क और कैलेंडर जानकारी प्राप्त करें
वह टास्क चुनें जिसे आप विश्लेषण करना चाहते हैं और उसका संबंधित कैलेंडर प्राप्त करें। यहाँ हम टास्क के लिए **कार्य घंटे प्राप्त** करते हैं:

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## चरण 3: प्रारंभ और समाप्ति तिथियाँ निर्धारित करें
उस समय विंडो को सेट करें जिसके लिए आप **कार्य दिवस निर्धारित** करना चाहते हैं:

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## चरण 4: तिथियों पर इटररेट करें
टास्क की अवधि में प्रत्येक तिथि पर लूप करें। यह लूप बाद में आवश्यकता पड़ने पर **कार्य घंटों को कस्टमाइज़** करने में मदद करेगा:

```java
java.util.Calendar tempDate = calStartDate;
```

## चरण 5: अवधि की गणना करें
इटररेशन के दौरान हम जांचते हैं कि प्रत्येक दिन कार्य दिवस है या नहीं, कार्य घंटों को जोड़ते हैं, और अंत में टास्क की अवधि को मिनट, घंटे, और दिनों में गणना करते हैं:

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

## सामान्य समस्याएँ और समाधान
| समस्या | समाधान |
|-------|----------|
| **टास्क के लिए कैलेंडर `null` लौटाता है** | सुनिश्चित करें कि टास्क को वास्तव में कैलेंडर असाइन किया गया है; अन्यथा यह प्रोजेक्ट के डिफ़ॉल्ट कैलेंडर को विरासत में लेता है। |
| **छुट्टियों के कारण अवधि गलत** | जाँचें कि छुट्टियों को टास्क के कैलेंडर या प्रोजेक्ट के बेस कैलेंडर में परिभाषित किया गया है। |
| **टाइम ज़ोन मेल नहीं खाता** | `java.util.TimeZone` का उपयोग करके कैलेंडर के टाइम ज़ोन को आवश्यकतानुसार अपने सिस्टम के साथ संरेखित करें। |

## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या Aspose.Tasks for Java जटिल प्रोजेक्ट संरचनाओं को संभाल सकता है?
A: हाँ, Aspose.Tasks for Java जटिल प्रोजेक्ट संरचनाओं को संभालने के लिए व्यापक समर्थन प्रदान करता है, जिसमें टास्क, रिसोर्स, और कैलेंडर शामिल हैं।

### प्रश्न: क्या Aspose.Tasks for Java विभिन्न संस्करणों के MS Project के साथ संगत है?
A: बिल्कुल, Aspose.Tasks for Java विभिन्न संस्करणों के MS Project को सपोर्ट करता है, जिससे विभिन्न वातावरणों में संगतता सुनिश्चित होती है।

### प्रश्न: क्या मैं प्रोजेक्ट कैलेंडरों में कार्य घंटे और छुट्टियों को कस्टमाइज़ कर सकता हूँ?
A: हाँ, आप Aspose.Tasks for Java APIs का उपयोग करके अपने प्रोजेक्ट आवश्यकताओं के अनुसार कार्य घंटे और छुट्टियों को आसानी से कस्टमाइज़ कर सकते हैं।

### प्रश्न: क्या Aspose.Tasks for Java समर्थन और दस्तावेज़ीकरण प्रदान करता है?
A: हाँ, Aspose.Tasks for Java व्यापक दस्तावेज़ीकरण और समर्पित समर्थन फ़ोरम प्रदान करता है जो डेवलपर्स को इसकी सुविधाओं का प्रभावी उपयोग करने में मदद करते हैं।

### प्रश्न: क्या Aspose.Tasks for Java के लिए ट्रायल संस्करण उपलब्ध है?
A: हाँ, आप Aspose.Tasks for Java का मुफ्त ट्रायल संस्करण [यहाँ](https://releases.aspose.com/) से प्राप्त कर सकते हैं।

## निष्कर्ष
इस गाइड में हमने Aspose.Tasks for Java का उपयोग करके MS Project कैलेंडर से **कार्य दिवस निर्धारित**, **कार्य घंटे प्राप्त**, और **टास्क अवधि की गणना** कैसे की जाए, दिखाया। ऊपर दिए गए चरणों का पालन करके आप शेड्यूल विश्लेषण को स्वचालित कर सकते हैं, कैलेंडर को कस्टमाइज़ कर सकते हैं, और अपने प्रोजेक्ट प्लान को सटीक और अद्यतन रख सकते हैं।

---

**Last Updated:** 2025-12-05  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}