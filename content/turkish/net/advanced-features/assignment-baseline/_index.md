---
title: Aspose.Tasks'ta Atama Temelini Yönetme
linktitle: Aspose.Tasks'ta Atama Temelini Yönetme
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET ile proje ilerlemesinin ve performansının doğru şekilde izlenmesini sağlayarak atama temellerini nasıl verimli bir şekilde yöneteceğinizi öğrenin.
type: docs
weight: 14
url: /tr/net/advanced-features/assignment-baseline/
---
## giriiş

Proje yönetimi görevleri üzerinde çalışırken, atama temel çizgilerini yönetmek, ilerlemenin doğru şekilde izlenmesi açısından çok önemlidir. Aspose.Tasks for .NET, atama temellerini verimli bir şekilde yönetmek için kapsamlı bir araç seti sağlar. Bu öğreticide, atama temellerini adım adım yönetme sürecini ele alacağız.

## Önkoşullar

Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

- Temel C# programlama dili bilgisi.
- Sisteminizde Visual Studio yüklü.
- Aspose.Tasks for .NET kütüphanesi projenize eklendi. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/tasks/net/).
- MPP formatında bir proje dosyasına erişim.

## Ad Alanlarını İçe Aktar

Aspose.Tasks ile çalışmaya başlamak için gerekli ad alanlarını C# projenize aktarmanız gerekir. C# dosyanızın başına aşağıdaki ad alanlarını ekleyin:

```csharp
using Aspose.Tasks;
using System;


```

## Adım 1: Projeyi Yükleyin ve Temel Çizgiyi Ayarlayın

 Öncelikle proje dosyasını kullanarak yükleyin.`Project` Aspose.Tasks'tan sınıf. Daha sonra, proje için temel tipini kullanarak ayarlayın.`SetBaseline` yöntem.

```csharp
// Belgeler dizinine giden yol.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
project.SetBaseline(BaselineType.Baseline);
```

## Adım 2: Ödev Temel Bilgilerini Okuyun

Projedeki her kaynak atamasını yineleyin ve her atama için temel bilgileri alın.

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

## 3. Adım: Temel Eşitliği Kontrol Edin

Aspose.Tasks tarafından sağlanan çeşitli karşılaştırma yöntemlerini kullanarak farklı atamalara ilişkin temel bilgileri karşılaştırın.

```csharp
var assn1 = project.ResourceAssignments.GetByUid(5);
var assn2 = project.ResourceAssignments.GetByUid(7);

var assignmentBaseline1 = assn1.Baselines.ToList()[0];
var assignmentBaseline2 = assn2.Baselines.ToList()[0];

// Temel eşitliği kontrol edin
Console.WriteLine("Are baselines equal: " + assignmentBaseline1.Equals(assignmentBaseline2));

// Temel karşılaştırmayı kontrol edin
Console.WriteLine("Is baseline 1 less than baseline 2: " + (assignmentBaseline1 < assignmentBaseline2));

// Temel karma kodlarını görüntüle
Console.WriteLine("Assignment baseline 1 hashcode: " + assignmentBaseline1.GetHashCode());
Console.WriteLine("Assignment baseline 2 hashcode: " + assignmentBaseline2.GetHashCode());
```

## Çözüm

Atama temel çizgilerini yönetmek, proje yönetiminin ayrılmaz bir parçasıdır ve ilerlemenin ve performansın doğru şekilde izlenmesine olanak tanır. Aspose.Tasks for .NET ile atama temellerinin yönetimi kolaylaştırılmış ve verimli hale gelir ve geliştiricilere proje yönetimi iş akışlarını geliştirecek güçlü araçlar sağlanır.

## SSS'ler

### S1: Aspose.Tasks tek bir atama için birden fazla temel çizgiyi yönetebilir mi?

Cevap1: Evet, Aspose.Tasks her atama için birden fazla temel çizgiyi destekleyerek projenin zaman içindeki ilerlemesinin kapsamlı bir şekilde izlenmesine olanak tanır.

### S2: Aspose.Tasks, MPP dışındaki çeşitli proje dosyası formatlarıyla uyumlu mudur?

C2: Evet, Aspose.Tasks, XML, MPX ve MPP dahil çok çeşitli proje dosyası formatlarını destekleyerek çeşitli proje yönetimi araçlarıyla uyumluluk sağlar.

### S3: Aspose.Tasks'ı kullanarak temel bilgileri programlı olarak değiştirebilir miyim?

Cevap3: Kesinlikle, Aspose.Tasks, temel bilgileri proje gereksinimlerine göre dinamik olarak değiştirmek için kapsamlı API'ler sağlayarak proje yönetimi süreçleri üzerinde esneklik ve kontrol sunar.

### S4: Aspose.Tasks geliştiriciler için dokümantasyon ve destek kaynakları sunuyor mu?

Cevap4: Evet, geliştiriciler Aspose.Tasks web sitesinden kapsamlı belgelere, eğitimlere ve forumlara erişebilir, böylece sorunsuz entegrasyon ve sorun giderme işlemleri kolaylaştırılabilir.

### S5: Aspose.Tasks for .NET'in deneme sürümü mevcut mu?

 Cevap5: Evet, geliştiriciler Aspose.Tasks for .NET'in ücretsiz deneme sürümünü şu adresten edinebilirler:[Burada](https://releases.aspose.com/)satın alma kararı vermeden önce özelliklerini ve yeteneklerini değerlendirmelerine olanak tanır.