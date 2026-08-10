---
date: 2026-06-15
description: Aspose.Tasks for Java kullanarak MS Project kaynaklarından timephased
  data nasıl çıkarılacağını öğrenin. Kimliğiyle resource almayı adım adım gösteren
  kılavuz.
keywords:
- get resource by id
- Aspose.Tasks timephased data
- Java MS Project API
linktitle: Aspose.Tasks'te Kaynaklar için Timephased Data Okuma
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to extract timephased data from MS Project resources using
    Aspose.Tasks for Java. Step‑by‑step guide to get resource by id.
  headline: Read Timephased Data for Resources in Aspose.Tasks – get resource by id
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks supports MPP, XML, CSV, and several other formats, allowing
      you to read and write across different standards.
    question: Can Aspose.Tasks handle other types of project files apart from Microsoft
      Project?
  - answer: Absolutely. The library works with all major IDEs (IntelliJ IDEA, Eclipse,
      NetBeans) and build tools (Maven, Gradle).
    question: Is Aspose.Tasks compatible with different Java development environments?
  - answer: Yes, you can create, modify, and delete tasks, resources, assignments,
      and even custom fields through the API.
    question: Can I manipulate project data using Aspose.Tasks?
  - answer: It is. Enterprises rely on Aspose.Tasks for high‑volume processing, batch
      conversions, and server‑side reporting because it requires no Microsoft Project
      installation.
    question: Is Aspose.Tasks suitable for enterprise‑level projects?
  - answer: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for assistance from the community and support team.
    question: Where can I find support if I encounter issues while using Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks'te Kaynaklar için Timephased Data Okuma – kimliğiyle resource
  al
url: /tr/java/resource-management/read-timephased-data/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zaman Aşamalı Verileri Kaynaklar İçin Aspose.Tasks'te Okuma

## Giriş
Bu öğreticide, **how to get resource by id** yöntemini öğrenip Aspose.Tasks for Java kullanarak zaman aşamalı verilerini okuyacaksınız. Proje klasörünün kurulmasından iş ve maliyet zaman aşamalı değerlerinin yazdırılmasına kadar her adımı adım adım göstereceğiz; böylece herhangi bir Microsoft Project dosyasından programlı olarak değerli zamanlama bilgilerini çıkarabilirsiniz. Aspose.Tasks for Java, Microsoft Project'in kurulu olmasını gerektirmeden Microsoft Project dosyalarını oluşturmanıza, okumanıza, değiştirmenize ve dönüştürmenize olanak tanıyan kapsamlı bir API'dir ve geniş bir proje yönetimi özellikleri ve formatları yelpazesini destekler.

## Hızlı Yanıtlar
- **“get resource by id” ne yapar?** Belirli bir `Resource` nesnesini, benzersiz tanımlayıcısını kullanarak bir `Project`'ten alır.  
- **Zaman aşamalı verileri hangi kütüphane işler?** Aspose.Tasks for Java, `Resource.getTimephasedData` API'sini sağlar.  
- **Lisans gerekir mi?** Geliştirme için ücretsiz deneme çalışır; üretim için ticari lisans gereklidir.  
- **Büyük projeleri okuyabilir miyim?** Evet—Aspose.Tasks, tüm dosyayı belleğe yüklemeden 10.000'e kadar görev içeren dosyaları işleyebilir.  
- **Hangi Java sürümü gereklidir?** Java 8 veya üzeri; kütüphane tüm büyük JDK'larla uyumludur.

## “get resource by id” nedir?
`get resource by id` yöntemi, bir `Project`'ten, kaynağın sayısal kimliğini kullanarak bir `Resource` örneği alır. Bu işlem, kaynağın atamaları, takvimleri ve özel alanları gibi ayrıntılı özelliklerine kesin erişim sağlar ve belirli bir kaynakla ilişkili zaman aşamalı iş veya maliyet verilerini çıkarmak için gereklidir.

## Zaman aşamalı veri için Aspose.Tasks neden kullanılmalı?
Aspose.Tasks, **50+ giriş ve çıkış formatını** (MPP, XML, CSV vb.) destekler ve çok yıllı takvimleri kapsayan kaynaklar için zaman aşamalı iş ve maliyet değerlerini düşük bellek kullanımıyla çıkarabilir. API, varsayılan olarak verileri 15 dakikalık aralıklarla döndürür; bu da raporlama veya özel analizler için ayrıntılı bir içgörü sağlar.

## Önkoşullar
Başlamadan önce aşağıdaki önkoşulları karşıladığınızdan emin olun:
1. Java Development Kit (JDK): Sisteminizde JDK yüklü olduğundan emin olun. [website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) adresinden indirebilir ve kurulum talimatlarını izleyebilirsiniz.  
2. Aspose.Tasks for Java Library: Aspose.Tasks for Java kütüphanesini [download page](https://releases.aspose.com/tasks/java/) adresinden indirebilir ve belgelerde verilen kurulum talimatlarını izleyebilirsiniz.

## Paketleri İçe Aktarma
İlk adım, gerekli Aspose.Tasks sınıflarını Java kaynak dosyanıza içe aktarmaktır.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```

## Adım 1: Veri Dizinini Ayarlama
İlk olarak, MS Project dosyanızın bulunduğu dizini tanımlayın. Veri klasörünü kaynak koddan ayrı tutmak, projenin bakımını kolaylaştırır.

```java
String dataDir = "Your Data Directory";
```

## Adım 2: MS Project Şablon Dosyasını Okuma
MS Project şablon dosyanızın adını belirtin. Şablon kullanmak, farklı projeler arasında tutarlı sütun ayarlarını sağlar.

```java
String fileName = "ResourceTimephasedData.mpp";
```

## Adım 3: Giriş Dosyasını Proje Olarak Okuma
`Project` sınıfı, Aspose.Tasks'in bellekte bir Microsoft Project dosyasını temsil eden temel nesnesidir. Dosyayı yüklemek, görevlere, kaynaklara ve zaman çizelgelerine programlı erişim sağlar.

```java
Project project = new Project(dataDir + fileName);
```

## Adım 4: Kaynağı ID ile Al
Belirli bir kaynağı almak için `getResources().getById(id)` metodunu çağırın. Bu, ana anahtar kelimeyle referans verilen tam işlemdir.

```java
Resource resource = project.getResources().getByUid(1);
```

## Adım 5: Kaynak İşi İçin Zaman Aşamalı Verileri Yazdır
`Resource` nesnesine sahip olduğunuzda, zaman içinde iş tahsislerini elde etmek için `resource.getTimephasedData(ResourceTimephasedDataType.Work)` metodunu çağırabilirsiniz. Dönen koleksiyon, her aralık için başlangıç tarihi, bitiş tarihi ve iş miktarını içeren `TimephasedData` nesnelerini içerir.

```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```

## Adım 6: Kaynak Maliyeti İçin Zaman Aşamalı Verileri Yazdır
Benzer şekilde, `resource.getTimephasedData(ResourceTimephasedDataType.Cost)` aynı zaman aralıklarıyla bölünmüş maliyet bilgilerini döndürür. Bu, bütçeleme ve maliyet takibi raporları için faydalıdır.

```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## Kaynağı ID ile Tek Satırda Nasıl Alınır?
Projeyi yükleyin, ardından `project.getResources().getById(5)` metodunu çağırın—**5** yerine ihtiyacınız olan gerçek kaynak kimliğini koyun. Bu tek çağrı `Resource` nesnesini döndürür; ardından zaman aşamalı verilerini, atamalarını veya özel alanlarını sorgulayabilirsiniz. Metot, kaynaklar dahili olarak indekslendiği için O(1) zamanında çalışır.

## Yaygın Sorunlar ve Çözümler
- **Resource not found** – Kimliğin proje dosyasında mevcut olduğundan emin olun; kimlikler 1'den başlar ve her kaynak için benzersizdir.  
- **Empty timephased data** – Kaynağın iş veya maliyet atamaları olduğundan emin olun; aksi takdirde koleksiyon boş olur.  
- **Large file performance** – 500 MB'den büyük projeler için tembel yüklemeyi etkinleştirmek amacıyla `Project.setLoadOptions(LoadOptions.fromFile(...))` kullanın.

## Sıkça Sorulan Sorular

**Q: Aspose.Tasks, Microsoft Project dışındaki diğer proje dosyası türlerini işleyebilir mi?**  
A: Evet, Aspose.Tasks MPP, XML, CSV ve birkaç diğer formatı destekler; bu sayede farklı standartlarda okuma ve yazma yapabilirsiniz.

**Q: Aspose.Tasks farklı Java geliştirme ortamlarıyla uyumlu mu?**  
A: Kesinlikle. Kütüphane tüm büyük IDE'lerle (IntelliJ IDEA, Eclipse, NetBeans) ve yapı araçlarıyla (Maven, Gradle) çalışır.

**Q: Aspose.Tasks kullanarak proje verilerini manipüle edebilir miyim?**  
A: Evet, API aracılığıyla görevleri, kaynakları, atamaları ve hatta özel alanları oluşturabilir, değiştirebilir ve silebilirsiniz.

**Q: Aspose.Tasks kurumsal‑düzey projeler için uygun mu?**  
A: Evet. Kuruluşlar, Microsoft Project kurulumu gerektirmediği için yüksek hacimli işleme, toplu dönüşümler ve sunucu tarafı raporlamada Aspose.Tasks'e güvenir.

**Q: Aspose.Tasks kullanırken sorunlarla karşılaşırsam nereden destek alabilirim?**  
A: Topluluk ve destek ekibinden yardım almak için [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) adresini ziyaret edebilirsiniz.

## Sonuç
Bu öğreticide, Aspose.Tasks for Java kullanarak **get resource by id** yöntemini nasıl uygulayacağımızı ve zaman aşamalı iş ve maliyet verilerini nasıl okuyacağımızı öğrendik. Bu adımları izleyerek proje dosyalarınızdan değerli zamanlama bilgilerini verimli bir şekilde çıkarabilir ve özel raporlama ya da analiz akışlarına entegre edebilirsiniz.

---

**Son Güncelleme:** 2026-06-15  
**Test Edilen:** Aspose.Tasks 24.11 for Java  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Aspose.Tasks for Java ile projeye kaynak ekleme](/tasks/java/resource-management/create-resources/)
- [Aspose.Tasks for Java ile MS Project kaynak maliyetlerini yönetme](/tasks/java/resource-management/resource-cost/)
- [Aspose.Tasks ile MS Project takviminden Java iş haftalarını okuma](/tasks/java/calendars/read-work-weeks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}