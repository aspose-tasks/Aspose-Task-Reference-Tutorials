---
date: 2026-03-03
description: Aspose.Tasks for Java में WBS को पुनः क्रमांकित करना सीखें, कार्य विभाजन
  को प्रबंधित करें और चरण‑दर‑चरण उदाहरणों के साथ WBS कोड को कुशलतापूर्वक अनुकूलित
  करें।
linktitle: WBS Associated with Task in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java में WBS को पुनः क्रमांकित कैसे करें
url: /hi/java/task-properties/wbs-associated-with-task/
weight: 36
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java में WBS को पुनः क्रमांकित कैसे करें

## परिचय
यदि आपको Aspose.Tasks for Java का उपयोग करके Microsoft Project फ़ाइल में **WBS को पुनः क्रमांकित करने** की आवश्यकता है, तो आप सही जगह पर हैं। यह ट्यूटोरियल आपको मौजूदा WBS कोड पढ़ने, उन्हें कस्टमाइज़ करने, और फिर पदानुक्रम को पुनः क्रमांकित करने की प्रक्रिया से ले जाता है ताकि आपका प्रोजेक्ट व्यवस्थित रहे। चाहे आप किसी लेगेसी शेड्यूल को साफ़ कर रहे हों या नई शुरुआत से नया शेड्यूल बना रहे हों, इन चरणों में निपुणता आपको **वर्क ब्रेकडाउन** संरचनाओं को आत्मविश्वास के साथ प्रबंधित करने में मदद करेगी।

## त्वरित उत्तर
- **WBS को पुनः क्रमांकित करने से क्या होता है?** यह कार्यों की पदानुक्रमिक क्रमांकन को पुनः गणना करता है ताकि किसी भी संरचनात्मक परिवर्तन को दर्शाया जा सके।  
- **कौन सा क्लास पुनः क्रमांकित करने का कार्य करता है?** `Project.renumberWBSCode`।  
- **क्या कोड चलाने के लिए लाइसेंस आवश्यक है?** उत्पादन उपयोग के लिए एक वैध Aspose.Tasks लाइसेंस आवश्यक है।  
- **क्या मैं WBS फ़ॉर्मेट को कस्टमाइज़ कर सकता हूँ?** हाँ—किसी भी स्ट्रिंग को असाइन करने के लिए `Task.set(Tsk.WBS, "...")` का उपयोग करें।  
- **मुख्य पूर्वापेक्षाएँ क्या हैं?** Java JDK, Aspose.Tasks for Java लाइब्रेरी, और एक वैध प्रोजेक्ट फ़ाइल (.mpp)।

## वर्क ब्रेकडाउन स्ट्रक्चर (WBS) क्या है?
वर्क ब्रेकडाउन स्ट्रक्चर (WBS) एक प्रोजेक्ट की डिलीवरबल्स और कार्यों का पदानुक्रमिक प्रतिनिधित्व है। प्रत्येक कार्य को एक कोड (जैसे 1.2.3) मिलता है जो उसकी पदानुक्रम में स्थिति को दर्शाता है। जब कार्य जोड़े, हटाए या पुनः क्रमित किए जाते हैं, तो कोड को तार्किक और पढ़ने में आसान रखने के लिए पुनः क्रमांकित करना आवश्यक हो जाता है।

## वर्क ब्रेकडाउन का प्रबंधन और WBS कोड को कस्टमाइज़ क्यों करें?
- **स्पष्टता:** स्पष्ट WBS कोड स्टेकहोल्डर्स के लिए कार्यों को खोजने में सरल बनाते हैं।  
- **रिपोर्टिंग:** कई रिपोर्टिंग टूल्स सुसंगत क्रमांकन पर निर्भर करते हैं।  
- **लचीलापन:** कस्टम कोड आपको प्रोजेक्ट संरचना को आंतरिक मानकों के साथ संरेखित करने की अनुमति देते हैं।  

## पूर्वापेक्षाएँ
कोड में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

- आपके मशीन पर Java Development Kit (JDK) स्थापित हो।  
- आपके प्रोजेक्ट में Aspose.Tasks for Java लाइब्रेरी जोड़ी गई हो। आप इसे [यहाँ](https://releases.aspose.com/tasks/java/) से प्राप्त कर सकते हैं।  

## पैकेज इम्पोर्ट करें
अपने प्रोजेक्ट को शुरू करने के लिए आवश्यक पैकेज इम्पोर्ट करना सुनिश्चित करें:

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
पहले, हम मौजूदा WBS कोड पढ़ेंगे ताकि आप देख सकें कि आप किस चीज़ पर काम कर रहे हैं।

### चरण 1: प्रोजेक्ट लोड करें
```java
Project project = new Project("Your Document Directory" + "input.mpp");
```

### चरण 2: कार्य एकत्रित करें
```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```

### चरण 3: पार्स और कस्टमाइज़ करें
```java
for (Task tsk : collector.getTasks()) {
    System.out.println(tsk.get(Tsk.WBS));
    System.out.println(tsk.get(Tsk.WBS_LEVEL));
    tsk.set(Tsk.WBS, "custom wbs");
}
```

ऊपर दिया गया स्निपेट प्रत्येक कार्य के वर्तमान WBS और स्तर को प्रिंट करता है, फिर एक नई स्ट्रिंग असाइन करके **WBS कोड को कस्टमाइज़** करने का प्रदर्शन करता है।

## कार्य WBS कोड को पुनः क्रमांकित करें
अब हम वास्तव में WBS पदानुक्रम को पुनः क्रमांकित करेंगे।

### चरण 1: प्रोजेक्ट लोड करें (पुनः क्रमांकित उदाहरण)
```java
Project project = new Project("Your Document Directory" + "RenumberExample.mpp");
```

### चरण 2: सभी कार्य चुनें
```java
List<Task> tasks = (List<Task>) project.getRootTask().selectAllChildTasks();
```

### चरण 3: प्रारंभिक WBS कोड आउटपुट करें
```java
System.out.println("WBS codes before: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```

### चरण 4: WBS कोड पुनः क्रमांकित करें
```java
List<Integer> listIds = new ArrayList<>();
listIds.add(1);
listIds.add(2);
listIds.add(3);
project.renumberWBSCode(listIds);
```

### चरण 5: अपडेटेड WBS कोड आउटपुट करें
```java
System.out.println("\nWBS codes after: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```

इन चरणों का पालन करके, आप अपने प्रोजेक्ट फ़ाइल में किसी भी कार्य सेट के लिए प्रभावी रूप से **WBS को पुनः क्रमांकित** कर पाएँगे।

## सामान्य समस्याएँ और समाधान
- **`set` कॉल के बाद WBS नहीं बदल रहा:** सुनिश्चित करें कि आप सही कार्य इंस्टेंस पर काम कर रहे हैं और संशोधनों के बाद प्रोजेक्ट सेव किया गया है।  
- **`renumberWBSCode` अपवाद फेंकता है:** पुष्टि करें कि IDs की सूची शीर्ष‑स्तर कार्यों की संख्या से मेल खाती है; अन्यथा मेथड नई संख्याओं को सही ढंग से मैप नहीं कर पाएगा।  
- **WBS मान अनुपलब्ध:** कुछ कार्यों में `null` WBS हो सकता है यदि वे ऐसी फ़ाइल से आयातित हुए हैं जिसमें यह परिभाषित नहीं था। प्रिंट करने से पहले एक फॉलबैक मान उपयोग करें।  

## अक्सर पूछे जाने वाले प्रश्न

**Q: Aspose.Tasks for Java की दस्तावेज़ीकरण कहाँ मिल सकता है?**  
A: दस्तावेज़ीकरण [यहाँ](https://reference.aspose.com/tasks/java/) उपलब्ध है।

**Q: मैं Aspose.Tasks for Java को कैसे डाउनलोड कर सकता हूँ?**  
A: आप इसे [यहाँ](https://releases.aspose.com/tasks/java/) से डाउनलोड कर सकते हैं।

**Q: क्या Aspose.Tasks for Java के लिए मुफ्त ट्रायल उपलब्ध है?**  
A: हाँ, आप एक मुफ्त ट्रायल [यहाँ](https://releases.aspose.com/) प्राप्त कर सकते हैं।

**Q: मैं Aspose.Tasks for Java के लिए समर्थन कहाँ प्राप्त कर सकता हूँ?**  
A: समर्थन के लिए [Aspose.Tasks फ़ोरम](https://forum.aspose.com/c/tasks/15) पर जाएँ।

**Q: क्या मैं Aspose.Tasks for Java के लिए अस्थायी लाइसेंस प्राप्त कर सकता हूँ?**  
A: हाँ, आप एक अस्थायी लाइसेंस [यहाँ](https://purchase.aspose.com/temporary-license/) प्राप्त कर सकते हैं।

**Q: क्या मैं पुनः क्रमांकित करने के बाद WBS फ़ॉर्मेट का नाम बदल सकता हूँ?**  
A: बिल्कुल। `renumberWBSCode` कॉल करने के बाद, आप कार्यों पर इटरेट करके `task.set(Tsk.WBS, "NewFormat-" + task.get(Tsk.WBS))` लागू कर सकते हैं ताकि आपके नामकरण मानकों के अनुरूप हो।

**Q: क्या पुनः क्रमांकित करने से कार्य निर्भरताओं पर प्रभाव पड़ता है?**  
A: नहीं। यह मेथड केवल WBS स्ट्रिंग को अपडेट करता है; कार्य लिंक और प्रतिबंध अपरिवर्तित रहते हैं।

---

**अंतिम अपडेट:** 2026-03-03  
**परीक्षित संस्करण:** Aspose.Tasks for Java 24.12 (latest)  
**लेखक:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}