---
title: Aspose.Tasks में कार्य लागत प्रबंधित करें
linktitle: Aspose.Tasks में कार्य लागत प्रबंधित करें
second_title: Aspose.Tasks जावा एपीआई
description: Aspose.Tasks का उपयोग करके जावा अनुप्रयोगों में कार्य लागतों को प्रबंधित करना सीखें। प्रभावी परियोजना लागत प्रबंधन के लिए हमारी चरण-दर-चरण मार्गदर्शिका का पालन करें।
type: docs
weight: 21
url: /hi/java/task-properties/manage-task-cost/
---
## परिचय
जावा के लिए Aspose.Tasks की दुनिया में आपका स्वागत है, एक शक्तिशाली लाइब्रेरी जो आपको अपने जावा अनुप्रयोगों के भीतर कार्य लागतों को निर्बाध रूप से प्रबंधित करने की अनुमति देती है। इस चरण-दर-चरण मार्गदर्शिका में, हम यह पता लगाएंगे कि कुशल परियोजना प्रबंधन सुनिश्चित करते हुए, कार्य लागत को संभालने के लिए Aspose.Tasks का प्रभावी ढंग से उपयोग कैसे किया जाए।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
1. जावा पर्यावरण: सुनिश्चित करें कि आपके सिस्टम पर जावा विकास वातावरण स्थापित है।
2. Aspose.Tasks लाइब्रेरी: जावा लाइब्रेरी के लिए Aspose.Tasks को डाउनलोड और इंस्टॉल करें। आप पुस्तकालय पा सकते हैं[यहाँ](https://releases.aspose.com/tasks/java/).
## पैकेज आयात करें
एक बार जब आप अपना वातावरण स्थापित कर लेते हैं और Aspose.Tasks लाइब्रेरी स्थापित कर लेते हैं, तो आपको अपने जावा प्रोजेक्ट में आवश्यक पैकेज आयात करने की आवश्यकता होती है। अपने कोड में निम्नलिखित पंक्तियाँ शामिल करें:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.math.BigDecimal;
// Aspose.Tasks कक्षाएं आयात करें
```
अब, आइए कार्य लागत को प्रभावी ढंग से प्रबंधित करने के लिए उदाहरण को कई चरणों में विभाजित करें।
## चरण 1: अपना प्रोजेक्ट सेट करें
```java
// अपनी दस्तावेज़ निर्देशिका के लिए पथ सेट करें
String dataDir = "Your Document Directory";
// एक नया प्रोजेक्ट बनाएं
Project project = new Project();
```
## चरण 2: एक नया कार्य जोड़ें
```java
// मूल कार्य में एक नया कार्य जोड़ें
Task task = project.getRootTask().getChildren().add("Task");
```
## चरण 3: कार्य लागत निर्धारित करें
```java
// कार्य लागत को 800 पर सेट करें
task.set(Tsk.COST, BigDecimal.valueOf(800));
```
## चरण 4: कार्य जानकारी पुनः प्राप्त करें
```java
// कार्य संबंधी जानकारी प्राप्त करें और प्रिंट करें
System.out.println("Remaining Cost: " + task.get(Tsk.REMAINING_COST));
System.out.println("Fixed Cost: " + task.get(Tsk.FIXED_COST));
System.out.println("Cost Variance: " + task.get(Tsk.COST_VARIANCE));
// परियोजना-स्तरीय लागत जानकारी पुनर्प्राप्त करें और प्रिंट करें
System.out.println("Project Cost: " + project.getRootTask().get(Tsk.COST));
System.out.println("Project Fixed Cost: " + project.getRootTask().get(Tsk.FIXED_COST));
System.out.println("Project Remaining Cost: " + project.getRootTask().get(Tsk.REMAINING_COST));
System.out.println("Project Cost Variance: " + project.getRootTask().get(Tsk.COST_VARIANCE));
```
जावा एप्लिकेशन के लिए अपने Aspose.Tasks में कार्य लागत को प्रभावी ढंग से प्रबंधित करने के लिए इन चरणों को दोहराएं।
## निष्कर्ष
अंत में, सफल परियोजना निष्पादन के लिए कार्य लागत प्रबंधन में महारत हासिल करना महत्वपूर्ण है। जावा के लिए Aspose.Tasks एक मजबूत समाधान प्रदान करता है, जो डेवलपर्स को सटीकता के साथ लागत संभालने में सक्षम बनाता है।
## पूछे जाने वाले प्रश्न
### प्रश्न: मैं जावा के लिए Aspose.Tasks के लिए दस्तावेज़ कहां पा सकता हूं?
 उ: आप दस्तावेज़ तक पहुंच सकते हैं[यहाँ](https://reference.aspose.com/tasks/java/).
### प्रश्न: मैं जावा लाइब्रेरी के लिए Aspose.Tasks कैसे डाउनलोड कर सकता हूं?
 उत्तर: लाइब्रेरी डाउनलोड करें[यहाँ](https://releases.aspose.com/tasks/java/).
### प्रश्न: मैं जावा के लिए Aspose.Tasks कहां से खरीद सकता हूं?
 उत्तर: आप इसे खरीद सकते हैं[यहाँ](https://purchase.aspose.com/buy).
### प्रश्न: क्या जावा के लिए Aspose.Tasks के लिए कोई निःशुल्क परीक्षण उपलब्ध है?
 उत्तर: हाँ, आप निःशुल्क परीक्षण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/).
### प्रश्न: मैं जावा के लिए Aspose.Tasks के लिए समर्थन कहाँ से प्राप्त कर सकता हूँ?
 उत्तर: सहायता मंच पर जाएँ[यहाँ](https://forum.aspose.com/c/tasks/15).