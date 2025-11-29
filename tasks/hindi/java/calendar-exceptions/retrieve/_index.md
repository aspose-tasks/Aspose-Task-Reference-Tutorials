---
date: 2025-11-29
description: Aspose.Tasks for Java का उपयोग करके MS Project से कैलेंडर अपवाद कैसे
  प्राप्त करें, सीखें। यह Aspose.Tasks Java ट्यूटोरियल चरण‑दर‑चरण कोड उदाहरण प्रदान
  करता है।
language: hi
linktitle: Retrieve Calendar Exceptions with Aspose.Tasks – asp tasks java tutorial
second_title: Aspose.Tasks Java API
title: Aspose.Tasks के साथ कैलेंडर अपवाद प्राप्त करें – ASP Tasks जावा ट्यूटोरियल
url: /java/calendar-exceptions/retrieve/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks के साथ कैलेंडर अपवाद प्राप्त करें – asp tasks java tutorial

## परिचय
इस **asp tasks java tutorial** में आप सीखेंगे कि Aspose.Tasks लाइब्रेरी फॉर जावा का उपयोग करके Microsoft Project फ़ाइल से कैलेंडर अपवाद कैसे प्राप्त किए जाते हैं। कैलेंडर अपवाद उन गैर‑कार्य अवधि को दर्शाते हैं जैसे छुट्टियाँ या कस्टम कार्य‑समय नियम, और इन्हें प्रोग्रामेटिक रूप से पढ़ना रिसोर्स‑लेवलिंग, रिपोर्टिंग और कस्टम शेड्यूलिंग लॉजिक के लिए आवश्यक है। हम पूरे प्रोसेस को चरण‑दर‑चरण समझाएंगे, ताकि आप इस क्षमता को अपने जावा एप्लिकेशन में आत्मविश्वास के साथ इंटीग्रेट कर सकें।

## त्वरित उत्तर
- **यह ट्यूटोरियल क्या कवर करता है?** Aspose.Tasks फॉर जावा का उपयोग करके MPP फ़ाइल से कैलेंडर अपवाद प्राप्त करना।  
- **इम्प्लीमेंटेशन में कितना समय लगेगा?** बेसिक सेटअप के लिए लगभग 10‑15 मिनट।  
- **पूर्वापेक्षाएँ?** JDK, Aspose.Tasks फॉर जावा, और एक IDE (IntelliJ IDEA या Eclipse)।  
- **क्या लाइसेंस चाहिए?** विकास के लिए फ्री ट्रायल चलती है; प्रोडक्शन के लिए कमर्शियल लाइसेंस आवश्यक है।  
- **समर्थित प्रोजेक्ट वर्ज़न?** सभी प्रमुख MS Project फ़ॉर्मेट (MPP, MPT, XML)।

## asp tasks java tutorial क्या है?
एक **asp tasks java tutorial** बताता है कि जावा प्रोजेक्ट्स में Aspose.Tasks API का कैसे उपयोग किया जाए। यह ठोस कोड स्निपेट्स, बेस्ट‑प्रैक्टिस एक्सप्लानेशन्स और रियल‑वर्ल्ड सीनारियो प्रदान करता है ताकि डेवलपर्स Microsoft Project इंस्टॉल किए बिना प्रोजेक्ट फ़ाइलों को मैनीपुलेट कर सकें।

## कैलेंडर अपवाद क्यों प्राप्त करें?
कैलेंडर अपवाद समझने से आप:
- ऐसे प्रोजेक्ट टाइमलाइन बना सकते हैं जो छुट्टियों और कस्टम कार्य‑शेड्यूल का सम्मान करते हैं।  
- कस्टम रिपोर्टिंग टूल बना सकते हैं जो गैर‑कार्य दिवसों को हाइलाइट करते हैं।  
- प्रोजेक्ट कैलेंडर को बाहरी सिस्टम (जैसे ERP, HR) के साथ सिंक्रनाइज़ कर सकते हैं।

## पूर्वापेक्षाएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

1. **Java Development Kit (JDK)** – सुनिश्चित करें कि आपके पास JDK 8 या बाद का संस्करण स्थापित है।  
2. **Aspose.Tasks for Java** – Aspose.Tasks for Java को [यहाँ](https://releases.aspose.com/tasks/java/) से डाउनलोड और इंस्टॉल करें।  
3. **Integrated Development Environment (IDE)** – आप अपनी पसंद का कोई भी IDE उपयोग कर सकते हैं, जैसे IntelliJ IDEA या Eclipse।

## पैकेज आयात करें
Aspose.Tasks के साथ काम करने के लिए आपको आवश्यक पैकेज आयात करने होंगे:

```java
import com.aspose.tasks.*;
```

## चरण 1: अपने डेटा डायरेक्टरी सेट करें
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

> **प्रो टिप:** `FileNotFoundException` से बचने के लिए एक एब्सोल्यूट पाथ या प्रोजेक्ट की रिसोर्सेज फ़ोल्डर के रिलेटिव पाथ का उपयोग करें।

## चरण 2: MS Project फ़ाइल लोड करें
```java
Project project = new Project(dataDir + "project.mpp");
```

यह लाइन निर्दिष्ट पाथ से MS Project फ़ाइल को लोड करके एक नया `Project` ऑब्जेक्ट इनिशियलाइज़ करती है।

## चरण 3: कैलेंडर अपवाद प्राप्त करें
```java
for (Calendar cal : project.getCalendars()) {
    for (CalendarException calExc : cal.getExceptions()) {
        System.out.println("From: " + calExc.getFromDate().toString());
        System.out.println("To: " + calExc.getToDate().toString());
    }
}
```

यहाँ हम प्रोजेक्ट के प्रत्येक कैलेंडर पर इटररेट करते हैं और फिर उस कैलेंडर के भीतर प्रत्येक कैलेंडर अपवाद पर। हम प्रत्येक अपवाद की प्रारंभ और समाप्ति तिथियों को प्रिंट करते हैं।

## सामान्य समस्याएँ और समाधान
| समस्या | कारण | समाधान |
|-------|--------|-----|
| **कोई आउटपुट नहीं प्रिंट हुआ** | प्रोजेक्ट फ़ाइल में कोई कैलेंडर अपवाद नहीं है। | MS Project में कैलेंडर के पास परिभाषित अपवाद (जैसे छुट्टियाँ) हैं या नहीं, यह सत्यापित करें। |
| **`NullPointerException`** | `dataDir` पाथ गलत है या फ़ाइल नहीं मिली। | डायरेक्टरी पाथ को दोबारा जांचें और सुनिश्चित करें कि `project.mpp` मौजूद है। |
| **Time zone mismatch** | तिथियाँ UTC में दिख रही हैं। | यदि आवश्यक हो तो `calExc.getFromDate().toLocalDateTime()` का उपयोग करके स्थानीय समय में बदलें। |

## अक्सर पूछे जाने वाले प्रश्न
### क्या Aspose.Tasks विभिन्न संस्करणों की MS Project फ़ाइलों को संभाल सकता है?
हाँ, Aspose.Tasks विभिन्न संस्करणों की MS Project फ़ाइलों को सपोर्ट करता है, जिसमें MPP, MPT और XML फ़ॉर्मेट शामिल हैं।

### क्या Aspose.Tasks के लिए फ्री ट्रायल उपलब्ध है?
हाँ, आप Aspose.Tasks का फ्री ट्रायल [यहाँ](https://releases.aspose.com/) से डाउनलोड कर सकते हैं।

### Aspose.Tasks फॉर जावा की डॉक्यूमेंटेशन कहाँ मिल सकती है?
आप डॉक्यूमेंटेशन [यहाँ](https://reference.aspose.com/tasks/java/) देख सकते हैं।

### Aspose.Tasks के लिए सपोर्ट कैसे प्राप्त करूँ?
आप कम्युनिटी फ़ोरम से सपोर्ट प्राप्त कर सकते हैं [यहाँ](https://forum.aspose.com/c/tasks/15)।

### Aspose.Tasks के लिए टेम्पररी लाइसेंस का विकल्प है क्या?
हाँ, आप टेम्पररी लाइसेंस [यहाँ](https://purchase.aspose.com/temporary-license/) से प्राप्त कर सकते हैं।

**Additional Q&A**

**Q:** *क्या मैं कैलेंडर अपवाद प्राप्त करने के बाद उन्हें संशोधित कर सकता हूँ?*  
**A:** बिल्कुल। तिथियों को बदलने के लिए `CalendarException.setFromDate()` और `setToDate()` का उपयोग करें, फिर `project.save(...)` से प्रोजेक्ट को सेव करें।

**Q:** *क्या Aspose.Tasks कैलेंडरों पर कस्टम फ़ील्ड्स को संरक्षित रखता है?*  
**A:** हाँ, सभी कस्टम फ़ील्ड्स और एक्सटेंडेड एट्रिब्यूट्स प्रोजेक्ट को लोड और सेव करने पर बरकरार रहते हैं।

## निष्कर्ष
इस **asp tasks java tutorial** में हमने Aspose.Tasks फॉर जावा का उपयोग करके MS Project से कैलेंडर अपवाद प्राप्त करना सीखा। इन सरल चरणों का पालन करके आप इस फ़ंक्शनैलिटी को अपने जावा एप्लिकेशन में सहजता से इंटीग्रेट कर सकते हैं, जिससे शेड्यूलिंग फीचर अधिक समृद्ध और प्रोजेक्ट एनालिटिक्स अधिक सटीक बनेंगे।

---

**अंतिम अपडेट:** 2025-11-29  
**परीक्षण किया गया:** Aspose.Tasks for Java 24.11  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}