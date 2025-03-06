---
title: Aspose.Tasks में MS प्रोजेक्ट फ़ॉर्मूले लिखना और पढ़ना
linktitle: Aspose.Tasks में सूत्र लिखें और पढ़ें
second_title: Aspose.Tasks जावा एपीआई
description: Java के लिए Aspose.Tasks के साथ MS प्रोजेक्ट फ़ार्मुलों को कुशलतापूर्वक लिखना और पढ़ना सीखें। अपने प्रोजेक्ट प्रबंधन कौशल को बढ़ाएं.
weight: 12
url: /hi/java/formulas/write-read-formulas/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में MS प्रोजेक्ट फ़ॉर्मूले लिखना और पढ़ना

## परिचय
परियोजना प्रबंधन के क्षेत्र में, डेटा का प्रभावी प्रबंधन सर्वोपरि है। जावा के लिए Aspose.Tasks एक मजबूत समाधान है जो Microsoft प्रोजेक्ट फ़ाइलों से डेटा के हेरफेर और निष्कर्षण की सुविधा प्रदान करता है। इसके द्वारा प्रदान की जाने वाली एक शक्तिशाली विशेषता एमएस प्रोजेक्ट फ़ार्मुलों को लिखने और पढ़ने की क्षमता है। यह ट्यूटोरियल आपके प्रोजेक्ट प्रबंधन कार्यों को बढ़ाने के लिए इस कार्यक्षमता का लाभ उठाने की प्रक्रिया में आपका मार्गदर्शन करेगा।
## आवश्यक शर्तें
इस ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
1. जावा डेवलपमेंट किट (जेडीके): सुनिश्चित करें कि आपके सिस्टम पर जावा स्थापित है।
2.  जावा के लिए Aspose.Tasks: जावा के लिए Aspose.Tasks को यहां से डाउनलोड और इंस्टॉल करें[यहाँ](https://releases.aspose.com/tasks/java/).
3. एकीकृत विकास पर्यावरण (आईडीई): जावा विकास के लिए अपना पसंदीदा आईडीई चुनें।

## पैकेज आयात करना
आरंभ करने के लिए, अपने जावा प्रोजेक्ट में आवश्यक पैकेज आयात करें:
```java
import com.aspose.tasks.*;
import java.io.IOException;
import java.math.BigDecimal;
import java.util.Objects;
```

## चरण 1: डेटा निर्देशिका सेट करें
```java
// दस्तावेज़ निर्देशिका का पथ.
String dataDir = "Your Data Directory";
```
इस चरण में, उस निर्देशिका को परिभाषित करें जहां आपकी MS प्रोजेक्ट फ़ाइलें स्थित हैं।
## चरण 2: प्रोजेक्ट फ़ाइल लोड करें
```java
Project project = new Project(dataDir + "project.mpp");
```
यहां, एमएस प्रोजेक्ट फ़ाइल को एक में लोड करें`Project` हेरफेर के लिए वस्तु.
## चरण 3: कस्टम फॉर्मूला परिभाषित करें
```java
project.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Custom");
attr.setAlias("Double Costs");
attr.setFormula("[Cost]*2");
project.getExtendedAttributes().add(attr);
```
इस चरण में एक फ़ॉर्मूले के साथ एक कस्टम फ़ील्ड बनाना शामिल है जो कार्य लागत को दोगुना कर देता है।
## चरण 4: कार्य जोड़ें और लागत निर्धारित करें
```java
Task task = project.getRootTask().getChildren().add("Task");
task.set(Tsk.COST, BigDecimal.valueOf(100));
```
यहां, एक नया कार्य जोड़ा गया है, और इसकी लागत 100 पर सेट की गई है।
## चरण 5: प्रोजेक्ट फ़ाइल सहेजें
```java
project.save(dataDir + "saved.mpp", SaveFileFormat.Mpp);
```
अंत में, संशोधित प्रोजेक्ट फ़ाइल को सहेजें।

## निष्कर्ष
इस ट्यूटोरियल में, हमने पता लगाया है कि जावा के लिए Aspose.Tasks का उपयोग करके एमएस प्रोजेक्ट फॉर्मूले कैसे लिखें और पढ़ें। इन चरणों का पालन करके, आप अपनी विशिष्ट आवश्यकताओं को पूरा करने के लिए प्रोजेक्ट डेटा में कुशलतापूर्वक हेरफेर कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या Aspose.Tasks MS प्रोजेक्ट के सभी संस्करणों के साथ संगत है?
Aspose.Tasks उपयोगकर्ताओं के लिए लचीलापन सुनिश्चित करते हुए, MS प्रोजेक्ट के विभिन्न संस्करणों के साथ अनुकूलता प्रदान करता है।
### क्या मैं Aspose.Tasks को अपने मौजूदा जावा प्रोजेक्ट में एकीकृत कर सकता हूँ?
बिल्कुल! Aspose.Tasks सरल एपीआई उपयोग के माध्यम से जावा परियोजनाओं के साथ सहज एकीकरण प्रदान करता है।
### क्या मेरे द्वारा बनाए जा सकने वाले फ़ार्मुलों के प्रकारों की कोई सीमाएँ हैं?
Aspose.Tasks के साथ, आपके पास अपनी परियोजना की आवश्यकताओं के अनुरूप कस्टम फ़ॉर्मूले तैयार करने में व्यापक लचीलापन है।
### क्या Aspose.Tasks मल्टी-प्लेटफ़ॉर्म परिनियोजन का समर्थन करता है?
हां, Aspose.Tasks अपनी बहुमुखी प्रतिभा को बढ़ाते हुए कई प्लेटफार्मों पर तैनाती का समर्थन करता है।
### मैं Aspose.Tasks के लिए तकनीकी सहायता कैसे प्राप्त कर सकता हूँ?
 तकनीकी सहायता और सामुदायिक सहायता के लिए, पर जाएँ[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
