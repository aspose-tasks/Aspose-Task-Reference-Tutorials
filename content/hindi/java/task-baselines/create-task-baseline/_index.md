---
title: Aspose.Tasks में MS प्रोजेक्ट टास्क बेसलाइन बनाएं
linktitle: Aspose.Tasks में एक कार्य आधार रेखा बनाना
second_title: Aspose.Tasks जावा एपीआई
description: प्रोजेक्ट डेटा को सहजता से प्रबंधित करने के लिए एक शक्तिशाली लाइब्रेरी, Aspose.Tasks का उपयोग करके जावा में Microsoft प्रोजेक्ट कार्य बेसलाइन बनाने का तरीका जानें।
type: docs
weight: 11
url: /hi/java/task-baselines/create-task-baseline/
---
## परिचय
इस ट्यूटोरियल में, हम जावा के लिए Aspose.Tasks का उपयोग करके एक Microsoft प्रोजेक्ट कार्य बेसलाइन बनाने की प्रक्रिया के बारे में विस्तार से जानेंगे। Aspose.Tasks एक शक्तिशाली जावा लाइब्रेरी है जो डेवलपर्स को Microsoft प्रोजेक्ट स्थापित करने की आवश्यकता के बिना Microsoft प्रोजेक्ट फ़ाइलों के साथ काम करने में सक्षम बनाती है। Aspose.Tasks के साथ, आप प्रोजेक्ट प्रबंधन कार्यों को सुव्यवस्थित करने के लिए कार्यों, संसाधनों और कैलेंडर सहित प्रोजेक्ट डेटा में आसानी से हेरफेर कर सकते हैं।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यकताएँ हैं:
1. जावा डेवलपमेंट किट (जेडीके): जावा के लिए Aspose.Tasks के लिए आपके सिस्टम पर JDK स्थापित होना आवश्यक है। आप Oracle वेबसाइट से JDK डाउनलोड और इंस्टॉल कर सकते हैं।
2.  जावा लाइब्रेरी के लिए Aspose.Tasks: जावा लाइब्रेरी के लिए Aspose.Tasks को यहां से डाउनलोड करें[लिंक को डाउनलोड करें](https://releases.aspose.com/tasks/java/) प्रदान किया।

## पैकेज आयात करें
अपने जावा प्रोजेक्ट में Aspose.Tasks के साथ काम करना शुरू करने के लिए, आवश्यक पैकेज आयात करें:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## चरण 1: एक प्रोजेक्ट ऑब्जेक्ट बनाएं
```java
Project project = new Project();
```
 सबसे पहले, एक नया बनाएं`Project` वस्तु। यह ऑब्जेक्ट उस Microsoft प्रोजेक्ट फ़ाइल का प्रतिनिधित्व करता है जिसके साथ आप काम करेंगे।
## चरण 2: प्रोजेक्ट में एक कार्य जोड़ें
```java
Task task = project.getRootTask().getChildren().add("Task");
```
 का उपयोग`getRootTask()` विधि, प्रोजेक्ट के मूल कार्य तक पहुंचें और फिर इसका उपयोग करके इसमें एक नया कार्य जोड़ें`add()` तरीका। कोष्ठक के भीतर कार्य के लिए एक नाम प्रदान करें।
## चरण 3: निर्दिष्ट कार्यों के लिए आधार रेखा निर्धारित करें
```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
विशिष्ट कार्यों के लिए आधार रेखा निर्धारित करने के लिए, कार्यों की एक सूची बनाएं (`myList` इस मामले में) और इसे उन कार्यों से भरें जिनके लिए आप आधार रेखा निर्धारित करना चाहते हैं। फिर, का उपयोग करें`setBaseline()` विधि, आधारभूत प्रकार और कार्यों की सूची निर्दिष्ट करना।
## चरण 4: संपूर्ण परियोजना के लिए आधार रेखा निर्धारित करें
```java
project.setBaseline(BaselineType.Baseline);
```
 वैकल्पिक रूप से, आप केवल कॉल करके पूरे प्रोजेक्ट के लिए आधार रेखा निर्धारित कर सकते हैं`setBaseline()` निर्दिष्ट बेसलाइन प्रकार के साथ विधि।

## निष्कर्ष
इस ट्यूटोरियल में, हमने पता लगाया है कि Java के लिए Aspose.Tasks का उपयोग करके Microsoft प्रोजेक्ट कार्य बेसलाइन कैसे बनाई जाए। ऊपर बताए गए चरणों का पालन करके, आप प्रोजेक्ट डेटा को कुशलतापूर्वक प्रबंधित कर सकते हैं और प्रोजेक्ट प्रबंधन कार्यों को आसानी से सुव्यवस्थित कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं माइक्रोसॉफ्ट प्रोजेक्ट स्थापित किए बिना जावा के लिए Aspose.Tasks का उपयोग कर सकता हूँ?
हां, जावा के लिए Aspose.Tasks आपको आपके सिस्टम पर Microsoft प्रोजेक्ट इंस्टॉल किए बिना Microsoft प्रोजेक्ट फ़ाइलों के साथ काम करने की अनुमति देता है।
### क्या जावा के लिए Aspose.Tasks माइक्रोसॉफ्ट प्रोजेक्ट के विभिन्न संस्करणों के साथ संगत है?
हाँ, Java के लिए Aspose.Tasks विभिन्न वातावरणों में अनुकूलता सुनिश्चित करते हुए, Microsoft प्रोजेक्ट के विभिन्न संस्करणों का समर्थन करता है।
### क्या मैं जावा के लिए Aspose.Tasks का उपयोग करके परियोजना संसाधनों में हेरफेर कर सकता हूँ?
बिल्कुल, जावा के लिए Aspose.Tasks परियोजना संसाधनों में हेरफेर करने के लिए मजबूत सुविधाएँ प्रदान करता है, जिसमें आवश्यकतानुसार संसाधनों को जोड़ना, अपडेट करना और हटाना शामिल है।
### क्या जावा के लिए Aspose.Tasks कार्य निर्भरताएँ निर्धारित करने का समर्थन करता है?
हां, आप जावा के लिए Aspose.Tasks का उपयोग करके आसानी से कार्य निर्भरताएं सेट कर सकते हैं, जिससे आप अपने प्रोजेक्ट के भीतर कार्यों का क्रम स्थापित कर सकेंगे।
### क्या जावा के लिए Aspose.Tasks के लिए तकनीकी सहायता उपलब्ध है?
 हां, आप जावा के लिए Aspose.Tasks के लिए तकनीकी सहायता प्राप्त कर सकते हैं[सहयता मंच](https://forum.aspose.com/c/tasks/15), जहां आप प्रश्न पूछ सकते हैं और समुदाय और Aspose सहयोगी स्टाफ से सहायता मांग सकते हैं।