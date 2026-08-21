---
date: 2026-03-19
description: Aspose.Tasks for .NET ile proje temel çizelgesini nasıl ayarlayacağınızı
  ve görev temel çizelgelerini verimli bir şekilde nasıl yöneteceğinizi öğrenin; proje
  ilerlemesinin doğru takibini sağlayın.
linktitle: Managing Assignment Baseline in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Proje Temel Çizgisini Ayarla – Aspose.Tasks'te Atama Temel Çizgisini Yönetme
url: /tr/net/advanced-features/assignment-baseline/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Proje Temel Çizgisini Ayarlama – Aspose.Tasks'te Atama Temel Çizgisini Yönetme

## Introduction

Proje yönetimi görevleri üzerinde çalışırken, **proje temel çizgisini ayarlamak**, gerçek ilerlemeyi orijinal plana karşı ölçmek için hayati öneme sahiptir. Aspose.Tasks for .NET, **proje temel çizgisini ayarlamanıza** izin vermekle kalmaz, aynı zamanda atama temel çizgileri üzerinde tam kontrol sağlar ve kesin performans takibi yapmanıza olanak tanır. Bu öğreticide, bir projeyi yükleme, temel çizgi ayarlama, atama temel çizgi verilerini okuma ve temel çizgileri karşılaştırma süreçlerini adım adım ele alacağız; böylece projelerinizi güvenle izleyebileceksiniz.

## Quick Answers
- **“Proje temel çizgisini ayarlamak” ne anlama geliyor?** Gerçek performansla daha sonra karşılaştırmak üzere orijinal takvim ve maliyet verilerini kaydeder.  
- **Hangi API yöntemi temel çizgi ayarlar?** `Project.SetBaseline(BaselineType.Baseline)`.  
- **Atama temel çizgileri ayrı bir çağrı gerektirir mi?** Hayır, bir proje temel çizgisi ayarlandığında otomatik olarak depolanırlar.  
- **Hangi formatlar destekleniyor?** MPP, XML, MPX ve daha fazlası Aspose.Tasks aracılığıyla.  
- **Üretim ortamında lisans gerekli mi?** Evet, deneme dışı kullanım için ticari bir lisans gereklidir.

## Prerequisites

Başlamadan önce şunlara sahip olduğunuzdan emin olun:

- C# programlama temelleri.  
- Visual Studio (herhangi bir güncel sürüm).  
- Projenize eklenmiş Aspose.Tasks for .NET kütüphanesi. İndirmek için [buraya](https://releases.aspose.com/tasks/net/) tıklayın.  
- MPP formatında bir proje dosyasına erişim (ör. `AssignmentBaseline2007.mpp`).

## Import Namespaces

C# dosyanızın en üstüne gerekli ad alanlarını ekleyin; böylece derleyici Aspose.Tasks sınıflarını bulabilir.

```csharp
using Aspose.Tasks;
using System;
```

## Step 1: Load Project and Set Project Baseline

Öncelikle mevcut MPP dosyasını yükleyin ve ardından `SetBaseline` metodunu çağırarak **proje temel çizgisini ayarlayın**.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
project.SetBaseline(BaselineType.Baseline);
```

## Step 2: Read Assignment Baseline Information

Temel çizgi ayarlandıktan sonra, her kaynak ataması kendi temel çizgi kayıtlarını içerir. Aşağıdaki döngü, başlangıç/bitiş tarihleri, maliyet, iş ve zaman‑fazlı veriler dahil olmak üzere bu detayları çıkarır ve yazdırır.

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

## Step 3: Compare Assignment Baselines

Farklı atamaların temel çizgilerini, yerleşik eşitlik ve karşılaştırma operatörlerini kullanarak karşılaştırabilirsiniz. Bu, görevler arasındaki takvim kaymalarını veya maliyet aşımlarını tespit etmeniz gerektiğinde oldukça kullanışlıdır.

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

## Common Issues and Solutions

| Issue | Why It Happens | Fix |
|-------|----------------|-----|
| **Baseline data appears empty** | Proje dosyası yalnızca‑okunur modda açıldı veya temel çizgi hiç ayarlanmamış. | Atama temel çizgilerini okumadan önce `project.SetBaseline(BaselineType.Baseline)` metodunu çağırın. |
| **`NullReferenceException` on `TimephasedData`** | Tüm temel çizgiler zaman‑fazlı girişler içermez. | Kodda gösterildiği gibi her zaman `baseline.TimephasedData != null` kontrolü yapın. |
| **Incorrect UID retrieval** | UID değerleri dosya sürümleri arasında farklılık gösterir. | Doğru UID ile `ResourceAssignments.GetByUid` metodunu kullanın veya ihtiyacınız olan atamayı bulmak için döngüyle gezin. |

## Frequently Asked Questions

**Q: Aspose.Tasks tek bir atama için birden fazla temel çizgi yönetebilir mi?**  
A: Evet, Aspose.Tasks her atama için birden fazla temel çizgi destekler; bu sayede proje ilerlemesini zaman içinde kapsamlı bir şekilde izleyebilirsiniz.

**Q: Aspose.Tasks MPP dışındaki farklı proje dosya formatlarıyla uyumlu mu?**  
A: Evet, Aspose.Tasks XML, MPX ve MPP dahil olmak üzere geniş bir proje dosyası formatı yelpazesini destekler; böylece çeşitli proje yönetim araçlarıyla uyumluluk sağlar.

**Q: Aspose.Tasks kullanarak temel çizgi bilgilerini programatik olarak değiştirebilir miyim?**  
A: Kesinlikle, Aspose.Tasks, proje gereksinimlerine göre temel çizgi bilgilerini dinamik olarak değiştirebilmeniz için kapsamlı API'ler sunar; bu da proje yönetim süreçlerinde esneklik ve kontrol sağlar.

**Q: Aspose.Tasks geliştiriciler için dokümantasyon ve destek kaynakları sunuyor mu?**  
A: Evet, geliştiriciler Aspose.Tasks web sitesinde kapsamlı dokümantasyon, öğreticiler ve forumlara erişebilir; bu da sorunsuz entegrasyon ve sorun giderme süreçlerini kolaylaştırır.

**Q: Aspose.Tasks for .NET için bir deneme sürümü mevcut mu?**  
A: Evet, geliştiriciler [buradan](https://releases.aspose.com/) Aspose.Tasks for .NET'in ücretsiz deneme sürümünü edinebilir; böylece satın alma kararı vermeden önce özelliklerini ve yeteneklerini değerlendirebilirler.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-03-19  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose