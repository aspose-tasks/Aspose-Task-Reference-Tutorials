---
date: 2026-06-10
description: Aspose.Tasks for Java kullanarak kaynak atamaları için rate'i ve rate
  scale'ı nasıl okuyup yazacağınızı öğrenin. Malzeme kaynaklarını, birden çok formatı
  ve büyük projeleri destekler.
keywords:
- how to read rate
- how to write rate
- write rate scale
- Aspose.Tasks rate scale
- resource assignments Java
linktitle: Aspose.Tasks'te Kaynak Atamaları için Rate Scale'ı Okuma ve Yazma
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to read rate and how to write rate scale for resource assignments
    using Aspose.Tasks for Java. Supports material resources, multiple formats, and
    large projects.
  headline: How to Read Rate Scale and Write Rate Scale for Resource Assignments in
    Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java is compatible with all major Java IDEs, including
      IntelliJ IDEA, Eclipse, and NetBeans.
    question: Can I use Aspose.Tasks for Java with any Java IDE?
  - answer: Yes, Aspose.Tasks supports various file formats, including MPP, XML, and
      HTML.
    question: Does Aspose.Tasks support other file formats besides MPP?
  - answer: Absolutely, Aspose.Tasks offers comprehensive features for managing projects
      of any scale, making it suitable for enterprise‑level project management.
    question: Is Aspose.Tasks suitable for enterprise‑level project management?
  - answer: Yes, Aspose.Tasks provides extensive capabilities for customizing resource
      assignments, including cost, work, and duration adjustments.
    question: Can I customize resource assignments further beyond rate scale?
  - answer: Yes, you can find support and interact with other users on the Aspose.Tasks
      forum [here](https://forum.aspose.com/c/tasks/15).
    question: Is there a community forum for Aspose.Tasks support?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks'te Kaynak Atamaları için Rate Scale'ı Okuma ve Yazma
url: /tr/java/resource-assignments/read-write-rate-scale/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'te Kaynak Atamaları İçin Oran Ölçeğini Okuma ve Yazma

Bu öğreticide, Aspose.Tasks for Java kullanarak **oran ölçeği** ayarlarını nasıl okuyacağınızı ve kaynak atamaları için nasıl ayarlayacağınızı keşfedeceksiniz. Bir zamanlayıcı, raporlama aracı oluşturuyor ya da sadece proje güncellemelerini otomatikleştirmeniz gerekiyorsa, oran ölçeği manipülasyonunu ustalaşmak, malzeme ve iş kaynakları üzerinde ayrıntılı kontrol sağlar.

## Hızlı Yanıtlar
`ResourceAssignment` bir görevi bir kaynağa bağlar ve atamaya özgü verileri tutar.  
`Asn` atama alanları için sabitleri içerir, `RATE_SCALE` dahil.  
`RateScaleType` enumu, oran ölçeklendirme için olası zaman birimlerini listeler.

- **Oran işleme için birincil sınıf nedir?** `ResourceAssignment` ve `Asn.RATE_SCALE` özelliği.  
- **Hangi enum ölçek seçeneklerini tanımlar?** `RateScaleType` (Day, Week, Month, vb.).  
- **Örneği çalıştırmak için lisansa ihtiyacım var mı?** Test için ücretsiz deneme lisansı yeterlidir; üretim için ticari lisans gereklidir.  
- **Kaydetmeden sonra ölçeği değiştirebilir miyim?** Evet – projeyi yeniden yükleyin ve `Asn.RATE_SCALE` özelliğini gösterildiği gibi değiştirin.  
- **Desteklenen IDE'ler?** IntelliJ IDEA, Eclipse, NetBeans gibi herhangi bir Java IDE kodu derleyebilir.

## Kaynak Atamaları İçin Oran Ölçeğini Nasıl Okunur?
Projeyi yükleyin, istediğiniz `ResourceAssignment` öğesini bulun ve `getRateScale()` metodunu çağırın – bu, oranının gün, hafta, ay veya başka bir birime göre uygulanıp uygulanmadığını belirten bir `RateScaleType` değeri döndürür. Yanıt anında gelir ve yalnızca iki API çağrısı gerektirir; bu da denetim betikleri veya UI gösterimleri için idealdir.

## Kaynak Atamaları İçin Oran Ölçeğini Nasıl Yazılır?
Bir `ResourceAssignment` nesnesi oluşturun veya alın, `Asn.RATE_SCALE` özelliğini istediğiniz `RateScaleType` değerine (ör. `RateScaleType.Week`) ayarlayın ve ardından projeyi kaydedin. Bu tek özellik değişikliği, maliyet hesaplamalarını otomatik olarak günceller ve tüm desteklenen dosya formatlarında kalıcı olur. Ölçeği ayarladıktan sonra, yeni zaman birimini yansıtmak için kaynağın standart oranını veya fazla mesai oranını da ayarlamanız gerekebilir; bu, maliyet hesaplamalarının doğru kalmasını sağlar.

## Oran Ölçeği Nedir?
Oran ölçeği, bir kaynağın maliyet oranının uygulanacağı zaman birimini (gün, hafta, ay, vb.) belirler. Ölçeği ayarlamak, malzeme tüketimini veya iş gücü çabasını doğru bir şekilde modellemenizi sağlar. Örneğin, ölçeği Hafta olarak ayarlamak, maliyet oranının haftalık maliyet olarak yorumlanması anlamına gelir ve bir görevin toplam maliyeti, kaynağın atandığı hafta sayısına göre hesaplanır.

## Neden Oran Ölçeğini Okumalı ve Yazmalısınız?
Mevcut ölçeği okumak, mevcut takvimleri denetlemenize yardımcı olur; yeni bir ölçek yazmak ise kaynakları projenin faturalama veya tüketim politikalarına uyarlamanızı sağlar. Bu, **malzeme kaynağı** maliyetlerini tanımlarken veya standart dışı çalışma takvimleri için **ölçeği ayarlamanız** gerektiğinde özellikle faydalıdır.

## Ön Koşullar
Başlamadan önce, aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
1. **Java Geliştirme Ortamı** – JDK 8 veya daha üstü yüklü.  
2. **Aspose.Tasks for Java Kütüphanesi** – Kütüphaneyi [buradan](https://releases.aspose.com/tasks/java/) indirip kurun.

## Paketleri İçe Aktarma
`ResourceAssignment` sınıfı bir görev ile bir kaynak arasındaki bağlantıyı temsil eder, `RateScaleType` ise bir oran için olası zaman birimlerini sıralar. Kodlamaya başlamadan önce gerekli Aspose.Tasks sınıflarını içe aktarın.  

`Project` Microsoft Project dosyalarını yükleyen ve kaydeden ana nesnedir.  
`Resource` iş veya malzeme gibi bir proje kaynağını tanımlar.  
`ResourceType` enumu, bir kaynağın iş mi yoksa malzeme mi olduğunu belirtir.  
`Task` proje takvimindeki bir iş öğesini temsil eder.  
`SaveFileFormat` enumu, bir projeyi kaydederken kullanılacak çıktı formatını tanımlar.

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.RateScaleType;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import java.io.IOException;
```

## Adım 1: Java projenizi kurun
Bir Maven veya Gradle projesi oluşturun ve Aspose.Tasks JAR dosyasını sınıf yolunuza ekleyin. Bu adım, derleyicinin içe aktarılan sınıfları bulmasını sağlar.

## Adım 2: Proje Dosyasını Yükleyin
Üzerinde çalışmak istediğiniz mevcut Microsoft Project dosyasını yükleyin.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```

## Adım 3: Bir Görev Ekleyin
Daha sonra kaynak atamaları alacak yeni bir görev oluşturun.

```java
Task task = project.getRootTask().getChildren().add("t1");
```

## Adım 4: Kaynakları Tanımlayın
Burada **malzeme kaynağını** ve normal bir iş kaynağını tanımlıyoruz. Malzeme tipi kaynak için `ResourceType.Material` kullanımına dikkat edin.

```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```

## Adım 5: Kaynakları Göreve Atayın
Şimdi **kaynakları göreve atıyoruz** ve `RateScaleType.Week` kullanarak **ölçeğin nasıl ayarlanacağını** belirtiyoruz. Bu, oran ölçeğinin hem okunmasını hem de yazılmasını gösterir.

```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```

## Adım 6: Projeyi Kaydedin
Değişiklikleri yeni bir dosyaya kaydedin, böylece daha sonra kaydedilen oran ölçeğini doğrulayabiliriz.

```java
project.save("output.mpp", SaveFileFormat.Mpp);
```

## Adım 7: Kaynak Atamalarını Alın
Kaydedilen projeyi yeniden yükleyin ve **oran** ölçeğini okuyarak doğru yazıldığını doğrulayın.

```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## Yaygın Tuzaklar ve İpuçları
- **UID Uyumsuzluğu** – UID ile atamaları alırken, UID değerlerinin oluşturma sırasında atananlarla eşleştiğinden emin olun.  
- **Yanlış Kaynak Türü** – İş kaynağı için `ResourceType.Material` kullanmak, oran hesaplamalarının beklenmedik şekilde davranmasına neden olur.  
- **Kaydetme Formatı** – Özelleştirilmiş alanları (ör. oran ölçeği) korumak için her zaman `SaveFileFormat.Mpp` (veya başka bir desteklenen format) ile kaydedin.  
- **Büyük Projeler** – Aspose.Tasks, akış mimarisi sayesinde tüm belgeyi belleğe yüklemeden **500+ sayfa** dosyaları işleyebilir.

## Sıkça Sorulan Sorular

**S: Aspose.Tasks for Java'ı herhangi bir Java IDE ile kullanabilir miyim?**  
C: Evet, Aspose.Tasks for Java, IntelliJ IDEA, Eclipse ve NetBeans dahil olmak üzere tüm büyük Java IDE'leriyle uyumludur.

**S: Aspose.Tasks MPP dışındaki diğer dosya formatlarını destekliyor mu?**  
C: Evet, Aspose.Tasks, MPP, XML ve HTML dahil çeşitli dosya formatlarını destekler.

**S: Aspose.Tasks kurumsal düzeyde proje yönetimi için uygun mu?**  
C: Kesinlikle, Aspose.Tasks, her ölçekten projeyi yönetmek için kapsamlı özellikler sunar ve kurumsal düzeyde proje yönetimi için uygundur.

**S: Oran ölçeğinin ötesinde kaynak atamalarını daha da özelleştirebilir miyim?**  
C: Evet, Aspose.Tasks, maliyet, iş ve süre ayarlamaları dahil olmak üzere kaynak atamalarını özelleştirmek için geniş yetenekler sunar.

**S: Aspose.Tasks desteği için bir topluluk forumu var mı?**  
C: Evet, Aspose.Tasks forumunda [burada](https://forum.aspose.com/c/tasks/15) destek bulabilir ve diğer kullanıcılarla etkileşime geçebilirsiniz.

---

**Son Güncelleme:** 2026-06-10  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.12 (yazım zamanındaki en son sürüm)  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Aspose.Tasks'te Kaynak Atamaları Oluşturma](/tasks/java/resource-assignments/create-resource-assignments/)
- [Atamaları Değiştirme – Aspose ile Paylaşılan Kaynakları Okuma](/tasks/java/resource-assignments/read-shared-resource-assignments/)
- [Aspose.Tasks'te Kaynak Atamalarına Not Ekleme](/tasks/java/resource-assignments/resource-assignment-notes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}