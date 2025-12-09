---
date: 2025-12-05
description: Aspose.Tasks for Java ile para birimi simgesini MPP'den çıkarma ve Java'da
  para birimi simgesini değiştirme yöntemlerini öğrenin. Proje yönetimi için para
  birimi simgesini Java'da hızlıca alın.
linktitle: Extract currency symbol mpp using Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java ile mpp dosyasından para birimi simgesini çıkar
url: /tr/java/currency/currency-symbols/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java kullanarak mpp para birimi simgesini çıkarma

## Giriş
Bu öğreticide Microsoft Project dosyasından **extract currency symbol mpp** işlemini yapacak ve Aspose.Tasks kütüphanesini kullanarak **change currency symbol java** ya da **retrieve currency symbol java** nasıl yapılacağını keşfedeceksiniz. Raporlama aracı oluşturuyor, Project verilerini bir finans sistemine entegre ediyor ya da UI'nizde doğru para birimi simgesini göstermeniz gerektiğinde, bu küçük ama önemli görevi ustalaşmak Java uygulamalarınızı daha sağlam ve kullanıcı‑dostu yapacaktır.

## Hızlı Yanıtlar
- **extract currency symbol mpp** ne anlama geliyor? Bu, MPP (Microsoft Project) dosyasında saklanan para birimi simgesini okuma anlamına gelir.  
- **Bu işlemi hangi kütüphane gerçekleştirir?** Aspose.Tasks for Java bu iş için basit bir API sağlar.  
- **Bir lisansa ihtiyacım var mı?** Geliştirme için ücretsiz deneme çalışır; üretim için ticari lisans gereklidir.  
- **Ne kadar sürer?** Aşağıdaki kodla bir dakikadan kısa sürede simgeyi alabilirsiniz.  
- **Simgesini de değiştirebilir miyim?** Evet – aynı `Prj.CURRENCY_SYMBOL` özelliğini kullanarak yeni bir değer atayabilirsiniz.

## “extract currency symbol mpp” nedir?
Microsoft Project, para birimi simgesini (ör. $, €, £) proje dosyası başlığında saklar. **extract currency symbol mpp** işlemi bu değeri okur, böylece programatik olarak görüntüleyebilir veya manipüle edebilirsiniz.

## Neden currency symbol java değiştirilir?
Projeler sık sık birden fazla bölgeyi kapsar. Çalışma zamanında **change currency symbol java** yapabilmek, raporları, faturaları veya gösterge panellerini yerel pazara uyarlamanıza, tüm proje dosyasını yeniden oluşturmanıza gerek kalmadan olanak tanır.

## Önkoşullar
1. **Java Development Kit (JDK)** – sürüm 8 veya üzeri.  
2. **Aspose.Tasks for Java** – en son JAR'ı [Aspose.Tasks indirme sayfasından](https://releases.aspose.com/tasks/java/) indirin.  
3. Kodunuzdan referans alabileceğiniz bir klasöre yerleştirilmiş geçerli bir **project.mpp** dosyası.

## Paketleri İçe Aktarma
İlk olarak, Project dosyalarıyla çalışmak için ihtiyaç duyacağımız sınıfları içe aktarın.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Adım 1: Veri Dizinini Tanımlama
Uygulamaya *.mpp* dosyanızın nerede olduğunu söyleyin.

```java
String dataDir = "Your Data Directory";
```

> **Pro ipucu:** Her makinede çalışan mutlak bir yol oluşturmak için `System.getProperty("user.dir")` kullanın.

## Adım 2: MS Project Dosyasını Yükleme
Bellekte MPP dosyasını temsil eden bir `Project` nesnesi oluşturun.

```java
Project project = new Project(dataDir + "project.mpp");
```

## Adım 3: Para Birimi Simgesini Al (ve isteğe bağlı olarak değiştir)
Şimdi `Prj.CURRENCY_SYMBOL` özelliğini okuyarak **retrieve currency symbol java** yapıyoruz. Aynı özelliğe yeni bir dize atayarak **change currency symbol java** da yapabilirsiniz.

```java
// Retrieve the current currency symbol
System.out.println(project.get(Prj.CURRENCY_SYMBOL));

// Example of changing it (uncomment to use)
// project.set(Prj.CURRENCY_SYMBOL, "€");
// System.out.println("New symbol: " + project.get(Prj.CURRENCY_SYMBOL));
```

`System.out.println` çağrısı simgeyi (ör. `$`) konsola yazar, çıkarma işleminin başarılı olduğunu onaylar.

## Yaygın Sorunlar ve Çözümleri
| Symptom | Likely Cause | Solution |
|---------|--------------|----------|
| `NullPointerException` on `project.get(...)` | Yanlış dosya yolu veya dosya bulunamadı | `dataDir` ve dosya adını doğrulayın; hata ayıklamak için `new File(dataDir).exists()` kullanın |
| Unexpected symbol (e.g., `?`) | Proje standart dışı bir yerel ayarla oluşturulmuş | Kaynak MPP dosyasının gerçekten bir para birimi simgesi tanımladığından emin olun; yukarıda gösterildiği gibi programatik olarak bir tane ayarlayabilirsiniz |
| License error | Geçerli bir lisans dosyası olmadan deneme sürümünü kullanmak | `Project` nesnesini oluşturmadan önce lisansınızı `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` kodu ile yükleyin |

## Sık Sorulan Sorular

**S: Para birimi simgelerinin yanı sıra Aspose.Tasks ile diğer proje özelliklerini de manipüle edebilir miyim?**  
**C:** Evet, Aspose.Tasks görevleri, kaynakları, atamaları, takvimleri ve daha birçok proje özelliğini düzenlemenize olanak tanır.

**S: Aspose.Tasks farklı MS Project dosya sürümleriyle uyumlu mu?**  
**C:** Kesinlikle. Project 98'den en yeni sürümlere kadar MPP, MPT ve XML formatlarını destekler.

**S: Aspose.Tasks geliştiriciler için dokümantasyon ve destek sunuyor mu?**  
**C:** Kapsamlı API belgeleri, kod örnekleri ve özel bir destek forumu Aspose.Tasks web sitesinde mevcuttur.

**S: Aspose.Tasks'i satın almadan önce deneyebilir miyim?**  
**C:** Evet – tam işlevsel ücretsiz deneme sürümü [Aspose web sitesinden](https://purchase.aspose.com/buy) indirilebilir.

**S: Aspose.Tasks için geçici bir lisans nasıl alabilirim?**  
**C:** Değerlendirme amaçlı geçici lisanslar [Aspose geçici lisans sayfasında](https://purchase.aspose.com/temporary-license/) sağlanır.

---

**Son Güncelleme:** 2025-12-05  
**Test Edilen Sürüm:** Aspose.Tasks for Java 24.12 (yazım zamanındaki en son sürüm)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}