---
date: 2026-09-20
description: Aspose.Tasks for Java kullanarak proje görev bağımlılıklarını nasıl yöneteceğinizi
  öğrenin. Bu kılavuz, önceki bağlantıları eklemeyi, görev adlarını yazdırmayı ve
  görev bağımlılıklarını verimli bir şekilde ayarlamayı gösterir.
keywords:
- project task dependencies
- how to add predecessor
- java project management
- manage task dependencies
- print task names
lastmod: 2026-09-20
linktitle: Aspose.Tasks for Java ile proje görev bağımlılıklarını yönetin
og_description: Aspose.Tasks for Java kullanarak proje görev bağımlılıklarını nasıl
  yöneteceğinizi öğrenin. Bu kılavuz, önceki bağlantıları eklemeyi, görev adlarını
  yazdırmayı ve görev bağımlılıklarını verimli bir şekilde ayarlamayı gösterir.
og_image_alt: Guide showing how to manage project task dependencies with Aspose.Tasks
  Java API
og_title: Aspose.Tasks for Java ile proje görev bağımlılıklarını yönetin
schemas:
- author: Aspose
  dateModified: '2026-09-20'
  description: Learn how to manage project task dependencies using Aspose.Tasks for
    Java. This guide shows you how to add predecessor links, print task names, and
    set task dependencies efficiently.
  headline: Manage project task dependencies via Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to manage project task dependencies using Aspose.Tasks for
    Java. This guide shows you how to add predecessor links, print task names, and
    set task dependencies efficiently.
  name: Manage project task dependencies via Aspose.Tasks for Java
  steps:
  - name: initialize the project object
    text: Create a new instance of the `Project` class and provide the path to your
      project file (e.g., `"project.mpp"`).
  - name: access task links
    text: Retrieve all task links from the project using the `getTaskLinks()` method.
  - name: iterate through task links
    text: Use a loop to iterate through each task link in the collection and print
      information about the predecessor and successor tasks.
  - name: add a new predecessor link (optional)
    text: If you need to create a new dependency, instantiate a `TaskLink`, set its
      `PredecessorTaskUid`, `SuccessorTaskUid`, and `LinkType`, then add it to the
      project's link collection. Repeat these steps as needed for your specific project
      requirements.
  type: HowTo
- questions:
  - answer: Yes, simply add the Aspose.Tasks JAR to your classpath or Maven/Gradle
      dependencies.
    question: Can I use Aspose.Tasks for Java in my existing Java project?
  - answer: Yes, it supports MPP, XML, CSV, and more than 30 additional formats.
    question: Is Aspose.Tasks compatible with different project file formats?
  - answer: Obtain a temporary license from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community support and discussions.
    question: Where can I find additional support for Aspose.Tasks?
  - answer: Yes, download a free trial from the [Aspose free trial page](https://releases.aspose.com/).
    question: Can I download a free trial of Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- project task dependencies
- Aspose.Tasks
- Java project management
title: Aspose.Tasks for Java ile proje görev bağımlılıklarını yönetin
url: /tr/java/task-links/predecessor-successor-tasks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projelerde görev bağımlılıklarını Aspose.Tasks for Java ile yönetin

## Giriş
Proje görev bağımlılıkları, gerçekçi bir takvimin omurgasını oluşturur ve hangi işin diğerine başlamadan önce tamamlanması gerektiğini modellemenizi sağlar. Bu öğreticide, Aspose.Tasks for Java ile **proje görev bağımlılıklarını** nasıl yöneteceğinizi, öncül bağlantılarını nasıl ekleyeceğinizi, görev adlarını nasıl yazdıracağınızı ve görev bağımlılıklarını programlı olarak nasıl ayarlayacağınızı öğreneceksiniz.

## Hızlı cevaplar
- **İlk adım nedir?** MPP dosyanızı bir `Project` nesnesine yükleyin.  
- **Bir öncül nasıl eklenir?** Bir `TaskLink` oluşturun ve onun `PredecessorTaskUid` ve `SuccessorTaskUid` özelliklerini ayarlayın.  
- **Tüm bağlantıları listeleyebilir misiniz?** `project.getTaskLinks()` metodunu kullanın ve koleksiyon üzerinde döngü yapın.  
- **Bir lisansa ihtiyacım var mı?** Değerlendirme için geçici bir lisans yeterlidir; üretim için tam lisans gereklidir.  
- **Hangi Java sürümü destekleniyor?** Java 8 veya üzeri.

## Proje görev bağımlılıkları nedir?
Proje görev bağımlılıkları, iki görev arasındaki mantıksal ilişkiyi tanımlar; örneğin Bitiş‑Başlangıç (Finish‑to‑Start) veya Başlangıç‑Başlangıç (Start‑to‑Start) gibi ve işin hangi sırayla yapılması gerektiğini belirler. Bu bağlantılar kurulduğunda, takvim otomatik olarak gerçek dünya kısıtlamalarına uyar, çakışan aktiviteleri önler ve sonraki görevlerin yalnızca ön koşulları karşılandığında başlamasını sağlar.

## Neden Aspose.Tasks for Java kullanmalısınız?
Aspose.Tasks for Java, en son Microsoft Project sürümleri de dahil olmak üzere otuzdan fazla proje dosya formatını destekler ve belgeyi belleğe tamamen yüklemeden iki gigabayta kadar dosyaları işleyebilir. Bu yüksek performanslı özellik, büyük takvimleri manipüle etmenizi, raporlar oluşturmanızı ve toplu güncellemeleri verimli bir şekilde gerçekleştirmenizi sağlar; bu da onu kurumsal ölçekli proje yönetimi çözümleri için ideal kılar.

## Önkoşullar
- Java Geliştirme Ortamı: Makinenizde Java 8 veya daha yeni bir sürüm yüklü.  
- Aspose.Tasks for Java Kütüphanesi: Aspose.Tasks kütüphanesini [Aspose.Tasks for Java indirme sayfasından](https://releases.aspose.com/tasks/java/) indirin ve kurun.  
- Entegre Geliştirme Ortamı (IDE): Eclipse, IntelliJ IDEA veya tercih ettiğiniz herhangi bir Java uyumlu IDE.

## Paketleri içe aktar
Proje manipülasyonunu sağlayan temel sınıfları içe aktarmanız gerekir.

`Project` sınıfı, Microsoft Project dosyalarını yüklemek ve kaydetmek için giriş noktasıdır.  
`TaskLink` sınıfı ise iki görev arasındaki bağımlılığı temsil eder.

## İki görev arasında bir öncül bağlantısı nasıl eklenir?
Bir `TaskLink` örneği oluşturun, öncül görevin UID'sini ve ardıl görevin UID'sini atayın, Finish‑to‑Start gibi uygun `TaskLinkType`'ı seçin ve ardından bağlantıyı projenin görev bağlantı koleksiyonuna ekleyin. Eklendikten sonra takvim, yeni bağımlılık ilişkisini hemen yansıtır.

### Adım 1: proje nesnesini başlat
`Project` sınıfının yeni bir örneğini oluşturun ve proje dosyanızın yolunu sağlayın (ör. `"project.mpp"`).

```java
import com.aspose.tasks.*;
```

### Adım 2: görev bağlantılarına eriş
Projeden tüm görev bağlantılarını `getTaskLinks()` metodu ile alın.

```java
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "project.mpp");
```

### Adım 3: görev bağlantıları arasında döngü yap
Koleksiyondaki her görev bağlantısı üzerinde döngü yapmak ve öncül ve ardıl görevler hakkında bilgi yazdırmak için bir döngü kullanın.

```java
TaskLinkCollection allinks = project.getTaskLinks();
```

### Adım 4: yeni bir öncül bağlantısı ekle (isteğe bağlı)
Yeni bir bağımlılık oluşturmanız gerekiyorsa, bir `TaskLink` örneği oluşturun, `PredecessorTaskUid`, `SuccessorTaskUid` ve `LinkType` özelliklerini ayarlayın, ardından projeye bağlantı koleksiyonuna ekleyin.

```java
for (TaskLink tsklnk : allinks) {
    System.out.println("Predecessor " + tsklnk.getPredTask().get(Tsk.NAME));
    System.out.println("Successor " + tsklnk.getSuccTask().get(Tsk.NAME));
}
```

Bu adımları, belirli proje gereksinimleriniz doğrultusunda gerektiği kadar tekrarlayın.

## Yaygın sorunlar ve çözümler
- **Bağlantı ekledikten sonra öncül eksik** – İç grafik yenilensin diye `project.updateTaskLinks()` (veya kaydedip yeniden yükleyin) metodunu çağırdığınızdan emin olun.  
- **Büyük dosyalarda performans yavaşlaması** – Bellek yükünü azaltmak için toplu işlemlerden önce `project.setReadOnly(true)` kullanın.  
- **Yanlış bağlantı türü** – Takvim mantığınıza uygun doğru `TaskLinkType` enum değerini (ör. `FinishToStart`) kullandığınızdan emin olun.

## Sıkça sorulan sorular

**Q:** Aspose.Tasks for Java'ı mevcut Java projenizde kullanabilir miyim?  
**A:** Evet, Aspose.Tasks JAR dosyasını sınıf yolunuza veya Maven/Gradle bağımlılıklarınıza eklemeniz yeterlidir.

**Q:** Aspose.Tasks farklı proje dosya formatlarıyla uyumlu mu?  
**A:** Evet, MPP, XML, CSV ve 30'dan fazla ek formatı destekler.

**Q:** Aspose.Tasks için geçici bir lisans nasıl alabilirim?  
**A:** [Geçici lisans sayfasından](https://purchase.aspose.com/temporary-license/) geçici bir lisans edinin.

**Q:** Aspose.Tasks için ek destek nereden bulunabilir?  
**A:** Topluluk desteği ve tartışmalar için [Aspose.Tasks forumunu](https://forum.aspose.com/c/tasks/15) ziyaret edin.

**Q:** Aspose.Tasks for Java için ücretsiz deneme sürümünü indirebilir miyim?  
**A:** Evet, [Aspose ücretsiz deneme sayfasından](https://releases.aspose.com/) ücretsiz deneme sürümünü indirin.

---

**Son Güncelleme:** 2026-09-20  
**Test Edilen:** Aspose.Tasks for Java 24.12  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Aspose.Tasks'te Proje Yönetimi Görev Bağımlılıkları Oluşturma](/tasks/java/task-links/create-task-link/)
- [Aspose.Tasks'te Proje Başlangıç Tarihini Ayarlama ve Üst-Alt Görevleri Yönetme](/tasks/java/task-properties/parent-child-tasks/)
- [Aspose.Tasks for Java ile Görev Önceliklerini Okuma ve Ayarlama](/tasks/java/task-properties/handle-priorities/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}