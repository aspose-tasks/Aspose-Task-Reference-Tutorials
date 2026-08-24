---
date: 2026-08-24
description: Aspose.Tasks for Java kullanarak MS Project'te kaynak eklemeyi, standart
  ücreti ve diğer kaynak özelliklerini ayarlamayı öğrenin ve kaynakları verimli bir
  şekilde yönetin.
keywords:
- add resource ms project
- set resource rate
- manage ms project resources
- create ms project file
lastmod: 2026-08-24
linktitle: Aspose.Tasks'te Kaynak Özelliklerini Ayarlama
og_description: Aspose.Tasks for Java kullanarak MS Project'e kaynak ekleyin ve standart
  ücreti ayarlayın. Gereksinimleri, adım adım kodu ve sorun giderme ipuçlarını bu
  kısa rehberde öğrenin.
og_image_alt: Screenshot of Aspose.Tasks Java code setting resource rates
og_title: Aspose.Tasks (Java) ile MS Project'e kaynak ekleyin ve ücreti ayarlayın
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to add resource ms project, set standard rate and other resource
    properties in MS Project using Aspose.Tasks for Java, and manage resources efficiently.
  headline: How to add resource ms project with Aspose.Tasks
  type: TechArticle
- description: Learn how to add resource ms project, set standard rate and other resource
    properties in MS Project using Aspose.Tasks for Java, and manage resources efficiently.
  name: How to add resource ms project with Aspose.Tasks
  steps:
  - name: Install JDK 8 or newer. You can download it from the [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
    text: Install JDK 8 or newer. You can download it from the [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
  - name: Choose an IDE such as IntelliJ IDEA, Eclipse, or NetBeans and configure
      it for Java development.
    text: Choose an IDE such as IntelliJ IDEA, Eclipse, or NetBeans and configure
      it for Java development.
  - name: Download the latest Aspose.Tasks for Java package from the [download page](https://releases.aspose.com/tasks/java/).
    text: Download the latest Aspose.Tasks for Java package from the [download page](https://releases.aspose.com/tasks/java/).
  - name: Add the JAR files to your project’s classpath or declare the Maven/Gradle
      dependency as shown in the product documentation.
    text: Add the JAR files to your project’s classpath or declare the Maven/Gradle
      dependency as shown in the product documentation.
  type: HowTo
- questions:
  - answer: Yes, it supports all major Project formats, including large files with
      thousands of tasks and resources, preserving every field without data loss.
    question: Can Aspose.Tasks for Java handle complex MS Project files?
  - answer: Yes, you can access a free trial of Aspose.Tasks for Java from the [Aspose.Tasks
      free trial page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: You can seek assistance on the [support forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I get support for Aspose.Tasks for Java?
  - answer: A temporary license is available from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for evaluation?
  - answer: Purchase a full license from the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase a licensed version?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose tasks
- java project automation
- ms project resources
- resource rate
title: Aspose.Tasks ile MS Project'e kaynak ekleme
url: /tr/java/resource-management/set-resource-properties/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'te kaynak MS Project ekleme ve oran ayarlama

## Giriş
Eğer Microsoft Project dosyalarını okuma veya yazma ihtiyacı olan Java uygulamaları geliştiriyorsanız, **kaynak MS projesi ekleme** ve standart oranını yapılandırmak rutin ama önemli bir görevdir. Bu rehberde `Project` nesnesi nasıl oluşturulur, bir kaynak nasıl eklenir ve Aspose.Tasks for Java kullanarak standart ve fazla mesai oranları nasıl ayarlanır göreceksiniz. Sonunda maliyet hesaplamalarını otomatikleştirebilecek ve proje takvimlerinizi Microsoft Project yüklü olmadan güncel tutabileceksiniz.

## Hızlı cevaplar
- **Bir Project dosyasını temsil eden sınıf nedir?** `Project`
- **Yeni bir kaynak ekleyen çağrı hangisidir?** `project.getResources().add()`
- **Standart oranı nasıl ayarlarsınız?** `rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(...))`
- **Üretim kullanımında lisans gerekli mi?** Evet, geçerli bir Aspose.Tasks lisansı yüklemelisiniz.
- **Hangi Java sürümleri desteklenir?** Java 8 ve sonrası (Java 17+ önerilir).

## “set standard rate” nedir?
*set standard rate* işlemi, bir kaynağa varsayılan saatlik maliyet atar. Bu oran, proje yöneticileri tarafından işçilik giderlerini hesaplamak, maliyet raporları oluşturmak ve bütçeleri tahmin etmek için kullanılır; böylece maliyet hesaplamaları, proje yaşam döngüsü boyunca her kaynak tarafından gerçekleştirilen işin beklenen fiyatını yansıtır.

## Aspose.Tasks ile oranları neden ayarlamalısınız?
Aspose.Tasks, **50'den fazla giriş ve çıkış formatını** işleyebilir, MPP, MPX, XML ve Primavera dosyaları dahil, ve tüm dosyayı belleğe yüklemeden çok sayfalı projeleri yönetir. Bu, Windows, Linux veya macOS sunucularında yüksek verimli toplu iş işleme imkanı sağlar ve tipik otomasyon senaryolarında manuel çabayı %90'a kadar azaltır.

## Önkoşullar
Başlamadan önce, aşağıdaki öğelerin hazır olduğundan emin olun:

### Java geliştirme ortamı kurulumu
1. JDK 8 veya daha yenisini kurun. [Oracle web sitesinden](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) indirebilirsiniz.  
2. IntelliJ IDEA, Eclipse veya NetBeans gibi bir IDE seçin ve Java geliştirme için yapılandırın.

### Aspose.Tasks for Java kurulumu
1. En son Aspose.Tasks for Java paketini [indirme sayfasından](https://releases.aspose.com/tasks/java/) indirin.  
2. JAR dosyalarını projenizin sınıf yoluna ekleyin veya ürün belgelerinde gösterildiği gibi Maven/Gradle bağımlılığını deklar edin.

## Paketleri içe aktar
Gerekli temel Aspose.Tasks sınıflarını içe aktarın. Bu adım, daha sonra kullanılacak `Project`, `Resource` ve `Rsc` tiplerine erişim sağlar.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import java.math.BigDecimal;
```

## Adım 1: bir proje nesnesi oluşturma
`Project` sınıfı, bellekte tüm bir MS Project dosyasını temsil eden üst‑seviye nesnedir. Bir örneğini oluşturmak, görevler, kaynaklar ve diğer verilerle doldurabileceğiniz boş bir proje yaratır.

```java
Project project = new Project();
```

## Adım 2: bir kaynak ekleme (add resource ms project)
`Resource` sınıfı, bir kişi, ekipman veya malzeme gibi tek bir proje kaynağını modeller. `project.getResources().add()` ile bir kaynak eklemek, özellik yapılandırmasına hazır, null olmayan bir `Resource` örneği döndürür.

```java
Resource rsc = project.getResources().add("Rsc");
```

## Adım 3: kaynak özelliklerini ayarlama (how to set rates)
`Rsc` enumu, `STANDARD_RATE` ve `OVERTIME_RATE` gibi kaynak alanları için sabitler içerir.  
Uygun `Rsc` enum değerleriyle `Resource` nesnesi üzerinde `set` metodunu çağırarak standart ve fazla mesai oranlarını ayarlarsınız. Oranlar, parasal hassasiyeti korumak için `BigDecimal` olarak saklanır.

```java
// Set standard rate for the resource
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(15));
// Set overtime rate for the resource
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(20));
```

## Yaygın sorunlar ve çözümler
| Issue | Why it happens | Fix |
|-------|----------------|-----|
| `set` çağrılırken NullPointerException | Kaynak doğru eklenmedi. | `project.getResources().add()`'ın null olmayan bir `Resource` döndürdüğünden emin olun. |
| Kaydedilen dosyada oranlar 0 olarak görünüyor | `int` yerine `BigDecimal` kullanılıyor. | Parasal değerler için her zaman `BigDecimal.valueOf()` kullanın. |
| Lisans bulunamadı | `Project` oluşturulmadan önce lisans dosyası yüklenmedi. | Program başlangıcında lisansı yükleyin (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Sonuç
Artık **kaynak ms projesi ekleme**, bir `Project` nesnesi oluşturma ve Aspose.Tasks for Java kullanarak **standart ve fazla mesai oranlarını ayarlama** konusunda bilgi sahibisiniz. Bu yetenek, maliyet hesaplamalarını otomatikleştirmenizi, özel raporlar oluşturmanızı ve herhangi bir Java uygulamasından MS Project kaynaklarını tam olarak yönetmenizi sağlar.

## Sıkça Sorulan Sorular
**Q:** Aspose.Tasks for Java karmaşık MS Project dosyalarını işleyebilir mi?  
**A:** Evet, binlerce görev ve kaynak içeren büyük dosyalar dahil olmak üzere tüm ana Project formatlarını destekler, her alanı veri kaybı olmadan korur.

**Q:** Ücretsiz deneme mevcut mu?  
**A:** Evet, Aspose.Tasks for Java için ücretsiz denemeye [Aspose.Tasks ücretsiz deneme sayfasından](https://releases.aspose.com/) ulaşabilirsiniz.

**Q:** Aspose.Tasks for Java için desteği nereden alabilirim?  
**A:** [destek forumundan](https://forum.aspose.com/c/tasks/15) yardım isteyebilirsiniz.

**Q:** Değerlendirme için geçici lisansı nasıl edinebilirim?  
**A:** Geçici lisans, [geçici lisans sayfasından](https://purchase.aspose.com/temporary-license/) temin edilebilir.

**Q:** Lisanslı bir sürümü nereden satın alabilirim?  
**A:** Tam lisansı [satın alma sayfasından](https://purchase.aspose.com/buy) satın alabilirsiniz.

---

**Son Güncelleme:** 2026-08-24  
**Test Edilen:** Aspose.Tasks for Java 24.12 (yazım zamanındaki en son sürüm)  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Kaynakları Oluşturma – Aspose.Tasks for Java ile Kaynak Yönetimi](/tasks/java/resource-management/)
- [Aspose.Tasks for Java ile projeye kaynak ekleme](/tasks/java/resource-management/create-resources/)
- [Projeye Kaynak Ekleme ve Aspose.Tasks'te Dengeleme Gecikme Özelliklerini Yönetme](/tasks/java/resource-assignments/leveling-delay-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}