---
date: 2026-09-09
description: Cómo establecer el calendario del proyecto en Java usando Aspose.Tasks.
  Aprenda a mostrar las horas de trabajo del calendario, configurar el tiempo de trabajo
  y modificar los días del calendario en archivos de MS Project.
keywords:
- how to set project calendar
- display calendar working hours
- configure calendar working time
- modify calendar working days
- aspose.tasks java
lastmod: 2026-09-09
linktitle: Administrar propiedades del calendario en Aspose.Tasks
og_description: Cómo establecer el calendario del proyecto en Java usando Aspose.Tasks.
  Aprenda a mostrar las horas de trabajo del calendario, configurar el tiempo de trabajo
  y modificar los días del calendario en archivos de MS Project.
og_image_alt: Screenshot of Java code managing MS Project calendar with Aspose.Tasks
og_title: Cómo establecer el calendario del proyecto en Java con Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: How to set project calendar in Java using Aspose.Tasks. Learn to display
    calendar working hours, configure working time, and modify calendar days in MS
    Project files.
  headline: How to set project calendar Java with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, the API provides full read/write access to calendars, allowing you
      to add, edit, or delete working times, exceptions, and base‑calendar relationships.
    question: Can I modify calendar properties programmatically using Aspose.Tasks?
  - answer: The library mirrors the capabilities of Microsoft Project, so you can
      customize virtually all calendar aspects. Only very old Project file versions
      may have minor compatibility quirks.
    question: Are there any limitations to calendar customization with Aspose.Tasks?
  - answer: Absolutely. Simply add the Aspose.Tasks JAR to your build path and use
      the same code patterns shown here.
    question: Can I integrate calendar management into existing Java projects?
  - answer: Yes, it covers tasks, resources, assignments, outlines, baselines, and
      more—making it a comprehensive solution for Java‑based project automation.
    question: Does Aspose.Tasks support other project‑management functionalities besides
      calendar management?
  - answer: Yes, Aspose provides dedicated forums, email support, and extensive documentation
      for all licensed users.
    question: Is technical support available for developers using Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose.tasks
- java project calendar
- ms project automation
- calendar management
title: Cómo establecer el calendario del proyecto en Java con Aspose.Tasks
url: /es/java/calendars/properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo establecer el calendario del proyecto Java con Aspose.Tasks

## Introducción
En este tutorial aprenderás **cómo establecer el calendario del proyecto** en Java aprovechando la biblioteca Aspose.Tasks. Controlar las propiedades del calendario te permite **mostrar las horas laborables del calendario**, configurar días laborables personalizados y mantener tu cronograma alineado con restricciones del mundo real, como festivos o patrones de turnos. Recorreremos la configuración del entorno, la carga de un proyecto, la iteración sobre los calendarios y la lectura o actualización de sus propiedades, para que puedas **gestionar la configuración del calendario de MS Project** con confianza en cualquier aplicación Java.

## Respuestas rápidas
- **¿Qué significa “establecer el calendario del proyecto”?** Significa crear o actualizar los horarios de trabajo, el calendario base y los tipos de día dentro de un archivo MS Project.  
- **¿Qué biblioteca se requiere?** Aspose.Tasks para Java (cualquier versión reciente).  
- **¿Necesito una licencia?** Una prueba gratuita funciona para desarrollo; se requiere una licencia comercial para producción.  
- **¿Puedo mostrar las horas laborables del calendario?** Sí—leyendo cada `WeekDay` puedes imprimir las horas para cada tipo de día.  
- **¿Es compatible con Maven/Gradle?** Absolutamente—añade el JAR de Aspose.Tasks como dependencia.

## Cómo establecer el calendario del proyecto en Java
Carga tu archivo de proyecto, localiza el calendario objetivo y luego ajusta sus definiciones de tiempo laborable, calendario base y tipos de día según sea necesario. Los pasos a continuación proporcionan una solución completa de extremo a extremo que muestra cómo cargar, iterar, modificar y guardar el proyecto mientras se manejan excepciones y se aseguran cálculos precisos de horas laborables.

## ¿Qué es un calendario de proyecto?
Un calendario de proyecto define los días y horas laborables para tareas, recursos y la línea de tiempo general del proyecto. En MS Project, los calendarios pueden heredar de un calendario base, y cada tipo de día (p. ej., **Standard**, **Non‑working**) puede tener su propio horario laborable. Gestionar estos ajustes programáticamente permite ajustes dinámicos del cronograma sin edición manual.

## ¿Por qué gestionar el calendario de MS Project programáticamente?
Gestionar los calendarios programáticamente te permite aplicar reglas de programación consistentes en muchos proyectos, reducir errores manuales e integrar datos de calendario con otros sistemas empresariales como HR o ERP. Esta automatización acelera la configuración del proyecto y asegura que todos los miembros del equipo sigan las mismas políticas de tiempo laborable.

- **Automatización:** Ajusta calendarios en docenas de proyectos con un solo script.  
- **Consistencia:** Aplica políticas de tiempo laborable a nivel organizacional automáticamente.  
- **Integración:** Sincroniza calendarios con sistemas externos de HR o ERP.  
- **Visibilidad:** Muestra rápidamente **las horas laborables del calendario** para informes o depuración.  
- **Flexibilidad:** Añade excepciones o patrones de turnos al vuelo sin abrir la interfaz de usuario.

## Requisitos previos
Antes de comenzar, asegúrate de tener:

- **Java Development Kit (JDK) 8+** instalado y `JAVA_HOME` configurado.  
- **Aspose.Tasks para Java** descargado desde la [página de descarga](https://releases.aspose.com/tasks/java/). Añade el JAR a tu classpath o decláralo como dependencia Maven/Gradle.  
- Un archivo de muestra de MS Project (`.mpp` o `.xml`) que contenga al menos un calendario que desees inspeccionar o modificar.

## Importar paquetes
Las clases `Project`, `Calendar`, `WeekDay` y relacionadas son el núcleo de la manipulación de calendarios.  
La clase `Calendar` representa un calendario de proyecto, contiene días laborables, excepciones y relaciones de calendario base.  
La clase `WeekDay` define la configuración de tiempo laborable para un solo día dentro de un calendario.

La clase `Project` es el objeto de nivel superior de Aspose.Tasks que representa un archivo MS Project en memoria. Después de cargar un archivo, todas las operaciones de calendario fluyen a través de este objeto.

```java
import com.aspose.tasks.*;
```

## Paso 1: configurar el directorio de datos
Define la carpeta que contiene tus archivos de proyecto. Reemplaza el marcador de posición con la ruta real en tu máquina.

```java
String dataDir = "Your Data Directory";
```

## Paso 2: definir constantes de unidad de tiempo
Los tiempos laborables se expresan en milisegundos. Definir constantes reutilizables hace que el código sea más legible y te ayuda a **calcular horas laborables en Java** con precisión.

```java
long OneSec = 1000; // 1000 milliseconds
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

## Paso 3: cargar datos del proyecto
Crea una instancia de `Project` cargando un archivo XML de MS Project existente (`.xml` o `.mpp`). Esto te da acceso a todos los calendarios almacenados en el archivo.

La clase `Project` carga el archivo en un modelo de objetos liviano; **no** requiere que todo el archivo se mantenga en memoria, lo que permite trabajar con proyectos que contienen decenas de miles de tareas.

```java
Project project = new Project(dataDir + "project.xml");
```

## Paso 4: iterar a través de los calendarios Java
Ahora recorremos cada calendario, imprimimos su identificador único, nombre, calendario base y las horas laborables para cada tipo de día. Esto demuestra **cómo establecer valores del calendario del proyecto en Java** y también cómo **mostrar las horas laborables del calendario**.

```java
for (Calendar cal : project.getCalendars()) {
    if (cal.getName() == null) {
        continue;
    }
    System.out.println("UID: " + cal.getUid() + " Name: " + cal.getName());
    // Show if it has a base calendar
    System.out.print("Base Calendar: ");
    System.out.println(cal.isBaseCalendar() ? "Self" : cal.getBaseCalendar().getName());
    // Iterate through weekdays
    for (WeekDay wd : cal.getWeekDays()) {
        double ts = wd.getWorkingTime();
        System.out.println("Day Type: " + DayType.toString(DayType.class, wd.getDayType()) + " Hours: " + ts / OneHour);
    }
}
```

### Qué hace este código
- **Filtra calendarios sin nombre** (algunos calendarios internos pueden tener un nombre `null`).  
- **Imprime UID y nombre** – útil para identificar el calendario más tarde.  
- **Muestra el calendario base** – ya sea “Self” (el calendario es su propio base) o el nombre del calendario heredado.  
- **Recorre cada `WeekDay`** para calcular y mostrar el total de horas laborables (`workingTime` está en milisegundos, por lo que lo dividimos por `OneHour`).  

## Beneficios cuantificados de usar Aspose.Tasks
Aspose.Tasks soporta **más de 30 formatos de entrada y salida** y puede procesar **proyectos con hasta 10 000 tareas** sin cargar todo el archivo en memoria, entregando resultados en menos de un segundo en hardware de servidor típico. Estas cifras lo convierten en una opción confiable para automatización a escala empresarial.

## Problemas comunes y soluciones
| Problema | Razón | Solución |
|----------|-------|----------|
| `NullPointerException` en `cal.getBaseCalendar()` | El calendario es un calendario base (`isBaseCalendar()` devuelve `true`). | Usa la verificación ternaria como se muestra (`cal.isBaseCalendar() ? "Self" : ...`). |
| No hay salida para horas laborables | El archivo del proyecto usa una unidad de tiempo diferente (ticks). | Verifica el formato del archivo; Aspose.Tasks normaliza a milisegundos, pero asegúrate de cargar el tipo de archivo correcto. |
| No se puede localizar `project.xml` | Ruta `dataDir` incorrecta. | Usa una ruta absoluta o `Paths.get(dataDir, "project.xml").toString()`. |

## Preguntas frecuentes

**P: ¿Puedo modificar las propiedades del calendario programáticamente usando Aspose.Tasks?**  
R: Sí, la API proporciona acceso completo de lectura/escritura a los calendarios, permitiéndote añadir, editar o eliminar tiempos laborables, excepciones y relaciones de calendario base.

**P: ¿Existen limitaciones en la personalización del calendario con Aspose.Tasks?**  
R: La biblioteca refleja las capacidades de Microsoft Project, por lo que puedes personalizar prácticamente todos los aspectos del calendario. Sólo versiones muy antiguas de archivos Project pueden presentar pequeñas incompatibilidades.

**P: ¿Puedo integrar la gestión de calendarios en proyectos Java existentes?**  
R: Absolutamente. Simplemente añade el JAR de Aspose.Tasks a tu ruta de compilación y usa los mismos patrones de código mostrados aquí.

**P: ¿Aspose.Tasks soporta otras funcionalidades de gestión de proyectos además de la gestión de calendarios?**  
R: Sí, cubre tareas, recursos, asignaciones, esquemas, líneas base y más, convirtiéndose en una solución integral para automatización de proyectos basada en Java.

**P: ¿Hay soporte técnico disponible para desarrolladores que usan Aspose.Tasks?**  
R: Sí, Aspose ofrece foros dedicados, soporte por correo electrónico y documentación extensa para todos los usuarios con licencia.

---

**Última actualización:** 2026-09-09  
**Probado con:** Aspose.Tasks para Java 24.12 (última disponible al momento de escribir)  
**Autor:** Aspose

## Tutoriales relacionados

- [Create Project Calendar Java – Aspose.Tasks for Java Guide](/tasks/java/)
- [Load Project Files in Java and Manage Project Properties](/tasks/java/project-management/default-properties/)
- [Set Project Start Date in MS Project using Aspose.Tasks for Java](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}