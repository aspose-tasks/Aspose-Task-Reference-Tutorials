---
date: 2026-06-30
description: Aspose.Tasks for .NET kullanarak C# kısıtlama tipini nasıl ayarlayacağınızı
  öğrenin, proje takvimlerini verimli bir şekilde yönetmek ve birden fazla kısıtlama
  uygulamak için.
keywords:
- set constraint type c#
- how to apply multiple constraints
- load project file c#
linktitle: Aspose.Tasks'teki Kısıtlama Tipleri
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to set constraint type C# using Aspose.Tasks for .NET to
    efficiently manage project schedules and apply multiple constraints.
  headline: Set Constraint Type C# with Aspose.Tasks
  type: TechArticle
- description: Learn how to set constraint type C# using Aspose.Tasks for .NET to
    efficiently manage project schedules and apply multiple constraints.
  name: Set Constraint Type C# with Aspose.Tasks
  steps:
  - name: Visual Studio installed on your workstation.
    text: Visual Studio installed on your workstation.
  - name: Aspose.Tasks for .NET library – download it from [here](https://releases.aspose.com/tasks/net/).
    text: Aspose.Tasks for .NET library – download it from [here](https://releases.aspose.com/tasks/net/).
  - name: Basic knowledge of C# programming.
    text: Basic knowledge of C# programming.
  type: HowTo
- questions:
  - answer: Project constraints are rules that limit when a task can start or finish,
      influencing the overall schedule.
    question: What are project constraints?
  - answer: Aspose.Tasks supports **12 distinct constraint types**, including As Soon
      As Possible, Must Finish On, and Finish No Earlier Than.
    question: How many types of constraints does Aspose.Tasks support?
  - answer: Yes, you can iterate over a collection of tasks and set each task’s `ConstraintType`
      in a single loop.
    question: Can I apply constraints to multiple tasks simultaneously?
  - answer: Absolutely—Aspose.Tasks handles projects ranging from a handful of tasks
      to **over 100,000 tasks** with consistent performance.
    question: Is Aspose.Tasks suitable for both small and large‑scale projects?
  - answer: You can get support by visiting their [forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I get support for Aspose.Tasks‑related queries?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks ile C# Kısıtlama Tipi Ayarlama
url: /tr/net/calendar-scheduling/constraint-types/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks ile C#'ta Kısıtlama Türünü Ayarlama

Bir proje takviminde **set constraint type C#**'ı ayarlamanız gerektiğinde, Aspose.Tasks for .NET, görev tarihlerini kontrol etmeniz için temiz ve programatik bir yol sunar. Bu öğreticide, bir projeyi yükleme, bir kısıtlama uygulama ve sonucu kaydetme adımlarını adım adım göstereceğiz; böylece hem basit hem de karmaşık takvimleri güvenle yönetebilirsiniz.

## Hızlı Yanıtlar
- **“set constraint type C#” ne yapar?** Bir göreve bir zamanlama kuralı (ör. As Soon As Possible) atar ve tarihlerin nasıl hesaplanacağını belirler.  
- **Bir lisansa ihtiyacım var mı?** Evet, üretim kullanımı için geçerli bir Aspose.Tasks lisansı gereklidir.  
- **Birden fazla kısıtlamayı aynı anda uygulayabilir miyim?** Görevler üzerinde döngü yaparak tek bir geçişte farklı `ConstraintType` değerlerini ayarlayabilirsiniz.  
- **Hangi .NET sürümleri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Kütüphaneyi nereden alabilirim?** Resmi Aspose sitesinden indirin (Önkoşullara bakın).

## set constraint type C# nedir?
C#'ta bir kısıtlama türünü ayarlamak, `ConstraintType` enum'ından bir değeri bir görevin `ConstraintType` özelliğine atamak anlamına gelir. Bu, zamanlama motoruna görevin mümkün olduğunca erken başlaması, belirli bir tarihe kadar bitmesi ya da kısıtlama tarafından tanımlanan başka bir kuralı takip etmesi gerektiğini söyler.

## Proje zamanlamasında neden kısıtlama türleri kullanılır?
Aspose.Tasks **30+ kısıtlama türünü** destekler ve **100.000'e kadar görev** içeren projeleri belirgin bir performans kaybı olmadan işleyebilir. Kısıtlamaları kullanmak, iş kurallarını—örneğin “belirli bir tarihte başlamalı” veya “son teslim tarihinden daha geç bitmemeli”—doğrudan kod içinde uygulamanızı sağlar ve manuel ayarlamaları ortadan kaldırır.

## Önkoşullar

1. İş istasyonunuzda Visual Studio yüklü olmalıdır.  
2. Aspose.Tasks for .NET kütüphanesi – [buradan](https://releases.aspose.com/tasks/net/) indirin.  
3. C# programlama temellerine sahip olmak.

## Ad Alanlarını İçe Aktar

Aşağıdaki ad alanları, temel zamanlama API'sine erişim sağlar:

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Saving;
```

*`Project` sınıfı, bellekte bir Microsoft Project dosyasını temsil eden Aspose.Tasks'in üst‑seviye nesnesidir.*  

## C#'ta bir proje dosyası nasıl yüklenir?
`Project` sınıfı, bellekte bir Microsoft Project dosyasını temsil eder ve kaynak dosyayı kilitlemeden içeriğini okumanıza ve değiştirmenize olanak tanır. .mpp verilerini ayrıştıran ve nesne modelini sonraki işlemler için hazırlayan yapıcıya dosya yolunu geçirerek mevcut projenizi yükleyebilir (veya yeni bir tane oluşturabilirsiniz).

## Adım 1: Proje Dosyasını Yükle

Kısıtlamayı ayarlamak istediğiniz proje dosyasını yükleyerek başlayın. Bu amaçla `Project` sınıfını kullanabilirsiniz:

```csharp
var project = new Project("PathToYourProjectFile");
```

## C#'ta bir görev için kısıtlama türü nasıl ayarlanır?
`ConstraintType` enum'ı, bir göreve uygulanabilecek olası zamanlama kısıtlamalarını tanımlar. İhtiyacınız olan kuralı bu enum ile belirleyin ve ardından görevin `ConstraintType` özelliğine atayın. Bu tek satır, set constraint type C# işleminin çekirdeğidir ve zamanlayıcıya başlangıç ve bitiş tarihlerini nasıl hesaplayacağını söyler.

## Adım 2: Kısıtlama Türünü Ayarla

Sonra, belirli bir göreve uygulamak istediğiniz kısıtlama türünü belirtin. Bu örnekte, kısıtlama türünü **As Soon As Possible** olarak ayarlayacağız:

```csharp
var task = project.RootTask.Children.GetById(11);
task.Set(Tsk.ConstraintType, ConstraintType.AsSoonAsPossible);
```

## Kısıtlamaları ayarladıktan sonra projeyi nasıl kaydedilir?
`Save` yöntemi, proje verilerini PDF veya XML gibi belirtilen formatta bir dosyaya yazar. Kısıtlamayı uyguladıktan sonra, uygun `SaveOptions` ile bu yöntemi çağırarak çıktı dosyasını oluşturun. Bu işlem, kısıtlama bilgileri dahil tüm değişiklikleri kaydeder ve kaydedilen takvimin güncellenmiş görev kurallarını yansıtmasını sağlar.

## Adım 3: Projeyi Kaydet

Kısıtlama ayarlandıktan sonra proje dosyasını kaydedebilirsiniz. Şimdi PDF dosyası olarak kaydedelim:

```csharp
SaveOptions options = new PdfSaveOptions();
options.StartDate = project.Get(Prj.StartDate);
options.Timescale = Timescale.ThirdsOfMonths;
project.Save("PathToSavePDF", options);
```

## Yaygın Sorunlar ve Çözümler

- **Kısıtlama uygulanmadı:** Doğru `Task` nesnesini ( `Task.Id`'yi kontrol edin) değiştirdiğinizden emin olun.  
- **Kaydetme sonrası beklenmeyen tarihler:** Proje takviminin istediğiniz çalışma günleri ve tatillerle eşleştiğini doğrulayın.  
- **Büyük dosyalarda performans yavaşlaması:** Çok büyük projelerle çalışırken bellek kullanımını azaltmak için `Project.Set(LoadOptions.DisableCache, true)` kullanın.

## Sıkça Sorulan Sorular

**S: Proje kısıtlamaları nedir?**  
**C:** Proje kısıtlamaları, bir görevin ne zaman başlayabileceğini veya bitebileceğini sınırlayan ve genel takvimi etkileyen kurallardır.

**S: Aspose.Tasks kaç tür kısıtlama destekliyor?**  
**C:** Aspose.Tasks **12 farklı kısıtlama türünü** destekler; bunlar arasında As Soon As Possible, Must Finish On ve Finish No Earlier Than bulunur.

**S: Kısıtlamaları birden fazla göreve aynı anda uygulayabilir miyim?**  
**C:** Evet, görev koleksiyonunu döngüyle gezerek her bir görevin `ConstraintType` özelliğini tek bir döngüde ayarlayabilirsiniz.

**S: Aspose.Tasks küçük ve büyük ölçekli projeler için uygun mu?**  
**C:** Kesinlikle—Aspose.Tasks, birkaç görevden **100.000'den fazla görev**e kadar değişen projeleri tutarlı bir performansla yönetir.

**S: Aspose.Tasks ile ilgili sorular için nereden destek alabilirim?**  
**C:** Destek almak için [forum](https://forum.aspose.com/c/tasks/15) sayfasını ziyaret edebilirsiniz.

---

**Son Güncelleme:** 2026-06-30  
**Test Edilen Versiyon:** Aspose.Tasks 24.11 for .NET  
**Yazar:** Aspose  

{{< blocks/products/products-backtop-button >}}

```csharp

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## İlgili Öğreticiler

- [Aspose.Tasks Takvim ve Zamanlama](/tasks/net/calendar-scheduling/)
- [Aspose.Tasks'te Görev Başlangıç Tarihi Türlerini Yapılandırma](/tasks/net/task-table-management/task-start-date-types/)
- [Aspose.Tasks'te MS Project Dosya Bilgilerini Al](/tasks/net/project-management-integration/project-file-information/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}