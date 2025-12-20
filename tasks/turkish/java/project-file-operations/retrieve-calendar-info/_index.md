---
date: 2025-12-20
description: Java kullanarak Aspose.Tasks'i Microsoft Project dosyalarından proje
  takvim detaylarını çıkarmak için nasıl kullanacağınızı öğrenin. Kod örnekleriyle
  adım adım rehber.
linktitle: Retrieve Calendar Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks'i Kullanarak MS Project Takvim Bilgilerini Nasıl Alabilirsiniz
url: /tr/java/project-file-operations/retrieve-calendar-info/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks Kullanarak MS Project Takvim Bilgilerini Nasıl Alabilirsiniz

## Giriş
Bu öğreticide, **Aspose.Tasks'i nasıl kullanacağınızı** keşfedecek ve Microsoft Project dosyalarından programlı olarak takvim bilgilerini alabileceksiniz. Çalışma günleri, saatler ve istisnalar gibi takvim verilerine erişmek, raporlama, entegrasyon veya özel zamanlama mantığı için **proje takvimini** çıkarmanız gerektiğinde çok önemlidir. Süreci adım adım inceleyelim.

## Hızlı Yanıtlar
- **Bu öğreticide hangi kütüphane kullanılıyor?** Aspose.Tasks for Java.  
- **Hangi anahtar kelime ele alınıyor?** *how to use aspose.tasks*.  
- **Ne çıkarabilirsiniz?** Çalışma günleri ve saatleri dahil olmak üzere proje takvimleri.  
- **Bir lisansa ihtiyacım var mı?** Ücretsiz deneme mevcuttur; üretim için bir lisans gereklidir.  
- **Hangi Java sürümü destekleniyor?** Java 8 veya üzeri.

## Neden proje takvim bilgilerini çıkarmalısınız?
Proje takvimleri görev tarihlerini, kaynak tahsislerini ve genel zaman çizelgesi hesaplamalarını yönlendirir. Bu verileri çıkararak şunları yapabilirsiniz:
- Gerçek çalışma programlarını yansıtan özel raporlar oluşturun.  
- Microsoft Project zaman çizelgelerini dış sistemlerle (ERP, BI vb.) senkronize edin.  
- Takvim ayarlarını programlı olarak değiştirerek ne‑olur analizi yapın.

## Önkoşullar
Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

- Java programlamada temel bilgi.  
- Sisteminizde yüklü Java Development Kit (JDK).  
- Aspose.Tasks for Java kütüphanesi. Bunu [buradan](https://releases.aspose.com/tasks/java/) indirebilirsiniz.

## Paketleri İçe Aktarma
İlk olarak, gerekli Aspose.Tasks sınıflarını Java projenize içe aktarın.

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```

## Adım 1: Veri Dizinini Ayarlama
*.mpp* dosyanızı içeren klasörü tanımlayın.

```java
String dataDir = "Your Data Directory";
```

`"Your Data Directory"` ifadesini **project.mpp** dosyasının bulunduğu klasörün mutlak yolu ile değiştirin.

## Adım 2: Zaman Birimlerini Tanımlama
İç zaman temsilini insan‑okunur saatlere dönüştürmeye yardımcı olacak sabitleri oluşturun.

```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

Bu değerler mikro saniye cinsindendir; Aspose.Tasks zamanı dahili olarak bu şekilde depolar.

## Adım 3: Proje Örneği Oluşturma
Microsoft Project dosyasını bir `Project` nesnesine yükleyin.

```java
Project project = new Project(dataDir + "project.mpp");
```

`Project` yapıcı (constructor) *.mpp* dosyasını ayrıştırır ve takvimler dahil tüm proje verilerini API üzerinden erişilebilir kılar.

## Adım 4: Takvim Bilgilerini Almak
Projede tanımlı takvim koleksiyonunu elde edin.

```java
CalendarCollection alCals = project.getCalendars();
```

Bir proje birden fazla takvim (standart, kaynak ve özel takvimler) içerebilir. Bu koleksiyon her birine erişim sağlar.

## Adım 5: Takvimler Üzerinde Döngü
Her takvim üzerinde döngü yapın, UID'sini, adını ve ilgili saatlerle çalışma günlerini gösterin.

```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        // Calendar Information
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        // Iterate Through WeekDays
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); // Time in milliseconds
            double time = ts / (OneHour); // Convert to hours
            if (wd.getDayWorking()) {
                // Display Working Days and Hours
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```

İç döngü her `WeekDay` nesnesini kontrol eder. Gün çalışma olarak işaretlendiyse, gün tipini (Monday, Tuesday, …) hesaplanan çalışma saatleriyle birlikte yazdırır.

## Adım 6: Tamamlanma Mesajını Görüntüleme
Çıkarma işleminin tamamlandığını bildirin.

```java
System.out.println("Process completed Successfully");
```

## Sonuç
Bu adımları izleyerek, **Java kullanarak bir MS Project dosyasından proje takvim bilgilerini çıkarmak için Aspose.Tasks'i nasıl kullanacağınızı** artık biliyorsunuz. Bu mantığı daha büyük uygulamalara entegre edebilir, raporlamayı otomatikleştirebilir veya takvimleri diğer kurumsal sistemlerle senkronize edebilirsiniz.

## Sıkça Sorulan Sorular

**S: Aspose.Tasks'i diğer programlama dilleriyle kullanabilir miyim?**  
C: Evet, Aspose.Tasks .NET, C++, Python ve Java dahil birden fazla platform ve programlama dilini destekler.

**S: Aspose.Tasks için ücretsiz deneme sürümü mevcut mu?**  
C: Evet, ücretsiz deneme sürümünü [buradan](https://releases.aspose.com/) indirebilirsiniz.

**S: Aspose.Tasks için destek nasıl alabilirim?**  
C: Aspose.Tasks topluluk forumundan [burada](https://forum.aspose.com/c/tasks/15) destek alabilirsiniz.

**S: Aspose.Tasks için geçici bir lisans satın alabilir miyim?**  
C: Evet, geçici lisanslar [buradan](https://purchase.aspose.com/temporary-license/) satın alınabilir.

**S: Aspose.Tasks için ayrıntılı belgeleri nerede bulabilirim?**  
C: Belgeleri [buradan](https://reference.aspose.com/tasks/java/) inceleyebilirsiniz.

---

**Son Güncelleme:** 2025-12-20  
**Test Edilen:** Aspose.Tasks for Java 24.12 (yazım anındaki en son sürüm)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}