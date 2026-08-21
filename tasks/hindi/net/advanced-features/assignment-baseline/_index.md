---
date: 2026-03-19
description: Aspose.Tasks for .NET के साथ प्रोजेक्ट बेसलाइन सेट करना और असाइनमेंट
  बेसलाइन को प्रभावी ढंग से प्रबंधित करना सीखें, जिससे प्रोजेक्ट प्रगति का सटीक ट्रैकिंग
  सुनिश्चित हो।
linktitle: Managing Assignment Baseline in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: प्रोजेक्ट बेसलाइन सेट करें – Aspose.Tasks में असाइनमेंट बेसलाइन का प्रबंधन
url: /hi/net/advanced-features/assignment-baseline/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# प्रोजेक्ट बेसलाइन सेट करें – Aspose.Tasks में असाइनमेंट बेसलाइन प्रबंधन

## परिचय

प्रोजेक्ट मैनेजमेंट कार्यों पर काम करते समय, **प्रोजेक्ट बेसलाइन सेट करना** वास्तविक प्रगति को मूल योजना के मुकाबले मापने के लिए आवश्यक है। Aspose.Tasks for .NET न केवल आपको **प्रोजेक्ट बेसलाइन सेट** करने देता है बल्कि असाइनमेंट बेसलाइन पर पूर्ण नियंत्रण भी प्रदान करता है, जिससे सटीक प्रदर्शन ट्रैकिंग संभव होती है। इस ट्यूटोरियल में हम पूरी प्रक्रिया—प्रोजेक्ट लोड करना, बेसलाइन सेट करना, असाइनमेंट बेसलाइन डेटा पढ़ना, और बेसलाइन की तुलना करना—परिचित कराएंगे, ताकि आप अपने प्रोजेक्ट्स को आत्मविश्वास के साथ मॉनिटर कर सकें।

## त्वरित उत्तर
- **“प्रोजेक्ट बेसलाइन सेट” का क्या मतलब है?** यह मूल शेड्यूल और लागत डेटा को रिकॉर्ड करता है ताकि बाद में वास्तविक प्रदर्शन से तुलना की जा सके।  
- **कौन सा API मेथड बेसलाइन सेट करता है?** `Project.SetBaseline(BaselineType.Baseline)`।  
- **क्या असाइनमेंट बेसलाइन के लिए अलग कॉल की आवश्यकता है?** नहीं, वे स्वचालित रूप से स्टोर हो जाती हैं जब आप प्रोजेक्ट बेसलाइन सेट करते हैं।  
- **कौन‑से फॉर्मेट सपोर्टेड हैं?** MPP, XML, MPX और Aspose.Tasks के माध्यम से अधिक।  
- **क्या प्रोडक्शन के लिए लाइसेंस आवश्यक है?** हाँ, गैर‑ट्रायल उपयोग के लिए एक कमर्शियल लाइसेंस चाहिए।

## आवश्यकताएँ

शुरू करने से पहले सुनिश्चित करें कि आपके पास है:

- C# प्रोग्रामिंग का बुनियादी ज्ञान।  
- Visual Studio (कोई भी हालिया संस्करण)।  
- Aspose.Tasks for .NET लाइब्रेरी आपके प्रोजेक्ट में जोड़ी गई हो। आप इसे [यहाँ](https://releases.aspose.com/tasks/net/) से डाउनलोड कर सकते हैं।  
- MPP फॉर्मेट में एक प्रोजेक्ट फ़ाइल तक पहुँच (उदाहरण के लिए `AssignmentBaseline2007.mpp`)।

## नेमस्पेस इम्पोर्ट करें

अपने C# फ़ाइल के शीर्ष पर आवश्यक नेमस्पेस जोड़ें ताकि कंपाइलर को Aspose.Tasks क्लासेज़ का पता चल सके।

```csharp
using Aspose.Tasks;
using System;
```

## चरण 1: प्रोजेक्ट लोड करें और प्रोजेक्ट बेसलाइन सेट करें

पहले मौजूदा MPP फ़ाइल लोड करें और फिर `SetBaseline` को कॉल करके **पूरे प्रोजेक्ट की बेसलाइन सेट** करें।

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
project.SetBaseline(BaselineType.Baseline);
```

## चरण 2: असाइनमेंट बेसलाइन जानकारी पढ़ें

बेसलाइन सेट होने के बाद, प्रत्येक रिसोर्स असाइनमेंट अपनी स्वयं की बेसलाइन रिकॉर्ड रखता है। नीचे दिया गया लूप उन विवरणों को निकालता और प्रिंट करता है, जिसमें स्टार्ट/फ़िनिश डेट, लागत, कार्य, और कोई भी टाइम‑फ़ेज़्ड डेटा शामिल है।

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var baseline in assignment.Baselines)
    {
        Console.WriteLine("Baseline Start: " + baseline.Start);
        Console.WriteLine("Baseline Finish: " + baseline.Finish);
        Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
        Console.WriteLine("Bcwp: " + baseline.Bcwp);
        Console.WriteLine("Bcws: " + baseline.Bcws);
        Console.WriteLine("Cost: " + baseline.Cost);
        Console.WriteLine("Work: " + baseline.Work);
        if (baseline.TimephasedData != null)
        {
            foreach (var td in baseline.TimephasedData)
            {
                Console.WriteLine("TD Start: " + td.Start);
                Console.WriteLine("TD Finish: " + td.Finish);
                Console.WriteLine("TD Timephased Data Type: " + td.TimephasedDataType);
                Console.WriteLine();
            }
        }

        Console.WriteLine();
    }

    Console.WriteLine();
}
```

## चरण 3: असाइनमेंट बेसलाइन की तुलना करें

आप बिल्ट‑इन इक्क्वैलिटी और तुलना ऑपरेटर्स का उपयोग करके विभिन्न असाइनमेंट की बेसलाइन की तुलना कर सकते हैं। यह तब उपयोगी होता है जब आपको टास्क के शेड्यूल शिफ्ट या लागत ओवररन का पता लगाना हो।

```csharp
var assn1 = project.ResourceAssignments.GetByUid(5);
var assn2 = project.ResourceAssignments.GetByUid(7);

var assignmentBaseline1 = assn1.Baselines.ToList()[0];
var assignmentBaseline2 = assn2.Baselines.ToList()[0];

// Check baseline equality
Console.WriteLine("Are baselines equal: " + assignmentBaseline1.Equals(assignmentBaseline2));

// Check baseline comparison
Console.WriteLine("Is baseline 1 less than baseline 2: " + (assignmentBaseline1 < assignmentBaseline2));

// Display baseline hashcodes
Console.WriteLine("Assignment baseline 1 hashcode: " + assignmentBaseline1.GetHashCode());
Console.WriteLine("Assignment baseline 2 hashcode: " + assignmentBaseline2.GetHashCode());
```

## सामान्य समस्याएँ और समाधान

| समस्या | क्यों होती है | समाधान |
|-------|----------------|-----|
| **बेसलाइन डेटा खाली दिख रहा है** | प्रोजेक्ट फ़ाइल रीड‑ओनली मोड में खोली गई थी या बेसलाइन कभी सेट नहीं हुई। | असाइनमेंट बेसलाइन पढ़ने से पहले `project.SetBaseline(BaselineType.Baseline)` कॉल करें। |
| **`NullReferenceException` on `TimephasedData`** | सभी बेसलाइन में टाइम‑फ़ेज़्ड एंट्री नहीं होती। | हमेशा `baseline.TimephasedData != null` चेक करें (कोड में दिखाए अनुसार)। |
| **गलत UID प्राप्ति** | फ़ाइल संस्करणों के बीच UID मान अलग होते हैं। | सही UID के साथ `ResourceAssignments.GetByUid` का उपयोग करें या असाइनमेंट खोजने के लिए इटररेट करें। |

## अक्सर पूछे जाने वाले प्रश्न

**प्र: क्या Aspose.Tasks एक ही असाइनमेंट के लिए कई बेसलाइन संभाल सकता है?**  
उ: हाँ, Aspose.Tasks प्रत्येक असाइनमेंट के लिए कई बेसलाइन सपोर्ट करता है, जिससे प्रोजेक्ट प्रगति को समय के साथ व्यापक रूप से ट्रैक किया जा सकता है।

**प्र: क्या Aspose.Tasks MPP के अलावा अन्य प्रोजेक्ट फ़ाइल फॉर्मेट्स के साथ संगत है?**  
उ: हाँ, Aspose.Tasks XML, MPX, और MPP सहित विभिन्न प्रोजेक्ट फ़ाइल फॉर्मेट्स को सपोर्ट करता है, जिससे विभिन्न प्रोजेक्ट मैनेजमेंट टूल्स के साथ संगतता सुनिश्चित होती है।

**प्र: क्या मैं प्रोग्रामेटिकली बेसलाइन जानकारी को संशोधित कर सकता हूँ?**  
उ: बिल्कुल, Aspose.Tasks विस्तृत APIs प्रदान करता है जिससे आप प्रोजेक्ट आवश्यकताओं के अनुसार बेसलाइन जानकारी को डायनामिक रूप से बदल सकते हैं, जिससे प्रोजेक्ट मैनेजमेंट प्रक्रियाओं पर लचीलापन और नियंत्रण मिलता है।

**प्र: क्या Aspose.Tasks डेवलपर्स के लिए दस्तावेज़ीकरण और सपोर्ट संसाधन प्रदान करता है?**  
उ: हाँ, डेवलपर्स Aspose.Tasks वेबसाइट पर व्यापक दस्तावेज़ीकरण, ट्यूटोरियल, और फ़ोरम तक पहुँच सकते हैं, जिससे सहज इंटीग्रेशन और ट्रबलशूटिंग संभव होती है।

**प्र: क्या Aspose.Tasks for .NET का ट्रायल वर्ज़न उपलब्ध है?**  
उ: हाँ, डेवलपर्स [यहाँ](https://releases.aspose.com/) से Aspose.Tasks for .NET का फ्री ट्रायल वर्ज़न प्राप्त कर सकते हैं, जिससे वे खरीद निर्णय से पहले इसकी फीचर्स और क्षमताओं का मूल्यांकन कर सकते हैं।

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**अंतिम अपडेट:** 2026-03-19  
**टेस्ट किया गया:** Aspose.Tasks 24.12 for .NET  
**लेखक:** Aspose  

---