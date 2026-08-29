---
date: 2026-08-29
description: Aspose.Tasks for Java kullanarak temel süreyi nasıl ayarlayacağınızı
  ve proje ilerlemesini nasıl izleyeceğinizi öğrenin. Bu adım adım rehber, görev temellerini
  verimli bir şekilde yönetmenize yardımcı olur.
keywords:
- track project progress
- manage project baselines
- Aspose.Tasks baseline duration
- Java project scheduling
- baseline management
lastmod: 2026-08-29
linktitle: Aspose.Tasks for Java'da Temel Süreyi Nasıl Ayarlarsınız
og_description: Aspose.Tasks for Java kullanarak temel süreyi nasıl ayarlayacağınızı
  ve proje ilerlemesini nasıl izleyeceğinizi öğrenin. Görev temellerini verimli bir
  şekilde yönetmek için bu ayrıntılı rehberi izleyin.
og_image_alt: Developer guide showing baseline duration setup with Aspose.Tasks for
  Java
og_title: Proje ilerlemesini izlemek için temel süreyi nasıl ayarlarsınız
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to set baseline duration and track project progress using
    Aspose.Tasks for Java. This step‑by‑step guide helps you manage task baselines
    efficiently.
  headline: How to set baseline duration to track project progress
  type: TechArticle
- description: Learn how to set baseline duration and track project progress using
    Aspose.Tasks for Java. This step‑by‑step guide helps you manage task baselines
    efficiently.
  name: How to set baseline duration to track project progress
  steps:
  - name: '**Java Development Environment** – JDK 8+ installed and configured.'
    text: '**Java Development Environment** – JDK 8+ installed and configured.'
  - name: '**Aspose.Tasks for Java** – download the library from the [Aspose.Tasks
      for Java download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the library from the [Aspose.Tasks
      for Java download page](https://releases.aspose.com/tasks/java/).'
  - name: '**IDE or build tool** – Maven, Gradle, or any IDE you prefer.'
    text: '**IDE or build tool** – Maven, Gradle, or any IDE you prefer.'
  type: HowTo
- questions:
  - answer: No. Calling `project.setBaseline(BaselineType.Baseline)` records the baseline
      for all tasks in the project at once.
    question: Do I need to call `setBaseline` for each task individually?
  - answer: Use `project.setBaseline(BaselineType.Baseline1)` (or Baseline2‑Baseline10)
      after updating the task’s schedule.
    question: How can I set an interim baseline for a specific task?
  - answer: Yes. Iterate over `task.getBaselines()` and write the desired fields to
      a CSV file using standard Java I/O.
    question: Is it possible to export the baseline data to CSV?
  - answer: Absolutely. Load the file with `new Project("myproject.mpp")` and then
      access each task’s baselines as shown above.
    question: Can I read an existing .mpp file that already contains baselines?
  - answer: Aspose.Tasks works with single‑project .mpp files. For multi‑project scenarios,
      combine the projects programmatically.
    question: Does Aspose.Tasks handle multi‑project files?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- baseline duration
- Aspose.Tasks
- Java project management
- task baselines
title: Proje ilerlemesini izlemek için temel süreyi nasıl ayarlarsınız
url: /tr/java/task-baselines/task-baseline-duration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Proje ilerlemesini izlemek için temel süreyi nasıl ayarlarsınız

## Giriş
Proje ilerlemesini izlemek sağlam bir temel ile başlar. Bu öğreticide, Java için Aspose.Tasks kütüphanesini kullanarak Microsoft Project dosyalarındaki görevler için **temel sürenin nasıl ayarlanacağını** keşfedecek ve erken bir temel oluşturmanın, projenin yaşamı boyunca zaman kayması, maliyet sapması ve kaynak aşırı tahsislerini izlemenize nasıl yardımcı olduğunu anlayacaksınız.

## Hızlı cevaplar
- **“set baseline” ne anlama gelir?** Bir görevin orijinal başlangıç, bitiş ve süresini kaydeder, böylece gelecekteki değişikliklerle karşılaştırabilirsiniz.  
- **Hangi Aspose.Tasks sınıfı bir proje oluşturur?** `Project` sınıfı – ayrıca **bir proje örneği oluşturmayı** doğru şekilde öğreneceksiniz.  
- **Kodu çalıştırmak için bir lisansa ihtiyacım var mı?** Test için ücretsiz bir değerlendirme lisansı yeterlidir; üretim için ticari bir lisans gereklidir.  
- **Ara temelleri alabilir miyim?** Evet, Aspose.Tasks ara temelleri ve bunların sabit maliyetlerini sorgulamanıza izin verir.  
- **Hangi Java sürümü gereklidir?** Java 8 veya daha yenisi önerilir.  
- **Bu, proje ilerlemesini izlememe nasıl yardımcı olur?** Temel ayarlandıktan sonra, yerleşik raporlama özelliklerini kullanarak gerçek tarihleri orijinal planla anında karşılaştırabilirsiniz.

## Görev temeli nedir ve neden ayarlanır?
Bir görev temeli, belirli bir zamanda planlanan takvimi (başlangıç tarihi, bitiş tarihi ve süre) yakalar. Bir temel ayarlayarak, projenin ilerlemesi sırasında zaman kayması, maliyet aşımları ve kaynak aşırı tahsislerini kolayca fark etmenizi sağlayan bir referans noktası oluşturursunuz.

## Temel yönetimi için neden Aspose.Tasks kullanılır?
Aspose.Tasks **tam .mpp uyumluluğu** sağlar – Microsoft Office yüklü olmadan yerel Microsoft Project dosyalarını okuyup yazabilirsiniz. API, **50+ giriş ve çıkış formatına** programatik erişim sunar, **ara temeller 1‑10**'u destekler ve tüm dosyayı belleğe yüklemeden **yüzlerce sayfalık projeleri** işleyebilir; bu, yüksek performanslı toplu işleme için esastır.

## Önkoşullar
1. **Java Geliştirme Ortamı** – JDK 8+ yüklü ve yapılandırılmış.  
2. **Aspose.Tasks for Java** – kütüphaneyi [Aspose.Tasks for Java indirme sayfasından](https://releases.aspose.com/tasks/java/) indirin.  
3. **IDE veya derleme aracı** – Maven, Gradle veya tercih ettiğiniz herhangi bir IDE.

## Paketleri içe aktar
Aşağıdaki içe aktarmalar, projeler, görevler, temeller ve zaman‑fazlı verilerle çalışmak için gerekli olan temel Aspose.Tasks sınıflarını getirir.

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```

## Adım 1: bir proje örneği oluşturun
`Project` sınıfı, bellekte bir Microsoft Project dosyasını temsil eder ve tüm işlemler için giriş noktasıdır.

```java
Project project = new Project();
```

## Adım 2: bir görev temeli oluşturun
`TaskBaseline`, belirli bir görev için planlanan başlangıç, bitiş ve süreyi depolar.

```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## Adım 3: görev temeli bilgilerini göster
`getBaselines()` yöntemi, bir görevle ilişkili temel koleksiyonunu döndürür.

```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## Adım 4: ara temeli ve sabit maliyeti kontrol et
`BaselineType`, birincil ve ara temelleri (Baseline, Baseline1‑Baseline10) sıralar.

```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```

## Adım 5: zaman‑fazlı verileri yazdır
`TimephasedData`, belirli bir zaman aralığı için takvim bilgisi parçasını temsil eder.

```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```

Bu adımları izleyerek, herhangi bir görev için **temel süresini ayarlayabilir** ve Aspose.Tasks for Java kullanarak ayrıntılı temel bilgilerini alabilirsiniz; bu, proje yaşam döngüsü boyunca **proje ilerlemesini izlemek** için güvenilir bir yol sunar.

## Yaygın sorunlar ve çözümler
- **Temel MS Project'te görünmüyor:** Görevi ekledikten **sonra** `project.setBaseline(BaselineType.Baseline)` çağırdığınızdan emin olun.  
- **`getBaselines()` üzerinde NullPointerException:** Temeli ayarlamadan önce görevin projeye eklendiğini doğrulayın.  
- **Zaman birimi uyumsuzluğu:** Özellikle özel takvimlerle çalışırken süreyi doğru biçimlendirmek için `TimeUnitType` kullanın.

## SSS
### MS Project'te görev temeli nedir?
MS Project'te bir görev temeli, bir görevin başlangıç tarihi, bitiş tarihi ve süresi dahil olmak üzere ilk planlanan takvimin bir anlık görüntüsüdür.

### Görev temellerini yönetmek neden önemlidir?
Görev temellerini yönetmek, planlanan takvimi projenin gerçek ilerlemesiyle karşılaştırmaya yardımcı olur, daha iyi izleme ve karar‑alma süreçlerini kolaylaştırır.

### Bir görev temeli ayarlandıktan sonra değiştirebilir miyim?
Evet, MS Project'te proje planındaki değişiklikleri yansıtmak için görev temellerini değiştirebilirsiniz. Ancak, orijinal temelden herhangi bir sapmayı belgelemek önemlidir.

### Aspose.Tasks diğer proje yönetimi işlevlerini destekliyor mu?
Evet, Aspose.Tasks görev zamanlaması, kaynak tahsisi ve Gantt şeması oluşturma gibi proje yönetimi için geniş bir özellik yelpazesi sunar.

### Aspose.Tasks için desteği nereden bulabilirim?
Aspose.Tasks için desteği, sorular sorabileceğiniz ve diğer kullanıcılarla etkileşimde bulunabileceğiniz [Aspose.Tasks forumunda](https://forum.aspose.com/c/tasks/15) bulabilirsiniz.

## Ek sıkça sorulan sorular
**S: `setBaseline` yöntemini her görev için ayrı ayrı çağırmam gerekiyor mu?**  
C: Hayır. `project.setBaseline(BaselineType.Baseline)` çağırmak, projedeki tüm görevler için temeli bir kerede kaydeder.

**S: Belirli bir görev için ara temel nasıl ayarlanır?**  
C: Görevin takvimini güncelledikten sonra `project.setBaseline(BaselineType.Baseline1)` (veya Baseline2‑Baseline10) kullanın.

**S: Temel verilerini CSV'ye dışa aktarmak mümkün mü?**  
C: Evet. `task.getBaselines()` üzerinde döngü yaparak istenen alanları standart Java I/O kullanarak bir CSV dosyasına yazabilirsiniz.

**S: Zaten temel içeren mevcut bir .mpp dosyasını okuyabilir miyim?**  
C: Kesinlikle. Dosyayı `new Project("myproject.mpp")` ile yükleyin ve ardından yukarıda gösterildiği gibi her görevin temellerine erişin.

**S: Aspose.Tasks çoklu‑proje dosyalarını yönetebiliyor mu?**  
C: Aspose.Tasks tek‑proje .mpp dosyalarıyla çalışır. Çoklu‑proje senaryoları için projeleri programlı olarak birleştirin.

---

**Son Güncelleme:** 2026-08-29  
**Test Edildiği Versiyon:** Aspose.Tasks for Java 24.12  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Görev Listesi Oluştur Java – Aspose.Tasks kullanarak MS Project Temeli](/tasks/java/task-baselines/create-task-baseline/)
- [MPP Projesi Oluştur Java – Aspose.Tasks ile Görev İlerlemesini Değiştir](/tasks/java/task-properties/change-progress/)
- [Proje Yönetimi Temeli – Aspose.Tasks ile Görev Zamanlaması](/tasks/java/task-baselines/baseline-task-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}