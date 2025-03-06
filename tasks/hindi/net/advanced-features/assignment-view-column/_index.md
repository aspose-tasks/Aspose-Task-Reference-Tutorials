---
title: Aspose.Tasks में कस्टम असाइनमेंट व्यू कॉलम
linktitle: Aspose.Tasks में कस्टम असाइनमेंट व्यू कॉलम
second_title: Aspose.Tasks .NET API
description: प्रोजेक्ट प्रबंधन क्षमताओं को बढ़ाने के लिए .NET के लिए Aspose.Tasks में कस्टम असाइनमेंट व्यू कॉलम जोड़ने का तरीका जानें।
weight: 16
url: /hi/net/advanced-features/assignment-view-column/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks में कस्टम असाइनमेंट व्यू कॉलम

## परिचय

इस ट्यूटोरियल में, हम यह पता लगाएंगे कि .NET के लिए Aspose.Tasks का उपयोग करके असाइनमेंट व्यू के लिए कस्टम कॉलम कैसे जोड़ें। कस्टम कॉलम लचीलापन प्रदान करते हैं और आपको अपनी परियोजना प्रबंधन आवश्यकताओं से संबंधित अतिरिक्त जानकारी प्रदर्शित करने की अनुमति देते हैं।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

1. C# प्रोग्रामिंग भाषा का बुनियादी ज्ञान।
2.  .NET लाइब्रेरी के लिए Aspose.Tasks स्थापित। यदि नहीं, तो आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/tasks/net/).
3. एक एकीकृत विकास वातावरण (आईडीई) जैसे विजुअल स्टूडियो।

## नामस्थान आयात करें

सबसे पहले, आइए कस्टम असाइनमेंट व्यू कॉलम बनाने के लिए आवश्यक कक्षाओं और विधियों तक पहुंचने के लिए आवश्यक नामस्थान आयात करें:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## चरण 1: प्रोजेक्ट लोड करें

 आरंभ करने के लिए, का उपयोग करके अपनी प्रोजेक्ट फ़ाइल लोड करें`Project` कक्षा:

```csharp
// वें दस्तावेज़ निर्देशिका का पथ.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject2.mpp");
```

## चरण 2: स्प्रेडशीट सेव विकल्प बनाएं

 इसके बाद, का एक उदाहरण बनाएं`Spreadsheet2003SaveOptions` जो हमें असाइनमेंट दृश्य कॉलम को अनुकूलित करने की अनुमति देता है:

```csharp
var options = new Spreadsheet2003SaveOptions();
```

## चरण 3: कस्टम कॉलम को परिभाषित करें

 अब, एक उदाहरण बनाकर अपने कस्टम कॉलम को परिभाषित करें`AssignmentViewColumn`. इस वर्ग को असाइनमेंट डेटा को कॉलम टेक्स्ट में बदलने के लिए कॉलम नाम, चौड़ाई और एक प्रतिनिधि फ़ंक्शन की आवश्यकता होती है:

```csharp
var column = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
```

## चरण 4: विकल्पों में कस्टम कॉलम जोड़ें

सेव विकल्पों के असाइनमेंट व्यू कॉलम संग्रह में कस्टम कॉलम जोड़ें:

```csharp
options.AssignmentView.Columns.Add(column);
```

## चरण 5: असाइनमेंट के माध्यम से पुनरावृति करें

प्रोजेक्ट में प्रत्येक संसाधन असाइनमेंट को दोहराएँ और कस्टम कॉलम टेक्स्ट प्रदर्शित करें:

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var col in options.AssignmentView.Columns)
    {
        var assnCol = (AssignmentViewColumn)col;
        Console.WriteLine("Column Field: " + assnCol.Field);
        Console.WriteLine("Column Text (converted): " + assnCol.GetColumnText(assignment));
        Console.WriteLine();
    }
}
```

## चरण 6: प्रोजेक्ट को कस्टम कॉलम के साथ सहेजें

अंत में, प्रोजेक्ट को कस्टम असाइनमेंट व्यू कॉलम के साथ सहेजें:

```csharp
project.Save(OutDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## निष्कर्ष

इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Aspose.Tasks का उपयोग करके कस्टम असाइनमेंट व्यू कॉलम कैसे जोड़ें। कस्टम कॉलम आपकी परियोजना आवश्यकताओं के अनुरूप अतिरिक्त जानकारी प्रदर्शित करने, परियोजना प्रबंधन क्षमताओं को बढ़ाने में लचीलापन प्रदान करते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या मैं असाइनमेंट दृश्य में एकाधिक कस्टम कॉलम जोड़ सकता हूँ?

 A1: हां, आप अतिरिक्त उदाहरण बनाकर कई कस्टम कॉलम जोड़ सकते हैं`AssignmentViewColumn` और उन्हें इसमें जोड़ रहा हूँ`Columns` संग्रह।

### Q2: क्या सामान्य असाइनमेंट फ़ील्ड के लिए पूर्वनिर्धारित कनवर्टर उपलब्ध हैं?

A2: हां, Aspose.Tasks सामान्य असाइनमेंट फ़ील्ड के लिए पूर्वनिर्धारित कन्वर्टर्स प्रदान करता है, जिससे कस्टम कॉलम के लिए डेटा निकालना आसान हो जाता है।

### Q3: क्या मैं कस्टम कॉलम के स्वरूप को अनुकूलित कर सकता हूं, जैसे टेक्स्ट को फ़ॉर्मेट करना या शैलियों को लागू करना?

A3: हाँ, आप चौड़ाई, फ़ॉन्ट और संरेखण जैसे गुणों को संशोधित करके कस्टम कॉलम की उपस्थिति को अनुकूलित कर सकते हैं।

### Q4: क्या असाइनमेंट दृश्य से डिफ़ॉल्ट कॉलम को हटाना संभव है?

 उ4: हाँ, आप डिफ़ॉल्ट कॉलमों को बाहर करके उन्हें हटा सकते हैं`Columns` संग्रह करना या उनकी चौड़ाई शून्य पर सेट करना।

### Q5: क्या Aspose.Tasks कस्टम कॉलम के साथ स्प्रेडशीट के अलावा अन्य प्रारूपों में परियोजनाओं को निर्यात करने का समर्थन करता है?

A5: हाँ, Aspose.Tasks पीडीएफ, HTML और XML जैसे विभिन्न प्रारूपों में परियोजनाओं को निर्यात करने का समर्थन करता है, जिससे बहुमुखी परियोजना रिपोर्टिंग विकल्पों की अनुमति मिलती है।
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
