---
title: Aspose.Tasks में MS प्रोजेक्ट आउटलाइन कोड पुनर्प्राप्त करें
linktitle: Aspose.Tasks में रूपरेखा कोड पुनः प्राप्त करें
second_title: Aspose.Tasks जावा एपीआई
description: जावा के लिए Aspose.Tasks का उपयोग करके प्रोग्रामेटिक रूप से Microsoft प्रोजेक्ट आउटलाइन कोड पुनर्प्राप्त करना सीखें। अपनी परियोजना प्रबंधन क्षमताओं को बढ़ाएँ।
weight: 15
url: /hi/java/project-file-operations/retrieve-outline-codes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में MS प्रोजेक्ट आउटलाइन कोड पुनर्प्राप्त करें

## परिचय
इस ट्यूटोरियल में, हम सीखेंगे कि जावा के लिए Aspose.Tasks का उपयोग करके Microsoft प्रोजेक्ट आउटलाइन कोड कैसे पुनर्प्राप्त करें। एमएस प्रोजेक्ट में आउटलाइन कोड प्रोजेक्ट कार्यों, संसाधनों और असाइनमेंट को वर्गीकृत और व्यवस्थित करने का एक संरचित तरीका प्रदान करते हैं। Aspose.Tasks एक शक्तिशाली जावा लाइब्रेरी है जो डेवलपर्स को Microsoft प्रोजेक्ट फ़ाइलों को प्रोग्रामेटिक रूप से हेरफेर और प्रबंधित करने की अनुमति देती है।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ स्थापित हैं:
### 1. जावा विकास पर्यावरण
सुनिश्चित करें कि आपके सिस्टम पर जावा डेवलपमेंट किट (जेडीके) स्थापित है। आप Oracle वेबसाइट से JDK डाउनलोड और इंस्टॉल कर सकते हैं।
### 2. Aspose.कार्य लाइब्रेरी
 Aspose.Tasks लाइब्रेरी को डाउनलोड करें और अपने जावा प्रोजेक्ट में शामिल करें। आप लाइब्रेरी को यहां से डाउनलोड कर सकते हैं[जावा डाउनलोड पेज के लिए Aspose.Tasks](https://releases.aspose.com/tasks/java/).
## पैकेज आयात करें
सबसे पहले, अपने जावा कोड में Aspose.Tasks से आवश्यक पैकेज आयात करें:
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```
आइए अब दिए गए उदाहरण कोड को कई चरणों में तोड़ें:
## चरण 1: प्रोजेक्ट लोड करें
```java
String projectName = "ProjectFile.mpp";
Project project = new Project(projectName);
```
 इस चरण में, हम Microsoft प्रोजेक्ट फ़ाइल को एक में लोड करते हैं`Project` दिए गए फ़ाइल नाम का उपयोग करके ऑब्जेक्ट करें।
## चरण 2: रूपरेखा कोड पुनः प्राप्त करें
```java
for (OutlineCodeDefinition ocd : project.getOutlineCodes()) {
```
हम प्रोजेक्ट में प्रत्येक आउटलाइन कोड परिभाषा को दोहराते हैं।
## चरण 3: आउटलाइन कोड गुणों तक पहुंचें
```java
System.out.println("Alias = " + ocd.getAlias());
System.out.println("Field Id = " + ocd.getFieldId());
System.out.println("Field Name = " + ocd.getFieldName());
```
हम रूपरेखा कोड परिभाषा के विभिन्न गुणों जैसे उपनाम, फ़ील्ड आईडी और फ़ील्ड नाम को पुनर्प्राप्त और प्रिंट करते हैं।
## चरण 4: एंटरप्राइज़ कस्टम कोड की जाँच करें
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
हम जाँचते हैं कि क्या आउटलाइन कोड एक एंटरप्राइज़ कस्टम कोड है और तदनुसार परिणाम प्रिंट करते हैं।
## चरण 5: आउटलाइन कोड मास्क प्रदर्शित करें
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
हम आउटलाइन कोड से जुड़े प्रत्येक मास्क को दोहराते हैं और उसके स्तर और मास्क मूल्य को प्रिंट करते हैं।
## चरण 6: रूपरेखा कोड मान प्रदर्शित करें
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
हम प्रत्येक आउटलाइन कोड मान को दोहराते हैं और उसका विवरण, मान आईडी, मान और प्रकार प्रिंट करते हैं।
## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा है कि जावा के लिए Aspose.Tasks का उपयोग करके एमएस प्रोजेक्ट आउटलाइन कोड कैसे प्राप्त करें। दिए गए चरणों का पालन करके, आप उन्नत परियोजना प्रबंधन क्षमताओं को सक्षम करते हुए, अपने जावा अनुप्रयोगों में रूपरेखा कोड तक प्रभावी ढंग से पहुंच और हेरफेर कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### Q1: क्या मैं प्रोजेक्ट फ़ाइल में आउटलाइन कोड को संशोधित करने के लिए जावा के लिए Aspose.Tasks का उपयोग कर सकता हूँ?
उत्तर: हां, जावा के लिए Aspose.Tasks एमएस प्रोजेक्ट फ़ाइलों में आउटलाइन कोड को प्रोग्रामेटिक रूप से संशोधित करने के लिए एपीआई प्रदान करता है।
### Q2: क्या जावा के लिए Aspose.Tasks के लिए कोई परीक्षण संस्करण उपलब्ध है?
 उत्तर: हां, आप जावा के लिए Aspose.Tasks का निःशुल्क परीक्षण संस्करण यहां से डाउनलोड कर सकते हैं[Aspose.कार्य वेबसाइट](https://releases.aspose.com/).
### Q3: मैं जावा के लिए Aspose.Tasks के लिए तकनीकी सहायता कैसे प्राप्त कर सकता हूं?
 उत्तर: आप पर जाकर तकनीकी सहायता प्राप्त कर सकते हैं[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15) और वहां अपने प्रश्न पोस्ट कर रहे हैं।
### Q4: क्या मैं जावा के लिए Aspose.Tasks के लिए एक अस्थायी लाइसेंस खरीद सकता हूँ?
 उ: हां, आप जावा के लिए Aspose.Tasks के लिए एक अस्थायी लाइसेंस खरीद सकते हैं[खरीद पृष्ठ](https://purchase.aspose.com/temporary-license/).
### Q5: मैं जावा के लिए Aspose.Tasks के लिए संपूर्ण दस्तावेज़ कहां पा सकता हूं?
 ए: आप इसका उल्लेख कर सकते हैं[प्रलेखन](https://reference.aspose.com/tasks/java/) जावा के लिए Aspose.Tasks का उपयोग करने के बारे में विस्तृत जानकारी के लिए।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
