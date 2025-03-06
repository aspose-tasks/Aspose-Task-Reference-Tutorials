---
title: Aspose.Tasks में कार्यों की अवधि प्रबंधित करें
linktitle: Aspose.Tasks में कार्यों की अवधि प्रबंधित करें
second_title: Aspose.Tasks जावा एपीआई
description: जावा के लिए Aspose.Tasks का अन्वेषण करें और कार्य अवधि को सहजता से प्रबंधित करना सीखें। प्रभावी परियोजना योजना और कार्यान्वयन के लिए हमारी चरण-दर-चरण मार्गदर्शिका का पालन करें।
weight: 20
url: /hi/java/task-properties/manage-durations/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में कार्यों की अवधि प्रबंधित करें

## परिचय
जावा के लिए Aspose.Tasks परियोजना कार्यों और अवधियों को कुशलतापूर्वक प्रबंधित करने के लिए एक मजबूत समाधान प्रदान करता है। इस ट्यूटोरियल में, हम यह पता लगाएंगे कि Aspose.Tasks का उपयोग करके कार्यों की अवधि को कैसे प्रबंधित किया जाए, प्रत्येक चरण में आपका मार्गदर्शन किया जाए। चाहे आप एक अनुभवी डेवलपर हों या नौसिखिया, यह मार्गदर्शिका आपको अपनी परियोजनाओं में कार्य अवधि के साथ काम करने की अनिवार्यताओं को समझने में मदद करेगी।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
-  जावा डेवलपमेंट किट (जेडीके): सुनिश्चित करें कि आपकी मशीन पर जावा स्थापित है। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://www.oracle.com/java/technologies/javase-downloads.html).
- Aspose.Tasks लाइब्रेरी: Aspose.Tasks लाइब्रेरी को डाउनलोड करें और अपने प्रोजेक्ट में शामिल करें। आप पुस्तकालय पा सकते हैं[यहाँ](https://releases.aspose.com/tasks/java/).
## पैकेज आयात करें
अपने जावा प्रोजेक्ट में, Aspose.Tasks के साथ काम करने के लिए आवश्यक पैकेज आयात करें:
```java
import com.aspose.tasks.Duration;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```
## चरण 1: अपना प्रोजेक्ट सेट करें
```java
// एक नया प्रोजेक्ट बनाएं
Project project = new Project();
```
## चरण 2: एक नया कार्य जोड़ें
```java
// प्रोजेक्ट में एक नया कार्य जोड़ें
Task task = project.getRootTask().getChildren().add("Task");
```
## चरण 3: कार्य अवधि प्राप्त करें और परिवर्तित करें
```java
// कार्य अवधि दिनों में प्राप्त करें (डिफ़ॉल्ट समय इकाई)
Duration duration = task.get(Tsk.DURATION);
System.out.println("Duration equals 1 day: " + duration.toString().equals("1 day"));
// अवधि को घंटों की समय इकाई में बदलें
duration = duration.convert(TimeUnitType.Hour);
System.out.println("Duration equals 8 hrs: " + duration.toString().equals("8 hrs"));
```
## चरण 4: कार्य अवधि को 1 सप्ताह तक अद्यतन करें
```java
// कार्य की अवधि बढ़ाकर 1 सप्ताह करें
task.set(Tsk.DURATION, project.getDuration(1, TimeUnitType.Week));
System.out.println("Duration equals 1 wk: " + task.get(Tsk.DURATION).toString().equals("1 wk"));
```
## चरण 5: कार्य की अवधि कम करें
```java
// कार्य की अवधि कम करें
task.set(Tsk.DURATION, task.get(Tsk.DURATION).subtract(0.5));
System.out.println("Duration equals 0.5 wks: " + task.get(Tsk.DURATION).toString().equals("0.5 wks"));
```
इन चरणों का पालन करके, आपने जावा प्रोजेक्ट के लिए अपने Aspose.Tasks में कार्यों की अवधि को सफलतापूर्वक प्रबंधित किया है।
## निष्कर्ष
इस ट्यूटोरियल में, हमने जावा के लिए Aspose.Tasks का उपयोग करके कार्य अवधि के प्रबंधन की मूल बातें शामिल की हैं। अब, आप प्रभावी कार्य अवधि प्रबंधन के लिए आत्मविश्वास से इन तकनीकों को अपनी परियोजनाओं में शामिल कर सकते हैं।
## पूछे जाने वाले प्रश्न
### क्या Aspose.Tasks सभी जावा संस्करणों के साथ संगत है?
Aspose.Tasks Java 6 और बाद के संस्करणों के साथ संगत है।
### क्या मैं व्यावसायिक परियोजनाओं के लिए Aspose.Tasks का उपयोग कर सकता हूँ?
 हां, आप व्यक्तिगत और व्यावसायिक दोनों परियोजनाओं के लिए Aspose.Tasks का उपयोग कर सकते हैं। मिलने जाना[यहाँ](https://purchase.aspose.com/buy) लाइसेंसिंग विवरण के लिए.
### मुझे अतिरिक्त सहायता और संसाधन कहां मिल सकते हैं?
 दौरा करना[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15) सामुदायिक समर्थन और चर्चा के लिए।
### मैं परीक्षण उद्देश्यों के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
 आपको अस्थायी लाइसेंस मिल सकता है[यहाँ](https://purchase.aspose.com/temporary-license/) परीक्षण और मूल्यांकन के लिए.
### क्या Aspose.Tasks के लिए कोई निःशुल्क परीक्षण उपलब्ध है?
 हाँ, आप नि:शुल्क परीक्षण का उपयोग कर सकते हैं[यहाँ](https://releases.aspose.com/) खरीदारी करने से पहले Aspose.Tasks का अन्वेषण करें।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
