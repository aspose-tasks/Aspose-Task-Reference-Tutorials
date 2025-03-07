---
title: Aspose.Tasks में कार्य समयबद्ध डेटा
linktitle: Aspose.Tasks में कार्य समयबद्ध डेटा
second_title: Aspose.Tasks जावा एपीआई
description: जावा के लिए Aspose.Tasks का अन्वेषण करें और कार्य समयबद्ध डेटा प्रबंधन में महारत हासिल करें। लाइब्रेरी डाउनलोड करें, निःशुल्क परीक्षण का आनंद लें और अपने प्रोजेक्ट ट्रैकिंग को सुव्यवस्थित करें।
weight: 34
url: /hi/java/task-properties/task-timephased-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में कार्य समयबद्ध डेटा

## परिचय
परियोजना प्रबंधन के क्षेत्र में, कुशल परियोजना निष्पादन के लिए कार्य समय-चरण डेटा की सटीक ट्रैकिंग महत्वपूर्ण है। जावा के लिए Aspose.Tasks इस प्रक्रिया को सुव्यवस्थित करने के लिए एक शक्तिशाली उपकरण के रूप में उभरता है, जो मजबूत सुविधाएँ और लचीलेपन की पेशकश करता है। यह ट्यूटोरियल आपको कार्य समय-चरण डेटा को प्रभावी ढंग से प्रबंधित करने के लिए जावा के लिए Aspose.Tasks का उपयोग करने में मार्गदर्शन करेगा।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
- जावा विकास पर्यावरण: सुनिश्चित करें कि आपके सिस्टम पर जावा स्थापित है।
-  जावा लाइब्रेरी के लिए Aspose.Tasks: Aspose.Tasks लाइब्रेरी को डाउनलोड करें और अपने प्रोजेक्ट में शामिल करें। आप पुस्तकालय पा सकते हैं[यहाँ](https://releases.aspose.com/tasks/java/).
- दस्तावेज़ निर्देशिका: अपने प्रोजेक्ट दस्तावेज़ों के लिए एक निर्देशिका सेट करें।
## पैकेज आयात करें
अपने जावा प्रोजेक्ट में, Aspose.Tasks के लिए आवश्यक पैकेज आयात करें:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
import java.math.BigDecimal;
import java.util.Date;
import java.util.List;
```
## चरण 1: परियोजना प्रारंभ तिथि निर्धारित करें
```java
Project project = new Project(dataDir + "project.xml");
// पैकेज आयात के लिए अतिरिक्त कोड
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 7, 17, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
```
स्पष्टीकरण: एक कैलेंडर ऑब्जेक्ट को प्रारंभ करें, आरंभ तिथि निर्धारित करें और इसे प्रोजेक्ट पर लागू करें।
## चरण 2: कार्य और संसाधन को परिभाषित करें
```java
Task task = project.getRootTask().getChildren().add("Task");
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(10));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(15));
```
स्पष्टीकरण: मानक और ओवरटाइम के लिए दरें निर्धारित करते हुए एक कार्य और संसाधन बनाएं।
## चरण 3: कार्य की अवधि निर्धारित करें
```java
task.set(Tsk.DURATION, project.getDuration(6));
```
स्पष्टीकरण: कार्य की अवधि परिभाषित करें (उदाहरण के लिए, 6 दिन)।
## चरण 4: कार्य को संसाधन सौंपें
```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```
स्पष्टीकरण: कार्य को संसाधन सौंपें.
## चरण 5: संसाधन असाइनमेंट कॉन्फ़िगर करें
```java
Date d = new Date(0);
assn.set(Asn.STOP, new Date(0));
assn.set(Asn.RESUME, new Date(0));
assn.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
```
स्पष्टीकरण: संसाधन असाइनमेंट के लिए स्टॉप, रिज्यूम और कार्य रूपरेखा जैसे पैरामीटर सेट करें।
## चरण 6: बेसलाइन सेट करें
```java
project.setBaseline(BaselineType.Baseline);
```
स्पष्टीकरण: परियोजना के लिए आधार रेखा स्थापित करें।
## चरण 7: कार्य पूर्णता अद्यतन करें
```java
task.set(Tsk.PERCENT_COMPLETE, 50);
```
स्पष्टीकरण: कार्य की पूर्णता का प्रतिशत बतायें।
## चरण 8: समयबद्ध डेटा पुनर्प्राप्त करें
```java
List<TimephasedData> td = assn.getTimephasedData(assn.get(Asn.START), assn.get(Asn.FINISH), TimephasedDataType.AssignmentRemainingWork).toList();
```
स्पष्टीकरण: असाइनमेंट के शेष कार्य के लिए समयबद्ध डेटा पुनर्प्राप्त करें।
## चरण 9: समयबद्ध डेटा प्रदर्शित करें
```java
System.out.println(td.size());
System.out.println(td.get(0).getValue());
// अन्य मान प्रदर्शित करने के लिए अतिरिक्त कोड
```
स्पष्टीकरण: आउटपुट और टाइमफ़ेज़्ड डेटा प्रदर्शित करें।
## निष्कर्ष
परियोजना की सफलता के लिए कार्य समयबद्ध डेटा को प्रभावी ढंग से प्रबंधित करना अपरिहार्य है। जावा के लिए Aspose.Tasks कार्यात्मकताओं का एक व्यापक सेट प्रदान करते हुए इस प्रक्रिया को सरल बनाता है। इस ट्यूटोरियल का अनुसरण करके, आप प्रोजेक्ट समयसीमा और संसाधन आवंटन पर सटीक नियंत्रण सुनिश्चित करते हुए, Aspose.Tasks को अपने जावा प्रोजेक्ट में सहजता से एकीकृत कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्नों
### प्रश्न: क्या मैं किसी जावा प्रोजेक्ट में जावा के लिए Aspose.Tasks का उपयोग कर सकता हूँ?
उत्तर: हां, जावा के लिए Aspose.Tasks किसी भी जावा-आधारित प्रोजेक्ट के साथ संगत है।
### प्रश्न: जावा के लिए Aspose.Tasks के लिए मुझे अतिरिक्त सहायता कहां मिल सकती है?
 ए: पर जाएँ[Aspose.कार्य फोरम](https://forum.aspose.com/c/tasks/15) समर्थन और चर्चा के लिए.
### प्रश्न: क्या जावा के लिए Aspose.Tasks के लिए कोई निःशुल्क परीक्षण उपलब्ध है?
 उ: हां, आप निःशुल्क परीक्षण का पता लगा सकते हैं[यहाँ](https://releases.aspose.com/).
### प्रश्न: मैं जावा के लिए Aspose.Tasks के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
 उ: आप अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.aspose.com/temporary-license/).
### प्रश्न: मैं जावा के लिए Aspose.Tasks कहां से खरीद सकता हूं?
 उ: आप जावा के लिए Aspose.Tasks खरीद सकते हैं[यहाँ](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
