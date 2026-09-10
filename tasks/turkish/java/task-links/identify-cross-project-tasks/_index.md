---
date: 2026-09-09
description: Aspose.Tasks for Java kullanarak çapraz proje görevlerini nasıl tanımlayacağınızı
  öğrenin. Sorunsuz entegrasyonu, verimli yönetimi ve gerçek dünya örneklerini keşfedin.
keywords:
- identify cross project tasks
- set document directory
- get task id java
lastmod: 2026-09-09
linktitle: Aspose.Tasks'te çapraz proje görevlerini tanımlama
og_description: Aspose.Tasks for Java'da çapraz proje görevlerini tanımlayın. Belge
  dizinini nasıl ayarlayacağınızı, görev kimliklerini nasıl alacağınızı ve bağlı projeleri
  verimli bir şekilde nasıl yöneteceğinizi öğrenin.
og_image_alt: Screenshot of Aspose.Tasks Java API showing cross‑project task identification
og_title: Aspose.Tasks'te çapraz proje görevlerini tanımlama – Java rehberi
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to identify cross project tasks using Aspose.Tasks for Java.
    Explore seamless integration, efficient management, and real‑world examples.
  headline: Identify cross project tasks in Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks supports multiple languages, including Java, .NET, and
      more.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Refer to the documentation **[here](https://reference.aspose.com/tasks/java/)**.
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Yes, you can get a free trial **[here](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: Obtain a temporary license **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I get temporary licensing for Aspose.Tasks?
  - answer: Visit the Aspose.Tasks support forum **[here](https://forum.aspose.com/c/tasks/15)**.
    question: Need help or have specific questions?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project management
- cross project tasks
- task linking
title: Aspose.Tasks'te çapraz proje görevlerini tanımlama
url: /tr/java/task-links/identify-cross-project-tasks/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'te çapraz proje görevlerini tanımlama

## Giriş
Bu öğreticide, Aspose.Tasks for Java ile **çapraz proje görevlerini nasıl tanımlayacağınızı** öğreneceksiniz. Bağımlı takvimlerden oluşan bir portföy yönetiyor ya da dış bağımlılıkları denetlemeniz gerekiyorsa, aşağıdaki adımlar diğer proje dosyalarına referans veren görevleri bulmanızı, kimliklerini almanızı ve programlı olarak bunlarla çalışmanızı gösterir.

## Hızlı cevaplar
- **“çapraz proje görevlerini tanımlama” ne anlama geliyor?** Başka bir proje dosyasındaki görevlere referans veren veya onlara bağımlı olan görevleri bulmak demektir.  
- **Görev kimliğini (ID) hangi yöntem yazdırır?** Görev kimliğini yazdırmak için `externalTask.get(Tsk.ID)` kullanın.  
- **Belge dizinini nasıl ayarlarım?** Klasör yolunu bir `String` değişkenine (ör. `dataDir`) atayın.  
- **UID ile bir görevi hangi özellik getirir?** `getChildren().getByUid(yourUid)` çağırın.  
- **Üretim ortamında lisansa ihtiyacım var mı?** Evet, ticari dağıtımlar için geçerli bir Aspose.Tasks lisansı gereklidir.

## “Çapraz proje görevlerini tanımlama” nedir?
Çapraz‑proje görevlerini tanımlamak, birden fazla Microsoft Project dosyasına yayılmış görevler arasındaki ilişkileri izlemenizi sağlar. Dış takvimlere referans veren veya onlara bağımlı olan görevleri bulduğunuzda, iş öğelerinin proje sınırları arasında nasıl etkileştiğini anlayabilir, yinelenen çabaları önleyebilir ve doğru zaman çizelgelerini koruyabilirsiniz. Bu yetenek, görevlerin paylaşıldığı veya dış takvimlere bağımlı olduğu büyük ölçekli portföyler için hayati öneme sahiptir.

## Neden Aspose.Tasks for Java kullanmalı?
Aspose.Tasks for Java, **50+ giriş ve çıkış formatını** (MPP, MPX, XML ve CSV dahil) destekler ve **10.000'e kadar görev** içeren projeleri tüm dosyayı belleğe yüklemeden işleyebilir. Kütüphane, herhangi bir JVM‑uyumlu platformda çalışır, Microsoft Project kurulumuna ihtiyaç duymaz ve ID'ler, UID'ler, dış ID'ler ve bağlama meta verileri için tam API erişimi sunar.

## Önkoşullar
- Çalışan bir Java geliştirme ortamı (JDK 8 veya üzeri).  
- Aspose.Tasks for Java yüklü. **[buradan](https://releases.aspose.com/tasks/java/)** indirebilirsiniz.  
- Üretimde kodu çalıştırmayı planlıyorsanız geçerli bir Aspose.Tasks lisans dosyası.

## Paketleri içe aktar
`Project` sınıfı bir Microsoft Project dosyasını, `Task` bireysel bir görevi ve `Tsk` görev alanı sabitlerini temsil eder.  
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
```

## Adım 1: belge dizinini ayarla
`dataDir` dizesi, `.mpp` dosyalarınızı içeren klasörün yolunu tutar.  
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

## Adım 2: dış projeyi yükle
`Project externalProject` belirtilen dış proje dosyasını inceleme için yükler.  
```java
Project externalProject = new Project(dataDir + "External.mpp");
```

## Adım 3: dış görevi UID ile al
`externalProject.getChildren().getByUid(uid)` dış projenin görev koleksiyonundan benzersiz kimliği kullanarak bir görev getirir.  
```java
Task externalTask = externalProject.getRootTask().getChildren().getByUid(1);
```

## Adım 4: görev kimliğini (ID) yazdır (ana kullanım durumu)
`externalTask.get(Tsk.ID)` verilen görev için Aspose.Tasks tarafından atanan iç ID'yi döndürür.  
```java
System.out.println(externalTask.get(Tsk.ID).toString());
```

## Adım 5: orijinal (dış) görev kimliğini yazdır
`externalTask.get(Tsk.ExternalID)` görevlerin kaynak proje dosyasında tanımlanan orijinal kimliğini alır.  
```java
System.out.println(externalTask.get(Tsk.EXTERNAL_ID).toString());
```

Projeler arasında izlemeniz gereken ek görevler için yukarıdaki adımları tekrarlayın.

## Yaygın sorunlar ve ipuçları
- **Yol hataları** – `dataDir`'in uygun dosya ayırıcıyla (`/` veya `\\`) bittiğinden emin olun.  
- **UID bulunamadı** – UID'nin dış projede mevcut olduğunu doğrulayın; mevcut UID'leri listelemek için `externalProject.getRootTask().getChildren().size()` kullanın.  
- **Lisans istisnaları** – Eksik veya geçersiz bir lisans çalışma zamanında lisans istisnası oluşturur.  
- **Büyük projeler** – 5.000'den fazla görev içeren projeler için, veri akışı sağlamak ve bellek tüketimini azaltmak amacıyla `LoadOptions` bayrağıyla `ProjectReader` kullanmayı düşünün.

## Sıkça Sorulan Sorular

**S: Aspose.Tasks'i diğer programlama dilleriyle kullanabilir miyim?**  
C: Evet, Aspose.Tasks Java, .NET ve daha fazlası dahil olmak üzere birden çok dili destekler.

**S: Aspose.Tasks for Java için ayrıntılı belgeleri nerede bulabilirim?**  
C: Belgeleri **[buradan](https://reference.aspose.com/tasks/java/)** inceleyin.

**S: Aspose.Tasks for Java için ücretsiz deneme mevcut mu?**  
C: Evet, ücretsiz denemeyi **[buradan](https://releases.aspose.com/)** alabilirsiniz.

**S: Aspose.Tasks için geçici lisans nasıl alabilirim?**  
C: Geçici bir lisansı **[buradan](https://purchase.aspose.com/temporary-license/)** edinebilirsiniz.

**S: Yardıma mı ihtiyacınız var ya da belirli sorularınız mı var?**  
C: Aspose.Tasks destek forumunu **[buradan](https://forum.aspose.com/c/tasks/15)** ziyaret edin.

---

**Son Güncelleme:** 2026-09-09  
**Test Edilen:** Aspose.Tasks for Java 24.11 (yazım anındaki en son sürüm)  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Aspose.Tasks'te Proje Yönetimi Görev Bağımlılıkları Oluşturma](/tasks/java/task-links/create-task-link/)
- [Aspose.Tasks'te Proje Başlangıç Tarihini Ayarlama ve Üst-Alt Görevleri Yönetme](/tasks/java/task-properties/parent-child-tasks/)
- [MPP Projesi Java Oluşturma – Aspose.Tasks ile Görev İlerlemesini Değiştirme](/tasks/java/task-properties/change-progress/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}