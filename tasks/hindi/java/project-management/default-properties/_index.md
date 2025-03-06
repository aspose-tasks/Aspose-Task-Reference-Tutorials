---
title: Aspose.Tasks में MS प्रोजेक्ट गुणों को कुशलतापूर्वक प्रबंधित करें
linktitle: Aspose.Tasks में डिफ़ॉल्ट प्रोजेक्ट गुण प्रबंधित करें
second_title: Aspose.Tasks जावा एपीआई
description: जावा के लिए Aspose.Tasks का उपयोग करके डिफ़ॉल्ट MS प्रोजेक्ट गुणों को प्रबंधित करना सीखें। अपने प्रोजेक्ट प्रबंधन वर्कफ़्लो को सहजता से सुव्यवस्थित करें।
type: docs
weight: 11
url: /hi/java/project-management/default-properties/
---
## परिचय
क्या आप Java के लिए Aspose.Tasks के साथ अपनी परियोजना प्रबंधन प्रक्रिया को सुव्यवस्थित करना चाहते हैं? Microsoft प्रोजेक्ट फ़ाइलों में डिफ़ॉल्ट गुणों को प्रबंधित करने से दक्षता में उल्लेखनीय वृद्धि हो सकती है। इस ट्यूटोरियल में, हम Aspose.Tasks का उपयोग करके डिफ़ॉल्ट MS प्रोजेक्ट गुणों को प्रबंधित करने के तरीके के बारे में चरण-दर-चरण निर्देशों के माध्यम से चलेंगे।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में गहराई से जाएँ, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यकताएँ हैं:
### 1. जावा डेवलपमेंट किट (जेडीके)
   - सुनिश्चित करें कि JDK आपके सिस्टम पर स्थापित है।
   -  आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
### 2. जावा लाइब्रेरी के लिए Aspose.Tasks
   - जावा लाइब्रेरी के लिए Aspose.Tasks को डाउनलोड करें और अपने प्रोजेक्ट में शामिल करें।
   -  आप इसे यहां से डाउनलोड कर सकते हैं[वेबसाइट](https://releases.aspose.com/tasks/java/).
## पैकेज आयात करें
सबसे पहले, अपनी जावा फ़ाइल में आवश्यक पैकेज आयात करें:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```
आइए इस प्रक्रिया को प्रबंधनीय चरणों में विभाजित करें:
## चरण 1: प्रोजेक्ट फ़ाइल लोड करें
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
## चरण 2: डिफ़ॉल्ट गुण प्रदर्शित करें
```java
// डिफ़ॉल्ट गुण प्रदर्शित करें
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("New Task Default Start: " + project.get(Prj.DEFAULT_START_TIME));
System.out.println("New Task Default Type: " + project.get(Prj.DEFAULT_TASK_TYPE));
System.out.println("Resource Default Standard Rate: " + project.get(Prj.DEFAULT_STANDARD_RATE));
System.out.println("Resource Default Overtime Rate: " + project.get(Prj.DEFAULT_OVERTIME_RATE));
System.out.println("Default Task EV Method: " + project.get(Prj.DEFAULT_TASK_EV_METHOD));
System.out.println("Default Cost Accrual: " + project.get(Prj.DEFAULT_FIXED_COST_ACCRUAL));
```
## चरण 3: डिफ़ॉल्ट गुण सेट करें
```java
// डिफ़ॉल्ट गुण सेट करें
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.DEFAULT_START_TIME, project.get(Prj.START_DATE));
project.set(Prj.DEFAULT_TASK_TYPE, TaskType.FixedDuration);
project.set(Prj.DEFAULT_STANDARD_RATE, 15d);
project.set(Prj.DEFAULT_OVERTIME_RATE, 12d);
project.set(Prj.DEFAULT_TASK_EV_METHOD, EarnedValueMethodType.PercentComplete);
project.set(Prj.DEFAULT_FIXED_COST_ACCRUAL, CostAccrualType.Prorated);
```
## चरण 4: प्रोजेक्ट को XML प्रारूप में सहेजें
```java
// प्रोजेक्ट को XML प्रारूप में सहेजें
project.save(dataDir + "project4.xml", SaveFileFormat.Xml);
```
## चरण 5: परिणाम प्रदर्शित करें
```java
// रूपांतरण का परिणाम प्रदर्शित करें.
System.out.println("Process completed Successfully");
```
इन चरणों का पालन करके, आप Java के लिए Aspose.Tasks का उपयोग करके डिफ़ॉल्ट MS प्रोजेक्ट गुणों को कुशलतापूर्वक प्रबंधित कर सकते हैं।
## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि जावा के लिए Aspose.Tasks का उपयोग करके डिफ़ॉल्ट MS प्रोजेक्ट गुणों को कैसे प्रबंधित किया जाए। इन तकनीकों का उपयोग करके, आप उत्पादकता और संगठन को बढ़ाकर अपने प्रोजेक्ट प्रबंधन वर्कफ़्लो को अनुकूलित कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### Q1: क्या मैं अन्य प्रोग्रामिंग भाषाओं के साथ Aspose.Tasks का उपयोग कर सकता हूँ?
A1: हां, Aspose.Tasks .NET, Python और Java जैसी विभिन्न प्रोग्रामिंग भाषाओं का समर्थन करता है।
### Q2: क्या Aspose.Tasks व्यक्तिगत और उद्यम दोनों उपयोग के लिए उपयुक्त है?
ए2: बिल्कुल! चाहे आप छोटी निजी परियोजनाओं का प्रबंधन कर रहे हों या बड़े पैमाने की उद्यम पहल का, Aspose.Tasks सभी को पूरा करता है।
### Q3: क्या Aspose.Tasks ग्राहक सहायता प्रदान करता है?
उ3: हाँ, आप सहायता और सामुदायिक सहायता पा सकते हैं[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15).
### Q4: क्या मैं खरीदने से पहले Aspose.Tasks आज़मा सकता हूँ?
 ए4: बिल्कुल! आप नि:शुल्क परीक्षण का लाभ उठा सकते हैं[वेबसाइट](https://releases.aspose.com/).
### Q5: मैं Aspose.Tasks के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
 A5: आप यहां से अस्थायी लाइसेंस प्राप्त कर सकते हैं[खरीद पृष्ठ](https://purchase.aspose.com/temporary-license/) परीक्षण और मूल्यांकन उद्देश्यों के लिए।