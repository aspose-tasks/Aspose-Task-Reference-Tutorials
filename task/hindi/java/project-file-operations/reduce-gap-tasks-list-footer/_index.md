---
title: Aspose.Tasks में कार्य सूची और पाद लेख के बीच अंतर को कम करना
linktitle: Aspose.Tasks में कार्य सूची और पाद लेख के बीच अंतर को कम करना
second_title: Aspose.Tasks जावा एपीआई
description: जावा के लिए Aspose.Tasks का उपयोग करके MS प्रोजेक्ट कार्य सूचियों और फ़ुटर के बीच अंतर को कम करना सीखें। प्रोजेक्ट दस्तावेज़ लेआउट को सहजता से अनुकूलित करें।
type: docs
weight: 10
url: /hi/java/project-file-operations/reduce-gap-tasks-list-footer/
---
## परिचय
इस ट्यूटोरियल में, हम जावा के लिए Aspose.Tasks का उपयोग करके Microsoft प्रोजेक्ट फ़ाइलों में कार्य सूची और पादलेख के बीच के अंतर को कम करने पर चर्चा करेंगे। इन चरणों का पालन करके, आप आसानी से अपने प्रोजेक्ट दस्तावेज़ों के लेआउट को अनुकूलित करने में सक्षम होंगे।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यकताएँ हैं:
1. जावा डेवलपमेंट किट (जेडीके): सुनिश्चित करें कि आपके सिस्टम पर जेडीके स्थापित है।
2.  जावा लाइब्रेरी के लिए Aspose.Tasks: जावा लाइब्रेरी के लिए Aspose.Tasks को डाउनलोड करें और अपने प्रोजेक्ट में शामिल करें। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/java/).

## पैकेज आयात करें
कोडिंग भाग में गोता लगाने से पहले, आइए आवश्यक पैकेज आयात करें:
```java
import com.aspose.tasks.HtmlSaveOptions;
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PageSize;
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```
## चरण 1: अपनी डेटा निर्देशिका को पथ प्रदान करें
```java
String dataDir = "Your Data Directory";
```
 प्रतिस्थापित करना सुनिश्चित करें`"Your Data Directory"` आपकी वास्तविक डेटा निर्देशिका के पथ के साथ जहां आपकी Microsoft प्रोजेक्ट फ़ाइल (`HomeMovePlan.mpp` इस उदाहरण में) स्थित है.
## चरण 2: एमपीपी फ़ाइल पढ़ें
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
 कोड की यह पंक्ति नामित Microsoft प्रोजेक्ट फ़ाइल को पढ़ती है`HomeMovePlan.mpp`.
## चरण 3: ImageSaveOptions सेट करें
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```
 छवि बचत विकल्प, सेटिंग कॉन्फ़िगर करें`ReduceFooterGap` को`true` कार्य सूची और पाद लेख के बीच अंतर को कम करने के लिए।
## चरण 4: छवि के रूप में सहेजें
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```
कॉन्फ़िगर विकल्पों के साथ प्रोजेक्ट को एक छवि के रूप में सहेजें।
## चरण 5: PdfSaveOptions सेट करें
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```
 पीडीएफ बचत विकल्पों को परिभाषित करें, सेट करना सुनिश्चित करें`ReduceFooterGap` को`true`.
## चरण 6: पीडीएफ के रूप में सहेजें
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```
कॉन्फ़िगर किए गए विकल्पों के साथ प्रोजेक्ट को पीडीएफ के रूप में सहेजें।
## चरण 7: HtmlSaveOptions सेट करें
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // सत्य पर सेट करें
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```
 HTML बचत विकल्प, सेटिंग निर्दिष्ट करें`ReduceFooterGap` को`true`.
## चरण 8: HTML के रूप में सहेजें
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```
कॉन्फ़िगर किए गए विकल्पों के साथ प्रोजेक्ट को HTML फ़ाइल के रूप में सहेजें।

## निष्कर्ष
निष्कर्षतः, Microsoft प्रोजेक्ट फ़ाइलों में कार्य सूची और पादलेख के बीच अंतर को कम करना जावा के लिए Aspose.Tasks के साथ एक सीधी प्रक्रिया है। इस ट्यूटोरियल में बताए गए चरणों का पालन करके, आप अपने प्रोजेक्ट दस्तावेज़ों के लेआउट को कुशलतापूर्वक अनुकूलित कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### प्रश्न: क्या Aspose.Tasks माइक्रोसॉफ्ट प्रोजेक्ट के सभी संस्करणों के साथ संगत है?

उत्तर: Aspose.Tasks विभिन्न संस्करणों में अनुकूलता सुनिश्चित करते हुए Microsoft Project 2003-2019 प्रारूपों का समर्थन करता है।

### प्रश्न: क्या मैं अपने प्रोजेक्ट दस्तावेज़ों में पाद लेख के स्वरूप को अनुकूलित कर सकता हूँ?

उत्तर: हां, Aspose.Tasks फ़ुटर्स की उपस्थिति को अनुकूलित करने के लिए व्यापक विकल्प प्रदान करता है, जिसमें अंतराल को कम करना और सामग्री प्लेसमेंट को समायोजित करना शामिल है।

### प्रश्न: क्या Aspose.Tasks पीएनजी, पीडीएफ और HTML के अलावा अन्य प्रारूपों में परियोजनाओं को सहेजने का समर्थन करता है?

उत्तर: हाँ, Aspose.Tasks XLSX, XML और MPP सहित अन्य प्रारूपों की एक विस्तृत श्रृंखला का समर्थन करता है।

### प्रश्न: क्या Aspose.Tasks के लिए कोई परीक्षण संस्करण उपलब्ध है?

 उत्तर: हां, आप Aspose.Tasks का निःशुल्क परीक्षण संस्करण यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/).

### प्रश्न: यदि Aspose.Tasks का उपयोग करते समय मुझे कोई समस्या आती है तो मुझे कहां से सहायता मिल सकती है?

 उत्तर: आप Aspose.Tasks समुदाय मंच से सहायता प्राप्त कर सकते हैं[यहाँ](https://forum.aspose.com/c/tasks/15).