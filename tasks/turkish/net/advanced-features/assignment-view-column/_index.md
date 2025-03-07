---
title: Aspose.Tasks'ta Özel Atama Görünümü Sütunu
linktitle: Aspose.Tasks'ta Özel Atama Görünümü Sütunu
second_title: Aspose.Tasks .NET API'si
description: Proje yönetimi yeteneklerini geliştirmek için Aspose.Tasks for .NET'te özel atama görünümü sütunlarının nasıl ekleneceğini öğrenin.
weight: 16
url: /tr/net/advanced-features/assignment-view-column/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'ta Özel Atama Görünümü Sütunu

## giriiş

Bu eğitimde Aspose.Tasks for .NET kullanarak atama görünümleri için özel sütunların nasıl ekleneceğini inceleyeceğiz. Özel sütunlar esneklik sağlar ve proje yönetimi ihtiyaçlarınızla ilgili ek bilgileri görüntülemenize olanak tanır.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. Temel C# programlama dili bilgisi.
2.  Aspose.Tasks for .NET kütüphanesi kuruldu. Değilse indirebilirsiniz[Burada](https://releases.aspose.com/tasks/net/).
3. Visual Studio gibi entegre bir geliştirme ortamı (IDE).

## Ad Alanlarını İçe Aktar

Öncelikle, özel atama görünümü sütunları oluşturmak için gereken sınıflara ve yöntemlere erişmek için gerekli ad alanlarını içe aktaralım:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Adım 1: Projeyi Yükleyin

 Başlamak için proje dosyanızı kullanarak yükleyin.`Project` sınıf:

```csharp
// Belgeler dizinine giden yol.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject2.mpp");
```

## 2. Adım: Elektronik Tablo Kaydetme Seçeneklerini Oluşturun

 Ardından, bir örneğini oluşturun`Spreadsheet2003SaveOptions` bu, atama görünümü sütunlarını özelleştirmemize olanak tanır:

```csharp
var options = new Spreadsheet2003SaveOptions();
```

## 3. Adım: Özel Sütunu Tanımlayın

 Şimdi özel sütununuzu bir örneğini oluşturarak tanımlayın.`AssignmentViewColumn`. Bu sınıf, atama verilerini sütun metnine dönüştürmek için sütun adını, genişliğini ve bir temsilci işlevini gerektirir:

```csharp
var column = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
```

## 4. Adım: Seçeneklere Özel Sütun Ekleme

Özel sütunu, kaydetme seçeneklerinin atama görünümü sütunları koleksiyonuna ekleyin:

```csharp
options.AssignmentView.Columns.Add(column);
```

## Adım 5: Ödevleri Yineleyin

Projedeki her kaynak atamasını yineleyin ve özel sütun metnini görüntüleyin:

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

## Adım 6: Projeyi Özel Sütunlarla Kaydetme

Son olarak projeyi özel atama görünümü sütunlarıyla kaydedin:

```csharp
project.Save(OutDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## Çözüm

Bu eğitimde Aspose.Tasks for .NET'i kullanarak özel atama görünümü sütunlarının nasıl ekleneceğini öğrendik. Özel sütunlar, proje gereksinimlerinize göre uyarlanmış ek bilgilerin görüntülenmesinde esneklik sunarak proje yönetimi yeteneklerini geliştirir.

## SSS'ler

### S1: Atama görünümüne birden çok özel sütun ekleyebilir miyim?

 Cevap1: Evet, ek örnekler oluşturarak birden çok özel sütun ekleyebilirsiniz.`AssignmentViewColumn` ve bunları eklemek`Columns` Toplamak.

### S2: Ortak atama alanları için önceden tanımlanmış dönüştürücüler mevcut mu?

C2: Evet, Aspose.Tasks, ortak atama alanları için önceden tanımlanmış dönüştürücüler sağlayarak özel sütunlar için veri çıkarmayı kolaylaştırır.

### S3: Metni biçimlendirme veya stil uygulama gibi özel sütunların görünümünü özelleştirebilir miyim?

C3: Evet, genişlik, yazı tipi ve hizalama gibi özellikleri değiştirerek özel sütunların görünümünü özelleştirebilirsiniz.

### S4: Varsayılan sütunları atama görünümünden kaldırmak mümkün müdür?

 Cevap4: Evet, varsayılan sütunları listeden hariç tutarak kaldırabilirsiniz.`Columns` toplama veya genişliklerini sıfıra ayarlama.

### S5: Aspose.Tasks, projelerin özel sütunlu e-tabloların yanı sıra diğer formatlara aktarılmasını da destekliyor mu?

Cevap5: Evet, Aspose.Tasks, projelerin PDF, HTML ve XML gibi çeşitli formatlara aktarılmasını destekleyerek çok yönlü proje raporlama seçeneklerine olanak tanır.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
