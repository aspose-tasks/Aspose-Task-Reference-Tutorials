---
title: Aspose.Tasks for .NET'te Proje Anahat Kodlarını Yönetin
linktitle: Aspose.Tasks'ta Anahat Kodlarını Yönetme
second_title: Aspose.Tasks .NET API'si
description: Aspose.Tasks for .NET ile MS Project taslak kodlarını yönetmeyi öğrenin. Proje organizasyonunu zahmetsizce basitleştirin.
weight: 10
url: /tr/net/outline-code-page-settings/outline-codes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for .NET'te Proje Anahat Kodlarını Yönetin

## giriiş
Bu eğitimde, Aspose.Tasks for .NET kullanarak Microsoft Project anahat kodlarının nasıl yönetileceğini inceleyeceğiz. Anahat kodları, Microsoft Project'teki kullanıcıların görevleri belirli ölçütlere göre kategorilere ayırmasına ve düzenlemesine olanak tanıyan özel alanlardır. Aspose.Tasks, bu taslak kodların programlı olarak okunması ve işlenmesi sürecini basitleştirir.
## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1.  Aspose.Tasks for .NET Kütüphanesi: Aspose.Tasks for .NET kütüphanesini aşağıdaki adresten indirip yükleyin:[İnternet sitesi](https://releases.aspose.com/tasks/net/).
2. Geliştirme Ortamı: .NET programlama için Visual Studio gibi uygun bir geliştirme ortamı kurun.
3. Temel C# Bilgisi: C# programlama diline aşina olmak, kod örneklerini anlamak açısından faydalı olacaktır.

## Ad Alanlarını İçe Aktarma
Başlamak için gerekli ad alanlarını C# projenize aktarmanız gerekir. Bu, Aspose.Tasks kütüphanesi tarafından sağlanan sınıflara ve yöntemlere erişmenizi sağlar.
1. Visual Studio'yu açın: Visual Studio IDE'nizi başlatın.
2. Yeni Bir Proje Oluşturun: Yeni bir C# projesi başlatın veya Aspose.Tasks'ı kullanmayı düşündüğünüz mevcut bir projeyi açın.
3. Aspose.Tasks Referansını Ekle: Solution Explorer'da projenize sağ tıklayın, "NuGet Paketlerini Yönet"i seçin, "Aspose.Tasks"ı arayın ve en son sürümü yükleyin.
4. Aspose.Tasks Ad Alanını İçe Aktar: C# dosyanızın en üstüne aşağıdaki kullanma yönergesini ekleyin:
```csharp
using Aspose.Tasks;
using System;

```
## 1. Adım: Belge Dizinini Tanımlayın
Öncelikle MS Project dosyanızı içeren dizinin yolunu ayarlayın.
```csharp
String DataDir = "Your Document Directory";
```
 Yer değiştirmek`"Your Document Directory"` proje dosyanızın gerçek yolu ile.
## Adım 2: Proje Dosyasını Yükleyin
 Yeni bir örnek oluştur`Project` MS Project dosyasını yükleyerek nesneyi oluşturun.
```csharp
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
Bu, proje nesnesini belirtilen dosyayla başlatır.
## 3. Adım: Anahat Kodlarını Okuyun
Projedeki tüm görevleri yineleyin ve bunların ana hat kodlarını alın.
```csharp
foreach (var task in project.RootTask.SelectAllChildTasks())
{
    if (task.OutlineCodes.Count <= 0)
    {
        continue;
    }
    Console.WriteLine("Print outline codes of the task: " + task.Get(Tsk.Name));
    foreach (var value in task.OutlineCodes)
    {
        Console.WriteLine("  Field Id: " + value.FieldId);
        Console.WriteLine("  Value Guid: " + value.ValueGuid);
        Console.WriteLine("  Value Id: " + value.ValueId);
    }
}
```
Bu kod parçacığı her görevde döngü yapar, anahat kodları olup olmadığını kontrol eder ve görevle ilişkili her anahat kodu için Alan Kimliği, Değer Kılavuzu ve Değer Kimliği gibi ayrıntıları yazdırır.

## Çözüm
Sonuç olarak Aspose.Tasks for .NET, Microsoft Project anahat kodlarını programlı olarak yönetmek için güçlü yetenekler sağlar. Bu öğreticide özetlenen adımları izleyerek, C# kullanarak MS Project dosyalarınızdaki anahat kodlarını verimli bir şekilde okuyabilir ve değiştirebilirsiniz.
## SSS'ler
### S: Aspose.Tasks'ı kullanarak anahat kodlarını değiştirebilir miyim?
C: Evet, Aspose.Tasks for .NET'i kullanarak anahat kodlarını programlı olarak değiştirebilirsiniz. Görevlerin anahat kodlarına erişmeniz ve değerlerini gerektiği gibi güncellemeniz yeterlidir.
### S: Aspose.Tasks Microsoft Project'in tüm sürümleriyle uyumlu mu?
C: Aspose.Tasks, 2003, 2007, 2010, 2013, 2016 ve 2019 dahil olmak üzere çok çeşitli Microsoft Project sürümlerini destekler.
### S: Aspose.Tasks ticari kullanım için lisans gerektiriyor mu?
C: Evet, Aspose.Tasks'ın ticari kullanımı için geçerli bir lisans gereklidir. Aspose web sitesinden lisans alabilirsiniz.
### S: Satın almadan önce Aspose.Tasks'ı deneyebilir miyim?
C: Evet, özelliklerini ve yeteneklerini değerlendirmek için Aspose.Tasks'ın ücretsiz deneme sürümünü web sitesinden indirebilirsiniz.
### S: Aspose.Tasks için nereden destek alabilirim?
 C: Aspose.Tasks için şu adresteki forumu ziyaret ederek destek alabilirsiniz:[Aspose.Tasks Forumu](https://forum.aspose.com/c/tasks/15).## Kaynak Kodunu Tamamlayın
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
