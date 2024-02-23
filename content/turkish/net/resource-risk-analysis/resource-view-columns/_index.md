---
title: Aspose.Tasks'ta MS Project Kaynak Görünümü Sütunlarını Özelleştirin
linktitle: Aspose.Tasks'ta Kaynak Görünümü Sütunlarını Özelleştirme
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'i kullanarak MS Project kaynak görünümü sütunlarını verimli bir şekilde nasıl özelleştireceğinizi öğrenin. Daha iyi proje yönetimi için özel görünümler oluşturun.
type: docs
weight: 17
url: /tr/net/resource-risk-analysis/resource-view-columns/
---
## giriiş
Aspose.Tasks for .NET, geliştiricilerin Microsoft Project dosyalarıyla programlı olarak çalışmasına olanak tanıyan güçlü bir API'dir. Proje yönetimindeki yaygın görevlerden biri, görünümleri belirli bilgileri gösterecek şekilde özelleştirmektir. Bu eğitimde Aspose.Tasks for .NET'i kullanarak MS Project kaynak görünümü sütunlarının nasıl özelleştirileceğini inceleyeceğiz.
## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1.  Aspose.Tasks for .NET Library: Buradan indirebilirsiniz.[Burada](https://releases.aspose.com/tasks/net/).
2. Microsoft Project Dosyası: Test için örnek bir MS Project dosyasını hazır bulundurun.
3. Geliştirme Ortamı: .NET çerçevesiyle kurulmuş bir geliştirme ortamı.
## Ad Alanlarını İçe Aktar
Öncelikle gerekli namespace’leri projemize aktaralım:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Globalization;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
## Adım 1: Proje Dosyasını Yükleyin
Aspose.Tasks API'yi kullanarak MS Project dosyasını yükleyin:
```csharp
var project = new Project("Your_Project_File_Path.mpp");
```
## Adım 2: Kaynağı Alın ve Seçenekleri Tanımlayın
Ardından, görünüm sütunlarını özelleştirmek istediğiniz kaynağı alın ve PDF kaydetme seçeneklerini tanımlayın:
```csharp
var resource = project.Resources.GetById(1);
var options = new PdfSaveOptions();
```
## 3. Adım: Özel Sütunları Tanımlayın
Şimdi kaynak görünümü için özel sütunlar tanımlayın. Çeşitli alanlar belirtebilir ve hatta özel hesaplamalar için delegeleri kullanabilirsiniz:
```csharp
var columns = new List<ViewColumn>
{
    new ResourceViewColumn(100, Field.ResourceName),
    new ResourceViewColumn(100, Field.ResourceActualWork),
    new ResourceViewColumn(100, Field.ResourceCost),
    new ResourceViewColumn(
        "Resource Cost2", 
        80,
        delegate(Resource res)
        {
            return res.Get(Rsc.Cost).ToString(CultureInfo.InvariantCulture);
        }),
    new ResourceViewColumn(
        "Resource Cost2", 
        80,
        delegate(Resource res)
        {
            return res.Get(Rsc.Cost).ToString(CultureInfo.InvariantCulture);
        }, 
        Field.ResourceCost2)
};
```
## Adım 4: Sütunlar Üzerinde Yineleme Yapın
Tanımlanan sütunlar üzerinde yineleme yapın ve özelliklerini görüntüleyin:
```csharp
foreach (var column in columns)
{
    var col = (ResourceViewColumn)column;
    Console.WriteLine("Column Name: " + col.Name);
    Console.WriteLine("Column Field: " + col.Field);
    Console.WriteLine("Column Text: " + col.GetColumnText(resource));
    Console.WriteLine();
}
```
## Adım 5: Özelleştirilmiş Görünümü Kaydedin
Son olarak özel görünümü ayarlayın ve PDF dosyası olarak kaydedin:
```csharp
options.View = new ProjectView(columns);
options.PresentationFormat = PresentationFormat.ResourceUsage;
project.Save("Output_PDF_File_Path.pdf", options);
```
Bu adımları izleyerek Aspose.Tasks for .NET'i kullanarak MS Project kaynak görünümü sütunlarını verimli bir şekilde özelleştirebilirsiniz.
## Çözüm
MS Project kaynak görünümü sütunlarının özelleştirilmesi, projenizin ihtiyaçlarına göre uyarlanmış ilgili bilgilerin görüntülenmesi için çok önemlidir. Aspose.Tasks for .NET ile bu görev basit ve verimli hale gelir ve özelleştirilmiş görünümleri zahmetsizce oluşturmanıza olanak tanır.
## SSS'ler
### Görünümleri kaynakların yanı sıra diğer öğeler için de özelleştirebilir miyim?
Evet, Aspose.Tasks görevler, atamalar ve diğer proje öğeleri için de özelleştirmeye olanak tanır.
### Aspose.Tasks, görünümlerin PDF dışındaki formatlarda kaydedilmesini destekliyor mu?
Evet, görünümleri XLSX, HTML ve resimler gibi çeşitli formatlarda kaydedebilirsiniz.
### Özel görünüme biçimlendirme uygulamak mümkün mü?
Aspose.Tasks, kişiselleştirilmiş görünümlerinizin görünümünü geliştirmek için kesinlikle kapsamlı biçimlendirme seçenekleri sunar.
### Özel görünümü değişen proje verilerine göre dinamik olarak güncelleyebilir miyim?
Evet, temeldeki proje verileri değiştiğinde özel görünümü güncelleyebilir ve yeniden oluşturabilirsiniz.
### Aspose.Tasks platformlar arası geliştirmeyi destekliyor mu?
Aspose.Tasks for .NET öncelikli olarak .NET platformlarını hedefler ancak Java ve diğer platformlar için de versiyonlar mevcuttur.