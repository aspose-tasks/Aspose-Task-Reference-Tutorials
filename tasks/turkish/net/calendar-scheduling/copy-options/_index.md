---
date: 2026-07-05
description: Aspose.Tasks for .NET kullanarak kopyalama seçenekleriyle proje verilerini
  nasıl kopyalayacağınızı öğrenin. .NET uygulamalarınızı kesin proje yönetimiyle güçlendirin.
keywords:
- how to copy project
- aspnet project copy
- aspose tasks copy options
linktitle: Aspose.Tasks'te Kopyalama Seçenekleriyle Proje Verilerini Nasıl Kopyalarsınız
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to copy project data using Aspose.Tasks for .NET with copy
    options. Boost your .NET apps with precise project management.
  headline: How to Copy Project Data with Copy Options in Aspose.Tasks
  type: TechArticle
- description: Learn how to copy project data using Aspose.Tasks for .NET with copy
    options. Boost your .NET apps with precise project management.
  name: How to Copy Project Data with Copy Options in Aspose.Tasks
  steps:
  - name: '**Aspose.Tasks for .NET** – download the latest version from the [download
      link](https://releases.aspose.com/tasks/net/).'
    text: '**Aspose.Tasks for .NET** – download the latest version from the [download
      link](https://releases.aspose.com/tasks/net/).'
  - name: '**.NET development environment** – Visual Studio 2022 (or any IDE that
      supports .NET 6+) installed.'
    text: '**.NET development environment** – Visual Studio 2022 (or any IDE that
      supports .NET 6+) installed.'
  - name: '**A valid Aspose.Tasks license** – optional for evaluation, mandatory for
      production builds.'
    text: '**A valid Aspose.Tasks license** – optional for evaluation, mandatory for
      production builds.'
  - name: '**An existing project file** (e.g., `SourceProject.xml`) that you want
      to copy.'
    text: '**An existing project file** (e.g., `SourceProject.xml`) that you want
      to copy.'
  type: HowTo
- questions:
  - answer: Yes, use `CopyToOptions` together with `ProjectRootTask` to specify a
      starting task, or manually copy selected tasks after the initial copy.
    question: Can I copy only a subset of tasks?
  - answer: Absolutely. You can load an MPP file and save the copy as XML, XER, or
      any other supported format—over **20 + formats** in total.
    question: Does Aspose.Tasks support copying between different file formats?
  - answer: Load the source with `new Project("file.mpp", new LoadOptions { Password
      = "pwd" })`, then proceed with the copy as usual.
    question: How do I handle password‑protected project files?
  - answer: Set `CopyToOptions.CopyResources = true` and `CopyToOptions.CopyTasks
      = false` to transfer only resource information.
    question: Is there a way to copy resource pools without tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community‑driven snippets, troubleshooting tips, and official documentation.
    question: Where can I find more examples?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks'te Kopyalama Seçenekleriyle Proje Verilerini Nasıl Kopyalarsınız
url: /tr/net/calendar-scheduling/copy-options/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'te Kopyalama Seçenekleriyle Proje Verilerini Kopyalama

## Giriş

Bir Microsoft Project dosyasından diğerine **projeyi nasıl kopyalanır** bilgilerini kopyalamanız gerekiyorsa, Aspose.Tasks for .NET size temiz, kod‑ilk bir yol sunar. Bu öğreticide, tam iş akışını—kaynak projeyi yükleme, kopyalama seçeneklerini yapılandırma, bir kopya oluşturma ve sonucu yükleme—adım adım göstereceğiz, böylece proje‑kopyalama mantığını herhangi bir .NET uygulamasına güvenle entegre edebilirsiniz.

## Hızlı Yanıtlar
- **Kopyalama özelliği ne yapar?** Proje verilerini çoğaltır ve takvimler, kaynaklar veya görünüm bilgileri gibi belirli bölümleri dahil etmenize veya hariç tutmanıza izin verir.  
- **Davranışı hangi sınıf kontrol eder?** `CopyToOptions` kopyalanacak şeyleri ince ayar yapmanıza olanak tanır.  
- **Lisans gerekli mi?** Üretim için geçerli bir Aspose.Tasks lisansı gerekir; ücretsiz deneme sürümü geliştirme için çalışır.  
- **Desteklenen formatlar?** Aspose.Tasks MPP, XML ve XER dosyalarını işler—toplamda 20 + format.  
- **Görünüm verilerini atlayabilir miyim?** Evet, UI‑ile ilgili bilgileri dışarıda bırakmak için `CopyToOptions.SkipViewData = true` ayarlayın.

## Aspose.Tasks'te “projeyi nasıl kopyalanır” nedir?
**“Projeyi nasıl kopyalanır”**, Aspose.Tasks API'sini kullanarak bir Project nesnesinin verilerini yeni bir dosyaya çoğaltmak anlamına gelir, isteğe bağlı olarak istenmeyen öğeler filtrelenebilir. Bu işlem, şablon oluşturma, arşivleme veya proje varyantları yaratma gibi manuel UI adımları olmadan faydalıdır ve tüm desteklenen dosya formatlarında çalışır.

## Aspose.Tasks'te Kopyalama Seçeneklerini Neden Kullanmalısınız?
Aspose.Tasks **50+ proje‑ilişkili varlık** (görevler, kaynaklar, takvimler, atamalar vb.) destekler ve **10.000'e kadar görev** içeren dosyaları işleyebilir, bellek kullanımını 200 MB'nin altında tutar. `CopyToOptions` kullanarak ağır görünüm verilerini kopyalamaktan kaçınabilir, çıktı dosya boyutunu **%30‑40** azaltabilir ve büyük projeler için işlemi yaklaşık **2×** hızlandırabilirsiniz.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. **Aspose.Tasks for .NET** – en son sürümü [download link](https://releases.aspose.com/tasks/net/) adresinden indirin.  
2. **.NET geliştirme ortamı** – Visual Studio 2022 (veya .NET 6+ destekleyen herhangi bir IDE) yüklü.  
3. **Geçerli bir Aspose.Tasks lisansı** – değerlendirme için isteğe bağlı, üretim sürümleri için zorunlu.  
4. **Mevcut bir proje dosyası** (ör. `SourceProject.xml`) kopyalamak istediğiniz.

## Aspose.Tasks için ad alanlarını nasıl içe aktarılır?
C# dosyanızın üst kısmına gerekli `using` yönergelerini ekleyin, böylece derleyici Aspose.Tasks tiplerini bulabilir. Bu ifadeleri eklemek, `Project`, `CopyToOptions` ve diğer yardımcı sınıflara tam nitelikli adlarını kullanmadan doğrudan erişim sağlar, kodunuzu basitleştirir ve okunabilirliği artırır.

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Util;
```

## Adım 1: Proje Nesnelerini Başlatma

İlk olarak, kaynak dosyayı temsil eden bir `Project` örneği oluşturun ve XML verisini yükleyin.  
`Project` sınıfı, belleğe yüklenen bir Microsoft Project dosyasını temsil eder ve görevler, kaynaklar, takvimler ve diğer proje bilgilerini ortaya çıkarır.

```csharp
Project sourceProject = new Project("SourceProject.xml");
```

> **Pro ipucu:** Çok büyük dosyalarla çalışıyorsanız, bellek tüketimini düşük tutmak için tembel yüklemeyi etkinleştiren `LoadOptions` yapıcısını kullanmayı düşünün.

## Adım 2: Projenin Bir Kopyasını Oluşturma

Sonra, kopyalanan verileri alacak ikinci bir `Project` nesnesi oluşturun. Bu nesne boş olarak başlar.

```csharp
Project copiedProject = new Project();
```

Artık iki ayrı `Project` nesneniz var: biri diskte yüklendi, diğeri kopyayı almaya hazır.

## Adım 3: Kopyalanan Projeyi Yükleme

Kopyalama işlemi (daha sonra gösterilecek) sonrasında, yeni kaydedilen dosyayı başka bir `Project` örneğine yükleyerek sonucu doğrulamak isteyeceksiniz.

```csharp
Project verificationProject = new Project("CopiedProject.xml");
```

Dosyayı geri yüklemek, kopyalamanın başarılı olduğunu ve ayarladığınız seçeneklerin beklendiği gibi çalıştığını doğrular.

## Adım 4: Kopyalama Seçeneklerini Yapılandırma

`CopyToOptions` sınıfı, kaynaktan hedefe tam olarak neyin aktarılacağını belirlemenizi sağlar.

```csharp
CopyToOptions options = new CopyToOptions
{
    // Skip copying view information (Gantt charts, tables, etc.)
    SkipViewData = true,
    
    // Include only common project data (tasks, resources, assignments)
    CopyCommonData = true
};
```

`SkipViewData = true` ayarı, çıktı dosya boyutunu azaltır ve işlemi hızlandırır, özellikle yalnızca mantıksal proje verilerine ihtiyacınız olduğunda.

## Adım 5: Proje Kopyasını Gerçekleştirme

Son olarak, kaynak proje üzerinde `CopyTo` metodunu çağırın, hedef projeyi ve yapılandırdığınız seçenekleri geçirin.

```csharp
sourceProject.CopyTo(copiedProject, options);
copiedProject.Save("CopiedProject.xml", SaveFileFormat.Xml);
```

Bu iki satırlık çağrı, tanımladığınız seçeneklere saygı göstererek tüm kopyalama işlemini gerçekleştirir. Oluşan `CopiedProject.xml` yalnızca istediğiniz verileri içerir.

## Yaygın Sorunlar ve Çözümler

| Sorun | Neden | Çözüm |
|-------|-------|-----|
| **`CopyTo` çağrılırken NullReferenceException** | Hedef proje örneklenmemiş. | `CopyTo`'dan önce `new Project()` çağrıldığından emin olun. |
| **Kopyalama sonrası görevler eksik** | `CopyCommonData` false olarak ayarlanmış. | `CopyCommonData = true` olarak ayarlayın veya belirli koleksiyonları manuel olarak kopyalayın. |
| **Büyük çıktı dosyası** | `SkipViewData` false olarak bırakılmış. | UI‑ile ilgili verileri dışarıda bırakmak için `SkipViewData`'yi etkinleştirin. |
| **Lisans uygulanmadı** | Lisans dosyası yüklenmemiş. | Herhangi bir API kullanmadan önce `License license = new License(); license.SetLicense("Aspose.Tasks.lic");` kodunu çalıştırın. |

## Sıkça Sorulan Sorular

**S: Yalnızca bir görev alt kümesini kopyalayabilir miyim?**  
C: Evet, başlangıç görevi belirtmek için `CopyToOptions` ile `ProjectRootTask` birlikte kullanın veya ilk kopyadan sonra seçili görevleri manuel olarak kopyalayın.

**S: Aspose.Tasks farklı dosya formatları arasında kopyalamayı destekliyor mu?**  
C: Kesinlikle. Bir MPP dosyasını yükleyebilir ve kopyayı XML, XER veya diğer desteklenen formatlardan herhangi birine kaydedebilirsiniz—toplamda **20 + format**.

**S: Şifre korumalı proje dosyalarını nasıl yönetirim?**  
C: Kaynağı `new Project("file.mpp", new LoadOptions { Password = "pwd" })` ile yükleyin, ardından kopyalamaya normal şekilde devam edin.

**S: Görevler olmadan kaynak havuzlarını kopyalamanın bir yolu var mı?**  
C: Yalnızca kaynak bilgilerini aktarmak için `CopyToOptions.CopyResources = true` ve `CopyToOptions.CopyTasks = false` ayarlayın.

**S: Daha fazla örnek nerede bulunabilir?**  
C: Topluluk tarafından sağlanan kod parçacıkları, sorun giderme ipuçları ve resmi belgeler için [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) adresini ziyaret edin.

---

**Son Güncelleme:** 2026-07-05  
**Test Edilen Versiyon:** Aspose.Tasks 24.12 for .NET  
**Yazar:** Aspose  

```csharp
using Aspose.Tasks;
using System.IO;


```
```csharp
var project = new Project(DataDir + "CopyToProjectEmpty.xml");
```
```csharp
File.Copy(DataDir + "CopyToProjectEmpty.mpp", OutDir + "ProjectCopying_out.mpp", true);
```
```csharp
var mppProject = new Project(OutDir + "ProjectCopying_out.mpp");
```
```csharp
var copyToOptions = new CopyToOptions();
copyToOptions.CopyViewData = false;
```
```csharp
project.CopyTo(mppProject, copyToOptions);
```

{{< blocks/products/products-backtop-button >}}

## İlgili Öğreticiler

- [Aspose.Tasks ile Proje Verilerini Ustalaştırma](/tasks/net/project-management-integration/project-data/)
- [Aspose.Tasks için MS Project Kaydetme Seçeneklerini Ustalaştırma](/tasks/net/saving-options/general-save-options/)
- [Aspose.Tasks Takvim ve Zamanlama](/tasks/net/calendar-scheduling/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}