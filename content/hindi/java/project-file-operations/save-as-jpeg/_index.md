---
title: Aspose.Tasks में MS प्रोजेक्ट को JPEG के रूप में कनवर्ट करें
linktitle: Aspose.Tasks में प्रोजेक्ट को JPEG के रूप में सहेजें
second_title: Aspose.Tasks जावा एपीआई
description: जावा के लिए Aspose.Tasks का उपयोग करके Microsoft प्रोजेक्ट फ़ाइलों को आसानी से JPEG छवियों में परिवर्तित करना सीखें। अपनी उत्पादकता बढ़ाएँ.
type: docs
weight: 20
url: /hi/java/project-file-operations/save-as-jpeg/
---
## परिचय
इस ट्यूटोरियल में, हम देखेंगे कि जावा के लिए Aspose.Tasks का उपयोग करके Microsoft प्रोजेक्ट फ़ाइल को JPEG छवि के रूप में कैसे सहेजा जाए। यह प्रोजेक्ट विज़ुअलाइज़ेशन साझा करने या प्रोजेक्ट डेटा को रिपोर्ट या प्रस्तुतियों में एकीकृत करने के लिए विशेष रूप से उपयोगी हो सकता है।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
1.  जावा डेवलपमेंट किट (जेडीके): सुनिश्चित करें कि आपके सिस्टम पर जावा स्थापित है। आप यहां से नवीनतम संस्करण डाउनलोड और इंस्टॉल कर सकते हैं[जावा वेबसाइट](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  जावा के लिए Aspose.Tasks: दिए गए निर्देशों का पालन करके जावा के लिए Aspose.Tasks को डाउनलोड और सेट करें।[प्रलेखन](https://reference.aspose.com/tasks/java/).

## पैकेज आयात करें
सबसे पहले, अपनी जावा फ़ाइल में आवश्यक पैकेज आयात करें:
```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.IOException;
```
## चरण 1: डेटा निर्देशिका को परिभाषित करें
अपनी डेटा निर्देशिका के लिए पथ सेट करें जहां आपकी एमएस प्रोजेक्ट फ़ाइल स्थित है।
```java
String dataDir = "Your Data Directory";
```
## चरण 2: एमएस प्रोजेक्ट फ़ाइल लोड करें
Aspose.Tasks का उपयोग करके MS प्रोजेक्ट फ़ाइल लोड करें।
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
## चरण 3: JPEG गुणवत्ता कॉन्फ़िगर करें (वैकल्पिक)
 यदि आप JPEG गुणवत्ता को समायोजित करना चाहते हैं, तो आप इसका उपयोग करके इसे सेट कर सकते हैं`ImageSaveOptions` कक्षा। गुणवत्ता 0 से 100 तक होती है।
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Jpeg);
options.setJpegQuality(50); // JPEG गुणवत्ता को 50 पर सेट करें
```
## चरण 4: प्रोजेक्ट को JPEG के रूप में सहेजें
MS प्रोजेक्ट फ़ाइल को JPEG छवि के रूप में सहेजें।
```java
project.save(dataDir + "image_out.jpeg", options);
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि जावा के लिए Aspose.Tasks का उपयोग करके Microsoft प्रोजेक्ट फ़ाइल को JPEG छवि के रूप में कैसे सहेजा जाए। यह सुविधा विभिन्न दस्तावेज़ों और प्रस्तुतियों में प्रोजेक्ट डेटा को आसानी से साझा करने और एकीकरण करने की अनुमति देती है।
## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या मैं JPEG छवि की गुणवत्ता समायोजित कर सकता हूँ?
 उत्तर: हाँ, आप इसका उपयोग करके गुणवत्ता को समायोजित कर सकते हैं`setJpegQuality()` विधि, 0 से 100 तक की सीमा के साथ।
### प्रश्न: यदि मैं JPEG गुणवत्ता निर्दिष्ट नहीं करूँ तो क्या होगा?
उ: यदि आप गुणवत्ता निर्दिष्ट नहीं करते हैं, तो डिफ़ॉल्ट गुणवत्ता का उपयोग किया जाएगा।
### प्रश्न: क्या जावा के लिए Aspose.Tasks का उपयोग निःशुल्क है?
 उत्तर: जावा के लिए Aspose.Tasks एक व्यावसायिक लाइब्रेरी है, लेकिन आप नि:शुल्क परीक्षण के साथ इसकी सुविधाओं का पता लगा सकते हैं। दौरा करना[निःशुल्क परीक्षण पृष्ठ](https://releases.aspose.com/) अधिक जानकारी के लिए।
### प्रश्न: जावा के लिए Aspose.Tasks के लिए मुझे समर्थन कहां से मिल सकता है?
उत्तर: आप Aspose.Tasks समुदाय मंच से समर्थन प्राप्त कर सकते हैं[यहाँ](https://forum.aspose.com/c/tasks/15).
### प्रश्न: क्या मैं Aspose.Tasks के लिए अस्थायी लाइसेंस खरीद सकता हूँ?
 उत्तर: हां, आप यहां से अस्थायी लाइसेंस खरीद सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).