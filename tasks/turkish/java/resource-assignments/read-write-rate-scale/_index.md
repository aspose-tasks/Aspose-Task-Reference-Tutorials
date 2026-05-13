---
date: 2026-01-10
description: Aspose.Tasks for Java'da oran ölçeğini okumayı ve kaynak atamalarını
  yönetmeyi öğrenin. Malzeme kaynağını tanımlayın, ölçeği nasıl ayarlayacağınızı ve
  kaynakları göreve atamayı öğrenin.
linktitle: Read and Write Rate Scale for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks'te Kaynak Atamaları için Oran Ölçeğini Okuma ve Yazma
url: /tr/java/resource-assignments/read-write-rate-scale/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'te Kaynak Atamaları için Oran Ölçeğini Okuma ve Yazma

## Hızlı Yanıtlar
- **Oran işleme için birincil sınıf nedir?** `ResourceAssignment` ile `Asn.RATE_SCALE` özelliği.  
- **Hangi enum ölçek seçeneklerini tanımlar?** `RateScaleType` (Day, Week, Month, vb.).  
- **Örneği çalıştırmak için lisansa ihtiyacım var mı?** Test için ücretsiz değerlendirme lisansı yeterlidir; üretim için ticari lisans gereklidir.  
- **Kaydettikten sonra ölçeği değiştirebilir miyim?** Evet – projeyi yeniden yükleyip `Asn.RATE_SCALE` özelliğini aşağıda gösterildiği gibi değiştirebilirsiniz.  
- **Desteklenen IDE'ler?** IntelliJ IDEA, Eclipse, NetBeans gibi herhangi bir Java IDE'si kodu derleyebilir.

## Oran Ölçeği Nedir?
Oran ölçeği, bir kaynağın maliyet oranının uygulanacağı zaman birimini (gün, hafta, ay vb.) belirler. Ölçeği ayarlamak, malzeme tüketimini veya iş çabasını doğru şekilde modellemenizi sağlar.

## Neden oran ölçeğini okur ve yazarsınız?
Mevcut ölçeği okumak, mevcut takvimleri denetlemenize yardımcı olur; yeni bir ölçek yazmak ise kaynakları projenin faturalama veya tüketim politikalarına göre hizalamanızı sağlar. Bu, özellikle **malzeme kaynağı** maliyetlerini tanımlarken veya **ölçeği** standart dışı iş takvimleri için ayarlarken faydalıdır.

## Önkoşullar
Başlamadan önce aşağıdaki önkoşulları karşıladığınızdan emin olun:
1. **Java Geliştirme Ortamı** – JDK 8 veya daha üstü yüklü.  
2. **Aspose.Tasks for Java Kütüphanesi** – Kütüphaneyi [buradan](https://releases.aspose.com/tasks/java/) indirin ve kurun.

## Paketleri İçe Aktarma
İlk olarak gerekli Aspose.Tasks sınıflarını içe aktarın.

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
Çalışmak istediğiniz mevcut Microsoft Project dosyasını yükleyin.

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
Burada **malzeme kaynağını** ve normal bir iş kaynağını tanımlıyoruz. Malzeme‑tipi kaynak için `ResourceType.Material` kullanımına dikkat edin.

```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```

## Adım 5: Kaynakları Göreve Atayın
Şimdi **kaynakları göreve atıyoruz** ve `RateScaleType.Week` kullanarak **ölçeği nasıl ayarlayacağımızı** belirtiyoruz. Bu, oran ölçeğini hem okuma hem de yazma işlemlerini gösterir.

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

## Adım 7: Kaynak Atamalarını Getirin
Kaydedilen projeyi yeniden yükleyin ve **oran** ölçeğini okuyarak doğru yazıldığını onaylayın.

```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## Yaygın Tuzaklar ve İpuçları
- **UID Uyumsuzluğu** – UID ile atamaları alırken, UID değerlerinin oluşturma sırasında atananlarla eşleştiğinden emin olun.  
- **Yanlış Kaynak Türü** – İş kaynağı için `ResourceType.Material` kullanmak, oran hesaplamalarının beklenmedik şekilde davranmasına neden olur.  
- **Kaydetme Formatı** – Oran ölçeği gibi özel alanları korumak için her zaman `SaveFileFormat.Mpp` (veya başka bir desteklenen format) kullanarak kaydedin.

## Sonuç
Aspose.Tasks for Java'da kaynak atamaları için oran ölçeğini yönetmek ve incelemek, ilgili sınıfları ve özellikleri bildiğinizde oldukça basittir. Bu rehberi izleyerek **oran** bilgilerini **okuyabilir**, **malzeme kaynağı** nesnelerini **tanımlayabilir**, **ölçeği ayarlayabilir** ve **kaynakları göreve atayabilirsiniz**.

## Sık Sorulan Sorular

**S: Aspose.Tasks for Java'ı herhangi bir Java IDE'siyle kullanabilir miyim?**  
C: Evet, Aspose.Tasks for Java tüm büyük Java IDE'leriyle uyumludur, IntelliJ IDEA, Eclipse ve NetBeans dahil.

**S: Aspose.Tasks MPP dışındaki diğer dosya formatlarını destekliyor mu?**  
C: Evet, Aspose.Tasks MPP, XML ve HTML gibi çeşitli dosya formatlarını destekler.

**S: Aspose.Tasks kurumsal düzeyde proje yönetimi için uygun mu?**  
C: Kesinlikle, Aspose.Tasks herhangi bir ölçeğin projelerini yönetmek için kapsamlı özellikler sunar ve kurumsal düzeyde proje yönetimi için uygundur.

**S: Oran ölçeğinin ötesinde kaynak atamalarını daha da özelleştirebilir miyim?**  
C: Evet, Aspose.Tasks maliyet, iş ve süre ayarlamaları dahil olmak üzere kaynak atamalarını özelleştirmek için geniş yetenekler sağlar.

**S: Aspose.Tasks desteği için bir topluluk forumu var mı?**  
C: Evet, Aspose.Tasks forumunda [burada](https://forum.aspose.com/c/tasks/15) destek bulabilir ve diğer kullanıcılarla etkileşime geçebilirsiniz.

---

**Last Updated:** 2026-01-10  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}