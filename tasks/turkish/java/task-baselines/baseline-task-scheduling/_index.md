---
date: 2026-08-29
description: Aspose.Tasks for Java kullanarak temel çizgi verilerini okuma ve görevleri
  zamanlama konusunda bilgi edinin, böylece planlanan ve gerçekleşen ilerlemeyi verimli
  bir şekilde karşılaştırabilirsiniz.
keywords:
- how to read baseline
- how to set baseline
- compare planned vs actual
lastmod: 2026-08-29
linktitle: Aspose.Tasks'te Temel Çizgi Görev Zamanlaması
og_description: Aspose.Tasks for Java kullanarak temel çizgi verilerini okuma ve görevleri
  zamanlama konusunda bilgi edinin, planlanan ve gerçekleşen ilerlemeyi kesin olarak
  karşılaştırmanızı sağlar.
og_image_alt: Tutorial showing how to read baseline and schedule tasks with Aspose.Tasks
  Java API
og_title: Aspose.Tasks ile temel çizgiyi okuma ve görevleri zamanlama
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to read baseline data and schedule tasks using Aspose.Tasks
    for Java, so you can compare planned vs actual progress efficiently.
  headline: How to read baseline and schedule tasks with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Instantiate the `Project` class (`Project project = new Project();`).
      This creates a fresh project file ready for tasks and baselines.
    question: How do I create a new project instance in Aspose.Tasks?
  - answer: '`BaselineType.Baseline` refers to the primary baseline (Baseline 1).
      Aspose.Tasks also supports Baseline 2‑10 for additional snapshots.'
    question: What is the difference between `BaselineType.Baseline` and other baseline
      types?
  - answer: Yes, you can iterate over `TaskBaseline` objects and write the values
      to a CSV file using standard Java I/O.
    question: Can I export the baseline data to Excel or CSV?
  - answer: Setting a baseline captures the current dates but does not modify the
      task’s active schedule. You can still adjust start/finish dates after the baseline
      is set.
    question: Does setting a baseline affect existing task dates?
  - answer: Absolutely. Retrieve each baseline via `task.getBaselines().get(index)`
      and compare their `Start`, `Finish`, and `Duration` properties.
    question: Is it possible to compare multiple baselines programmatically?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- project baseline
- Aspose.Tasks
- Java project management
title: Aspose.Tasks ile temel çizgiyi okuma ve görevleri zamanlama
url: /tr/java/task-baselines/baseline-task-scheduling/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks ile temel çizgiyi okuma ve görevleri zamanlama

Bu rehberde Aspose.Tasks for Java kullanarak **temel çizgiyi okuma** bilgisini ve görevleri programlı olarak zamanlamayı keşfedeceksiniz. Eğitim sonunda, orijinal proje planını yakalayabilecek, gerçek ilerlemeyle karşılaştırabilecek ve sapma raporları oluşturabileceksiniz — Microsoft Project yüklü olmadan.

## Proje yönetimi temel çizgisine giriş

Bir **proje yönetimi temel çizgisi** yönetmek, etkili proje yönetiminin temel taşlarından biridir. Orijinal planı yakalamanızı ve daha sonra **planlanan ile gerçek ilerlemeyi** karşılaştırmanızı sağlar, böylece sapmaları erken fark edebilirsiniz. Bu eğitimde, Aspose.Tasks for Java kullanarak görev temel çizgilerini nasıl zamanlayacağınızı adım adım gösterecek, **proje temel çizgilerini** güvenle yönetmeniz ve projelerinizi yolunda tutmanız için araçları sunacağız.

## Hızlı cevaplar
- **Proje yönetimi temel çizgisi neyi temsil eder?**  
  Proje başlangıcında onaylanmış takvimi, maliyeti ve kapsamı kaydeder ve sapma analizleri için bir referans sağlar.  
- **Java'da temel çizgi zamanlamasını hangi kütüphane yönetir?**  
  Aspose.Tasks for Java, 45+ giriş ve çıkış formatını destekleyen saf‑Java API'si sunar ve 100 000'e kadar görev içeren projeleri işleyebilir.  
- **Kodu çalıştırmak için lisansa ihtiyacım var mı?**  
  Test için ücretsiz deneme sürümü yeterlidir; üretim kullanımı için ticari lisans gereklidir.  
- **Ana önkoşullar nelerdir?**  
  Java Development Kit (JDK) 11+ ve Aspose.Tasks for Java kütüphanesi.  
- **Temel çizgi tarihlerini ayarladıktan sonra görüntüleyebilir miyim?**  
  Evet—başlangıç, bitiş ve süre değerlerini okumak için `TaskBaseline` nesnesini kullanın.

## Proje yönetimi temel çizgisi nedir?
Bir proje yönetimi temel çizgisi, yürütmeye başlandığında onaylanmış takvimi, bütçeyi ve kapsamı kaydeder. Performansı ölçmek ve proje yaşam döngüsü boyunca sapmaları belirlemek için bir referans noktası olarak hizmet eder. Planlanan başlangıç ve bitiş tarihlerini, toplam maliyeti ve kapsam detaylarını içerir ve gelecekteki karşılaştırmalar için kapsamlı bir anlık görüntü sağlar.

## Temel çizgi zamanlaması için neden Aspose.Tasks kullanılmalı?
Aspose.Tasks, Microsoft Project yüklü olmadan çalışan saf‑Java API'si sunar. **45+ giriş ve çıkış formatını** destekler, bellek‑verimli modda **100 000'e kadar görev** işleyebilir ve temel çizgi verilerini okuma‑yazma için yerleşik yöntemler sağlar—otomatik raporlama ve entegrasyonu kolaylaştırır.

## Önkoşullar
- **Java Development Kit (JDK)** – JDK 11 veya daha yeni bir sürüm kurun. İndirmek için [website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) adresini ziyaret edebilirsiniz.  
- **Aspose.Tasks for Java library** – En son sürümü [download page](https://releases.aspose.com/tasks/java/) adresinden indirin ve JAR dosyasını projenizin sınıf yoluna ekleyin.

## Paketleri içe aktar
`Project`, `Task` ve `TaskBaseline` sınıfları `com.aspose.tasks` ad alanında bulunur. Kaynak dosyanızın en üst kısmına şu import ifadelerini ekleyin:

`Project` sınıfı, bellek içinde tek bir proje dosyasını temsil eden Aspose.Tasks'in üst‑seviye nesnesidir. Görevlere, kaynaklara ve temel çizgi koleksiyonlarına erişim sağlar.

## Temel çizgiyi nasıl okursunuz?
Projeyi yükleyin, ardından her görev için `TaskBaseline` koleksiyonunu sorgulayın. `TaskBaseline` nesnesi, `setBaseline` çağrısı yapıldığında yakalanan temel çizgi başlangıç, bitiş ve süre değerlerini döndürür. Bu doğrudan yaklaşım, XML veya ikili dosyaları ayrıştırmadan temel çizgi değerlerini okumanızı sağlar.

## Adım 1: yeni bir proje örneği oluşturun
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
```

## Adım 2: bir görev tanımlayın ve temel çizgiyi ayarlayın
```java
Project project = new Project();
```

## Adım 3: temel çizgi bilgilerine erişin
```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## Adım 4: temel çizgi süresini gösterin
```java
TaskBaseline baseline = task.getBaselines().get(0);
```

## Adım 5: temel çizgi başlangıç tarihini gösterin
```java
System.out.println(baseline.getDuration().toString());
```

## Adım 6: temel çizgi bitiş tarihini gösterin
```java
System.out.println("Baseline Start: " + baseline.getStart());
```

## Yaygın sorunlar ve çözümler
- **Baseline not set:** Görevleri ekledikten **sonra** `project.setBaseline(BaselineType.Baseline)` çağırdığınızdan emin olun; aksi takdirde temel çizgi koleksiyonu boş olur.  
- **Null values:** `task.getBaselines()` boş bir liste döndürürse, temel çizgi ayarlamadan önce görevin proje hiyerarşisine eklendiğini doğrulayın.  
- **Date format:** `getStart()` ve `getFinish()` metodları `java.util.Date` nesneleri döndürür. Özel bir görüntüleme biçimi gerekiyorsa `SimpleDateFormat` kullanın.

## Sıkça sorulan sorular

**S: Aspose.Tasks'te yeni bir proje örneği nasıl oluştururum?**  
C: `Project` sınıfını örnekleyin (`Project project = new Project();`). Bu, görevler ve temel çizgiler için hazır yeni bir proje dosyası oluşturur.

**S: `BaselineType.Baseline` ile diğer temel çizgi türleri arasındaki fark nedir?**  
C: `BaselineType.Baseline`, birincil temel çizgi (Baseline 1) anlamına gelir. Aspose.Tasks ayrıca ek anlık görüntüler için Baseline 2‑10'ı da destekler.

**S: Temel çizgi verilerini Excel veya CSV'ye aktarabilir miyim?**  
C: Evet, `TaskBaseline` nesneleri üzerinde döngü kurarak değerleri standart Java I/O kullanarak bir CSV dosyasına yazabilirsiniz.

**S: Bir temel çizgi ayarlamak mevcut görev tarihlerini etkiler mi?**  
C: Temel çizgi ayarlamak mevcut tarihleri yakalar ancak görevin aktif takvimini değiştirmez. Temel çizgi ayarlandıktan sonra başlangıç/bitiş tarihlerini hâlâ ayarlayabilirsiniz.

**S: Birden fazla temel çizgiyi programlı olarak karşılaştırmak mümkün mü?**  
C: Kesinlikle. `task.getBaselines().get(index)` ile her temel çizgiyi alın ve `Start`, `Finish` ve `Duration` özelliklerini karşılaştırın.

---

**Son Güncelleme:** 2026-08-29  
**Test Edilen:** Aspose.Tasks for Java 24.12  
**Yazar:** Aspose  








```java
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## İlgili Eğitimler

- [Görev Listesi Oluşturma Java – MS Project Temel Çizgisi Aspose.Tasks ile](/tasks/java/task-baselines/create-task-baseline/)
- [Aspose.Tasks for Java'da Temel Çizgi Süresini Nasıl Ayarlarsınız](/tasks/java/task-baselines/task-baseline-duration/)
- [MPP Projesi Oluşturma Java – Görev İlerlemesini Aspose.Tasks ile Değiştir](/tasks/java/task-properties/change-progress/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}