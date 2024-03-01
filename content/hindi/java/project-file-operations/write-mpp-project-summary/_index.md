---
title: Aspose.Tasks में MPP प्रोजेक्ट सारांश लिखें
linktitle: Aspose.Tasks में MPP प्रोजेक्ट सारांश लिखें
second_title: Aspose.Tasks जावा एपीआई
description: Aspose.Tasks का उपयोग करके जावा में MPP प्रोजेक्ट सारांश लिखना सीखें। प्रोजेक्ट जानकारी को सहजता से सेट करें और पुनः प्राप्त करें।
type: docs
weight: 27
url: /hi/java/project-file-operations/write-mpp-project-summary/
---
## परिचय
इस ट्यूटोरियल में, हम सीखेंगे कि एमपीपी प्रोजेक्ट सारांश लिखने के लिए जावा के लिए Aspose.Tasks का उपयोग कैसे करें। Aspose.Tasks Microsoft प्रोजेक्ट फ़ाइलों के साथ काम करने के लिए एक शक्तिशाली जावा लाइब्रेरी है। नीचे दिए गए चरणों का पालन करके, आप इस लाइब्रेरी का उपयोग करके किसी प्रोजेक्ट के बारे में विभिन्न सारांश जानकारी सेट और पुनर्प्राप्त करने में सक्षम होंगे।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यकताएँ हैं:
1. जावा डेवलपमेंट किट (जेडीके): सुनिश्चित करें कि आपके सिस्टम पर जेडीके स्थापित है।
2.  जावा के लिए Aspose.Tasks: जावा लाइब्रेरी के लिए Aspose.Tasks को डाउनलोड और इंस्टॉल करें। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/java/).
3. एकीकृत विकास पर्यावरण (आईडीई): जावा विकास के लिए अपना पसंदीदा आईडीई चुनें, जैसे इंटेलीजे आईडीईए, एक्लिप्स, या नेटबीन्स।

## पैकेज आयात करें
सबसे पहले, अपने जावा क्लास में आवश्यक पैकेज आयात करें:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```
## चरण 1: प्रोजेक्ट सेट करें और सारांश जानकारी परिभाषित करें
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Data Directory";
//अपनी प्रोजेक्ट फ़ाइल के पथ के साथ एक नया प्रोजेक्ट ऑब्जेक्ट प्रारंभ करें
Project project = new Project(dataDir + "project.mpp");
// प्रोजेक्ट के बारे में सारांश जानकारी सेट करें
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");
project.set(Prj.COMMENTS, "Comments");
// प्रोजेक्ट की निर्माण तिथि निर्धारित करें
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());
// प्रोजेक्ट के लिए कीवर्ड सेट करें
project.set(Prj.KEYWORDS, "MPP Aspose");
// प्रोजेक्ट की अंतिम मुद्रित तिथि निर्धारित करें
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```
## चरण 2: परियोजना सारांश जानकारी सहेजें
```java
// प्रोजेक्ट को वापस एमपीपी प्रारूप में सहेजें
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// एक सफलता संदेश प्रदर्शित करें
System.out.println("Process completed Successfully");
```
## चरण 3: परियोजना सारांश जानकारी पढ़ें
```java
// परियोजना सारांश जानकारी पढ़ना
project = new Project(dataDir + "MppAspose.xml");
// प्रोजेक्ट का प्रिंट लेखक
System.out.println("Author: " + project.get(Prj.AUTHOR));
// प्रोजेक्ट के अंतिम लेखक को प्रिंट करें
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// प्रोजेक्ट का पुनरीक्षण क्रमांक प्रिंट करें
System.out.println("Revision: " + project.get(Prj.REVISION));
// प्रोजेक्ट के कीवर्ड प्रिंट करें
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// प्रोजेक्ट की टिप्पणियाँ प्रिंट करें
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// प्रोजेक्ट की निर्माण तिथि प्रिंट करें
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// प्रोजेक्ट के कीवर्ड प्रिंट करें (फिर से)
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// प्रोजेक्ट की अंतिम मुद्रित तिथि प्रिंट करें
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने जावा के लिए Aspose.Tasks का उपयोग करके एमपीपी प्रोजेक्ट सारांश लिखने का तरीका बताया है। इन चरणों का पालन करके, आप अपनी प्रोजेक्ट फ़ाइलों के बारे में विभिन्न सारांश जानकारी कुशलतापूर्वक सेट और पुनर्प्राप्त कर सकते हैं। Aspose.Tasks जावा अनुप्रयोगों में Microsoft प्रोजेक्ट फ़ाइलों के साथ काम करने की प्रक्रिया को सरल बनाता है, मजबूत कार्यक्षमता और उपयोग में आसानी प्रदान करता है।
## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या मैं अन्य जावा लाइब्रेरीज़ के साथ जावा के लिए Aspose.Tasks का उपयोग कर सकता हूँ?
उत्तर: हां, आपकी परियोजना प्रबंधन क्षमताओं को बढ़ाने के लिए जावा के लिए Aspose.Tasks को अन्य जावा लाइब्रेरी के साथ सहजता से एकीकृत किया जा सकता है।
### प्रश्न: क्या जावा के लिए Aspose.Tasks का कोई परीक्षण संस्करण उपलब्ध है?
 उत्तर: हां, आप यहां से नि:शुल्क परीक्षण संस्करण डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/).
### प्रश्न: जावा के लिए Aspose.Tasks को कितनी बार अद्यतन किया जाता है?
उ: जावा और माइक्रोसॉफ्ट प्रोजेक्ट फ़ाइलों के नवीनतम संस्करणों के साथ संगतता सुनिश्चित करने के लिए जावा के लिए Aspose.Tasks को नियमित रूप से अपडेट किया जाता है।
### प्रश्न: क्या मैं परियोजना सारांश जानकारी को और अधिक अनुकूलित कर सकता हूँ?
उत्तर: बिल्कुल, जावा के लिए Aspose.Tasks आपकी विशिष्ट आवश्यकताओं के अनुसार प्रोजेक्ट सारांश जानकारी को अनुकूलित करने के लिए व्यापक विकल्प प्रदान करता है।
### प्रश्न: जावा के लिए Aspose.Tasks के लिए मुझे समर्थन कहां से मिल सकता है?
उत्तर: आप Aspose.Tasks समुदाय मंच से समर्थन प्राप्त कर सकते हैं[यहाँ](https://forum.aspose.com/c/tasks/15).