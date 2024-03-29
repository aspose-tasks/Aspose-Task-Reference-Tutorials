---
title: Aspose.Tasks में कार्य की प्रगति बदलें
linktitle: Aspose.Tasks में कार्य की प्रगति बदलें
second_title: Aspose.Tasks जावा एपीआई
description: Aspose.Tasks के साथ जावा प्रोजेक्ट प्रबंधन को बेहतर बनाएं। इस चरण-दर-चरण ट्यूटोरियल में कार्य प्रगति को सहजता से संशोधित करना सीखें। अब डाउनलोड करो!
type: docs
weight: 12
url: /hi/java/task-properties/change-progress/
---
## परिचय
परियोजना प्रबंधन के गतिशील क्षेत्र में, प्रभावी कार्य प्रगति ट्रैकिंग महत्वपूर्ण है। जावा के लिए Aspose.Tasks एक मजबूत समाधान के रूप में सामने आया है, जो अपनी शक्तिशाली विशेषताओं के साथ प्रक्रिया को सरल बनाता है। इस ट्यूटोरियल में, हम जावा के लिए Aspose.Tasks का उपयोग करके किसी कार्य की प्रगति को बदलने के चरणों के माध्यम से आपका मार्गदर्शन करेंगे।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपने निम्नलिखित आवश्यक शर्तें स्थापित कर ली हैं:
1. जावा विकास पर्यावरण: अपने सिस्टम पर एक कार्यात्मक जावा विकास वातावरण स्थापित और स्थापित करें।
2.  जावा लाइब्रेरी के लिए Aspose.Tasks: लाइब्रेरी को यहां से डाउनलोड करें[जोड़ना](https://releases.aspose.com/tasks/java/).
3. दस्तावेज़ निर्देशिका: अपने प्रोजेक्ट दस्तावेज़ों को संग्रहीत करने के लिए एक निर्देशिका बनाएं।
## पैकेज आयात करें
आइए आपके जावा प्रोजेक्ट में आवश्यक पैकेज आयात करके शुरुआत करें। यह कोड स्निपेट प्रोजेक्ट प्रारंभ करता है और 50% प्रगति के साथ एक कार्य जोड़ता है।
```java
import com.aspose.tasks.*;

```
## चरण 1: अपना प्रोजेक्ट सेट करें
अपने विकास परिवेश में एक नया जावा प्रोजेक्ट बनाकर शुरुआत करें।
## चरण 2: आवश्यक पैकेज आयात करें
 अपने जावा क्लास में, आवश्यक पैकेज आयात करें:`Project` और`Task`.
## चरण 3: दस्तावेज़ निर्देशिका निर्दिष्ट करें
प्रोजेक्ट फ़ाइलों को संग्रहीत करने के लिए अपनी दस्तावेज़ निर्देशिका का पथ परिभाषित करें।
```java
String dataDir = "Your Document Directory";
```
## चरण 4: एक नया प्रोजेक्ट बनाएं
 उपयोग`Project` एक नया प्रोजेक्ट बनाने के लिए क्लास।
```java
Project project = new Project(dataDir + "project.mpp");
```
## चरण 5: एक कार्य जोड़ें
 का उपयोग करें`Task` अपने प्रोजेक्ट में एक नया कार्य जोड़ने के लिए क्लास।
```java
Task task = project.getRootTask().getChildren().add("Task");
```
## चरण 6: कार्य प्रगति निर्धारित करें
 का उपयोग करके कार्य की प्रगति निर्धारित करें`set` विधि और`Tsk.PERCENT_COMPLETE` गुण।
```java
task.set(Tsk.PERCENT_COMPLETE, percent(50));
```
### चरण 7: प्रगति प्रदर्शित करें
कार्य प्रगति पुनर्प्राप्त करें और प्रदर्शित करें।
```java
System.out.println(task.get(Tsk.PERCENT_COMPLETE));
```
इन चरणों का पालन करके, आपने जावा के लिए Aspose.Tasks का उपयोग करके किसी कार्य की प्रगति को सफलतापूर्वक बदल दिया है।
## निष्कर्ष
परियोजना प्रबंधन में कार्य प्रगति ट्रैकिंग को सुव्यवस्थित करना महत्वपूर्ण है। जावा के लिए Aspose.Tasks एक उपयोगकर्ता-अनुकूल इंटरफ़ेस और शक्तिशाली सुविधाएँ प्रदान करके इस प्रक्रिया को सरल बनाता है। इस गाइड में उल्लिखित चरणों में महारत हासिल करने से आपकी परियोजना प्रबंधन क्षमताएं बढ़ती हैं।
## अक्सर पूछे जाने वाले प्रश्नों
### क्या Aspose.Tasks सभी जावा विकास परिवेशों के साथ संगत है?
दस्तावेज़ में दिए गए इंस्टॉलेशन निर्देशों का पालन करके अनुकूलता सुनिश्चित करें।
### क्या मैं एक परियोजना के भीतर अनेक कार्यों की प्रगति को ट्रैक कर सकता हूँ?
जिस भी कार्य की आप निगरानी करना चाहते हैं, उसके लिए चरणों को दोहराएँ।
### क्या जावा के लिए Aspose.Tasks का कोई परीक्षण संस्करण उपलब्ध है?
 निःशुल्क परीक्षण संस्करण तक पहुंचें[यहाँ](https://releases.aspose.com/).
### मैं जावा के लिए Aspose.Tasks के लिए विस्तृत दस्तावेज़ कहाँ पा सकता हूँ?
 व्यापक दस्तावेज़ीकरण का अन्वेषण करें[यहाँ](https://reference.aspose.com/tasks/java/).
### मैं जावा के लिए Aspose.Tasks के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
 दौरा करना[अस्थायी लाइसेंस पृष्ठ](https://purchase.aspose.com/temporary-license/).