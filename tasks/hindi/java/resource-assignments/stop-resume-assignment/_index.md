---
date: 2026-01-10
description: इस चरण‑दर‑चरण ट्यूटोरियल के साथ Aspose.Tasks for Java में असाइनमेंट रोकना,
  संसाधन असाइनमेंट प्रबंधित करना और एक संसाधन असाइनमेंट उदाहरण देखना सीखें।
linktitle: Stop and Resume Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks में असाइनमेंट को रोकने और संसाधन असाइनमेंट को पुनः शुरू करने का
  तरीका
url: /hi/java/resource-assignments/stop-resume-assignment/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में असाइनमेंट को रोकना और रिसोर्स असाइनमेंट को फिर से शुरू करना

## परिचय
इस ट्यूटोरियल में, **आप सीखेंगे कि असाइनमेंट को कैसे रोकें** और बाद में इसे Aspose.Tasks for Java का उपयोग करके फिर से शुरू करें। Aspose.Tasks एक शक्तिशाली Java API है जो आपको प्रोजेक्ट फ़ाइलों को पढ़ने, Microsoft Project डेटा को संशोधित करने, और Microsoft Project स्थापित किए बिना रिसोर्स असाइनमेंट को प्रबंधित करने की अनुमति देता है। हम प्रत्येक चरण को विस्तार से देखेंगे, समझाएंगे कि प्रत्येक पंक्ति क्यों महत्वपूर्ण है, और आपको व्यावहारिक टिप्स देंगे जिन्हें आप वास्तविक प्रोजेक्ट्स में लागू कर सकते हैं।

## त्वरित उत्तर
- **“stop assignment” का क्या अर्थ है?** यह एक रिसोर्स असाइनमेंट को एक विशिष्ट स्टॉप डेट से अस्थायी रूप से निष्क्रिय के रूप में चिह्नित करता है।  
- **क्या मैं बाद में उसी असाइनमेंट को फिर से शुरू कर सकता हूँ?** हाँ, उसी असाइनमेंट पर एक रिज्यूम डेट सेट करके।  
- **क्या इस API का उपयोग करने के लिए Microsoft Project आवश्यक है?** नहीं, Aspose.Tasks Microsoft Project से स्वतंत्र रूप से काम करता है।  
- **Java का कौन सा संस्करण आवश्यक है?** Java 8 या उससे ऊपर की सिफारिश की जाती है।  
- **लाइब्रेरी कहाँ से डाउनलोड कर सकते हैं?** आधिकारिक Aspose.Tasks Java डाउनलोड पेज से।

## Aspose.Tasks के संदर्भ में “how to stop assignment” क्या है?
एक असाइनमेंट को रोकना शेड्यूलर को बताता है कि **स्टॉप डेट** के बाद रिसोर्स को आवंटित कार्य को **रिज्यूम डेट** (यदि हो) तक नजरअंदाज करे। यह छुट्टियों, उपकरण के डाउनटाइम, या किसी भी अवधि को संभालने में उपयोगी है जब रिसोर्स को सक्रिय नहीं माना जाना चाहिए।

## रिसोर्स असाइनमेंट को प्रबंधित करने के लिए Aspose.Tasks क्यों उपयोग करें?
- **Microsoft Project की आवश्यकता नहीं** – .mpp फ़ाइलों के साथ सीधे काम करें।  
- **तिथियों पर पूर्ण नियंत्रण** – आप प्रोग्रामेटिक रूप से स्टॉप डेट, रिज्यूम डेट की जाँच कर सकते हैं और उन्हें समायोजित कर सकते हैं।  
- **क्रॉस‑प्लेटफ़ॉर्म** – किसी भी OS पर चलाएँ जो Java को सपोर्ट करता है।  
- **समृद्ध API** – एक *resource assignment example* प्रदान करता है जिसे आप कस्टम रिपोर्टिंग के लिए विस्तारित कर सकते हैं।

## पूर्वापेक्षाएँ
शुरू करने से पहले सुनिश्चित करें कि आपके पास है:

- अपने सिस्टम पर Java Development Kit (JDK) स्थापित हो।  
- Aspose.Tasks for Java लाइब्रेरी डाउनलोड की हुई हो। आप इसे [here](https://releases.aspose.com/tasks/java/) से डाउनलोड कर सकते हैं।  
- Java प्रोग्रामिंग की बुनियादी समझ हो।  

## पैकेज इम्पोर्ट करें
पहले, अपने Java प्रोजेक्ट में आवश्यक पैकेज इम्पोर्ट करें:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```

## चरण 1: प्रोजेक्ट फ़ाइल लोड करें
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Load the project file
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```

यहाँ हम **प्रोजेक्ट फ़ाइल Java** फ़ॉर्मेट (`.mpp`) को पढ़ते हैं और एक `Project` ऑब्जेक्ट बनाते हैं जो हमें सभी प्रोजेक्ट डेटा, जिसमें रिसोर्स असाइनमेंट शामिल हैं, तक पहुँच प्रदान करता है।

## चरण 2: रिसोर्स असाइनमेंट्स पर इटरेट करें
```java
// Define minimum date
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iterate through resource assignments
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```

हम **minimum date** सेट करते हैं ताकि प्लेसहोल्डर डेट्स को फ़िल्टर किया जा सके और फिर प्रत्येक असाइनमेंट पर लूप चलाते हैं। यह वह सामान्य *resource assignment example* पैटर्न है जिसका उपयोग तब किया जाता है जब आपको असाइनमेंट्स का निरीक्षण या संशोधन करना हो।

## चरण 3: स्टॉप और रिज्यूम डेट्स की जाँच करें
```java
    // Check stop date
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    // Check resume date
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```

इस ब्लॉक में हम प्रत्येक असाइनमेंट के लिए **स्टॉप डेट** और **रिज्यूम डेट** की जाँच करते हैं। यदि डेट हमारे `minDate` से पहले है, तो हम इसे सेट नहीं किया हुआ मानते हैं (`"NA"`); अन्यथा हम वास्तविक डेट प्रिंट करते हैं। यह लॉजिक **रिसोर्स असाइनमेंट को सही ढंग से प्रबंधित** करने के लिए आवश्यक है।

## सामान्य समस्याएँ और समाधान
- **Null डेट्स** – `ra.get(Asn.STOP)` `null` लौट सकता है। `.before(minDate)` कॉल करने से पहले null चेक जोड़कर इसे रोकें।  
- **गलत फ़ाइल पाथ** – सुनिश्चित करें कि `dataDir` आपके OS के अनुसार एक पाथ सेपरेटर (`/` या `\\`) के साथ समाप्त हो।  
- **वर्ज़न मिसमैच** – लापता enum वैल्यूज़ से बचने के लिए नवीनतम Aspose.Tasks for Java संस्करण का उपयोग करें।

## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं Microsoft Project स्थापित किए बिना Aspose.Tasks का उपयोग कर सकता हूँ?
हाँ, Aspose.Tasks आपको Microsoft Project फ़ाइलों के साथ काम करने की अनुमति देता है बिना आपके सिस्टम पर Microsoft Project स्थापित किए।

### और अधिक दस्तावेज़ कहाँ मिल सकते हैं?
आप विस्तृत दस्तावेज़ीकरण [here](https://reference.aspose.com/tasks/java/) पर पा सकते हैं।

### क्या कोई फ्री ट्रायल उपलब्ध है?
हाँ, आप फ्री ट्रायल [here](https://releases.aspose.com/) से प्राप्त कर सकते हैं।

### यदि मुझे कोई समस्या आती है तो मैं समर्थन कैसे प्राप्त कर सकता हूँ?
आप समुदाय से समर्थन [here](https://forum.aspose.com/c/tasks/15) पर प्राप्त कर सकते हैं।

### क्या मैं एक अस्थायी लाइसेंस खरीद सकता हूँ?
हाँ, आप एक अस्थायी लाइसेंस [here](https://purchase.aspose.com/temporary-license/) से खरीद सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

**Q: मैं प्रोग्रामेटिक रूप से असाइनमेंट के लिए स्टॉप डेट कैसे सेट करूँ?**  
A: `ra.set(Asn.STOP, yourDateObject);` का उपयोग करें जहाँ `yourDateObject` एक `java.util.Date` है।

**Q: यदि रिज्यूम डेट स्टॉप डेट से पहले हो तो क्या होता है?**  
A: API कालक्रमिक क्रम लागू नहीं करता; हालांकि, शेड्यूलर असाइनमेंट को केवल दोनों डेट्स में से बाद की डेट के बाद सक्रिय मानता है, इसलिए आपको स्वयं डेट्स को वैलिडेट करना चाहिए।

**Q: क्या मैं केवल उन असाइनमेंट्स को फ़िल्टर कर सकता हूँ जिनमें स्टॉप डेट सेट है?**  
A: हाँ, `prj.getResourceAssignments()` पर इटरेट करें और `ra.get(Asn.STOP) != null` की जाँच करें।

**Q: क्या सेट होने के बाद स्टॉप डेट को हटाना संभव है?**  
A: `ra.set(Asn.STOP, null);` के साथ स्टॉप डेट को `null` सेट करें और फिर प्रोजेक्ट को सेव करें।

**Q: क्या Aspose.Tasks अन्य डेट‑संबंधित फ़ील्ड जैसे start, finish, या actual start को सपोर्ट करता है?**  
A: बिल्कुल। `Asn` enum सभी असाइनमेंट फ़ील्ड्स के लिए कॉन्स्टेंट्स प्रदान करता है, जैसे `Asn.START`, `Asn.FINISH` आदि।

## निष्कर्ष
इन चरणों का पालन करके आप अब **असाइनमेंट को कैसे रोकें** जानते हैं, स्टॉप/रिज्यूम डेट्स की जाँच कर सकते हैं, और आवश्यकता पड़ने पर असाइनमेंट को फिर से शुरू कर सकते हैं। यह क्षमता आपको **रिसोर्स असाइनमेंट को** अधिक सटीकता से प्रबंधित करने देती है, विशेषकर रिसोर्स की छुट्टियों या उपकरण के डाउनटाइम जैसे परिदृश्यों में। आप उदाहरण को डेट्स अपडेट करने, रिपोर्ट जनरेट करने, या अपने स्वयं के शेड्यूलिंग लॉजिक के साथ इंटीग्रेट करने के लिए स्वतंत्र हैं।

---

**अंतिम अपडेट:** 2026-01-10  
**परीक्षित संस्करण:** Aspose.Tasks for Java 24.12  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}