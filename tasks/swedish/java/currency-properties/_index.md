---
date: 2026-09-14
description: Lär dig hur du ändrar valutformat och läser valutaproperty i Java med
  Aspose.Tasks. Extrahera valutakod, hämta valutasymbol och uppdatera projektvaluta
  i MS Project-filer.
keywords:
- change currency format
- retrieve currency symbol
- update project currency
- extract currency code java
lastmod: 2026-09-14
linktitle: Hur du ändrar valutformat
og_description: Lär dig hur du ändrar valutformat och läser valutaproperty i Java
  med Aspose.Tasks. Steg‑för‑steg‑guide för att extrahera valutakod och uppdatera
  projektvaluta.
og_image_alt: Tutorial showing how to change currency format in Aspose.Tasks for Java
og_title: Hur du ändrar valutformat i Java med Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-09-14'
  description: Learn how to change currency format and read currency properties in
    Java using Aspose.Tasks. Extract currency code, retrieve currency symbol, and
    update project currency in MS Project files.
  headline: How to change currency format in Java with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes. Use `Project.setCurrencyCode()` and related methods, then save the
      project again.
    question: Can I change the currency after the project is already saved?
  - answer: The numeric values remain unchanged; only the display format (symbol,
      decimal separator) is updated. You must recalculate costs if you need conversion
      between currencies.
    question: Does changing the currency affect existing cost values?
  - answer: Aspose.Tasks supports any ISO‑4217 currency code, so you’re effectively
      unlimited.
    question: Are there any limits on the number of currencies I can define?
  - answer: The library falls back to the default currency (USD) and logs a warning;
      you can override this by setting the desired currency manually.
    question: What happens if I open a project with an unsupported currency code?
  - answer: Absolutely. The same API works for both *.mpp* and *.xml* formats.
    question: Is it possible to read/write currency properties in a Project XML file?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- change currency format
- Aspose.Tasks
- Java project management
- currency handling
title: Hur du ändrar valutformat i Java med Aspose.Tasks
url: /sv/java/currency-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Läs valutaegenskaper Java med Aspose.Tasks

## Introduktion
I den här handledningen kommer du att lära dig hur du **ändrar valutaformat** och läser valutaegenskaper i Java‑projekt som använder Aspose.Tasks. Noggranna finansiella data är avgörande för multinationella team, och genom att behärska dessa API:er kan du extrahera ISO‑4217‑koden, hämta valutasymbolen och uppdatera projektets monetära inställningar utan manuella kalkylbladsredigeringar.

## Snabba svar
- **Vad betyder “read currency”?** Det betyder att extrahera valutakoden, symbolen och inställningarna för talformat som lagras i en projektfil.  
- **Varför justera valutainställningar?** För att anpassa kostnadsrapporter till regionala konventioner och undvika konverteringsfel.  
- **Behöver jag en licens?** Ja – en giltig Aspose.Tasks för Java‑licens krävs för produktion; en gratis provversion fungerar för utvärdering.  
- **Vilka Project‑versioner stöds?** Både *.mpp* (Project 2007‑2024) och *.xml*-format stöds fullt ut, vilket täcker mer än 20 år av filversioner.  
- **Krävs någon ytterligare konfiguration?** Lägg bara till Aspose.Tasks för Java‑JAR‑filen i din classpath och importera de relevanta klasserna.

## Läs valutaegenskaper Java i Aspose.Tasks‑projekt
I den dynamiska världen av projektledning är extrahering av valutainformation avgörande för exakt kostnadsanalys. Vår dedikerade guide **[Reading Currency Properties in Aspose.Tasks Projects](./read-properties/)** leder dig genom varje steg – från att öppna en projektfil till att hämta valutakoden, symbolen och formatet. Genom att följa handledningen kommer du att kunna:

* Hämta valutakoden (t.ex. USD, EUR) som används i hela projektet.  
* Åtkomst till valutasymbolen och inställningarna för talformat.  
* Använd denna information för att generera lokalanpassade kostnadsrapporter eller mata in finansiella instrumentpaneler.

Att förstå hur man läser valuta säkerställer att du kan granska projektbudgetar, jämföra kostnader över regioner och upprätthålla efterlevnad av redovisningsstandarder.

## Hur man extraherar valutakod java med Aspose.Tasks
`Project.getCurrencyCode()`‑metoden returnerar den tresiffriga ISO‑4217‑identifieraren för projektets monetära enhet.

**Direkt svar:** Anropa `project.getCurrencyCode()` för att få valutakoden, t.ex. **USD** eller **EUR**; du kan sedan lagra, logga eller skicka detta värde till externa finansiella tjänster för konvertering. Detta enkla anrop ger dig en pålitlig, standardbaserad identifierare som fungerar i alla stödda Project‑versioner.

Metoden ger ett snabbt sätt att synkronisera projektdata med ERP‑system som förväntar en standardiserad kod.

## Hur man justerar valutaformat java med Aspose.Tasks
Att ändra den visuella representationen av monetära värden görs via tre enkla egenskaper.

`project.setCurrencySymbol(String)` sätter valutasymbolen som visas för monetära värden.  
`project.setCurrencyDecimalSeparator(char)` definierar tecknet som används för att separera heltalsdelen från bråkdelen.  
`project.setCurrencyThousandsSeparator(char)` definierar tecknet som används för att separera tusentalsgrupper.

**Direkt svar:** Använd `project.setCurrencySymbol("€")`, `project.setCurrencyDecimalSeparator(",")` och `project.setCurrencyThousandsSeparator(".")` för att definiera symbolen, decimalavgränsaren och tusentalsavgränsaren respektive – detta ändrar valutaformatet helt på ett ställe. Att justera dessa inställningar garanterar att alla intressenter ser siffror i en bekant stil, vilket minskar missförstånd.

* `project.setCurrencySymbol("€")` – sätter den visuella symbolen.  
* `project.setCurrencyDecimalSeparator(",")` – definierar decimalavgränsaren.  
* `project.setCurrencyThousandsSeparator(".")` – definierar tusentalsavgränsaren.  

## Hur man ställer in valutaegenskaper i Aspose.Tasks‑projekt
När ett projekt flyttas till en ny marknad eller en kund begär ett annat monetärt format, måste du uppdatera valutan programatiskt.

`project.setCurrencyCode(String)` definierar ISO‑4217‑valutakoden för projektet.

**Direkt svar:** Anropa `project.setCurrencyCode("GBP")` tillsammans med `project.setCurrencySymbol("£")` och lämpliga avgränsare, spara sedan projektet; biblioteket uppdaterar alla visningsinställningar samtidigt som befintliga kostnadsdata bevaras. Detta tillvägagångssätt ger dig full kontroll över den finansiella representationen av ditt schema.

Vår steg‑för‑steg‑guide **[Setting Currency Properties in Aspose.Tasks Projects](./set-properties/)** förklarar hur man:

* Definiera en ny valutakod och symbol för hela projektet.  
* Justera talformatet (decimaler, tusentalsavgränsare) för att matcha lokala konventioner.  
* Spara den uppdaterade projektfilen utan att förlora befintliga data.

Genom att behärska hur man ställer in valuta kan du växla mellan USD, GBP, JPY eller någon annan stödd valuta i realtid.

## Varför behärska valutahantering i Aspose.Tasks?
Korrekt valutahantering eliminerar kostsamma missförstånd och effektiviserar globalt samarbete.

**Direkt svar:** Att behärska valutahantering låter dig presentera kostnader i varje teams inhemska format, säkerställer exakt rapportering, följer regionala redovisningsstandarder och möjliggör automatiserade finansiella arbetsflöden – vilket sparar timmar av manuell omformatering per projekt.

* **Globalt samarbete:** Team i olika länder kan se kostnader i sitt inhemska format.  
* **Exakt rapportering:** Förhindra avrundnings- eller konverteringsfel som kan påverka budgetering.  
* **Efterlevnad:** Anpassa dig till regionala redovisningsstandarder och kundspecifikationer.  
* **Automation:** Minska manuella redigeringar genom att programatiskt tillämpa valutainställningar under projektgenerering.

## Verkliga användningsfall
* **Multinationella projekt:** Ett byggföretag som hanterar platser i Europa och Nordamerika behöver presentera budgetar i både EUR och USD.  
* **Finansiella revisioner:** Revisorer kräver en tydlig översikt över valutakontexten för varje kostnadspost.  
* **Dynamiska prismodeller:** SaaS‑leverantörer justerar prenumerationskostnader baserat på kundens lokala valuta.

## Vanliga fallgropar & tips
* **Fallgrop:** Glömmer att uppdatera valutasymbolen efter att ha ändrat koden.  
  **Tips:** Sätt alltid både koden och symbolen tillsammans för att undvika felaktiga visningar.  
* **Fallgrop:** Litar på standardlokalen för maskinen som kör koden.  
  **Tips:** Specificera explicit önskat valutaformat i din Aspose.Tasks‑kod för att säkerställa konsistens över miljöer.  

## Handledning för valutaegenskaper
### [Läs valutaegenskaper i Aspose.Tasks‑projekt](./read-properties/)
Lär dig hur du extraherar valutainformation från MS Project‑filer med Aspose.Tasks för Java. Steg‑för‑steg‑guide tillhandahållen.

### [Ställ in valutaegenskaper i Aspose.Tasks‑projekt](./set-properties/)
Lär dig hur du ställer in valutaegenskaper i Aspose.Tasks‑projekt med Java. Manipulera Microsoft Project‑filer utan ansträngning.

## Vanliga frågor

**Q: Kan jag ändra valutan efter att projektet redan har sparats?**  
A: Ja. Använd `Project.setCurrencyCode()` och relaterade metoder, spara sedan projektet igen.

**Q: Påverkar en förändring av valutan befintliga kostnadsvärden?**  
A: De numeriska värdena förblir oförändrade; endast visningsformatet (symbol, decimalavgränsare) uppdateras. Du måste omräkna kostnaderna om du behöver konvertering mellan valutor.

**Q: Finns det några begränsningar för hur många valutor jag kan definiera?**  
A: Aspose.Tasks stöder alla ISO‑4217‑valutakoder, så du är i praktiken obegränsad.

**Q: Vad händer om jag öppnar ett projekt med en ej stödd valutakod?**  
A: Biblioteket återgår till standardvalutan (USD) och loggar en varning; du kan åsidosätta detta genom att manuellt ställa in önskad valuta.

**Q: Är det möjligt att läsa/skriva valutaegenskaper i en Project‑XML‑fil?**  
A: Absolut. Samma API fungerar för både *.mpp* och *.xml*-format.

---

**Senast uppdaterad:** 2026-09-14  
**Testad med:** Aspose.Tasks for Java 24.12  
**Författare:** Aspose

## Relaterade handledningar

- [java projekt egenskaper – Extrahera valutasymbol från MPP med Aspose.Tasks för Java](/tasks/java/currency/currency-symbols/)
- [Hur man hämtar valuta från MS Project med Aspose.Tasks](/tasks/java/currency/currency-codes/)
- [Projekt egenskaper Java – Läs metadata med Aspose.Tasks](/tasks/java/project-properties/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}