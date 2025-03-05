---
title: Aspose.Tasks में PDF के रूप में सहेजें
linktitle: Aspose.Tasks में PDF के रूप में सहेजें
second_title: Aspose.Tasks जावा एपीआई
description: जावा के लिए Aspose.Tasks का उपयोग करके प्रोजेक्ट फ़ाइलों को पीडीएफ में परिवर्तित करना सीखें। कुशल रूपांतरण के लिए सरल कदम.
type: docs
weight: 17
url: /hi/java/project-file-operations/save-as-pdf/
---
## परिचय
इस ट्यूटोरियल में, हम जावा के लिए Aspose.Tasks का उपयोग करके किसी प्रोजेक्ट को पीडीएफ के रूप में सहेजने की प्रक्रिया में आपका मार्गदर्शन करेंगे। Aspose.Tasks के साथ, आप अनुकूलता और साझा करने में आसानी सुनिश्चित करते हुए अपनी प्रोजेक्ट फ़ाइलों को कुशलतापूर्वक पीडीएफ प्रारूप में परिवर्तित कर सकते हैं। आइए चरणों में गोता लगाएँ:
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
1. जावा डेवलपमेंट किट (जेडीके): सुनिश्चित करें कि आपके सिस्टम पर जेडीके स्थापित है।
2.  जावा लाइब्रेरी के लिए Aspose.Tasks: Aspose.Tasks लाइब्रेरी डाउनलोड और इंस्टॉल करें। आप डाउनलोड लिंक पा सकते हैं[यहाँ](https://releases.aspose.com/tasks/java/).
3. एक प्रोजेक्ट फ़ाइल: एक प्रोजेक्ट फ़ाइल (उदाहरण के लिए, HomeMovePlan.mpp) तैयार रखें जिसे आप पीडीएफ में कनवर्ट करना चाहते हैं।

## पैकेज आयात करें
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
```
## चरण 1: इनपुट प्रोजेक्ट फ़ाइल पढ़ें
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
 सुनिश्चित करें कि आप प्रतिस्थापित करें`"Your Data Directory"` प्रोजेक्ट फ़ाइल वाली आपकी डेटा निर्देशिका के पथ के साथ।
## चरण 2: प्रोजेक्ट को पीडीएफ के रूप में सहेजें
```java
project.save(dataDir + "Project5.pdf", SaveFileFormat.Pdf);
```
यह कोड स्निपेट प्रोजेक्ट को "Project5.pdf" नाम से एक पीडीएफ फ़ाइल के रूप में सहेजता है।
## चरण 3: सामग्री को सेल आकार में फ़िट करना
```java
Project project1 = new Project(dataDir + "project6.mpp");
SaveOptions o = new PdfSaveOptions();
o.setFitContent(true);
o.setTimescale(Timescale.Months);
o.setPresentationFormat(PresentationFormat.TaskUsage);
```
यहां, हम पीडीएफ को सहेजने के लिए विकल्प निर्धारित करते हैं, जिसमें फिटिंग सामग्री, टाइमस्केल और प्रस्तुति प्रारूप शामिल हैं।
## चरण 4: किंवदंतियाँ छिपाएँ
```java
o.setLegendOnEachPage(false);
```
यह चरण पीडीएफ के प्रत्येक पृष्ठ पर किंवदंतियों को छुपाता है।
## चरण 5: प्रोजेक्ट को एप्लाइड विकल्पों के साथ सहेजें
```java
project1.save(dataDir + "result_months_WithoutLegend.pdf", o);
```
अंत में, यह कोड लागू विकल्पों के साथ प्रोजेक्ट को एक पीडीएफ फाइल में सहेजता है।

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि किसी प्रोजेक्ट को पीडीएफ के रूप में सहेजने के लिए जावा के लिए Aspose.Tasks का उपयोग कैसे करें। इन सरल चरणों का पालन करके, आप आसानी से साझा करने और वितरण के लिए अपनी प्रोजेक्ट फ़ाइलों को कुशलतापूर्वक परिवर्तित कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या Aspose.Tasks जावा के सभी संस्करणों के साथ संगत है?
उत्तर: हां, Aspose.Tasks JDK 6 और उससे ऊपर के जावा संस्करणों का समर्थन करता है।
### प्रश्न: क्या मैं पीडीएफ आउटपुट के स्वरूप को अनुकूलित कर सकता हूं?
उत्तर: बिल्कुल! Aspose.Tasks आपकी आवश्यकताओं के अनुसार पीडीएफ आउटपुट को अनुकूलित करने के लिए विभिन्न विकल्प प्रदान करता है।
### प्रश्न: क्या Aspose.Tasks रूपांतरण के लिए अन्य फ़ाइल स्वरूपों का समर्थन करता है?
उत्तर: हाँ, Aspose.Tasks MPP, XML, XLSX और अन्य सहित फ़ाइल स्वरूपों की एक विस्तृत श्रृंखला का समर्थन करता है।
### प्रश्न: क्या Aspose.Tasks के लिए कोई परीक्षण संस्करण उपलब्ध है?
 उत्तर: हाँ, आप Aspose.Tasks का निःशुल्क परीक्षण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/).
### प्रश्न: मुझे Aspose.Tasks के लिए सहायता कहाँ से मिल सकती है?
 उत्तर: समर्थन और सहायता के लिए, आप यहां जा सकते हैं[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15).