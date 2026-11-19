---
date: 2026-11-19
description: Aspose.Tasks kullanarak Java'da özel takvim oluşturmayı öğrenin. Bu rehber,
  çalışma günlerini tanımlamayı, çalışma saatlerini ayarlamayı ve MS Project takvimlerini
  programlı olarak değiştirmeyi gösterir.
images:
- /java/calendars/og-image.png
keywords:
- create custom calendar java
- define working days ms project
- set working hours ms project
- aspose.tasks java calendar
- ms project calendar manipulation
lastmod: 2026-11-19
linktitle: Takvimler
og_description: Aspose.Tasks ile Java'da özel takvim oluşturmayı öğrenin. Çalışma
  günlerini tanımlamayı, çalışma saatlerini ayarlamayı ve MS Project takvimlerini
  verimli bir şekilde değiştirmeyi ustalaşın.
og_image_alt: Guide to creating custom calendars in MS Project using Aspose.Tasks
  for Java
og_title: Aspose.Tasks ile Java'da özel takvim oluşturma
schemas:
- author: Aspose
  dateModified: '2026-11-19'
  description: Learn how to create custom calendar Java using Aspose.Tasks. This guide
    shows you how to define working days, set working hours, and modify MS Project
    calendars programmatically.
  headline: How to create custom calendar Java with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes. Aspose.Tasks lets you set start and finish times individually for
      Monday through Sunday.
    question: Can I define different working hours for each weekday?
  - answer: After defining weekdays, you can add exceptions (dates) to mark holidays
      or custom non‑working periods.
    question: How do I handle holidays or non‑working days?
  - answer: Absolutely. You can retrieve a `WeekDay` object from an existing calendar
      and add it to another calendar instance.
    question: Is it possible to copy a weekday definition from one calendar to another?
  - answer: No. Changes are applied directly to the in‑memory `Project` object; just
      save the project when you’re done.
    question: Do I need to reload the project after updating weekdays?
  - answer: All recent versions (20.10 and later) support full weekday APIs. We recommend
      using the latest stable release for best performance.
    question: Which Aspose.Tasks version is required for weekday manipulation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendars
- Aspose.Tasks
- Java project management
- MS Project integration
- working days
title: Aspose.Tasks ile Java'da özel takvim oluşturma
url: /tr/java/calendars/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Takvimler

## Giriş

Java geliştiricisiyseniz ve **özel takvim Java** çözümleri oluşturmak istiyorsanız, doğru yerdesiniz. Bu merkez, **çalışma günlerini MS Project'te tanımlama**, **çalışma saatlerini MS Project'te ayarlama** ve takvim ayarlarını programlı olarak değiştirmeyi gösteren tüm Aspose.Tasks for Java öğreticilerini bir araya getirir. Yeni bir zamanlama motoru oluşturuyor ya da mevcut bir planı genişletiyor olun, bu API'leri ustalaşmak, çalışma günü desenleri, tatiller ve özel vardiyalar üzerinde kesin kontrol sağlar—MS Project UI'sını hiç açmadan.

## Hızlı cevaplar
- **Haftanın günlerini tanımlamanın temel amacı nedir?**  
  MS Project'e hangi günlerin çalışma günü olduğunu ve çalışma saatlerinin ne olduğunu söylemektir.  
- **Java'da hafta günü tanımını hangi kütüphane yönetir?**  
  Aspose.Tasks for Java, takvim manipülasyonu için akıcı bir API sağlar.  
- **Bir lisansa ihtiyacım var mı?**  
  Ücretsiz bir değerlendirme lisansı test için çalışır; üretim için ticari bir lisans gereklidir.  
- **Farklı ekipler için birden fazla takvim tanımlayabilir miyim?**  
  Evet – her proje birden fazla takvim içerebilir, her biri kendi hafta günü ayarlarına sahiptir.  
- **Başlamak için bir örnek proje var mı?**  
  Aşağıda bağlantısı verilen “Define Weekdays in Calendar” öğreticisi, çalıştırmaya hazır bir örnek içerir.

## Özel takvim Java nasıl oluşturulur?

Bir proje yükleyin, bir takvim oluşturun veya alın, hafta günü tanımları ekleyin ve dosyayı kaydedin—tüm bunlar birkaç API çağrısı ile yapılır. Bu yaklaşım manuel UI adımlarını ortadan kaldırır, onlarca proje boyunca takvim oluşturmayı otomatikleştirmenizi sağlar ve organizasyonunuzda tutarlı çalışma günü desenlerini garanti eder.

## Project sınıfı nedir?

`Project` sınıfı, MS Project dosyalarını yüklemek, düzenlemek ve kaydetmek için merkezi nesnedir. Görevler, kaynaklar ve takvim koleksiyonlarını tutar ve bir projeyi programlı olarak okumanıza ve değiştirmenize olanak tanıyan yöntemler sunar. Bu sınıfı kullanarak, bir projenin takvim koleksiyonuna erişebilir, çalışma zamanlarını ayarlayabilir ve değişiklikleri bir MPP veya XML dosyasına kalıcı olarak kaydedebilirsiniz.

## MS Project takvimlerinde hafta günlerini nasıl tanımlarım?

`Project` sınıfı bir MS Project dosyasını temsil eder ve veri yapılarına erişim sağlar. Bir `Calendar` nesnesi, bir proje için çalışma zamanı tanımlarını ve istisnaları depolar. Projenizi `new Project("myproject.mpp")` ile yükleyin, bir `Calendar` nesnesi alın (veya oluşturun) ve ardından `calendar.getWeekDays().add(new WeekDay(DayType.Monday, true, new WorkingTime(9, 0, 17, 0)))` çağrısını yapın. Bu tek satır, 8‑saatlik bir vardiya ile Pazartesi çalışma günü girdisi oluşturur. Diğer günler için tekrarlayın ve sonunda projeyi `project.save("updated.mpp")` ile kaydedin. Bu özlü desen, sadece birkaç API çağrısıyla hafta günlerini tanımlamanıza, değiştirmenize veya silmenize olanak tanır ve manuel UI etkileşimine gerek kalmaz.

## WeekDay nesnesi nedir?

`WeekDay` nesnesi, bir takvim içinde tek bir hafta günü girişini temsil eder. Günün çalışma olup olmadığını, o gün için çalışma zamanı aralıklarını ve varsayılan davranış bayraklarını saklar. Bölünmüş vardiyaları modellemek için bir veya daha fazla `WorkingTime` aralığı ekleyebilir, günü çalışmayan olarak ayarlayabilir veya varsayılanları üst takvimden devralabilirsiniz.

## MS Project'te çalışma günlerini nasıl tanımlarım?

Çalışma günlerini, bir takvimin `WeekDays` koleksiyonuna `WeekDay` nesneleri ekleyerek tanımlarsınız. Her `WeekDay`, günün çalışma olup olmadığını ve çalışma zamanı olarak kabul edilen zaman aralıklarını belirtir. Örneğin, Cumartesi'yi yarım gün yapmak için 10:00‑14:00 arasında tek bir `WorkingTime` içeren bir `WeekDay` ekleyin. API, projenin takvim hesaplamalarını otomatik olarak günceller.

## MS Project'te çalışma saatlerini nasıl ayarlarım?

Her `WeekDay` için bir veya daha fazla `WorkingTime` aralığı oluşturarak çalışma saatlerini ayarlayın. `WorkingTime`, başlangıç‑saat, başlangıç‑dakika, bitiş‑saat ve bitiş‑dakika değerlerini alır. Bölünmüş vardiyaları modellemek için tek bir güne birden fazla aralık atayabilirsiniz (ör. 08:00‑12:00 ve 13:00‑17:00). Tüm hafta günlerini yapılandırdıktan sonra, değişiklikleri kalıcı kılmak için `project.save(...)` çağrısını yapın.

## Hafta günlerini tanımlamak için Aspose.Tasks for Java neden kullanılmalı?

- **Tam API kontrolü** – UI sınırlamaları yoktur; hafta günü girişlerini programlı olarak oluşturabilir, değiştirebilir veya silebilirsiniz.  
- **Çapraz platform** – Masaüstü uygulamalardan bulut hizmetlerine kadar herhangi bir JVM uyumlu ortamda çalışır.  
- **Hassasiyet** – Her hafta günü için farklı çalışma zamanları ayarlayın, tatiller için istisnalar ekleyin ve takvimleri birden fazla proje arasında senkronize edin.  
- **Performans** – Tüm UI'yı yüklemeden 500+ görev ve 100+ hafta içeren takvimleri işleyin, standart 2.5 GHz sunucuda dönüşüm sürelerini 2 saniyenin altında elde edin (Aspose benchmark'ına dayalı ölçülen iddia).  
- **Geniş format desteği** – Aspose.Tasks, 30+ takvim‑ile ilgili API'yi destekler ve 20'den fazla dosya formatına içe/dışa aktarabilir, mevcut proje veri hatlarıyla sorunsuz entegrasyon sağlar.

## Önkoşullar
- Java 8 veya daha yüksek bir sürüm yüklü.  
- Aspose.Tasks for Java kütüphanesi (Aspose web sitesinden indirilen veya Maven/Gradle aracılığıyla eklenen).  
- Geçerli bir Aspose.Tasks lisansı (değerlendirme lisansı öğrenme için çalışır).  

## Aspose.Tasks ile MS Project takvim özelliklerini yönetin

Aspose.Tasks ile Java'da MS Project takvim özelliklerini yönetmenin tam potansiyelini ortaya çıkarın. Öğreticimiz, takvim yönetiminin inceliklerini adım adım anlatır, özelleştirme ve optimizasyon konusunda değerli bilgiler sunar. Çalışma saatlerini ayarlamaktan özel tarihleri tanımlamaya kadar her şeyi ustalaşacaksınız.

Proje zaman çizelgelerinizi kontrol etmeye hazır mısınız? [Buradan öğreticiyi keşfedin](./properties/).

## Aspose.Tasks kullanarak MS Project takvimleri oluşturun

Aspose.Tasks for Java kullanarak MS Project takvimleri oluşturmakla proje yönetiminizi zahmetsizce hızlandırın. Öğreticimiz süreci basitleştirir, projenizin benzersiz ihtiyaçlarına göre takvimler oluşturmanızı sağlar. Verimli proje planlaması ve organizasyonu için ilk adımı atın.

Takvimleri kolayca oluşturmak için hazır mısınız? [Öğreticiye göz atın](./create/).

## Aspose.Tasks ile takvimde hafta günlerini tanımlayın

Aspose.Tasks for Java kullanarak hafta günlerini tanımlayarak MS Project takvimlerinizi özelleştirin. Bu öğretici, çalışma günlerini ve zamanlamalarını özelleştirme sürecinde size rehberlik eder, başarılı proje yönetimi için gereken esnekliği sunar. Takvimlerinizi sizin için çalışır hâle getirin.

Hafta günlerini zahmetsizce tanımlamaya hazır mısınız? [Buradan başlayın](./define-weekdays/).

Bu öğreticilerde ilerledikçe, çalışma saatlerinin çıkarılması, standart takvim oluşturma, çalışma haftalarının okunması ve takvimlerin MPP formatına güncellenmesi gibi ek konuları keşfedeceksiniz. Her öğretici, size pratik bilgi sunacak şekilde hazırlanmıştır, böylece öğrendiklerinizi doğrudan Java projelerinizde uygulayabilirsiniz.

## Aspose.Tasks ile takvimden çalışma saatlerini alın

Aspose.Tasks for Java kullanarak MS Project takvimlerinden çalışma saatlerini çıkararak proje yönetimi görevlerinizi basitleştirin. Bu öğretici, proje zaman çizelgelerinizi verimli bir şekilde optimize etmek için gereken becerileri size kazandırır.

Çalışma saatlerini zahmetsizce çıkarmaya hazır mısınız? [Öğreticiyi keşfedin](./working-hours/).

## Aspose.Tasks ile standart takvim oluşturun

Aspose.Tasks ile Java'da standart bir MS Project takvimi oluşturmayı öğrenerek proje yönetimi yeteneklerinizi geliştirin. Bu adım adım öğretici, proje zaman çizelgelerinizde standart bir yaklaşım uygulamanızı sağlar.

Standart bir takvim oluşturmak için hazır mısınız? [Öğreticiye göz atın](./make-standard/).

## Aspose.Tasks ile MS Project takviminden çalışma haftalarını okuyun

Aspose.Tasks for Java kullanarak MS Project takvimlerinden çalışma haftalarını okumaya dair kapsamlı bilgiler edinin. Bu öğretici, ayrıntılı talimatlar sunar ve proje takvimlerinizi etkili bir şekilde yönetmenizi sağlar.

Çalışma haftalarını zahmetsizce okumaya hazır mısınız? [Buradan başlayın](./read-work-weeks/).

## Aspose.Tasks ile MS Project takvimlerini MPP formatına güncelleyin

Aspose.Tasks for Java kullanarak MS Project takvimlerini MPP formatına zahmetsizce güncelleyin. Bu öğretici, proje verilerinizin optimal uyumluluk için doğru formatta olmasını sağlayan sorunsuz bir yaklaşım sunar.

Takvimleri MPP formatına güncellemeye hazır mısınız? [Öğreticiyi keşfedin](./update-to-mpp/).

Aspose.Tasks for Java'un tam potansiyelini ortaya çıkarın ve proje yönetimi becerilerinizi yükseltin. Her öğretici, tüm seviyelerdeki geliştiricilere hitap edecek şekilde tasarlanmıştır, sorunsuz bir öğrenme deneyimi sağlar. Hemen dalın ve Java proje yönetimi yolculuğunuzu bugün devrim niteliğinde bir şekilde yeniden şekillendirin!

## Takvim öğreticileri
### [Aspose.Tasks ile MS Project Takvim Özelliklerini Yönetin](./properties/)
Aspose.Tasks kullanarak Java'da MS Project takvim özelliklerini nasıl yöneteceğinizi öğrenin. Bu, Java uygulamalarınızda takvim için adım adım rehberlik sağlar.
### [Aspose.Tasks ile MS Project Takvimleri Oluşturun](./create/)
Aspose.Tasks for Java kullanarak MS Project takvimlerini nasıl oluşturacağınızı öğrenin. Proje yönetimini kolaylıkla hızlandırın.
### [Aspose.Tasks ile takvimde hafta günlerini tanımlayın](./define-weekdays/)
Aspose.Tasks for Java kullanarak MS Project takviminde hafta günlerini nasıl tanımlayacağınızı öğrenin. Çalışma günlerini ve zamanlamalarını zahmetsizce özelleştirin.
### [Aspose.Tasks ile takvimden çalışma saatlerini alın](./working-hours/)
Aspose.Tasks for Java ile MS Project takvimlerinden çalışma saatlerini kolayca çıkarın. Proje yönetimi görevlerini basitleştirin.
### [Aspose.Tasks ile standart takvim oluşturun](./make-standard/)
Aspose.Tasks kullanarak Java'da standart bir MS Project takvimi nasıl oluşturulacağını öğrenin. Bu adım adım öğretici ile proje yönetimi yeteneklerinizi geliştirin.
### [Aspose.Tasks ile MS Project takviminden çalışma haftalarını okuyun](./read-work-weeks/)
Aspose.Tasks for Java kullanarak MS Project takviminden çalışma haftalarını nasıl okuyacağınızı öğrenin. Bu kapsamlı öğreticide adım adım talimatları alın.
### [Aspose.Tasks for Java ile MS Project takvimlerini MPP formatına zahmetsizce güncelleyin](./update-to-mpp/)
Aspose.Tasks for Java kullanarak MS Project takvimlerini MPP formatına zahmetsizce nasıl güncelleyeceğinizi öğrenin.

## Sıkça Sorulan Sorular

**Q: Her hafta günü için farklı çalışma saatleri tanımlayabilir miyim?**  
A: Evet. Aspose.Tasks, Pazartesi'den Pazar'a kadar her gün için başlangıç ve bitiş zamanlarını ayrı ayrı ayarlamanıza olanak tanır.

**Q: Tatilleri veya çalışılmayan günleri nasıl yönetirim?**  
A: Hafta günlerini tanımladıktan sonra, tatilleri veya özel çalışılmayan dönemleri işaretlemek için istisnalar (tarihler) ekleyebilirsiniz.

**Q: Bir takvimden başka bir takvime hafta günü tanımını kopyalamak mümkün mü?**  
A: Kesinlikle. Mevcut bir takvimden bir `WeekDay` nesnesi alıp başka bir takvim örneğine ekleyebilirsiniz.

**Q: Hafta günlerini güncelledikten sonra projeyi yeniden yüklemem gerekiyor mu?**  
A: Hayır. Değişiklikler doğrudan bellek içindeki `Project` nesnesine uygulanır; işiniz bittiğinde sadece projeyi kaydedin.

**Q: Hafta günü manipülasyonu için hangi Aspose.Tasks sürümü gerekir?**  
A: Tüm yeni sürümler (20.10 ve sonrası) tam hafta günü API'lerini destekler. En iyi performans için en son stabil sürümü kullanmanızı öneririz.

---

**Son Güncelleme:** 2026-11-19  
**Test Edilen:** Aspose.Tasks for Java 24.12  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Aspose.Tasks for Java ile projeye takvim ekleyin](/tasks/java/calendars/create/)
- [Aspose.Tasks ile Çalışma Günlerini ve Çalışma Saatlerini Belirleyin](/tasks/java/calendars/working-hours/)
- [Aspose.Tasks for Java ile Özel Takvim İstisnaları Oluşturun](/tasks/java/calendar-exceptions/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}