---
date: 2026-07-29
description: Aspose.Tasks for Java ile bir proje takvimi oluşturarak çalışma dışı
  günleri nasıl planlayacağınızı, hafta içi istisnalarını tanımlamayı ve tatil takvimlerini
  yönetmeyi öğrenin.
keywords:
- schedule non working days
- how to define weekdays
- set non working days
- java calendar exceptions
lastmod: 2026-07-29
linktitle: Çalışma Dışı Günleri Planlama – Proje Takvimi Oluşturma Aspose
og_description: Aspose.Tasks for Java kullanarak çalışma dışı günleri planlayın. Hafta
  içi günlerini tanımlamayı, takvim istisnaları eklemeyi ve tatil takvimlerini verimli
  bir şekilde yönetmeyi öğrenin.
og_image_alt: 'Developer guide: schedule non working days with Aspose.Tasks Java'
og_title: Çalışma Dışı Günleri Planlama – Proje Takvimi Oluşturma Aspose
schemas:
- author: Aspose
  dateModified: '2026-07-29'
  description: Learn how to schedule non working days by creating a project calendar
    with Aspose.Tasks for Java, defining weekday exceptions and managing holiday schedules.
  headline: Schedule Non Working Days – Create Project Calendar Aspose
  type: TechArticle
- description: Learn how to schedule non working days by creating a project calendar
    with Aspose.Tasks for Java, defining weekday exceptions and managing holiday schedules.
  name: Schedule Non Working Days – Create Project Calendar Aspose
  steps:
  - name: Import Required Packages
    text: We need the core Aspose.Tasks classes and Java’s `GregorianCalendar` for
      date handling.
  - name: Define the Data Directory
    text: Specify where the generated project file will be saved.
  - name: Create a Project Instance
    text: '`Project` is the main object that holds all project data, including tasks,
      resources, and calendars.'
  - name: Define a Calendar
    text: '`Calendar` represents a schedule of working and non‑working times within
      a project.'
  - name: Define Weekdays Exception
    text: '`CalendarException` represents a period that is marked as non‑working in
      a calendar.'
  - name: Save the Project
    text: Persist the project, including the custom calendar and its exception, to
      an XML file.
  type: HowTo
- questions:
  - answer: Yes. Add additional `CalendarException` objects to `cal.getExceptions()`
      for each distinct period or rule.
    question: Can I define multiple exceptions for different weekdays within the same
      calendar?
  - answer: Absolutely. The library works with IntelliJ IDEA, Eclipse, NetBeans, and
      any IDE that supports standard Java projects.
    question: Is Aspose.Tasks for Java compatible with different Java IDEs?
  - answer: Yes. Use `CalendarExceptionType.Weekly`, `Monthly`, or `Yearly` to suit
      your scheduling needs.
    question: Can I customize exception types other than daily exceptions?
  - answer: Build the exception objects programmatically—e.g., read holiday dates
      from a database or configuration file and create `CalendarException` instances
      in a loop.
    question: How can I handle exceptions dynamically based on project requirements?
  - answer: Yes, you can download a free trial from the [Aspose.Tasks Java download
      page](https://releases.aspose.com/tasks/java/).
    question: Is there a trial version available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- schedule non working days
- Aspose.Tasks
- Java calendar exceptions
- project calendar
- non-working days
title: Çalışma Dışı Günleri Planlama – Proje Takvimi Oluşturma Aspose
url: /tr/java/calendar-exceptions/define-weekdays/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Çalışma Dışı Günleri Planla – Aspose Proje Takvimi Oluştur

### Giriş
Bir proje için **çalışma dışı günleri planlamak** gerektiğinde, tatilleri, özel vardiyaları veya geçici kapanışları doğrudan proje planına modelleyebilmelisiniz. Aspose.Tasks for Java, takvim tanımlamaları üzerinde tam kontrol sağlar ve gerçek‑dünya programlarını yansıtan istisnalar eklemenize olanak tanır. Bu öğreticide, takvim istisnaları için hafta günlerini tanımlamanın tam adımlarını göstereceğiz, böylece proje zaman çizelgeleriniz doğru ve güvenilir kalır. Sonunda, bu yaklaşımın herhangi bir kurumsal proje için daha geniş bir **çalışma dışı günler takvimi** stratejisine nasıl uyduğunu da göreceksiniz.

## Hızlı Yanıtlar
- **“Çalışma dışı günleri planlamak” ne anlama geliyor?**  
  Aspose.Tasks kullanarak belirli tarihleri çalışma dışı olarak işaretleyen bir takvim oluşturmak ve bu sayede görev tarihlerini otomatik olarak etkilemek anlamına gelir.  
- **Örneği çalıştırmak için lisansa ihtiyacım var mı?**  
  Geliştirme için ücretsiz deneme sürümü yeterlidir; üretim ortamı için ticari lisans gereklidir.  
- **Hangi IDE'ler destekleniyor?**  
  IntelliJ IDEA, Eclipse, NetBeans veya Java 8+ destekleyen herhangi bir IDE.  
- **Aynı takvime birden fazla istisna ekleyebilir miyim?**  
  Evet – ihtiyacınız kadar `CalendarException` nesnesi ekleyebilirsiniz.  
- **Projeyi hangi dosya formatlarında kaydedebilirim?**  
  XML, MPP ve Aspose.Tasks tarafından desteklenen diğer çeşitli formatlar.  

## Aspose.Tasks'te Proje Takvimi Nedir?
**Proje takvimi**, Aspose.Tasks'in bir projenin çalışma günlerini ve saatlerini tanımlayan üst‑seviye nesnesidir. Görev başlangıç/bitiş tarihlerini, kaynak tahsislerini ve genel zaman çizelgesi hesaplamalarını doğrudan etkiler. Bir takvimi özelleştirerek, şirket tatilleri veya hafta sonu çalışma politikaları gibi gerçek‑dünya kısıtlamalarına uyumlu bir program sağlarsınız.

## Takvim İstisnaları İçin Hafta Günlerini Neden Tanımlamalıyız?
Hafta günü istisnalarını tanımlamak, proje motorunun bu günleri çalışma dışı olarak görmesini sağlar; böylece görevler otomatik olarak bu günlere planlanmaz ve zaman çizelgesi tatiller, bakım pencereleri veya organizasyon genelindeki özel vardiya desenleri gibi gerçek‑dünya kısıtlamalarıyla uyumlu kalır.

- **Doğru zaman çizelgeleri:** Görevler tatil veya kara liste dönemlerine yerleştirilmez.  
- **Kaynak planlaması:** Kaynaklar yalnızca geçerli çalışma günlerinde tahsis edilir, aşırı tahsis önlenir.  
- **Uyumluluk:** Zaman çizelgeleri otomatik olarak organizasyon politikalarına veya yasal tatil takvimlerine uyar.  

## Takvim İstisnalarıyla Çalışma Dışı Günler Takvimi
Bir **çalışma dışı günler takvimi** oluşturduğunuzda, genellikle tatiller, bakım pencereleri veya diğer kara liste dönemlerinin bir ana listesini tutarsınız. Bu tarihleri `CalendarException` nesneleri olarak eklemek, kritik yol analizi veya kaynak dengelemesi gibi tüm hesaplamaların bu kısıtlamaları otomatik olarak göz önünde bulundurmasını sağlar. Bu yaklaşım manuel tarih ayarlamalarını ortadan kaldırır ve zaman çizelgesi sapması riskini azaltır.

## Ön Koşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. **Java Development Kit (JDK)** – sürüm 8 veya üzeri.  
2. **Aspose.Tasks for Java** – resmi [Aspose.Tasks Java indirme sayfasından](https://releases.aspose.com/tasks/java/) indirin.  
3. **Bir IDE** – IntelliJ IDEA, Eclipse, NetBeans veya herhangi bir Java‑uyumlu editör.  

## Takvim İstisnaları Kullanarak Çalışma Dışı Günleri Nasıl Planlayabilirsiniz
Projenizi yükleyin, özel bir takvim oluşturun ve istenen hafta günlerini çalışma dışı olarak işaretleyen `CalendarException` nesneleri ekleyin. Bu işlem birkaç basit adımda tamamlanabilir ve oluşturulan takvim tüm görev planlama mantığını otomatik olarak etkiler.

### Adım‑Adım Kılavuz

### Adım 1: Gerekli Paketleri İçe Aktarın
Core Aspose.Tasks sınıflarına ve tarih işleme için Java’nın `GregorianCalendar` sınıfına ihtiyacımız var.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

### Adım 2: Veri Dizinini Tanımlayın
Oluşturulan proje dosyasının kaydedileceği yeri belirtin.

```java
String dataDir = "Your Data Directory";
```

### Adım 3: Bir Proje Örneği Oluşturun
`Project`, görevler, kaynaklar ve takvimler dahil olmak üzere tüm proje verilerini tutan ana nesnedir.

```java
Project project = new Project();
```

### Adım 4: Bir Takvim Tanımlayın
`Calendar`, bir proje içinde çalışma ve çalışma dışı zamanların programını temsil eder.

```java
Calendar cal = project.getCalendars().add("Calendar1");
```

### Adım 5: Hafta Günleri İstisnasını Tanımlayın
`CalendarException`, bir takvim içinde çalışma dışı olarak işaretlenen bir dönemi temsil eder.

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
Özel takvimi ve istisnasını içerecek şekilde projeyi bir XML dosyasına kalıcı hale getirin.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Yaygın Sorunlar ve Çözümler
| Sorun | Çözüm |
|-------|----------|
| **İstisna tarihleri uygulanmıyor** | `setEnteredByOccurrences(false)` ve doğru `FromDate/ToDate` değerlerini kullandığınızdan emin olun. |
| **Kaydedilen dosya boş** | `dataDir`'in yazılabilir bir klasöre işaret ettiğini ve dosya adının `.xml` ile bittiğini doğrulayın. |
| **Takvim görev planlamasında yansımıyor** | Takvimi görev veya kaynaklara `task.setCalendar(cal)` veya `resource.setCalendar(cal)` ile atayın. |

## Sıkça Sorulan Sorular

**S: Aynı takvim içinde farklı hafta günleri için birden fazla istisna tanımlayabilir miyim?**  
C: Evet. Her ayrı dönem veya kural için `cal.getExceptions()` koleksiyonuna ek `CalendarException` nesneleri ekleyebilirsiniz.

**S: Aspose.Tasks for Java farklı Java IDE'leriyle uyumlu mu?**  
C: Kesinlikle. Kütüphane IntelliJ IDEA, Eclipse, NetBeans ve standart Java projelerini destekleyen herhangi bir IDE ile çalışır.

**S: Günlük istisnalar dışında başka istisna türlerini özelleştirebilir miyim?**  
C: Evet. `CalendarExceptionType.Weekly`, `Monthly` veya `Yearly` kullanarak planlama ihtiyaçlarınıza uygun istisnalar oluşturabilirsiniz.

**S: Proje gereksinimlerine göre istisnaları dinamik olarak nasıl yönetebilirim?**  
C: İstisna nesnelerini programlı olarak oluşturun—örneğin, tatil tarihlerini bir veritabanı veya yapılandırma dosyasından okuyup bir döngü içinde `CalendarException` örnekleri yaratın.

**S: Aspose.Tasks for Java için bir deneme sürümü mevcut mu?**  
C: Evet, ücretsiz deneme sürümünü [Aspose.Tasks Java indirme sayfasından](https://releases.aspose.com/tasks/java/) indirebilirsiniz.

## Sonuç
Bu adımları izleyerek **çalışma dışı günleri planlamak** için bir proje takvimi oluşturmayı ve hafta günü istisnalarını tanımlamayı öğrendiniz; bu sayede tatilleri veya özel çalışma dışı dönemleri doğru bir şekilde yansıtabilirsiniz. Doğru takvim yapılandırması, gerçekçi zaman çizelgeleri, kaynak tahsisi ve genel proje başarısı için kritiktir. Özel takvimi görev veya kaynaklara ekleyerek ve diğer istisna türleriyle deneyler yaparak herhangi bir proje için kapsamlı bir **çalışma dışı günler takvimi** oluşturabilirsiniz.

---

**Son Güncelleme:** 2026-07-29  
**Test Edilen Versiyon:** Aspose.Tasks for Java 24.11  
**Yazar:** Aspose

## İlgili Eğitimler

- [Aspose.Tasks for Java ile projeye takvim ekleme](/tasks/java/calendars/create/)
- [Aspose for Java ile Takvim İstisnası Oluşturma](/tasks/java/calendar-exceptions/add-remove/)
- [MS Project'te Takvim Ayarlama ve Hafta Günlerini Tanımlama Aspose.Tasks ile](/tasks/java/calendars/define-weekdays/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}