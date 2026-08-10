---
date: 2026-06-15
description: Aspose.Tasks for Java का उपयोग करके MS Project संसाधनों से टाइमफ़ेज़्ड
  डेटा निकालना सीखें। get resource by id के लिए चरण‑दर‑चरण गाइड।
keywords:
- get resource by id
- Aspose.Tasks timephased data
- Java MS Project API
linktitle: Aspose.Tasks में संसाधनों के लिए टाइमफ़ेज़्ड डेटा पढ़ें
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to extract timephased data from MS Project resources using
    Aspose.Tasks for Java. Step‑by‑step guide to get resource by id.
  headline: Read Timephased Data for Resources in Aspose.Tasks – get resource by id
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks supports MPP, XML, CSV, and several other formats, allowing
      you to read and write across different standards.
    question: Can Aspose.Tasks handle other types of project files apart from Microsoft
      Project?
  - answer: Absolutely. The library works with all major IDEs (IntelliJ IDEA, Eclipse,
      NetBeans) and build tools (Maven, Gradle).
    question: Is Aspose.Tasks compatible with different Java development environments?
  - answer: Yes, you can create, modify, and delete tasks, resources, assignments,
      and even custom fields through the API.
    question: Can I manipulate project data using Aspose.Tasks?
  - answer: It is. Enterprises rely on Aspose.Tasks for high‑volume processing, batch
      conversions, and server‑side reporting because it requires no Microsoft Project
      installation.
    question: Is Aspose.Tasks suitable for enterprise‑level projects?
  - answer: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for assistance from the community and support team.
    question: Where can I find support if I encounter issues while using Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks में संसाधनों के लिए टाइमफ़ेज़्ड डेटा पढ़ें – get resource by id
url: /hi/java/resource-management/read-timephased-data/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में संसाधनों के लिए टाइमफ़ेज़्ड डेटा पढ़ें

## परिचय
इस ट्यूटोरियल में, आप **how to get resource by id** सीखेंगे और Aspose.Tasks for Java का उपयोग करके उसका टाइमफ़ेज़्ड डेटा पढ़ेंगे। हम प्रत्येक चरण को समझाएंगे—प्रोजेक्ट फ़ोल्डर सेट अप करने से लेकर कार्य और लागत के टाइमफ़ेज़्ड मान प्रिंट करने तक—ताकि आप किसी भी Microsoft Project फ़ाइल से प्रोग्रामेटिकली मूल्यवान शेड्यूलिंग जानकारी निकाल सकें। Aspose.Tasks for Java एक व्यापक API है जो डेवलपर्स को Microsoft Project फ़ाइलों को बिना Microsoft Project इंस्टॉल किए बनाना, पढ़ना, संशोधित करना और कनवर्ट करना सक्षम बनाता है, और यह प्रोजेक्ट मैनेजमेंट की विभिन्न सुविधाओं और फ़ॉर्मैट्स को सपोर्ट करता है।

## त्वरित उत्तर
- **“get resource by id” क्या करता है?** यह एक विशिष्ट `Resource` ऑब्जेक्ट को `Project` से उसके अद्वितीय पहचानकर्ता का उपयोग करके प्राप्त करता है।  
- **कौन सा लाइब्रेरी टाइमफ़ेज़्ड डेटा संभालता है?** Aspose.Tasks for Java `Resource.getTimephasedData` API प्रदान करता है।  
- **क्या मुझे लाइसेंस चाहिए?** विकास के लिए एक फ्री ट्रायल काम करता है; उत्पादन के लिए एक व्यावसायिक लाइसेंस आवश्यक है।  
- **क्या मैं बड़े प्रोजेक्ट पढ़ सकता हूँ?** हाँ—Aspose.Tasks फ़ाइलों को 10,000 टास्क तक बिना पूरी फ़ाइल को मेमोरी में लोड किए प्रोसेस कर सकता है।  
- **कौन सा Java संस्करण आवश्यक है?** Java 8 या उससे ऊपर; लाइब्रेरी सभी प्रमुख JDKs के साथ संगत है।

## “get resource by id” क्या है?
`get resource by id` एक मेथड कॉल है जो लोडेड `Project` से संसाधन की संख्यात्मक ID का उपयोग करके `Resource` इंस्टेंस प्राप्त करता है। यह ऑपरेशन संसाधन की विस्तृत प्रॉपर्टीज़ जैसे असाइनमेंट्स, कैलेंडर, और कस्टम फ़ील्ड्स तक सटीक पहुँच प्रदान करता है, और उस विशिष्ट संसाधन से जुड़े टाइमफ़ेज़्ड कार्य या लागत डेटा निकालने के लिए आवश्यक है।

## टाइमफ़ेज़्ड डेटा के लिए Aspose.Tasks क्यों उपयोग करें?
Aspose.Tasks **50+ इनपुट और आउटपुट फॉर्मैट्स** (MPP, XML, CSV, आदि) को सपोर्ट करता है और कई‑सालों की शेड्यूल्स में फैले संसाधनों के लिए टाइमफ़ेज़्ड कार्य और लागत मान निकाल सकता है, जबकि मेमोरी उपयोग कम रखता है। API डिफ़ॉल्ट रूप से डेटा को 15‑मिनट के अंतराल में लौटाता है, जिससे आपको रिपोर्टिंग या कस्टम एनालिटिक्स के लिए विस्तृत अंतर्दृष्टि मिलती है।

## आवश्यकताएँ
1. Java Development Kit (JDK): सुनिश्चित करें कि आपके सिस्टम पर JDK स्थापित है। आप इसे [website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) से डाउनलोड कर सकते हैं और इंस्टॉलेशन निर्देशों का पालन करें।  
2. Aspose.Tasks for Java Library: Aspose.Tasks for Java लाइब्रेरी को [download page](https://releases.aspose.com/tasks/java/) से डाउनलोड करें और दस्तावेज़ में प्रदान किए गए इंस्टॉलेशन निर्देशों का पालन करें।

## पैकेज इम्पोर्ट करें
पहला कदम आवश्यक Aspose.Tasks क्लासेज़ को आपके Java स्रोत फ़ाइल में इम्पोर्ट करना है।

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```

## चरण 1: डेटा डायरेक्टरी सेट अप करें
पहले, उस डायरेक्टरी को परिभाषित करें जहाँ आपका MS Project फ़ाइल स्थित है। डेटा फ़ोल्डर को स्रोत कोड से अलग रखने से प्रोजेक्ट को बनाए रखना आसान हो जाता है।

```java
String dataDir = "Your Data Directory";
```

## चरण 2: MS Project टेम्पलेट फ़ाइल पढ़ें
अपने MS Project टेम्पलेट फ़ाइल का नाम निर्दिष्ट करें। टेम्पलेट का उपयोग करने से विभिन्न प्रोजेक्ट्स में कॉलम सेटिंग्स सुसंगत रहती हैं।

```java
String fileName = "ResourceTimephasedData.mpp";
```

## चरण 3: इनपुट फ़ाइल को प्रोजेक्ट के रूप में पढ़ें
`Project` क्लास Aspose.Tasks का कोर ऑब्जेक्ट है जो मेमोरी में एक Microsoft Project फ़ाइल का प्रतिनिधित्व करता है। फ़ाइल को लोड करने से आपको टास्क, रिसोर्सेज़ और शेड्यूल्स तक प्रोग्रामेटिक एक्सेस मिलता है।

```java
Project project = new Project(dataDir + fileName);
```

## चरण 4: ID द्वारा रिसोर्स प्राप्त करें
एक विशिष्ट रिसोर्स प्राप्त करने के लिए, `getResources().getById(id)` मेथड को कॉल करें। यह वही ऑपरेशन है जिसका उल्लेख मुख्य कीवर्ड में किया गया है।

```java
Resource resource = project.getResources().getByUid(1);
```

## चरण 5: रिसोर्स कार्य के लिए टाइमफ़ेज़्ड डेटा प्रिंट करें
एक बार जब आपके पास `Resource` ऑब्जेक्ट हो, आप `resource.getTimephasedData(ResourceTimephasedDataType.Work)` को कॉल करके समय के साथ कार्य आवंटन प्राप्त कर सकते हैं। लौटाई गई कलेक्शन में `TimephasedData` ऑब्जेक्ट्स होते हैं जिनमें प्रत्येक अंतराल के लिए शुरूआती तिथि, समाप्ति तिथि, और कार्य की मात्रा शामिल होती है।

```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```

## चरण 6: रिसोर्स लागत के लिए टाइमफ़ेज़्ड डेटा प्रिंट करें
इसी प्रकार, `resource.getTimephasedData(ResourceTimephasedDataType.Cost)` समान समय अंतराल के अनुसार लागत जानकारी देता है। यह बजटिंग और लागत‑ट्रैकिंग रिपोर्ट्स के लिए उपयोगी है।

```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## एक लाइन में ID द्वारा रिसोर्स कैसे प्राप्त करें?
प्रोजेक्ट लोड करें, फिर `project.getResources().getById(5)` को कॉल करें—**5** को उस वास्तविक रिसोर्स ID से बदलें जिसकी आपको आवश्यकता है। यह एकल कॉल `Resource` ऑब्जेक्ट लौटाता है, जिसके बाद आप उसका टाइमफ़ेज़्ड डेटा, असाइनमेंट्स, या कस्टम फ़ील्ड्स क्वेरी कर सकते हैं। मेथड O(1) समय में चलता है क्योंकि रिसोर्सेज़ को आंतरिक रूप से इंडेक्स किया गया है।

## सामान्य समस्याएँ और समाधान
- **Resource not found** – सुनिश्चित करें कि ID प्रोजेक्ट फ़ाइल में मौजूद है; IDs 1 से शुरू होती हैं और प्रत्येक रिसोर्स के लिए अद्वितीय होती हैं।  
- **Empty timephased data** – पुष्टि करें कि रिसोर्स के पास कार्य या लागत असाइनमेंट्स हैं; अन्यथा कलेक्शन खाली रहेगा।  
- **Large file performance** – 500 MB से बड़े प्रोजेक्ट्स के लिए लेज़ी लोडिंग सक्षम करने हेतु `Project.setLoadOptions(LoadOptions.fromFile(...))` का उपयोग करें।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या Aspose.Tasks Microsoft Project के अलावा अन्य प्रकार की प्रोजेक्ट फ़ाइलें संभाल सकता है?**  
A: हाँ, Aspose.Tasks MPP, XML, CSV, और कई अन्य फॉर्मैट्स को सपोर्ट करता है, जिससे आप विभिन्न मानकों के बीच पढ़ और लिख सकते हैं।

**Q: क्या Aspose.Tasks विभिन्न Java विकास परिवेशों के साथ संगत है?**  
A: बिल्कुल। लाइब्रेरी सभी प्रमुख IDEs (IntelliJ IDEA, Eclipse, NetBeans) और बिल्ड टूल्स (Maven, Gradle) के साथ काम करती है।

**Q: क्या मैं Aspose.Tasks का उपयोग करके प्रोजेक्ट डेटा को हेरफेर कर सकता हूँ?**  
A: हाँ, आप API के माध्यम से टास्क, रिसोर्सेज़, असाइनमेंट्स, और यहां तक कि कस्टम फ़ील्ड्स को बना, संशोधित और हटाकर हेरफेर कर सकते हैं।

**Q: क्या Aspose.Tasks एंटरप्राइज़‑लेवल प्रोजेक्ट्स के लिए उपयुक्त है?**  
A: यह उपयुक्त है। एंटरप्राइज़ उच्च‑वॉल्यूम प्रोसेसिंग, बैच कन्वर्ज़न, और सर्वर‑साइड रिपोर्टिंग के लिए Aspose.Tasks पर भरोसा करते हैं क्योंकि इसे Microsoft Project इंस्टॉल करने की आवश्यकता नहीं होती।

**Q: यदि मैं Aspose.Tasks उपयोग करते समय समस्याओं का सामना करता हूँ तो समर्थन कहाँ मिल सकता है?**  
A: आप समुदाय और सपोर्ट टीम से सहायता के लिए [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) पर जा सकते हैं।

## निष्कर्ष
इस ट्यूटोरियल में, हमने **get resource by id** कैसे प्राप्त करें और Aspose.Tasks for Java का उपयोग करके उसके टाइमफ़ेज़्ड कार्य और लागत डेटा को पढ़ें, यह सीखा। इन चरणों का पालन करके आप अपने प्रोजेक्ट फ़ाइलों से मूल्यवान शेड्यूलिंग जानकारी को प्रभावी ढंग से निकाल सकते हैं और इसे कस्टम रिपोर्टिंग या एनालिटिक्स पाइपलाइन में एकीकृत कर सकते हैं।

---

**Last Updated:** 2026-06-15  
**Tested With:** Aspose.Tasks 24.11 for Java  
**Author:** Aspose

## संबंधित ट्यूटोरियल

- [Aspose.Tasks for Java के साथ प्रोजेक्ट में रिसोर्स जोड़ें](/tasks/java/resource-management/create-resources/)
- [Aspose.Tasks for Java के साथ MS Project रिसोर्स लागत प्रबंधित करें](/tasks/java/resource-management/resource-cost/)
- [Aspose.Tasks के साथ MS Project कैलेंडर से जावा में कार्य सप्ताह पढ़ें](/tasks/java/calendars/read-work-weeks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}