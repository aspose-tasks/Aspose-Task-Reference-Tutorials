---
date: 2026-01-13
description: Aspose.Tasks के साथ जावा में रिसोर्स प्रतिशत कैसे गणना करें, जिसमें MS
  Project रिसोर्सेज़ के लिए पूर्ण कार्य प्रतिशत प्राप्त करना शामिल है, सीखें। कोड
  उदाहरणों के साथ चरण‑दर‑चरण गाइड।
linktitle: Perform Percentage Calculations for Resources in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks का उपयोग करके जावा में संसाधन प्रतिशत की गणना
url: /hi/java/resource-management/percentage-calculations/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks के साथ जावा में रिसोर्स प्रतिशत की गणना

## परिचय
स्वागत है! इस ट्यूटोरियल में आप Aspose.Tasks लाइब्रेरी for Java का उपयोग करके **how to calculate resource percentage java** सीखेंगे। हम प्रत्येक रिसोर्स के लिए Microsoft Project फ़ाइल में *percent work complete* निकालने की प्रक्रिया दिखाएंगे, समझाएंगे कि यह मीट्रिक क्यों महत्वपूर्ण है, और आपको आवश्यक कोड दिखाएंगे। अंत तक, आप किसी भी Java‑आधारित प्रोजेक्ट‑मैनेजमेंट समाधान में resource‑percentage गणना को एकीकृत कर पाएँगे।

## त्वरित उत्तर
- **“resource percentage” का क्या मतलब है?** यह कुल असाइन किए गए कार्य की तुलना में रिसोर्स द्वारा पूरा किया गया कार्य का प्रतिशत है।  
- **कौन सा API कॉल यह मान लौटाता है?** `Rsc.PERCENT_WORK_COMPLETE` `Resource` क्लास के माध्यम से।  
- **क्या मुझे लाइसेंस चाहिए?** प्रोडक्शन उपयोग के लिए एक टेम्पररी या फुल Aspose.Tasks लाइसेंस आवश्यक है।  
- **क्या मैं इसे अन्य Java फ्रेमवर्क्स के साथ उपयोग कर सकता हूँ?** हाँ – API Spring, Hibernate, और साधारण Java प्रोजेक्ट्स के साथ काम करता है।  
- **Aspose.Tasks का कौन सा संस्करण चाहिए?** कोई भी हालिया संस्करण जो `Rsc` एनेमरेशन को सपोर्ट करता है (जैसे 24.x)।

## calculate resource percentage java क्या है?
Java में रिसोर्स प्रतिशत की गणना का अर्थ है Microsoft Project फ़ाइल को प्रोग्रामेटिकली पढ़ना और यह निर्धारित करना कि प्रत्येक रिसोर्स ने कितना कार्य पूरा किया है। यह जानकारी प्रोजेक्ट मैनेजर्स को टाइमलाइन का पूर्वानुमान लगाने, कार्यभार संतुलित करने, और बाधाओं की पहचान करने में मदद करती है।

## percent work complete क्यों प्राप्त करें?
- **प्रोग्रेस ट्रैकिंग:** एक नज़र में देखिए कौन से टीम सदस्य समय पर हैं।  
- **कैपेसिटी प्लानिंग:** वास्तविक प्रदर्शन के आधार पर भविष्य के असाइनमेंट समायोजित करें।  
- **रिपोर्टिंग:** मैन्युअल गणना के बिना स्टेकहोल्डर्स के लिए सटीक स्टेटस रिपोर्ट जनरेट करें।

## आवश्यकताएँ
### Java विकास पर्यावरण
सुनिश्चित करें कि आपके पास Java Development Kit (JDK) स्थापित है। आप JDK को [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) से डाउनलोड कर सकते हैं।

### Aspose.Tasks लाइब्रेरी
Aspose.Tasks लाइब्रेरी को अपने प्रोजेक्ट में जोड़ें और डाउनलोड करें [here](https://releases.aspose.com/tasks/java/) और दस्तावेज़ में दिए गए इंस्टॉलेशन निर्देशों का पालन करें [here](https://reference.aspose.com/tasks/java/)।

## पैकेज आयात करें
कोडिंग शुरू करने से पहले, इस ट्यूटोरियल के लिए आवश्यक पैकेज आयात करें:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## चरण 1: प्रोजेक्ट फ़ाइल पथ सेट करें
```java
String dataDir = "Your Data Directory";
```
`"Your Data Directory"` को उस फ़ोल्डर से बदलें जिसमें आपका Microsoft Project फ़ाइल मौजूद है।

## चरण 2: प्रोजेक्ट लोड करें
```java
Project prj = new Project(dataDir + "Software Development.mpp");
```
यह निर्दिष्ट डायरेक्टरी से **Software Development.mpp** फ़ाइल को लोड करता है।

## चरण 3: रिसोर्सेज़ पर इटररेट करें
```java
for (Resource res : prj.getResources()) {
```
हम प्रोजेक्ट में परिभाषित प्रत्येक रिसोर्स पर लूप करते हैं।

## चरण 4: रिसोर्स नाम जांचें और Percent Work Complete प्राप्त करें
```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.PERCENT_WORK_COMPLETE));
}
```
कोड पहले यह सुनिश्चित करता है कि रिसोर्स का नाम मौजूद है और फिर उस रिसोर्स के **percent work complete** मान को प्रिंट करता है।

## सामान्य समस्याएँ और समाधान
- **NullPointerException** – सुनिश्चित करें कि प्रोजेक्ट फ़ाइल पथ सही है और फ़ाइल बिना त्रुटियों के लोड होती है।  
- **गलत प्रतिशत** – पुष्टि करें कि रिसोर्स को वास्तव में कार्य असाइन किया गया है; अन्यथा प्रतिशत `0` रहेगा।  
- **लाइसेंस त्रुटियाँ** – रनटाइम प्रतिबंधों से बचने के लिए वैध Aspose.Tasks लाइसेंस या टेम्पररी इवैल्यूएशन लाइसेंस का उपयोग करें।

## अक्सर पूछे जाने वाले प्रश्न (Original)

### क्या मैं Aspose.Tasks for Java को अन्य Java फ्रेमवर्क्स के साथ उपयोग कर सकता हूँ?
हाँ, Aspose.Tasks for Java विभिन्न Java फ्रेमवर्क्स जैसे Spring, Hibernate, और अन्य के साथ संगत है।

### क्या Aspose.Tasks सभी संस्करणों की Microsoft Project फ़ाइलों का समर्थन करता है?
Aspose.Tasks सभी संस्करणों की Microsoft Project फ़ाइलों का समर्थन करता है, जिसमें MPP, MPT, XML, आदि शामिल हैं।

### क्या मैं Aspose.Tasks का उपयोग करके प्रोजेक्ट शेड्यूल को बदल सकता हूँ?
बिल्कुल, Aspose.Tasks कार्य, रिसोर्सेज़, कैलेंडर आदि सहित प्रोजेक्ट शेड्यूल को बदलने के लिए व्यापक सुविधाएँ प्रदान करता है।

### क्या Aspose.Tasks समर्थन के लिए कोई कम्युनिटी फ़ोरम है?
हाँ, आप Aspose.Tasks कम्युनिटी फ़ोरम पर सहायता प्राप्त कर सकते हैं और अन्य उपयोगकर्ताओं के साथ संवाद कर सकते हैं [here](https://forum.aspose.com/c/tasks/15)।

### क्या Aspose.Tasks मूल्यांकन उद्देश्यों के लिए अस्थायी लाइसेंस प्रदान करता है?
हाँ, आप [here](https://purchase.aspose.com/temporary-license/) से मूल्यांकन के लिए एक टेम्पररी लाइसेंस प्राप्त कर सकते हैं।

## अतिरिक्त FAQ

**Q:** आउटपुट को प्रतिशत के साथ % चिह्न दिखाने के लिए कैसे फॉर्मेट करूँ?  
**A:** संख्यात्मक मान को `res.get(Rsc.PERCENT_WORK_COMPLETE)` से प्राप्त करें और `String.format("%.2f%%", value)` का उपयोग करके फॉर्मेट करें।

**Q:** क्या मैं केवल उन रिसोर्सेज़ को दिखाने के लिए फ़िल्टर कर सकता हूँ जिनका पूर्णता 50 % से कम है?  
**A:** हाँ, प्रिंट करने से पहले `if` शर्त जोड़ें जो `res.get(Rsc.PERCENT_WORK_COMPLETE) < 50` की जाँच करे।

**Q:** क्या प्रतिशत को फिर से प्रोजेक्ट फ़ाइल में लिखना संभव है?  
**A:** `Rsc.PERCENT_WORK_COMPLETE` फ़ील्ड केवल‑पढ़ने योग्य है; आपको टास्क असाइनमेंट्स को समायोजित करना होगा।

**Q:** क्या यह Project Online (क्लाउड) फ़ाइलों के साथ काम करता है?  
**A:** आपको पहले .mpp फ़ाइल को स्थानीय रूप से डाउनलोड करना होगा; Aspose.Tasks फ़ाइल फ़ॉर्मेट के साथ काम करता है, सीधे क्लाउड सेवा के साथ नहीं।

## निष्कर्ष
इस गाइड में हमने Aspose.Tasks का उपयोग करके **how to calculate resource percentage java** को दर्शाया, जिसमें प्रत्येक रिसोर्स के *percent work complete* को प्राप्त करने पर ध्यान दिया गया। ऊपर दिए गए चरणों का पालन करके आप अपने Java एप्लिकेशन में सटीक रिसोर्स‑percentage एनालिटिक्स को एम्बेड कर सकते हैं, जिससे प्रोजेक्ट स्वास्थ्य और रिसोर्स उपयोगिता की बेहतर दृश्यता मिलती है।

---

**अंतिम अपडेट:** 2026-01-13  
**परीक्षण किया गया:** Aspose.Tasks for Java 24.10  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}