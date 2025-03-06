---
title: Aspose.Tasks में समूह परिभाषा डेटा पढ़ें
linktitle: Aspose.Tasks में समूह परिभाषा डेटा पढ़ें
second_title: Aspose.Tasks जावा एपीआई
description: जावा के लिए Aspose.Tasks का उपयोग करके Microsoft प्रोजेक्ट फ़ाइलों से समूह परिभाषा डेटा को पढ़ना सीखें। हमारे चरण-दर-चरण ट्यूटोरियल का अनुसरण करें।
type: docs
weight: 10
url: /hi/java/project-data-reading/read-group-definition/
---
## परिचय
जावा के लिए Aspose.Tasks एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को Microsoft प्रोजेक्ट फ़ाइलों में आसानी से हेरफेर करने की अनुमति देती है। इस ट्यूटोरियल में, हम जावा के लिए Aspose.Tasks का उपयोग करके एक प्रोजेक्ट फ़ाइल से समूह परिभाषा डेटा को चरण दर चरण पढ़ने की प्रक्रिया के बारे में जानेंगे।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यकताएँ हैं:
1. जावा डेवलपमेंट किट (जेडीके): सुनिश्चित करें कि आपके सिस्टम पर जेडीके स्थापित है।
2.  जावा लाइब्रेरी के लिए Aspose.Tasks: जावा लाइब्रेरी के लिए Aspose.Tasks को डाउनलोड और इंस्टॉल करें[यहाँ](https://releases.aspose.com/tasks/java/).
3. एकीकृत विकास पर्यावरण (आईडीई): अपना पसंदीदा आईडीई चुनें जैसे कि इंटेलीज आईडीईए या एक्लिप्स।

## पैकेज आयात करें
सबसे पहले, जावा के लिए Aspose.Tasks के साथ काम शुरू करने के लिए आवश्यक पैकेज आयात करें।
```java
import com.aspose.tasks.*;
```
## चरण 1: अपनी डेटा निर्देशिका सेट करें
```java
String dataDir = "Your Data Directory";
```
 प्रतिस्थापित करें`"Your Data Directory"` आपकी प्रोजेक्ट फ़ाइल वाली निर्देशिका के पथ के साथ।
## चरण 2: प्रोजेक्ट फ़ाइल लोड करें
```java
Project project = new Project(dataDir + "project.mpp");
```
 का उपयोग करके अपनी प्रोजेक्ट फ़ाइल लोड करें`Project` क्लास कंस्ट्रक्टर, आपके प्रोजेक्ट फ़ाइल का पथ पास कर रहा है।
## चरण 3: कार्य समूह गणना पुनः प्राप्त करें
```java
System.out.println("Task Groups Count: " + project.getTaskGroups().size());
```
 का उपयोग करके प्रोजेक्ट में कार्य समूहों की गिनती पुनः प्राप्त करें`getTaskGroups()` तरीका।
## चरण 4: कार्य समूह की जानकारी पुनः प्राप्त करें
```java
Group taskGroup = project.getTaskGroups().toList().get(1);
System.out.println("Percent Complete:" + taskGroup.getName());
System.out.println("Group Criteria count: " + taskGroup.getGroupCriteria().size());
```
किसी विशिष्ट कार्य समूह के बारे में जानकारी प्राप्त करें, जैसे उसका नाम और समूह मानदंडों की गिनती।
## चरण 5: समूह मानदंड जानकारी पुनः प्राप्त करें
```java
GroupCriterion criterion = taskGroup.getGroupCriteria().toList().get(0);
System.out.println("Criterion Field: " + criterion.getField());
System.out.println("Criterion GroupOn: " + criterion.getGroupOn());
System.out.println("Criterion Cell Color: " + criterion.getCellColor());
System.out.println("Criterion Pattern: " + criterion.getPattern());
```
समूह मानदंड के बारे में जानकारी प्राप्त करें, जैसे फ़ील्ड, समूह पर, सेल रंग और पैटर्न।
## चरण 6: मूल समूह की जाँच करें
```java
if (taskGroup == criterion.getParentGroup())
    System.out.println("Parent Group is equval to task Group.");
```
जांचें कि क्या मूल समूह कार्य समूह के बराबर है।
## चरण 7: मानदंड की फ़ॉन्ट जानकारी पुनः प्राप्त करें
```java
System.out.println("Font Family Name: " + criterion.getFont().getFontFamily());
System.out.println("Font Size: " + criterion.getFont().getSize());
System.out.println("Font Style: " + criterion.getFont().getStyle());
System.out.println("Ascending/Descending: " + criterion.getAscending());
```
मानदंड के लिए फ़ॉन्ट जानकारी पुनर्प्राप्त करें, जैसे फ़ॉन्ट परिवार, आकार, शैली और सॉर्टिंग क्रम।

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि जावा के लिए Aspose.Tasks का उपयोग करके Microsoft प्रोजेक्ट फ़ाइल से समूह परिभाषा डेटा को कैसे पढ़ा जाए। इन चरणों का पालन करके, आप अपने जावा अनुप्रयोगों में कार्य समूह की जानकारी प्रभावी ढंग से निकाल और उपयोग कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या मैं प्रोजेक्ट फ़ाइलों को संशोधित करने के लिए जावा के लिए Aspose.Tasks का उपयोग कर सकता हूँ?
उत्तर: हाँ, जावा के लिए Aspose.Tasks Microsoft प्रोजेक्ट फ़ाइलों को प्रोग्रामेटिक रूप से पढ़ने और संशोधित करने दोनों के लिए व्यापक सुविधाएँ प्रदान करता है।
### प्रश्न: क्या जावा के लिए Aspose.Tasks Microsoft प्रोजेक्ट फ़ाइलों के सभी संस्करणों के साथ संगत है?
उ: जावा के लिए Aspose.Tasks एमपीपी और एक्सएमएल प्रारूपों सहित माइक्रोसॉफ्ट प्रोजेक्ट फ़ाइलों के विभिन्न संस्करणों का समर्थन करता है।
### प्रश्न: जावा के लिए Aspose.Tasks के साथ काम करते समय मैं त्रुटियों को कैसे संभाल सकता हूँ?
ए: आप फ़ाइल हेरफेर के दौरान होने वाले अपवादों को शानदार ढंग से संभालने के लिए ट्राई-कैच ब्लॉक का उपयोग करके त्रुटि प्रबंधन तंत्र को कार्यान्वित कर सकते हैं।
### प्रश्न: क्या जावा के लिए Aspose.Tasks प्रोजेक्ट डेटा को अन्य प्रारूपों में निर्यात करने के लिए समर्थन प्रदान करता है?
उ: हां, जावा के लिए Aspose.Tasks आपको प्रोजेक्ट डेटा को पीडीएफ, एक्सएलएसएक्स और सीएसवी जैसे प्रारूपों में निर्यात करने की अनुमति देता है।
### प्रश्न: जावा के लिए Aspose.Tasks के लिए मुझे अतिरिक्त संसाधन और समर्थन कहां मिल सकता है?
 उत्तर: आप यहां जा सकते हैं[जावा दस्तावेज़ीकरण के लिए Aspose.Tasks](https://reference.aspose.com/tasks/java/) व्यापक मार्गदर्शिकाओं के लिए और देखें[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15) सामुदायिक समर्थन के लिए.