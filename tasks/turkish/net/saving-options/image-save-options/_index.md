---
title: Aspose.Tasks için Görüntü Kaydetme MS Proje Seçenekleri
linktitle: Aspose.Tasks için Görüntü Kaydetme Seçenekleri
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'i kullanarak MS Project seçeneklerini görüntü olarak nasıl kaydedeceğinizi öğrenin. Sorunsuz entegrasyon için adım adım kılavuzumuzu izleyin.
weight: 11
url: /tr/net/saving-options/image-save-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks için Görüntü Kaydetme MS Proje Seçenekleri


## giriiş
Yazılım geliştirme dünyasında, proje görevlerini verimli bir şekilde ele almak, başarılı proje yönetimi için çok önemlidir. Aspose.Tasks for .NET, Microsoft Project dosyalarıyla çalışan geliştiricilere, .NET uygulamalarında proje görevlerini sorunsuz bir şekilde değiştirmelerine, dönüştürmelerine ve yönetmelerine olanak tanıyan güçlü bir çözüm sunar.
## Önkoşullar
MS Project seçeneklerini görüntü olarak kaydetmek için Aspose.Tasks for .NET'i kullanmaya başlamadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:
### 1. Aspose.Tasks for .NET'i yükleyin
Başlamak için geliştirme ortamınızda Aspose.Tasks for .NET'in kurulu olması gerekir. Kütüphaneyi adresinden indirebilirsiniz.[İnternet sitesi](https://releases.aspose.com/tasks/net/) ve verilen kurulum talimatlarını izleyin.
### 2. Lisans Alın (İsteğe Bağlı)
 Aspose.Tasks for .NET, değerlendirme modunda lisans olmadan kullanılabilse de, tam işlevsellik ve değerlendirme sınırlamalarını kaldırmak için bir lisans alınması önerilir. adresinden lisans alabilirsiniz.[satın alma sayfası](https://purchase.aspose.com/buy) veya birini tercih edin[geçici lisans](https://purchase.aspose.com/temporary-license/) test amaçlı.
### 3. C# ve .NET Geliştirmeye İlişkin Temel Bilgiler
Örnekleri takip etmek ve Aspose.Tasks işlevlerini uygulamalarınıza etkili bir şekilde entegre etmek için C# programlama dili ve .NET çerçevesi hakkında temel bir anlayış gereklidir.
## Ad Alanlarını İçe Aktar
Aspose.Tasks for .NET kullanarak MS Project seçeneklerini görüntü olarak kaydetmeye başlamadan önce, gerekli ad alanlarını C# projemize aktardığımızdan emin olalım:
```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;
using System.Drawing.Imaging;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## 1. Adım: Belge Dizini Yolunu Ayarlayın
Belgeleriniz için belirlenmiş bir dizininiz olduğundan emin olun ve yolu buna göre ayarlayın:
```csharp
String DataDir = "Your Document Directory";
```
## Adım 2: MS Proje Dosyasını Yükleyin
 Yeni bir başlangıç başlat`Project` MS Project dosyasını yükleyerek nesne:
```csharp
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## 3. Adım: Görüntü Kaydetme Seçeneklerini Tanımlayın
 Bir örneğini oluşturun`ImageSaveOptions`ve istediğiniz ayarları belirtin:
```csharp
var options = new ImageSaveOptions(SaveFileFormat.Jpeg)
{
    RenderToSinglePage = false,
    StartDate = project.Get(Prj.StartDate),
    EndDate = project.Get(Prj.FinishDate),
    PageSize = PageSize.Letter
};
```
## 4. Adım: Kaydedilecek Sayfaları Belirleyin
Gerekirse kaydedilecek sayfaları belirtin. Bu örnekte 2. sayfayı ekliyoruz:
```csharp
options.Pages.Add(2);
```
## Adım 5: Görüntüyü Kaydedin
Son olarak, seçilen sayfaları belirtilen seçeneklerle resim olarak kaydedin:
```csharp
project.Save(DataDir + "SaveSelectedPagesImageSaveOptions_page2_out.jpeg", options);
```

## Çözüm
Aspose.Tasks for .NET, MS Project dosyalarıyla çalışma sürecini basitleştirerek geliştiricilerin proje görevlerini zahmetsizce değiştirmesine olanak tanır. Bu eğitimde özetlenen adımları izleyerek MS Project seçeneklerini .NET uygulamalarınızda verimli bir şekilde görüntü olarak kaydedebilirsiniz.
## SSS'ler
### S1: Aspose.Tasks for .NET'i lisans olmadan kullanabilir miyim?
C: Evet, Aspose.Tasks for .NET'i lisans olmadan değerlendirme modunda kullanabilirsiniz. Ancak tam işlevsellik için lisans alınması ve değerlendirme sınırlamalarının kaldırılması önerilir.
### S2: Test için nasıl geçici lisans alabilirim?
 C: Test amaçlı olarak geçici bir lisansı şu adresten alabilirsiniz:[geçici lisans sayfası](https://purchase.aspose.com/temporary-license/).
### S3: Aspose.Tasks for .NET diğer .NET çerçeveleriyle uyumlu mu?
C: Evet, Aspose.Tasks for .NET, .NET Core ve .NET Standard dahil olmak üzere çeşitli .NET çerçeveleriyle uyumludur.
### S4: Görüntü kaydetme seçeneklerini daha da özelleştirebilir miyim?
C: Evet, görüntü kaydetme seçeneklerini sayfa boyutunu, çözünürlüğü veya çıktı formatını ayarlamak gibi özel gereksinimlerinize göre özelleştirebilirsiniz.
### S5: Aspose.Tasks for .NET desteğini nerede bulabilirim?
 C: Aspose.Tasks for .NET için destek ve yardımı şu adreste bulabilirsiniz:[forum](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
