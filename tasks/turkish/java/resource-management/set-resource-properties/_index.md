---
date: 2026-01-18
description: Aspose.Tasks for Java kullanarak MS Project'te standart ücreti ve diğer
  kaynak özelliklerini nasıl ayarlayacağınızı, kaynak eklemeyi ve kaynakları verimli
  bir şekilde yönetmeyi öğrenin.
linktitle: Set Resource Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks'te Kaynaklar İçin Standart Ücreti Nasıl Ayarlarsınız
url: /tr/java/resource-management/set-resource-properties/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'te Kaynaklar İçin Standart Ücret Ayarlama

## Giriş
Microsoft Project dosyalarıyla etkileşim kurması gereken Java uygulamaları geliştiriyorsanız, **standart ücreti ayarlamak** en yaygın görevlerden biridir. Bu öğreticide **standart ücreti** ve diğer kaynak özelliklerini Aspose.Tasks for Java kullanarak nasıl ayarlayacağınızı öğreneceksiniz. Kılavuzun sonunda bir proje nesnesi oluşturabilecek, bir MS Project dosyasına kaynak ekleyebilecek ve MS Project kaynaklarını güvenle yönetebileceksiniz.

## Hızlı Yanıtlar
- **Bir Project dosyasıyla çalışmak için birincil sınıf nedir?** `Project`
- **Yeni bir kaynak ekleyen yöntem hangisidir?** `project.getResources().add()`
- **Standart ücret nasıl ayarlanır?** `rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(...))`
- **Üretim için lisans gerekir mi?** Evet, geçerli bir Aspose.Tasks lisansı gereklidir.
- **Hangi Java sürümü desteklenir?** Java 8+ (en yeni JDK önerilir).

## “Standart ücret ayarlama” nedir?
*Standart ücret ayarlama* işlemi, bir kaynağa varsayılan saatlik maliyet atar. Proje yöneticileri bu değeri işçilik maliyetlerini hesaplamak, maliyet raporları oluşturmak ve bütçeleri öngörmek için kullanır.

## Neden Aspose.Tasks ile ücret ayarlamalısınız?
- **Microsoft Project kurulumu gerekmez** – dosyaları doğrudan Java’dan manipüle edin.
- **Tam bütünlük** – fazla mesai ve maliyet oranları dahil tüm kaynak alanları korunur.
- **Çapraz platform** – Windows, Linux ve macOS’ta çalışır.
- **Otomasyon dostu** – toplu işleme veya CI boru hatlarıyla entegrasyon için idealdir.

## Önkoşullar
Başlamadan önce aşağıdakilerin kurulu olduğundan emin olun:

### Java Geliştirme Ortamı Kurulumu
1. JDK’yı kurun: Sisteminizde Java Development Kit (JDK) yüklü olmalı. İndirmek için [Oracle web sitesini](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) ziyaret edin.
2. IDE Kurulumu: IntelliJ IDEA, Eclipse veya NetBeans gibi bir Entegre Geliştirme Ortamı (IDE) seçin ve makinenize kurun.

### Aspose.Tasks for Java Kurulumu
1. Aspose.Tasks for Java’yı indirin: [indirme sayfasına](https://releases.aspose.com/tasks/java/) gidin ve en son Aspose.Tasks for Java sürümünü edinin.
2. Projeye Entegre Edin: Aspose.Tasks for Java kütüphanesini projenize bağımlılık olarak ekleyerek entegre edin.

## Paketleri İçe Aktarma
Başlamak için Aspose.Tasks for Java’dan gerekli paketleri projenize içe aktarmanız gerekir. Bu adım, gereken işlevselliğe erişmenizi sağlar.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import java.math.BigDecimal;
```

## Adım 1: Bir Project Nesnesi Oluşturma
**Project nesnesi** oluşturmak, herhangi bir MS Project manipülasyonunun ilk adımıdır. Bu nesne, proje dosyasının tamamını bellekte temsil eder.

```java
Project project = new Project();
```

## Adım 2: Bir Kaynak Ekleme (add resource ms project)
Şimdi **add resource MS Project** işlemini Resources koleksiyonunu kullanarak yapacağız. Kaynak adı, takviminiz için anlamlı herhangi bir şey olabilir.

```java
Resource rsc = project.getResources().add("Rsc");
```

## Adım 3: Kaynak Özelliklerini Ayarlama (how to set rates)
Burada **standart ücreti** ayarlıyor ve aynı zamanda fazla mesai ücretini nasıl belirleyeceğinizi gösteriyoruz. Bu ücretler, hassasiyeti korumak için `BigDecimal` değerleri olarak saklanır.

```java
// Set standard rate for the resource
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(15));
// Set overtime rate for the resource
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(20));
```

## Yaygın Sorunlar ve Çözümler
| Sorun | Neden Oluşur | Çözüm |
|-------|----------------|-----|
| `NullPointerException` `set` çağrılırken | Kaynak doğru eklenmemiş. | `project.getResources().add()` çağrısının null olmayan bir `Resource` döndürdüğünden emin olun. |
| Kayıtlı dosyada ücretler 0 görünüyor | `int` yerine `BigDecimal` kullanılmadı. | Para birimleri için her zaman `BigDecimal.valueOf()` kullanın. |
| Lisans bulunamadı | `Project` oluşturulmadan lisans dosyası yüklenmemiş. | Program başlangıcında lisansı yükleyin (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Sonuç
Bu adımları izleyerek **project nesnesi oluşturmayı**, **add resource MS Project** işlemini ve **standart ücreti** diğer kaynak özellikleriyle birlikte ayarlamayı öğrendiniz. Bu sayede maliyet hesaplamalarını otomatikleştirebilir, özel raporlar üretebilir ve Java’dan MS Project kaynaklarını tam olarak yönetebilirsiniz.

## SSS
### Aspose.Tasks for Java karmaşık MS Project dosyalarını işleyebilir mi?
Evet, Aspose.Tasks for Java, geniş görev hiyerarşilerine sahip karmaşık dosyalar dahil olmak üzere çok çeşitli MS Project dosya formatlarını işleyebilir.
### Aspose.Tasks for Java için ücretsiz deneme mevcut mu?
Evet, ücretsiz deneme sürümüne [buradan](https://releases.aspose.com/) ulaşabilirsiniz.
### Aspose.Tasks for Java desteğini nereden bulabilirim?
Aspose.Tasks for Java ile ilgili yardım ve tartışmalara [destek forumundan](https://forum.aspose.com/c/tasks/15) ulaşabilirsiniz.
### Aspose.Tasks for Java için geçici bir lisans nasıl alınır?
Değerlendirme amaçlı geçici lisansı [geçici lisans sayfasından](https://purchase.aspose.com/temporary-license/) temin edebilirsiniz.
### Aspose.Tasks for Java lisanslı sürümünü nereden satın alabilirim?
Lisanslı sürümü [satın alma sayfasından](https://purchase.aspose.com/buy) satın alabilirsiniz.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Son Güncelleme:** 2026-01-18  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.12 (yazım anındaki en yeni)  
**Yazar:** Aspose