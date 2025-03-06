---
title: Aspose.Tasks ile MS Project Dosyalarını Şablon Olarak Kaydetme
linktitle: Aspose.Tasks için Şablon Seçeneklerini Kaydet
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'i kullanarak Microsoft Project dosyalarını şablon olarak nasıl kaydedeceğinizi öğrenin. Kolaylaştırılmış proje yönetimi için şablon ayarlarını özelleştirin.
type: docs
weight: 18
url: /tr/net/saving-options/save-template-options/
---
## giriiş
Bu eğitimde Aspose.Tasks for .NET'i kullanarak bir şablonu kaydetme sürecini anlatacağız. Şablonlar, gelecekte kullanılmak üzere proje yapılarını ve ayarlarını standartlaştırmak için kullanışlıdır. Bir projeyi şablon olarak nasıl kaydedeceğimizi ve özelliklerini ayarlayarak göstereceğiz.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1.  Aspose.Tasks for .NET Library: Aspose.Tasks for .NET kütüphanesinin kurulu olduğundan emin olun. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/tasks/net/).
2. C# Programlama Bilgisi: Sağlanan kod parçacıklarını anlamak ve uygulamak için temel C# programlama bilgisi gereklidir.
3. Microsoft Project Dosyası: Şablon olarak kaydetmek istediğiniz bir Microsoft Project dosyasını (MPP formatında) hazır bulundurun.

## Ad Alanlarını İçe Aktar
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## Adım 1: Projeyi Yükle
Öncelikle şablon olarak kaydetmek istediğimiz Microsoft Project dosyasını (.mpp) yüklememiz gerekiyor.
```csharp
// Belgeler dizininin yolu.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## Adım 2: Proje Dosya Bilgilerini Alın
Yüklenen proje dosyası hakkında, formatı gibi bilgileri alın.
```csharp
var projectFileInfo = Project.GetProjectFileInfo(DataDir + "EstimatedMilestoneTasks.mpp");
Console.WriteLine("Project File Format: " + projectFileInfo.ProjectFileFormat);
```
## 3. Adım: Şablonu Kaydetme Seçeneklerini Yapılandırma
Şablon kaydetme seçenekleri oluşturun ve özelliklerini gereksinimlerinize göre yapılandırın. Bu seçenekler, şablondan hangi verilerin kaldırılması gerektiğini özelleştirmenize olanak tanır.
```csharp
var options = new SaveTemplateOptions
{
	// Tüm sabit maliyetleri proje şablonundan kaldırın
	RemoveFixedCosts = true,
	// Tüm gerçek değerleri proje şablonundan kaldırın
	RemoveActualValues = true,
	// Kaynak oranlarını proje şablonundan kaldırın
	RemoveResourceRates = true,
	// Proje şablonundan tüm temel değerleri kaldırın
	RemoveBaselineValues = true
};
```
## Adım 4: Projeyi Şablon Olarak Kaydet
Projeyi belirtilen seçeneklerle şablon olarak kaydedin.
```csharp
project.SaveAsTemplate(DataDir + "SaveProjectDataAsTemplate_out.mpt", options);
```
## Adım 5: Şablon Dosya Bilgilerini Alın
Kaydedilen şablon dosyası hakkında, formatı gibi bilgileri alın.
```csharp
var templateFileInfo = Project.GetProjectFileInfo(DataDir + "SaveProjectDataAsTemplate_out.mpt");
Console.WriteLine("Project File Format: " + templateFileInfo.ProjectFileFormat);
```
Tebrikler! Aspose.Tasks for .NET'i kullanarak bir şablonu başarıyla kaydettiniz ve özelliklerini gerektiği gibi özelleştirdiniz.

## Çözüm
Bu eğitimde, Aspose.Tasks for .NET kullanarak bir Microsoft Project dosyasını şablon olarak nasıl kaydedeceğimizi araştırdık. Şablonlar, proje yapılarını ve ayarlarını standartlaştırma ve gelecekteki proje yaratımlarını kolaylaştırma açısından değerlidir.
## SSS'ler
### S: Şablondan hangi verilerin kaldırılacağını özelleştirebilir miyim?
C: Evet, sabit maliyetler, fiili değerler, kaynak oranları ve temel değerler gibi belirli verileri kaldırmak için Şablonu Kaydetme Seçeneklerini yapılandırabilirsiniz.
### S: Aspose.Tasks for .NET, Microsoft Project'in tüm sürümleriyle uyumlu mudur?
C: Aspose.Tasks for .NET, Microsoft Project'in çeşitli sürümleriyle kapsamlı uyumluluk sağlayarak kusursuz entegrasyon ve işlevsellik sağlar.
### S: Şablonları mevcut projelere uygulayabilir miyim?
C: Evet, şablon dosyasını yükleyerek ve gerektiğinde mevcut projenizle birleştirerek mevcut projelere şablonlar uygulayabilirsiniz.
### S: Aspose.Tasks for .NET platformlar arası geliştirmeyi destekliyor mu?
C: Aspose.Tasks for .NET öncelikle Windows platformlarında çalışan .NET framework uygulamaları için tasarlanmıştır.
### S: Aspose.Tasks for .NET için teknik destek mevcut mu?
 C: Evet, Aspose.Tasks topluluğundan teknik yardım ve rehberlik alabilirsiniz.[forumlar](https://forum.aspose.com/c/tasks/15)veya doğrudan destek ekibiyle iletişime geçin.