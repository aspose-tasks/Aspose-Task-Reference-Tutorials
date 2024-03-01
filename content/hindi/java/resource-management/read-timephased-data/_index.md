---
title: Aspose.Tasks में संसाधनों के लिए समयबद्ध डेटा पढ़ें
linktitle: Aspose.Tasks में संसाधनों के लिए समयबद्ध डेटा पढ़ें
second_title: Aspose.Tasks जावा एपीआई
description: जावा के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट संसाधनों से टाइमफ़ेज़्ड डेटा निकालने का तरीका जानें। चरण-दर-चरण ट्यूटोरियल.
type: docs
weight: 15
url: /hi/java/resource-management/read-timephased-data/
---
## परिचय
इस ट्यूटोरियल में, हम आपको जावा के लिए Aspose.Tasks का उपयोग करके एमएस प्रोजेक्ट संसाधनों के लिए टाइमफ़ेज़्ड डेटा पढ़ने की प्रक्रिया के माध्यम से मार्गदर्शन करेंगे। यह लाइब्रेरी Microsoft प्रोजेक्ट फ़ाइलों को प्रोग्रामेटिक रूप से प्रबंधित करने के लिए शक्तिशाली कार्यक्षमताएँ प्रदान करती है।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यकताएँ हैं:
1.  जावा डेवलपमेंट किट (जेडीके): सुनिश्चित करें कि आपके सिस्टम पर जेडीके स्थापित है। आप इसे यहां से डाउनलोड कर सकते हैं[वेबसाइट](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) और स्थापना निर्देशों का पालन करें.
2.  जावा लाइब्रेरी के लिए Aspose.Tasks: जावा लाइब्रेरी के लिए Aspose.Tasks को यहां से डाउनलोड करें[डाउनलोड पेज](https://releases.aspose.com/tasks/java/) और दस्तावेज़ में दिए गए इंस्टॉलेशन निर्देशों का पालन करें।

## पैकेज आयात करें
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```
## चरण 1: डेटा निर्देशिका स्थापित करें
सबसे पहले, उस निर्देशिका को परिभाषित करें जहां आपकी एमएस प्रोजेक्ट फ़ाइल स्थित है।
```java
String dataDir = "Your Data Directory";
```
## चरण 2: एमएस प्रोजेक्ट टेम्पलेट फ़ाइल पढ़ें
अपने एमएस प्रोजेक्ट टेम्पलेट फ़ाइल का नाम निर्दिष्ट करें।
```java
String fileName = "ResourceTimephasedData.mpp";
```
## चरण 3: इनपुट फ़ाइल को प्रोजेक्ट के रूप में पढ़ें
Aspose.Tasks का उपयोग करके इनपुट फ़ाइल पढ़ें और इसे प्रोजेक्ट ऑब्जेक्ट के रूप में लोड करें।
```java
Project project = new Project(dataDir + fileName);
```
## चरण 4: आईडी द्वारा संसाधन प्राप्त करें
प्रोजेक्ट से उसके विशिष्ट पहचानकर्ता (आईडी) द्वारा वांछित संसाधन पुनः प्राप्त करें।
```java
Resource resource = project.getResources().getByUid(1);
```
## चरण 5: संसाधन कार्य के लिए समयबद्ध डेटा प्रिंट करें
संसाधन कार्य के लिए समयबद्ध डेटा प्रिंट करें।
```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```
## चरण 6: संसाधन लागत के लिए समयबद्ध डेटा प्रिंट करें
संसाधन लागत के लिए समयबद्ध डेटा प्रिंट करें।
```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा है कि जावा के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट संसाधनों के लिए टाइमफ़ेज़्ड डेटा कैसे पढ़ा जाए। इन चरणों का पालन करके, आप प्रोग्रामेटिक रूप से अपनी प्रोजेक्ट फ़ाइलों से मूल्यवान जानकारी कुशलतापूर्वक निकाल सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या Aspose.Tasks Microsoft प्रोजेक्ट के अलावा अन्य प्रकार की प्रोजेक्ट फ़ाइलों को संभाल सकता है?
हाँ, Aspose.Tasks MPP, XML और CSV सहित विभिन्न फ़ाइल स्वरूपों का समर्थन करता है।
### क्या Aspose.Tasks विभिन्न जावा विकास परिवेशों के साथ संगत है?
हां, Aspose.Tasks सभी प्रमुख जावा आईडीई और फ्रेमवर्क के साथ संगत है।
### क्या मैं Aspose.Tasks का उपयोग करके प्रोजेक्ट डेटा में हेरफेर कर सकता हूँ?
बिल्कुल, Aspose.Tasks प्रोजेक्ट डेटा बनाने, संशोधित करने और विश्लेषण करने के लिए व्यापक एपीआई प्रदान करता है।
### क्या Aspose.Tasks उद्यम-स्तरीय परियोजनाओं के लिए उपयुक्त है?
हाँ, Aspose.Tasks का उपयोग इसकी विश्वसनीयता और मापनीयता के कारण उद्यम परिवेश में व्यापक रूप से किया जाता है।
### यदि Aspose.Tasks का उपयोग करते समय मुझे कोई समस्या आती है तो मुझे सहायता कहां मिल सकती है?
 आप विजिट कर सकते हैं[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15) समुदाय और सहायता टीम से सहायता के लिए।