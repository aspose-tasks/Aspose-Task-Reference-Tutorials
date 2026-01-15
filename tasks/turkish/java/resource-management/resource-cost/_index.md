---
date: 2026-01-15
description: Aspose.Tasks for Java kullanarak Microsoft Project dosyalarında planlanan
  bütçeli maliyet çalışmalarını nasıl yöneteceğinizi öğrenin. Adım adım rehberimizi
  izleyin.
linktitle: Handle Resource Cost in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java ile planlanan bütçelenmiş maliyet çalışması
url: /tr/java/resource-management/resource-cost/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java ile Planlanan Bütçeli Maliyet Çalışması

## Giriş

**Planlanan Bütçeli Maliyet Çalışması (BCWS)**, bir projenin zamanında ilerlemesini sağlamak ve finansal tahminin planlanan iş ile uyumlu olmasını temin etmek için kritik öneme sahiptir. Microsoft Project'te BCWS, belirli bir tarihe kadar planlanan iş için harcanması gereken para miktarını temsil eder. Aspose.Tasks for Java, bu değerler üzerinde tam programatik kontrol sağlar; .mpp dosyasını manuel olarak açmadan kaynak maliyetlerini okuyabilir, değiştirebilir ve raporlayabilirsiniz. Bu öğreticide, bir projeyi nasıl yükleyeceğinizi, kaynakları nasıl döngüye alacağınızı ve planlanan bütçeli maliyet çalışmasını diğer temel maliyet ölçütleriyle birlikte nasıl görüntüleyeceğinizi gösteren eksiksiz bir örnek üzerinden ilerleyeceğiz.

## Hızlı Yanıtlar
- **BCWS ne anlama gelir?** Budgeted Cost Work Scheduled – tarihe kadar planlanan iş için öngörülen maliyet.  
- **Hangi API özelliği BCWS'yi alır?** `Rsc.BCWS` bir `Resource` nesnesinde.  
- **Örneği çalıştırmak için lisansa ihtiyacım var mı?** Test için ücretsiz deneme lisansı yeterlidir; üretim için tam lisans gereklidir.  
- **BCWS değerlerini değiştirebilir miyim?** Evet, `Rsc.BCWS`'yi diğer sayısal alanlar gibi ayarlayabilirsiniz.  
- **Desteklenen Project sürümleri?** 2000'den en yeni .mpp formatına kadar tüm Microsoft Project sürümleri.

## Planlanan Bütçeli Maliyet Çalışması nedir?

**Budgeted Cost Work Scheduled (BCWS)**, belirli bir zaman noktasına kadar planlanan iş için harcanması gereken maliyeti yansıtan bir performans ölçümüdür. Earned Value Management (EVM) sisteminin temel taşlarından biridir ve proje yöneticilerinin planlanan harcama ile gerçekleşen harcama arasını karşılaştırmasına yardımcı olur.

## Önkoşullar

1. Java temellerine sağlam bir hakimiyet.  
2. Projenize Aspose.Tasks for Java eklenmiş olması (Maven/Gradle ya da JAR).  
3. Maliyet verileri içeren kaynakları barındıran bir Microsoft Project dosyası (`.mpp`) (ör. *ResourceCosts.mpp*).

## Paketleri İçe Aktarma

İlk olarak, projeleri ve kaynakları işlemek için gereken Aspose.Tasks sınıflarını içe aktarın:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## Adım 1: Veri Dizinini Tanımlama

`"Your Data Directory"` ifadesini *ResourceCosts.mpp* dosyasının bulunduğu mutlak ya da göreli yol ile değiştirin.

```java
String dataDir = "Your Data Directory";
```

## Adım 2: MS Project Dosyasını Yükleme

`Project` yapıcı (constructor) .mpp dosyasını okur ve sorgulayabileceğiniz bellek içi bir temsil oluşturur.

```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```

## Adım 3: Kaynaklar Üzerinde Döngü

Bu döngü, projede tanımlı her kaynağı dolaşır ve size maliyet alanlarına erişim sağlar.

```java
for (Resource res : prj.getResources()) {
```

## Adım 4: Kaynak Adını ve Maliyetleri Kontrol Et

`if` bloğu içinde şunları yaparız:

* **toplam maliyeti** (`Rsc.COST`) yazdır.  
* **gerçekleştirilen işin gerçek maliyetini** (`Rsc.ACWP`) yazdır.  
* **planlanan bütçeli maliyet çalışmasını** (`Rsc.BCWS`) – odaklandığımız ana ölçüt, yazdır.  
* **gerçekleştirilen işin planlanan bütçeli maliyetini** (`Rsc.BCWP`) yazdır.

Bu dört değer, projenin finansal durumuna hızlı bir bakış sunar.

```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.COST));
    System.out.println(res.get(Rsc.ACWP));
    System.out.println(res.get(Rsc.BCWS));
    System.out.println(res.get(Rsc.BCWP));
}
```

## Planlanan Bütçeli Maliyet Çalışmasını İzlemenin Önemi

* **Erken uyarı:** BCWS, gerçek maliyetten belirgin şekilde yüksekse, kaynakları fazla tahsis ediyor olabilirsiniz.  
* **Kazanılmış Değer Analizi:** BCWS, Maliyet Sapması (CV) ve Zaman Sapması (SV) hesaplamaları için temel girdi.  
* **Tahmin:** Doğru BCWS verileri, gelecekteki nakit akışı ihtiyaçlarını öngörmeye yardımcı olur ve paydaş raporlamasını bilgilendirir.

## Yaygın Sorunlar ve Sorun Giderme

| Belirti | Muhtemel Neden | Çözüm |
|---------|----------------|-------|
| `null` printed for BCWS | Resource has no cost rate table defined | Define a cost rate table for the resource in Microsoft Project or set it programmatically via `Rsc.COST_RATE_TABLE` |
| `ArrayIndexOutOfBoundsException` when iterating resources | Project file corrupted or contains empty resource entries | Validate the .mpp file in Microsoft Project and remove empty resources |
| Unexpected values (e.g., negative BCWS) | Custom fields overriding standard cost fields | Ensure you’re accessing the standard `Rsc.BCWS` and not a custom field with the same name |

## Sıkça Sorulan Sorular

**S: BCWS değerini programatik olarak güncelleyebilir miyim?**  
C: Evet. `res.set(Rsc.BCWS, newValue)` kullanın ve ardından projeyi `prj.save("Updated.mpp")` ile kaydedin.

**S: Aspose.Tasks çoklu para birimi projelerini destekliyor mu?**  
C: Kesinlikle. Maliyet alanları, Project dosyasında tanımlı para birimi ayarlarını dikkate alır.

**S: Bu maliyet ölçütlerini CSV'ye aktarmanın bir yolu var mı?**  
C: Kaynaklar üzerinde döngü kurarak değerleri bir `StringBuilder`'a yazabilir veya bir CSV kütüphanesi kullanarak dosyayı oluşturabilirsiniz.

**S: BCWS, BCWP'den nasıl farklıdır?**  
C: BCWS, planlanan iş için öngörülen maliyettir; BCWP (Budgeted Cost Work Performed) ise gerçekte tamamlanan iş için planlanan maliyeti yansıtır.

**S: Maliyet verilerini okumak için özel bir lisansa ihtiyacım var mı?**  
C: Değerlendirme lisansı tam okuma/yazma erişimi sağlar; üretim ortamları için ticari lisans gereklidir.

## Sonuç

Aspose.Tasks for Java'yi kullanarak **planlanan bütçeli maliyet çalışması** ve diğer kritik maliyet ölçütlerine kesin, programatik erişim elde edersiniz. Bu sayede özel panolar oluşturabilir, Earned Value raporlarını otomatikleştirebilir ve projelerinizi finansal olarak yolunda tutabilirsiniz—Microsoft Project ile manuel etkileşim gerektirmeden.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Son Güncelleme:** 2026-01-15  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.12 (latest)  
**Yazar:** Aspose