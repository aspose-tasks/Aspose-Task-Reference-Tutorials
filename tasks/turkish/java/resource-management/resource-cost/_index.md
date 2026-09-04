---
date: 2026-06-15
description: Aspose.Tasks for Java kullanarak MS Project dosyalarında maliyetleri
  nasıl yöneteceğinizi öğrenin; MPP dosyasını nasıl yükleyeceğiniz ve gerçek maliyet
  çalışması ile bütçelenmiş maliyet takvimini nasıl okuyacağınız dahil.
keywords:
- how to manage costs
- actual cost work
- load mpp file
- budgeted cost schedule
linktitle: Aspose.Tasks'te Kaynak Maliyetini İşleme
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to manage costs in MS Project files using Aspose.Tasks for
    Java, including how to load an MPP file and read actual cost work and budgeted
    cost schedule.
  headline: How to Manage Costs in MS Project with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to manage costs in MS Project files using Aspose.Tasks for
    Java, including how to load an MPP file and read actual cost work and budgeted
    cost schedule.
  name: How to Manage Costs in MS Project with Aspose.Tasks for Java
  steps:
  - name: Basic understanding of Java programming.
    text: Basic understanding of Java programming.
  - name: Aspose.Tasks for Java library added to your project (Maven/Gradle or manual
      JAR).
    text: Aspose.Tasks for Java library added to your project (Maven/Gradle or manual
      JAR).
  - name: Access to a Microsoft Project file (`.mpp`) you want to analyze.
    text: Access to a Microsoft Project file (`.mpp`) you want to analyze.
  type: HowTo
- questions:
  - answer: Yes, it fully supports nested summary tasks, multiple resource calendars,
      and custom fields across all supported Project versions.
    question: Can Aspose.Tasks for Java handle complex project structures?
  - answer: Absolutely. Aspose.Tasks reads and writes files from Microsoft Project
      2000 up to the latest 2023 format.
    question: Is the library compatible with different versions of Microsoft Project
      files?
  - answer: Yes, the API returns standard Java objects, allowing seamless integration
      with logging frameworks, ORM tools, or reporting libraries.
    question: Can I integrate Aspose.Tasks for Java with other Java libraries?
  - answer: Aspose provides dedicated forum support, detailed documentation, and responsive
      email assistance for licensed users.
    question: Does Aspose.Tasks for Java offer customer support?
  - answer: You can download a 30‑day evaluation license from the Aspose website to
      explore all features without cost.
    question: Is there a free trial available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: MS Project'te Aspose.Tasks for Java ile Maliyetleri Yönetme
url: /tr/java/resource-management/resource-cost/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Project'te Maliyetleri Yönetme Aspose.Tasks for Java ile

## Giriş

Proje bütçelerini yönetmek, her proje yöneticisinin temel sorumluluğudur ve **maliyetleri nasıl yönetilir** sorusuna etkili bir yanıt vermek, bir projenin başarısını belirleyebilir. Aspose.Tasks for Java, Microsoft Project dosyaları üzerinde programatik kontrol sağlar; .mpp dosyasını manuel olarak açmadan kaynak maliyet verilerini okuyabilir ve güncelleyebilirsiniz. Bu öğreticide, bir MPP dosyasını nasıl yükleyeceğinizi, gerçek maliyet işini nasıl inceleyeceğinizi ve her kaynak için bütçelenmiş maliyet planını nasıl çıkaracağınızı adım adım göreceksiniz.

## Hızlı Yanıtlar
- **Aspose.Tasks for Java ne yapar?** Microsoft Project yüklü olmasına gerek kalmadan Microsoft Project dosyalarını (.mpp) okur ve yazar.  
- **Bir MPP dosyasını nasıl yükleyebilirim?** `new Project("path/to/file.mpp")` kullanın – API dosyayı bellekte ayrıştırır.  
- **Hangi maliyet alanları mevcuttur?** Actual Cost Work (ACWP), Budgeted Cost of Work Scheduled (BCWS) ve Budgeted Cost of Work Performed (BCWP).  
- **Geliştirme için lisansa ihtiyacım var mı?** Test için ücretsiz geçici bir lisans yeterlidir; üretim için tam lisans gereklidir.  
- **Hangi Java sürümleri destekleniyor?** Java 8 ve üzeri, Java 17 LTS dahil.  

## MS Project'te Maliyetleri Nasıl Yönetilir?

Projenizi `new Project("yourFile.mpp")` ile yükleyin, ardından her `Resource` nesnesi üzerinden döngü yaparak ACWP, BCWS ve BCWP gibi maliyetle ilgili özellikleri okuyun. Aspose.Tasks, iç maliyet değerlerini otomatik olarak projenin para birimine dönüştürür, böylece doğrudan görüntüleyebilir veya depolayabilirsiniz. Bu yaklaşım, manuel elektronik tablo hesaplamalarını ortadan kaldırır ve tüm proje raporlarında veri tutarlılığını garanti eder.

## Önkoşullar

1. Java programlaması hakkında temel anlayış.  
2. Projenize Aspose.Tasks for Java kütüphanesinin eklenmesi (Maven/Gradle veya manuel JAR).  
3. Analiz etmek istediğiniz bir Microsoft Project dosyasına (`.mpp`) erişim.  

## Paketleri İçe Aktarma

`Project` ve `Resource` sınıfları, proje verileriyle çalışmak için giriş noktalarıdır.

`Project` sınıfı, Aspose.Tasks'in bellek içinde tek bir Microsoft Project dosyasını temsil eden üst‑seviye nesnesidir.  
```text
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```
```

## Adım 1: Veri Dizinini Tanımlama

İlk olarak, `.mpp` dosyanızın bulunduğu klasörü belirtin. Bu yol, uygulamanızın çalışma dizinine göre mutlak ya da göreli olabilir.

```text
```java
String dataDir = "Your Data Directory";
```
```

## Adım 2: MS Project Dosyasını Yükleme

`Project` dosyayı yükler ve sorgulayabileceğiniz bir nesne modeli oluşturur. API, Microsoft Project yüklü olmadan dosyayı ayrıştırır ve 30'dan fazla giriş formatını destekler.

```text
```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```
```

## Adım 3: Kaynaklar Üzerinde Döngü

`Resource` nesneleri, bütçeyi tüketen kişi, ekipman veya malzemeyi temsil eder. Her birine erişmek için `project.getResources()` koleksiyonu üzerinde döngü yapabilirsiniz.

```text
```java
for (Resource res : prj.getResources()) {
```
```

## Adım 4: Kaynak Adını ve Maliyetlerini Kontrol Et

Her kaynak için, adının tanımlı olduğunu doğrulayın, ardından maliyet alanlarını okuyun. `getActualCost()` metodu **actual cost work** (ACWP) döndürür, `getBudgetedCost()` ise size **budgeted cost schedule** (BCWS/BCWP) verir.

```text
```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.COST));
    System.out.println(res.get(Rsc.ACWP));
    System.out.println(res.get(Rsc.BCWS));
    System.out.println(res.get(Rsc.BCWP));
}
```
```

## Neden Aspose.Tasks for Java ile bir MPP Dosyası Yüklenir?

Aspose.Tasks, **30+ dosya formatını** (`.mpp`, `.xml` ve `.xlsx` dahil) destekler ve **10.000'e kadar görev** içeren projeleri 200 MB'den az RAM kullanarak işleyebilir. Kütüphane tüm hesaplamaları sunucu tarafında gerçekleştirir, bu da lisanslı bir Microsoft Project kopyasına ihtiyaç duyulmadan çalışmayı sağlar.

## Yaygın Sorunlar ve Çözümler

- **Null kaynak adları:** Bazı eski dosyalar yer tutucu kaynaklar içerir. Maliyet özelliklerine erişmeden önce her zaman `resource.getName() != null` kontrol edin.  
- **Büyük dosyalar bellek baskısı oluşturuyor:** LoadOptions, hangi proje verilerinin yükleneceğini belirlemenizi sağlayan bir yapılandırma sınıfıdır. Yalnızca ihtiyacınız olan verileri yüklemek için `project.setLoadOptions(LoadOptions.setLoadResourceData(false))` kullanın, ardından gerekirse daha sonra etkinleştirin.  
- **Para birimi uyumsuzlukları:** API, projenin para birimi ayarlarına saygı gösterir; gerekirse `project.getRootTask().setCostRateTable(CostRateTableType.CostRateTable1)` ile geçersiz kılabilirsiniz. CostRateTableType, bir göreve uygulanabilecek farklı maliyet oran tablolarını listeler.  

## Sıkça Sorulan Sorular

**Q: Aspose.Tasks for Java karmaşık proje yapılarıyla başa çıkabilir mi?**  
**A:** Evet, tüm desteklenen Project sürümlerinde iç içe özet görevleri, birden çok kaynak takvimini ve özel alanları tam olarak destekler.

**Q: Kütüphane, Microsoft Project dosyalarının farklı sürümleriyle uyumlu mu?**  
**A:** Kesinlikle. Aspose.Tasks, Microsoft Project 2000'den en son 2023 formatına kadar dosyaları okur ve yazar.

**Q: Aspose.Tasks for Java'ı diğer Java kütüphaneleriyle entegre edebilir miyim?**  
**A:** Evet, API standart Java nesneleri döndürür, bu da günlükleme çerçeveleri, ORM araçları veya raporlama kütüphaneleriyle sorunsuz entegrasyon sağlar.

**Q: Aspose.Tasks for Java müşteri desteği sunuyor mu?**  
**A:** Aspose, lisanslı kullanıcılar için özel forum desteği, ayrıntılı dokümantasyon ve hızlı e-posta yardımı sağlar.

**Q: Aspose.Tasks for Java için ücretsiz deneme sürümü mevcut mu?**  
**A:** Aspose web sitesinden 30 günlük bir değerlendirme lisansı indirerek tüm özellikleri ücretsiz olarak keşfedebilirsiniz.

---

**Son Güncelleme:** 2026-06-15  
**Test Edilen:** Aspose.Tasks for Java 24.12  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Aspose.Tasks ile Maliyet Varyansını Hesaplama ve Atama Maliyetlerini Yönetme](/tasks/java/resource-assignments/assignment-cost/)
- [Aspose.Tasks'te Görevler için Bütçe, İş ve Maliyet Yönetimi](/tasks/java/task-properties/task-budget-work-cost/)
- [Aspose.Tasks for Java ile projeye kaynak ekleme](/tasks/java/resource-management/create-resources/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}