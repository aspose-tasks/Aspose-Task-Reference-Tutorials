---
title: Aspose.Tasks में कार्य गुणों में महारत हासिल करना
linktitle: Aspose.Tasks में कार्यों के सामान्य गुण पढ़ें और लिखें
second_title: Aspose.Tasks जावा एपीआई
description: कार्य गुणों को सहजता से प्रबंधित करने में जावा के लिए Aspose.Tasks की शक्ति का अन्वेषण करें। हमारी चरण-दर-चरण मार्गदर्शिका का उपयोग करके आसानी से पढ़ें और लिखें।
weight: 26
url: /hi/java/task-properties/read-write-general-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में कार्य गुणों में महारत हासिल करना

## परिचय
Aspose.Tasks के साथ जावा में कार्य प्रबंधन की पूरी क्षमता को अनलॉक करें। इस व्यापक मार्गदर्शिका में, हम जावा के लिए Aspose.Tasks का उपयोग करके कार्यों के सामान्य गुणों को पढ़ने और लिखने में गहराई से उतरेंगे। चाहे आप एक अनुभवी डेवलपर हों या नौसिखिया, यह ट्यूटोरियल आपको कार्य गुणों में आसानी से हेरफेर करने के कौशल से लैस करेगा।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
- आपके सिस्टम पर जावा डेवलपमेंट किट (जेडीके) स्थापित है।
-  जावा लाइब्रेरी के लिए Aspose.Tasks डाउनलोड और सेट अप करें। आप डाउनलोड लिंक पा सकते हैं[यहाँ](https://releases.aspose.com/tasks/java/).
- एक कोड संपादक जैसे IntelliJ IDEA या Eclipse।
## पैकेज आयात करें
चीजों को शुरू करने के लिए, अपने जावा प्रोजेक्ट में आवश्यक पैकेज आयात करें। यह चरण सुनिश्चित करता है कि आपके पास Aspose.Tasks कार्यात्मकताओं तक पहुंच है। आपका मार्गदर्शन करने के लिए यहां एक स्निपेट दिया गया है:
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
## कार्यों के सामान्य गुण पढ़ना
## चरण 1: एक कार्य बनाएं
अपने प्रोजेक्ट में एक कार्य बनाकर शुरुआत करें। इसमें कार्य का नाम, प्रारंभ तिथि और अन्य प्रासंगिक विवरण सेट करना शामिल है। यहाँ एक उदाहरण है:
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Document Directory";
Project project = new Project();
Task task = project.getRootTask().getChildren().add("Task1");
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, Calendar.JULY, 17, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.NAME, "new name");
```
## चरण 2: कार्य गुण पढ़ें
अब जब आपने एक कार्य बना लिया है, तो आइए उसके सामान्य गुणों को पुनः प्राप्त करें और प्रदर्शित करें। निम्नलिखित कोड स्निपेट इसे पूरा करता है:
```java
// कार्यों के सामान्य गुण पढ़ना
Project prj = new Project(dataDir + "project.xml");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(prj.getRootTask(), collector, 0);
for (Task tsk : collector.getTasks()) {
    System.out.println("Task Id:" + tsk.get(Tsk.ID));
    System.out.println("Task Uid: " + tsk.get(Tsk.UID));
    System.out.println("Task Name: " + tsk.get(Tsk.NAME));
    System.out.println("Task Start: " + tsk.get(Tsk.START));
    System.out.println("Task Finish: " + tsk.get(Tsk.FINISH));
}
```
## कार्यों के सामान्य गुण लिखना
## चरण 3: प्रोजेक्ट लोड करें और कलेक्टर बनाएं
 सामान्य गुण लिखने के लिए, एक मौजूदा प्रोजेक्ट लोड करें और एक सेट अप करें`ChildTasksCollector`:
```java
Project prj = new Project(dataDir + "project.xml");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(prj.getRootTask(), collector, 0);
```
## चरण 4: गुणों को पार्स और प्रदर्शित करें
अंत में, एकत्रित कार्यों का विश्लेषण करें और उनके गुण प्रदर्शित करें:
```java
for (Task tsk : collector.getTasks()) {
    System.out.println("Task Id:" + tsk.get(Tsk.ID));
    System.out.println("Task Uid: " + tsk.get(Tsk.UID));
    System.out.println("Task Name: " + tsk.get(Tsk.NAME));
    System.out.println("Task Start: " + tsk.get(Tsk.START));
    System.out.println("Task Finish: " + tsk.get(Tsk.FINISH));
}
```
बधाई हो! आपने जावा के लिए Aspose.Tasks का उपयोग करके कार्यों के सामान्य गुणों को सफलतापूर्वक पढ़ा और लिखा है।
## निष्कर्ष
इस ट्यूटोरियल में, हमने जावा के लिए Aspose.Tasks के साथ कार्य गुणों को सहजता से हेरफेर करने के लिए मूलभूत चरणों का पता लगाया है। इन तकनीकों में महारत हासिल करके, आप अपने जावा विकास कौशल को बढ़ा सकते हैं और अपनी परियोजनाओं में कार्य प्रबंधन को सुव्यवस्थित कर सकते हैं।
## पूछे जाने वाले प्रश्न
### क्या Aspose.Tasks Java 11 के साथ संगत है?
हाँ, Aspose.Tasks Java 11 और बाद के संस्करणों के साथ संगत है।
### क्या मैं व्यावसायिक परियोजनाओं के लिए Aspose.Tasks का उपयोग कर सकता हूँ?
 बिल्कुल! Aspose.Tasks व्यक्तिगत और व्यावसायिक दोनों परियोजनाओं के लिए एक शक्तिशाली उपकरण है। मिलने जाना[यहाँ](https://purchase.aspose.com/buy) लाइसेंसिंग विकल्पों का पता लगाने के लिए।
### मैं परीक्षण उद्देश्यों के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
 एक अस्थायी लाइसेंस प्राप्त करें[यहाँ](https://purchase.aspose.com/temporary-license/) परीक्षण और मूल्यांकन के लिए.
### मुझे Aspose.Tasks के लिए सामुदायिक समर्थन कहां मिल सकता है?
 सामुदायिक चर्चा में शामिल हों[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15) सहायता एवं सहयोग के लिए.
### क्या संदर्भ के लिए कोई नमूना परियोजनाएँ उपलब्ध हैं?
 दस्तावेज़ीकरण के उदाहरण अनुभाग का अन्वेषण करें[यहाँ](https://reference.aspose.com/tasks/java/) नमूना परियोजनाओं और कोड स्निपेट के लिए।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
