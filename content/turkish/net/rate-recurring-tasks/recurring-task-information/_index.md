---
title: Aspose.Tasks'ta Tekrarlanan Görev Bilgilerini Çıkarma
linktitle: Aspose.Tasks'ta Tekrarlanan Görev Bilgilerini Çıkarma
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET'i kullanarak MS Project dosyalarından yinelenen görev bilgilerini nasıl çıkaracağınızı öğrenin. .NET geliştiricileri için kolay entegrasyon.
type: docs
weight: 13
url: /tr/net/rate-recurring-tasks/recurring-task-information/
---
## giriiş
Aspose.Tasks for .NET, geliştiricilerin .NET uygulamalarında Microsoft Project dosyalarıyla çalışmasına olanak tanıyan güçlü bir kitaplıktır. Bu eğitimde Aspose.Tasks'ı kullanarak MS Project dosyalarından yinelenen görev bilgilerinin nasıl çıkarılacağını inceleyeceğiz.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1. C# programlama dilinin temel anlayışı.
2. Sisteminizde Visual Studio yüklü.
3.  Aspose.Tasks for .NET kütüphanesi kuruldu. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/tasks/net/).
## Ad Alanlarını İçe Aktar
Başlamak için gerekli ad alanlarını C# kodunuza aktarın:
```csharp
    using Aspose.Tasks;
    using System;
    
```
Şimdi örneği birden çok adıma ayıralım:
## 1. Adım: Proje dosyası yolunu ayarlayın
```csharp
String DataDir = "Your Document Directory";
```
 Yer değiştirmek`"Your Document Directory"` MS Project dosyanızın yolu ile.
## Adım 2: MS Project dosyasını yükleyin
```csharp
var project = new Project(DataDir + "TestRecurringTask2016.mpp");
```
 Bu satır yeni bir başlangıç başlatır`Project` Yolun belirttiği MS Project dosyasını yükleyerek nesneyi oluşturun.
## 3. Adım: Görevlerle ilgili yinelenen bilgileri okuyun
```csharp
foreach (var task in project.RootTask.SelectAllChildTasks())
{
    var info = task.RecurringInfo;
    if (info == null)
    {
        continue;
    }
    // Tekrarlanan görev bilgilerine erişin ve görüntüleyin
    Console.WriteLine("Start Date: " + info.StartDate);
    Console.WriteLine("Duration: " + info.Duration);
    Console.WriteLine("End Date: " + info.EndDate);
    // Gerektiğinde diğer yinelenen görev bilgilerini görüntülemeye devam edin
}
```
Bu döngü, projedeki tüm görevleri yineler ve her görevin kendisiyle ilişkili yinelenen bilgilere sahip olup olmadığını kontrol eder. Bunu yaparsa, yinelenen görevin başlangıç tarihi, süre, bitiş tarihi vb. gibi çeşitli özelliklerini alır ve görüntüler.
## Çözüm
Bu eğitimde Aspose.Tasks for .NET'i kullanarak MS Project dosyalarından yinelenen görev bilgilerinin nasıl çıkarılacağını öğrendik. Bu bilgiyle, yinelenen görevlerle daha verimli çalışmak için artık bu işlevselliği .NET uygulamalarınıza entegre edebilirsiniz.
## SSS'ler
### S: Aspose.Tasks for .NET'i kullanarak yinelenen görev bilgilerini değiştirebilir miyim?
C: Evet, sağlanan API'leri kullanarak yinelenen görev bilgilerini programlı olarak değiştirebilirsiniz.
### S: Aspose.Tasks, MS Project'in yanı sıra diğer proje dosya formatlarını da destekliyor mu?
C: Evet, Aspose.Tasks MPP, XML ve CSV gibi çeşitli proje dosyası formatlarını destekler.
### S: Aspose.Tasks for .NET'in ücretsiz deneme sürümü mevcut mu?
 C: Evet, ücretsiz deneme sürümünü şuradan indirebilirsiniz:[Burada](https://releases.aspose.com/).
### S: Aspose.Tasks for .NET belgelerini nerede bulabilirim?
 C: Belgeleri bulabilirsiniz[Burada](https://reference.aspose.com/tasks/net/).
### S: Aspose.Tasks for .NET için nasıl teknik destek alabilirim?
 C: Aspose.Tasks forumundan teknik destek alabilirsiniz.[Burada](https://forum.aspose.com/c/tasks/15).