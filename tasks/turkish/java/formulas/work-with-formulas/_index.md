---
date: 2026-02-13
description: Tarihlerin arasındaki günleri nasıl hesaplayacağınızı, bir test projesi
  oluşturmayı ve Aspose.Tasks for Java kullanarak Microsoft Project dosyalarını manipüle
  ederken özel bir alan eklemeyi öğrenin.
linktitle: Work with Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks for Java ile tarihler arasındaki günleri hesaplayın
url: /tr/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for Java ile tarihler arasındaki günleri hesaplama

## Giriş
Bu eğitimde bir test projesi oluşturarak, özel bir alan ekleyerek ve Aspose.Tasks Java kütüphanesi aracılığıyla Microsoft Project formüllerini kullanarak **tarihler arasındaki günleri hesaplayacaksınız**. Programlama yoluyla takvim oluşturmanız, son tarihleri hesaplamanız veya raporlamayı otomatikleştirmeniz gerekse, Aspose.Tasks, masaüstü kurulumu olmadan Project verilerini programlı olarak manipüle etmenizi sağlar. Kılavuzun sonunda, genişletilmiş bir öznitelik tanımlayan, bir görev için son tarih belirleyen ve projeyi MPP dosyası olarak kaydeden çalıştırılabilir bir örnek elde edeceksiniz.

## Hızlı Yanıtlar
- **Bu eğitim neyi kapsıyor?** Bir test projesi oluşturma, özel bir alan ekleme, genişletilmiş bir öznitelik tanımlama ve tarihler arasındaki günleri hesaplamak için bir formül kullanarak görev son tarihi ayarlama.  
- **Hangi kütüphane gerekiyor?** Aspose.Tasks for Java (en son sürüm).  
- **Lisans gerekli mi?** Geliştirme için ücretsiz deneme çalışır; üretim için lisans gereklidir.  
- **Hangi IDE'yi kullanabilirim?** JDK 8+ destekleyen herhangi bir Java IDE (IntelliJ IDEA, Eclipse, VS Code).  
- **Uygulamanın süresi ne kadar?** Kodu kopyalayıp çalıştırmak yaklaşık 10‑15 dakika sürer.

## Aspose.Tasks'te “tarihler arasındaki günleri hesaplama” nedir?
Tarihler arasındaki günleri hesaplamak, bir Project formülünün bir tarih alanını (ör. **Finish**) diğer bir tarih alanından (ör. **Deadline**) çıkartarak sayısal gün farkını döndürmesi anlamına gelir. Bu, takvim kaymalarını izlemek, tampon süresini ölçmek veya özel raporlar oluşturmak için faydalıdır.

## Neden Aspose.Tasks ile Tarihler Arasındaki Günleri Hesaplamalısınız?
- **Full API coverage** – her Project, Task ve Resource özelliğine erişim.  
- **No Office installation required** – sunucularda, CI boru hatlarında ve Docker konteynerlerinde çalışır.  
- **Cross‑platform** – aynı Java kodu Windows, Linux ve macOS'ta çalışır.  
- **Robust formula engine** – `[Deadline] - [Finish]` gibi hesaplamaları doğrudan proje dosyası içinde tanımlamanıza olanak tanır.

## Bir görev için son tarih nasıl ayarlanır
Son tarih, bir görevin `Tsk.DEADLINE` alanında depolanır ve bir `java.util.Calendar` örneği kullanılarak atanabilir.

## Genişletilmiş öznitelik nasıl tanımlanır
Genişletilmiş öznitelik, formülünüzün sonucunu tutacak özel alandır. Bunu bir kez tanımlarsınız, okunabilirlik için bir takma ad (alias) verirsiniz ve ardından tarih çıkarma işlemini yapan bir formül eklersiniz.

## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- **Java Development Kit (JDK) 8+** – Oracle web sitesinden veya OpenJDK dağıtımından indirin.  
- **Aspose.Tasks for Java** – En son JAR dosyasını [Aspose.Tasks for Java indirme sayfasından](https://releases.aspose.com/tasks/java/) edinin ve projenizin sınıf yoluna veya Maven/Gradle bağımlılıklarına ekleyin.

## Paketleri İçe Aktarma
İhtiyacımız olan sınıfları ilk olarak içe aktaralım:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Adım‑Adım Kılavuz

### Adım 1: Özel Alanlı Bir Test Projesi Oluşturma
**Özel bir test projesi** oluşturup, daha sonra formül sonucunu tutacak bir özel alan ekleyerek başlıyoruz.

```java
Project project = CreateTestProjectWithCustomField();
```

> *Pro tip:* `CreateTestProjectWithCustomField()` minimal bir takvim oluşturur ve formül atamaya hazır bir genişletilmiş öznitelik kaydeder.

### Adım 2: Genişletilmiş Öznitelik Tanımlama (Özel Alan Ekleme)
Şimdi **genişletilmiş bir öznitelik** tanımlıyoruz – temelde özel alan – ve ona okunabilir bir takma ad veriyoruz. İşte **özel alan** ekleme mantığı burada gerçekleşir.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias**, alanı Project içinde okunabilir kılar.  
- **Formula**, bir görevin *Finish* (Bitiş) tarihi ile *Deadline* (Son tarih) arasındaki gün sayısını hesaplar – *tarihler arasındaki günleri hesaplama* işleminin çekirdeği.

### Adım 3: Bir Görev İçin Son Tarih Ayarlama (Deadline Görevi Ekle & Görev Son Tarihini Belirleme)
Şimdi belirli bir görevde *Deadline* özelliğini ayarlayarak **deadline görev** verisini ekliyoruz.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- `Calendar` örneği kesin son tarih anını tanımlar.  
- `set(Tsk.DEADLINE, …)` seçilen görev için **görev son tarihini ayarlar**.

### Adım 4: Projeyi Kaydetme (Microsoft Project Dosyasını Manipüle Etme)
Son olarak **Microsoft Project** dosyasını değişiklikleri bir MPP dosyasına kaydederek manipüle ediyoruz.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

`SaveFile.mpp` dosyasını Microsoft Project'te açarak özel alanı, formül sonucunu ve takvimde yansıtılan son tarihi görebilirsiniz.

## Yaygın Sorunlar ve Çözümler
| Sorun | Çözüm |
|-------|----------|
| **Formula not evaluating** | Özniteliğin `Formula` dizesinin doğru alan adlarını (ör. `[Deadline]`, `[Finish]`) kullandığından emin olun. |
| **Task not found** | Görev kimliğinin (`1` örnekte) mevcut olduğunu doğrulayın; hata ayıklamak için `project.getRootTask().getChildren().size()` kullanın. |
| **License exception** | Her API çağrısından önce geçerli bir Aspose.Tasks lisansı uygulayın (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Sıkça Sorulan Sorular

**S: Aspose.Tasks'i başka programlama dilleriyle kullanabilir miyim?**  
C: Evet, Aspose.Tasks .NET, Java ve diğer platformlar için API'ler sunar; böylece **Microsoft Project** dosyalarını tercih ettiğiniz dilde manipüle edebilirsiniz.

**S: Aspose.Tasks için ücretsiz bir deneme mevcut mu?**  
C: Kesinlikle. Tam işlevsel deneme sürümünü [Aspose.Tasks indirme sayfasından](https://releases.aspose.com/tasks/java/) indirebilirsiniz.

**S: Aspose.Tasks için ayrıntılı belgeleri nereden bulabilirim?**  
C: Resmi dokümantasyon [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/) adresinde bulunur.

**S: Aspose.Tasks için destek nasıl alınır?**  
C: Toplulukla soru sormak ve deneyim paylaşmak için [Aspose.Tasks forumunu](https://forum.aspose.com/c/tasks/15) ziyaret edin.

**S: Değerlendirme için geçici bir lisansa ihtiyacım var mı?**  
C: Kısa vadeli testler için geçici bir lisans mevcuttur; bir tane talep etmek için [buraya](https://purchase.aspose.com/temporary-license/) tıklayın.

**Son Güncelleme:** 2026-02-13  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.12 (yazım anındaki en son sürüm)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}