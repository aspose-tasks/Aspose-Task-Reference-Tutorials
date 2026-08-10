---
date: 2026-06-15
description: Aspose.Tasks ile Java'da kaynak yüzdesi nasıl hesaplanacağını, MS Project
  kaynakları için yüzde çalışma tamamlanmasını nasıl alacağınızı öğrenin. Adım adım
  kılavuz ve kod örnekleri.
keywords:
- calculate resource percentage java
- get percent work complete
- Aspose.Tasks resource percentage
- Java project management API
linktitle: Aspose.Tasks'te Kaynaklar İçin Yüzde Hesaplamalarını Gerçekleştirin
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to calculate resource percentage java with Aspose.Tasks,
    including how to get percent work complete for MS Project resources. Step‑by‑step
    guide with code examples.
  headline: calculate resource percentage java with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: It’s the percentage of work a resource has completed relative to its total
      assigned work.
    question: What does “resource percentage” mean?
  - answer: '`Rsc.PERCENT_WORK_COMPLETE` via the `Resource` class.'
    question: Which API call returns this value?
  - answer: A temporary or full Aspose.Tasks license is required for production use.
    question: Do I need a license?
  - answer: Yes – the API works with Spring, Hibernate, and plain Java projects.
    question: Can I use this with other Java frameworks?
  - answer: Any recent version that supports the `Rsc` enumeration (e.g., 24.x).
    question: What version of Aspose.Tasks is needed?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Aspose.Tasks ile Java'da kaynak yüzdesi hesaplama
url: /tr/java/resource-management/percentage-calculations/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks ile Java'da kaynak yüzde hesaplama

## Giriş
Hoş geldiniz! Bu öğreticide **Java'da kaynak yüzde nasıl hesaplanır** konusunu Aspose.Tasks Java kütüphanesini kullanarak öğreneceksiniz. Microsoft Project dosyasındaki her kaynak için *tamamlanan iş yüzdesi* değerini nasıl çıkaracağımızı adım adım gösterecek, bu metriğin neden önemli olduğunu açıklayacak ve ihtiyacınız olan tam kodu sunacağız. Sonunda, kaynak‑yüzde hesaplamalarını herhangi bir Java‑tabanlı proje‑yönetim çözümüne entegre edebileceksiniz.

## Hızlı Yanıtlar
- **“resource percentage” ne anlama geliyor?** Bir kaynağın toplam atanan işine göre tamamladığı iş yüzdesidir.  
- **Hangi API çağrısı bu değeri döndürür?** `Rsc.PERCENT_WORK_COMPLETE` `Resource` sınıfı aracılığıyla.  
- **Bir lisansa ihtiyacım var mı?** Üretim kullanımı için geçici veya tam bir Aspose.Tasks lisansı gereklidir.  
- **Bunu diğer Java çerçeveleriyle kullanabilir miyim?** Evet – API Spring, Hibernate ve sade Java projeleriyle çalışır.  
- **Hangi Aspose.Tasks sürümü gerekiyor?** `Rsc` enumarasyonunu destekleyen herhangi bir yeni sürüm (ör. 24.x).

## Java'da kaynak yüzde hesaplaması nedir?
Java'da kaynak yüzdesi hesaplamak, bir Microsoft Project dosyasını açmayı, her kaynağın atanmış işini okumayı ve bu işin ne kadarının zaten tamamlandığını belirlemeyi içerir. Bu metrik, proje yöneticilerinin ilerlemeyi değerlendirmesine, iş yüklerini dengelemesine ve manuel hesaplamalar yapmadan olası gecikmeleri tespit etmesine yardımcı olur.

## Neden tamamlanan iş yüzdesi alınmalı?
Tamamlanan iş yüzdesini her kaynak için almak, planlanan çabanın ne kadarının tamamlandığını anında gösterir; bu sayede geciken görevleri veya yetersiz kullanılan kaynakları hızlıca fark edebilirsiniz. Bu içgörü, zamanında karar‑alma ve daha doğru durum raporlamasını destekler.

## Önkoşullar
### Java Geliştirme Ortamı
Java Development Kit (JDK) yüklü olduğundan emin olun. JDK'yi [buradan](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) indirebilirsiniz.

### Aspose.Tasks Kütüphanesi
Aspose.Tasks kütüphanesini projenize [buradan](https://releases.aspose.com/tasks/java/) indirin ve belge içinde verilen kurulum talimatlarını [buradan](https://reference.aspose.com/tasks/java/) izleyin.

## Paketleri İçe Aktarma
`Resource` sınıfı bir proje kaynağını temsil eder ve *tamamlanan iş yüzdesi* gibi alanlara erişim sağlar.  
Kodlamaya başlamadan önce bu öğretici için gerekli paketleri içe aktaralım:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## Proje dosyası yolunu nasıl ayarlarım?
Microsoft Project dosyanızın konumunu, mutlak bir yol ya da uygulamanın çalışma dizinine göre göreceli bir yol belirterek tanımlayın. Yol dizesi geçerli bir *.mpp* dosyasına işaret etmelidir; böylece Aspose.Tasks dosyayı bulup açabilir.  
```java
String dataDir = "Your Data Directory";
```
`"Your Data Directory"` ifadesini Microsoft Project dosyanızın bulunduğu klasörle değiştirin.

## Projeyi nasıl yüklerim?
Daha önce tanımladığınız dosya yolunu kullanarak `Project` sınıfının yeni bir örneğini oluşturun. `Project` sınıfı bir Microsoft Project dosyasını temsil eder ve görevlerine, kaynaklarına ve diğer proje verilerine erişim sağlar; tüm verileri analiz için belleğe yükler.  
```java
Project prj = new Project(dataDir + "Software Development.mpp");
```
Bu, belirttiğiniz dizinden **Software Development.mpp** dosyasını yükler.

## Kaynaklar arasında nasıl döngü kurarım?
Yüklenen projede tanımlı tüm kaynakları elde etmek için `project.getResources()` metodunu kullanın. Bu koleksiyon üzerinde standart bir Java `for` döngüsü ya da geliştirilmiş `for‑each` yapısı ile yineleme yaparak her `Resource` nesnesini tek tek inceleyebilir ve ilişkili alanlarını alabilirsiniz.  
```java
for (Resource res : prj.getResources()) {
```
Projede tanımlı tüm kaynaklar üzerinde döngü kurarız.

## Kaynak adını nasıl kontrol eder ve tamamlanan iş yüzdesini alırım?
İlk olarak `Resource` nesnesinin boş olmayan bir adı olduğundan emin olun; böylece yer tutucu girdileri işlemden kaçınabilirsiniz. Ardından `res.get(Rsc.PERCENT_WORK_COMPLETE)` metodunu çağırın; bu, kaynak için tamamlanan iş yüzdesini 0‑100 arasında bir double olarak döndürür. Değeri ekranda göstermek için biçimlendirebilir veya proje sağlığını değerlendirmek üzere daha ileri hesaplamalarda kullanabilirsiniz.  
```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.PERCENT_WORK_COMPLETE));
}
```
Kod önce kaynağın bir adı olduğundan emin olur ve ardından o kaynak için **tamamlanan iş yüzdesi** değerini yazdırır.

## Yaygın Sorunlar ve Çözümler
- **NullPointerException** – Proje dosyası yolunun doğru olduğundan ve dosyanın hatasız yüklendiğinden emin olun.  
- **Yanlış yüzdeler** – Kaynağın gerçekten atanmış işi olup olmadığını doğrulayın; aksi takdirde yüzde `0` olur.  
- **Lisans hataları** – Çalışma zamanı kısıtlamalarından kaçınmak için geçerli bir Aspose.Tasks lisansı veya geçici bir değerlendirme lisansı kullanın.

## Sıkça Sorulan Sorular (Orijinal)

### Aspose.Tasks for Java'ı diğer Java çerçeveleriyle kullanabilir miyim?
Evet, Aspose.Tasks for Java Spring, Hibernate ve diğer çeşitli Java çerçeveleriyle uyumludur.

### Aspose.Tasks tüm Microsoft Project dosya sürümlerini destekliyor mu?
Aspose.Tasks, MPP, MPT, XML ve daha fazlası dahil olmak üzere tüm Microsoft Project dosya sürümlerini destekler.

### Aspose.Tasks ile proje takvimlerini manipüle edebilir miyim?
Kesinlikle, Aspose.Tasks görevler, kaynaklar, takvimler ve daha fazlası dahil olmak üzere proje takvimlerini manipüle etmek için kapsamlı özellikler sunar.

### Aspose.Tasks desteği için bir topluluk forumu var mı?
Evet, Aspose.Tasks topluluk forumunda [buradan](https://forum.aspose.com/c/tasks/15) yardım bulabilir ve diğer kullanıcılarla etkileşime geçebilirsiniz.

### Aspose.Tasks değerlendirme amaçlı geçici lisanslar sunuyor mu?
Evet, değerlendirme için geçici bir lisansı [buradan](https://purchase.aspose.com/temporary-license/) edinebilirsiniz.

## Ek SSS

**S:** Çıktıyı yüzde işaretiyle gösterecek şekilde nasıl biçimlendiririm?  
**C:** `res.get(Rsc.PERCENT_WORK_COMPLETE)` ile sayısal değeri alın ve `String.format("%.2f%%", value)` kullanarak biçimlendirin.

**S:** Yüzde 50 %’nin altında olan kaynakları filtreleyebilir miyim?  
**C:** Evet, yazdırmadan önce `res.get(Rsc.PERCENT_WORK_COMPLETE) < 50` koşulunu kontrol eden bir `if` ekleyin.

**S:** Yüzdeleri Project dosyasına geri yazmak mümkün mü?  
**C:** `Rsc.PERCENT_WORK_COMPLETE` alanı yalnızca‑okunur; bunun yerine görev atamalarını ayarlamanız gerekir.

**S:** Bu, Project Online (bulut) dosyalarıyla çalışır mı?  
**C:** Öncelikle .mpp dosyasını yerel olarak indirmeniz gerekir; Aspose.Tasks dosya formatıyla çalışır, bulut hizmetiyle doğrudan etkileşime girmez.

## Aspose.Tasks Kullanımının Sayısal Yararları
Aspose.Tasks **30+ dosya formatını** (MPP, MPT, XML, CSV vb.) destekler ve **10.000’e kadar görev** içeren projeleri, verileri akış halinde işleyerek bellek kullanımını 200 MB’nin altında tutarak işleyebilir. Kütüphanenin **salt‑okunur `Rsc.PERCENT_WORK_COMPLETE`** alanı O(n) sürede hesaplanır; bu, büyük takvimlerde bile hızlı veri alımını garanti eder.

## Sonuç
Bu rehberde Aspose.Tasks kullanarak **Java'da kaynak yüzde nasıl hesaplanır** konusunu gösterdik; odak noktamız her kaynak için *tamamlanan iş yüzdesi* değerini almaktı. Yukarıdaki adımları izleyerek Java uygulamalarınıza kesin kaynak‑yüzde analizleri ekleyebilir, proje sağlığı ve kaynak kullanımı hakkında daha iyi bir görünürlük elde edebilirsiniz.

---

**Son Güncelleme:** 2026-06-15  
**Test Edilen:** Aspose.Tasks for Java 24.10  
**Yazar:** Aspose

## İlgili Eğitimler

- [Aspose.Tasks for Java ile projeye kaynak ekleme](/tasks/java/resource-management/create-resources/)
- [Aspose.Tasks for Java ile MS Project kaynak maliyetlerini yönetme](/tasks/java/resource-management/resource-cost/)
- [Aspose.Tasks'te görevler için yüzde tamamlama hesaplamaları](/tasks/java/task-properties/percentage-complete-calculations/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}