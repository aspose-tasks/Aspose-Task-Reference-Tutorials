---
title: Aspose.Tasks ile Verimli MS Project Görev Gruplaması
linktitle: Aspose.Tasks'ta Görevleri Gruplama
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'i kullanarak Microsoft Project görevlerini etkili bir şekilde nasıl gruplandıracağınızı öğrenin.
weight: 25
url: /tr/net/tasks-project-management/grouping-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks ile Verimli MS Project Görev Gruplaması

## giriiş
Microsoft Project'te görevleri yönetmek bazen zorlayıcı olabilir, özellikle de konu onları verimli bir şekilde organize etmek olduğunda. Aspose.Tasks for .NET, görevleri etkili bir şekilde gruplamak için işlevsellikler sağlayarak buna kapsamlı bir çözüm sunuyor. Bu eğitimde Aspose.Tasks for .NET'i kullanarak MS Project görevlerini nasıl gruplandıracağımızı inceleyeceğiz.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
1.  Aspose.Tasks for .NET Kütüphanesi: Aspose.Tasks for .NET kütüphanesini şu adresten indirip yükleyin:[Burada](https://releases.aspose.com/tasks/net/).
2. Geliştirme Ortamı: Bir .NET geliştirme ortamı kurduğunuzdan emin olun.
3. Temel C# Bilgisi: C# programlama diline aşina olmak faydalı olacaktır.

## Ad Alanlarını İçe Aktar
Aspose.Tasks işlevlerini kullanmak için öncelikle gerekli ad alanlarını C# projenize aktarmanız gerekir:
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Adım 1: MS Proje Dosyasını Yükleyin
Aşağıdaki kodu kullanarak MS Project dosyanızı yükleyerek başlayın:
```csharp
// Belgeler dizininin yolu.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "YourProjectFile.mpp");
```
## 2. Adım: Görev Gruplarına Erişin
Daha sonra proje içindeki görev gruplarına erişelim:
```csharp
Console.WriteLine("Task Groups Count: " + project.TaskGroups.Count);
var group = project.TaskGroups.ToList()[1];
```
## 3. Adım: Grup Bilgilerini Alın
Şimdi görev grubuyla ilgili bilgileri alın:
```csharp
Console.WriteLine("Task Group Uid: " + group.Uid);
Console.WriteLine("Task Group Index: " + group.Index);
Console.WriteLine("Task Group Name: " + group.Name);
Console.WriteLine("Is Task Group Maintain Hierarchy?: " + group.MaintainHierarchy);
Console.WriteLine("Is Task Group Show In Menu?: " + group.ShowInMenu);
Console.WriteLine("Is Task Group Show Summary?: " + group.ShowSummary);
```
## Adım 4: Grup Kriterlerine Erişim
Görev grubu için belirlenen kriterlere erişin:
```csharp
Console.WriteLine("Task Group Criteria count: " + group.GroupCriteria.Count);
```
## Adım 5: Kriter Bilgilerini Alın
Her kriter hakkında ayrıntılı bilgi alın:
```csharp
foreach (var criterion in group.GroupCriteria)
{
    Console.WriteLine("Task Criterion Field: " + criterion.Field);
    Console.WriteLine("Task Criterion GroupOn: " + criterion.GroupOn);
    Console.WriteLine("Task Criterion Cell Color: " + criterion.CellColor);
    Console.WriteLine("Task Criterion Pattern: " + criterion.Pattern);
    if (group == criterion.ParentGroup)
    {
        Console.WriteLine("Parent Group is equal to task Group.");
    }
    Console.WriteLine("Font Name: " + criterion.Font.FontFamily);
    Console.WriteLine("Font Size: " + criterion.Font.Size);
    Console.WriteLine("Font Style: " + criterion.Font.Style);
    Console.WriteLine("Ascending/Descending: " + criterion.Ascending);
}
```
Bu adımları izleyerek Aspose.Tasks for .NET'i kullanarak MS Project görevlerini etkili bir şekilde gruplandırabilir, proje verilerinizin organizasyonunu ve yönetimini geliştirebilirsiniz.

## Çözüm
Sonuç olarak Aspose.Tasks for .NET, MS Project görevlerini gruplamak için güçlü yetenekler sunarak proje verilerinin daha iyi organize edilmesine ve yönetilmesine olanak tanır. Bu öğreticide özetlenen adımları izleyerek bu özellikleri .NET uygulamalarınızda verimli bir şekilde kullanabilirsiniz.
## SSS'ler
### Görevleri özel ölçütlere göre gruplayabilir miyim?
Evet, Aspose.Tasks for .NET'i kullanarak görevleri özel gereksinimlerinize göre gruplamak için özel kriterler tanımlayabilirsiniz.
### Aspose.Tasks, MS Project dosyalarının farklı sürümlerini destekliyor mu?
Evet, Aspose.Tasks, MS Project dosyalarının çeşitli sürümlerini destekleyerek uyumluluk ve kusursuz entegrasyon sağlar.
### Aspose.Tasks for .NET'in deneme sürümü mevcut mu?
 Evet, Aspose.Tasks for .NET'in ücretsiz deneme sürümünü şu adresten edinebilirsiniz:[Burada](https://releases.aspose.com/).
### Gruplandırılmış görevlerin görünümünü özelleştirebilir miyim?
Kesinlikle Aspose.Tasks, hücre renkleri, yazı tipleri ve stiller dahil olmak üzere gruplandırılmış görevlerin görünümünü özelleştirmek için seçenekler sunar.
### Aspose.Tasks for .NET desteğini nerede bulabilirim?
 Aspose.Tasks for .NET için destek ve yardımı şurada bulabilirsiniz:[Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
