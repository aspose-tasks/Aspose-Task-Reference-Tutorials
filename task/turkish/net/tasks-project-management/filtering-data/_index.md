---
title: Aspose.Tasks ile Verimli Veri Filtreleme
linktitle: Aspose.Tasks'ta Verileri Filtreleme
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'i kullanarak MS Project dosyalarındaki verileri nasıl filtreleyeceğinizi öğrenin. Üretkenliği ve analiz yeteneklerini zahmetsizce geliştirin.
type: docs
weight: 16
url: /tr/net/tasks-project-management/filtering-data/
---
## giriiş
Aspose.Tasks for .NET, Microsoft Project dosyalarındaki verileri filtrelemek için güçlü işlevsellik sağlayarak kullanıcıların proje bilgilerini verimli bir şekilde yönetmesine ve analiz etmesine olanak tanır. Bu eğitimde, Aspose.Tasks'ı kullanarak verileri adım adım kılavuz formatında nasıl filtreleyeceğimizi keşfedeceğiz.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
### 1. Aspose.Tasks for .NET'i yükleyin
 Aspose.Tasks for .NET'i şu adresten indirip yükleyin:[indirme sayfası](https://releases.aspose.com/tasks/net/). Kitaplığı geliştirme ortamınıza kurmak için sağlanan kurulum talimatlarını izleyin.
### 2. Geliştirme Ortamınızı Kurun
.NET programlama için çalışan bir geliştirme ortamına sahip olduğunuzdan emin olun. Buna Visual Studio gibi uyumlu bir IDE ve C# programlama dilinin temel düzeyde anlaşılması da dahildir.
### 3. Örnek Microsoft Project Dosyasına Erişin
Filtrelemek istediğiniz verileri içeren örnek bir Microsoft Project dosyası (.mpp) hazırlayın. Dosyanın proje dizininizde erişilebilir olduğundan emin olun.
## Ad Alanlarını İçe Aktar
Aspose.Tasks işlevlerini kullanmak için C# kod dosyanıza gerekli ad alanlarını içe aktarın.

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Saving;
using System;
using System.Collections.Generic;

```
Şimdi MS Project'te Aspose.Tasks kullanarak veri filtreleme sürecini birden fazla adıma ayıralım:
## Adım 1: Proje Dosyasını Yükleyin
```csharp
string dataDir = "Your Document Directory";
var project = new Project(dataDir + "SampleProject.mpp");
```
 Değiştirildiğinden emin olun`"Your Document Directory"`proje dosyası dizininizin yolu ile.
## 2. Adım: Görev Filtrelerini Alın
```csharp
List<Filter> filters = project.TaskFilters.ToList();
```
Projede mevcut olan görev filtrelerinin listesini alın.
## 3. Adım: Görev Filtresi Ayrıntılarını Görüntüleme
```csharp
foreach (var filter in filters)
{
    Console.WriteLine("Uid: " + filter.Uid);
    Console.WriteLine("Index: " + filter.Index);
    Console.WriteLine("Name: " + filter.Name);
    Console.WriteLine("Type: " + filter.FilterType);
    Console.WriteLine("Show In Menu: " + filter.ShowInMenu);
    Console.WriteLine("Show Related Summary Rows: " + filter.ShowRelatedSummaryRows);
}
```
Görev filtreleri listesini yineleyin ve Kullanıcı Kimliği, Dizin, Ad, Filtre Türü, Menüde Göster ve İlgili Özet Satırlarını Göster gibi ayrıntılarını görüntüleyin.
## 4. Adım: Kaynak Filtrelerini Kontrol Edin
```csharp
List<Filter> resourceFilters = project.ResourceFilters.ToList();
```
Projede mevcut olan kaynak filtrelerinin listesini alın.
## Adım 5: Kaynak Filtresi Ayrıntılarını Görüntüleyin
```csharp
Console.WriteLine("Project.ResourceFilters count: " + resourceFilters.Count);
Console.WriteLine("Resource Filter Item Type: Item.ResourceType: " + resourceFilters[0].FilterType);
Console.WriteLine("Resource filter ShowInMenu" + resourceFilters[0].ShowInMenu);
Console.WriteLine("Resource filter ShowRelatedSummaryRows: " + resourceFilters[0].ShowRelatedSummaryRows);
```
Sayım, filtre türü, Menüde Göster ve İlgili Özet Satırlarını Göster dahil olmak üzere kaynak filtrelerinin ayrıntılarını görüntüleyin.
## Çözüm
Aspose.Tasks for .NET'i kullanarak MS Project dosyalarındaki verileri filtrelemek, üretkenliği ve analiz yeteneklerini artıran basit bir işlemdir. Bu eğitimde özetlenen adımları izleyerek proje bilgilerini belirli kriterlere göre verimli bir şekilde yönetebilirsiniz.
## SSS'ler
### S: Aspose.Tasks verileri özel kriterlere göre filtreleyebilir mi?
C: Evet, Aspose.Tasks, proje gereksinimlerinize göre uyarlanmış özel kriterlere göre verilerin filtrelenmesine olanak tanır.
### S: Aspose.Tasks, Microsoft Project dosyalarının tüm sürümleriyle uyumlu mudur?
C: Aspose.Tasks, Microsoft Project dosyalarının çeşitli sürümlerini destekleyerek farklı ortamlar arasında uyumluluk sağlar.
### S: Aspose.Tasks'ta birden fazla filtreyi birleştirebilir miyim?
C: Aspose.Tasks'ta veri çıkarma ve analizini geliştirmek için kesinlikle birden fazla filtreyi birleştirebilirsiniz.
### S: Aspose.Tasks daha fazla yardım için belgeler sağlıyor mu?
 C: Evet, kapsamlı bilgilere başvurabilirsiniz[dokümantasyon](https://reference.aspose.com/tasks/net/) Ayrıntılı rehberlik için Aspose.Tasks tarafından sağlanmıştır.
### S: Aspose.Tasks kullanıcıları için teknik destek mevcut mu?
 C: Evet, teknik desteğe şu adresten erişebilirsiniz:[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15) Karşılaştığınız herhangi bir soru veya sorun için.