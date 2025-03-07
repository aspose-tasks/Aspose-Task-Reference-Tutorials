---
title: WBS Aspose.Tasks में कार्य से संबद्ध है
linktitle: WBS Aspose.Tasks में कार्य से संबद्ध है
second_title: Aspose.Tasks जावा एपीआई
description: जावा के लिए Aspose.Tasks के साथ मास्टर WBS - कार्य WBS कोड को पढ़ना और पुनः क्रमांकित करना सीखें। परियोजना प्रबंधन दक्षता बढ़ाएँ!
weight: 36
url: /hi/java/task-properties/wbs-associated-with-task/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# WBS Aspose.Tasks में कार्य से संबद्ध है

## परिचय
जावा के लिए Aspose.Tasks के साथ परियोजना प्रबंधन की दुनिया में आपका स्वागत है! इस ट्यूटोरियल में, हम Java के लिए Aspose.Tasks का उपयोग करके कार्यों से जुड़े वर्क ब्रेकडाउन स्ट्रक्चर (WBS) की जटिलताओं को समझेंगे। चाहे आप एक अनुभवी डेवलपर हों या अभी शुरुआत कर रहे हों, यह मार्गदर्शिका आपको WBS कोड को कुशलतापूर्वक प्रबंधित करने की अनिवार्यताओं के माध्यम से नेविगेट करने में मदद करेगी।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
- आपकी मशीन पर जावा डेवलपमेंट किट (जेडीके) स्थापित है।
-  जावा लाइब्रेरी के लिए Aspose.Tasks डाउनलोड किया गया और आपके प्रोजेक्ट में जोड़ा गया। आप इसे यहां से प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/java/).
## पैकेज आयात करें
सुनिश्चित करें कि आप अपने प्रोजेक्ट को किकस्टार्ट करने के लिए आवश्यक पैकेज आयात करें:
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.ArrayList;
import java.util.List;
```
## WBS कोड पढ़ें
आइए कार्यों से जुड़े WBS कोड को पढ़कर शुरुआत करें। इन चरणों का पालन करें:
## चरण 1: प्रोजेक्ट लोड करें
```java
Project project = new Project("Your Document Directory" + "input.mpp");
```
## चरण 2: कार्य एकत्रित करें
```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```
## चरण 3: पार्स और कस्टमाइज़ करें
```java
for (Task tsk : collector.getTasks()) {
    System.out.println(tsk.get(Tsk.WBS));
    System.out.println(tsk.get(Tsk.WBS_LEVEL));
    tsk.set(Tsk.WBS, "custom wbs");
}
```
यह स्निपेट आपके प्रोजेक्ट में कार्यों से जुड़े WBS कोड को पढ़ता है और अनुकूलित करता है।
## कार्य WBS कोड को पुनः क्रमांकित करें
अब, आइए कार्यों के लिए WBS कोड को पुनः क्रमांकित करने का पता लगाएं:
## चरण 1: प्रोजेक्ट लोड करें
```java
Project project = new Project("Your Document Directory" + "RenumberExample.mpp");
```
## चरण 2: सभी कार्य चुनें
```java
List<Task> tasks = (List<Task>) project.getRootTask().selectAllChildTasks();
```
## चरण 3: प्रारंभिक WBS कोड आउटपुट करें
```java
System.out.println("WBS codes before: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```
## चरण 4: WBS कोड को पुनः क्रमांकित करें
```java
List<Integer> listIds = new ArrayList<>();
listIds.add(1);
listIds.add(2);
listIds.add(3);
project.renumberWBSCode(listIds);
```
## चरण 5: आउटपुट अद्यतन WBS कोड
```java
System.out.println("\nWBS codes after: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```
इन चरणों का पालन करके, आप अपने प्रोजेक्ट में कार्यों के लिए प्रभावी ढंग से WBS कोड को पुनः क्रमांकित करेंगे।
## निष्कर्ष
बधाई हो! आपने जावा के लिए Aspose.Tasks का उपयोग करके WBS कोड के साथ काम करना सफलतापूर्वक सीख लिया है। यह ज्ञान आपको अपने प्रोजेक्ट के कार्य पदानुक्रम को कुशलतापूर्वक प्रबंधित और अनुकूलित करने में सशक्त बनाएगा।
## पूछे जाने वाले प्रश्न
### प्रश्न: मैं जावा के लिए Aspose.Tasks के लिए दस्तावेज़ कहां पा सकता हूं?
 उत्तर: दस्तावेज़ उपलब्ध है[यहाँ](https://reference.aspose.com/tasks/java/).
### प्रश्न: मैं जावा के लिए Aspose.Tasks कैसे डाउनलोड कर सकता हूं?
 उत्तर: आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/java/).
### प्रश्न: क्या जावा के लिए Aspose.Tasks के लिए कोई निःशुल्क परीक्षण उपलब्ध है?
 उत्तर: हाँ, आप निःशुल्क परीक्षण प्राप्त कर सकते हैं[यहाँ](https://releases.aspose.com/).
### प्रश्न: जावा के लिए Aspose.Tasks के लिए मुझे समर्थन कहां से मिल सकता है?
 ए: पर जाएँ[Aspose.कार्य मंच](https://forum.aspose.com/c/tasks/15) समर्थन के लिए।
### प्रश्न: क्या मैं जावा के लिए Aspose.Tasks के लिए अस्थायी लाइसेंस प्राप्त कर सकता हूँ?
 उत्तर: हां, अस्थायी लाइसेंस प्राप्त करें[यहाँ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
