---
date: 2026-06-15
description: Aspose.Tasks के साथ जावा में रिसोर्स प्रतिशत कैसे गणना करें, जिसमें MS
  Project रिसोर्सेज़ के लिए पूर्ण कार्य प्रतिशत प्राप्त करना शामिल है। कोड उदाहरणों
  के साथ चरण-दर-चरण गाइड।
keywords:
- calculate resource percentage java
- get percent work complete
- Aspose.Tasks resource percentage
- Java project management API
linktitle: Aspose.Tasks में रिसोर्सेज़ के लिए प्रतिशत गणनाएँ करें
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to calculate resource percentage java with Aspose.Tasks,
    including how to get percent work complete for MS Project resources. Step‑by‑step
    guide with code examples.
  headline: calculate resource percentage java with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: It’s the percentage of work a resource has completed relative to its total
      assigned work.
    question: What does “resource percentage” mean?
  - answer: '`Rsc.PERCENT_WORK_COMPLETE` via the `Resource` class.'
    question: Which API call returns this value?
  - answer: A temporary or full Aspose.Tasks license is required for production use.
    question: Do I need a license?
  - answer: Yes – the API works with Spring, Hibernate, and plain Java projects.
    question: Can I use this with other Java frameworks?
  - answer: Any recent version that supports the `Rsc` enumeration (e.g., 24.x).
    question: What version of Aspose.Tasks is needed?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks के साथ जावा में रिसोर्स प्रतिशत की गणना करें
url: /hi/java/resource-management/percentage-calculations/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks के साथ जावा में रिसोर्स प्रतिशत की गणना

## परिचय
स्वागत है! इस ट्यूटोरियल में आप Aspose.Tasks लाइब्रेरी का उपयोग करके **जावा में रिसोर्स प्रतिशत की गणना** कैसे करें सीखेंगे। हम प्रत्येक रिसोर्स के *percent work complete* को Microsoft Project फ़ाइल से निकालने की प्रक्रिया दिखाएंगे, समझाएंगे कि यह मीट्रिक क्यों महत्वपूर्ण है, और आपको आवश्यक सटीक कोड दिखाएंगे। अंत तक, आप किसी भी जावा-आधारित प्रोजेक्ट‑मैनेजमेंट समाधान में रिसोर्स‑परसेंटेज गणनाओं को एकीकृत कर सकेंगे।

## त्वरित उत्तर
- **“resource percentage” का क्या अर्थ है?** यह वह प्रतिशत है जो एक रिसोर्स ने अपने कुल निर्धारित कार्य की तुलना में पूरा किया है।  
- **कौन सा API कॉल यह मान लौटाता है?** `Rsc.PERCENT_WORK_COMPLETE` `Resource` क्लास के माध्यम से।  
- **क्या मुझे लाइसेंस की आवश्यकता है?** प्रोडक्शन उपयोग के लिए एक अस्थायी या पूर्ण Aspose.Tasks लाइसेंस आवश्यक है।  
- **क्या मैं इसे अन्य जावा फ्रेमवर्क्स के साथ उपयोग कर सकता हूँ?** हां – API Spring, Hibernate, और साधारण जावा प्रोजेक्ट्स के साथ काम करता है।  
- **Aspose.Tasks का कौन सा संस्करण आवश्यक है?** `Rsc` एनेमरेशन को सपोर्ट करने वाला कोई भी नवीनतम संस्करण (उदा., 24.x)।

## जावा में रिसोर्स प्रतिशत की गणना क्या है?
जावा में रिसोर्स प्रतिशत की गणना में Microsoft Project फ़ाइल खोलना, प्रत्येक रिसोर्स के निर्धारित कार्य को पढ़ना, और यह निर्धारित करना शामिल है कि उस कार्य का कितना हिस्सा पहले ही पूरा हो चुका है। यह मीट्रिक प्रोजेक्ट मैनेजर्स को प्रगति का आकलन करने, कार्यभार संतुलित करने, और मैन्युअल गणनाओं के बिना संभावित देरी की पहचान करने में मदद करता है।

## percent work complete क्यों प्राप्त करें?
प्रत्येक रिसोर्स के लिए percent work complete प्राप्त करने से यह तुरंत पता चलता है कि नियोजित प्रयास का कितना हिस्सा समाप्त हो चुका है, जिससे आप जल्दी से उन कार्यों को पहचान सकते हैं जो पीछे रह रहे हैं या रिसोर्सेज़ जो कम उपयोग में हैं। यह अंतर्दृष्टि समय पर निर्णय लेने और अधिक सटीक स्थिति रिपोर्टिंग को समर्थन देती है।

## पूर्वापेक्षाएँ
### जावा विकास पर्यावरण
सुनिश्चित करें कि आपके पास Java Development Kit (JDK) स्थापित है। आप JDK को [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) से डाउनलोड कर सकते हैं।

### Aspose.Tasks लाइब्रेरी
Aspose.Tasks लाइब्रेरी को अपने प्रोजेक्ट में जोड़ने के लिए [here](https://releases.aspose.com/tasks/java/) से डाउनलोड करें और दस्तावेज़ीकरण में प्रदान किए गए इंस्टॉलेशन निर्देशों का पालन करें [here](https://reference.aspose.com/tasks/java/)।

## पैकेज आयात करें
`Resource` क्लास एक प्रोजेक्ट रिसोर्स को दर्शाता है और percent work complete जैसे फ़ील्ड्स तक पहुँच प्रदान करता है।  
कोडिंग शुरू करने से पहले, चलिए इस ट्यूटोरियल के लिए आवश्यक पैकेज आयात करते हैं:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## प्रोजेक्ट फ़ाइल पथ कैसे सेट करें?
अपने Microsoft Project फ़ाइल का स्थान निर्दिष्ट करें, चाहे वह एक पूर्ण पथ हो या एप्लिकेशन की कार्य निर्देशिका के सापेक्ष पथ। पथ स्ट्रिंग को एक वैध *.mpp* फ़ाइल की ओर इंगित करना चाहिए ताकि Aspose.Tasks उसे ढूंढ सके और आगे की प्रोसेसिंग के लिए खोल सके।
```java
String dataDir = "Your Data Directory";
```
`"Your Data Directory"` को उस फ़ोल्डर से बदलें जिसमें आपकी Microsoft Project फ़ाइल है।

## प्रोजेक्ट को कैसे लोड करें?
पहले परिभाषित फ़ाइल पथ का उपयोग करके `Project` क्लास का नया इंस्टेंस बनाएं। `Project` क्लास एक Microsoft Project फ़ाइल का प्रतिनिधित्व करता है और इसके टास्क, रिसोर्सेज़, और अन्य प्रोजेक्ट डेटा तक पहुँच प्रदान करता है, सभी को विश्लेषण के लिए मेमोरी में लोड करता है।
```java
Project prj = new Project(dataDir + "Software Development.mpp");
```
यह निर्दिष्ट निर्देशिका से फ़ाइल **Software Development.mpp** को लोड करता है।

## रिसोर्सेज़ पर कैसे इटररेट करें?
`project.getResources()` मेथड का उपयोग करके लोड किए गए प्रोजेक्ट में परिभाषित सभी रिसोर्सेज़ का संग्रह प्राप्त करें। इस संग्रह पर मानक जावा `for` लूप या उन्नत `for‑e` कंस्ट्रक्ट के साथ इटररेट करें, जिससे आप प्रत्येक `Resource` ऑब्जेक्ट को व्यक्तिगत रूप से जांच सकें और उसके संबंधित फ़ील्ड्स प्राप्त कर सकें।
```java
for (Resource res : prj.getResources()) {
```
हम प्रोजेक्ट में परिभाषित प्रत्येक रिसोर्स पर लूप करते हैं।

## रिसोर्स नाम कैसे जांचें और percent work complete प्राप्त करें?
पहले सुनिश्चित करें कि `Resource` ऑब्जेक्ट का नाम खाली नहीं है ताकि प्लेसहोल्डर एंट्रीज़ को प्रोसेस करने से बचा जा सके। फिर `res.get(Rsc.PERCENT_WORK_COMPLETE)` कॉल करें, जो उस रिसोर्स के लिए पूर्ण किए गए कार्य का प्रतिशत दर्शाने वाला एक डबल मान लौटाता है, जो 0 से 100 तक हो सकता है। आप इस मान को डिस्प्ले के लिए फ़ॉर्मेट कर सकते हैं या समग्र प्रोजेक्ट स्वास्थ्य का आकलन करने के लिए आगे की गणनाओं में उपयोग कर सकते हैं।
```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.PERCENT_WORK_COMPLETE));
}
```
कोड पहले यह सुनिश्चित करता है कि रिसोर्स का नाम मौजूद है और फिर उस रिसोर्स के लिए **percent work complete** मान को प्रिंट करता है।

## सामान्य समस्याएँ और समाधान
- **NullPointerException** – सुनिश्चित करें कि प्रोजेक्ट फ़ाइल पथ सही है और फ़ाइल बिना त्रुटियों के लोड हो रही है।  
- **Incorrect percentages** – जाँचें कि रिसोर्स के पास वास्तव में असाइन किया गया कार्य है; अन्यथा प्रतिशत `0` होगा।  
- **License errors** – रनटाइम प्रतिबंधों से बचने के लिए एक वैध Aspose.Tasks लाइसेंस या अस्थायी इवैल्यूएशन लाइसेंस का उपयोग करें।

## अक्सर पूछे जाने वाले प्रश्न (Original)
### क्या मैं Aspose.Tasks for Java को अन्य जावा फ्रेमवर्क्स के साथ उपयोग कर सकता हूँ?
हां, Aspose.Tasks for Java विभिन्न जावा फ्रेमवर्क्स जैसे Spring, Hibernate, और अन्य के साथ संगत है।

### क्या Aspose.Tasks Microsoft Project फ़ाइलों के सभी संस्करणों को सपोर्ट करता है?
Aspose.Tasks सभी संस्करणों की Microsoft Project फ़ाइलों को सपोर्ट करता है, जिसमें MPP, MPT, XML, और अन्य शामिल हैं।

### क्या मैं Aspose.Tasks का उपयोग करके प्रोजेक्ट शेड्यूल को मैनीपुलेट कर सकता हूँ?
बिल्कुल, Aspose.Tasks प्रोजेक्ट शेड्यूल को मैनीपुलेट करने के लिए व्यापक फीचर्स प्रदान करता है, जिसमें टास्क, रिसोर्सेज़, कैलेंडर, और अन्य शामिल हैं।

### क्या Aspose.Tasks समर्थन के लिए कोई कम्युनिटी फ़ोरम है?
हां, आप Aspose.Tasks कम्युनिटी फ़ोरम पर सहायता प्राप्त कर सकते हैं और अन्य उपयोगकर्ताओं के साथ जुड़ सकते हैं [here](https://forum.aspose.com/c/tasks/15).

### क्या Aspose.Tasks मूल्यांकन उद्देश्यों के लिए अस्थायी लाइसेंस प्रदान करता है?
हां, आप [here](https://purchase.aspose.com/temporary-license/) से मूल्यांकन के लिए अस्थायी लाइसेंस प्राप्त कर सकते हैं।

## अतिरिक्त अक्सर पूछे जाने वाले प्रश्न
**Q:** आउटपुट को प्रतिशत के साथ % चिह्न दिखाने के लिए कैसे फ़ॉर्मेट करें?  
**A:** संख्यात्मक मान को `res.get(Rsc.PERCENT_WORK_COMPLETE)` से प्राप्त करें और `String.format("%.2f%%", value)` का उपयोग करके फ़ॉर्मेट करें।

**Q:** केवल उन रिसोर्सेज़ को दिखाने के लिए जिन्हें 50 % से कम पूरा हुआ है, फ़िल्टर कर सकता हूँ?  
**A:** हां, प्रिंट करने से पहले `res.get(Rsc.PERCENT_WORK_COMPLETE) < 50` की जाँच करने वाली `if` शर्त जोड़ें।

**Q:** क्या प्रतिशत को फिर से प्रोजेक्ट फ़ाइल में लिखना संभव है?  
**A:** `Rsc.PERCENT_WORK_COMPLETE` फ़ील्ड केवल पढ़ने योग्य है; आपको इसके बजाय टास्क असाइनमेंट्स को समायोजित करना होगा।

**Q:** क्या यह Project Online (cloud) फ़ाइलों के साथ काम करता है?  
**A:** आपको पहले .mpp फ़ाइल को स्थानीय रूप से डाउनलोड करना होगा; Aspose.Tasks फ़ाइल फ़ॉर्मेट के साथ काम करता है, न कि सीधे क्लाउड सेवा के साथ।

## Aspose.Tasks उपयोग करने के मापनीय लाभ
Aspose.Tasks **30+ फ़ाइल फ़ॉर्मेट** (MPP, MPT, XML, CSV, आदि) को सपोर्ट करता है और **10,000 टास्क** तक के प्रोजेक्ट्स को प्रोसेस कर सकता है, जबकि डेटा को स्ट्रीम करके मेमोरी उपयोग 200 MB से कम रखता है। लाइब्रेरी का **read‑only `Rsc.PERCENT_WORK_COMPLETE`** फ़ील्ड O(n) समय में गणना किया जाता है, जिससे बड़े शेड्यूल्स के लिए भी तेज़ पुनर्प्राप्ति सुनिश्चित होती है।

## निष्कर्ष
इस गाइड में हमने Aspose.Tasks का उपयोग करके **जावा में रिसोर्स प्रतिशत की गणना** कैसे करें दिखाया, प्रत्येक रिसोर्स के लिए *percent work complete* प्राप्त करने पर ध्यान केंद्रित किया। ऊपर दिए गए चरणों का पालन करके, आप अपने जावा एप्लिकेशन्स में सटीक रिसोर्स‑परसेंटेज एनालिटिक्स एम्बेड कर सकते हैं, जिससे आपको प्रोजेक्ट स्वास्थ्य और रिसोर्स उपयोगिता की बेहतर दृश्यता मिलती है।

---

**अंतिम अपडेट:** 2026-06-15  
**परीक्षित संस्करण:** Aspose.Tasks for Java 24.10  
**लेखक:** Aspose

## संबंधित ट्यूटोरियल
- [Aspose.Tasks for Java के साथ प्रोजेक्ट में रिसोर्स जोड़ें](/tasks/java/resource-management/create-resources/)
- [Aspose.Tasks for Java के साथ MS Project रिसोर्स लागत प्रबंधित करें](/tasks/java/resource-management/resource-cost/)
- [Aspose.Tasks में टास्क के लिए प्रतिशत पूर्णता गणनाएँ](/tasks/java/task-properties/percentage-complete-calculations/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}