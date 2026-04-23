---
date: 2026-01-23
description: Aspose.Tasks for Java kullanarak temel süreyi nasıl ayarlayacağınızı
  ve proje örneği oluşturacağınızı öğrenin. Bu adım adım rehber, görev temellerini
  verimli bir şekilde yönetmenize yardımcı olur.
linktitle: How to Set Baseline Duration in Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java'da Temel Süre Nasıl Ayarlanır
url: /tr/java/task-baselines/task-baseline-duration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java'da Temel Süre Nasıl Ayarlanır

## Giriş
Bir temel ayarlamak, projenin ilerlemesini orijinal plana karşı izlemek için temel bir adımdır. Bu öğreticide, Aspose.Tasks Java kütüphanesini kullanarak Microsoft Project'teki görevlerin **temel süresini nasıl ayarlayacağınızı** öğrenecek ve erken bir temel oluşturmanın daha sonra zaman ve baş ağrısı tasarrufu sağlayacağını göreceksiniz.

## Hızlı Yanıtlar
- **“set baseline” ne anlama gelir?** Bir görevin orijinal başlangıç, bitiş ve süresini kaydeder, böylece gelecekteki değişikliklerle karşılaştırabilirsiniz.  
- **Hangi Aspose.Tasks sınıfı bir proje oluşturur?** `Project` sınıfı – ayrıca **proje örneği oluşturmayı** doğru şekilde öğreneceksiniz.  
- **Kodu çalıştırmak için lisansa ihtiyacım var mı?** Test için ücretsiz değerlendirme lisansı yeterlidir; üretim için ticari lisans gereklidir.  
- **Ara temelleri alabilir miyim?** Evet, Aspose.Tasks ara temelleri ve bunların sabit maliyetlerini sorgulamanıza izin verir.  
- **Hangi Java sürümü gereklidir?** Java 8 veya daha yenisi önerilir.

## Bir görev temeli nedir ve neden ayarlanır?
Bir görev temeli, belirli bir zamanda planlanan takvimi (başlangıç tarihi, bitiş tarihi ve süre) yakalar. Bir temel ayarlayarak, projenin ilerlemesi sırasında takvim sapmalarını, maliyet aşımlarını ve kaynak aşırı tahsislerini kolayca fark edebileceğiniz bir referans noktası oluşturursunuz.

## Temel yönetimi için neden Aspose.Tasks kullanmalı?
- **Tam .mpp uyumluluğu** – Office yüklü olmadan yerel Microsoft Project dosyalarını okuyup yazabilirsiniz.  
- **Zengin API** – temel verilerine, ara temellere ve zaman‑fazlı bilgilere programlı olarak erişebilirsiniz.  
- **Çapraz platform** – herhangi bir standart JDK ile Windows, Linux ve macOS'ta çalışır.

## Önkoşullar
1. **Java Geliştirme Ortamı** – JDK 8+ yüklü ve yapılandırılmış.  
2. **Aspose.Tasks for Java** – kütüphaneyi [here](https://releases.aspose.com/tasks/java/) adresinden indirin.  
3. **IDE veya derleme aracı** – Maven, Gradle veya tercih ettiğiniz herhangi bir IDE.

## Paketleri İçe Aktarma
İlk olarak, gerekli sınıfları Java projenize içe aktarın:

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```

## Adım 1: Proje Örneği Oluşturma
Bir proje örneği oluşturmak, sonraki tüm manipülasyonların temelidir. Bu adım, Aspose.Tasks kullanarak **proje örneği oluşturmayı** gösterir:

```java
Project project = new Project();
```

## Adım 2: Görev Temeli Oluşturma
Projeye kök seviyesinde yeni bir görev ekleyin ve temelini ayarlayın. Bu, görevin orijinal takvimini kaydeder:

```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## Adım 3: Görev Temeli Bilgilerini Görüntüleme
Az önce oluşturduğunuz temeli alın ve ana özelliklerini yazdırın. Bu, temelinin doğru şekilde ayarlandığını doğrulamanıza yardımcı olur:

```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## Adım 4: Ara Temeli ve Sabit Maliyeti Kontrol Etme
Ara temellerle çalışıyorsanız, mevcut temelinin ara olup olmadığını ve ilişkili sabit maliyeti sorgulayabilirsiniz:

```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```

## Adım 5: Zaman‑Fazlı Verileri Yazdırma
Zaman‑fazlı veri, temelinin zaman içinde nasıl dağıldığını gösterir. Koleksiyonu döngüyle gezerek her bir girişi inceleyin:

```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```

Bu adımları izleyerek, herhangi bir görev için **temel süresini nasıl ayarlayacağınızı** öğrenebilir ve Aspose.Tasks for Java kullanarak ayrıntılı temel bilgilerini alabilirsiniz.

## Yaygın Sorunlar ve Çözümler
- **Temel MS Project'te görünmüyor:** Görevi ekledikten **sonra** `project.setBaseline(BaselineType.Baseline)` çağırdığınızdan emin olun.  
- **`getBaselines()` üzerinde NullPointerException:** Temeli ayarlamadan önce görevin projeye eklendiğini doğrulayın.  
- **Zaman birimi uyumsuzluğu:** Özellikle özel takvimlerle çalışırken süreyi doğru biçimlendirmek için `TimeUnitType` kullanın.

## SSS'ler
### MS Project'te görev temeli nedir?
MS Project'te bir görev temeli, bir görevin başlangıç tarihi, bitiş tarihi ve süresi dahil olmak üzere ilk planlanan takviminin bir anlık görüntüsüdür.

### Görev temellerini yönetmek neden önemlidir?
Görev temellerini yönetmek, planlanan takvimi projenin gerçek ilerlemesiyle karşılaştırmaya yardımcı olur ve daha iyi izleme ve karar‑alma süreçlerini kolaylaştırır.

### Bir görev temeli ayarlandıktan sonra değiştirilebilir mi?
Evet, MS Project'te görev temellerini proje planındaki değişiklikleri yansıtacak şekilde değiştirebilirsiniz. Ancak, orijinal temelden sapmaları belgelemek önemlidir.

### Aspose.Tasks diğer proje yönetimi işlevlerini destekliyor mu?
Evet, Aspose.Tasks görev zamanlaması, kaynak tahsisi ve Gantt şeması oluşturma gibi proje yönetimi için geniş bir özellik yelpazesi sunar.

### Aspose.Tasks için desteği nereden bulabilirim?
Aspose.Tasks desteğini, sorular sorabileceğiniz ve diğer kullanıcılarla etkileşimde bulunabileceğiniz [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) adresinde bulabilirsiniz.

## Ek Sıkça Sorulan Sorular
**S: Her görev için ayrı ayrı `setBaseline` çağırmam gerekiyor mu?**  
C: Hayır. `project.setBaseline(BaselineType.Baseline)` çağırmak, projedeki tüm görevler için temeli bir kerede kaydeder.

**S: Belirli bir görev için ara temel nasıl ayarlanır?**  
C: Görevin takvimini güncelledikten sonra `project.setBaseline(BaselineType.Baseline1)` (veya Baseline2‑Baseline10) kullanın.

**S: Temel verilerini CSV'ye dışa aktarmak mümkün mü?**  
C: Evet. `task.getBaselines()` üzerinde döngü yaparak istenen alanları standart Java I/O kullanarak bir CSV dosyasına yazabilirsiniz.

**S: Zaten temel içeren mevcut bir .mpp dosyasını okuyabilir miyim?**  
C: Kesinlikle. Dosyayı `new Project("myproject.mpp")` ile yükleyin ve ardından yukarıda gösterildiği gibi her görevin temelini erişin.

**S: Aspose.Tasks çok‑proje dosyalarını destekliyor mu?**  
C: Aspose.Tasks tek‑proje .mpp dosyalarıyla çalışır. Çok‑proje senaryoları için projeleri programlı olarak birleştirmeniz gerekir.

**Son Güncelleme:** 2026-01-23  
**Test Edilen Sürüm:** Aspose.Tasks for Java 24.12  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}