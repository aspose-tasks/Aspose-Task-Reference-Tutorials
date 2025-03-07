---
title: Aspose.Tasks में टास्क शीट प्रस्तुत करें
linktitle: Aspose.Tasks में टास्क शीट प्रस्तुत करें
second_title: Aspose.Tasks जावा एपीआई
description: जावा के लिए Aspose.Tasks के साथ कुशल परियोजना प्रबंधन को अनलॉक करें। कार्य पत्रक को निर्बाध रूप से प्रस्तुत करें। अब व्यापक गाइड का अन्वेषण करें!
weight: 27
url: /hi/java/task-properties/render-task-sheet/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में टास्क शीट प्रस्तुत करें

## परिचय
जावा के लिए Aspose.Tasks की दुनिया में आपका स्वागत है, एक शक्तिशाली लाइब्रेरी जो जावा डेवलपर्स को निर्बाध परियोजना प्रबंधन क्षमताओं के साथ सशक्त बनाती है। चाहे आप एक अनुभवी डेवलपर हों या नौसिखिया जो अपने प्रोजेक्ट प्रबंधन कौशल को बढ़ाना चाहते हों, यह मार्गदर्शिका आपको Aspose.Tasks का उपयोग करके कार्य पत्रक प्रस्तुत करने में मदद करेगी।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
1. जावा डेवलपमेंट किट (जेडीके): जावा प्रोग्राम निष्पादित करने के लिए जेडीके का नवीनतम संस्करण स्थापित करें।
2.  जावा लाइब्रेरी के लिए Aspose.Tasks: लाइब्रेरी डाउनलोड करें और सेटअप करें। आप इसे पा सकते हैं[यहाँ](https://releases.aspose.com/tasks/java/).
## पैकेज आयात करें
आरंभ करने के लिए, अपने जावा प्रोजेक्ट में आवश्यक पैकेज आयात करें। यह चरण आपके कोड में Aspose.Tasks कार्यात्मकताओं तक पहुँचने के लिए महत्वपूर्ण है।
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
```
## चरण 1: अपनी दस्तावेज़ निर्देशिका सेट करें
जावा कोड में अपनी दस्तावेज़ निर्देशिका के पथ को परिभाषित करके प्रारंभ करें। यह वह जगह है जहां आपकी प्रोजेक्ट फ़ाइल और रेंडर की गई टास्क शीट सहेजी जाएगी।
```java
String dataDir = "Your Document Directory";
```
## चरण 2: प्रोजेक्ट फ़ाइल लोड करें
Aspose.Tasks लाइब्रेरी का उपयोग करके अपनी प्रोजेक्ट फ़ाइल लोड करें। इस उदाहरण में, हम मानते हैं कि प्रोजेक्ट फ़ाइल का नाम "NewProductDev.mpp" है।
```java
Project project = new Project(dataDir + "NewProductDev.mpp");
```
## चरण 3: सहेजें विकल्प कॉन्फ़िगर करें
वांछित प्रस्तुति प्रारूप निर्दिष्ट करते हुए, सहेजें विकल्प कॉन्फ़िगर करें। इस मामले में, हम पीडीएफ प्रारूप में एक कार्य पत्रक तैयार करना चाहते हैं।
```java
SaveOptions options = new PdfSaveOptions();
options.setPresentationFormat(PresentationFormat.TaskSheet);
```
## चरण 4: प्रोजेक्ट को टास्क शीट के रूप में सहेजें
पीडीएफ प्रारूप में टास्क शीट तैयार करने के लिए निर्दिष्ट विकल्पों के साथ प्रोजेक्ट को सहेजें।
```java
project.save(dataDir + "taskSheet.pdf", options);
```
## चरण 5: परिणाम की समीक्षा करें
निर्दिष्ट निर्देशिका में संलग्न जनरेट की गई कार्य शीट की समीक्षा करें। आपके प्रोजेक्ट की टास्क शीट अब जावा के लिए Aspose.Tasks का उपयोग करके कुशलतापूर्वक प्रस्तुत की गई है।
## निष्कर्ष
जावा के लिए Aspose.Tasks कार्य पत्रक प्रस्तुत करने के लिए मजबूत सुविधाएँ प्रदान करके परियोजना प्रबंधन को सरल बनाता है। इस चरण-दर-चरण मार्गदर्शिका का पालन करके, आपने अपनी परियोजना प्रबंधन क्षमताओं को बढ़ाने के लिए Aspose.Tasks की शक्ति का उपयोग किया है।

## पूछे जाने वाले प्रश्न
### क्या Aspose.Tasks सभी जावा संस्करणों के साथ संगत है?
 हां, Aspose.Tasks जावा संस्करणों की एक विस्तृत श्रृंखला के साथ संगत है। को देखें[प्रलेखन](https://reference.aspose.com/tasks/java/) विशिष्ट विवरण के लिए.
### क्या मैं खरीदने से पहले Aspose.Tasks आज़मा सकता हूँ?
 बिल्कुल! निःशुल्क परीक्षण संस्करण का अन्वेषण करें[यहाँ](https://releases.aspose.com/).
### मुझे Aspose.Tasks के लिए समर्थन कहां मिल सकता है?
 Aspose.Tasks समुदाय में शामिल हों[मंच](https://forum.aspose.com/c/tasks/15) समर्थन और चर्चा के लिए.
### मैं Aspose.Tasks के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूँ?
 अपना अस्थायी लाइसेंस प्राप्त करें[यहाँ](https://purchase.aspose.com/temporary-license/).
### मैं जावा के लिए Aspose.Tasks कहां से खरीद सकता हूं?
 जावा के लिए Aspose.Tasks खरीदें[यहाँ](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
