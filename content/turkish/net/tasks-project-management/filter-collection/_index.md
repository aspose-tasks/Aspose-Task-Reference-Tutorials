---
title: Aspose.Tasks ile MS Proje Filtrelerini Verimli Bir Şekilde Yönetin
linktitle: Aspose.Tasks'ta Filtre Koleksiyonunu Yönetme
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'i kullanarak filtre MS Project koleksiyonlarını etkili bir şekilde nasıl yöneteceğinizi öğrenin.
type: docs
weight: 17
url: /tr/net/tasks-project-management/filter-collection/
---
## giriiş
Bu eğitimde, Aspose.Tasks for .NET'i kullanarak filtre MS Project koleksiyonlarını etkili bir şekilde nasıl yönetebileceğimizi keşfedeceğiz. Filtreleri yönetmek, proje verilerini verimli bir şekilde organize etmek ve analiz etmek için çok önemlidir. Aspose.Tasks, görev ve kaynak filtrelerini sorunsuz bir şekilde yönetmek için güçlü işlevsellik sağlar.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1.  Aspose.Tasks for .NET Kurulumu: Aspose.Tasks for .NET'i aşağıdaki adresten indirip yükleyin:[İndirme: {link](https://releases.aspose.com/tasks/net/).
2. .NET Geliştirme Ortamına Erişim: Aspose.Tasks ile çalışacak şekilde ayarlanmış bir .NET geliştirme ortamına sahip olduğunuzdan emin olun.

## Ad Alanlarını İçe Aktar
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## Adım 1: Proje Dosyasını Yükleyin
```csharp
// Belgeler dizininin yolu.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadFilterDefinitionData.mpp");
```
## Adım 2: Görev Filtrelerini Yineleyin
```csharp
Console.WriteLine("Print task filters of {0} project: ", project.Get(Prj.Name));
Console.WriteLine("Task Filters Count: " + project.TaskFilters.Count);
foreach (var filter in project.TaskFilters)
{
    Console.WriteLine("All Tasks: " + filter.Name);
    Console.WriteLine("Task Item: " + filter.FilterType);
    Console.WriteLine("Task Filters Show In Menu: " + filter.ShowInMenu);
    Console.WriteLine("Task filter ShowRelatedSummaryRows: " + filter.ShowRelatedSummaryRows);
    Console.WriteLine();
}
```
## Adım 3: Kaynak Filtreleri Üzerinde Yineleme Yapın
```csharp
Console.WriteLine("Project.ResourceFilters count: " + project.ResourceFilters.Count);
foreach (var filter in project.ResourceFilters)
{
    Console.WriteLine("Resource Filter Item Type: Item.ResourceType: " + filter.FilterType);
    Console.WriteLine("Resource filter ShowInMenu" + filter.ShowInMenu);
    Console.WriteLine("Resource filter ShowRelatedSummaryRows: " + filter.ShowRelatedSummaryRows);
}
```
## 4. Adım: Filtreleri Temizleyin ve Kopyalayın
```csharp
var otherProject = new Project(DataDir + "Blank2010.mpp");
// Diğer projenin filtrelerini temizle
otherProject.TaskFilters.Clear();
// Filtreleri diğer projeye kopyala
var filters = new Filter[project.TaskFilters.Count];
project.TaskFilters.CopyTo(filters, 0);
foreach (var filter in filters)
{
    otherProject.TaskFilters.Add(filter);
}
```
## 5. Adım: Özel Görev Filtresi Ekleyin
```csharp
// Özel görev filtresi ekle
var customFilter = new Filter();
customFilter.Name = "Custom Filter";
customFilter.ShowInMenu = true;
customFilter.ShowRelatedSummaryRows = true;
if (!otherProject.TaskFilters.Contains(customFilter))
{
    if (!otherProject.TaskFilters.IsReadOnly)
    {
        otherProject.TaskFilters.Add(customFilter);
    }
}
```
## Adım 6: Tüm Filtreleri Kaldır
```csharp
// Tüm filtreleri kaldır
List<Filter> filtersToDelete = otherProject.TaskFilters.ToList();
foreach (var filter in filtersToDelete)
{
    otherProject.TaskFilters.Remove(filter);
}
```
Bu adımları izleyerek Aspose.Tasks for .NET'i kullanarak filtre MS Project koleksiyonlarını verimli bir şekilde yönetebilirsiniz.

## Çözüm
MS Project koleksiyonlarındaki filtreleri etkili bir şekilde yönetmek, proje verilerinin düzenlenmesi ve analiz edilmesi açısından çok önemlidir. Aspose.Tasks for .NET, görev ve kaynak filtrelerini sorunsuz bir şekilde yönetmek için kapsamlı işlevsellik sağlayarak geliştiricilerin proje yönetimi görevlerini verimli bir şekilde kolaylaştırmalarını sağlar.
## SSS'ler
### S: Aspose.Tasks karmaşık proje yapılarını yönetebilir mi?
C: Aspose.Tasks, karmaşık olanlar da dahil olmak üzere çeşitli proje yapılarını yönetmek için kapsamlı proje yönetimi yetenekleri sağlayan güçlü özellikler sunar.
### S: Aspose.Tasks, MS Project dosyalarının farklı sürümleriyle uyumlu mudur?
C: Evet, Aspose.Tasks çok çeşitli MS Project dosya formatlarını destekleyerek farklı sürümler arasında uyumluluk sağlar.
### S: Filtreleri belirli proje gereksinimlerine göre özelleştirebilir miyim?
C: Kesinlikle! Aspose.Tasks, geliştiricilerin benzersiz proje ihtiyaçlarına göre uyarlanmış özel filtreler oluşturmasına olanak tanıyarak esnekliği ve verimliliği artırır.
### S: Aspose.Tasks dokümantasyon ve destek kaynakları sağlıyor mu?
C: Evet, Aspose.Tasks, geliştiricilere proje uygulamalarının her adımında yardımcı olmak için kapsamlı belgeler, eğitimler ve özel bir destek forumu sunuyor.
### S: Aspose.Tasks'ın deneme sürümü mevcut mu?
C: Evet, geliştiriciler, satın alma kararı vermeden önce Aspose.Tasks'ın ücretsiz deneme sürümüne erişebilir ve özelliklerini keşfedebilirler.