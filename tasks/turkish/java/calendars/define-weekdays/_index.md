---
date: 2025-12-02
description: Aspose.Tasks for Java kullanarak takvim ayarlamayı, MS Project'te hafta
  içi günlerini tanımlamayı ve özel çalışma günlerini ayarlamayı öğrenin. Projeyi
  sadece birkaç satır kodla XML olarak kaydedin.
language: tr
linktitle: How to Set Calendar and Define Weekdays in MS Project with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks ile MS Project’te Takvim Nasıl Ayarlanır ve Haftanın Günleri Nasıl
  Tanımlanır
url: /java/calendars/define-weekdays/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Project'te Takvim Ayarlama ve Hafta Günlerini Tanımlama Aspose.Tasks ile

## Giriş
Bu öğreticide, Aspose.Tasks Java kütüphanesini kullanarak bir Microsoft Project dosyasında **takvim ayarlarını programlı olarak nasıl ayarlayacağınızı** ve hafta günlerini nasıl tanımlayacağınızı keşfedeceksiniz. Standart bir çalışma haftası oluşturmanız, hafta sonu çalışma günleri eklemeniz veya kısa bir Cuma programı yapılandırmanız gerekse, bu rehber proje oluşturulmasından dosyanın XML olarak kaydedilmesine kadar her adımı size gösterir.

## Hızlı Yanıtlar
- **Hangi kütüphane gerekiyor?** Aspose.Tasks for Java  
- **Hafta sonu çalışma günleri ekleyebilir miyim?** Evet – sadece Cumartesi ve Pazar'ı çalışma günü olarak ekleyin.  
- **Projeyi nasıl kaydederim?** `prj.save(..., SaveFileFormat.Xml)` kullanın.  
- **Lisans gerekiyor mu?** Değerlendirme için ücretsiz deneme çalışır; üretim için lisans gereklidir.  
- **Hangi Java sürümü gerekli?** Java 8 veya üzeri.

## “Takvim ayarlama” MS Project bağlamında ne anlama geliyor?
MS Project'te bir takvim ayarlamak, hangi günlerin çalışma günü olduğunu, günlük çalışma saatlerini ve tatil gibi istisnaları tanımlamak anlamına gelir. Bu takvim, görev zamanlamasını, kaynak tahsislerini ve genel proje takvimlerini yönlendirir.

## Takvim manipülasyonu için Aspose.Tasks neden tercih edilmeli?
- **Tam kontrol** – UI açmadan programlı olarak takvimleri oluşturabilir, değiştirebilir veya silebilirsiniz.  
- **Çapraz platform** – Java'yı destekleyen herhangi bir işletim sisteminde çalışır.  
- **Tüm dosya formatlarını destekler** – MPP, MPT ve XML; böylece *projeyi XML olarak kaydedebilir* ve diğer sistemlerle kolay entegrasyon sağlayabilirsiniz.  
- **COM bağımlılığı yok** – Microsoft Project Interop kütüphanesinin aksine.

## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. **Java Development Kit (JDK) 8+** – [Oracle web sitesinden](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) indirin.  
2. **Aspose.Tasks for Java** – En yeni JAR dosyasını [Aspose.Tasks indirme sayfasından](https://releases.aspose.com/tasks/java/) temin edin.  
3. Projenizin sınıf yoluna Aspose.Tasks JAR'ını eklemek için bir IDE veya yapı aracı (Maven/Gradle).

## Paketleri İçe Aktarma
İlk olarak, ihtiyacınız olan sınıfları içe aktarın. Bu importlar, proje, takvim ve çalışma‑zamanı nesnelerine erişmenizi sağlar.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

## Adım‑Adım Kılavuz

### Adım 1: Proje Örneği Oluşturma
Yeni bir `Project` nesnesi oluşturun. Bu nesne, düzenleyeceğiniz MS Project dosyasını temsil eder.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```

### Adım 2: Yeni Takvim Tanımlama
Projeye yeni bir takvim ekleyin. Birden fazla takviminiz olduğunda açık bir ad vermek faydalıdır.

```java
Calendar cal = prj.getCalendars().add("Calendar1");
```

### Adım 3: Standart Çalışma Günlerini (Pazartesi‑Perşembe) Ekleyin
Yerleşik yardımcı `WeekDay.createDefaultWorkingDay` metodunu kullanarak temel çalışma haftası için varsayılan 09:00‑17:00 programını ayarlayın.

```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```

### Adım 4: Hafta Sonu Çalışma Günlerini Ekleyin
Projeniz hafta sonları da çalışıyorsa, Cumartesi ve Pazar'ı normal çalışma günleri olarak ekleyin. Bu, **hafta sonu çalışma günleri ekleme** örneğidir.

```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```

### Adım 5: Özel Kısa Çalışma Günü (Cuma) Ayarlama
Burada **Cuma için özel çalışma günleri** belirliyoruz: sabah vardiyası (09:00‑12:00) ve öğleden sonra vardiyası (13:00‑16:00).

```java
WeekDay myWeekDay = new WeekDay(DayType.Friday);
WorkingTime wt1 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 9, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 12, 0, 0).getTime()
);
WorkingTime wt2 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 13, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 16, 0, 0).getTime()
);
myWeekDay.getWorkingTimes().add(wt1);
myWeekDay.getWorkingTimes().add(wt2);
myWeekDay.setDayWorking(true);
cal.getWeekDays().add(myWeekDay);
```

### Adım 6: Projeyi XML Olarak Kaydetme
Son olarak değişiklikleri kalıcı hale getirin. `SaveFileFormat.Xml` seçeneği, **projeyi XML olarak kaydetmenizi** sağlar; bu, diğer araçlarla entegrasyon için faydalıdır.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Yaygın Sorunlar & Çözümler
| Sorun | Çözüm |
|-------|----------|
| **Çalışma zamanları uygulanmadı** | Özel `WeekDay` üzerinde `setDayWorking(true)` çağrısının yapıldığından emin olun. |
| **Kaydederken dosya bulunamadı** | `dataDir`'in mevcut bir klasöre işaret ettiğini ve uygulamanızın yazma iznine sahip olduğunu doğrulayın. |
| **Takvim görevlerde yansımıyor** | Yeni oluşturulan takvimi kaynaklara veya görevlere `task.setCalendar(cal)` ile atayın. |

## Sık Sorulan Sorular

**S: Aspose.Tasks for Java ile özel çalışmayan günler tanımlayabilir miyim?**  
C: Evet. Çalışmayan gün olarak görmek istediğiniz herhangi bir `WeekDay` için `DayWorking` özelliğini `false` olarak ayarlayın.

**S: Tatil günleri veya şirket çapında istisnalar nasıl eklenir?**  
C: `CalendarException` nesneleri oluşturun, istisna tarihlerini belirleyin ve `cal.getExceptions()` koleksiyonuna ekleyin.

**S: Kütüphane eski MS Project sürümleriyle uyumlu mu?**  
C: Kesinlikle. Aspose.Tasks, çeşitli Project sürümlerinde MPP, MPT ve XML formatlarını destekler.

**S: İçe aktarılan bir projedeki mevcut takvimi değiştirebilir miyim?**  
C: `new Project("existing.mpp")` ile projeyi yükleyin, istediğiniz takvimi alın, değişiklikleri yapın ve kaydedin.

**S: Aspose.Tasks yinelemeli görevleri de yönetebiliyor mu?**  
C: Evet, `RecurringTask` sınıfını kullanarak yinelemeli görevler oluşturabilir ve düzenleyebilirsiniz.

## Sonuç
Artık **takvim ayarlama** ayarlarını, **MS Project'te hafta günlerini tanımlamayı**, hafta sonu çalışma günlerini eklemeyi ve kısa bir Cuma programı oluşturmayı Aspose.Tasks for Java ile nasıl yapacağınızı biliyorsunuz. Sonucu XML olarak kaydedin ve takvim mantığını herhangi bir Java‑tabanlı proje yönetim çözümüne entegre edin.

---

**Son Güncelleme:** 2025-12-02  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.11  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}