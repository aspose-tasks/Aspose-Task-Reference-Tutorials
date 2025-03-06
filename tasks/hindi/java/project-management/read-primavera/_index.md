---
title: जावा के लिए Aspose.Tasks के साथ प्रिमावेरा से एमएस प्रोजेक्ट पढ़ें
linktitle: Aspose.Tasks में प्रिमावेरा से प्रोजेक्ट पढ़ें
second_title: Aspose.Tasks जावा एपीआई
description: जावा के लिए Aspose.Tasks का उपयोग करके प्राइमेरा XML से MS प्रोजेक्ट फ़ाइलों को सहजता से पढ़ने का तरीका जानें। अपनी परियोजना प्रबंधन दक्षता बढ़ाएँ।
weight: 20
url: /hi/java/project-management/read-primavera/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# जावा के लिए Aspose.Tasks के साथ प्रिमावेरा से एमएस प्रोजेक्ट पढ़ें

## परिचय
परियोजना प्रबंधन में, निर्बाध वर्कफ़्लो के लिए विभिन्न सॉफ़्टवेयर प्लेटफ़ॉर्म के बीच अंतरसंचालनीयता महत्वपूर्ण है। जावा के लिए Aspose.Tasks प्राइमेरा XML से Microsoft प्रोजेक्ट फ़ाइलों को पढ़ने के लिए मजबूत कार्यक्षमता प्रदान करता है। यह ट्यूटोरियल जावा के लिए Aspose.Tasks का उपयोग करके प्रिमावेरा से एमएस प्रोजेक्ट फ़ाइलों को पढ़ने की प्रक्रिया में आपका मार्गदर्शन करेगा, जिससे आप कार्यों के प्रिमावेरा-विशिष्ट गुणों की कुशलता से जांच कर सकेंगे।
## आवश्यक शर्तें
आगे बढ़ने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यकताएँ स्थापित और सेटअप हैं:
1. जावा डेवलपमेंट किट (जेडीके): सुनिश्चित करें कि आपके सिस्टम पर जेडीके स्थापित है।
2.  जावा के लिए Aspose.Tasks: जावा के लिए Aspose.Tasks को यहां से डाउनलोड और इंस्टॉल करें[यहाँ](https://releases.aspose.com/tasks/java/).

## पैकेज आयात करें
```java
import com.aspose.tasks.PrimaveraReadOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeDelta;
```
## चरण 1: डेटा निर्देशिका स्थापित करें
```java
String dataDir = "Your Data Directory";
```
 प्रतिस्थापित करना सुनिश्चित करें`"Your Data Directory"` आपकी डेटा निर्देशिका के वास्तविक पथ के साथ।
## चरण 2: प्रिमावेरा XML से प्रोजेक्ट पढ़ें
```java
PrimaveraReadOptions options = new PrimaveraReadOptions();
options.setProjectUid(3883);
Project project = new Project(dataDir + "PrimaveraProject.xml", options);
```
 प्रतिस्थापित करना सुनिश्चित करें`"PrimaveraProject.xml"` आपकी प्राइमेरा XML फ़ाइल के वास्तविक नाम के साथ।
## चरण 3: कार्यों के माध्यम से पुनरावृत्ति करें और प्रिमावेरा-विशिष्ट गुणों को पुनः प्राप्त करें
```java
for (Task task : project.enumerateAllChildTasks()) {
    System.out.println("Task '" + task.getName() + "'");
    
    if (task.isSummary()) {
        System.out.println("WBS Sequence number: " + task.getPrimaveraProperties().getSequenceNumber());
    } else {
        System.out.println("Task ActivityId: " + task.getPrimaveraProperties().getActivityId());
    }
    
    System.out.println("Activity Type: " + task.getPrimaveraProperties().getActivityType());
    System.out.println("Duration Type: " + task.getPrimaveraProperties().getDurationType());
    System.out.println("Percent Complete Type: " + task.getPrimaveraProperties().getPercentCompleteType());
    System.out.println("Original Duration: " + TimeDelta.fromMilliseconds(task.getDuration().getTimeSpan()).getTotalHours());
    System.out.println("At Complete Duration: " +
            (TimeDelta.fromMilliseconds(task.getActualDuration().getTimeSpan()).getTotalHours() + TimeDelta.fromMilliseconds(task.getRemainingDuration().getTimeSpan()).getTotalHours()));
    System.out.println("Duration % Complete: " + task.getPrimaveraProperties().getDurationPercentComplete());
    System.out.println("Physical % Complete: " + task.getPrimaveraProperties().getPhysicalPercentComplete());
    
    System.out.println("Task RemainingEarlyStart: " + task.getPrimaveraProperties().getRemainingEarlyStart());
    System.out.println("Task RemainingEarlyFinish: " + task.getPrimaveraProperties().getRemainingEarlyFinish());
    
    System.out.println("Actual costs:");
    System.out.println(task.getPrimaveraProperties().getActualExpenseCost() + ", "
                    + task.getPrimaveraProperties().getActualLaborCost() + ", "
                    + task.getPrimaveraProperties().getActualMaterialCost() + ", "
                    + task.getPrimaveraProperties().getActualNonlaborCost() + ", Total: "
                    + task.getPrimaveraProperties().getActualTotalCost());
    
    System.out.println("Labor Units:");
    System.out.println(task.getPrimaveraProperties().getActualLaborUnits() + ", " +
            task.getPrimaveraProperties().getActualNonLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingNonLaborUnits());
    
    System.out.println("Units % Complete: " + task.getPrimaveraProperties().getUnitsPercentComplete());
}
```
यह कोड प्रोजेक्ट में प्रत्येक कार्य के माध्यम से प्रासंगिक प्रिमावेरा-विशिष्ट गुणों को प्रिंट करते हुए पुनरावृत्त होता है।

## निष्कर्ष
इस ट्यूटोरियल में, आपने सीखा कि जावा के लिए Aspose.Tasks का उपयोग करके प्राइमेरा XML से MS प्रोजेक्ट फ़ाइलों को कैसे पढ़ा जाए। यह कार्यक्षमता विभिन्न प्लेटफार्मों पर परियोजना डेटा के निर्बाध एकीकरण और विश्लेषण को सक्षम बनाती है, जिससे समग्र परियोजना प्रबंधन दक्षता बढ़ती है।
## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या मैं जावा के लिए Aspose.Tasks का उपयोग करके कार्यों के प्राइमेरा-विशिष्ट गुणों को संशोधित कर सकता हूं?
उत्तर: हां, जावा के लिए Aspose.Tasks आवश्यकतानुसार कार्यों के प्राइमेरा-विशिष्ट गुणों को संशोधित करने के लिए एपीआई प्रदान करता है।
### प्रश्न: क्या जावा के लिए Aspose.Tasks अन्य प्रोजेक्ट फ़ाइल स्वरूपों को पढ़ने में सहायता करता है?
उत्तर: हां, जावा के लिए Aspose.Tasks एमपीपी, एक्सएमएल और प्रिमावेरा एक्सएमएल सहित विभिन्न प्रोजेक्ट फ़ाइल स्वरूपों को पढ़ने का समर्थन करता है।
### प्रश्न: क्या जावा के लिए Aspose.Tasks एंटरप्राइज़-स्तरीय परियोजना प्रबंधन अनुप्रयोगों के लिए उपयुक्त है?
उत्तर: बिल्कुल, जावा के लिए Aspose.Tasks मजबूत सुविधाएँ और स्केलेबिलिटी प्रदान करता है, जो इसे एंटरप्राइज़-स्तरीय परियोजना प्रबंधन अनुप्रयोगों के लिए उपयुक्त बनाता है।
### प्रश्न: क्या मैं जावा के लिए Aspose.Tasks का उपयोग करके प्रिमावेरा परियोजनाओं से संसाधन जानकारी निकाल सकता हूँ?
उत्तर: हां, जावा के लिए Aspose.Tasks आपको प्राइमेरा परियोजनाओं से कार्य विवरण के साथ संसाधन जानकारी निकालने की अनुमति देता है।
### प्रश्न: जावा के लिए Aspose.Tasks के लिए मुझे अतिरिक्त समर्थन या दस्तावेज़ कहां मिल सकता है?
 उ: आप इस पर समर्थन के लिए व्यापक दस्तावेज और मंचों तक पहुंच पा सकते हैं[जावा दस्तावेज़ीकरण के लिए Aspose.Tasks](https://reference.aspose.com/tasks/java/) पृष्ठ।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
