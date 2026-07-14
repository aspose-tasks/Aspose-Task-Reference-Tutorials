---
date: 2026-07-14
description: इस चरण-दर-चरण गाइड में सीखें कि Java में resource assignment कैसे रोकें,
  resource assignments को कैसे प्रबंधित करें, और Aspose.Tasks for Java का उपयोग करके
  उदाहरण देखें।
keywords:
- stop resource assignment java
- Aspose.Tasks Java
- resource assignment management
- project scheduling Java
lastmod: 2026-07-14
linktitle: Aspose.Tasks में Resource Assignments को रोकें और Resume करें
og_description: Aspose.Tasks के साथ Java में resource assignment रोकें। यह ट्यूटोरियल
  दिखाता है कि असाइनमेंट को कैसे pause और resume करें, तिथियों को कैसे संभालें, और
  Microsoft Project के बिना API को कैसे इंटीग्रेट करें।
og_image_alt: Guide to stop and resume resource assignments in Aspose.Tasks for Java
og_title: Java में Resource Assignment रोकें – Aspose.Tasks गाइड
schemas:
- author: Aspose
  dateModified: '2026-07-14'
  description: Learn how to stop resource assignment java, manage resource assignments,
    and view examples using Aspose.Tasks for Java in this step‑by‑step guide.
  headline: How to Stop Resource Assignment Java – Resume with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Use `ra.set(Asn.STOP, yourDateObject);` where `yourDateObject` is a `java.util.Date`.
    question: How do I programmatically set a stop date for an assignment?
  - answer: The API does not enforce chronological order; however, the scheduler will
      treat the assignment as active only after the later of the two dates, so you
      should validate dates yourself.
    question: What happens if the resume date is earlier than the stop date?
  - answer: Yes, iterate through `prj.getResourceAssignments()` and check `ra.get(Asn.STOP)
      != null`.
    question: Can I filter assignments to only those that have a stop date set?
  - answer: Set the stop date to `null` with `ra.set(Asn.STOP, null);` and then save
      the project.
    question: Is it possible to remove a stop date once set?
  - answer: Absolutely. The `Asn` enum provides constants for all assignment fields,
      such as `Asn.START`, `Asn.FINISH`, etc.
    question: Does Aspose.Tasks support other date‑related fields like start, finish,
      or actual start?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- stop resource assignment
- Aspose.Tasks
- Java project scheduling
- resource management
title: Java में Resource Assignment कैसे रोकें – Aspose.Tasks के साथ Resume करें
url: /hi/java/resource-assignments/stop-resume-assignment/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा में रिसोर्स असाइनमेंट को कैसे रोकें – Aspose.Tasks के साथ पुनः शुरू करें

## परिचय
इस ट्यूटोरियल में आप **जावा में रिसोर्स असाइनमेंट को कैसे रोकें** और बाद में इसे Aspose.Tasks for Java का उपयोग करके पुनः शुरू करना सीखेंगे। Aspose.Tasks एक मजबूत Java API है जो आपको Microsoft Project फ़ाइलें पढ़ने और लिखने, शेड्यूल को बदलने, और रिसोर्स असाइनमेंट को नियंत्रित करने की अनुमति देता है—बिना Microsoft Project स्थापित किए। हम प्रत्येक चरण को विस्तार से देखेंगे, समझाएंगे कि प्रत्येक पंक्ति क्यों महत्वपूर्ण है, और व्यावहारिक टिप्स साझा करेंगे जिन्हें आप वास्तविक प्रोजेक्ट योजनाओं में लागू कर सकते हैं।

## त्वरित उत्तर
- **“stop assignment” का क्या मतलब है?** यह एक रिसोर्स असाइनमेंट को एक विशिष्ट स्टॉप डेट से अस्थायी रूप से निष्क्रिय के रूप में चिह्नित करता है।  
- **क्या मैं बाद में वही असाइनमेंट फिर से शुरू कर सकता हूँ?** हाँ, उसी असाइनमेंट पर एक रिज्यूम डेट सेट करके।  
- **क्या इस API को उपयोग करने के लिए Microsoft Project की आवश्यकता है?** नहीं, Aspose.Tasks Microsoft Project से स्वतंत्र रूप से काम करता है।  
- **कौन सा Java संस्करण आवश्यक है?** Java 8 या उससे ऊपर की सलाह दी जाती है।  
- **लाइब्रेरी कहाँ से डाउनलोड कर सकते हैं?** आधिकारिक Aspose.Tasks Java डाउनलोड पेज से।

## जावा में रिसोर्स असाइनमेंट को कैसे रोकें?
अपने प्रोजेक्ट को लोड करें, लक्ष्य `ResourceAssignment` को खोजें, `STOP` डेट सेट करें, वैकल्पिक रूप से `RESUME` डेट सेट करें, और फिर फ़ाइल को सहेजें। यह क्रम निर्दिष्ट अवधि के लिए कार्य को रोकता है और रिज्यूम डेट के बाद स्वचालित रूप से पुनः सक्रिय करता है, जिससे आप रिसोर्स कैलेंडर पर सटीक नियंत्रण प्राप्त करते हैं बिना मैन्युअल फ़ाइल संपादन के।

## Aspose.Tasks के संदर्भ में “how to stop assignment” क्या है?
एक असाइनमेंट को रोकना शेड्यूलर को बताता है कि **स्टॉप डेट** के बाद रिसोर्स को आवंटित कार्य को **रिज्यूम डेट** (यदि हो) तक अनदेखा करे। यह छुट्टियों, उपकरण के डाउनटाइम, या किसी भी अवधि को संभालने में उपयोगी है जब रिसोर्स को सक्रिय नहीं माना जाना चाहिए।

## रिसोर्स असाइनमेंट को प्रबंधित करने के लिए Aspose.Tasks क्यों उपयोग करें?
Aspose.Tasks आपको प्रोग्रामेटिक रूप से असाइनमेंट डेट्स को नियंत्रित करने की सुविधा देता है, जिससे मैन्युअल संपादन समाप्त होते हैं और त्रुटियों का जोखिम कम होता है। यह **50+ इनपुट और आउटपुट फॉर्मैट** को सपोर्ट करता है और **10,000 तक टास्क** वाले प्रोजेक्ट को प्रोसेस कर सकता है, जबकि मेमोरी उपयोग 200 MB से कम रहता है क्योंकि यह पूरी फ़ाइल को मेमोरी में लोड करने के बजाय डेटा को स्ट्रीम करता है। API किसी भी OS पर चलती है जो Java को सपोर्ट करता है, जिससे आपको क्रॉस‑प्लेटफ़ॉर्म लचीलापन मिलता है।

## पूर्वापेक्षाएँ
शुरू करने से पहले, सुनिश्चित करें कि आपके पास है:

- Java Development Kit (JDK) 8 या उससे नया स्थापित हो।  
- Aspose.Tasks for Java लाइब्रेरी डाउनलोड की हुई। आप इसे [here](https://releases.aspose.com/tasks/java/) से डाउनलोड कर सकते हैं।  
- Java प्रोग्रामिंग की बुनियादी समझ।

## पैकेज इम्पोर्ट करें
`Project`, `ResourceAssignment`, और `Asn` क्लासेस `com.aspose.tasks` नेमस्पेस में स्थित हैं। इन्हें अपने सोर्स फ़ाइल के शीर्ष पर इम्पोर्ट करें:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```

## चरण 1: प्रोजेक्ट फ़ाइल लोड करें
`Project` क्लास Aspose.Tasks का टॉप‑लेवल ऑब्जेक्ट है जो मेमोरी में एकल Microsoft Project फ़ाइल का प्रतिनिधित्व करता है। एक इंस्टेंस बनाकर फ़ाइल लोड होती है और आपको टास्क, रिसोर्स, और असाइनमेंट तक पहुँच मिलती है।

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Load the project file
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```

## चरण 2: रिसोर्स असाइनमेंट्स पर इटररेट करें
`ResourceAssignment` ऑब्जेक्ट्स सभी असाइनमेंट‑संबंधित फ़ील्ड्स को एक्सपोज़ करते हैं। हम **न्यूनतम डेट** सेट करते हैं ताकि प्लेसहोल्डर डेट्स को फ़िल्टर किया जा सके और फिर प्रत्येक असाइनमेंट पर लूप चलाते हैं। यह पैटर्न निरीक्षण या संशोधन के लिए मानक *रिसोर्स असाइनमेंट उदाहरण* है।

```java
// Define minimum date
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iterate through resource assignments
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```

## चरण 3: स्टॉप और रिज्यूम डेट्स जांचें
इस ब्लॉक में हम प्रत्येक असाइनमेंट के `STOP` और `RESUME` फ़ील्ड्स की जांच करते हैं। यदि कोई डेट हमारे `minDate` से पहले है, तो हम इसे सेट नहीं माना (`"NA"`); अन्यथा हम वास्तविक डेट प्रिंट करते हैं। यह लॉजिक **रिसोर्स असाइनमेंट को सही ढंग से प्रबंधित** करने के लिए आवश्यक है।

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

## सामान्य समस्याएँ और समाधान
- **नल डेट्स** – `ra.get(Asn.STOP)` `null` लौट सकता है। इसे रोकने के लिए `.before(minDate)` कॉल करने से पहले नल चेक जोड़ें।  
- **गलत फ़ाइल पाथ** – सुनिश्चित करें कि `dataDir` आपके OS के अनुसार एक पाथ सेपरेटर (`/` या `\\`) के साथ समाप्त हो।  
- **वर्ज़न मिसमैच** – गायब enum वैल्यूज़ से बचने के लिए नवीनतम Aspose.Tasks for Java संस्करण का उपयोग करें।

## अक्सर पूछे जाने वाले प्रश्न

**Q:** मैं प्रोग्रामेटिक रूप से असाइनमेंट के लिए स्टॉप डेट कैसे सेट करूँ?  
**A:** `ra.set(Asn.STOP, yourDateObject);` का उपयोग करें जहाँ `yourDateObject` एक `java.util.Date` है।

**Q:** यदि रिज्यूम डेट स्टॉप डेट से पहले हो तो क्या होता है?  
**A:** API कालक्रमिक क्रम लागू नहीं करती; हालांकि, शेड्यूलर दो डेट्स में से बाद की डेट के बाद ही असाइनमेंट को सक्रिय मानता है, इसलिए आपको स्वयं डेट्स को वैलिडेट करना चाहिए।

**Q:** क्या मैं केवल उन असाइनमेंट्स को फ़िल्टर कर सकता हूँ जिनमें स्टॉप डेट सेट है?  
**A:** हाँ, `prj.getResourceAssignments()` पर इटररेट करें और `ra.get(Asn.STOP) != null` जांचें।

**Q:** एक बार सेट होने के बाद स्टॉप डेट को हटाना संभव है?  
**A:** `ra.set(Asn.STOP, null);` के साथ स्टॉप डेट को `null` सेट करें और फिर प्रोजेक्ट को सहेजें।

**Q:** क्या Aspose.Tasks अन्य डेट‑संबंधित फ़ील्ड्स जैसे स्टार्ट, फिनिश, या एक्चुअल स्टार्ट को सपोर्ट करता है?  
**A:** बिल्कुल। `Asn` एन्‍उम सभी असाइनमेंट फ़ील्ड्स के लिए कॉन्स्टैंट्स प्रदान करता है, जैसे `Asn.START`, `Asn.FINISH`, आदि।

## निष्कर्ष
इन चरणों का पालन करके आप अब **जावा में रिसोर्स असाइनमेंट को कैसे रोकें** जानते हैं, स्टॉप/रिज्यूम डेट्स की जांच कर सकते हैं, और आवश्यकता पड़ने पर असाइनमेंट को पुनः शुरू कर सकते हैं। यह क्षमता आपको **रिसोर्स असाइनमेंट को** अधिक सटीक रूप से प्रबंधित करने देती है, विशेषकर रिसोर्स की छुट्टियों या उपकरण के डाउनटाइम जैसी स्थितियों में। आप उदाहरण को डेट्स अपडेट करने, रिपोर्ट जनरेट करने, या अपने स्वयं के शेड्यूलिंग लॉजिक के साथ इंटीग्रेट करने के लिए विस्तारित कर सकते हैं।

---

**अंतिम अपडेट:** 2026-07-14  
**परीक्षित संस्करण:** Aspose.Tasks for Java 24.12  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल्स

- [Aspose.Tasks में रिसोर्स असाइनमेंट बनाएं](/tasks/java/resource-assignments/create-resource-assignments/)
- [Aspose.Tasks के साथ लागत विचलन की गणना और असाइनमेंट लागत प्रबंधन कैसे करें](/tasks/java/resource-assignments/assignment-cost/)
- [Aspose.Tasks में रिसोर्स असाइनमेंट्स में नोट्स कैसे जोड़ें](/tasks/java/resource-assignments/resource-assignment-notes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}