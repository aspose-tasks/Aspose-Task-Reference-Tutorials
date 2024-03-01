---
title: Aspose.Tasks में CSV, टेक्स्ट और टेम्पलेट के रूप में सहेजें
linktitle: Aspose.Tasks में CSV, टेक्स्ट और टेम्पलेट के रूप में सहेजें
second_title: Aspose.Tasks जावा एपीआई
description: जावा के लिए Aspose.Tasks का उपयोग करके Microsoft प्रोजेक्ट फ़ाइलों को CSV, टेक्स्ट और टेम्पलेट स्वरूपों में सहेजना सीखें।
type: docs
weight: 16
url: /hi/java/project-file-operations/save-csv-text-template/
---
## परिचय
इस ट्यूटोरियल में, हम जावा के लिए Aspose.Tasks का उपयोग करके प्रोजेक्ट फ़ाइलों को CSV, टेक्स्ट और टेम्पलेट जैसे विभिन्न प्रारूपों में सहेजने का तरीका जानेंगे। Aspose.Tasks एक शक्तिशाली जावा लाइब्रेरी है जो डेवलपर्स को Microsoft प्रोजेक्ट स्थापित करने की आवश्यकता के बिना Microsoft प्रोजेक्ट फ़ाइलों के साथ काम करने की अनुमति देती है।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
1. आपके सिस्टम पर जावा डेवलपमेंट किट (जेडीके) स्थापित है।
2.  जावा लाइब्रेरी के लिए Aspose.Tasks को आपके जावा प्रोजेक्ट में डाउनलोड और कॉन्फ़िगर किया गया है। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/java/).
3. जावा प्रोग्रामिंग भाषा का बुनियादी ज्ञान।

## पैकेज आयात करें
सबसे पहले, आपको अपनी जावा फ़ाइल में आवश्यक पैकेज आयात करने होंगे:
```java
import java.io.IOException;
import com.aspose.tasks.*;
```
## प्रोजेक्ट को सीएसवी के रूप में सहेजें
आइए किसी प्रोजेक्ट को CSV के रूप में सहेजने के चरणों का विवरण दें:
### चरण 1: प्रोजेक्ट लोड करें
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### चरण 2: सीएसवी के रूप में सहेजें
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```
## प्रोजेक्ट को टेक्स्ट के रूप में सहेजें
यहां बताया गया है कि आप किसी प्रोजेक्ट को टेक्स्ट के रूप में कैसे सहेज सकते हैं:
### चरण 1: प्रोजेक्ट लोड करें
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### चरण 2: टेक्स्ट के रूप में सहेजें
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```
## प्रोजेक्ट को टेम्पलेट के रूप में सहेजें
किसी प्रोजेक्ट को टेम्पलेट के रूप में सहेजने में निम्नलिखित चरण शामिल हैं:
### चरण 1: प्रोजेक्ट लोड करें
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### चरण 2: टेम्पलेट विकल्प सेट करें
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```
### चरण 3: टेम्पलेट के रूप में सहेजें
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि जावा के लिए Aspose.Tasks का उपयोग करके Microsoft प्रोजेक्ट फ़ाइलों को CSV, टेक्स्ट और टेम्पलेट के रूप में कैसे सहेजा जाए। इन सरल चरणों के साथ, आप जावा डेवलपर के रूप में अपनी उत्पादकता को बढ़ाते हुए, विभिन्न प्रारूपों में अपनी प्रोजेक्ट फ़ाइलों को कुशलतापूर्वक प्रबंधित कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या जावा के लिए Aspose.Tasks जटिल प्रोजेक्ट फ़ाइलों को संभाल सकता है?
उत्तर: बिल्कुल! जावा के लिए Aspose.Tasks माइक्रोसॉफ्ट प्रोजेक्ट फ़ाइल स्वरूपों के लिए व्यापक समर्थन प्रदान करते हुए, अलग-अलग जटिलता की परियोजनाओं को आसानी से संभाल सकता है।
### प्रश्न: क्या जावा के लिए Aspose.Tasks का कोई परीक्षण संस्करण उपलब्ध है?
 उत्तर: हाँ, आप जावा के लिए Aspose.Tasks का निःशुल्क परीक्षण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/).
### प्रश्न: मुझे जावा के लिए Aspose.Tasks के लिए समर्थन कहां मिल सकता है?
 उत्तर: आप यहां जा सकते हैं[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15) जावा के लिए Aspose.Tasks के संबंध में किसी भी सहायता या प्रश्न के लिए।
### प्रश्न: क्या मैं जावा के लिए Aspose.Tasks के लिए एक अस्थायी लाइसेंस खरीद सकता हूँ?
 उत्तर: हां, आप यहां से अस्थायी लाइसेंस खरीद सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/), आपको पुस्तकालय की पूरी क्षमता का मूल्यांकन करने की अनुमति देता है।
### प्रश्न: क्या जावा के लिए Aspose.Tasks विभिन्न ऑपरेटिंग सिस्टम के साथ संगत है?
उत्तर: हां, जावा के लिए Aspose.Tasks विंडोज़, मैकओएस और लिनक्स सहित विभिन्न ऑपरेटिंग सिस्टम के साथ संगत है।