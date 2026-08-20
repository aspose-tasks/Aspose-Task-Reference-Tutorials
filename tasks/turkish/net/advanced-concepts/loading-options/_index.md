---
date: 2026-03-08
description: Aspose.Tasks for .NET kullanarak proje dosyasını nasıl içe aktaracağınızı,
  dosya kodlamasını nasıl belirteceğinizi ve Microsoft Project dosyasını verimli bir
  şekilde nasıl yükleyeceğinizi öğrenin.
linktitle: Options for Loading in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Proje Dosyasını İçe Aktar – Aspose.Tasks'te Yükleme Seçenekleri
url: /tr/net/advanced-concepts/loading-options/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Proje Dosyasını İçe Aktarma – Aspose.Tasks'te Yükleme Seçenekleri

## Giriş

Aspose.Tasks for .NET, Microsoft Project, Primavera ve diğer formatlardan **import project file** verilerini kolayca almanızı sağlar. Şifre korumalı bir dosyayı okumanız, özel bir kodlama ayarlamanız veya ayrıştırma hatalarını yönetmeniz gerektiğinde, kütüphane yükleme seçenekleri aracılığıyla ayrıntılı kontrol sunar. Bu öğreticide en yaygın senaryoları adım adım inceleyecek ve .NET uygulamalarınızda **load Microsoft Project file** nesnelerini güvenle yükleyebileceksiniz.

## Hızlı Yanıtlar
- **Proje dosyasını içe aktarmanın temel yolu nedir?** `Project` yapıcısını bir `LoadOptions` örneğiyle kullanın.  
- **Şifre korumalı dosyaları açabilir miyim?** Evet—`LoadOptions` üzerindeki `Password` özelliğini ayarlayın.  
- **Dosya kodlamasını nasıl belirtirim?** `LoadOptions.Encoding` özelliğine bir `Encoding` nesnesi atayın.  
- **Hata işleme özelleştirilebilir mi?** Kesinlikle—`LoadOptions.ErrorHandler` için bir temsilci (delegate) sağlayın.  
- **Bu seçenekler Primavera dosyalarıyla çalışır mı?** Evet, `LoadOptions` içinde `PrimaveraReadOptions` aracılığıyla.

## Önkoşullar

Başlamadan önce, şunların olduğundan emin olun:

1. **Visual Studio** (veya tercih ettiğiniz herhangi bir .NET IDE).  
2. **Aspose.Tasks for .NET** – bunu [web sitesinden](https://releases.aspose.com/tasks/net/) indirin.  
3. **C#** sözdizimi ve proje yapısına temel bir hakimiyet.

Şimdi kurulum tamam, gerekli ad alanlarını (namespaces) içe aktaralım.

## Ad Alanlarını (Namespaces) İçeri Aktarma

C# projenizde, API sınıflarının kullanılabilir olması için aşağıdaki `using` ifadelerini ekleyin:

```csharp
using Aspose.Tasks;
using System.Text;
using System.Threading;
```

## Yükleme Seçenekleriyle Proje Dosyasını Nasıl İçe Aktarılır

Aşağıda en sık karşılaşılan yükleme senaryolarını kapsayan dört pratik örnek bulabilirsiniz.

### Adım 1: Şifre‑Korumalı Bir Projeyi Yükleme

```csharp
public void WorkWithLoadOptionsAndPassword()
{
    // Initialize FileStream to load the project file
    using (var stream = new FileStream(DataDir + "PasswordProtectedProject.mpp", FileMode.Open))
    {
        // Create LoadOptions instance
        var options = new LoadOptions
        {
            Password = "password" // Set the password
        };

        // Load the project with specified options
        var project = new Project(stream, options);

        // Display project name
        Console.WriteLine(project.Get(Prj.Name));
    }
}
```

### Adım 2: Özel Seçeneklerle Bir Primavera Projesi Yükleme

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptions()
{
    // Create LoadOptions instance
    var loadOptions = new LoadOptions();

    // Configure Primavera reading options
    var primaveraOptions = new PrimaveraReadOptions()
    {
        ProjectUid = 3882, // Set the Project UID
        UndefinedConstraintHandlingBehavior = UndefinedConstraintHandlingBehavior.None,
        PreserveUids = true
    };

    // Set Primavera reading options
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    // Load the Primavera project with specified options
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Display project name
    Console.WriteLine("Project Name: " + project.Get(Prj.Name));

    // Perform further operations with the loaded project
}
```

### Adım 3: XER Dosyası İçe Aktarırken **Dosya Kodlamasını Belirtme**

```csharp
public void SpecifyFileEncoding()
{
    // Create LoadOptions instance
    LoadOptions lo = new LoadOptions();

    // Specify encoding when opening a project from Primavera XER file
    lo.Encoding = Encoding.GetEncoding(1251);

    // Load the project with specified encoding
    var project = new Project("encoding1251.xer", lo);

    // Perform further operations with the loaded project
}
```

### Adım 4: Özel Hata İşleme ile Bir Primavera Projesi Yükleme

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptionsAndErrorHandler()
{
    // Create LoadOptions instance
    var loadOptions = new LoadOptions();

    // Configure Primavera reading options
    var primaveraOptions = new PrimaveraReadOptions
    {
        ProjectUid = 3882 // Set the Project UID
    };

    // Set Primavera reading options
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    // Set custom error handling
    loadOptions.ErrorHandler = CustomDurationHandlerForFile;

    // Load the Primavera project with specified options and error handling
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Perform further operations with the loaded project
}

// Custom error handler method
private static object CustomDurationHandlerForFile(object sender, ParseErrorArgs args)
{
    // Implement custom error handling logic
}
```

Bu adımları izleyerek **import project file** verilerini kesin bir şekilde alabilir, yükleme sürecini ihtiyaçlarınıza göre özelleştirebilir ve uygulamanızı sağlam tutabilirsiniz.

## Yaygın Sorunlar ve İpuçları

- **Yanlış şifre** – `Password` özelliği bir istisna (exception) fırlatır; yüklemeden önce kimlik bilgilerini doğrulayın.  
- **Desteklenmeyen kodlama** – belirttiğiniz kod sayfasının hedef makinede mevcut olduğundan emin olun (`Encoding.GetEncoding(1251)` Kiril alfabesi için çalışır).  
- **Primavera seçenekleri eksik** – görev UID'lerini korumanız gerekiyorsa `PreserveUids = true` olarak ayarlayın; aksi takdirde yinelenen ID'ler ortaya çıkabilir.  
- **Hata işleyicisinin null döndürmesi** – `null` döndürmek, ayrıştırıcıya sorunlu öğeyi atlamasını söyler; gerektiği gibi özelleştirin.

## Sıkça Sorulan Sorular

**S: Aspose.Tasks for .NET tüm Microsoft Project sürümleriyle uyumlu mu?**  
C: Evet, geniş bir Microsoft Project sürüm yelpazesini destekler, bu sayede eski MPP dosyalarından en yeni formatlara kadar **load Microsoft Project file** formatlarını **yükleyebilirsiniz**.

**S: Aspose.Tasks for .NET'i diğer üçüncü‑taraf kütüphanelerle entegre edebilir miyim?**  
C: Kesinlikle. Kütüphane diğer .NET paketleriyle sorunsuz çalışır ve raporlama, UI veya veri‑erişim çerçeveleriyle birleştirmenize olanak tanır.

**S: Aspose.Tasks for .NET belge ve destek kaynakları sunuyor mu?**  
C: Evet, kapsamlı [belgelere](https://reference.aspose.com/tasks/net/) başvurabilir ve [Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15) üzerinden destek alabilirsiniz.

**S: Aspose.Tasks for .NET için lisans seçenekleri mevcut mu?**  
C: Evet, ücretsiz denemeler ve geçici lisanslar dahil olmak üzere çeşitli lisans seçeneklerini [Aspose.Tasks web sitesinde](https://purchase.aspose.com/buy) inceleyebilirsiniz.

**S: Aspose.Tasks for .NET için güncellemeler ve yeni özellikler ne sıklıkla yayınlanıyor?**  
C: Aspose.Tasks, yeni özellikler ekleyen, performansı artıran ve en son Microsoft Project sürümleriyle uyumluluğu koruyan düzenli güncellemeler alır.

---

**Son Güncelleme:** 2026-03-08  
**Test Edilen Versiyon:** Aspose.Tasks 24.11 for .NET  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}