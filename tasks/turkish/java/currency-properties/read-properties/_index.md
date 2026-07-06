---
date: 2026-02-07
description: Java için Aspose.Tasks kullanarak MS Project dosyalarından para birimi
  özelliklerini okuma ve para birimi simgesini çıkarma yöntemlerini öğrenin. Para
  birimi kodunu, simgesini, basamak sayısını ve konumunu programlı olarak çıkarmak
  için bu adım adım rehberi izleyin.
linktitle: Read Currency Properties Java with Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: Aspose.Tasks Projeleriyle Java'da Para Birimi Özelliklerini Okuma
url: /tr/java/currency-properties/read-properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks Projeleri ile Java’da Para Birimi Özelliklerini Okuma

## Introduction
Bu öğreticide, Aspose.Tasks for Java API'sini kullanarak Microsoft Project dosyalarından **read currency properties java** öğreneceksiniz. Aspose.Tasks, Microsoft Project yüklü olmadan .mpp dosyalarıyla çalışmanıza olanak tanır; bu da otomatik raporlama, veri taşıma veya Java‑tabanlı kurumsal uygulamalara entegrasyon için idealdir. Bu rehberin sonunda, bir proje dosyasından doğrudan para birimi kodunu, simgesini, ondalık basamak sayısını ve simge konumunu çıkarabileceksiniz.

## Quick Answers
- **“read currency properties java” ne anlama geliyor?** Bir MS Project dosyasından Java kodu kullanarak para birimiyle ilgili meta verileri (kod, simge, basamak sayısı, konum) almayı ifade eder.  
- **Bunu denemek için lisansa ihtiyacım var mı?** Aspose.Tasks'in ücretsiz deneme sürümü mevcuttur; üretim kullanımı için ticari lisans gereklidir.  
- **Hangi JDK sürümü gerekiyor?** Java 8 veya üzeri.  
- **Para birimi ayarlarını okuduktan sonra değiştirebilir miyim?** Evet, Aspose.Tasks para birimi özellikleri üzerinde hem okuma hem de yazma işlemlerine izin verir.  
- **Tüm .mpp sürümleriyle uyumlu mu?** API, Microsoft Project 2003‑2021 ile oluşturulmuş dosyaları destekler.

## What is read currency properties java?
Java’da para birimi özelliklerini okumak, bir Microsoft Project dosyasında para değerlerinin nasıl gösterileceğini tanımlayan proje‑seviyesi ayarlara erişmek anlamına gelir. Bu ayarlar ISO para birimi kodunu (ör. **USD**), simgesini (**$**), ondalık basamak sayısını ve simgenin miktardan önce mi yoksa sonra mı görüneceğini içerir.

## Why read currency properties java with Aspose.Tasks?
- **Microsoft Project kurulumu gerekmez** – API, Java destekleyen herhangi bir platformda çalışır.  
- **Hızlı, süreç içi çıkarma** – çok sayıda proje dosyasını toplu olarak işlemek için idealdir.  
- **Tam kontrol** – alınan değerleri özel raporlarla birleştirebilir veya ERP sistemlerine entegre edebilirsiniz.  
- **Sürüm arası destek** – Project 2003'ten en yeni 2021 sürümüne kadar .mpp dosyalarıyla çalışır.

## Prerequisites
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. **Java Development Kit (JDK)** – `PATH` içinde yapılandırılmış Java 8 veya daha yeni bir sürüm.  
2. **Aspose.Tasks for Java JAR** – en son kütüphaneyi [here](https://releases.aspose.com/tasks/java/) adresinden indirip projenizin sınıf yoluna ekleyin.

## Import Packages
Proje manipülasyonu için gerekli Aspose.Tasks ad alanını içe aktararak başlayın:

```java
import com.aspose.tasks.*;
```

## Step 1: Set Up Your Project Directory
Analiz etmek istediğiniz `.mpp` dosyasını içeren klasörü tanımlayın. Yolu bir değişkende tutmak kodun yeniden kullanılabilir olmasını sağlar:

```java
String dataDir = "Your Data Directory";
```

*`"Your Data Directory"` ifadesini `project.mpp` dosyasının bulunduğu klasörün mutlak ya da göreli yolu ile değiştirin.*

## Step 2: Create a Project Reader Instance
Microsoft Project dosyasını bir `Project` nesnesine yükleyin. Bu nesne, para birimi ayarları da dahil olmak üzere tüm proje özelliklerine erişim sağlar:

```java
Project project = new Project(dataDir + "project.mpp");
```

*Dosyanızın adı farklıysa `"project.mpp"` ifadesini buna göre değiştirin.*

## Step 3: Display Currency Properties
Şimdi `Prj` enum'ı kullanarak her bir para birimi niteliğini alın ve sonuçları konsola yazdırın. API, görüntüleme için stringe dönüştürülebilen nesneler döndürür:

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
- **Currency Symbol Position** – miktardan **önce** ise `0`, **sonra** ise `1`.

## How to extract currency symbol java?
Sadece simgeye ihtiyacınız varsa, `Prj.CURRENCY_SYMBOL` özelliğine odaklanabilirsiniz. Aynı `project.get(...)` çağrısı simgeyi döndürür; bu değeri saklayabilir, günlüğe kaydedebilir veya başka bir servise aktarabilirsiniz. Bu, finansal gösterge panoları veya yerelleştirilmiş UI bileşenleri için **extract currency symbol java** işlemi yapmanız gerektiğinde özellikle faydalıdır.

## Step 4: Process Completion
Çıkarma işleminin başarıyla tamamlandığını bildirin. Bu basit mesaj, kod daha büyük bir toplu işin parçası olarak çalıştığında faydalıdır:

```java
System.out.println("Process completed Successfully");
```

## Common Issues and Solutions
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **FileNotFoundException** | `dataDir` yolu hatalı veya dosya adı yanlış yazılmış. | Dizin dizesini kontrol edin ve belirtilen konumda `.mpp` dosyasının bulunduğundan emin olun. |
| **NullPointerException on `project.get(...)`** | Proje dosyası para birimi bilgisi içermiyor (olası değil) ya da özellik anahtarı yanlış. | Okumadan önce `project.contains(Prj.CURRENCY_CODE)` kullanarak varlığı kontrol edin. |
| **LicenseException** | Üretim ortamında geçerli bir Aspose.Tasks lisansı olmadan çalıştırılıyor. | `License license = new License(); license.setLicense("Aspose.Tasks.lic");` kodunu `Project` nesnesini oluşturmadan önce ekleyerek lisans dosyasını uygulayın. |

## Frequently Asked Questions

**Q: Aspose.Tasks tüm Microsoft Project sürümleriyle uyumlu mu?**  
A: Aspose.Tasks, Microsoft Project 2003‑2021 tarafından üretilen .mpp dosyalarını destekler; hem eski hem de en yeni formatları kapsar.

**Q: Aspose.Tasks kullanarak para birimi özelliklerini değiştirebilir miyim?**  
A: Evet, para birimi ayarlarını hem okuyabilir hem de yazabilirsiniz. `project.set(Prj.CURRENCY_CODE, "EUR");` kullanıp ardından projeyi kaydedin.

**Q: Aspose.Tasks ticari kullanım için uygun mu?**  
A: Kesinlikle. Bu bir ticari kütüphanedir; lisansı [here](https://purchase.aspose.com/buy) adresinden satın alabilirsiniz.

**Q: Aspose.Tasks ücretsiz deneme sunuyor mu?**  
A: Evet, tam işlevsel bir deneme sürümü [here](https://releases.aspose.com/) adresinden temin edilebilir.

**Q: Aspose.Tasks için yardım veya destek nereden alınabilir?**  
A: Resmi Aspose.Tasks forumu en iyi yardım kaynağıdır – [here](https://forum.aspose.com/c/tasks/15) adresini ziyaret edin.

## Additional FAQ (AI‑Optimized)

**Q: Java’da sadece para birimi simgesini programatik olarak nasıl çıkarabilirim?**  
A: `project.get(Prj.CURRENCY_SYMBOL)` çağrısını yapıp sonucu `String` tipine dönüştürün. Bu, proje dosyasında kullanılan tam simgeyi döndürür.

**Q: Şifre korumalı bir .mpp dosyasından para birimi özelliklerini okuyabilir miyim?**  
A: Evet. Şifreyi kabul eden `Project` yapıcı overload'ını kullanarak dosyayı yükleyin, ardından özellikleri aynı şekilde okuyun.

**Q: Çok sayıda proje dosyası işlediğimde ne tür bir performans bekleyebilirim?**  
A: Aspose.Tasks süreç içinde çalışır ve tipik bir .mpp dosyasını birkaç milisaniyede okur. Toplu işlemler için mümkün olduğunca aynı `Project` örneğini yeniden kullanmayı değerlendirin.

## Conclusion
Artık **read currency properties java** ve **extract currency symbol java** işlemlerini Aspose.Tasks for Java kullanarak bir MS Project dosyasından nasıl gerçekleştireceğinizi öğrendiniz. Bu yetenek, Microsoft Project'e bağımlı olmadan para birimi meta verilerini özel raporlara, finansal analizlere veya entegrasyon boru hatlarına dahil etmenizi sağlar. Özellikleri değiştirmeyi veya bu verileri diğer proje öznitelikleriyle birleştirerek daha zengin çözümler oluşturmayı deneyebilirsiniz.

---

**Last Updated:** 2026-02-07  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}