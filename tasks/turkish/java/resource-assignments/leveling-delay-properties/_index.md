---
date: 2026-01-07
description: Projeye kaynak eklemeyi ve Aspose.Tasks for Java kullanarak kaynak atamaları
  için seviye gecikme özelliklerini nasıl yöneteceğinizi öğrenin.
linktitle: Handle Leveling Delay Properties for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks'te Projeye Kaynak Ekleme ve Seviyelendirme Gecikme Özelliklerini
  Yönetme
url: /tr/java/resource-assignments/leveling-delay-properties/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projeye Kaynak Ekleme ve Seviyelendirme Gecikme Özelliklerini Aspose.Tasks ile Yönetme

## Giriş
Bu öğreticide, **projeye kaynak ekleme** işlemini ve Aspose.Tasks for Java ile kaynak atamaları için seviyelendirme gecikme özelliklerini yönetmeyi öğreneceksiniz. Bir zamanlama motoru oluşturuyor ya da proje güncellemelerini otomatikleştiriyorsanız, bu adımları ustalaşmak, Microsoft Project yüklü olmadan proje verilerinizi doğru tutmanızı sağlar.

## Hızlı Yanıtlar
- **“Projeye kaynak ekleme” ne anlama geliyor?** Yeni bir kaynak kaydı oluşturur ve bu kaynak görevler için atanabilir.  
- **Atamadan sonra seviyelendirme gecikmesi ayarlayabilir miyim?** Evet, `Asn.DELAY` veya `Asn.LEVELING_DELAY` alanlarını kullanarak.  
- **Bu kodu çalıştırmak için lisansa ihtiyacım var mı?** Geliştirme için ücretsiz deneme sürümü yeterlidir; üretim için ücretli lisans gereklidir.  
- **Hangi Java sürümü destekleniyor?** Java 8 ve üzeri.  
- **Tüm MS Project dosya formatlarıyla uyumlu mu?** Aspose.Tasks .MPP, .XML, .XER ve daha fazlasını destekler.

## Aspose.Tasks’te “projeye kaynak ekleme” nedir?
Projeye bir kaynak eklemek, `Project` modelinin içinde bir `Resource` nesnesi oluşturmaktır. Bu nesne daha sonra `ResourceAssignment` aracılığıyla görevlere bağlanabilir; böylece iş, maliyet ve seviyelendirme ayarlarını izleyebilirsiniz.

## Neden seviyelendirme gecikme özelliklerini ele almalıyız?
Seviyelendirme gecikmesi, kaynaklar aşırı tahsis edildiğinde işin yayılmasını sağlar. Bir gecikme ayarlayarak, motorun bir atamanın başlangıcını ertelemesini ve çakışmaları önlemesini, projenin gerçekçi kalmasını sağlarsınız.

## Ön Koşullar
Başlamadan önce aşağıdaki ön koşulları karşıladığınızdan emin olun:
1. Java Development Kit (JDK): Sisteminizde Java JDK yüklü olmalı. İndirmek ve kurmak için [web sitesini](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html) ziyaret edin.  
2. Aspose.Tasks for Java Kütüphanesi: Aspose.Tasks for Java kütüphanesini [indirme sayfasından](https://releases.aspose.com/tasks/java/) alın.

## Paketleri İçe Aktarma
Aspose.Tasks işlevlerini kullanmak için Java projenize gerekli paketleri içe aktarın:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Adım 1: Project Nesnesi Oluşturma
Tüm görev, kaynak ve atamaları tutacak bir `Project` nesnesi örnekleyin:
```java
Project prj = new Project();
```

## Adım 2: Görev Oluşturma
Projeye bir görev ekleyin. Bu, **programlı olarak görev ekleme** yöntemini gösterir:
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```

## Adım 3: Görev Başlangıç Tarihi ve Süresini Ayarlama
Görevin ne zaman başlayacağını ve ne kadar süreceğini tanımlayın:
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```

## Adım 4: Kaynak Ekleme
Şimdi yeni bir `Resource` kaydı oluşturarak **projeye kaynak ekliyoruz**:
```java
Resource resource = prj.getResources().add("Resource 1");
```

## Adım 5: Kaynak Ataması Oluşturma
Görevi yeni eklenen kaynakla ilişkilendirin:
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```

## Adım 6: Seviyelendirme Gecikmesini Ayarlama
Atama için seviyelendirme gecikmesini yapılandırın. Sıfır ayarlamak ek bir gecikme olmadığını gösterir; ihtiyaca göre değeri değiştirebilirsiniz:
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```

## Adım 7: Sonuçları Görüntüleme
Her şeyin doğru ayarlandığını doğrulamak için önemli özellikleri yazdırın:
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## Yaygın Hatalar ve İpuçları
- **Hata:** Görev başlangıç tarihini ayarlamamak, atamanın proje başlangıcına varsayılan olarak ayarlanmasına neden olabilir.  
- **İpucu:** Gecikmenin inceliğini kontrol etmek için `prj.getDuration(value, TimeUnitType.Day)` kullanın.  
- **İpucu:** Birden fazla kaynak ekledikten sonra `prj.updateResourceAssignments()` çağırarak zamanlayıcının seviyelendirmeyi yeniden hesaplamasını sağlayın.

## Sonuç
Bu adımları izleyerek **projeye kaynak ekleme**, bir göreve atama ve Aspose.Tasks for Java ile seviyelendirme gecikme özelliklerini yönetme konularında uzmanlaştınız. Bu bilgi, gerçek dünya kaynak kısıtlamalarıyla senkronize çalışan sağlam proje‑otomasyon çözümleri oluşturmanızı sağlar.

## SSS
### S: Aspose.Tasks’i diğer Java kütüphaneleriyle kullanabilir miyim?

C: Evet, Aspose.Tasks diğer Java kütüphaneleriyle entegre edilerek proje yönetimi yetenekleri artırılabilir.

### S: Aspose.Tasks, farklı Microsoft Project dosya sürümleriyle uyumlu mu?

C: Evet, Aspose.Tasks çeşitli Microsoft Project dosya sürümlerini destekler, böylece farklı ortamlarla uyumluluk sağlanır.

### S: Aspose.Tasks için ek destek nereden bulabilirim?

C: [Aspose.Tasks forumunda](https://forum.aspose.com/c/tasks/15) destek ve kaynakları bulabilirsiniz.

### S: Aspose.Tasks’i satın almadan önce deneyebilir miyim?

C: Evet, [releases sayfasından](https://releases.aspose.com/) Aspose.Tasks ücretsiz deneme sürümünü edinebilirsiniz.

### S: Aspose.Tasks için geçici bir lisans alabilir miyim?

C: Değerlendirme amaçlı olarak [geçici lisans sayfasından](https://purchase.aspose.com/temporary-license/) geçici lisans talep edebilirsiniz.

## Ek Sık Sorulan Sorular

**S: Sıfır olmayan bir seviyelendirme gecikmesi ayarlarsam ne olur?**  
C: Zamanlayıcı, atamanın başlangıcını belirtilen süre kadar erteler ve aşırı tahsisleri çözmeye yardımcı olur.

**S: Projeyi kaydettikten sonra seviyelendirme gecikmesini okuyabilir miyim?**  
C: Evet, proje dosyasını yeniden açıp atamadan `Asn.DELAY` özelliğini okuyabilirsiniz.

**S: Tüm atamalara aynı anda seviyelendirme gecikmesi uygulamanın bir yolu var mı?**  
C: `prj.getResourceAssignments()` üzerinden döngü kurarak her atama için gecikmeyi ayarlayabilirsiniz.

---

**Son Güncelleme:** 2026-01-07  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.11  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}