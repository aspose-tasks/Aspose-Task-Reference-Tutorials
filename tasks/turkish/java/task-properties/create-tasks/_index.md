---
date: 2026-09-25
description: Aspose.Tasks kullanarak Java'da project schedule oluşturmayı öğrenin.
  Bu kılavuz, summary tasks eklemeyi, project hierarchy yönetmeyi ve document directory'yi
  verimli bir şekilde ayarlamayı gösterir.
keywords:
- create project schedule
- java project management
- java task management
- add summary task
- manage project hierarchy
lastmod: 2026-09-25
linktitle: Aspose.Tasks'te Tasks Oluştur
og_description: Aspose.Tasks kullanarak Java'da project schedule oluşturmayı öğrenin.
  step‑by‑step talimatlarla summary tasks ekleyin, project hierarchy yönetin ve document
  directory'yi ayarlayın.
og_image_alt: Tutorial image showing Aspose.Tasks Java project schedule creation
og_title: Aspose.Tasks for Java ile project schedule nasıl oluşturulur
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to create project schedule in Java using Aspose.Tasks. This
    guide shows you how to add summary tasks, manage project hierarchy, and set document
    directory efficiently.
  headline: How to create project schedule with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create project schedule in Java using Aspose.Tasks. This
    guide shows you how to add summary tasks, manage project hierarchy, and set document
    directory efficiently.
  name: How to create project schedule with Aspose.Tasks for Java
  steps:
  - name: set the document directory
    text: Define where the resulting project file will be written. Setting the directory
      early ensures all subsequent save operations use a consistent path. The `RootFolder`
      property specifies the base folder where project files are read from or written
      to.
  - name: create a new project
    text: Instantiate a fresh `Project` object that will hold your schedule. You can
      optionally pass a pre‑existing file path to load an existing schedule for modification.
      The `Project` constructor creates an empty schedule ready for task addition.
  - name: add a summary task
    text: A summary task groups related subtasks and appears as a collapsible node
      in Gantt charts. Use the `Task` class and set `IsSummary` to `true`. The `addTask`
      method creates a new task under a specified parent and returns its ID.
  - name: add a subtask
    text: Subtasks inherit start/finish dates from their parent summary task unless
      you override them. Adding a subtask is as simple as calling `addTask` again
      and specifying the parent ID. Calling `addTask` with a parent ID adds a subtask
      under that summary task. Continue adding as many tasks and subtasks as
  type: HowTo
- questions:
  - answer: Absolutely. The library scales from a single‑task list to enterprise‑level
      schedules with thousands of tasks.
    question: Is Aspose.Tasks suitable for small‑scale projects?
  - answer: Refer to the documentation [Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/).
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Visit the [temporary license request page](https://purchase.aspose.com/temporary-license/)
      for a time‑limited license that works for development and testing.
    question: How do I obtain a temporary license for Aspose.Tasks?
  - answer: Yes, you can extend tasks with custom fields, assign resources, and modify
      calendars programmatically.
    question: Can I customize task attributes using Aspose.Tasks?
  - answer: Absolutely! Join the Aspose.Tasks community on [the support forum](https://forum.aspose.com/c/tasks/15).
    question: Is there a support community for Aspose.Tasks users?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- create project schedule
- Aspose.Tasks
- Java project management
title: Aspose.Tasks for Java ile project schedule nasıl oluşturulur
url: /tr/java/task-properties/create-tasks/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java için Aspose.Tasks ile proje takvimi nasıl oluşturulur

## Giriş
Bu öğreticide, Aspose.Tasks kullanarak bir Java uygulamasında **create project schedule** nasıl oluşturulacağını öğreneceksiniz. Basit bir yapılacaklar listesi mi yoksa karmaşık bir kurumsal düzey planlayıcı mı oluşturuyorsanız, aşağıdaki adımlar özet görevler eklemeyi, proje hiyerarşisini yönetmeyi ve belge dizinini ayarlamayı adım adım gösterir—hepsi net, çalıştırılabilir kod parçacıklarıyla. Sonunda, daha fazla manipülasyon veya dışa aktarım için hazır, tamamen yapılandırılmış bir takvime sahip olacaksınız.

## Hızlı cevaplar
- **Aspose.Tasks neyi yönetir?** Görev hiyerarşileri, kaynaklar, takvimler ve proje dosya formatlarını (MS‑Project, Primavera vb.) yönetir.  
- **Geliştirme için lisansa ihtiyacım var mı?** Değerlendirme için ücretsiz geçici bir lisans çalışır; üretim için tam lisans gereklidir.  
- **Hangi Java sürümü destekleniyor?** Java 8 ve üzeri tam olarak desteklenir.  
- **Görevlere özel alanlar ekleyebilir miyim?** Evet, API aracılığıyla kullanıcı tanımlı alanlarla görevleri genişletebilirsiniz.  
- **Gantt grafikleri için yerleşik destek var mı?** Aspose.Tasks, Gantt görselleştirmelerini içeren PDF/HTML dışa aktarımı yapabilir.

## Aspose.Tasks'te proje takvimi nedir?
Proje takvimi, işin nasıl yürütüleceğini tanımlayan görevlerin, bağımlılıkların ve zaman çizelgelerinin tam setidir. Aspose.Tasks bu bilgileri, okuyabileceğiniz, değiştirebileceğiniz ve çeşitli formatlarda kaydedebileceğiniz bir `Project` nesnesinde saklar. Başlangıç ve bitiş tarihleri, kısıtlamalar ve kaynak atamaları içerir, kapsamlı planlama ve raporlama sağlar.

## Java proje yönetimi için Aspose.Tasks neden kullanılmalı?
Aspose.Tasks **30'dan fazla giriş ve çıkış formatını** destekler ve **10.000'e kadar görev** içeren projeleri tüm dosyayı belleğe yüklemeden işleyebilir, büyük ölçekli Java proje yönetimi senaryoları için yüksek performans sunar.

## Önkoşullar
Öğreticiye başlamadan önce, aşağıdaki önkoşulların yerine getirildiğinden emin olun:
- **Java Development Kit (JDK)** – Makinenizde JDK 8 veya daha yeni bir sürüm yüklü.  
- **Aspose.Tasks for Java kütüphanesi** – Kütüphaneyi [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/) adresinden indirin ve kurun.  
- **Entegre Geliştirme Ortamı (IDE)** – Eclipse, IntelliJ IDEA veya tercih ettiğiniz herhangi bir Java‑uyumlu IDE'yi kullanın.

## Paketleri içe aktar
`Project`, `Task` ve ilgili sınıflar `com.aspose.tasks` ad alanında bulunur. Bunları Java dosyanızın en üstüne içe aktarın:

`Project` sınıfı, tam bir proje takvimini temsil eder ve görevleri ve kaynakları manipüle etmek için yöntemler sunar.

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

`Project` sınıfı, bir proje dosyasındaki tüm işlemler için giriş noktasıdır.

## Aspose.Tasks ile proje takvimi nasıl oluşturulur?

Yeni bir `Project` örneği yükleyin, belge dizinini ayarlayın ve görev eklemeye başlayın. Bu doğrudan‑cevap paragrafı temel akışı açıklar: bir `Project` oluşturursunuz, `RootFolder` (belge dizini) özelliğini yapılandırırsınız, ardından bir özet görev ve ardından alt görevler eklersiniz. Tüm değişiklikler, takvimi bir dosyaya kaydetmek için `save` çağrılana kadar bellekte tutulur.

### Adım 1: belge dizinini ayarla
Oluşturulan proje dosyasının nereye yazılacağını tanımlayın. Dizini erken ayarlamak, sonraki tüm kaydetme işlemlerinin tutarlı bir yol kullanmasını sağlar.

`RootFolder` özelliği, proje dosyalarının okunup yazıldığı temel klasörü belirtir.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```

### Adım 2: yeni bir proje oluştur
Takviminizi tutacak yeni bir `Project` nesnesi oluşturun. İsterseniz mevcut bir takvimi değiştirmek için önceden var olan bir dosya yolunu geçebilirsiniz.

`Project` yapıcı metodu, görev eklemeye hazır boş bir takvim oluşturur.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Adım 3: bir özet görev ekle
Özet görev, ilgili alt görevleri gruplar ve Gantt grafiklerinde katlanabilir bir düğüm olarak görünür. `Task` sınıfını kullanın ve `IsSummary` özelliğini `true` olarak ayarlayın.

`addTask` metodu, belirtilen bir üst görev altında yeni bir görev oluşturur ve onun kimliğini döndürür.

```java
// Create a new project
Project project = new Project(dataDir + "project.mpp");
```

### Adım 4: bir alt görev ekle
Alt görevler, siz geçersiz kılmadığınız sürece başlangıç/bitiş tarihlerini üst özet görevden devralır. Alt görev eklemek, `addTask` metodunu tekrar çağırıp üst görev kimliğini belirtmek kadar basittir.

Bir üst görev kimliğiyle `addTask` çağırmak, o özet görev altında bir alt görev ekler.

```java
// Add a summary task
Task task = project.getRootTask().getChildren().add("Summary1");
```

Projeniz için gerektiği kadar görev ve alt görev eklemeye devam edin. Her adım, MS‑Project, PDF veya diğer desteklenen formatlara dışa aktarılabilecek yapılandırılmış bir proje hiyerarşisi oluşturulmasına katkı sağlar.

## Yaygın sorunlar ve çözümler
- **Problem:** “Document directory not found.”  
  **Solution:** `RootFolder`'a atadığınız yolun dosya sisteminde mevcut olduğunu ve Java sürecinizin yazma izinlerine sahip olduğunu doğrulayın.
- **Problem:** Alt görevler özet görevin altında görünmüyor.  
  **Solution:** `addTask` çağırırken doğru üst görev kimliğini geçtiğinizden emin olun. API, üst görev kimliğini ikinci argüman olarak ister.
- **Problem:** Büyük projeler OutOfMemoryError hatasına neden oluyor.  
  **Solution:** Aspose.Tasks görevleri akış (streaming) modunda işler; JVM yığın boyutunu (`-Xmx2g`) artırın veya takvimi birden fazla dosyaya bölün.

## Sıkça sorulan sorular
**S: Aspose.Tasks küçük ölçekli projeler için uygun mu?**  
A: Evet. Kütüphane, tek görevli bir listeden binlerce görev içeren kurumsal düzey takvimlere kadar ölçeklenir.

**S: Aspose.Tasks for Java için ayrıntılı belgeleri nerede bulabilirim?**  
A: Belgelere [Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/) adresinden bakın.

**S: Aspose.Tasks için geçici bir lisans nasıl alabilirim?**  
A: Geliştirme ve test için geçerli zaman sınırlı bir lisans almak için [temporary license request page](https://purchase.aspose.com/temporary-license/) adresini ziyaret edin.

**S: Aspose.Tasks kullanarak görev niteliklerini özelleştirebilir miyim?**  
A: Evet, görevleri özel alanlarla genişletebilir, kaynak atayabilir ve takvimleri programlı olarak değiştirebilirsiniz.

**S: Aspose.Tasks kullanıcıları için bir destek topluluğu var mı?**  
A: Evet! Aspose.Tasks topluluğuna [the support forum](https://forum.aspose.com/c/tasks/15) üzerinden katılabilirsiniz.

**Son Güncelleme:** 2026-09-25  
**Test Edilen Versiyon:** Aspose.Tasks 24.12 for Java  
**Yazar:** Aspose  

```java
// Add a subtask under the summary task
Task subtask = task.getChildren().add("Subtask1");
```

## İlgili Öğreticiler

- [MS Project'te Proje Başlangıç Tarihini Aspose.Tasks for Java ile ayarlama](/tasks/java/project-properties/write-project-info/)
- [Aspose.Tasks'de Proje Yönetimi Görev Bağlantılarını Oluşturma](/tasks/java/task-links/create-task-link/)
- [Aspose.Tasks'de Projeye Kaynak Ekleme ve Kaynak Atamaları Oluşturma](/tasks/java/resource-assignments/create-resource-assignments/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}