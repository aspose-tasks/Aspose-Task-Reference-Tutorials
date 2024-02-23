---
title: Aspose.Tasks .NET'te Anahat Kod Tanımlarının Toplanması
linktitle: Aspose.Tasks'ta Anahat Kod Tanımlarının Toplanması
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'i kullanarak Microsoft Project belgelerindeki anahat kodu tanımlarını nasıl değiştireceğinizi öğrenin. Proje verilerinizin zahmetsizce sınıflandırılması.
type: docs
weight: 13
url: /tr/net/outline-code-page-settings/outline-code-definition-collection/
---
## giriiş
Aspose.Tasks, Microsoft Project belgelerini kolaylıkla ve etkili bir şekilde yönetmek için tasarlanmış güçlü bir .NET kitaplığıdır. Temel özelliklerinden biri, kullanıcıların proje verilerini etkili bir şekilde organize etmesine ve kategorilere ayırmasına olanak tanıyan anahat kodu tanımlarıyla çalışma yeteneğidir. Bu eğitimde Aspose.Tasks for .NET'i kullanarak taslak kod tanımlarıyla nasıl çalışılacağını inceleyeceğiz.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1. Temel C# Anlayışı: C# programlama diline aşina olmak faydalı olacaktır.
2. Visual Studio: Visual Studio'yu veya tercih edilen herhangi bir C# geliştirme ortamını yükleyin.
3.  Aspose.Tasks for .NET: Aspose.Tasks for .NET kütüphanesini şu adresten indirip yükleyin:[Burada](https://releases.aspose.com/tasks/net/).

## Ad Alanlarını İçe Aktar
Başlamak için gerekli ad alanlarını içe aktardığınızdan emin olun:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## 1. Adım: Bir Microsoft Project Belgesi Yükleyin
İlk olarak, anahat kodu tanımlarıyla çalışmaya başlamak için bir Microsoft Project belgesi yükleyin:
```csharp
// Belgeler dizininin yolu.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineCodes.mpp");
```
## Adım 2: Anahat Kodu Tanımlarına Erişim
Şimdi proje içerisindeki anahat kod tanımlarına erişelim:
```csharp
Console.WriteLine("Count of outline code definitions: " + project.OutlineCodes.Count);
foreach (var outlineCode in project.OutlineCodes)
{
	Console.WriteLine("Field Name: " + outlineCode.FieldName);
	Console.WriteLine("Alias: " + outlineCode.Alias);
	Console.WriteLine();
}
```
## 3. Adım: Özel Anahat Kodu Tanımlarını Ekleyin
Özel anahat kodu tanımlarını aşağıdaki gibi ekleyebilirsiniz:
```csharp
var outlineCodeDefinition = new OutlineCodeDefinition { FieldId = ((int)ExtendedAttributeTask.OutlineCode3).ToString("D"), Alias = "My Outline Code" };
if (!project.OutlineCodes.IsReadOnly)
{
    project.OutlineCodes.Add(outlineCodeDefinition);
}
```
## 4. Adım: Anahat Kodu Tanımlarını Değiştirin
Mevcut anahat kodu tanımlarını kolayca değiştirin:
```csharp
var index = project.OutlineCodes.IndexOf(outlineCodeDefinition);
project.OutlineCodes[index].Alias = "New Alias";
```
## Adım 5: Anahat Kodu Tanımlarını Kaldırma
Artık ihtiyaç duyulmadığında anahat kodu tanımlarını kaldırın:
```csharp
if (project.OutlineCodes.Contains(outlineCodeDefinition))
{
    project.OutlineCodes.Remove(outlineCodeDefinition);
}
```
## Adım 6: Değişiklikleri Kaydet
Son olarak değişikliklerinizi proje belgesine kaydedin:
```csharp
project.Save(DataDir + "ModifiedOutlineCodes.mpp", SaveFileFormat.MPP);
```

## Çözüm
Sonuç olarak Aspose.Tasks for .NET, Microsoft Project belgelerindeki anahat kod tanımlarını yönetmek için kapsamlı işlevsellik sağlar. Bu öğreticide özetlenen adımları izleyerek, proje verilerinizi etkili bir şekilde düzenlemek ve kategorilere ayırmak için anahat kodu tanımlarını verimli bir şekilde değiştirebilirsiniz.
## SSS'ler
### S: Tek bir projeye birden fazla anahat kodu tanımı ekleyebilir miyim?
 C: Evet, gereksinimlerinize göre bir projeye birden fazla anahat kodu tanımı ekleyebilirsiniz. Basitçe kullanın`Add` Eklemek istediğiniz her tanım için yöntem.
### S: Bir projedeki tüm anahat kodu tanımlarını tek seferde kaldırmak mümkün müdür?
 C: Evet, bir projedeki tüm anahat kodu tanımlarını aşağıdaki komutu kullanarak temizleyebilirsiniz:`Clear` yöntem.
### S: Salt okunur bir anahat kodu tanımını değiştirmeye çalışırsam ne olur?
C: Anahat kodu tanımı salt okunursa onu doğrudan değiştiremezsiniz. Herhangi bir değişiklik yapmadan önce salt okunur durumunu kontrol etmeniz gerekir.
### S: Bir projeye ekleyebileceğim anahat kodu tanımlarının sayısında herhangi bir sınırlama var mı?
C: Aspose.Tasks for .NET, bir projeye ekleyebileceğiniz taslak kod tanımlarının sayısına herhangi bir özel sınırlama getirmez. Ancak çok sayıda tanımla çalışırken performans sonuçlarını göz önünde bulundurun.
### S: Görevleri özel ölçütlere göre gruplandırmak için anahat kodu tanımlarını kullanabilir miyim?
C: Evet, anahat kodu tanımları, görevleri özel kriterlere göre kategorilere ayırmanıza olanak tanıyarak proje verilerinin düzenlenmesinde esneklik sağlar.## Kaynak Kodunu Tamamlayın