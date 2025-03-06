---
title: Aspose.Tasks में कार्यों में विस्तारित विशेषताएँ जोड़ें
linktitle: Aspose.Tasks में कार्यों में विस्तारित विशेषताएँ जोड़ें
second_title: Aspose.Tasks जावा एपीआई
description: विस्तारित विशेषताओं के साथ Microsoft प्रोजेक्ट फ़ाइलों को अनुकूलित करने में Aspose.Tasks Java की शक्ति का अन्वेषण करें। अपनी परियोजना प्रबंधन क्षमताओं को सहजता से बढ़ाएं।
weight: 11
url: /hi/java/task-properties/add-extended-attributes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में कार्यों में विस्तारित विशेषताएँ जोड़ें

## परिचय
कुशल कार्य ट्रैकिंग और संसाधन प्रबंधन के लिए अपनी परियोजना प्रबंधन क्षमताओं को बढ़ाना महत्वपूर्ण है। जावा के लिए Aspose.Tasks जावा डेवलपर्स के लिए Microsoft प्रोजेक्ट फ़ाइलों में निर्बाध रूप से हेरफेर करने के लिए एक शक्तिशाली समाधान प्रदान करता है। इस ट्यूटोरियल में, हम यह पता लगाएंगे कि जावा के लिए Aspose.Tasks का उपयोग करके कार्यों में विस्तारित विशेषताओं को कैसे जोड़ा जाए, जिससे आप अपनी विशिष्ट आवश्यकताओं के अनुसार अपने प्रोजेक्ट डेटा को अनुकूलित और व्यवस्थित कर सकें।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
- जावा प्रोग्रामिंग का बुनियादी ज्ञान।
-  जावा लाइब्रेरी के लिए Aspose.Tasks स्थापित। आप इसे यहां से डाउनलोड कर सकते हैं[वेबसाइट](https://releases.aspose.com/tasks/java/).
- आपके सिस्टम पर एक जावा इंटीग्रेटेड डेवलपमेंट एनवायरनमेंट (आईडीई) स्थापित है।
## पैकेज आयात करें
अपने जावा प्रोजेक्ट में, Aspose.Tasks कार्यात्मकताओं तक पहुंचने के लिए आवश्यक पैकेज आयात करें:
```java
import java.io.IOException;
import com.aspose.tasks.*;
```
अब, आइए प्रत्येक उदाहरण को कई चरणों में तोड़ें:
## 1. सादा पाठ विशेषता जोड़ना
1. दस्तावेज़ निर्देशिका पथ सेट करें:
```java
String dataDir = "Your Document Directory";
```
2. एक नया प्रोजेक्ट बनाएं:
```java
Project project = new Project(dataDir + "project.mpp");
```
3. Text1 प्रकार की एक विस्तारित विशेषता परिभाषा बनाएं:
```java
ExtendedAttributeDefinition taskExtendedAttributeText1Definition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Task City Name");
```
4. प्रोजेक्ट के विस्तारित गुण संग्रह में परिभाषा जोड़ें:
```java
project.getExtendedAttributes().add(taskExtendedAttributeText1Definition);
```
5. प्रोजेक्ट में कोई कार्य जोड़ें:
```java
Task task = project.getRootTask().getChildren().add("Task 1");
```
6. गुण परिभाषा से एक विस्तारित गुण बनाएँ:
```java
ExtendedAttribute taskExtendedAttributeText1 = taskExtendedAttributeText1Definition.createExtendedAttribute();
```
7. उत्पन्न विस्तारित विशेषता के लिए एक मान निर्दिष्ट करें:
```java
taskExtendedAttributeText1.setTextValue("London");
```
8. कार्य में विस्तारित विशेषता जोड़ें:
```java
task.getExtendedAttributes().add(taskExtendedAttributeText1);
```
9. प्रोजेक्ट सहेजें:
```java
project.save(dataDir + "PlainTextExtendedAttribute_out.mpp", SaveFileFormat.Mpp);
```
## 2. लुकअप विकल्प के साथ टेक्स्ट विशेषता जोड़ना
उपरोक्त चरणों का पालन करें, टेक्स्ट1 को टेक्स्ट2 से बदलें और लुकअप मानों को अनुकूलित करें।
## 3. लुकअप विकल्प के साथ अवधि विशेषता जोड़ना
उपरोक्त चरणों का पालन करें, टेक्स्ट1 को अवधि2 से बदलें और लुकअप मानों को अनुकूलित करें।
## निष्कर्ष
इस चरण-दर-चरण मार्गदर्शिका का पालन करके, आपने सीखा है कि अपनी Microsoft प्रोजेक्ट फ़ाइलों में कार्यों में विस्तारित विशेषताएँ जोड़ने के लिए जावा के लिए Aspose.Tasks का लाभ कैसे उठाया जाए। यह अनुकूलन आपको लचीलेपन और दक्षता को बढ़ाते हुए अपने प्रोजेक्ट प्रबंधन दृष्टिकोण को अनुकूलित करने की अनुमति देता है।
## अक्सर पूछे जाने वाले प्रश्नों
### प्रश्न: क्या मैं अन्य जावा लाइब्रेरीज़ के साथ जावा के लिए Aspose.Tasks का उपयोग कर सकता हूँ?
उत्तर: हां, जावा के लिए Aspose.Tasks को आपके जावा प्रोजेक्ट्स में सहजता से एकीकृत किया जा सकता है, और यह अन्य जावा लाइब्रेरीज़ के साथ अच्छी तरह से काम करता है।
### प्रश्न: क्या जावा के लिए Aspose.Tasks बड़े पैमाने पर परियोजना प्रबंधन अनुप्रयोगों के लिए उपयुक्त है?
उत्तर: बिल्कुल, जावा के लिए Aspose.Tasks को बड़े पैमाने के अनुप्रयोगों सहित विभिन्न आकारों की परियोजनाओं को संभालने के लिए डिज़ाइन किया गया है।
### प्रश्न: क्या किसी वाणिज्यिक परियोजना में जावा के लिए Aspose.Tasks का उपयोग करने के लिए कोई लाइसेंस संबंधी विचार हैं?
 उत्तर: हां, इस पर दी गई लाइसेंसिंग जानकारी की समीक्षा करना सुनिश्चित करें[Aspose.कार्य वेबसाइट](https://purchase.aspose.com/buy).
### प्रश्न: मैं जावा के लिए Aspose.Tasks के साथ समर्थन या सहायता कैसे प्राप्त कर सकता हूं?
 ए: पर जाएँ[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15) सामुदायिक समर्थन और चर्चा के लिए।
### प्रश्न: क्या मैं खरीदने से पहले जावा के लिए Aspose.Tasks आज़मा सकता हूँ?
 उत्तर: हां, आप निःशुल्क परीक्षण संस्करण तक पहुंच सकते हैं[यहाँ](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
