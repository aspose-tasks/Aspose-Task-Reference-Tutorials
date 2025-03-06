---
title: Aspose.Tasks ile MS Project Sayfası Ayarlarını Yapılandırma
linktitle: Aspose.Tasks'ta Sayfa Ayarlarını Yapılandırma
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'i kullanarak MS Project sayfa ayarlarını nasıl yapılandıracağınızı öğrenin. Yönü, boyutu ve daha fazlasını basit adımlarla özelleştirin.
weight: 20
url: /tr/net/outline-code-page-settings/page-settings/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks ile MS Project Sayfası Ayarlarını Yapılandırma

## giriiş
Bu eğitimde, Aspose.Tasks for .NET'i kullanarak Microsoft Project sayfa ayarlarını yapılandırma sürecini anlatacağız. Aspose.Tasks, geliştiricilerin Microsoft Project dosyalarını programlı olarak değiştirmesine olanak tanıyan güçlü bir API'dir.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1.  Aspose.Tasks for .NET: Aspose.Tasks for .NET'i yüklediğinizden emin olun. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/tasks/net/).
2. Geliştirme Ortamı: Visual Studio veya .NET geliştirme için tercih edilen herhangi bir IDE ile ayarlanmış bir geliştirme ortamına sahip olun.

## Ad Alanlarını İçe Aktarma
Başlamak için projenize gerekli ad alanlarını içe aktarmanız gerekir. Bu ad alanları, MS Project dosyalarını yönetmek için gereken Aspose.Tasks sınıflarına ve yöntemlerine erişim sağlar.
```csharp
using Aspose.Tasks;
using System.Linq;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## Adım 1: Proje Dosyasını Yükleyin
Öncelikle sayfa ayarlarını yapılandırmak istediğiniz MS Project dosyasını yüklemeniz gerekmektedir.
```csharp
// Belgeler dizininin yolu.
string dataDir = "Your Document Directory";
var project = new Project(dataDir + "Project2.mpp");
```
## 2. Adım: Sayfa Ayarlarına Erişim
Daha sonra proje dosyasının sayfa ayarlarına erişeceksiniz.
```csharp
// Ayarları alın
var settings = project.DefaultView.PageInfo.PageSettings;
```
## 3. Adım: Sayfa Ayarlarını Yapılandırın
Şimdi sayfa ayarlarının çeşitli özelliklerini gereksinimlerinize göre yapılandıralım.
```csharp
// Sayfa yönünü dikey olarak ayarla
settings.IsPortrait = true;
// Yazdırılacak genişlikteki sayfa sayısını ayarlayın
settings.PagesInWidth = 5;
// Yazdırılacak sayfaların yüksekliğini ayarlayın
settings.PagesInHeight = 7;
// Yazdırmayı ayarlamak için normal boyutun yüzdesini ayarlayın.
settings.PercentOfNormalSize = 200;
// Kağıt boyutunu ayarla
settings.PaperSize = PrinterPaperSize.PaperB4;
// Yazdırma için ilk sayfa numarasını ayarlayın
settings.FirstPageNumber = 3;
```
## Adım 4: Proje Dosyasını Kaydedin
Son olarak proje dosyasını güncellenen sayfa ayarlarıyla kaydedin.
```csharp
SimpleSaveOptions options = new MPPSaveOptions
{
    WriteViewData = true
};
project.Save(dataDir + "TestCanWritePageSettings.mpp", options);
```

## Çözüm
Bu eğitimde Aspose.Tasks for .NET'i kullanarak Microsoft Project sayfa ayarlarını nasıl yapılandıracağımızı öğrendik. Bu adımları izleyerek sayfa yönünü, boyutunu ve diğer yazdırma seçeneklerini gereksinimlerinize göre kolayca özelleştirebilirsiniz.

## SSS'ler
### S: Birden fazla MS Project dosyası için sayfa ayarlarını aynı anda yapılandırabilir miyim?
C: Evet, birden fazla proje dosyası arasında geçiş yapabilir ve her birine aynı sayfa ayarlarını uygulayabilirsiniz.
### S: Sayfa ayarlarını varsayılana döndürmek mümkün mü?
C: Kesinlikle, yapılandırma adımlarını atlayabilir veya ayarları varsayılan değerlerine sıfırlayabilirsiniz.
### S: Desteklenen kağıt boyutlarında herhangi bir sınırlama var mı?
C: Aspose.Tasks, standart ve özel boyutlar da dahil olmak üzere çok çeşitli kağıt boyutlarını destekler.
### S: Sayfa ayarları yapılandırma sürecini otomatikleştirebilir miyim?
C: Elbette, sayfa ayarları yapılandırmasını otomatikleştirmek için bu işlevselliği uygulamanızın iş akışına entegre edebilirsiniz.
### S: Aspose.Tasks .mpp'nin yanı sıra farklı dosya formatlarını da destekliyor mu?
C: Evet, Aspose.Tasks diğerlerinin yanı sıra XML, MPT ve HTML gibi çeşitli dosya formatlarını destekler.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
