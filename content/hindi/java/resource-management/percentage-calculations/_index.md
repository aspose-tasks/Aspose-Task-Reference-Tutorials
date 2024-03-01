---
title: Aspose.Tasks के साथ एमएस प्रोजेक्ट संसाधन प्रतिशत गणना
linktitle: Aspose.Tasks में संसाधनों के लिए प्रतिशत गणना करें
second_title: Aspose.Tasks जावा एपीआई
description: जावा के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट संसाधन प्रतिशत की गणना करना सीखें। कोड उदाहरणों के साथ चरण-दर-चरण मार्गदर्शिका शामिल है।
type: docs
weight: 14
url: /hi/java/resource-management/percentage-calculations/
---
## परिचय
जावा के लिए Aspose.Tasks का उपयोग करके एमएस प्रोजेक्ट संसाधनों के लिए प्रतिशत गणना करने पर हमारी चरण-दर-चरण मार्गदर्शिका में आपका स्वागत है। इस ट्यूटोरियल में, हम Microsoft प्रोजेक्ट फ़ाइलों से संसाधन डेटा को कुशलतापूर्वक हेरफेर करने और निकालने के लिए Aspose.Tasks का लाभ उठाने की प्रक्रिया के बारे में विस्तार से जानेंगे। Aspose.Tasks एक शक्तिशाली जावा एपीआई है जो माइक्रोसॉफ्ट प्रोजेक्ट दस्तावेज़ों के साथ काम करने के लिए व्यापक सुविधाएँ प्रदान करता है, जिससे डेवलपर्स को अपने जावा अनुप्रयोगों में परियोजना प्रबंधन कार्यात्मकताओं को सहजता से एकीकृत करने की अनुमति मिलती है।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपने निम्नलिखित आवश्यक शर्तें स्थापित कर ली हैं:
### जावा विकास पर्यावरण
 सुनिश्चित करें कि आपके सिस्टम पर जावा डेवलपमेंट किट (जेडीके) स्थापित है। आप यहां से जेडीके डाउनलोड और इंस्टॉल कर सकते हैं[यहाँ](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
### Aspose.कार्य लाइब्रेरी
आपको Aspose.Tasks लाइब्रेरी को अपने जावा प्रोजेक्ट में एकीकृत करना होगा। यदि आपने पहले से ऐसा नहीं किया है, तो आप यहां से लाइब्रेरी डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/java/) और दस्तावेज़ में दिए गए इंस्टॉलेशन निर्देशों का पालन करें[यहाँ](https://reference.aspose.com/tasks/java/).

## पैकेज आयात करें
इससे पहले कि हम कोडिंग शुरू करें, आइए इस ट्यूटोरियल के लिए आवश्यक आवश्यक पैकेज आयात करें:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```
## चरण 1: प्रोजेक्ट फ़ाइल पथ सेट करें
```java
String dataDir = "Your Data Directory";
```
 प्रतिस्थापित करें`"Your Data Directory"` आपकी Microsoft प्रोजेक्ट फ़ाइल के पथ के साथ।
## चरण 2: प्रोजेक्ट लोड करें
```java
Project prj = new Project(dataDir + "Software Development.mpp");
```
यह कोड निर्दिष्ट डेटा निर्देशिका में स्थित "सॉफ़्टवेयर डेवलपमेंट.एमपीपी" नामक Microsoft प्रोजेक्ट फ़ाइल को लोड करता है।
## चरण 3: संसाधनों के माध्यम से पुनरावृति करें
```java
for (Resource res : prj.getResources()) {
```
हम प्रोजेक्ट में प्रत्येक संसाधन के माध्यम से लूप करते हैं।
## चरण 4: संसाधन का नाम और प्रतिशत कार्य पूर्ण की जाँच करें
```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.PERCENT_WORK_COMPLETE));
}
```
हम जांचते हैं कि संसाधन का नाम शून्य तो नहीं है और फिर प्रत्येक संसाधन के लिए पूर्ण किए गए कार्य का प्रतिशत प्रिंट करते हैं।

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा है कि एमएस प्रोजेक्ट संसाधनों के लिए प्रतिशत गणना कुशलतापूर्वक करने के लिए जावा के लिए Aspose.Tasks का उपयोग कैसे करें। इन चरणों का पालन करके, आप परियोजना प्रबंधन कार्यात्मकताओं को अपने जावा अनुप्रयोगों में निर्बाध रूप से एकीकृत कर सकते हैं, जिससे परियोजना संसाधन उपयोग में बेहतर नियंत्रण और अंतर्दृष्टि प्रदान की जा सकती है।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं अन्य जावा फ्रेमवर्क के साथ जावा के लिए Aspose.Tasks का उपयोग कर सकता हूँ?
हां, जावा के लिए Aspose.Tasks स्प्रिंग, हाइबरनेट और अन्य जैसे विभिन्न जावा फ्रेमवर्क के साथ संगत है।
### क्या Aspose.Tasks Microsoft Project फ़ाइलों के सभी संस्करणों का समर्थन करता है?
Aspose.Tasks एमपीपी, एमपीटी, एक्सएमएल और अन्य सहित माइक्रोसॉफ्ट प्रोजेक्ट फ़ाइलों के सभी संस्करणों के लिए समर्थन प्रदान करता है।
### क्या मैं Aspose.Tasks का उपयोग करके प्रोजेक्ट शेड्यूल में हेरफेर कर सकता हूँ?
बिल्कुल, Aspose.Tasks कार्य, संसाधन, कैलेंडर और बहुत कुछ सहित प्रोजेक्ट शेड्यूल में हेरफेर करने के लिए व्यापक सुविधाएँ प्रदान करता है।
### क्या Aspose.Tasks समर्थन के लिए कोई सामुदायिक मंच है?
 हां, आप Aspose.Tasks समुदाय मंच पर सहायता पा सकते हैं और अन्य उपयोगकर्ताओं के साथ जुड़ सकते हैं[यहाँ](https://forum.aspose.com/c/tasks/15).
### क्या Aspose.Tasks मूल्यांकन उद्देश्यों के लिए अस्थायी लाइसेंस प्रदान करता है?
 हां, आप मूल्यांकन के लिए अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).