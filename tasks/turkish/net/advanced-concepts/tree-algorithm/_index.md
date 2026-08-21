---
date: 2026-03-19
description: Aspose.Tasks'in Ağaç Algoritması'nı kullanarak projeye kaynak eklemeyi
  ve görev süresini hesaplamayı öğrenin ve .NET'te kaynakları görevlere atayın.
linktitle: Add Resource to Project with Tree Algorithm in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks'te Ağaç Algoritmasıyla Projeye Kaynak Ekle
url: /tr/net/advanced-concepts/tree-algorithm/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'te Ağaç Algoritmasıyla Projeye Kaynak Ekleme

## Giriş

Bu öğreticide, Aspose.Tasks for .NET tarafından sağlanan güçlü Ağaç Algoritması'nı kullanarak **projeye nasıl kaynak ekleneceğini** keşfedeceksiniz. Görev hiyerarşisi oluşturmayı, görev süresini hesaplamayı ve görevlere kaynak atamayı adım adım, net bir şekilde göstererek kendi çözümünüze kopyalayabileceğiniz bir şekilde ele alacağız.

## Hızlı Yanıtlar
- **Ağaç Algoritması ne yapar?** Görev hiyerarşisini dolaşarak iş değerlerini verimli bir şekilde toplar.  
- **Bu kılavuz hangi temel işlemi kapsar?** Projeye bir kaynak ekleme ve iş toplamlarını güncelleme.  
- **Lisans gerekiyor mu?** Üretim kullanımı için geçici veya tam bir lisans gereklidir.  
- **Bunu .NET Core ile kullanabilir miyim?** Evet, Aspose.Tasks .NET Framework ve .NET Core'u destekler.  
- **Uygulama ne kadar sürer?** Temel bir proje dosyası için yaklaşık 10‑15 dakika.

## Aspose.Tasks'te “projeye kaynak ekleme” nedir?

Projeye bir kaynak eklemek, bir `Resource` nesnesi oluşturmak, türünü (ör. work) tanımlamak ve `ResourceAssignments` aracılığıyla bir veya daha fazla göreve bağlamak anlamına gelir. Bu, zamanlayıcının çaba, maliyet ve toplam proje süresini hesaplamasını sağlar.

## Neden Kaynak İş Hesaplamaları için Ağaç Algoritmasını Kullanmalıyız?

Ağaç Algoritması, görev ağacını bir kez dolaşarak yaprak görevlerden özet görevlere doğru işi biriktirir. Bu yaklaşım, özellikle derin hiyerarşilere sahip büyük projelerde, her görevi ayrı ayrı yinelemekten çok daha verimlidir ve özet iş değerlerinin alt görevlerle senkronize kalmasını garanti eder.

## Önkoşullar

1. **Visual Studio** – herhangi bir yeni sürüm (2019, 2022 veya daha yeni).  
2. **Aspose.Tasks for .NET** – indirmek için [buraya](https://releases.aspose.com/tasks/net/) tıklayın.  
3. **Temel C# bilgisi** – sınıflar, nesneler ve basit LINQ konusunda rahat olmalısınız.

## Ad Alanlarını İçe Aktarma

C# projenizde Aspose.Tasks işlevselliğiyle çalışmak için gerekli ad alanlarını içe aktarın:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;
```

Şimdi her örneği birden fazla adıma ayıralım:

## Adım 1: Proje Dosyasını Yükle

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

Proje dosyasını `Project` sınıfını kullanarak belleğe yükleyin.

## Adım 2: Görev Hiyerarşisini Tanımla

```csharp
var root = project.RootTask.Children.Add("Project Management");
var summary = root.Children.Add("Manage iteration");
var task = summary.Children.Add("Acquire staff");
```

Üst ve alt görevler ekleyerek görev hiyerarşisini tanımlayın.

## Adım 3: Görev Özelliklerini Ayarla (içinde **görev süresini hesapla**)

```csharp
task.Set(Tsk.Start, new DateTime(1999, 5, 3, 9, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8 * 14, TimeUnitType.Hour));
task.Set(Tsk.Finish, project.Get(Prj.Calendar).GetFinishDateByStartAndWork(task.Get(Tsk.Start), task.Get(Tsk.Duration)));
```

Burada, iş saatlerini bir `Duration` nesnesine dönüştürerek ve ardından bitiş tarihini elde ederek **görev süresini hesaplıyoruz**.

## Adım 4: Kaynak Ekle (**kaynakları görevlere ata**)

```csharp
var resource = project.Resources.Add("Project Manager");
resource.Set(Rsc.Type, ResourceType.Work);
project.ResourceAssignments.Add(task, resource);
```

Bu kod parçacığı **projeye bir kaynak ekler** ve **kaynakları görevlere atar**, böylece zamanlayıcı işi kimin yapacağını bilir.

## Adım 5: Ağaç Algoritmasını Uygula

```csharp
var acc = new WorkAccumulator();
TaskUtils.Apply(summary, acc, 0);
```

`WorkAccumulator` sınıfını başlatın ve hiyerarşi boyunca ortak işi toplamak için Ağaç Algoritmasını uygulayın.

## Adım 6: Görev İşini Güncelle

```csharp
var summaryWork = acc.Work.ToDouble();
summary.Set(Tsk.Work, project.GetWork(summaryWork));
summary.Set(Tsk.RemainingWork, project.GetWork(summaryWork));
```

Toplanan bilgilere dayanarak görevlerin iş değerlerini güncelleyin.

## Yaygın Sorunlar ve İpuçları

- **Takvim ayarları eksik:** Bitiş tarihi yanlış görünüyorsa, `GetFinishDateByStartAndWork` çağrılmadan önce proje takviminin doğru yapılandırıldığından emin olun.  
- **Kaynak türü uyumsuzluğu:** Çaba tabanlı kaynaklar için `Rsc.Type` değerini her zaman `ResourceType.Work` olarak ayarlayın; aksi takdirde iş birikimi sıfır dönebilir.  
- **Pro ipucu:** İş güncellendikten sonra değişiklikleri kalıcı hale getirmek için `project.Save("UpdatedProject.mpp")` çağırın.

## Sonuç

Bu adımları izleyerek artık Aspose.Tasks'in Ağaç Algoritmasıyla **projeye kaynak ekleme**, **görev süresini hesaplama** ve **kaynakları görevlere atama** konularını biliyorsunuz. Bu yöntem, hiyerarşi yönetimini basitleştirir ve özet iş değerlerinin doğru kalmasını minimal kodla sağlar.

## SSS'ler

### S1: Aspose.Tasks for .NET nedir?

A1: Aspose.Tasks for .NET, geliştiricilerin C# kullanarak Microsoft Project dosyalarını programatik olarak manipüle etmelerini sağlayan güçlü bir API'dir.

### S2: Aspose.Tasks for .NET'in ücretsiz deneme sürümünü indirebilir miyim?

A2: Evet, Aspose.Tasks for .NET'in ücretsiz deneme sürümünü [buradan](https://releases.aspose.com/) indirebilirsiniz.

### S3: Aspose.Tasks for .NET dokümantasyonunu nerede bulabilirim?

A3: Aspose.Tasks for .NET dokümantasyonunu [burada](https://reference.aspose.com/tasks/net/) bulabilirsiniz.

### S4: Aspose.Tasks for .NET için destek nasıl alabilirim?

A4: Aspose.Tasks for .NET ile ilgili destek için [Aspose.Tasks forumunu](https://forum.aspose.com/c/tasks/15) ziyaret edebilirsiniz.

### S5: Test amaçlı geçici bir lisans mevcut mu?

A5: Evet, test amaçlı geçici bir lisansı [buradan](https://purchase.aspose.com/temporary-license/) temin edebilirsiniz.

## Sık Sorulan Sorular

**S: Bu yaklaşımı mevcut büyük bir proje dosyasıyla kullanabilir miyim?**  
A: Kesinlikle. Ağaç Algoritması, boyutu ne olursa olsun herhangi bir `Project` örneği üzerinde çalışır.

**S: Algoritma aynı zamanda maliyet değerlerini de güncelliyor mu?**  
A: Örnek iş üzerine odaklanmıştır, ancak benzer bir şekilde `Tsk.Cost` biriktirerek maliyete de genişletebilirsiniz.

**S: Hangi .NET sürümleri destekleniyor?**  
A: Aspose.Tasks .NET Framework 4.5+, .NET Core 3.1+, .NET 5+ ve .NET 6+ sürümlerini destekler.

**S: Bir görev için birden fazla kaynağı nasıl yönetirim?**  
A: Her kaynağı `project.ResourceAssignments.Add(task, resource)` ile ekleyin; biriktirici otomatik olarak işlerini toplayacaktır.

**Son Güncelleme:** 2026-03-19  
**Test Edilen:** Aspose.Tasks 24.11 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}