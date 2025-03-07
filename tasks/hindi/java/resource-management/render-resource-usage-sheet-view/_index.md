---
title: Aspose.Tasks में संसाधन उपयोग और शीट दृश्य प्रस्तुत करें
linktitle: Aspose.Tasks में संसाधन उपयोग और शीट दृश्य प्रस्तुत करें
second_title: Aspose.Tasks जावा एपीआई
description: जानें कि जावा के लिए Aspose.Tasks में MS प्रोजेक्ट संसाधन उपयोग और शीट दृश्य कैसे प्रस्तुत करें। विस्तृत पीडीएफ रिपोर्ट आसानी से तैयार करने के लिए हमारी चरण-दर-चरण मार्गदर्शिका का पालन करें।
weight: 16
url: /hi/java/resource-management/render-resource-usage-sheet-view/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में संसाधन उपयोग और शीट दृश्य प्रस्तुत करें

## परिचय
इस ट्यूटोरियल में, हम सीखेंगे कि एमएस प्रोजेक्ट संसाधन उपयोग और शीट दृश्यों को प्रस्तुत करने के लिए जावा के लिए Aspose.Tasks का उपयोग कैसे करें। Aspose.Tasks एक शक्तिशाली जावा लाइब्रेरी है जो डेवलपर्स को Microsoft प्रोजेक्ट स्थापित करने की आवश्यकता के बिना Microsoft प्रोजेक्ट फ़ाइलों के साथ काम करने की अनुमति देती है।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें स्थापित और सेटअप हैं:
1. जावा डेवलपमेंट किट (जेडीके): सुनिश्चित करें कि आपके सिस्टम पर जावा डेवलपमेंट किट स्थापित है। आप Oracle वेबसाइट से JDK का नवीनतम संस्करण डाउनलोड और इंस्टॉल कर सकते हैं।
2.  जावा के लिए Aspose.Tasks: जावा लाइब्रेरी के लिए Aspose.Tasks को डाउनलोड और इंस्टॉल करें[डाउनलोड पेज](https://releases.aspose.com/tasks/java/).

## पैकेज आयात करें
सबसे पहले, आपको अपने जावा प्रोजेक्ट में आवश्यक पैकेज आयात करने होंगे:
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```
## चरण 1: स्रोत प्रोजेक्ट पढ़ें
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Data Directory";
// स्रोत प्रोजेक्ट पढ़ें
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```
इस चरण में, हम स्रोत प्रोजेक्ट फ़ाइल का पथ निर्दिष्ट करते हैं (`ResourceUsageView.mpp` ) और उपयोग करें`Project` इसे पढ़ने के लिए कक्षा.
## चरण 2: आवश्यक टाइमस्केल सेटिंग्स के साथ सेवऑप्शंस को परिभाषित करें
```java
// आवश्यक टाइमस्केल सेटिंग्स के साथ सेवऑप्शंस को दिनों के रूप में परिभाषित करें
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```
 यहां, हम परिभाषित करते हैं`SaveOptions` आवश्यक के साथ`TimeScale` समायोजन। इस उदाहरण में, हमने सेट किया है`TimeScale` आज का।
## चरण 3: प्रेजेंटेशन फॉर्मेट को रिसोर्सयूजेज पर सेट करें
```java
// प्रेजेंटेशन फॉर्मेट को रिसोर्सयूजेज पर सेट करें
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```
 हमने प्रेजेंटेशन फॉर्मेट को इस पर सेट किया है`ResourceUsage`, यह दर्शाता है कि हम संसाधन उपयोग दृश्य प्रस्तुत करना चाहते हैं।
## चरण 4: प्रोजेक्ट सहेजें
```java
// प्रोजेक्ट सहेजें
project.save(dataDir + days, options);
```
अंत में, हम निर्दिष्ट विकल्पों के साथ प्रोजेक्ट को सहेजते हैं। इस उदाहरण में, आउटपुट फ़ाइल को इस रूप में सहेजा जाएगा`result_days.pdf`.
## चरण 5: अन्य टाइमस्केल सेटिंग्स के लिए दृश्य प्रस्तुत करें
अलग-अलग टाइमस्केल सेटिंग्स (तीन महीने और महीने) के साथ दृश्य प्रस्तुत करने के लिए चरण 2 से 4 दोहराएं।
```java
// टाइमस्केल सेटिंग्स को थर्डऑफमंथ पर सेट करें
options.setTimescale(Timescale.ThirdsOfMonths);
// प्रोजेक्ट सहेजें
project.save(thirds, options);
// टाइमस्केल सेटिंग्स को महीनों पर सेट करें
options.setTimescale(Timescale.Months);
// प्रोजेक्ट सहेजें
project.save(dataDir + months, options);
```
 को बदलना सुनिश्चित करें`Timescale` प्रत्येक दृश्य के लिए तदनुसार सेटिंग्स।

## निष्कर्ष
इस ट्यूटोरियल में, हमने पता लगाया है कि MS प्रोजेक्ट संसाधन उपयोग और शीट दृश्यों को प्रस्तुत करने के लिए जावा के लिए Aspose.Tasks का उपयोग कैसे करें। ऊपर बताए गए चरणों का पालन करके, आप इन दृश्यों को पीडीएफ प्रारूप में कुशलतापूर्वक उत्पन्न कर सकते हैं, जिससे आपके प्रोजेक्ट डेटा के बेहतर विज़ुअलाइज़ेशन और विश्लेषण की सुविधा मिल सकती है।
## अक्सर पूछे जाने वाले प्रश्न
### क्या Aspose.Tasks संसाधन उपयोग और शीट के अलावा अन्य दृश्य प्रस्तुत कर सकता है?
Aspose.Tasks गैंट चार्ट, टास्क उपयोग और कैलेंडर दृश्य जैसे विभिन्न दृश्यों को प्रस्तुत करने का समर्थन करता है।
### क्या Aspose.Tasks Microsoft प्रोजेक्ट फ़ाइलों के विभिन्न संस्करणों के साथ संगत है?
हां, Aspose.Tasks एमपीपी, एमपीटी और एक्सएमएल प्रारूपों सहित माइक्रोसॉफ्ट प्रोजेक्ट फ़ाइल स्वरूपों की एक विस्तृत श्रृंखला का समर्थन करता है।
### क्या मैं Aspose.Tasks का उपयोग करके प्रस्तुत दृश्यों के स्वरूप को अनुकूलित कर सकता हूँ?
बिल्कुल! Aspose.Tasks आपकी विशिष्ट आवश्यकताओं के अनुरूप प्रस्तुत दृश्यों की उपस्थिति और लेआउट को अनुकूलित करने के लिए व्यापक विकल्प प्रदान करता है।
### क्या Aspose.Tasks के लिए सिस्टम पर Microsoft Project स्थापित होना आवश्यक है?
नहीं, Aspose.Tasks एक स्टैंडअलोन लाइब्रेरी है और इसके कामकाज के लिए Microsoft Project को स्थापित करने की आवश्यकता नहीं है।
### क्या Aspose.Tasks उपयोगकर्ताओं के लिए तकनीकी सहायता उपलब्ध है?
 हां, Aspose.Tasks उपयोगकर्ता इसके माध्यम से तकनीकी सहायता का लाभ उठा सकते हैं[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
