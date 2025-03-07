---
title: Aspose.Tasks प्रोजेक्ट्स में गैंट चार्ट व्यू कॉन्फ़िगर करें
linktitle: Aspose.Tasks प्रोजेक्ट्स में गैंट चार्ट व्यू कॉन्फ़िगर करें
second_title: Aspose.Tasks जावा एपीआई
description: जावा का उपयोग करके Aspose.Tasks में गैंट एमएस प्रोजेक्ट चार्ट व्यू को कॉन्फ़िगर करने का तरीका जानें। प्रोजेक्ट को अनुकूलित करें और चरण-दर-चरण गैंट चार्ट में उनकी कल्पना करें।
weight: 10
url: /hi/java/project-configuration/configure-gantt-chart/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks प्रोजेक्ट्स में गैंट चार्ट व्यू कॉन्फ़िगर करें

## परिचय
इस ट्यूटोरियल में, आप सीखेंगे कि जावा का उपयोग करके Aspose.Tasks प्रोजेक्ट में गैंट एमएस प्रोजेक्ट चार्ट व्यू को कैसे कॉन्फ़िगर किया जाए। Aspose.Tasks एक शक्तिशाली जावा एपीआई है जो आपको Microsoft प्रोजेक्ट फ़ाइलों के साथ प्रोग्रामेटिक रूप से काम करने की अनुमति देता है। इन चरणों का पालन करके, आप अपने प्रोजेक्ट की आवश्यकताओं के अनुसार गैंट चार्ट दृश्य को अनुकूलित करने में सक्षम होंगे।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
1. जावा डेवलपमेंट किट (जेडीके): सुनिश्चित करें कि आपके सिस्टम पर जावा स्थापित है।
2.  Aspose.Tasks लाइब्रेरी: Aspose.Tasks लाइब्रेरी डाउनलोड और इंस्टॉल करें। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/java/).
3. एकीकृत विकास पर्यावरण (आईडीई): अपनी पसंद का एक आईडीई चुनें। यह ट्यूटोरियल IntelliJ IDEA का उपयोग करता है, लेकिन आप अपनी सुविधानुसार किसी भी IDE का उपयोग कर सकते हैं।
## पैकेज आयात करें
सबसे पहले, आपको अपने जावा प्रोजेक्ट में Aspose.Tasks के साथ काम करने के लिए आवश्यक पैकेज आयात करने होंगे। अपनी जावा फ़ाइल में निम्नलिखित आयात विवरण जोड़ें:
```java
import com.aspose.tasks.*;
```
अब, आइए गैंट एमएस प्रोजेक्ट चार्ट व्यू को चरण-दर-चरण निर्देशों में कॉन्फ़िगर करने की प्रक्रिया को तोड़ें:
## चरण 1: डेटा निर्देशिका सेट करें
```java
String dataDir = "Your Data Directory";
```
 प्रतिस्थापित करें`"Your Data Directory"` आपके प्रोजेक्ट डेटा निर्देशिका के पथ के साथ।
## चरण 2: प्रोजेक्ट फ़ाइल लोड करें
```java
Project project = new Project(dataDir + "project.mpp");
```
अपनी प्रोजेक्ट फ़ाइल लोड करें (`project.mpp` इस उदाहरण में) का उपयोग करके`Project` Aspose.Tasks से कक्षा।
## चरण 3: नई गतिविधि जोड़ें
```java
Task task = project.getRootTask().getChildren().add("New Activity");
```
 का उपयोग करके अपने प्रोजेक्ट में एक नया कार्य बनाएं`Task` कक्षा बनाएं और इसे मूल कार्य के बच्चों में जोड़ें।
## चरण 4: कस्टम विशेषता को परिभाषित करें
```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```
 का उपयोग करके एक नई कस्टम विशेषता परिभाषित करें`ExtendedAttributeDefinition`क्लास बनाएं और इसे प्रोजेक्ट की विस्तारित विशेषताओं में जोड़ें।
## चरण 5: कार्य में कस्टम विशेषता जोड़ें
```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```
 का उपयोग करके बनाए गए कार्य में कस्टम विशेषता जोड़ें`createExtendedAttribute` तरीका।
## चरण 6: तालिका अनुकूलित करें
```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```
निर्दिष्ट चौड़ाई, शीर्षक और संरेखण के साथ टेक्स्ट विशेषता फ़ील्ड जोड़कर तालिका को अनुकूलित करें।
## चरण 7: प्रोजेक्ट सहेजें
```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```
कॉन्फ़िगर गैंट एमएस प्रोजेक्ट चार्ट व्यू के साथ प्रोजेक्ट को सहेजें। परिणामी फ़ाइल को Microsoft Project 2010 में खोला जा सकता है।
## निष्कर्ष
बधाई हो! आपने जावा का उपयोग करके Aspose.Tasks प्रोजेक्ट में गैंट एमएस प्रोजेक्ट चार्ट व्यू को सफलतापूर्वक कॉन्फ़िगर किया है। अब आप प्रोजेक्ट विशेषताओं को अनुकूलित कर सकते हैं और उन्हें अपने प्रोजेक्ट की आवश्यकताओं के अनुसार गैंट चार्ट में विज़ुअलाइज़ कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या मैं अन्य प्रोग्रामिंग भाषाओं के साथ Aspose.Tasks का उपयोग कर सकता हूँ?
उत्तर: हां, Aspose.Tasks .NET, Java और C सहित कई प्रोग्रामिंग भाषाओं के लिए उपलब्ध है++.
### प्रश्न: क्या Aspose.Tasks के लिए कोई निःशुल्क परीक्षण उपलब्ध है?
 उत्तर: हाँ, आप नि:शुल्क परीक्षण डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/).
### प्रश्न: मुझे Aspose.Tasks के लिए समर्थन कहां मिल सकता है?
उ: आप सहायता पा सकते हैं और प्रश्न पूछ सकते हैं[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15).
### प्रश्न: मैं Aspose.Tasks के लिए लाइसेंस कैसे खरीद सकता हूं?
 उ: आप यहां से लाइसेंस खरीद सकते हैं[यहाँ](https://purchase.aspose.com/buy).
### प्रश्न: क्या मुझे परीक्षण उद्देश्यों के लिए अस्थायी लाइसेंस की आवश्यकता है?
 उत्तर: हां, आप यहां से अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
