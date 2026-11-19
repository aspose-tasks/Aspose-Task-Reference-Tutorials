---
date: 2026-11-19
description: Aprenda a crear un calendario personalizado en Java usando Aspose.Tasks.
  Esta guía le muestra cómo definir días laborables, establecer horas de trabajo y
  modificar los calendarios de MS Project de forma programática.
images:
- /java/calendars/og-image.png
keywords:
- create custom calendar java
- define working days ms project
- set working hours ms project
- aspose.tasks java calendar
- ms project calendar manipulation
lastmod: 2026-11-19
linktitle: Calendarios
og_description: Aprenda a crear un calendario personalizado en Java con Aspose.Tasks.
  Domine la definición de días laborables, el establecimiento de horas de trabajo
  y la modificación eficiente de los calendarios de MS Project.
og_image_alt: Guide to creating custom calendars in MS Project using Aspose.Tasks
  for Java
og_title: Cómo crear un calendario personalizado en Java con Aspose.Tasks
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
title: Cómo crear un calendario personalizado en Java con Aspose.Tasks
url: /es/java/calendars/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Calendarios

## Introducción

Si eres un desarrollador Java que desea **crear soluciones de calendario Java** personalizadas, has llegado al lugar correcto. Este centro reúne todos los tutoriales de Aspose.Tasks for Java que demuestran cómo **definir días laborables en MS Project**, **establecer horas laborables en MS Project** y ajustar la configuración del calendario de forma programática. Ya sea que estés construyendo un nuevo motor de programación o ampliando un plan existente, dominar estas APIs te brinda un control preciso sobre los patrones de días laborables, festivos y turnos personalizados, sin necesidad de abrir la interfaz de MS Project.

## Respuestas rápidas
- **¿Cuál es el propósito principal de definir los días de la semana?**  
  Indicar a MS Project qué días son laborables y cuáles son sus horas de trabajo.  
- **¿Qué biblioteca maneja la definición de días de la semana en Java?**  
  Aspose.Tasks for Java proporciona una API fluida para la manipulación de calendarios.  
- **¿Necesito una licencia?**  
  Una licencia de evaluación gratuita funciona para pruebas; se requiere una licencia comercial para producción.  
- **¿Puedo definir varios calendarios para diferentes equipos?**  
  Sí, cada proyecto puede contener varios calendarios, cada uno con su propia configuración de días laborables.  
- **¿Existe un proyecto de ejemplo para comenzar?**  
  El tutorial “Define Weekdays in Calendar” enlazado a continuación incluye un ejemplo listo para ejecutar.

## ¿Cómo crear un calendario personalizado Java?

Carga un proyecto, crea o recupera un calendario, agrega definiciones de días laborables y guarda el archivo, todo con un puñado de llamadas a la API. Este enfoque elimina los pasos manuales de la UI, te permite automatizar la creación de calendarios en docenas de proyectos y garantiza patrones de días laborables consistentes en toda tu organización.

## ¿Qué es la clase Project?

La clase `Project` es el objeto central para cargar, editar y guardar archivos de MS Project. Contiene colecciones de tareas, recursos y calendarios, exponiendo métodos que te permiten leer y modificar cada aspecto de un proyecto de forma programática. Con esta clase, puedes acceder a la colección de calendarios de un proyecto, ajustar los horarios de trabajo y persistir los cambios en un archivo MPP o XML.

## ¿Cómo defino los días de la semana en los calendarios de MS Project?

La clase `Project` representa un archivo de MS Project y brinda acceso a sus estructuras de datos. Un objeto `Calendar` almacena definiciones de tiempo de trabajo y excepciones para un proyecto. Carga tu proyecto con `new Project("myproject.mpp")`, recupera (o crea) un objeto `Calendar` y luego llama a `calendar.getWeekDays().add(new WeekDay(DayType.Monday, true, new WorkingTime(9, 0, 17, 0)))`. Esa única línea crea una entrada de día laborable para el lunes con un turno de 8 horas. Repite para los demás días y, finalmente, guarda el proyecto con `project.save("updated.mpp")`. Este patrón conciso te permite definir, modificar o eliminar días de la semana con solo unas pocas llamadas a la API, eliminando la necesidad de interacción manual con la UI.

## ¿Qué es un objeto WeekDay?

Un objeto `WeekDay` representa una única entrada de día de la semana dentro de un calendario. Almacena si el día es laborable, los intervalos de tiempo de trabajo para ese día y banderas para el comportamiento predeterminado. Puedes adjuntar uno o más intervalos `WorkingTime` para modelar turnos divididos, establecer el día como no laborable o heredar valores predeterminados del calendario padre.

## ¿Cómo definir días laborables en MS Project?

Defines los días laborables agregando objetos `WeekDay` a la colección `WeekDays` de un calendario. Cada `WeekDay` especifica si el día es laborable y los rangos de tiempo que se consideran horas de trabajo. Por ejemplo, para hacer del sábado medio día, agrega un `WeekDay` con un único `WorkingTime` de 10:00 a 14:00. La API actualiza automáticamente los cálculos de programación del proyecto.

## ¿Cómo establecer horas laborables en MS Project?

Establece las horas laborables creando uno o más intervalos `WorkingTime` para cada `WeekDay`. Un `WorkingTime` recibe valores de hora de inicio, minuto de inicio, hora de fin y minuto de fin. Puedes asignar múltiples intervalos a un solo día para modelar turnos divididos (p. ej., 08:00‑12:00 y 13:00‑17:00). Después de configurar todos los días laborables, llama a `project.save(...)` para persistir los cambios.

## ¿Por qué usar Aspose.Tasks for Java para definir días de la semana?

- **Control total de la API** – Sin limitaciones de UI; puedes crear, modificar o eliminar entradas de días laborables programáticamente.  
- **Multiplataforma** – Funciona en cualquier entorno compatible con JVM, desde aplicaciones de escritorio hasta servicios en la nube.  
- **Precisión** – Establece diferentes horarios de trabajo para cada día laborable, agrega excepciones para festivos y sincroniza calendarios entre múltiples proyectos.  
- **Rendimiento** – Procesa proyectos con más de 500 tareas y calendarios que abarcan más de 100 semanas sin cargar toda la UI, logrando tiempos de conversión inferiores a 2 segundos en un servidor estándar de 2.5 GHz (cifra basada en el benchmark de Aspose).  
- **Amplio soporte de formatos** – Aspose.Tasks soporta más de 30 APIs relacionadas con calendarios y puede importar/exportar a más de 20 formatos de archivo, facilitando la integración con pipelines de datos de proyecto existentes.

## Requisitos previos
- Java 8 o superior instalado.  
- Biblioteca Aspose.Tasks for Java (descargada del sitio web de Aspose o añadida vía Maven/Gradle).  
- Una licencia válida de Aspose.Tasks (la licencia de evaluación sirve para aprendizaje).  

## Administrar propiedades del calendario de MS Project en Aspose.Tasks

Desbloquea todo el potencial de la gestión de propiedades del calendario de MS Project en Java con Aspose.Tasks. Nuestro tutorial te guía a través de las complejidades de la gestión de calendarios, ofreciendo ideas valiosas sobre personalización y optimización. Desde ajustar horas laborables hasta definir fechas especiales, dominarás todo.

¿Listo para tomar el control de los cronogramas de tu proyecto? [Explora el tutorial aquí](./properties/).

## Crear calendarios de MS Project usando Aspose.Tasks

Optimiza la gestión de proyectos creando calendarios de MS Project con Aspose.Tasks for Java. Nuestro tutorial simplifica el proceso, asegurando que puedas configurar calendarios adaptados a las necesidades únicas de tu proyecto. Da el primer paso hacia una planificación y organización de proyectos eficientes.

¿Listo para crear calendarios con facilidad? [Consulta el tutorial](./create/).

## Definir días laborables en el calendario con Aspose.Tasks

Personaliza tus calendarios de MS Project definiendo los días laborables con Aspose.Tasks for Java. Este tutorial te guía en el proceso de adaptar los días y horarios de trabajo, brindándote la flexibilidad necesaria para una gestión de proyectos exitosa. Haz que tus calendarios trabajen para ti.

¿Listo para definir días laborables sin esfuerzo? [Comienza aquí](./define-weekdays/).

A medida que navegas por estos tutoriales, descubrirás temas adicionales que cubren la extracción de horas laborables, creación de calendarios estándar, lectura de semanas de trabajo y actualización de calendarios al formato MPP. Cada tutorial está diseñado para proporcionarte conocimientos prácticos, asegurando que puedas aplicar lo aprendido directamente a tus proyectos Java.

## Obtener horas laborables del calendario usando Aspose.Tasks

Simplifica tus tareas de gestión de proyectos extrayendo las horas laborables de los calendarios de MS Project con Aspose.Tasks for Java. Este tutorial te brinda las habilidades necesarias para optimizar tus cronogramas de proyecto de manera eficiente.

¿Listo para extraer horas laborables sin esfuerzo? [Explora el tutorial](./working-hours/).

## Crear calendario estándar en Aspose.Tasks

Mejora tus capacidades de gestión de proyectos aprendiendo a crear un calendario estándar de MS Project en Java con Aspose.Tasks. Este tutorial paso a paso te asegura poder implementar un enfoque estandarizado para tus cronogramas de proyecto.

¿Listo para crear un calendario estándar? [Consulta el tutorial](./make-standard/).

## Leer semanas de trabajo del calendario de MS Project con Aspose.Tasks

Obtén una visión completa sobre la lectura de semanas de trabajo de los calendarios de MS Project usando Aspose.Tasks for Java. Este tutorial ofrece instrucciones detalladas, capacitándote para gestionar los cronogramas de tus proyectos de manera eficaz.

¿Listo para leer semanas de trabajo sin esfuerzo? [Comienza aquí](./read-work-weeks/).

## Actualizar calendarios de MS Project al formato MPP con Aspose.Tasks

Actualiza fácilmente los calendarios de MS Project al formato MPP usando Aspose.Tasks for Java. Este tutorial proporciona un enfoque sin complicaciones para garantizar que tus datos de proyecto estén en el formato correcto para una compatibilidad óptima.

¿Listo para actualizar calendarios al formato MPP? [Explora el tutorial](./update-to-mpp/).

Desbloquea todo el potencial de Aspose.Tasks for Java y eleva tus habilidades de gestión de proyectos. Cada tutorial está diseñado para desarrolladores de todos los niveles, asegurando una experiencia de aprendizaje fluida. ¡Sumérgete y revoluciona tu gestión de proyectos Java hoy mismo!

## Tutoriales de calendarios
### [Administrar propiedades del calendario de MS Project en Aspose.Tasks](./properties/)
Aprende a gestionar las propiedades del calendario de MS Project en Java usando Aspose.Tasks. Proporciona una guía paso a paso para el calendario dentro de tus aplicaciones Java.
### [Crear calendarios de MS Project usando Aspose.Tasks](./create/)
Aprende a crear calendarios de MS Project usando Aspose.Tasks for Java. Optimiza la gestión de proyectos con facilidad.
### [Definir días laborables en el calendario con Aspose.Tasks](./define-weekdays/)
Aprende a definir días laborables en el calendario de MS Project usando Aspose.Tasks for Java. Personaliza los días y horarios de trabajo sin esfuerzo.
### [Obtener horas laborables del calendario usando Aspose.Tasks](./working-hours/)
Extrae horas laborables de los calendarios de MS Project fácilmente con Aspose.Tasks for Java. Simplifica las tareas de gestión de proyectos.
### [Crear calendario estándar en Aspose.Tasks](./make-standard/)
Aprende a crear un calendario estándar de MS Project en Java usando Aspose.Tasks. Mejora tus capacidades de gestión de proyectos con este tutorial paso a paso.
### [Leer semanas de trabajo del calendario de MS Project con Aspose.Tasks](./read-work-weeks/)
Aprende a leer semanas de trabajo del calendario de MS Project usando Aspose.Tasks for Java. Obtén instrucciones paso a paso en este tutorial integral.
### [Actualizar calendarios de MS Project al formato MPP sin esfuerzo usando Aspose.Tasks for Java](./update-to-mpp/)
Aprende a actualizar calendarios de MS Project al formato MPP sin esfuerzo usando Aspose.Tasks for Java.

## Preguntas frecuentes

**P: ¿Puedo definir diferentes horas laborables para cada día de la semana?**  
R: Sí. Aspose.Tasks te permite establecer horarios de inicio y fin individualmente para lunes a domingo.

**P: ¿Cómo manejo festivos o días no laborables?**  
R: Después de definir los días laborables, puedes agregar excepciones (fechas) para marcar festivos o periodos personalizados no laborables.

**P: ¿Es posible copiar una definición de día laborable de un calendario a otro?**  
R: Absolutamente. Puedes recuperar un objeto `WeekDay` de un calendario existente y agregarlo a otra instancia de calendario.

**P: ¿Necesito volver a cargar el proyecto después de actualizar los días laborables?**  
R: No. Los cambios se aplican directamente al objeto `Project` en memoria; solo guarda el proyecto cuando termines.

**P: ¿Qué versión de Aspose.Tasks se requiere para la manipulación de días laborables?**  
R: Todas las versiones recientes (20.10 y posteriores) soportan la API completa de días laborables. Recomendamos usar la última versión estable para obtener el mejor rendimiento.

---

**Última actualización:** 2026-11-19  
**Probado con:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose

## Tutoriales relacionados

- [Agregar calendario al proyecto con Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [Determinar días laborables y horas laborables con Aspose.Tasks](/tasks/java/calendars/working-hours/)
- [Crear excepciones de calendario personalizadas con Aspose.Tasks for Java](/tasks/java/calendar-exceptions/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}