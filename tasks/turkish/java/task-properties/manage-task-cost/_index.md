---
date: 2026-02-20
description: Aspose.Tasks kullanarak Java’da proje maliyet sapmasını nasıl hesaplayacağınızı
  ve görev maliyetlerini nasıl yöneteceğinizi öğrenin. Maliyeti ayarlamak ve bütçeleri
  kontrol etmek için adım adım rehberimizi izleyin.
linktitle: Manage Task Costs in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java ile Proje Maliyet Varyansını Hesaplayın
url: /tr/java/task-properties/manage-task-cost/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks ile Proje Maliyet Varyansını Hesaplama

## Giriş
Bu kapsamlı öğreticide **proje maliyet varyansını nasıl hesaplayacağınızı** keşfedecek ve Aspose.Tasks ile Java uygulamalarınız içinde görev maliyetlerini verimli bir şekilde yöneteceksiniz. Küçük bir iç proje ya da büyük ölçekli bir kurumsal dağıtımı izliyor olun, maliyet varyansını anlamak bütçeleri kontrol altında tutmanıza ve aşırı harcamaları erken fark etmenize yardımcı olur.

## Hızlı Yanıtlar
- **Maliyet varyansı nedir?** Planlanan (sabit) maliyet ile gerçekleşen (kalan) maliyet arasındaki fark.  
- **Bir görevin maliyetini ayarlayan API yöntemi hangisidir?** `task.set(Tsk.COST, BigDecimal.valueOf(...))`.  
- **Geliştirme için lisansa ihtiyacım var mı?** Test için ücretsiz deneme çalışır; üretim için ticari lisans gereklidir.  
- **Proje seviyesindeki maliyet verilerini alabilir miyim?** Evet, kök görevin maliyet özelliklerine erişerek.  
- **Hangi Java sürümü destekleniyor?** Aspose.Tasks Java 8 ve üzeri sürümlerle çalışır.

## “Proje maliyet varyansını hesaplama” nedir?
Proje maliyet varyansını hesaplamak, bir görev veya proje için başlangıçta planladığınız **sabit maliyet** ile hâlâ yapılması gereken işi yansıtan **kalan maliyet** arasını karşılaştırmak anlamına gelir. Varyans, bütçenizin altında mı yoksa üzerinde mi olduğunu gösterir ve proaktif ayarlamalar yapmanıza olanak tanır.

## Proje maliyet varyansını hesaplamak için neden Aspose.Tasks kullanılmalı?
- **Tamamen .NET’siz Java API** – yerel kütüphanelere gerek yok.  
- **Zengin maliyet yönetimi özellikleri** (`COST`, `FIXED_COST`, `REMAINING_COST`, `COST_VARIANCE`).  
- **Mevcut Maven/Gradle projeleriyle kolay entegrasyon**.  
- **Doğru raporlama** ve MS Project® dosyalarına aktarılabilir.

## Önkoşullar
İlerlemeye başlamadan önce şunların olduğundan emin olun:

1. **Java Development Kit (JDK)** – Java 8 veya daha yeni bir sürüm yüklü.  
2. **Aspose.Tasks for Java kütüphanesi** – resmi siteden **[buradan](https://releases.aspose.com/tasks/java/)** indirin.  
3. Örnek kodu derlemek ve çalıştırmak için bir IDE veya derleme aracı (IntelliJ, Eclipse, Maven, Gradle).

## Paketleri İçe Aktarma
Projeler ve görevlerle çalışabilmek için gerekli Aspose.Tasks sınıflarını Java kaynak dosyanıza ekleyin.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.math.BigDecimal;
// Import Aspose.Tasks classes
```

## Adım Adım Kılavuz

### Adım 1: Projenizi Kurun
İlk olarak, yeni bir `Project` örneği oluşturun ve oluşturulan dosyaları saklayabileceğiniz bir klasöre işaret edin.

```java
// Set the path to your document directory
String dataDir = "Your Document Directory";
// Create a new project
Project project = new Project();
```

### Adım 2: Yeni Bir Görev Ekleyin
Kök görevin altına bir görev ekleyin. Maliyetleri burada atayacağız.

```java
// Add a new task to the root task
Task task = project.getRootTask().getChildren().add("Task");
```

### Adım 3: Görev Maliyetini Ayarlayın – **nasıl maliyet ayarlanır**
Göreve planlanan bir maliyet atayın. Gerçek bir senaryoda bu, bir bütçeleme elektronik tablosundan gelebilir.

```java
// Set the task cost to 800
task.set(Tsk.COST, BigDecimal.valueOf(800));
```

### Adım 4: Maliyet Bilgilerini Alın ve Görüntüleyin – **nasıl maliyet yönetilir**
Şimdi, hesaplanan maliyet varyansı da dahil olmak üzere çeşitli maliyet özelliklerini geri okuyacağız.

```java
// Retrieve and print task information
System.out.println("Remaining Cost: " + task.get(Tsk.REMAINING_COST));
System.out.println("Fixed Cost: " + task.get(Tsk.FIXED_COST));
System.out.println("Cost Variance: " + task.get(Tsk.COST_VARIANCE));
// Retrieve and print project-level cost information
System.out.println("Project Cost: " + project.getRootTask().get(Tsk.COST));
System.out.println("Project Fixed Cost: " + project.getRootTask().get(Tsk.FIXED_COST));
System.out.println("Project Remaining Cost: " + project.getRootTask().get(Tsk.REMAINING_COST));
System.out.println("Project Cost Variance: " + project.getRootTask().get(Tsk.COST_VARIANCE));
```

**Gördükleriniz:**  
- `Remaining Cost` henüz tamamlanmamış işi yansıtır.  
- `Fixed Cost` belirlediğiniz temel (bu örnekte 800).  
- `Cost Variance` otomatik olarak **Fixed – Remaining** olarak hesaplanır.  
- Aynı değerler proje (kök görev) seviyesinde de mevcuttur ve tüm görevlerde **proje maliyet varyansını hesaplamanıza** olanak tanır.

### Adım 5: Ek Görevler İçin Tekrarlayın (İsteğe Bağlı)
Projenizin birden fazla aşaması varsa, her görev için Adım 2‑4'ü tekrarlayın. Bireysel varyansları toplamak size genel proje maliyet varyansını verir.

## Yaygın Sorunlar ve Çözümler
| Sorun | Neden Oluşur | Çözüm |
|-------|--------------|-------|
| `NullPointerException` görev özelliklerine erişirken | Görev, proje hiyerarşisine eklenmemişti. | Maliyetleri ayarlamadan önce `project.getRootTask().getChildren().add(...)` çağırdığınızdan emin olun. |
| Maliyet değerleri `0` olarak görünüyor | `int` yerine `BigDecimal` kullanılıyor. | Her zaman gösterildiği gibi `BigDecimal.valueOf(...)` kullanın. |
| Beklenmeyen varyans (negatif) | `REMAINING_COST`, `FIXED_COST` değerini aşıyor. | İş ilerledikçe kalan maliyeti güncellediğinizden emin olun. |

## Sıkça Sorulan Sorular

**S: Aspose.Tasks for Java belgelerini nerede bulabilirim?**  
C: Belgeleri **[buradan](https://reference.aspose.com/tasks/java/)** erişebilirsiniz.

**S: Aspose.Tasks for Java kütüphanesini nasıl indirebilirim?**  
C: Kütüphaneyi **[buradan](https://releases.aspose.com/tasks/java/)** indirebilirsiniz.

**S: Aspose.Tasks for Java'ı nereden satın alabilirim?**  
C: **[Buradan](https://purchase.aspose.com/buy)** satın alabilirsiniz.

**S: Aspose.Tasks for Java için ücretsiz deneme mevcut mu?**  
C: Evet, ücretsiz denemeyi **[buradan](https://releases.aspose.com/)** alabilirsiniz.

**S: Aspose.Tasks for Java için destek nereden alabilirim?**  
C: Destek forumunu **[buradan](https://forum.aspose.com/c/tasks/15)** ziyaret edin.

---

**Son Güncelleme:** 2026-02-20  
**Test Edilen:** Aspose.Tasks for Java 24.12 (yazım anındaki en yeni sürüm)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}