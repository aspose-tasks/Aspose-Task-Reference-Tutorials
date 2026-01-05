---
date: 2026-01-05
description: Aspose.Tasks for Java ile planlanan ve gerçekleşen iş ile diğer proje
  sapmalarını verimli bir şekilde nasıl yöneteceğinizi öğrenin. İş, maliyet, başlangıç
  ve bitiş sapmalarını zahmetsizce yönetin.
linktitle: Deal with Variances in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 'Planlanan ve Gerçek İş: Aspose.Tasks ile Verimli Proje Varyans Yönetimi'
url: /tr/java/resource-assignments/deal-with-variances/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Planlanan ve Gerçekleşen İş: Aspose.Tasks ile Verimli Proje Varyans Yönetimi

## Introduction
Bu öğreticide, Aspose.Tasks Java API'sini kullanarak **varyans** verilerini nasıl alacağınızı ve *planlanan ve gerçekleşen iş* karşılaştırmasını keşfedeceksiniz. Varyanslar—iş, maliyet, başlangıç tarihleri veya bitiş tarihleri olsun—zaman çizelgesi sağlığının ana göstergeleridir. Bu rehberin sonunda, maliyet varyansını hesaplayabilecek, her kaynak ataması için varyans değerlerini çıkarabilecek ve projelerinizi yolunda tutmak için proje varyanslarını etkili bir şekilde yönetebileceksiniz.

## Quick Answers
- **“Planlanan ve gerçekleşen iş” nedir?** Orijinal olarak planlanan iş ile gerçekte yapılan iş arasındaki farktır.  
- **Hangi API sınıfı varyans verilerini sağlar?** `Asn` sınıfı (ör. `Asn.WORK_VARIANCE`, `Asn.COST_VARIANCE`).  
- **Örneği çalıştırmak için lisansa ihtiyacım var mı?** Değerlendirme için ücretsiz deneme sürümü yeterlidir; üretim ortamı için ticari lisans gereklidir.  
- **Tüm varyans tiplerini tek bir döngüde alabilir miyim?** Evet—`ResourceAssignment` nesneleri üzerinde döngü yapın ve `ra.get(Asn.*_VARIANCE)` çağrısını kullanın.  
- **Hangi Java sürümü gereklidir?** Java 8 veya üzeri önerilir.

## Prerequisites
İlerlemeye başlamadan önce aşağıdaki önkoşulları karşıladığınızdan emin olun:
1. Sisteminizde Java Development Kit (JDK) yüklü olmalı.  
2. Aspose.Tasks for Java kütüphanesini indirin ve projenize ekleyin. İndirmek için [buraya](https://releases.aspose.com/tasks/java/) tıklayın.  
3. Java programlama diline temel bir hakimiyetiniz olmalı.

## Import Packages
Aspose.Tasks ile çalışmak için gerekli paketleri içe aktarın:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
```

## Step 1: Iterate through Resource Assignments
**Proje varyanslarını yönetmek** için, yüklü proje dosyasındaki her kaynak atamasını döngüyle işlemek gerekir:

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "ResourceAssignmentVariance.mpp");
for (ResourceAssignment ra : project.getResourceAssignments()) {
    // Perform operations on each resource assignment
}
```

## Step 2: Retrieve Work Variance (Planned vs Actual Work)
İş varyansı, **planlanan ve gerçekleşen iş** arasındaki farkı gösterir. Aşağıdaki kodla alın:

```java
System.out.println(ra.get(Asn.WORK_VARIANCE));
```

## Step 3: Retrieve Cost Variance
**Maliyet varyansını** hesaplamak istiyorsanız, aşağıdaki çağrıyı kullanın:

```java
System.out.println(ra.get(Asn.COST_VARIANCE));
```

## Step 4: Retrieve Start Variance
Başlangıç varyansı, planlanan başlangıç tarihi ile gerçek başlangıç tarihi arasındaki farkı gösterir:

```java
System.out.println(ra.get(Asn.START_VARIANCE));
```

## Step 5: Retrieve Finish Variance
Bitiş varyansı, planlanan bitiş tarihi ile gerçek bitiş tarihi arasındaki sapmayı yansıtır:

```java
System.out.println(ra.get(Asn.FINISH_VARIANCE));
```

## Why Retrieve Variance Data?
Varyansları anlamak şunlara yardımcı olur:
- Zaman çizelgesi gecikmelerini erken tespit edin.  
- Maliyetlerin artmadan önce kaynak dağılımını ayarlayın.  
- Paydaşlar için doğru durumorları oluşturun.  
- Geciken görevlerin kök neden analizini yapın.

## Common Pitfalls & Tips
- **Sorun:** Doğru `.mpp` dosya yolunun yüklenmemesi.  
  **İpucu:** `dataDir` değişkeninin `ResourceAssignmentVariance.mpp` dosyasını içeren klasöre işaret ettiğini doğrulayın.  
- **Sorun:** Varyans değerlerinin her zaman sayısal olduğu varsayımı.  
  **İpucu:** Veri mevcut değilse bazı atamalar `null` dönebilir; `null` kontrolleri ekleyin.  
- **Pro ipucu:** Gerçek yapılan işi hesaplamak için `ra.get(Asn.WORK)` ile `ra.get(Asn.WORK_VARIANCE)` birlikte kullanın.

## Conclusion
**Planlanan ve gerçekleşen iş** ile diğer varyansların ele alınması, etkili proje kontrolü için kritiktir. Aspose.Tasks for Java sayesinde bu metrikleri programlı olarak alıp analiz edebilir, veri odaklı kararlar alarak projelerin zamanında ve bütçe içinde kalmasını sağlayabilirsiniz.

## FAQ's
### Q: Aspose.Tasks'i diğer Java kütüphaneleriyle entegre edebilir miyim?
A: Evet, Aspose.Tasks diğer Java kütüphaneleriyle sorunsuz bir şekilde entegre edilerek proje yönetimi yetenekleri artırılabilir.  
### Q: Aspose.Tasks büyük ölçekli projeler için uygun mu?
A: Kesinlikle, Aspose.Tasks herhangi bir ölçekteki projeyi yönetebilecek şekilde tasarlanmıştır ve güçlü performans ile güvenilirlik sunar.  
### Q: Varyans analizine dayalı raporları özelleştirebilir miyim?
A: Elbette, Aspose.Tasks varyans analizi gereksinimlerine göre raporları özelleştirmenize olanak tanıyan kapsamlı özellikler sağlar.  
### Q: Aspose.Tasks kullanıcıları için teknik destek mevcut mu?
A: Evet, kullanıcılar herhangi bir soruları veya yardıma ihtiyaçları olduğunda [Aspose.Tasks forumu](https://forum.aspose.com/c/tasks/15) üzerinden teknik destek alabilirler.  
### Q: Aspose.Tasks'i satın almadan önce deneyebilir miyim?
A: Evet, satın almadan önce özelliklerini değerlendirmek için [buradan](https://releases.aspose.com/) ücretsiz bir deneme sürümü edinebilirsiniz.

## Frequently Asked Questions

**S: Belirli bir görev için maliyet varyansını nasıl hesaplarım?**  
C: Atamayı döngü içinde `ra.get(Asn.COST_VARIANCE)` kullanın; tam maliyet analizi için `ra.get(Asn.COST)` ile birleştirin.

**S: Varyans değeri null dönerse ne yapmalıyım?**  
C: Null, kaynağın dosyada ayarlanmamış olduğunu gösterir. Değeri yazdırmadan veya kullanmadan önce null kontrolü ekleyin.

**S: Varyans verilerini Excel'e aktarabilir miyim?**  
C: Evet—değerleri bir koleksiyona toplayıp Apache POI gibi bir kütüphane ile Excel sayfasına yazabilirsiniz.

**S: Aspose.Tasks Agile proje varyans metriklerini destekliyor mu?**  
C: API temel olarak geleneksel MS‑Project verilerine odaklansa da, Agile sprint bilgilerini görevlere eşleyerek yine varyans değerlerini alabilirsiniz.

**S: Varyans değerlerini toplu olarak güncellemenin bir yolu var mı?**  
C: Temel alanları (ör. `Asn.WORK`) değiştirip projeyi kaydedebilirsiniz; bir sonraki okuma sırasında varyans alanları yeniden hesaplanır.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Son Güncelleme:** 2026-01-05  
**Test Edilen:** Aspose.Tasks for Java 24.12  
**Yazar:** Aspose