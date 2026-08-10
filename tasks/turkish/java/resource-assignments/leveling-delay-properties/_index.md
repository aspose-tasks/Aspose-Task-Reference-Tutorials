---
date: 2026-06-05
description: Aspose.Tasks for Java ile kaynak ataması oluşturmayı, bir projeye kaynak
  eklemeyi ve seviye gecikme özelliklerini yönetmeyi öğrenin.
keywords:
- create resource assignment aspotasks
- Aspose.Tasks Java
- leveling delay properties
linktitle: Aspose.Tasks'te Kaynak Atamaları için Seviye Gecikme Özelliklerini Yönetme
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to create resource assignment with Aspose.Tasks for Java,
    add resources to a project, and manage leveling delay properties.
  headline: Create Resource Assignment with Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates smoothly with libraries such as Jackson for
      JSON handling or Apache POI for additional spreadsheet operations, allowing
      you to build richer project‑management solutions.
    question: Can I use Aspose.Tasks with other Java libraries?
  - answer: Aspose.Tasks supports 12+ file formats—including .MPP (2003‑2021), .XML,
      .XER, .CSV, .PDF, .HTML, and .MPP12—ensuring seamless round‑trip editing across
      all major Project versions.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: You can find support and community discussions on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find additional support for Aspose.Tasks?
  - answer: Yes, a fully functional free trial is available from the [releases page](https://releases.aspose.com/).
    question: Can I try Aspose.Tasks before purchasing?
  - answer: Request a temporary license from the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to run the library without evaluation restrictions.
    question: How can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java ile Kaynak Ataması Oluşturma
url: /tr/java/resource-assignments/leveling-delay-properties/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java ile Kaynak Ataması Oluşturma

Bu kapsamlı rehberde Aspose.Tasks kütüphanesini Java için kullanarak **aspotasks kaynak ataması nasıl oluşturulur** öğreneceksiniz. İster özel bir zamanlama motoru oluşturuyor, toplu proje güncellemelerini otomatikleştiriyor, ister sadece masaüstü uygulaması olmadan Microsoft Project dosyalarını manipüle etmeniz gerekse, bu adımları öğrenmek proje verilerinizi doğru ve tamamen kontrol edilebilir tutmanızı sağlar.

## Hızlı Yanıtlar
- **“add resource to project” ne anlama geliyor?** Daha sonra görevlere atanabilecek yeni bir kaynak girişi oluşturur.  
- **Atamadan sonra bir dengeleme gecikmesi ayarlayabilir miyim?** Evet, `Asn.DELAY` veya `Asn.LEVELING_DELAY` alanlarını kullanarak.  
- **Bu kodu çalıştırmak için lisansa ihtiyacım var mı?** Geliştirme için ücretsiz deneme sürümü çalışır; üretim için ücretli lisans gereklidir.  
- **Hangi Java sürümü destekleniyor?** Java 8 ve üzeri.  
- **Bu, tüm MS Project dosya formatlarıyla uyumlu mu?** Aspose.Tasks 12+ formatı destekler—.MPP, .XML, .XER, .CSV, .PDF ve daha fazlası dahil.

## Aspose.Tasks'te “add resource to project” nedir?
Bir projeye kaynak eklemek, `Project` modelinin içinde bir `Resource` nesnesi oluşturmak anlamına gelir. Bu nesne daha sonra `ResourceAssignment` aracılığıyla görevlere bağlanabilir ve çalışmayı, maliyetleri ve dengeleme ayarlarını takip etmenizi sağlar. Bir kaynak ekleyerek zamanlayıcıya tahsis edebileceği bir şey vermiş olursunuz ve daha sonra kullanılabilirlik, oranlar ve takvim atamaları gibi özelliklerini sorgulayabilir veya değiştirebilirsiniz.

## Neden dengeleme gecikmesi özelliklerini ele almalı?
Dengeleme gecikmesi, zamanlayıcıya aşırı tahsis edilmiş bir atamanın başlangıcını ertelemeyi ve işi zaman çizelgesi boyunca daha eşit dağıtmayı söyler. Bu gecikmeyi yapılandırarak gerçekçi olmayan başlangıç tarihlerinden kaçınır, aşırı tahsis uyarılarını azaltır ve gerçek dünya kaynak kısıtlamalarını yansıtan bir takvim oluşturursunuz. Gecikmeyi ayarlamak, motorun ekleyebileceği boşluk miktarı üzerinde ince ayar yapmanızı sağlar ve proje teslim tarihlerini kaynak sınırlamalarına saygı göstererek karşılamanıza yardımcı olur.

## Aspose.Tasks ile kaynak ataması nasıl oluşturulur?
`Project` nesnenizi yükleyin, bir görev ekleyin, bir kaynak oluşturun ve ardından bunları bir `ResourceAssignment` ile bağlayın. Bu uçtan uca akış, tam bir proje yapısını programlı olarak oluşturmanıza ve atama üzerindeki dengeleme gecikmesini hemen kontrol etmenize olanak tanır. Süreç, temel iş akışını gösterir: proje başlatma, görev tanımlama, kaynak oluşturma, atama bağlama ve son olarak dengeleme gecikmesi gibi zamanlama parametrelerini uygulama.

## Önkoşullar
1. Java Development Kit (JDK): Sisteminizde Java JDK yüklü olduğundan emin olun. [web sitesinden](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html) indirebilir ve kurabilirsiniz.  
2. Aspose.Tasks for Java Kütüphanesi: Aspose.Tasks for Java kütüphanesini [indirme sayfasından](https://releases.aspose.com/tasks/java/) indirin.

## Paketleri İçe Aktar
Aşağıdaki içe aktarmalar, proje manipülasyonu için gereken temel Aspose.Tasks sınıflarını getirir.  
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

## Aspose.Tasks ile kaynak ataması nasıl oluşturulur?
`Project` nesnenizi yükleyin, bir görev ekleyin, bir kaynak oluşturun ve ardından bunları bir `ResourceAssignment` ile bağlayın. Bu uçtan uca akış, tam bir proje yapısını programlı olarak oluşturmanıza ve atama üzerindeki dengeleme gecikmesini hemen kontrol etmenize olanak tanır. Süreç, temel iş akışını gösterir: proje başlatma, görev tanımlama, kaynak oluşturma, atama bağlama ve son olarak dengeleme gecikmesi gibi zamanlama parametrelerini uygulama.

## Adım 1: Project Nesnesi Oluşturma
`Project` sınıfı, Aspose.Tasks'in bellek içinde tüm bir proje dosyasını temsil eden üst‑seviye kapsayıcısıdır. Bir örnek oluşturmak, görevlere, kaynaklara ve atamalara eklemek için temiz bir başlangıç sağlar.
```java
Project prj = new Project();
```

## Adım 2: Görev Oluşturma
`Task` sınıfı, takvimdeki tek bir iş öğesini temsil eder. Bir görev eklemek, programlı olarak **görev ekleme** nasıl yapılır gösterir ve yaklaşan kaynak ataması için bir hedef sağlar.
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```

## Adım 3: Görev Başlangıç Tarihi ve Süresini Ayarla
Görevin ne zaman başlayacağını ve ne kadar süreceğini tanımlayın. Doğru başlangıç tarihleri çok önemlidir çünkü dengeleme hesaplamaları, daha sonra belirteceğiniz gecikmeler için bunları temel alır.
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```

## Adım 4: Kaynak Ekle
Şimdi yeni bir `Resource` girişi oluşturarak **projeye kaynak ekliyoruz**. `Resource` sınıfı, görevlere atanabilen bir kişi, ekipman veya malzemenin temsilidir.
```java
Resource resource = prj.getResources().add("Resource 1");
```

## Adım 5: Kaynak Ataması Oluşturma
`ResourceAssignment`, bir `Task` ve bir `Resource` öğesini bağlar. Bu ilişki, belirli bir görevde belirli bir kaynak için çalışma, maliyet ve dengeleme ayrıntılarını kaydetmenizi sağlar.
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```

## Adım 6: Dengeleme Gecikmesini Ayarla
Atama için dengeleme gecikmesini yapılandırın. Sıfıra ayarlamak ek bir gecikme olmadığı anlamına gelir, ancak değeri ihtiyaca göre ayarlayabilirsiniz. `Asn.DELAY` alanı gecikmeyi dakikalar içinde tutar; `Asn.LEVELING_DELAY` aynı şekilde çalışan bir takma addır.
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```

## Adım 7: Sonuçları Görüntüle
Önemli özellikleri yazdırarak her şeyin doğru ayarlandığını doğrulayın. Bu adım, dosyayı kaydetmeden önce kaynak, görev ve gecikme değerlerinin tam olarak beklediğiniz gibi olduğunu onaylamanıza yardımcı olur.
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## Yaygın Tuzaklar ve İpuçları
- **Tuzak:** Görev başlangıç tarihini ayarlamayı unutmak, atamanın proje başlangıcına varsayılan olarak ayarlanmasına neden olabilir.  
- **İpucu:** Gecikmenin ayrıntısını kontrol etmek için `prj.getDuration(value, TimeUnitType.Day)` kullanın.  
- **İpucu:** Birden fazla kaynak ekledikten sonra, zamanlayıcının dengeleme yeniden hesaplamasını sağlamak için `prj.updateResourceAssignments()` çağırın.  
- **Pro ipucu:** Büyük projeler (10.000+ görev) için toplu güncellemelerden önce `prj.setAutoCalculate(false)` etkinleştirin, ardından sonunda bir kez `prj.calculate()` çağırarak performansı artırın.

## Sıkça Sorulan Sorular

**S: Aspose.Tasks'i diğer Java kütüphaneleriyle kullanabilir miyim?**  
C: Evet, Aspose.Tasks JSON işleme için Jackson veya ek tablo işlemleri için Apache POI gibi kütüphanelerle sorunsuz bir şekilde entegre olur ve daha zengin proje yönetimi çözümleri oluşturmanıza olanak tanır.

**S: Aspose.Tasks, Microsoft Project dosyalarının farklı sürümleriyle uyumlu mu?**  
C: Aspose.Tasks 12+ dosya formatını destekler—.MPP (2003‑2021), .XML, .XER, .CSV, .PDF, .HTML ve .MPP12 dahil—tüm büyük Project sürümleri arasında sorunsuz çift yönlü düzenleme sağlar.

**S: Aspose.Tasks için ek destek nereden bulunabilir?**  
C: [Aspose.Tasks forumunda](https://forum.aspose.com/c/tasks/15) destek ve topluluk tartışmalarını bulabilirsiniz.

**S: Aspose.Tasks'i satın almadan deneme şansım var mı?**  
C: Evet, [sürüm sayfasından](https://releases.aspose.com/) tam işlevsel ücretsiz bir deneme sürümü mevcuttur.

**S: Değerlendirme için geçici bir lisans nasıl alabilirim?**  
C: Kütüphaneyi değerlendirme kısıtlamaları olmadan çalıştırmak için [geçici lisans sayfasından](https://purchase.aspose.com/temporary-license/) geçici bir lisans talep edebilirsiniz.

---

**Son Güncelleme:** 2026-06-05  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.11  
**Yazar:** Aspose

## İlgili Eğitimler

- [Aspose.Tasks'te Kaynak Atamaları Oluşturma](/tasks/java/resource-assignments/create-resource-assignments/)
- [Aspose.Tasks kullanarak Atama Bütçesini Java'da Yönetme](/tasks/java/resource-assignments/assignment-budget/)
- [Aspose.Tasks'te Atamayı Durdurma ve Kaynak Atamalarını Yeniden Başlatma](/tasks/java/resource-assignments/stop-resume-assignment/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}