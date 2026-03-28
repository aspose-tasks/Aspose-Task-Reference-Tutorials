---
date: 2026-01-28
description: Aspose.Tasks for Java kullanarak proje takvimini nasıl oluşturacağınızı,
  takvim istisnaları için hafta içi günlerini nasıl tanımlayacağınızı ve çalışmayan
  günler programını nasıl yöneteceğinizi öğrenin.
linktitle: Create Project Calendar Aspose – Define Weekdays for Calendar Exceptions
second_title: Aspose.Tasks Java API
title: Aspose Proje Takvimi Oluştur – Takvim İstisnaları için Hafta Günlerini Tanımla
url: /tr/java/calendar-exceptions/define-weekdays/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose Proje Takvimi Oluşturma – Takvim İstisnaları için Hafta Günlerini Tanımlama

### Giriş
**create project calendar aspose** oluşturmanız gerektiğinde, tatiller, özel vardiyalar veya geçici kapanışlar gibi standart dışı çalışma günlerini modelleyebilmelisiniz. Aspose.Tasks for Java, takvim tanımları üzerinde tam kontrol sağlar ve gerçek dünyadaki programları yansıtan istisnalar eklemenize olanak tanır. Bu öğreticide, takvim istisnaları için hafta günlerini tanımlamak için gereken adımları adım adım göstereceğiz, böylece proje zaman çizelgeleriniz doğru ve güvenilir kalır. Sonunda, bunun herhangi bir kurumsal proje için daha geniş bir **non‑working days schedule** stratejisine nasıl uyduğunu da göreceksiniz.

## Hızlı Yanıtlar
- **“create project calendar aspose” ne anlama geliyor?**  
  Aspose.Tasks kullanarak görev planlamasını yönlendiren özel bir takvim nesnesi oluşturmayı ifade eder.
- **Örneği çalıştırmak için lisansa ihtiyacım var mı?**  
  Geliştirme için ücretsiz deneme yeterlidir; üretim için ticari lisans gereklidir.
- **Hangi IDE'ler destekleniyor?**  
  IntelliJ IDEA, Eclipse, NetBeans veya Java 8+ destekleyen herhangi bir IDE.
- **Aynı takvime birden fazla istisna ekleyebilir miyim?**  
  Evet – ihtiyacınız kadar `CalendarException` nesnesi ekleyebilirsiniz.
- **Projeyi hangi dosya formatlarında kaydedebilirim?**  
  XML, MPP ve Aspose.Tasks tarafından desteklenen diğer çeşitli formatlar.

## Aspose.Tasks'te Proje Takvimi Nedir?
**Proje takvimi**, bir projenin çalışma günlerini ve saatlerini tanımlar. Görev başlangıç/bitiş tarihlerini, kaynak tahsislerini ve genel zaman çizelgesi hesaplamalarını etkiler. Takvimi özelleştirerek, takvimin şirket tatilleri veya hafta sonu çalışma politikaları gibi gerçek dünya kısıtlamalarına uymasını sağlarsınız.

## Neden takvim istisnaları için hafta günlerini tanımlamalıyız?
- **Doğru zaman çizelgeleri:** Görevler, çalışma olmayan olarak işaretlenen günlerde planlanmaz.
- **Kaynak planlaması:** Kaynaklar yalnızca geçerli çalışma günlerinde tahsis edilir.
- **Uyumluluk:** Proje takvimlerini organizasyon politikaları veya yasal tatillerle hizalar.

## Takvim İstisnalarıyla Non‑working Days Schedule
**non‑working days schedule** yönetirken, genellikle tatiller, bakım pencereleri veya diğer kara listelerinin bir ana listesini tutarsınız. Bu tarihleri `CalendarException` nesneleri olarak eklemek, kritik yol analizi ya da kaynak dengelemesi gibi tüm hesaplamaların bu kısıtlamalara otomatik olarak uymasını garanti eder. Bu yaklaşım manuel tarih ayarlamalarını ortadan kaldırır ve zaman çizelgesi sapma riskini azaltır.

## Ön Koşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. **Java Development Kit (JDK)** – sürüm 8 veya üzeri.  
2. **Aspose.Tasks for Java** – resmi [Aspose.Tasks Java download page](https://releases.aspose.com/tasks/java/) adresinden indirin.  
3. **Bir IDE** – IntelliJ IDEA, Eclipse, NetBeans veya herhangi bir Java‑uyumlu editör.  

## Aspose ile proje takvimi oluşturma – Takvim istisnaları için hafta günlerini tanımlama

### Adım‑Adım Kılavuz

### Adım 1: Gerekli Paketleri İçe Aktarın
Tarih işleme için Java’nın `GregorianCalendar` sınıfı ve temel Aspose.Tasks sınıflarına ihtiyacımız var.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

### Adım 2: Veri Dizinini Tanımlayın
Oluşturulan proje dosyasının kaydedileceği yeri belirtin.

```java
String dataDir = "Your Data Directory";
```

### Adım 3: Bir Project Örneği Oluşturun
Yeni bir `Project` nesnesi örnekleyin – bu, takvimler dahil tüm proje verilerinin konteyneridir.

```java
Project project = new Project();
```

### Adım 4: Bir Takvim Tanımlayın
Projeye özel bir takvim ekleyin. Bu takvim istisnalarımızı tutacak.

```java
Calendar cal = project.getCalendars().add("Calendar1");
```

### Adım 5: Hafta Günleri İstisnasını Tanımlayın
Bir `CalendarException` oluşturun ve bir gün aralığını (ör. Aralık ayının son haftası) çalışma dışı olarak işaretleyin.  
Örnek, istisnayı **24 Dec 2009** ile **31 Dec 2009** arasında ayarlar, bu günlerde çalışmayı devre dışı bırakır ve istisnayı günlük tipte ele alır.

```java
CalendarException except = new CalendarException();
except.setEnteredByOccurrences(false);
except.setFromDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 24, 0, 0, 0).getTime());
except.setToDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 31, 23, 59, 0).getTime());
except.setType(CalendarExceptionType.Daily);
except.setDayWorking(false);
cal.getExceptions().add(except);
```

### Adım 6: Projeyi Kaydedin
Özel takvimi ve istisnasını içeren projeyi bir XML dosyasına kalıcı hale getirin.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Yaygın Sorunlar ve Çözümler
| Sorun | Çözüm |
|-------|----------|
| **İstisna tarihleri uygulanmıyor** | `setEnteredByOccurrences(false)` ve doğru `FromDate/ToDate` değerlerini kullandığınızdan emin olun. |
| **Kaydedilen dosya boş** | `dataDir`'in yazılabilir bir klasöre işaret ettiğini ve dosya adının `.xml` ile bittiğini kontrol edin. |
| **Takvim görev planlamasında yansımıyor** | Takvimi görev veya kaynaklara `task.setCalendar(cal)` ya da `resource.setCalendar(cal)` ile atayın. |

## Sık Sorulan Sorular

**S: Aynı takvim içinde farklı hafta günleri için birden fazla istisna tanımlayabilir miyim?**  
C: Evet. Her ayrı dönem veya kural için `cal.getExceptions()` koleksiyonuna ek `CalendarException` nesneleri ekleyin.

**S: Aspose.Tasks for Java farklı Java IDE'leriyle uyumlu mu?**  
C: Kesinlikle. Kütüphane IntelliJ IDEA, Eclipse, NetBeans ve standart Java projelerini destekleyen herhangi bir IDE ile çalışır.

**S: Günlük istisnalar dışında başka istisna tiplerini özelleştirebilir miyim?**  
C: Evet. `CalendarExceptionType.Weekly`, `Monthly` veya `Yearly` kullanarak planlama ihtiyaçlarınıza uygun istisnalar oluşturabilirsiniz.

**S: Proje gereksinimlerine göre istisnaları dinamik olarak nasıl yönetebilirim?**  
C: İstisna nesnelerini programatik olarak oluşturun – örneğin, tatil tarihlerini bir veri tabanı veya yapılandırma dosyasından okuyup bir döngü içinde `CalendarException` örnekleri yaratın.

**S: Aspose.Tasks for Java için deneme sürümü mevcut mu?**  
C: Evet, ücretsiz deneme sürümünü [Aspose.Tasks Java download page](https://releases.aspose.com/tasks/java/) adresinden indirebilirsiniz.

## Sonuç
Bu adımları izleyerek artık **create project calendar aspose** nasıl yapılacağını ve tatilleri ya da özel çalışma dışı dönemleri doğru bir şekilde yansıtan hafta günü istisnalarını nasıl tanımlayacağınızı biliyorsunuz. Doğru takvim yapılandırması, gerçekçi zaman çizelgeleri, kaynak tahsisi ve proje başarısı için kritiktir. Özel takvimi görev veya kaynaklara ekleyerek ve diğer istisna tipleriyle deneyler yaparak herhangi bir proje için kapsamlı bir **non‑working days schedule** oluşturabilirsiniz.

---

**Son Güncelleme:** 2026-01-28  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.11  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}