---
title: Aspose.Tasks परियोजनाओं में मुद्रा गुण पढ़ें
linktitle: Aspose.Tasks परियोजनाओं में मुद्रा गुण पढ़ें
second_title: Aspose.Tasks जावा एपीआई
description: जावा के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट फ़ाइलों से मुद्रा जानकारी निकालने का तरीका जानें। चरण-दर-चरण मार्गदर्शिका प्रदान की गई.
weight: 10
url: /hi/java/currency-properties/read-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks परियोजनाओं में मुद्रा गुण पढ़ें

## परिचय
इस ट्यूटोरियल में, हम सीखेंगे कि माइक्रोसॉफ्ट प्रोजेक्ट फाइलों से मुद्रा गुणों को पढ़ने के लिए जावा के लिए Aspose.Tasks का उपयोग कैसे करें। Aspose.Tasks एक शक्तिशाली जावा एपीआई है जो डेवलपर्स को Microsoft प्रोजेक्ट को स्थापित करने की आवश्यकता के बिना Microsoft प्रोजेक्ट दस्तावेज़ों में हेरफेर करने में सक्षम बनाता है। नीचे दिए गए चरणों का पालन करके, आप मुद्रा से संबंधित जानकारी आसानी से निकालने में सक्षम होंगे।
## आवश्यक शर्तें
इस ट्यूटोरियल के साथ आगे बढ़ने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
1. जावा डेवलपमेंट किट (जेडीके): सुनिश्चित करें कि आपके सिस्टम पर जेडीके स्थापित है।
2.  जावा JAR के लिए Aspose.Tasks: जावा लाइब्रेरी के लिए Aspose.Tasks को यहां से डाउनलोड करें[यहाँ](https://releases.aspose.com/tasks/java/) और इसे अपने जावा प्रोजेक्ट में शामिल करें।
## पैकेज आयात करें
अपने जावा क्लास में आवश्यक पैकेज आयात करके शुरुआत करें:
```java
import com.aspose.tasks.*;
```
## चरण 1: अपनी परियोजना निर्देशिका सेट करें
सबसे पहले, अपनी प्रोजेक्ट निर्देशिका सेट करें जहाँ आपकी Microsoft प्रोजेक्ट फ़ाइल स्थित है। आप इस निर्देशिका पथ को इस प्रकार परिभाषित कर सकते हैं:
```java
String dataDir = "Your Data Directory";
```
 प्रतिस्थापित करें`"Your Data Directory"` आपकी प्रोजेक्ट निर्देशिका के वास्तविक पथ के साथ।
## चरण 2: एक प्रोजेक्ट रीडर इंस्टेंस बनाएं
 त्वरित करें ए`Project` अपनी Microsoft प्रोजेक्ट फ़ाइल का पथ प्रदान करके ऑब्जेक्ट करें:
```java
Project project = new Project(dataDir + "project.mpp");
```
 प्रतिस्थापित करना सुनिश्चित करें`"project.mpp"` आपकी एमएस प्रोजेक्ट फ़ाइल के नाम के साथ।
## चरण 3: मुद्रा गुण प्रदर्शित करें
प्रोजेक्ट फ़ाइल से मुद्रा गुण पुनर्प्राप्त करें और प्रदर्शित करें:
```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position" + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```
यह कोड खंड एमएस प्रोजेक्ट फ़ाइल से मुद्रा कोड, अंक, प्रतीक और प्रतीक स्थिति जैसी जानकारी प्राप्त करता है और उन्हें कंसोल पर प्रिंट करता है।
## चरण 4: प्रक्रिया पूर्ण करना
अंत में, प्रक्रिया के सफल समापन का संकेत देने वाला एक संदेश प्रिंट करें:
```java
System.out.println("Process completed Successfully");
```
## निष्कर्ष
इस ट्यूटोरियल में, हमने पता लगाया कि जावा के लिए Aspose.Tasks का उपयोग करके Microsoft प्रोजेक्ट फ़ाइलों से मुद्रा गुणों को कैसे पढ़ा जाए। उल्लिखित चरणों का पालन करके, आप आसानी से अपने प्रोजेक्ट फ़ाइलों से मुद्रा-संबंधित जानकारी प्रोग्रामेटिक रूप से निकाल सकते हैं, जिससे आपके जावा अनुप्रयोगों में निर्बाध एकीकरण सक्षम हो सकता है।
## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या Aspose.Tasks माइक्रोसॉफ्ट प्रोजेक्ट के सभी संस्करणों के साथ संगत है?
उत्तर: Aspose.Tasks Microsoft Project के विभिन्न संस्करणों का समर्थन करता है, जिसमें MS Project 2003-2021 द्वारा उत्पन्न MPP फ़ाइलें भी शामिल हैं।
### प्रश्न: क्या मैं Aspose.Tasks का उपयोग करके मुद्रा गुणों को संशोधित कर सकता हूँ?
उत्तर: हाँ, Aspose.Tasks आपको एमएस प्रोजेक्ट फ़ाइलों में मुद्रा गुणों को प्रोग्रामेटिक रूप से पढ़ने और संशोधित करने की अनुमति देता है।
### प्रश्न: क्या Aspose.Tasks व्यावसायिक उपयोग के लिए उपयुक्त है?
 उत्तर: हां, Aspose.Tasks एक व्यावसायिक लाइब्रेरी है जिसे व्यावसायिक उपयोग के लिए डिज़ाइन किया गया है। आप लाइसेंस खरीद सकते हैं[यहाँ](https://purchase.aspose.com/buy).
### प्रश्न: क्या Aspose.Tasks निःशुल्क परीक्षण की पेशकश करता है?
 उत्तर: हाँ, आप Aspose.Tasks के निःशुल्क परीक्षण का लाभ उठा सकते हैं[यहाँ](https://releases.aspose.com/).
### प्रश्न: मैं Aspose.Tasks के लिए सहायता या सहायता कहां से मांग सकता हूं?
 उत्तर: आप Aspose.Tasks फोरम पर जा सकते हैं[यहाँ](https://forum.aspose.com/c/tasks/15) किसी भी सहायता या प्रश्न के लिए।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
