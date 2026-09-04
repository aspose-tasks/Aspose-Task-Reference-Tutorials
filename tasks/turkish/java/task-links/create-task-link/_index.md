---
date: 2026-07-05
description: Aspose.Tasks kullanarak Java'da proje yönetimi görev bağımlılıklarını
  nasıl oluşturacağınızı öğrenin. Kod parçacıklarıyla adım adım bu rehberi izleyin.
keywords:
- project management task dependencies
- Aspose.Tasks Java
- task linking tutorial
linktitle: Aspose.Tasks'te Proje Yönetimi Görev Bağımlılıklarını Oluşturun
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to create project management task dependencies in Java using
    Aspose.Tasks. Follow this step‑by‑step guide with code snippets.
  headline: Create Project Management Task Dependencies in Aspose.Tasks
  type: TechArticle
- description: Learn how to create project management task dependencies in Java using
    Aspose.Tasks. Follow this step‑by‑step guide with code snippets.
  name: Create Project Management Task Dependencies in Aspose.Tasks
  steps:
  - name: Set Document Directory
    text: Define the directory where your documents are stored to ensure Aspose.Tasks
      locates and processes files correctly. The `java.nio.file.Paths` utility helps
      you build platform‑independent file paths. java // The path to the documents
      directory. String dataDir = "Your Document Directory";
  - name: Initialize Project and Tasks
    text: Create a new project and initialize tasks within it. In this example, "Task
      1" and "Task 2" are added to the root task. The `Task` class represents an individual
      work item; each task can have its own ID, name, and schedule. java Project project
      = new Project(dataDir + "project5.mpp"); Task pred = pr
  - name: Establish Task Link
    text: Utilize the `getTaskLinks()` method to add a link between two tasks. This
      example demonstrates linking "Task 1" as a predecessor to "Task 2." The `TaskLink`
      object defines the type of dependency (Finish‑to‑Start, Start‑to‑Start, etc.)
      and optional lag. java TaskLink link = project.getTaskLinks().add
  - name: Display Result
    text: Print a message indicating the successful completion of the task link creation
      process. This step is crucial for debugging and verification. A simple `System.out.println`
      call confirms that the link was added without errors. java // Display the result
      of the conversion. System.out.println("Task Link
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks seamlessly integrates with Spring, Jakarta EE, Android,
      and any standard Java environment.
    question: Can I use Aspose.Tasks for Java with other Java frameworks?
  - answer: Yes, explore the functionalities with the [free trial](https://releases.aspose.com/)
      before making a commitment.
    question: Is there a free trial available before purchasing the library?
  - answer: Acquire a temporary license [here](https://purchase.aspose.com/temporary-license/)
      for testing and evaluation purposes.
    question: How can I obtain a temporary license for Aspose.Tasks for Java?
  - answer: Yes, check the documentation for comprehensive sample projects and code
      snippets.
    question: Are there any sample projects available for reference?
  - answer: Secure your copy by visiting the [purchase page](https://purchase.aspose.com/buy)
      and explore licensing options.
    question: What is the recommended way to purchase Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks'te Proje Yönetimi Görev Bağımlılıklarını Oluşturun
url: /tr/java/task-links/create-task-link/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks ile Proje Yönetimi Görev Bağımlılıkları Oluşturma

## Giriş
Proje yönetimi görev bağımlılıkları, iyi yapılandırılmış bir takvimin temelini oluşturur; başlangıç tarihlerini, bitiş tarihlerini ve kritik yolları otomatik olarak hesaplamayı sağlar. Bu öğreticide, Java için Aspose.Tasks kullanarak **proje yönetimi görev bağımlılıkları** oluşturmayı öğreneceksiniz; bu kütüphane 50 den fazla dosya formatını destekler ve tüm dosyayı belleğe yüklemeden binlerce görevli projeleri işleyebilir. Aşağıdaki adımları izleyerek görevleri bağlayın, bağlantıları doğrulayın ve çözümü gerçek dünya uygulamalarına entegre edin.

## Hızlı Yanıtlar
- **Bu öğreticide ne ele alınıyor?** Aspose.Tasks for Java ile görev bağlantıları (bağımlılıkları) oluşturma.  
- **Kaç satır kod gerekir?** Temel bağlantı mantığı sadece iki ifadeye sığar.  
- **Denemek için lisansa ihtiyacım var mı?** 30 günlük ücretsiz bir deneme mevcuttur; üretim için lisans gereklidir.  
- **Hangi Java sürümleri destekleniyor?** Java 8 ‑ 17 tam olarak desteklenir.  
- **İki görevden fazla bağlayabilir miyim?** Evet – istediğiniz sayıda önceki‑sonraki çift için bağlantı desenini tekrarlayın.

## Proje yönetimi görev bağımlılıkları nedir?
Proje yönetimi görev bağımlılıkları, bir görevin başlangıç veya bitişinin başka bir görevle nasıl ilişkili olduğunu tanımlar ve işin hangi sırayla yapılması gerektiğini belirler. Aspose.Tasks bu ilişkileri `TaskLink` nesneleri aracılığıyla temsil eder; bu nesneleri programlı olarak oluşturabilir, değiştirebilir veya silebilirsiniz.

## Görev Bağlantısı İçin Aspose.Tasks Neden Kullanılmalı?
Aspose.Tasks **50+ giriş ve çıkış formatını** (MPP, XML, CSV vb.) destekler ve **10.000+ görev** içeren projeleri tipik bir sunucuda 200 MB'den az RAM kullanarak işleyebilir. API'si, bağlantı türleri, gecikme süreleri ve kısıtlama yönetimi üzerinde ince ayar yapmanıza olanak tanır; Microsoft Project'in yüklü olmasına gerek yoktur.

## Ön Koşullar
Öğreticiye başlamadan önce aşağıdaki ön koşulların sağlandığından emin olun:
- Java Geliştirme Ortamı: Makinenizde çalışan bir Java geliştirme ortamı kurun.  
- Aspose.Tasks Kütüphanesi: Aspose.Tasks for Java kütüphanesini indirin ve entegre edin, [buradan](https://releases.aspose.com/tasks/java/) ulaşabilirsiniz.

## Paketleri İçe Aktar
Başlamak için gerekli paketleri Java projenize dahil edin. Bu, Aspose.Tasks işlevlerine erişim için kritiktir.

`Project` sınıfı, Aspose.Tasks'in bellekte bir proje dosyasını temsil eden giriş noktasıdır.  
```text
```java
import com.aspose.tasks.*;
```
```

## Aspose.Tasks for Java ile görev bağlantıları nasıl oluşturulur?
Bir `Project` örneği yükleyin veya oluşturun, gerekli görevleri ekleyin ve ardından `getTaskLinks().add()` metodunu çağırarak bir bağımlılık kurun. Bu yöntem, önceki ve sonraki görevleri bağlayan bir `TaskLink` nesnesi oluşturur; isteğe bağlı olarak bağlantı türü ve gecikme süresi belirtebilirsiniz. Aşağıdaki adımlar, ekstra kod kalıbı olmadan ihtiyacınız olan tam kodu gösterir.

### Adım 1: Belge Dizini Ayarla
Belgelerinizin depolandığı dizini tanımlayın; böylece Aspose.Tasks dosyaları doğru şekilde bulur ve işler.

`java.nio.file.Paths` yardımcı sınıfı, platform bağımsız dosya yolları oluşturmanıza yardımcı olur.  
```text
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```
```

### Adım 2: Projeyi ve Görevleri Başlat
Yeni bir proje oluşturun ve içinde görevleri başlatın. Bu örnekte, kök göreve "Task 1" ve "Task 2" eklenir.

`Task` sınıfı, bireysel bir iş öğesini temsil eder; her görev kendi kimliği, adı ve takvimi olabilir.  
```text
```java
Project project = new Project(dataDir + "project5.mpp");
Task pred = project.getRootTask().getChildren().add("Task 1");
Task succ = project.getRootTask().getChildren().add("Task 2");
```
```

### Adım 3: Görev Bağlantısı Kur
`getTaskLinks()` metodunu kullanarak iki görev arasında bir bağlantı ekleyin. Bu örnek, "Task 1"i "Task 2"nin öncülü olarak bağlamayı gösterir.

`TaskLink` nesnesi, bağımlılık türünü (Finish‑to‑Start, Start‑to‑Start vb.) ve isteğe bağlı gecikmeyi tanımlar.  
```text
```java
TaskLink link = project.getTaskLinks().add(pred, succ);
```
```

### Adım 4: Sonucu Görüntüle
Görev bağlantısı oluşturma sürecinin başarılı bir şekilde tamamlandığını belirten bir mesaj yazdırın. Bu adım, hata ayıklama ve doğrulama için kritiktir.

Basit bir `System.out.println` çağrısı, bağlantının hatasız eklendiğini onaylar.  
```text
```java
// Display the result of the conversion.
System.out.println("Task Link Creation Process Completed Successfully");
```
```

Bu adımları daha karmaşık görev bağlama senaryoları için tekrarlayın, görev adlarını özelleştirin ve projenizin gereksinimlerine göre bağımlılıkları kurun.

Ayrıntılı API bilgileri için [Aspose.Tasks Documentation](https://reference.aspose.com/tasks/java/) sayfasına bakın.  
Topluluk desteği için [Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15) adresini ziyaret edin.

## Yaygın Sorunlar ve Çözümler
`save` metodu, eklenen bağlantılar dahil tüm değişiklikleri belirtilen dosya yoluna yazar.  
`TaskLinkType` enum'ı, `FinishToStart` gibi bir bitiş‑başlangıç bağımlılığı türünü tanımlar.

- **Bağlantı kaydedilen dosyada görünmüyor** – Bağlantıları ekledikten sonra `project.save(outputPath)` çağırdığınızdan emin olun.  
- **Yanlış bağlantı türü** – Zamanlama mantığınıza uygun olarak `TaskLinkType.FinishToStart`, `StartToStart` vb. kullanın.  
- **Büyük projeler bellek kullanımını artırıyor** – Yükleme öncesinde `project.setReadOnly(true)` ayarlayarak akış modunda çalışın.

## Sık Sorulan Sorular
**S: Aspose.Tasks for Java’yı diğer Java çerçeveleriyle kullanabilir miyim?**  
C: Evet, Aspose.Tasks Spring, Jakarta EE, Android ve herhangi bir standart Java ortamı ile sorunsuz entegrasyon sağlar.

**S: Kütüphaneyi satın almadan önce ücretsiz bir deneme mevcut mu?**  
C: Evet, [ücretsiz deneme](https://releases.aspose.com/) ile işlevleri keşfedebilirsiniz.

**S: Aspose.Tasks for Java için geçici bir lisans nasıl alınır?**  
C: Test ve değerlendirme amaçlı geçici lisansı [buradan](https://purchase.aspose.com/temporary-license/) edinebilirsiniz.

**S: Referans için örnek projeler var mı?**  
C: Evet, belgelerde kapsamlı örnek projeler ve kod parçacıkları bulunur.

**S: Aspose.Tasks for Java’yı satın almanın önerilen yolu nedir?**  
C: Kopyanızı edinmek için [satın alma sayfasını](https://purchase.aspose.com/buy) ziyaret edin ve lisans seçeneklerini inceleyin.

---

**Son Güncelleme:** 2026-07-05  
**Test Edilen Versiyon:** Aspose.Tasks 24.12 for Java  
**Yazar:** Aspose

## İlgili Eğitimler

- [Create Tasks Aspose Java – Task Properties](/tasks/java/task-properties/)
- [Project Management Baseline – Task Scheduling with Aspose.Tasks](/tasks/java/task-baselines/baseline-task-scheduling/)
- [How to Create Resources – Resource Management with Aspose.Tasks for Java](/tasks/java/resource-management/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}