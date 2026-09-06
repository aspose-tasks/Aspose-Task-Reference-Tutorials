---
date: 2026-08-29
description: Aspose.Tasks kullanarak Microsoft Project olmadan Java'da projeye görev
  eklemeyi, görev listesi oluşturmayı ve bir temel çizgi ayarlamayı öğrenin.
keywords:
- add task to project
- how to set baseline
- how to create baseline
- how to add task
- java create ms project
lastmod: 2026-08-29
linktitle: Aspose.Tasks'te Görev Temel Çizgisi Oluşturma
og_description: Aspose.Tasks kullanarak Java'da projeye görev eklemeyi ve bir temel
  çizgi ayarlamayı öğrenin. Bu rehber, Microsoft Project'e ihtiyaç duymadan adım adım
  kod gösterir.
og_image_alt: 'Tutorial: add task to project and set baseline with Aspose.Tasks Java'
og_title: Java'da projeye görev ekleme ve bir temel çizgi ayarlama
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to add task to project in Java, create a task list, and set
    a baseline without Microsoft Project using Aspose.Tasks.
  headline: How to add task to project in Java and set a baseline
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks works independently and does not require Microsoft Project
      on the host machine.
    question: Can I use Aspose.Tasks for Java without Microsoft Project installed?
  - answer: Absolutely. The library supports Project files from 2007 through the latest
      2024 releases.
    question: Is Aspose.Tasks for Java compatible with different versions of Microsoft
      Project?
  - answer: Yes, you can add, update, and delete resources programmatically, just
      like tasks.
    question: Can I manipulate project resources using Aspose.Tasks for Java?
  - answer: Yes, you can define predecessor‑successor relationships using the `TaskLink`
      class.
    question: Does Aspose.Tasks for Java support setting task dependencies?
  - answer: Yes, you can get help via the [support forum](https://forum.aspose.com/c/tasks/15),
      where Aspose staff and the community respond to queries.
    question: Is technical support available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add task to project
- Aspose.Tasks
- Java project automation
title: Java'da projeye görev ekleme ve bir temel çizgi ayarlama
url: /tr/java/task-baselines/create-task-baseline/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java'da projeye görev ekleme ve bir temel çizgi ayarlama

## Giriş
Bu öğreticide programlı olarak **add task to project** yapacak, bir Microsoft Project görev temel çizgisi oluşturacak ve dosyayı kaydedeceksiniz—Microsoft Project'i hiç açmadan. Aspose.Tasks for Java, herhangi bir platformda çalışan saf‑Java API'si sunar ve otomatik derleme hatları, raporlama hizmetleri veya .mpp dosyalarını manipüle etmesi gereken herhangi bir sunucu‑tarafı çözüm için mükemmeldir.

## Hızlı cevaplar
- **Aspose.Tasks ne yapar?** Microsoft Project gerektirmeden Microsoft Project dosyalarını oluşturmak, okumak ve düzenlemek için bir Java API'si sağlar.  
- **Microsoft Project yüklü olması gerekiyor mu?** Hayır, kütüphane tamamen bağımsız çalışır.  
- **Hangi Java sürümü gereklidir?** JDK 8 veya üzeri.  
- **Tek bir görev için temel çizgi ayarlayabilir miyim?** Evet – yalnızca istediğiniz görevleri içeren bir listede `setBaseline` metodunu çağırın.  
- **Üretim için lisans gerekli mi?** Evet, ticari bir lisans değerlendirme sınırlamalarını kaldırır ve tüm özelliklerin kilidini açar.

## Görev temel çizgisi nedir?
Bir görev temel çizgisi, zaman çizelgesi ilk kaydedildiğinde görevin orijinal planlanan başlangıç tarihi, bitiş tarihi ve iş çabasını yakalar. Bu anlık görüntü, proje yöneticilerinin gerçek ilerleme ve maliyetleri ilk planla karşılaştırmasına ve performans analizinde sapmaları hesaplamasına olanak tanıyan bir referans noktası görevi görür.

## Java'da projeye görev eklemek için Aspose.Tasks'i neden kullanmalısınız?
Herhangi bir masaüstü kurulumuna ihtiyaç duymadan görevleri oluşturabilir, değiştirebilir ve temel çizgi ekleyebilirsiniz; bu da tamamen otomatik iş akışlarını mümkün kılar. Aspose.Tasks **50+ giriş ve çıkış formatını** destekler ve **yüzlerce görevi** yönetebilirken bellek kullanımını 200 MB'nin altında tutar; bu da bulut hizmetleri ve CI/CD hatları için idealdir.

## Önkoşullar
1. **Java Development Kit (JDK)** – JDK 8 veya daha yenisini kurun.  
2. **Aspose.Tasks for Java** – kütüphaneyi [download link](https://releases.aspose.com/tasks/java/) adresinden indirin.  

## Paketleri içe aktar
To start working with Aspose.Tasks in your Java project, import the necessary packages:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## Adım 1: bir proje nesnesi oluşturun
`Project` sınıfı, Aspose.Tasks'in bellek içinde bir Microsoft Project dosyasını temsil eden üst‑seviye nesnesidir. Bir örneğini oluşturmak, görevler, kaynaklar ve takvimlerle doldurabileceğiniz boş bir proje sağlar.
```java
Project project = new Project();
```
Burada yeni bir `Project` nesnesi örnekliyoruz – bu, görev listemizi tutacak MS Project dosyasını temsil eder.

## Adım 2: projeye bir görev ekleyin
`Task` sınıfı, bir proje zaman çizelgesindeki bireysel bir iş öğesini temsil eder. Her `Task` kendi süresine, başlangıç tarihine ve kaynak atamalarına sahip olabilir.
```java
Task task = project.getRootTask().getChildren().add("Task");
```
`getRootTask()` kullanarak proje hiyerarşisinin köküne erişir ve **add task to Microsoft Project** yaparız. `"Task"` dizesi görev adıdır; ihtiyacınıza göre herhangi bir açıklama ile değiştirebilirsiniz.

## Adım 3: belirtilen görevler için temel çizgi ayarlayın
`BaselineType`, hangi temel çizgi yuvasının (Baseline, Baseline1 … Baseline10) yazılacağını tanımlayan bir enum'dur. Görevlerin bir listesini geçirerek yalnızca seçtiğiniz öğelere temel çizgi ekleyebilirsiniz.
```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
**set baseline without MS Project** için, temel çizgi eklemek istediğiniz görevlerin bir listesini (burada `myList`) oluşturun ve `setBaseline` metoduna geçirin. Yalnızca seçici bir temel çizgiye ihtiyacınız varsa, eklediğiniz görevlerle `myList`'i doldurun.

## Adım 4: tüm proje için temel çizgi ayarlayın
`setBaseline`, seçilen temel çizgi değerlerini projedeki her göreve yazar.  
Tüm projeyi tek bir çağrıda temel çizgi eklemeyi tercih ederseniz, istediğiniz `BaselineType` ile `setBaseline` metodunu çağırmanız yeterlidir.
```java
project.setBaseline(BaselineType.Baseline);
```
Bu çağrı, projedeki **every task** için seçilen temel çizgi değerlerini yazar ve orijinal zaman çizelgesinin tam bir anlık görüntüsünü sağlar.

## Aspose.Tasks kullanarak Microsoft Project'e görev ekleme
`add()` belirtilen üst görevin altında yeni bir alt görev oluşturur ve yeni oluşturulan `Task` nesnesini döndürür.  
Bir görevi, bir üst `Task` nesnesi (genellikle kök görev) üzerinde `add()` çağırarak eklersiniz. Metot, proje dosyasını kaydetmeden önce süresi, başlangıç tarihi, kaynakları veya özel alanları gibi ek yapılandırmalar yapabileceğiniz yeni bir `Task` örneği döndürür.

## MS Project olmadan temel çizgi ayarlama
Aspose.Tasks, temel çizgi oluşturmayı tamamen kod aracılığıyla sağlar. Bir `BaselineType` seçin (ör. `BaselineType.Baseline`) ve `setBaseline` metodunu çağırın. `Baseline1`‑`Baseline10` ile tekrarlayarak birden fazla revizyon temel çizgisi tutabilirsiniz; tüm bunlar Microsoft Project'i açmadan gerçekleşir.

## Yaygın sorunlar ve çözümler
- **Baseline görünmüyor:** Temel çizgi ayarlandıktan sonra `project.save("output.mpp")` çağırdığınızdan emin olun (kısalık için kaydetme adımı burada atlanmıştır).  
- **Görev listesi boş görünüyor:** Görevleri doğru üst öğeye (`getRootTask()` veya bir alt‑göreve) eklediğinizi doğrulayın.  
- **Sürüm uyumsuzluğu hataları:** Yeni .mpp formatlarıyla uyumluluğu garanti etmek için en son Aspose.Tasks JAR'ını kullanın.

## Sıkça Sorulan Sorular

**Q: Aspose.Tasks for Java'ı Microsoft Project yüklü olmadan kullanabilir miyim?**  
A: Evet, Aspose.Tasks bağımsız çalışır ve ana makinede Microsoft Project gerektirmez.

**Q: Aspose.Tasks for Java farklı Microsoft Project sürümleriyle uyumlu mu?**  
A: Kesinlikle. Kütüphane, 2007'den en son 2024 sürümlerine kadar olan Project dosyalarını destekler.

**Q: Aspose.Tasks for Java kullanarak proje kaynaklarını manipüle edebilir miyim?**  
A: Evet, kaynakları görevler gibi programlı olarak ekleyebilir, güncelleyebilir ve silebilirsiniz.

**Q: Aspose.Tasks for Java görev bağımlılıklarını ayarlamayı destekliyor mu?**  
A: Evet, `TaskLink` sınıfını kullanarak önceki‑sonraki ilişkileri tanımlayabilirsiniz.

**Q: Aspose.Tasks for Java için teknik destek mevcut mu?**  
A: Evet, [support forum](https://forum.aspose.com/c/tasks/15) üzerinden yardım alabilirsiniz; Aspose personeli ve topluluk sorulara yanıt verir.

## Sonuç
Bu adımları izleyerek Java'da **add task to project** nasıl yapılacağını, bir görev listesi oluşturmayı ve Aspose.Tasks kullanarak **set baseline without MS Project** nasıl yapılacağını öğrendiniz. Bu yaklaşım proje otomasyonunu kolaylaştırır, masaüstü Project kurulumlarına ihtiyaç duyulmasını ortadan kaldırır ve zaman çizelgenizin her yönü üzerinde tam programlı kontrol sağlar.

---

**Son Güncelleme:** 2026-08-29  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.12  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Projeyi Oluşturma aspose.tasks – Yeni Görev Özelliklerini Ayarlama](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [Aspose.Tasks for Java'da Temel Çizgi Süresini Ayarlama](/tasks/java/task-baselines/task-baseline-duration/)
- [Görevler Oluşturma Aspose Java – Görev Özellikleri](/tasks/java/task-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}