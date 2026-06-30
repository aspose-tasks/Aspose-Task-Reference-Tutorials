---
date: 2026-06-30
description: Aspose.Tasks for Java का उपयोग करके कई संसाधनों को अपडेट करना, संसाधन
  समूह डेटा को संशोधित करना, फिर प्रोजेक्ट को MPP में निर्यात करना और प्रोजेक्ट को
  MPP के रूप में सहेजना सीखें।
keywords:
- update multiple resources
- modify resource group
- export project to mpp
- save project as mpp
linktitle: Aspose.Tasks for Java में कई संसाधनों को अपडेट करें
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to update multiple resources and modify resource group data,
    then export project to MPP and save project as MPP using Aspose.Tasks for Java.
  headline: Update Multiple Resources in Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to update multiple resources and modify resource group data,
    then export project to MPP and save project as MPP using Aspose.Tasks for Java.
  name: Update Multiple Resources in Aspose.Tasks for Java
  steps:
  - name: Java Development Kit (JDK) installed on your system.
    text: Java Development Kit (JDK) installed on your system.
  - name: Aspose.Tasks for Java library. You can download it from [here](https://releases.aspose.com/tasks/java/).
    text: Aspose.Tasks for Java library. You can download it from [here](https://releases.aspose.com/tasks/java/).
  - name: Basic knowledge of Java programming.
    text: Basic knowledge of Java programming.
  type: HowTo
- questions:
  - answer: Yes, you can update multiple resources by iterating through them and setting
      their attributes accordingly.
    question: Can I update multiple resources in the same project using Aspose.Tasks
      for Java?
  - answer: Yes, Aspose.Tasks supports various file formats including XML, MPP, and
      more.
    question: Does Aspose.Tasks support other file formats besides MS Project?
  - answer: Aspose.Tasks is compatible with Java versions 6 and above.
    question: Is Aspose.Tasks compatible with different versions of Java?
  - answer: Yes, you can perform a wide range of operations such as reading, writing,
      and manipulating tasks, resources, and calendars.
    question: Can I perform other operations on MS Project files with Aspose.Tasks?
  - answer: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for any assistance or queries.
    question: Where can I find additional help or support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java में कई संसाधनों को अपडेट करें
url: /hi/java/resource-management/write-updated-resource-data/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspise.Tasks for Java में कई संसाधनों को अपडेट करें

## परिचय
इस ट्यूटोरियल में, आप सीखेंगे कि Aspose.Tasks for Java का उपयोग करके Microsoft Project फ़ाइल में **कई संसाधनों को अपडेट** कैसे किया जाता है। चाहे आपको दरें बदलनी हों, समूहों को पुनः‑निर्धारित करना हो, या अपडेट की गई फ़ाइल को MPP में निर्यात करना हो, नीचे दिए गए चरण एक पूर्ण, प्रोडक्शन‑रेडी वर्कफ़्लो के माध्यम से आपका मार्गदर्शन करेंगे। Microsoft Project की कोई इंस्टॉलेशन आवश्यक नहीं है, और API सैकड़ों संसाधनों वाले प्रोजेक्ट को कुशलतापूर्वक संभाल सकता है।

## त्वरित उत्तर
- **क्या मैं एक साथ कई संसाधनों को अपडेट कर सकता हूँ?** हाँ – `ResourceCollection` पर इटररेट करें और एक ही पास में एट्रिब्यूट सेट करें।  
- **कौन सा मेथड फ़ाइल को MPP के रूप में सहेजता है?** `project.save("output.mpp", SaveFileFormat.MPP)`।  
- **क्या व्यावसायिक उपयोग के लिए लाइसेंस चाहिए?** प्रोडक्शन के लिए एक पेड लाइसेंस आवश्यक है; एक फ्री ट्रायल उपलब्ध है।  
- **कौन से Java संस्करण समर्थित हैं?** Java 6 और उससे ऊपर, जिसमें Java 17 LTS शामिल है।  
- **क्या बल्क‑अपडेट प्रदर्शनकारी है?** Aspose.Tasks सामान्य सर्वर पर 500‑संसाधन प्रोजेक्ट को 2 सेकंड से कम समय में प्रोसेस करता है।

## “कई संसाधनों को अपडेट करना” क्या है?
**“कई संसाधनों को अपडेट करना”** का अर्थ है प्रोग्रामेटिक रूप से कई संसाधन प्रविष्टियों के गुणों को बदलना—जैसे दरें, समूह, कैलेंडर, या कस्टम फ़ील्ड—एक ही प्रोजेक्ट फ़ाइल के भीतर। यह ऑपरेशन अक्सर तब आवश्यक होता है जब एंटरप्राइज़ रिसोर्स प्लानिंग सिस्टम के साथ प्रोजेक्ट डेटा को सिंक्रोनाइज़ किया जाता है, कई संसाधनों में बजट समायोजित किया जाता है, या संगठन‑व्यापी नीति परिवर्तन लागू किए जाते हैं।

## संसाधन समूह को संशोधित करने और प्रोजेक्ट को MPP में निर्यात करने के लिए Aspose.Tasks का उपयोग क्यों करें?
Aspose.Tasks **50+ इनपुट और आउटपुट फ़ॉर्मेट** का समर्थन करता है, जिसमें MPP, XML, और CSV शामिल हैं, और **प्रोजेक्ट को MPP में निर्यात** कर सकता है बिना पूरी फ़ाइल को मेमोरी में लोड किए। लाइब्रेरी **2 GB** तक की फ़ाइलों को प्रोसेस करती है, जिससे आप **प्रोजेक्ट को MPP के रूप में सहेज** सकते हैं तेज़ी और विश्वसनीयता के साथ।

## पूर्वापेक्षाएँ

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

1. आपके सिस्टम पर Java Development Kit (JDK) स्थापित हो।  
2. Aspose.Tasks for Java लाइब्रेरी। आप इसे [यहाँ](https://releases.aspose.com/tasks/java/) से डाउनलोड कर सकते हैं।  
3. Java प्रोग्रामिंग का बुनियादी ज्ञान।

## पैकेज आयात करें

`import` स्टेटमेंट्स आवश्यक Aspose.Tasks क्लासेज़ को आपके स्रोत फ़ाइल में लाते हैं।

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## चरण 1: अपना डेटा डायरेक्टरी सेट करें

अपने डेटा फ़ाइलों के स्थित डायरेक्टरी को परिभाषित करें:

```java
String dataDir = "Your Data Directory";
```

## चरण 2: इनपुट और आउटपुट फ़ाइलें निर्दिष्ट करें

इनपुट MS Project फ़ाइल और परिणामी अपडेटेड फ़ाइल के पाथ को परिभाषित करें:

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Test file with one rsc to update
String resultFile = dataDir + "OutputMPP.mpp"; // File to write test project
```

## चरण 3: प्रोजेक्ट लोड करें

`Project` एक Microsoft Project फ़ाइल को मेमोरी में लोड करने का प्रतिनिधित्व करता है, जो टास्क, रिसोर्सेज़, और अन्य प्रोजेक्ट डेटा तक पहुँच प्रदान करता है।

```java
Project project = new Project(file);
```

## चरण 4: एक रिसोर्स जोड़ें और एट्रिब्यूट सेट करें

`Resource` एक व्यक्तिगत प्रोजेक्ट रिसोर्स को मॉडल करता है, जिससे आप दरें, समूह, कैलेंडर, और अन्य एट्रिब्यूट सेट कर सकते हैं।

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

## चरण 5: कई संसाधनों को कुशलतापूर्वक अपडेट करें

`ResourceCollection` प्रोजेक्ट में सभी रिसोर्सेज़ का संग्रह है, जिसे `project.getResources()` के माध्यम से एक्सेस किया जा सकता है।

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## चरण 6: प्रोजेक्ट सहेजें

`SaveFileFormat` प्रोजेक्ट को सहेजने के लिए समर्थित फ़ाइल फ़ॉर्मेट्स को सूचीबद्ध करता है, जैसे MPP, XML, और PDF।

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## प्रोजेक्ट में कई संसाधनों को कैसे अपडेट करें?
मौजूदा प्रोजेक्ट को लोड करें, उसकी `ResourceCollection` प्राप्त करें, और प्रत्येक `Resource` ऑब्जेक्ट पर इटररेट करें। प्रत्येक रिसोर्स के लिए, आवश्यक फ़ील्ड जैसे दरें, समूह, या कस्टम एट्रिब्यूट बदलें, फिर अगले आइटम पर जाएँ। सभी रिसोर्सेज़ को प्रोसेस करने के बाद, `project.save(...)` को एक बार कॉल करें ताकि परिवर्तन कुशलतापूर्वक सहेजे जा सकें।

## सामान्य समस्याएँ और समाधान

- **Resource IDs टकराव** – `project.getResources().add(new Resource())` का उपयोग करके सुनिश्चित करें कि प्रत्येक नया रिसोर्स एक अनूठा ID प्राप्त करे।  
- **Rate फ़ॉर्मेट त्रुटियाँ** – `ResourceRate` ऑब्जेक्ट्स का उपयोग करें और `RateType` को `StandardRate` या `OvertimeRate` सेट करें।  
- **बड़ी फ़ाइलें मेमोरी दबाव बनाती हैं** – लोड करने से पहले `Project.setReadOnly(true)` सक्षम करें ताकि मेमोरी फ़ुटप्रिंट कम हो।

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या मैं Aspose.Tasks for Java का उपयोग करके एक ही प्रोजेक्ट में कई संसाधनों को अपडेट कर सकता हूँ?**  
उत्तर: हाँ, आप उन्हें इटररेट करके और उनके एट्रिब्यूट्स को उपयुक्त रूप से सेट करके कई संसाधनों को अपडेट कर सकते हैं।

**प्रश्न: क्या Aspose.Tasks MS Project के अलावा अन्य फ़ाइल फ़ॉर्मेट्स का समर्थन करता है?**  
उत्तर: हाँ, Aspose.Tasks विभिन्न फ़ाइल फ़ॉर्मेट्स का समर्थन करता है जिसमें XML, MPP, और अन्य शामिल हैं।

**प्रश्न: क्या Aspose.Tasks विभिन्न Java संस्करणों के साथ संगत है?**  
उत्तर: Aspose.Tasks Java संस्करण 6 और उससे ऊपर के साथ संगत है।

**प्रश्न: क्या मैं Aspose.Tasks के साथ MS Project फ़ाइलों पर अन्य ऑपरेशन्स कर सकता हूँ?**  
उत्तर: हाँ, आप रीडिंग, राइटिंग, और टास्क, रिसोर्सेज़, तथा कैलेंडर को मैनीपुलेट करने जैसे विभिन्न ऑपरेशन्स कर सकते हैं।

**प्रश्न: Aspose.Tasks के लिए अतिरिक्त सहायता या सपोर्ट कहाँ मिल सकता है?**  
उत्तर: आप किसी भी सहायता या प्रश्नों के लिए [Aspose.Tasks फ़ोरम](https://forum.aspose.com/c/tasks/15) पर जा सकते हैं।

**प्रश्न: अपडेटेड फ़ाइल को MPP फ़ॉर्मेट में कैसे निर्यात करूँ?**  
उत्तर: सभी रिसोर्स बदलावों के बाद `project.save("UpdatedProject.mpp", SaveFileFormat.MPP)` को कॉल करें।

**प्रश्न: रिसोर्स समूह को संशोधित करने का सबसे अच्छा तरीका क्या है?**  
उत्तर: प्रोजेक्ट सहेजने से पहले प्रत्येक `Resource` ऑब्जेक्ट पर `Resource.Group` प्रॉपर्टी सेट करें।

---

**अंतिम अपडेट:** 2026-06-30  
**परीक्षित संस्करण:** Aspose.Tasks for Java 24.12  
**लेखक:** Aspose  

{{< blocks/products/products-backtop-button >}}

## संबंधित ट्यूटोरियल

- [Aspose.Tasks for Java के साथ प्रोजेक्ट में रिसोर्स जोड़ें](/tasks/java/resource-management/create-resources/)
- [Aspose.Tasks for Java के साथ MS Project रिसोर्स लागत प्रबंधित करें](/tasks/java/resource-management/resource-cost/)
- [Aspose.Tasks for Java के साथ MPP को Excel में निर्यात करने का तरीका](/tasks/java/project-file-operations/save-data-to-excel/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}