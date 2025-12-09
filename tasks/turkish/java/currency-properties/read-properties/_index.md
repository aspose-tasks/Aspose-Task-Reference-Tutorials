---
date: 2025-12-04
description: Aspose.Tasks for Java kullanarak MS Project dosyalarından para birimi
  özelliklerini Java’da nasıl okuyacağınızı öğrenin. Para birimi kodunu, sembolünü,
  basamak sayısını ve konumunu programlı olarak çıkarmak için bu adım‑adım kılavuzu
  izleyin.
linktitle: Read Currency Properties Java with Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: Java ile Aspose.Tasks Projelerinde Para Birimi Özelliklerini Okuma
url: /tr/java/currency-properties/read-properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks Projeleri ile Java'da Para Birimi Özelliklerini Okuma

## Giriş
Bu öğreticide **read currency properties Java**'ı Microsoft Project dosyalarından Aspose.Tasks for Java API'si kullanarak okuyacaksınız. Aspose.Tasks, Microsoft Project yüklü olmadan .mpp dosyalarıyla çalışmanıza olanak tanır; bu da otomatik raporlama, veri taşıma veya Java tabanlı kurumsal uygulamalara entegrasyon için idealdir. Bu rehberin sonunda, bir proje dosyasından para birimi kodunu, sembolünü, ondalık basamak sayısını ve sembol konumunu doğrudan çıkarabileceksiniz.

## Hızlı Yanıtlar
- **“read currency properties java” ne anlama geliyor?** Bir MS Project dosyasından Java kodu kullanarak para birimiyle ilgili meta verileri (kod, sembol, basamak sayısı, konum) almayı ifade eder.  
- **Bunu denemek için lisansa ihtiyacım var mı?** Aspose.Tasks'in ücretsiz deneme sürümü mevcuttur; üretim kullanımı için ticari lisans gereklidir.  
- **Hangi JDK sürümü gerekiyor?** Java 8 veya daha yenisi.  
- **Para birimi ayarlarını okuduktan sonra değiştirebilir miyim?** Evet, Aspose.Tasks para birimi özellikleri üzerinde okuma ve yazma işlemlerine izin verir.  
- **Bu, tüm .mpp sürümleriyle uyumlu mu?** API, Microsoft Project 2003‑2021 ile oluşturulmuş dosyaları destekler.

## read currency properties java nedir?
Java'da para birimi özelliklerini okumak, bir Microsoft Project dosyasında para değerlerinin nasıl görüntüleneceğini tanımlayan proje‑seviyesi ayarlara erişmek anlamına gelir. Bu ayarlar ISO para birimi kodunu (ör. **USD**), sembolü (**$**), ondalık basamak sayısını ve sembolün miktardan önce mi yoksa sonra mı görüneceğini içerir.

## Aspose.Tasks ile read currency properties java neden okunur?
- **Microsoft Project kurulumu gerekmez** – API, Java destekleyen herhangi bir platformda çalışır.  
- **Hızlı, aynı süreçte çıkarım** – büyük sayıda proje dosyasının toplu işlenmesi için idealdir.  
- **Tam kontrol** – elde edilen değerleri özel raporlarla birleştirebilir veya ERP sistemlerine entegre edebilirsiniz.  
- **Sürüm geçişi desteği** – Project 2003'ten en yeni 2021 sürümüne kadar .mpp dosyalarıyla çalışır.

## Önkoşullar
Başlamadan önce şunların kurulu olduğundan emin olun:

1. **Java Development Kit (JDK)** – Java 8 veya daha yenisi yüklü ve `PATH` içinde yapılandırılmış.  
2. **Aspose.Tasks for Java JAR** – en son kütüphaneyi [buradan](https://releases.aspose.com/tasks/java/) indirip projenizin sınıf yoluna ekleyin.  

## Paketleri İçe Aktarma
Proje manipülasyonu için gerekli Aspose.Tasks ad alanını içe aktararak başlayın:

```java
import com.aspose.tasks.*;
```

## Adım 1: Proje Dizinini Ayarlama
`.mpp` dosyanızın bulunduğu klasörü tanımlayın. Yolu bir değişkende tutmak kodun yeniden kullanılabilir olmasını sağlar:

```java
String dataDir = "Your Data Directory";
```

*`"Your Data Directory"` ifadesini `project.mpp` dosyasının bulunduğu klasörün mutlak ya da göreli yolu ile değiştirin.*

## Adım 2: Proje Okuyucu Örneği Oluşturma
Microsoft Project dosyasını bir `Project` nesnesine yükleyin. Bu nesne, para birimi ayarları da dahil olmak üzere tüm proje özelliklerine erişim sağlar:

```java
Project project = new Project(dataDir + "project.mpp");
```

*Dosyanızın adı farklıysa `"project.mpp"` ifadesini buna göre değiştirin.*

## Adım 3: Para Birimi Özelliklerini Görüntüleme
Şimdi `Prj` enum'ı kullanarak her para birimi özniteliğini alın ve sonuçları konsola yazdırın. API, görüntüleme için string'e dönüştürülebilen nesneler döndürür:

```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position : " + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```

**Gördükleriniz:**  
- **Currency Code** – `USD`, `EUR`, `JPY` gibi ISO‑4217 kodları.  
- **Currency Digits** – çoğu para birimi için genellikle `2`, Japon Yen'i için `0`.  
- **Currency Symbol** – raporlarda gösterilen karakter (`$`, `€`, `¥`).  
- **Currency Symbol Position** – miktardan **önce** `0`, **sonra** `1` olarak temsil edilir.

## Adım 4: İşlem Tamamlanması
Çıkarma işleminin başarıyla bittiğini işaretleyin. Bu basit mesaj, kod daha büyük bir toplu işin parçası olarak çalıştığında faydalıdır:

```java
System.out.println("Process completed Successfully");
```

## Yaygın Sorunlar ve Çözümler
| Sorun | Neden Oluşur | Çözüm |
|-------|--------------|-------|
| **FileNotFoundException** | `dataDir` yolu hatalı veya dosya adı yanlış yazılmış. | Dizin dizesini kontrol edin ve belirtilen konumda `.mpp` dosyasının bulunduğundan emin olun. |
| **NullPointerException on `project.get(...)`** | Proje dosyası para birimi bilgisi içermiyor (olası değil) ya da özellik anahtarı yanlış. | Okumadan önce `project.contains(Prj.CURRENCY_CODE)` kullanarak varlığı kontrol edin. |
| **LicenseException** | Üretim ortamında geçerli bir Aspose.Tasks lisansı olmadan çalıştırılıyor. | `Project` nesnesini oluşturmadan önce `License license = new License(); license.setLicense("Aspose.Tasks.lic");` koduyla lisans dosyasını uygulayın. |

## Sıkça Sorulan Sorular

**S: Aspose.Tasks, Microsoft Project'in tüm sürümleriyle uyumlu mu?**  
C: Aspose.Tasks, Microsoft Project 2003‑2021 tarafından üretilen .mpp dosyalarını destekler; hem eski hem de en yeni formatları kapsar.

**S: Aspose.Tasks kullanarak para birimi özelliklerini değiştirebilir miyim?**  
C: Evet, para birimi ayarlarını okuyabilir ve yazabilirsiniz. Örneğin `project.set(Prj.CURRENCY_CODE, "EUR");` ardından projeyi kaydedin.

**S: Aspose.Tasks ticari kullanım için uygun mu?**  
C: Kesinlikle. Bu bir ticari kütüphanedir; lisansı [buradan](https://purchase.aspose.com/buy) satın alabilirsiniz.

**S: Aspose.Tasks ücretsiz deneme sunuyor mu?**  
C: Evet, tamamen işlevsel bir deneme sürümü [buradan](https://releases.aspose.com/) temin edilebilir.

**S: Aspose.Tasks için yardım veya destek nereden alınabilir?**  
C: Resmi Aspose.Tasks forumu en iyi yardım kaynağıdır – [burayı](https://forum.aspose.com/c/tasks/15) ziyaret edin.

## Sonuç
Artık Aspose.Tasks for Java kullanarak bir MS Project dosyasından **read currency properties java**'ı nasıl okuyacağınızı öğrendiniz. Bu yetenek, para birimi meta verilerini özel raporlar, finansal analizler veya entegrasyon boru hatlarına Microsoft Project'e bağımlı olmadan dahil etmenizi sağlar. Özellikleri değiştirmeyi veya bu verileri diğer proje öznitelikleriyle birleştirmeyi deneyerek daha zengin çözümler oluşturabilirsiniz.

---

**Son Güncelleme:** 2025-12-04  
**Test Edilen Sürüm:** Aspose.Tasks for Java 24.12 (yazım zamanındaki en yeni sürüm)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}