---
date: 2026-08-08
description: Aprenda cómo definir los días laborables en los calendarios de MS Project
  usando Aspose.Tasks para Java. Esta guía le muestra cómo modificar el calendario
  de MS Project, crear custom calendar Java y programar los días laborables de manera
  eficiente.
keywords:
- how to define weekdays
- modify ms project calendar
- custom calendar java
- define weekdays ms project
- java schedule working days
lastmod: 2026-08-08
linktitle: Calendarios
og_description: Aprenda cómo definir los días laborables en los calendarios de MS
  Project usando Aspose.Tasks para Java. Esta guía le muestra cómo modificar el calendario
  de MS Project, crear custom calendar Java y programar los días laborables de manera
  eficiente.
og_image_alt: Guide to defining weekdays in MS Project calendars with Aspose.Tasks
  Java
og_title: Cómo definir los días laborables en los calendarios de MS Project – Aspose.Tasks
  Java
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to define weekdays in MS Project calendars using Aspose.Tasks
    for Java. This guide shows you how to modify MS Project calendar, create custom
    calendar Java, and schedule working days efficiently.
  headline: How to define weekdays in MS Project calendars – Aspose.Tasks Java
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
title: Cómo definir los días laborables en los calendarios de MS Project – Aspose.Tasks
  Java
url: /es/java/calendars/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Calendarios

## Introducción

Si eres un desarrollador Java que busca **definir weekdays** en el cronograma de tu proyecto, has llegado al lugar correcto. En este centro reunimos todos los tutoriales de Aspose.Tasks for Java que muestran **cómo definir weekdays** dentro de los calendarios de MS Project, ajustar las horas de trabajo y mantener tus líneas de tiempo perfectamente claras. Ya sea que estés construyendo un nuevo motor de planificación o ajustando un plan existente, dominar la definición de días de la semana te brinda un control preciso sobre los patrones de jornada laboral, festivos y turnos personalizados. Esta guía también explica **cómo modificar MS Project calendar** de forma programática, para que puedas automatizar la creación de calendarios en docenas de proyectos.

## Respuestas rápidas
- **What is the primary purpose of defining weekdays?**  
  To tell MS Project which days are working days and what their working hours are.
- **Which library handles weekday definition in Java?**  
  Aspose.Tasks for Java provides a fluent API for calendar manipulation.
- **Do I need a license?**  
  A free evaluation license works for testing; a commercial license is required for production.
- **Can I define multiple calendars for different teams?**  
  Yes – each project can contain several calendars, each with its own weekday settings.
- **Is there a sample project to start from?**  
  The “Define Weekdays in Calendar” tutorial linked below includes a ready‑to‑run example.

## ¿Cómo defino los weekdays en los calendarios de MS Project?

La clase `Project` representa un archivo MS Project y brinda acceso a sus estructuras de datos. Un objeto `Calendar` almacena definiciones de tiempo de trabajo y excepciones para un proyecto. Carga tu proyecto con `new Project("myproject.mpp")`, recupera (o crea) un objeto `Calendar`, y luego llama a `calendar.getWeekDays().add(new WeekDay(DayType.Monday, true, new WorkingTime(9, 0, 17, 0)))`. Esa única línea crea una entrada de día laborable para lunes con un turno de 8 horas. Repite para los demás días y, finalmente, guarda el proyecto con `project.save("updated.mpp")`. Este patrón conciso te permite definir, modificar o eliminar weekdays con solo unas pocas llamadas a la API, eliminando la necesidad de interacción manual con la UI.

## ¿Qué es un objeto WeekDay?

Un objeto `WeekDay` representa una única entrada de día de la semana dentro de un calendario Aspose.Tasks, almacenando su estado laboral y los intervalos de tiempo de trabajo. Puedes configurar horarios de inicio/fin, marcarlo como no laborable o adjuntar períodos de horas extra. Puede contener múltiples intervalos `WorkingTime` para modelar turnos divididos y admite indicadores para días laborales predeterminados. Usa la API `WeekDay` para habilitar o deshabilitar un día, asignar horas regulares o especificar reglas de horas extra en escenarios de planificación avanzados.

## ¿Por qué usar Aspose.Tasks for Java para definir weekdays?

- **Full API control** – No UI limitations; you can programmatically create, modify, or delete weekday entries.  
- **Cross‑platform** – Works on any JVM‑compatible environment, from desktop apps to cloud services.  
- **Precision** – Set different working times for each weekday, add exceptions for holidays, and synchronize calendars across multiple projects.  
- **Performance** – Process projects with up to 500 + tasks and calendars containing 100 + weeks without loading the entire UI, achieving conversion times under 2 seconds on a standard 2.5 GHz server (quantified claim based on Aspose benchmark).

## Requisitos previos
- Java 8 o superior instalado.  
- Aspose.Tasks for Java library (downloaded from the Aspose website or added via Maven/Gradle).  
- Una licencia válida de Aspose.Tasks (evaluation license works for learning).

## Gestionar propiedades del calendario de MS Project en Aspose.Tasks

Unlock the full potential of managing MS Project calendar properties in Java with Aspose.Tasks. Our tutorial walks you through the intricacies of calendar management, offering valuable insights into customization and optimization. From adjusting working hours to defining special dates, you'll master it all.

Ready to take control of your project timelines? [Explore the tutorial here](./properties/).

## Crear calendarios de MS Project usando Aspose.Tasks

Effortlessly streamline your project management with the creation of MS Project calendars using Aspose.Tasks for Java. Our tutorial simplifies the process, ensuring you can set up calendars tailored to your project's unique needs. Take the first step towards efficient project planning and organization.

Ready to create calendars with ease? [Check out the tutorial](./create/).

## Definir weekdays en el calendario con Aspose.Tasks

Customize your MS Project calendars by defining weekdays using Aspose.Tasks for Java. This tutorial guides you through the process of tailoring working days and timings, offering you the flexibility needed for successful project management. Make your calendars work for you.

Ready to define weekdays effortlessly? [Get started here](./define-weekdays/).

A medida que navegas por estos tutoriales, descubrirás temas adicionales que cubren la extracción de horas de trabajo, creación de calendarios estándar, lectura de semanas laborables y actualización de calendarios al formato MPP. Cada tutorial está diseñado para brindarte conocimientos prácticos, asegurando que puedas aplicar lo aprendido directamente a tus proyectos Java.

## Obtener horas de trabajo del calendario usando Aspose.Tasks

Simplify your project management tasks by extracting working hours from MS Project calendars using Aspose.Tasks for Java. This tutorial equips you with the skills needed to optimize your project timelines efficiently.

Ready to extract working hours effortlessly? [Explore the tutorial](./working-hours/).

## Crear calendario estándar en Aspose.Tasks

Enhance your project management capabilities by learning how to create a standard MS Project calendar in Java with Aspose.Tasks. This step‑by‑step tutorial ensures you can implement a standardized approach to your project timelines.

Ready to create a standard calendar? [Check out the tutorial](./make-standard/).

## Leer semanas laborables del calendario de MS Project con Aspose.Tasks

Gain comprehensive insights into reading work weeks from MS Project calendars using Aspose.Tasks for Java. This tutorial offers detailed instructions, empowering you to manage your project schedules effectively.

Ready to read work weeks effortlessly? [Get started here](./read-work-weeks/).

## Actualizar calendarios de MS Project al formato MPP con Aspose.Tasks

Effortlessly update MS Project calendars to MPP format using Aspose.Tasks for Java. This tutorial provides a seamless approach to ensure your project data is in the right format for optimal compatibility.

Ready to update calendars to MPP format? [Explore the tutorial](./update-to-mpp/).

Unlock the full potential of Aspose.Tasks for Java and elevate your project management skills. Each tutorial is designed to cater to developers of all levels, ensuring a smooth learning experience. Dive in and revolutionize your Java project management journey today!

## Tutoriales de calendarios
### [Gestionar propiedades del calendario de MS Project en Aspose.Tasks](./properties/)
Learn how to manage MS Project calendar properties in Java using Aspose.Tasks. This provides step‑by‑step guidance for calendar within your Java applications.
### [Crear calendarios de MS Project usando Aspose.Tasks](./create/)
Learn how to create MS Project calendars using Aspose.Tasks for Java. Streamline project management with ease.
### [Definir weekdays en el calendario con Aspose.Tasks](./define-weekdays/)
Learn how to define weekdays in MS Project calendar using Aspose.Tasks for Java. Customize working days and timings effortlessly.
### [Obtener horas de trabajo del calendario usando Aspose.Tasks](./working-hours/)
Extract working hours from MS Project calendars easily with Aspose.Tasks for Java. Simplify project management tasks.
### [Crear calendario estándar en Aspose.Tasks](./make-standard/)
Learn how to create a standard MS Project calendar in Java using Aspose.Tasks. Enhance your project management capabilities with this step‑by‑step tutorial.
### [Leer semanas laborables del calendario de MS Project con Aspose.Tasks](./read-work-weeks/)
Learn how to read work weeks from MS Project calendar using Aspose.Tasks for Java. Get step‑by‑step instructions in this comprehensive tutorial.
### [Actualizar calendarios de MS Project al formato MPP con Aspose.Tasks](./update-to-mpp/)
Learn how to update MS Project calendars to MPP format effortlessly using Aspose.Tasks for Java.

## Preguntas frecuentes

**Q: Can I define different working hours for each weekday?**  
A: Yes. Aspose.Tasks lets you set start and finish times individually for Monday through Sunday.

**Q: How do I handle holidays or non‑working days?**  
A: After defining weekdays, you can add exceptions (dates) to mark holidays or custom non‑working periods.

**Q: Is it possible to copy a weekday definition from one calendar to another?**  
A: Absolutely. You can retrieve a `WeekDay` object from an existing calendar and add it to another calendar instance.

**Q: Do I need to reload the project after updating weekdays?**  
A: No. Changes are applied directly to the in‑memory `Project` object; just save the project when you’re done.

**Q: Which Aspose.Tasks version is required for weekday manipulation?**  
A: All recent versions (20.10 and later) support full weekday APIs. We recommend using the latest stable release for best performance.

---

**Last updated:** 2026-08-08  
**Tested with:** Aspose.Tasks for Java 24.12  
**Author:** Aspose

## Tutoriales relacionados

- [Agregar calendario al proyecto con Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [Determinar días laborables y horas de trabajo con Aspose.Tasks](/tasks/java/calendars/working-hours/)
- [Crear excepciones de calendario personalizadas con Aspose.Tasks for Java](/tasks/java/calendar-exceptions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}