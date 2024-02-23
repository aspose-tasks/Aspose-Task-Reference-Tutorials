---
title: Aspose.Tasks'ta MS Project Dosyalarını Çeşitli Formatlarda Kaydetme
linktitle: Aspose.Tasks'ta Dosyaları Çeşitli Formatlarda Kaydetme
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'i kullanarak MS Project dosyalarını çeşitli formatlarda nasıl kaydedeceğinizi öğrenin. Etkin proje yönetimi için kolay adımlar.
type: docs
weight: 17
url: /tr/net/rate-recurring-tasks/save-file-formats/
---
## giriiş
Bu eğitimde, Microsoft Project dosyalarını Aspose.Tasks for .NET kullanarak çeşitli formatlarda nasıl kaydedeceğimizi inceleyeceğiz. Aspose.Tasks, geliştiricilerin proje dosyalarını programlı olarak değiştirmesine ve yönetmesine olanak tanıyan güçlü bir API'dir.
## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1.  Aspose.Tasks for .NET: Aspose.Tasks for .NET'i şu adresten indirip yükleyin:[Burada](https://releases.aspose.com/tasks/net/).
2. Geliştirme Ortamı: Visual Studio gibi bir .NET geliştirme ortamı kurun.
3. Temel C# Anlayışı: C# programlama diline aşina olmak faydalı olacaktır.

## Ad Alanlarını İçe Aktar
C# dosyanızın başında gerekli ad alanlarını içe aktardığınızdan emin olun:
```csharp

using Aspose.Tasks.Saving;
```
## Adım 1: Proje Nesnesi Oluşturun
Öncelikle bir Project nesnesi oluşturun ve Microsoft Project dosyanızı yükleyin.
```csharp
// Belgeler dizininin yolu.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject1.mpp");
```
## Adım 2: Projeyi CSV Formatında Kaydetme
Şimdi projemizi CSV formatında kaydedelim. 
```csharp
project.Save(DataDir + "SaveProjectAsCSV_out.csv", SaveFileFormat.Csv);
```
## 3. Adım: Diğer Formatları Keşfedin
 Aspose.Tasks, proje dosyalarını kaydetmek için XML, PDF, XLSX ve daha fazlası gibi çeşitli formatları destekler. Bu formatları basitçe değiştirerek keşfedebilirsiniz.`SaveFileFormat` parametreler`Save` yöntem.
```csharp
project.Save(DataDir + "SaveProjectAsXML_out.xml", SaveFileFormat.XML);
project.Save(DataDir + "SaveProjectAsPDF_out.pdf", SaveFileFormat.PDF);
project.Save(DataDir + "SaveProjectAsXLSX_out.xlsx", SaveFileFormat.XLSX);
```
Bu adımları takip ederek Aspose.Tasks for .NET'i kullanarak Microsoft Project dosyalarını çeşitli formatlarda kolayca kaydedebilirsiniz.

## Çözüm
Bu eğitimde Aspose.Tasks for .NET kullanarak MS Project dosyalarını farklı formatlarda nasıl kaydedeceğimizi öğrendik. Aspose.Tasks, proje dosyalarını programlı olarak değiştirme sürecini basitleştirerek geliştiricilere esneklik ve verimlilik sunar.
## SSS'ler
### S: Aspose.Tasks Microsoft Project'in tüm sürümleriyle uyumlu mu?
C: Aspose.Tasks, Microsoft Project 2003 XML, Microsoft Project 2007 MPP ve Microsoft Project 2010 MPP formatlarını destekler.
### S: Satın almadan önce Aspose.Tasks'ı deneyebilir miyim?
 C: Evet, ücretsiz deneme sürümünü şuradan indirebilirsiniz:[Burada](https://releases.aspose.com/).
### S: Aspose.Tasks için nasıl destek alabilirim?
 C: Aspose.Tasks topluluk forumundan destek alabilirsiniz.[Burada](https://forum.aspose.com/c/tasks/15).
### S: Aspose.Tasks için geçici lisanslar mevcut mu?
 C: Evet, değerlendirme amaçlı olarak geçici lisanslar mevcuttur. Bir tane alabilirsin[Burada](https://purchase.aspose.com/temporary-license/).
### S: Aspose.Tasks'ın fiyatı nedir?
 C: Fiyatlandırma bilgilerini Aspose.Tasks satın alma sayfasında bulabilirsiniz[Burada](https://purchase.aspose.com/buy).