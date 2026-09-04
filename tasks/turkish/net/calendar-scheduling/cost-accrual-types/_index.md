---
date: 2026-07-05
description: Aspose.Tasks for .NET kullanarak proje bütçesini nasıl izleyebileceğinizi
  ve proje maliyetlerini nasıl yöneteceğinizi öğrenin. Doğru maliyet takibi için cost
  accrual types tanımlayın.
keywords:
- track project budget
- manage project costs
- how to set accrual
- define project cost tracking
- access resource by id
linktitle: Aspose.Tasks'te Cost Accrual Types
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to track project budget and manage project costs using Aspose.Tasks
    for .NET. Define cost accrual types for accurate cost tracking.
  headline: Track Project Budget with Cost Accrual Types in Aspose.Tasks
  type: TechArticle
- description: Learn how to track project budget and manage project costs using Aspose.Tasks
    for .NET. Define cost accrual types for accurate cost tracking.
  name: Track Project Budget with Cost Accrual Types in Aspose.Tasks
  steps:
  - name: Import Namespaces
    text: 'Let''s start by importing the necessary namespaces to access Aspose.Tasks
      functionality in our .NET project: Now that we have the namespaces ready, we
      can move on to loading a project file.'
  - name: Load Project File
    text: The `Project` class represents a Microsoft Project file and provides access
      to its tasks, resources, and other data. First, we need to load the project
      file into our application. We create a new `Project` object and initialize it
      with the path to our project file.
  - name: Access Resource
    text: 'The `Resources` collection holds all resources defined in the project.
      The `GetById` method retrieves a resource by its unique identifier. Next, we
      access the resource to which we want to apply the cost accrual type. We use
      the `GetById` method of the `Resources` collection and pass the resource ID '
  - name: Set Cost Accrual Type
    text: The `Set` method assigns a value to a resource field. Here, we set the cost
      accrual type for the resource. In this example, we are setting it to `CostAccrualType.End`,
      which means costs will not be accrued until remaining work is zero. Choosing
      `End` is ideal when you want to **track project budget*
  - name: Continue Working with the Project
    text: After setting the cost accrual type, you can continue working with the project
      as needed, performing additional operations or calculations such as generating
      cost reports, updating assignments, or exporting the file.
  type: HowTo
- questions:
  - answer: Yes, iterate through `project.Resources` and assign the desired `CostAccrualType`
      to each resource within a `foreach` loop.
    question: Can I change the cost accrual type for multiple resources simultaneously?
  - answer: Aspose.Tasks provides `Start`, `Prorated`, and `Duration`—each aligns
      with a different billing strategy.
    question: What are the other available cost accrual types besides `End`?
  - answer: Retrieve the value via `resource.Get(TskResource.CostAccrualType)`; it
      returns the enum representing the current setting.
    question: How can I determine the current cost accrual type for a specific resource?
  - answer: Absolutely. Both tasks and resources expose a `CostAccrualType` property,
      allowing independent configuration per entity.
    question: Is it possible to apply different cost accrual types to different tasks
      in the same project?
  - answer: No, the library currently supports the four built‑in types only; custom
      logic must be implemented externally if required.
    question: Does Aspose.Tasks support custom cost accrual types?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks'te Cost Accrual Types ile Proje Bütçesini İzleyin
url: /tr/net/calendar-scheduling/cost-accrual-types/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'te Maliyet Tahakkuk Türleriyle Proje Bütçesini Takip Etme

## Giriş

Doğru bir şekilde **proje bütçesini izlemek**, başarılı proje teslimatının temelidir. Maliyet bilgileri doğru zamanlarda yakalandığında, aşım tahminleri yapabilir, kaynakları ayarlayabilir ve paydaşları bilgilendirebilirsiniz. Aspose.Tasks for .NET, geliştiricilere maliyet tahakkuku üzerinde ayrıntılı kontrol sağlar ve maliyetin *ne zaman* kaydedileceğine karar vermenize olanak tanır—işin başlangıcında, sürekli olarak veya yalnızca iş tamamlandığında. Bu öğretici, kavramları adım adım anlatır, bir tahakkuk türünün nasıl ayarlanacağını gösterir ve güvenilir bütçe takibi için en iyi uygulamaları sergiler.

## Hızlı Yanıtlar
- **Maliyet tahakkuk türlerinin temel amacı nedir?** Bir görevin yaşam döngüsünde maliyetin ne zaman tanındığını belirler ve kesin bütçe takibini mümkün kılar.  
- **Hangi enum değeri maliyeti iş tamamlanana kadar geciktirir?** `CostAccrualType.End`.  
- **Kodu çalıştırmak için bir lisansa ihtiyacım var mı?** Evet, üretim kullanımında geçerli bir Aspose.Tasks lisansı gereklidir.  
- **Birçok kaynak için tahakkuk türlerini aynı anda değiştirebilir miyim?** Evet—`Resources` koleksiyonunu döngüyle gezerek istenen türü atayabilirsiniz.  
- **.NET sürümleri hangileri destekleniyor?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Maliyet Tahakkuk Türü Nedir?
Bir **maliyet tahakkuk türü**, Aspose.Tasks'e bir kaynağın maliyetini proje bütçesine ne zaman uygulayacağını söyler. `CostAccrualType` enum'ı tarafından temsil edilir ve kaynak başına ya da görev başına ayarlanabilir. Doğru türün seçilmesi, maliyet verilerinin kuruluşunuzun faturalama politikalarıyla uyumlu olmasını sağlar; ister maliyetlerin iş başlangıcında, süre boyunca orantılı olarak ya da yalnızca tamamlandıktan sonra kaydedilmesi gerekse.

## Neden Maliyet Tahakkuk Türlerini Kullanarak Proje Bütçesini Takip Etmeliyiz?
Aspose.Tasks, **dört** tahakkuk seçeneğini destekler—`Start`, `Prorated`, `Duration` ve `End`—ve tipik proje muhasebesi senaryolarının tam yelpazesini kapsar. Uygun seçeneği seçmek, maliyet tanımını sözleşmeye dayalı faturalama döngüleriyle hizalamanızı, finansal raporlardaki sapmaları azaltmanızı ve ERP sistemleriyle sorunsuz entegrasyon sağlayan maliyet beyanları oluşturmanızı sağlar; ayrıca büyük projelerde bellek kullanımını düşük tutar.

## Ön Koşullar

Başlamadan önce, aşağıdaki ön koşullara sahip olduğunuzdan emin olun:

### 1. Aspose.Tasks for .NET'i Kurun
Başlamak için, geliştirme ortamınızda Aspose.Tasks for .NET'in kurulu olması gerekir. Kütüphaneyi [indirme sayfasından](https://releases.aspose.com/tasks/net/) indirebilir ve sağlanan kurulum talimatlarını izleyebilirsiniz.

### 2. .NET Framework'e Hakim Olmak
Bu öğreticideki örnekleri takip edebilmek için .NET framework'ü ve C# programlama dili hakkında temel bilgiye sahip olmanız gerekir.

## Bir Kaynak İçin Maliyet Tahakkuk Türü Nasıl Ayarlanır?
Projeyi yükleyin, hedef kaynağı bulun ve istenen `CostAccrualType` değerini atayın. Aşağıdaki iki satırlık desen standart yaklaşımdır: bir `Project` örneği oluşturun, kaynağı kimliğiyle alın ve ardından `CostAccrualType`'ı ayarlayın. Bu özlü sıralama, kaynağın eklendiği andan itibaren **proje bütçesini izlemek** için doğruluk sağlar.

### Adım 1: Ad Alanlarını İçe Aktarın
Aspose.Tasks işlevselliğine .NET projemizde erişmek için gerekli ad alanlarını içe aktararak başlayalım:

```csharp

```

Artık ad alanları hazır olduğuna göre, bir proje dosyasını yüklemeye geçebiliriz.

### Adım 2: Proje Dosyasını Yükle
`Project` sınıfı, bir Microsoft Project dosyasını temsil eder ve görevlerine, kaynaklarına ve diğer verilerine erişim sağlar.

```csharp
var project = new Project("Project2.mpp");
```

İlk olarak, proje dosyasını uygulamamız içine yüklememiz gerekir. Yeni bir `Project` nesnesi oluşturur ve onu proje dosyamızın yolu ile başlatırız.

### Adım 3: Kaynağa Eriş
`Resources` koleksiyonu, projede tanımlanan tüm kaynakları tutar. `GetById` yöntemi, benzersiz kimliğiyle bir kaynağı alır.

```csharp
var resource = project.Resources.GetById(1);
```

Sonra, maliyet tahakkuk türünü uygulamak istediğimiz kaynağa erişiriz. `Resources` koleksiyonunun `GetById` metodunu kullanır ve kaynak kimliğini argüman olarak geçiririz. Bu, maliyet güncellemelerini otomatikleştirirken sıkça ihtiyaç duyulan **kimliğe göre kaynağa eriş**i gösterir.

### Adım 4: Maliyet Tahakkuk Türünü Ayarla
`Set` yöntemi, bir kaynak alanına değer atar.

```csharp
resource.Set(Rsc.AccrueAt, CostAccrualType.End);
```

Burada, kaynak için maliyet tahakkuk türünü ayarlıyoruz. Bu örnekte, `CostAccrualType.End` olarak ayarlıyoruz; bu, kalan iş sıfır olana kadar maliyetlerin tahakkuk etmeyeceği anlamına gelir. `End` seçmek, bir görevin tamamen tamamlanmasından sonra **proje bütçesini izlemek** istediğinizde idealdir.

### Adım 5: Proje ile Çalışmaya Devam Et
Maliyet tahakkuk türünü ayarladıktan sonra, proje ile ihtiyaç duyduğunuz şekilde çalışmaya devam edebilir, maliyet raporları oluşturma, atamaları güncelleme veya dosyayı dışa aktarma gibi ek işlemler veya hesaplamalar yapabilirsiniz.

## Yaygın Tuzaklar ve Uzman İpuçları
- **Pro ipucu:** Tahakkuk türlerini değiştirdikten sonra değişiklikleri kalıcı kılmak için her zaman `project.Save` çağırın.  
- **Tüzak:** İşe hiç başlamayan bir kaynakta `CostAccrualType.Start` ayarlamak bütçe raporlarını şişirecektir—önce görev takvimlerini doğrulayın.  
- **Pro ipucu:** Birçok kaynağı toplu olarak güncellemeniz gerektiğinde `project.Resources.ToList()` kullanın; bu, koleksiyon aramalarını tekrarlamaktan kaçınır ve büyük projelerde performansı artırır.

## Sıkça Sorulan Sorular

**Q: Birden fazla kaynak için maliyet tahakkuk türünü aynı anda değiştirebilir miyim?**  
A: Evet, `project.Resources` koleksiyonunu döngüyle gezerek her bir kaynağa istenen `CostAccrualType` değerini `foreach` döngüsü içinde atayabilirsiniz.

**Q: `End` dışında başka hangi maliyet tahakkuk türleri mevcuttur?**  
A: Aspose.Tasks `Start`, `Prorated` ve `Duration` sağlar—her biri farklı bir faturalama stratejisine uyar.

**Q: Belirli bir kaynak için mevcut maliyet tahakkuk türünü nasıl belirleyebilirim?**  
A: `resource.Get(TskResource.CostAccrualType)` yöntemiyle değeri alın; bu, mevcut ayarı temsil eden enum'ı döndürür.

**Q: Aynı projede farklı görevlere farklı maliyet tahakkuk türleri uygulamak mümkün mi?**  
A: Kesinlikle. Hem görevler hem de kaynaklar bir `CostAccrualType` özelliği sunar ve her varlık için bağımsız yapılandırmaya izin verir.

**Q: Aspose.Tasks özel maliyet tahakkuk türlerini destekliyor mu?**  
A: Hayır, kütüphane şu anda yalnızca dört yerleşik türü desteklemektedir; gerektiğinde özel mantık harici olarak uygulanmalıdır.

**Last Updated:** 2026-07-05  
**Tested With:** Aspose.Tasks 24.8 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## İlgili Öğreticiler

- [Aspose.Tasks Takvim ve Zamanlama](/tasks/net/calendar-scheduling/)
- [Aspose.Tasks for .NET ile MS Project Ücretlerini Yönetme](/tasks/net/rate-recurring-tasks/handling-rates/)
- [Aspose.Tasks ile MS Project Kaynaklarını Kolayca Yönetme](/tasks/net/resource-risk-analysis/managing-resources/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}