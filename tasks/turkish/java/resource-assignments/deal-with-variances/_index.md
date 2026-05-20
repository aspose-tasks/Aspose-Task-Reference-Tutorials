---
date: 2026-05-20
description: Aspose.Tasks for Java ile proje sapmalarını nasıl yöneteceğinizi öğrenin,
  cost variance, work variance ve date variances'ı verimli bir şekilde nasıl alacağınızı
  da öğrenin.
keywords:
- handle project variances
- get cost variance
- Aspose.Tasks Java
linktitle: Aspose.Tasks'te Sapmalarla Baş Et
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to handle project variances with Aspose.Tasks for Java, including
    how to get cost variance, work variance, and date variances efficiently.
  headline: How to Handle Project Variances with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to handle project variances with Aspose.Tasks for Java, including
    how to get cost variance, work variance, and date variances efficiently.
  name: How to Handle Project Variances with Aspose.Tasks for Java
  steps:
  - name: Iterate through Resource Assignments
    text: 'To deal with variances, we need to iterate through resource assignments
      in the project. This is achieved using a simple loop:'
  - name: Retrieve Work Variance
    text: 'Work variance represents the deviation between planned work and actual
      work performed by a resource. To retrieve work variance for each resource assignment,
      use the following code snippet:'
  - name: Retrieve Start Variance
    text: 'Start variance signifies the variance between planned and actual start
      dates for a task. To fetch start variance, utilize the following code:'
  - name: Retrieve Finish Variance
    text: 'Finish variance denotes the difference between planned and actual finish
      dates for a task. To acquire finish variance, employ the following code:'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks integrates seamlessly with libraries such as Jackson
      for JSON, Apache POI for Excel, and JFreeChart for reporting.
    question: Can I integrate Aspose.Tasks with other Java libraries?
  - answer: Absolutely. It efficiently processes projects containing up to 10,000
      tasks and 5,000 resources without loading the entire file into memory.
    question: Is Aspose.Tasks suitable for large‑scale projects?
  - answer: Certainly. Use the variance values you retrieve to feed custom PDF, Excel,
      or HTML reports via Aspose.Words, Aspose.Cells, or standard Java templating
      engines.
    question: Can I customize reports based on variance analysis?
  - answer: Yes, users can access technical support through the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for any assistance or queries.
    question: Is technical support available for Aspose.Tasks users?
  - answer: Yes, you can avail of a free trial of Aspose.Tasks from [here](https://releases.aspose.com/)
      to evaluate its features before making a purchase.
    question: Can I try Aspose.Tasks before purchasing?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java ile Proje Sapmalarını Nasıl Yönetilir
url: /tr/java/resource-assignments/deal-with-variances/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java ile Proje Varyanslarını Nasıl Yönetilir

## Giriş
Bu öğreticide, Aspose.Tasks for Java kullanarak **proje varyanslarını nasıl yöneteceğinizi** öğreneceksiniz. Varyanslar—planlanan ve gerçekleşen iş, maliyet, başlangıç veya bitiş tarihleri arasındaki farklar—bir projenin yolunda olup olmadığını gösteren önemli sinyallerdir. Aspose.Tasks, bu sayıları programlı bir şekilde alıp analiz etmenizi sağlayarak veri odaklı ayarlamaları hızlıca yapmanıza olanak tanır.

## Hızlı Yanıtlar
- **Varyanslara erişmek için ana sınıf nedir?** `ResourceAssignment` sınıfı `WorkVariance`, `CostVariance`, `StartVariance` ve `FinishVariance` gibi özellikler sağlar.  
- **Maliyet varyansını döndüren yöntem hangisidir?** Bir `ResourceAssignment` örneği üzerinde `getCostVariance()` kullanın.  
- **Bu özellik için lisans gerekir mi?** Evet, geçerli bir Aspose.Tasks lisansı tüm varyans API'lerini açar.  
- **Büyük projeler işlenebilir mi?** Aspose.Tasks, tüm dosyayı belleğe yüklemeden 10.000'e kadar görev içeren projeleri işleyebilir.  
- **Hangi Java sürümü gereklidir?** Java 8 veya üzeri desteklenir.

## “Proje varyanslarını yönetmek” nedir?
Proje varyanslarını yönetmek, temel (planlanan) değerler ile gerçekleşen iş, maliyet, başlangıç tarihleri ve bitiş tarihleri arasındaki farkları çıkarmayı içerir. Bu boşlukları analiz ederek proje yöneticileri performansı ölçebilir, takvim veya bütçe aşımlarını tespit edebilir ve projeyi yolunda tutmak için yeniden planlama ya da kaynak ayarlamaları konusunda bilinçli kararlar alabilir.

## Varyans analizinde neden Aspose.Tasks kullanılmalı?
Aspose.Tasks, **30'dan fazla giriş/çıkış dosya formatını** destekler ve tipik sunucu donanımında çok sayfalı takvimleri bir saniyeden kısa sürede işleyebilir. API'si varyans değerlerini doğrudan döndürür, manuel hesaplamalara veya üçüncü‑taraf eklentilerine gerek kalmaz.

## Önkoşullar
Devam etmeden önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1. Sisteminizde Java Development Kit (JDK) kurulu.  
2. Aspose.Tasks for Java kütüphanesini indirin ve projenize ekleyin. Kütüphaneyi [buradan](https://releases.aspose.com/tasks/java/) indirebilirsiniz.  
3. Java programlama dili hakkında temel bilgi.

## Paketleri İçe Aktarma
`ResourceAssignment` sınıfı `com.aspose.tasks` ad alanında bulunur. Kodlamaya başlamadan önce gerekli paketleri içe aktarın:

`ResourceAssignment` sınıfı, bir kaynak ile görev arasındaki bağlantıyı temsil eder ve sorgulayabileceğiniz varyans özelliklerini ortaya çıkarır.

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;

```

## Aspose.Tasks'te proje varyanslarını nasıl yönetilir?
Projenizi `new Project("yourfile.mpp")` ile yükleyin, ardından her `ResourceAssignment` üzerinde döngü yaparak varyans alanlarını okuyun. Bu tek geçiş, her atama için iş, maliyet, başlangıç ve bitiş varyanslarını sağlar ve anlık performans panolarını etkinleştirir.

### Adım 1: Kaynak Atamalarını Döngüyle Gezin
Varyanslarla başa çıkmak için projedeki kaynak atamaları üzerinden döngü yapmamız gerekir. Bu, basit bir döngü ile sağlanır:

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "ResourceAssignmentVariance.mpp");
for (ResourceAssignment ra : project.getResourceAssignments()) {
    // Perform operations on each resource assignment
}
```

### Adım 2: İş Varyansını Al
İş varyansı, planlanan iş ile bir kaynak tarafından gerçekleştirilen gerçek iş arasındaki sapmayı temsil eder. Her kaynak ataması için iş varyansını almak üzere aşağıdaki kod parçacığını kullanın:

```java
System.out.println(ra.get(Asn.WORK_VARIANCE));
```

### Bir kaynak ataması için maliyet varyansı nasıl alınır?
Belirli bir atama için maliyet varyansını elde etmek üzere, bir `ResourceAssignment` örneği üzerinde `getCostVariance()` metodunu çağırın. Bu metod, temel maliyet ile gerçekleşen maliyet arasındaki parasal farkı hesaplayarak, projenin varsayılan para birimindeki varyansı yansıtan bir `double` değer döndürür. Bu değeri bütçe analizinde kullanabilirsiniz.

```java
System.out.println(ra.get(Asn.COST_VARIANCE));
```

### Adım 4: Başlangıç Varyansını Al
Başlangıç varyansı, bir görev için planlanan ve gerçekleşen başlangıç tarihleri arasındaki farkı gösterir. Başlangıç varyansını almak için aşağıdaki kodu kullanın:

```java
System.out.println(ra.get(Asn.START_VARIANCE));
```

### Adım 5: Bitiş Varyansını Al
Bitiş varyansı, bir görev için planlanan ve gerçekleşen bitiş tarihleri arasındaki farkı gösterir. Bitiş varyansını elde etmek için aşağıdaki kodu kullanın:

```java
System.out.println(ra.get(Asn.FINISH_VARIANCE));
```

## Yaygın Sorunlar ve Çözümler
- **Null değerler:** Bir görevde temel yoksa, varyans özellikleri `null` döndürür. Değeri kullanmadan önce her zaman `null` kontrolü yapın.  
- **Zaman dilimi uyumsuzlukları:** Tarihler UTC olarak depolanır; kullanıcıya gösteriyorsanız yerel saat diliminize dönüştürün.  
- **Büyük dosyalar:** Binlerce atamaya sahip projeler için, bellek kullanımını düşük tutmak amacıyla atamaları toplu olarak işlemeyi düşünün.

## Sıkça Sorulan Sorular

**S: Aspose.Tasks'i diğer Java kütüphaneleriyle entegre edebilir miyim?**  
C: Evet, Aspose.Tasks JSON için Jackson, Excel için Apache POI ve raporlama için JFreeChart gibi kütüphanelerle sorunsuz bir şekilde entegre olur.

**S: Aspose.Tasks büyük ölçekli projeler için uygun mu?**  
C: Kesinlikle. Tüm dosyayı belleğe yüklemeden 10.000 göreve ve 5.000 kaynağa kadar projeleri verimli bir şekilde işler.

**S: Varyans analizine dayalı raporları özelleştirebilir miyim?**  
C: Elbette. Aldığınız varyans değerlerini Aspose.Words, Aspose.Cells veya standart Java şablon motorları aracılığıyla özel PDF, Excel veya HTML raporlarına besleyebilirsiniz.

**S: Aspose.Tasks kullanıcıları için teknik destek mevcut mu?**  
C: Evet, kullanıcılar herhangi bir yardım veya soru için [Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15) üzerinden teknik desteğe erişebilir.

**S: Satın almadan önce Aspose.Tasks'i deneyebilir miyim?**  
C: Evet, satın almadan önce özelliklerini değerlendirmek için Aspose.Tasks'in ücretsiz denemesini [buradan](https://releases.aspose.com/) alabilirsiniz.

---

**Son Güncelleme:** 2026-05-20  
**Test Edilen Versiyon:** Aspose.Tasks 24.12 for Java  
**Yazar:** Aspose  

{{< blocks/products/products-backtop-button >}}

## İlgili Öğreticiler

- [Aspose.Tasks ile Proje Maliyet İzleme - Fazla Mesai ve İş](/tasks/java/resource-assignments/overtime-remaining-costs-work/)
- [Aspose.Tasks for Java ile MS Project Kaynak Maliyetlerini Yönetme](/tasks/java/resource-management/resource-cost/)
- [Aspose.Tasks for Java kullanarak MS Project'te Proje Başlangıç Tarihini Ayarlama](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}