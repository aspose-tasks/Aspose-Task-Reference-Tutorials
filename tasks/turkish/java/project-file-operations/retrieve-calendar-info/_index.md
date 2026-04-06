---
date: 2026-03-27
description: Aspose ve Aspose.Tasks'i kullanarak Java ile Microsoft Project dosyalarından
  proje takvim detaylarını nasıl çıkaracağınızı öğrenin. Adım adım kod örnekli rehber.
linktitle: Retrieve Calendar Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks'i Kullanarak MS Project Takvim Bilgilerini Nasıl Alabilirsiniz
url: /tr/java/project-file-operations/retrieve-calendar-info/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks'i Kullanarak MS Project Takvim Bilgilerini Alma

## Introduction
Bu öğreticide, **Aspose.Tasks'i nasıl kullanacağınızı** keşfedecek ve Microsoft Project dosyalarından takvim bilgilerini programlı olarak nasıl alacağınızı öğreneceksiniz. Çalışma günleri, saatleri ve istisnalar gibi takvim verilerine erişmek, raporlama, entegrasyon veya özel zamanlama mantığı için **proje takvimini çıkarmak** gerektiğinde hayati öneme sahiptir. Süreci adım adım inceleyeceğiz ve **Aspose**'u bir *.mpp* dosyasından bu verileri çekmek için **nasıl kullanacağınızı** tam olarak göreceksiniz.

## Quick Answers
- **Bu öğreticide hangi kütüphane kullanılıyor?** Aspose.Tasks for Java.  
- **Hangi anahtar kelime ele alınıyor?** *how to use aspose*.  
- **Ne çıkarabilirsiniz?** Çalışma günleri ve saatleri dahil olmak üzere proje takvimleri.  
- **Lisans gerekir mi?** Ücretsiz deneme mevcuttur; üretim için lisans gereklidir.  
- **Hangi Java sürümü destekleniyor?** Java 8 veya üzeri.

## What is Aspose.Tasks and Why Use It?
Aspose.Tasks, geliştiricilerin Microsoft Project dosyalarını Microsoft Project'e ihtiyaç duymadan okuyup yazmasına ve manipüle etmesine olanak tanıyan güçlü bir Java API'sidir. Aspose.Tasks'i kullanarak **takvim bilgilerini nasıl çıkaracağınızı**, zaman çizelgesi hesaplamalarını otomatikleştirebilir ve proje verilerini diğer kurumsal sistemlerle saf Java kodu üzerinden entegre edebilirsiniz.

## Why extract project calendar information?
Proje takvimleri görev tarihlerini, kaynak tahsislerini ve genel zaman çizelgesi hesaplamalarını yönlendirir. Bu verileri çıkararak şunları yapabilirsiniz:
- Gerçek çalışma programlarını yansıtan özel raporlar oluşturmak.  
- Microsoft Project zaman çizelgelerini dış sistemlerle (ERP, BI vb.) senkronize etmek.  
- Takvim ayarlarını programlı olarak değiştirerek “ne olurdu” analizleri yapmak.  
- **MS Project takvim** verilerini diğer planlama araçlarına geçiş için çıkarmak.

## Prerequisites
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

- Java programlamaya temel aşinalık.  
- Sisteminizde Java Development Kit (JDK) kurulu.  
- Aspose.Tasks for Java kütüphanesi. İndirmek için [burada](https://releases.aspose.com/tasks/java/) tıklayın.

## Import Packages
İlk olarak, gerekli Aspose.Tasks sınıflarını Java projenize içe aktarın.

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```

## Step 1: Set Data Directory
*.mpp* dosyanızın bulunduğu klasörü tanımlayın.

```java
String dataDir = "Your Data Directory";
```

`"Your Data Directory"` ifadesini **project.mpp** dosyanızın bulunduğu klasörün mutlak yolu ile değiştirin.

## Step 2: Define Time Units
İç zaman temsilini insan‑okunur saatlere dönüştürmeye yardımcı olacak sabitleri oluşturun.

```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

Bu değerler mikro saniyeler cinsindendir; Aspose.Tasks zamanı dahili olarak bu birimde saklar.

## Step 3: Create Project Instance
Microsoft Project dosyasını bir `Project` nesnesine yükleyin.

```java
Project project = new Project(dataDir + "project.mpp");
```

`Project` yapıcı (constructor) *.mpp* dosyasını ayrıştırır ve takvimler dahil tüm proje verilerini API üzerinden erişilebilir kılar.

## Step 4: Retrieve Calendars Information
Projede tanımlı takvim koleksiyonunu alın.

```java
CalendarCollection alCals = project.getCalendars();
```

Bir proje birden fazla takvim (standart, kaynak ve özel takvimler) içerebilir. Bu koleksiyon her birine erişim sağlar.

## Step 5: Iterate Through Calendars
Her takvimi döngüye alarak UID, ad ve çalışma günlerini ilgili saatlerle birlikte gösterin.

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

İç döngü her `WeekDay` nesnesini kontrol eder. Gün çalışma olarak işaretlendiyse, gün tipi (Monday, Tuesday, …) ve hesaplanan çalışma saatleri birlikte yazdırılır.

## Step 6: Display Completion Message
Çıkarma işleminin tamamlandığını bildirin.

```java
System.out.println("Process completed Successfully");
```

## Common Issues and Solutions
| Sorun | Neden Oluşur | Çözüm |
|-------|--------------|-------|
| **Takvimler döndürülmüyor** | Proje dosyası herhangi bir özel takvim içermiyor olabilir. | *.mpp* dosyasının gerçekten takvim tanımladığını doğrulayın veya Microsoft Project'te açarak kontrol edin. |
| **Yanlış çalışma saatleri** | Zaman dönüşüm sabitleri farklı bir Project sürümü için uyumsuz. | `OneSec`, `OneMin`, `OneHour` değerlerini, dahili zaman birimini değiştiren daha yeni bir Aspose.Tasks sürümü kullanıyorsanız ayarlayın. |
| **`NullPointerException` on `cal.getName()`** | Bazı takvim nesneleri null olabilir. | Özelliklere erişmeden önce null kontrolü ekleyin (zaten gösterildiği gibi). |

## Frequently Asked Questions

**Q: Aspose.Tasks'i diğer programlama dilleriyle kullanabilir miyim?**  
A: Evet, Aspose.Tasks .NET, C++, Python ve Java dahil birden çok platform ve programlama dili için destek sağlar.

**Q: Aspose.Tasks için ücretsiz deneme mevcut mu?**  
A: Evet, ücretsiz deneme sürümünü [burada](https://releases.aspose.com/) indirebilirsiniz.

**Q: Aspose.Tasks için destek nasıl alınır?**  
A: Aspose.Tasks topluluk forumundan [burada](https://forum.aspose.com/c/tasks/15) destek alabilirsiniz.

**Q: Aspose.Tasks için geçici bir lisans satın alabilir miyim?**  
A: Evet, geçici lisansları [burada](https://purchase.aspose.com/temporary-license/) satın alabilirsiniz.

**Q: Aspose.Tasks için ayrıntılı belgeleri nereden bulabilirim?**  
A: Belgeleri [burada](https://reference.aspose.com/tasks/java/) inceleyebilirsiniz.

## Conclusion
Bu adımları izleyerek, **Aspose.Tasks'i kullanarak bir MS Project dosyasından proje takvim bilgilerini nasıl çıkaracağınızı** artık biliyorsunuz. Bu mantığı daha büyük uygulamalara entegre edebilir, raporlamayı otomatikleştirebilir veya takvimleri diğer kurumsal sistemlerle senkronize edebilirsiniz. **Aspose'i nasıl kullanacağınızı** öğrenmek, gelişmiş proje‑yönetimi otomasyon senaryolarının kapılarını açar.

---

**Last Updated:** 2026-03-27  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}